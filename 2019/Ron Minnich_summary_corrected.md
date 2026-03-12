• Introduction to Ron Min nick and his role as the "godfather of open firmware"
• History of open firmware: its beginnings, development, and evolution
• Early challenges in developing open firmware: licensing issues, limited flash memory, and self-defining hardware limitations
• The VA Linux cluster project: a frustrating experience that led to the development of a more robust open firmware solution
• Development of the original Linux BIOS and its growth over time to accommodate changing DRAM requirements
• Collaboration with other experts in the field, including Stefan Reindeer and Ying HAI Liu, to overcome technical challenges
• Discussion of DRAM training and its complexity
• DRAM training requiring billions of instructions
• BIOS attempting to cache computed parameters for DRAM training
• Comparison of DRAM training time to UEFI time
• Concerns about DIMM failures and the robustness of DRAM training parameters
• The shift from open-source knowledge to binary blobs in firmware development
• The importance of open source repositories like Linux, BIOS, and Core boot
• Open source community and social networking
• Exhaustion with pull requests and commercialization of open source
• Root project goals: simplify build process and make systems more accessible
• Binary blob barrier in open source development
• Complexity of modern operating system build processes (e.g. Gen2)
• Importance of understanding source code, not just dependencies
• Difficulty building systems from first principles today
• Complexity of Rust and LLVM
• Ken Thompson's C compiler from Plan 9 as an example of compactness
• Trusting trust concept and avoiding vulnerabilities in the C library
• Ken's code philosophy and its impact on writing simple, efficient code
• Unix philosophy and its influence on coding style and thinking
• History of exposure to Plan 9 and Unix, including the PDP-11/45 computer
• First computer experience in 1969
• Built relay computers and later leased HP 2100 machine from Lease Co
• Used ASR 33 paper tape punch and reader
• Had Dr. Him, a plastic device that played the game of Him using marbles as input bits
• Worked with other digital devices from ESR company, including Thinkable and Digicam
• Learned Boolean algebra and Oregon's theorem through Digicam
• The speaker's first exposure to computers was through the Digicam 1 and Dr. Him
• They mention ESR (Electronic Systems Review) and Wikipedia as resources for learning about early computer history
• The ENIAC, a pre-computer device that used logic equations and plug boards, is mentioned as another early influence
• The speaker discusses the importance of limitations in design, allowing for careful thought and creativity
• A digital clock designed by an artist in France using LEDs and flip-flops is mentioned as an example of visually clear computation
• The conversation touches on the idea that the fundamental principles of computation have not changed, despite advancements in technology.
• The concept of quantum supremacy and its impact on society, with a humorous comparison to ritual suicide
• Criticism of people who think that writing code in C for a BIOS is impossible
• Discussion of the limitations of early computers, such as the 1145 machine, and how Unix was used as firmware
• Contrast between old methods of finding interrupt routing (literally poking registers) and modern approaches (using megabytes of software)
• Commentary on the loss of simplicity in computer design and the tendency to use complex workarounds
• Discussion of a complex system and a proposed solution to "paper over" its mess through firmware
• Importance of simplicity and powerful abstractions in systems design
• Comparison of Unix to other operating systems, including Windows NT
• Unix's innovative approach to resource management and abstraction (e.g., dev TTY)
• The significance of being able to treat resources as files or devices
• Mention of Plan 9 and its similarity to Unix
• Unix's complexity and the idea that it would replace monoliths with simplicity
• The concept of a synthetic file system introduced in the 1980s
• Plan 9's development and how it addressed some of Unix's issues by providing better abstractions for namespaces and resource management
• Rob Pike's talk on naming and how putting a host name in a path can be problematic
• AT&T's handling of Plan 9's release, which took over 25 years due to various issues
• The decision not to release Unix was made by company leaders who feared losing control
• AT&T's Unix could have died without the widespread availability of its abstractions
• The future looked like an IBM mainframe in the late 1970s, with plug compatibles and IBM dominance
• DARPA announced they would only fund Windows NT efforts around 1998
• A developer was told to focus on Windows development due to market trends
• Unix is now seen as a complex, dying system, while everyone mortgages their future to Windows
• The current trend of everything being on AWS may be similar to the IBM mainframe era
• Open-source software tends to win in the long run
• Linux eventually became widely used for serious work and infrastructure after being dismissed as a "toy"
• X86 was initially underestimated by the industry.
• Intel's accomplishment in achieving high-performance x86 architecture is recognized.
• Power PC and Alpha processors had higher clock rates, but x86 eventually surpassed them.
• A cluster of x86 Linux BIOS nodes demonstrated high uptime and reliability at a lower cost than traditional machines.
• The concept that you can buy a better cluster at a fraction of the cost of expensive machines is discussed.
• The speaker recounts a situation in the early 1990s where they presented a cluster game to a government agency and proposed using commodity workstations instead of expensive vector Cray machines.
• The speaker explains that reducing costs in government budgets often means increasing personnel costs, which was why their proposal was met with anger.
• The agency was relying on 5% of users who were running vector cycles to pay for the rest of the system.
• The speaker mentions how commodity clusters eventually replaced expensive vector machines and X86 processors.
• They highlight that commodity PCs can be just as reliable or more so than custom-built systems like Alphas, due to their resistance to cosmic rays.
• The speaker expresses frustration with advertising restrictions imposed by lawyers, including not being able to discuss customer experiences on-premises or in public cloud environments.
• Discussion about using the word "criminal" to describe public cloud vendors
• Reference to a statement from Oxide Computer Company that can be used
• Mention of lawyers being present in a meeting and their opinions on an ad
• Description of a cluster built by Ron, called "pink", which is unpopular due to its danger
• Story about the VA Linux node taking five minutes to boot and the use of Deep Rock software to improve boot times
• Explanation of how B Proc works, including the use of an ad hoc tree for node communication
• Discussion about a previous network mapping tool that took four hours to run and being replaced by a faster alternative written by Eric Hendricks
• The new tool maps the network in seven seconds
• Issues with booting speed and serial messages printing
• A scalable storage system was purchased but proved to be unreliable when tested under heavy load
• Bad memories about Linux, BIOS, and BP ROC from past issues with cluster systems
• Eric implemented a scheduler that took advantage of his BP ROC ideas and significantly improved cluster performance
• Mirror Net and its development by Chuck Switz
• Description of Mirror Net's features: all-copper network, low latency, high speed
• Explanation of how Mirror Net worked, including source-routed networking
• Discussion of Mirror Net's performance and advantages over other networks at the time
• Reasons for Mirror Net's decline: competition from commodity Ethernet and Infiniband
• Patrick Joffrey and Miracom's work showing OS bypass isn't necessary for all applications
• Infiniband (IB) was touted as the "Ethernet of HPC" but ultimately became just another type of Ethernet due to lack of vendor competition
• Most companies, including Eleanor, now use a similar underlying technology to IB but label it as Ethernet
• The FI (fabric interface) used by many networks was originally licensed from Dolphin and has since been widely adopted
• IB itself is complex and difficult to configure, leading to humour about its adoption by national labs due to their access to postdocs who could handle the setup
• Discussion of difficulties with Infinite and the Linux kernel patch
• Criticism of large, complex codebases (14 million lines in one example)
• Proposal to start from scratch on firmware development
• Appreciation for the open firmware movement's emphasis on simplicity and necessity
• Mention of Intel releasing firmware called "ignition"
• Intel engineers spearheaded getting redistributable firmware done
• Four Intel engineers were involved in the process
• The company's note about ignition firmware was widely shared and seen as a positive step forward
• There are still challenges with getting firmware changes approved due to organizational barriers
• The speaker has personal experience asking Intel about open firmware, but was met with reluctance due to lack of empowerment among certain employees
• The importance of open source firmware and the issue with proprietary blobs
• The impact of security issues like Spectre and Meltdown on Intel's acceptance of open firmware
• A personal anecdote from 20 years ago where the speaker demonstrated a method to embed a secret message in flash, highlighting potential vulnerabilities in firmware
• The initial dismissal of concerns about firmware security by some organizations, with claims that certain operating systems (specifically Windows) would prevent such issues
• Chrome books have popularized core boot for mainstream computers
• System 76 laptops run open firmware and are unique in their approach to laptop design
• They are price competitive with other laptops and offer a high level of customization
• The company started from a point of doing things the "right" way, focusing on building open systems that run core boot
• System 76's commitment to openness and transparency allows for easy firmware modification and cloning
• Chrome books have a high degree of configurability
• The ability to reeky a Chromebook with personal keys and build an operating system image
• This property allows the Chromebook to only boot the user's own version of the operating system
• System 76 may potentially take advantage of these properties in the future
• Chrome books have improved significantly since their early days, now offering high-quality hardware and a pleasant user experience
• The speaker uses a Chromebook for work and notes its limitations in terms of memory and NVMe expansion.
• They recall having a Chromebook with 16GB RAM and a large flash SSD, which they considered their main laptop at the time.
• The speaker mentions the benefits of being able to install custom operating systems on Chrome books, including Chrome OS and Web Boot.
• They discuss how Chrome books can discourage experimentation with custom software due to restrictive boot requirements.
• The speaker notes that some interns have successfully installed non-Chrome OS operating systems on Chrome books.
• Discussion of stateless laptops and devices
• Joanna Wachowski's Tails machine and Chromebook/web boot potential
• Advantages of stateless devices, including no data retention
• Scenarios where a stateless device is beneficial (e.g. for journalists in high-risk situations)
• UEFI reboot network stack issue with DMA causing corruption in RAM
• Difficulty debugging firmware bugs when they affect the operating system
• The speaker mentions a fictional scenario where a company strangles one of its vendors due to pain caused by running on premises.
• The conversation shifts to discussing Chrome books and open firmware, specifically in relation to the server space.
• The speaker talks about his involvement with the Open Compute Platform (OCP) and its incubation committee, which evaluates new standards for OCP.
• He mentions his previous role as project leader for the Open System Firmware Project, now officially a part of OCP.
• The speaker discusses the requirements for an OCP server to have OCP accepted branding, including the ability to replace firmware with custom-built versions without permission from ODMs.
• He notes that current servers from companies like Dell and HPE do not allow this level of customization due to restrictions on modifying firmware.
• The concept of boot guard and its effect on firmware updates
• The idea that Intel's design can "brick" devices if the firmware is not properly signed
• The goal of open system firmware to provide a model where devices can "boot, not brick"
• The importance of user control over firmware and being able to verify its authenticity
• The concept of a chain of trust in firmware updates
• Companies are happy with brick-and-mortar servers, not bootable machines.
• Fuses on bootable machines can be problematic and create vulnerabilities.
• Recapping and chip analysis can reveal vulnerabilities for exploitation by malicious actors.
• Large tech companies employ many smart people to solve security problems, but there are more smart individuals outside who can find vulnerabilities.
• The goal is to have open firmware allowing users to control and burn their own firmware, empowering good guys to find vulnerabilities instead of just bad ones.
• The ultimate aim is to create a world where servers are designed for recallability and refurbishment.
• Discussion of the "circular economy" and its goals
• Challenges with recycling servers due to firmware limitations
• Intel's release of FSP firmware support package blobs on GitHub
• Freely distributable firmware blobs for certain chip sets
• Release of ME binary blob, including the ignition variant
• Web server issue
• System Management Mode (SMM) problems and limitations
• Intel's proposed PRM as an alternative to SMM
• Discussion of SMM's history and its role in supporting legacy features like DOS 1.0
• Critique of SMM's bloat and inefficiencies
• Discussion of mouse drivers in a BIOS
• Porting UEFI to RISC-V
• Reasons for implementing UEFI on RISC-V
• Linux's stance on UEFI
• ARM's involvement and requirements for UEFI support
• Replacing UEFI with a Linux kernel and U-Boot
• Criticism of the SMM model on RISC-V architecture
• Admiration for the instruction set design of RISC-V
• Introducing Or boot, a downstream fork of Cor boot without C code
• Using Rust to write firmware code for Or boot
• Loading kernels on the RISC-V-based sci-fi five freedom U board using Or boot
• Compiling Or boot for the open Titan and finding bugs in the Rust code
• Bugs related to atomics on RV 32
• Incorrect handling of processors without atomics by a compiler (Rust)
• Running the kernel in M mode as an experiment, including modifying M mode code and using memory protect area registers
• Discussion about whether not having paging enabled in the kernel is too far to go, considering potential gains and losses.
• Paging enabled and kernel size
• Open Titan and Linux not being used
• Rethinking the need for a traditional kernel
• Building machines with thousands of cores due to per-core license costs
• Questioning the need for virtual machine capabilities
• Exploring possibilities in RISC-V, including proprietary implementations
• Low-cost RISC-V boards and their potential uses
• The explosive growth and innovation in the tech industry, particularly in China
• The advancements in RISC-V processors and their potential to drive innovation
• The limitations of traditional processor design and the need for simpler approaches
• The concept of "2.5D" integration, where different processes are combined on a single die
• The increasing importance of process nodes (7nm, 28nm) and their impact on industry advancements
• End of Moore's Law brings an age of limits
• Innovation can thrive when resources are scarce
• The Linux era was marked by clever solutions due to resource constraints
• Forcing limits on computing will be a good thing for the software ecosystem
• The example of graphics stacks with excessive API layering is given as a cautionary tale against unnecessary complexity
• Limits and constraints can force innovation and creativity
• The importance of being creative in the face of limitations
• Fun times ahead due to innovative efforts
• Gratitude expressed for the guest's appearance on the show
• Show notes and next steps for listeners
• Credits for production team, theme music, and editing