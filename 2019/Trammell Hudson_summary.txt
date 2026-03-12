• Introduction to Trammell Hudson and his background
• Discovery of hardware-software interface through work at Sandia National Labs
• Development of custom operating system for supercomputers
• Building lightweight kernel to optimize resource usage
• Discussion of various CPUs used in early projects, including i-60, i-860, and Pinium Pro
• The speaker discusses the difficulties they faced with a specific Linux kernel patch due to the rarity of the CPU it was for
• The ASCII Red Storm and Opturon-based systems are mentioned as significant projects that utilized tightly coupled networks and DMA engines for improved performance
• The importance of network performance in HPC machines is emphasized, especially given the limited memory available at the time
• The speaker describes a distributed system architecture where most nodes had no external connections and were used solely for compute tasks
• This approach allowed for efficient management and administration of tens of thousands to hundreds of thousands of cores with a small staff
• Firmware development is introduced as an area of focus, particularly through work on the ASCII Red Storm and Portals projects
• The speaker reflects on the realization that there are multiple layers of software beneath what appears to be the lowest level, including firmware and ring levels within CPUs.
• Firmware at low system level can control entire system
• Hidden pieces inside commodity machine between SMM and management engine
• Unexamined code with too much privilege in BMC or embedded controllers
• Concerns for runtime security and resale/decommissioning
• Mod chips of the state: possibility of hardware implants on spy bus
• Spy bus timing-critical bus requiring programmable hardware
• FPGA tool for timing-critical hardware interface projects
• Spy Spy flash emulator for poking at systems during boot-up
• Hacker News's failure to report on Spy Spy
• Importance of early boot time security and potential attack vectors
• Role of the management engine in firmware validation and user freedom trade-offs
• Tension between system security and user freedom to modify firmware
• Potential solutions with attestation, allowing systems to prove their startup code
• Examples of secure-by-default systems and those that prioritize user freedom
• Design of Chromebooks was revolutionary in open source security
• Importance of attestation in non-mobile space using TPMs (Trusted Platform Modules)
• Explanation of what a TPM is and how it works
• Chain of trust in boot process and potential vulnerabilities
• Limitations of commodity firmware in maintaining chain of trust
• TPMs are not highly tamper-resistant
• Physical attacks on TPM chips have been demonstrated, including decapsulation and access to the LPC bus
• The "evil maid" attack is a realistic threat model for laptops left unattended in public places
• Chromebooks use the Titan chip as both a TPM and closed case debugger, allowing for secure firmware updates and debugging via USB
• Some features of the Titan chip are not well-documented but have been reverse-engineered by enthusiasts.
• On-premises infrastructure still has its uses, including security and latency benefits
• Neglect and misconceptions about on-premises infrastructure lead to a "feeling of neglect"
• People running on-premises infrastructure may feel ignored by the industry
• Open-source firmware movement is growing in interest and adoption
• Linux BIOS project started by Ron Minnick at Los Alamos National Labs was a precursor to current open-source firmware efforts
• Intel's recent introduction of the "Linux Boot" project allows for faster boot times using Linux on commodity hardware
• Open firmware movement gaining critical mass
• Linux booting all-in-one system enables engineers from various backgrounds to work together
• Importance of open source in hardware development, particularly in the server space
• RISC-V and its potential for creating a completely open-source system
• OpenTitan project's announcement and its significance in making security coprocessors more accessible
• Criticism of proprietary toolchains and closed-source FPGA environments
• Open-source movement and its tools
• Advantages of open-source development for FPGA work
• Recommendations for getting started with FPGA exploration
• Low-cost, open-source FPGAs such as Ice40 and Upduino V2
• Retro computing projects using FPGAs (e.g. emulating old consoles)
• Discussion of PDP-10, PDP-11, and PDP-8 replicas built on newer silicon
• Craigslist sale of a PDP-11
• Discovery of an entire data center's worth of hardware in storage
• Theft theory, as the items were likely stolen and then stored
• Purchase of multiple PDP-11s, terminals, printers, and floppy disks
• Restoration process, including cleaning out a locker and getting systems bootable
• The archive.org website has been updated with various materials
• Discussion of the Opnix system, which ran RT11 for real-time OS needs
• A nine-track tape labeled "digitized monkey brains" was found but unable to be read
• Several other finds include:
  • Eight-inch floppy drive and disk packs working properly
  • Email schools that were not uploaded to the archive
  • A draft of a speech about buying a computer for a medical department
• A physician discovered he loved software programming
• He spent his free time writing BASIC programs for data analysis and processing
• The PDP-11 is discussed as a fun system to work with
• Teletypes, including the ASR-33, are mentioned as being used during this period
• The connection between teletypes (TTYs) and Unix's origins is noted
• Discussion of using an emulated PDP-11 on a Raspberry Pi to run a teletype.
• The limitations of the ASR-33 teletype's mechanical keyboard, which prevents multiple keys from being pressed simultaneously.
• Explanation of the 110 baud rate and its impact on typing speed.
• Description of the distance and propagation time for signals between the teletype and machine.
• The device being discussed is an old computer that uses a mechanical mechanism to enforce its baud rate.
• The speaker compares the computer's operation to steam-powered computing and describes it as steampunk-like.
• The software on the computer was designed for hardware that requires oil and grease, but the software has persisted even though the original hardware is obsolete.
• The speaker quotes a Unix newsletter about 10 installations of the system around the world, and notes that this number is expected to grow.
• Longevity of Unix philosophy and its implementation in various systems
• Distributed systems vs single systems approach
• Creative sourcing of equipment for projects, including Craigslist and storage lockers
• Reverse engineering old machines and dumping ROMs to uncover hidden information
• Discovering interesting features such as bitmap fonts, icons, and Easter eggs in old firmware
• Importance of documenting tools and processes for others to replicate and learn from
• Need to ensure projects are easily transferable to other developers
• Successful projects often involve handing over control to the community
• Documenting process not only helps future self but also enables others to continue work
• Open source allows building on top of previous work and enables learning through experimentation
• Matthew Garrett's experience with computers is limited, but he enjoys experimenting and "banging against problems"
• He has been working on a project involving ZigBee encryption protocols
• The documentation for these protocols is written in prose, making it difficult to understand
• ZigBee is used in IoT applications, such as smart home devices
• Matthew Garrett is creating a system that allows users to write custom firmware extensions for IKEA smart devices
• The goal of the project is to enable users to control their devices offline, reducing dependence on the internet
• Light bulb firmware incompatibility and Philips' decision to break compatibility
• Discussion of different protocols (Zigbee, Bluetooth) used by Hue Bridge and light bulbs
• Canon camera firmware reverse engineering and loading new code on an SLR camera
• Discovering a developer mode or debug mode that allows running custom code without modifying the camera's ROM
• The speaker discovered a debug mode in firmware that allowed them to run code without reflashing the camera
• The debug mode was activated by renaming the SD card with a specific string
• The discovery of the debug mode was made through reverse engineering of the boot path in the firmware
• Debug strings can be useful for reverse engineers, and the speaker notes that they were able to understand the behavior of the system by examining these strings
• The idea of vendors embedding unique strings in their products to track reverse engineering efforts is discussed, with one example being Colin Molnar's talk on using Google AdWords for tracking
• Discussion of a bug in Google's ad system that charges users unexpectedly for viewing ads.
• Author's own project involving reverse engineering Canon camera firmware.
• Porting the project from the Canon 5D Mark II to the T2i, and its impact on community development and user interest.
• Handing over the commit keys to Alex, who continued the project after the author's involvement.
• The project's 10th anniversary celebration.
• Canon's potential knowledge of and response to the project.
• UEFI preboot network stack issue causing corruption in RAM disk
• Trying to explain a tweet about the issue to their boss, Steve Tuck
• Discussion of running on-premises systems and encountering firmware bugs
• Need for a new computer company that doesn't sell PCs
• Introducing Oxide Computer Company as a solution to on-premises pain points
• Switching back to discussing hardware-software interfaces with guest Trammell Hudson
• Discussion of Home Assistant, an open-source home automation system
• Comparison with other systems, including Node-RED and Mozilla IoT gateway
• Reverse engineering of IKEA Zigbee devices and building a custom Zigbee stack in Python
• Concerns about the complexity and potential security risks of smart home automation
• Preference for simple manual controls over automated systems
• Discussion of the idea of hiring a remote sysadmin to control smart home devices
• LED panel features: gradual brightness adjustment and color temperature change
• Localized heating control for specific rooms
• Power usage tracking and monitoring
• Reverse engineering of firmware update protocol
• Ability to modify firmware in place without physical reprogramming
• Security concerns with internet connectivity and potential hacking risks
• Discussion of the relative concern of hacking a device versus preventing it from being hacked
• Analysis of a specific gateway's design, which connects to the internet but still functions without network access
• Comparison between this gateway and other devices that require constant internet connectivity
• Concerns about local attackers targeting devices on a home network
• Proposal to limit devices' surface area by keeping them off the internet as a security measure
• Criticism of device manufacturers prioritizing internet connectivity over security
• Digital sovereignty and control over devices and networks
• Importance of containing automation devices to controllable networks
• Need for controlling firmware and root of trust on servers and laptops
• Detection of modifications to devices or firmware
• Trade-offs between digital sovereignty and other considerations
• Intel boot guard issue where a bad Dixie allowed unsecured booting
• UEFI firmware organization and potential vulnerabilities in different firmware volumes
• Discussion of a side channel attack and how it can be mitigated by installing microcode without OEM involvement
• Explanation of a UEFI reference code vulnerability that allowed malicious code to run without measurement or validation
• Description of a boot guard mechanism designed to measure and validate boot components, but vulnerable to exploitation due to legacy implementation issues
• Discussion of the consequences of exploiting this vulnerability, including loading arbitrary payloads and bypassing security measures
• Disclosure of a time-of-check-time-of-use (TOCTOU) vulnerability in the boot guard mechanism, allowing for hardware-based bypass via an FPGA
• The challenges of achieving hardware trust and full firmware verification in the server space
• Use of high-level languages like Go and Rust to implement hardware trust solutions
• Project Orboot, a Rust implementation similar to Corboot, and its presentation at OSFC
• Discussion of various online platforms for finding and staying up-to-date with Trammell's projects and schedule
• Recap of Trammell's contributions to the field of hardware software interface and his documentation of his work
• Wrap-up of a podcast episode
• Thanking listeners and guests
• Mention of show notes and website for more information
• Credits for production team, theme music, and editing
• Oxide Computer Company's projects and tools
• Future episode plans