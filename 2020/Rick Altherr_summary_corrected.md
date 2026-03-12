• Introduction and banter between hosts Brian Cantwell and Jess Frizzell
• Interview with guest Rick Alter, who discovered a vulnerability in Supermicro BMCs called USB Anywhere
• Background on how Rick Alter found the vulnerability through research and reverse engineering
• Discussion of the scope of the vulnerability, including 47,000 affected servers worldwide
• Geographic distribution of affected servers, with high concentration in the US
• Contact between Rick Alter and network operators to raise awareness about the issue
• Process of identifying potential targets among the affected servers, without exploiting them personally
• Details on the reverse engineering process used by Rick Alter to discover the vulnerability
• The speaker discussed their experience reverse engineering a system that used a BMC (Baseboard Management Controller) to emulate a USB device
• They identified the external functionality and capabilities of the chip, but needed to understand the in-between steps
• The speaker analyzed packet captures using Wireshark and identified suspicious network traffic
• They implemented their own client to use the protocol for malicious purposes
• The speaker mentioned their love for old computers, specifically Cray supercomputers
• They shared a story about finding a location to put a Cray in their home, but it was just a decorative piece
• Seymour Cray's views on multiprocessors
• History of computers, including CDC machines and Alpha stations
• True64 operating system and its branding
• Running Windows NT on different platforms, including MIPS and Alpha
• Binary compatibility issues with NT on multiple architectures
• FX32 program for converting x86 binaries to run on Alpha
• SGI's marketing efforts and humorous advertising tactics
• Discussion of NT on MIPS and its complexities
• The vulnerability of hanging a BMC (Baseboard Management Controller) on the internet
• Rick's explanation of the BMC's design and vulnerabilities
• The limitations of PMI (Intelligent Platform Management Interface) and Redfish standards
• The potential risks of exploiting a BMC, including system contamination and difficulty in removing the exploit
• Discussion of hardware disposal methods, including shredding and reconditioning
• Risks associated with default BMC passwords and the ease of cracking them
• Vulnerabilities in BMC management systems, such as USB Anywhere and Redfish
• Critique of Redfish's design, including its reliance on internet exposure
• Historical context of PMI and the development process for Redfish
• Redfish has been around for years, but implementation is just starting to show up
• The protocol was created based on industry standards, but it's had issues with security and data interchange
• Implementing Redfish requires running additional software (e.g. HTTP server, JSON parser) which can be complex and error-prone
• The protocol's design does not take into account the constraints of a BMC (baseboard management controller)
• The creators did not engage with operators who actually use these technologies in production environments
• The speaker discusses the feeling of neglect among those who still run on-premises infrastructure due to a perceived shift towards public cloud.
• The speaker emphasizes that there are valid reasons for running on-premises, including security and latency concerns.
• The speaker invites those running on-premises to sign up for their mailing list at Oxide. Computer to discuss their challenges.
• The speaker shares a personal anecdote about a "zombie" bug they inherited from a previous team that was caused by an alert pin not clearing after a power cutover.
• The speaker explains the technical details of how the bug manifested and its persistence.
• Discussion of a hardware bug in a machine that caused it to not power off
• Bug was reproducible and considered "psychotic" due to its unexpected behaviour
• Realization that the issue was due to a design decision locked into the hardware
• Exploration of ways to fix or work around the problem, including clearing a flag with a cron job
• Discussion of the challenges of dealing with hardware bugs and covering them up
• Discussion of who wrote a cron job
• Explanation of the role of firmware in hardware and failure scenarios
• Description of experience with hardware failures at hyperscalers, including equipment catching fire
• Explanation of how hard drives work and a specific mistake made by a manufacturer regarding calculations for fly height during writes
• Natural air creates turbulence issues with drive platters
• Helium used as alternative due to lower drag and ability to fly closer
• Surface impurities on hard drives can cause head crashes at high RPMs
• Failure mode: head deformation from repeated impacts
• Importance of accurate firmware control for mechanical hardware interactions
• Designing hardware for safety when interacting with software that may fail
• Comparison of safe vs. critical systems, where intrinsic design is prioritized
• The book "He who must not be named" has a good story about hackers accessing a Xerox machine
• Open source firmware is discussed, including the open source firmware conference attended by Jess and Rick
• The future of open source firmware is considered, with thoughts on its potential to become more widespread and accepted
• Security concerns are mentioned as a potential barrier to fully open-source firmware
• Examples of successful adoption of open-source firmware in Chrome books and Open BMC are shared
• Open source firmware is thriving in BMCs (baseboard management controllers) and BIOS
• Silicon vendors resist sharing documentation due to concerns about trade secrets and hardware design
• The concept of "blobs" that provide pre-built libraries rather than raw documentation is discussed
• A historical analogy is made between ODM manufacturers and the existing 19-inch rack standard, with a humorous discussion about horses' butts
• The Open Compute Project (OCP) has grown and gained momentum with the involvement of hyperscalers like Google and Microsoft
• OCP partners are working on reference designs that can be adapted for others to use
• Google's infrastructure development and manufacturing partnerships
• "Infrastructure privilege" and how hyperscalers don't understand pain of off-the-shelf hardware
• ODMs (Original Design Manufacturers) still involved in design contributions for companies like Facebook
• Refurbished systems being sold by companies that buy decommissioned equipment
• Open Compute Project (OCP) goals to allow non-hyperscalers to access infrastructure
• Complexity of software story with OCP, particularly regarding Kubernetes
• Security awareness and pushing for secure firmware in the server space
• The speaker mentions that the open firmware movement will continue to grow and that they hope OSF (Open Source Firmware Conference) will be bigger next year.
• They express a fondness for the European feel of the conference and suggest that changing the currency from euros to something else would alter this feel.
• The speaker shares a humorous anecdote about being "egg drunk" at Facebook, implying an overindulgence in their eggs during breakfast.
• They participated in a firmware hackathon where they resoldered a component, describing it as one of the best experiences of the conference.
• The conversation turns to security and vulnerabilities in lower-level software systems, with one person asking if others are concerned about this issue and how to assess exposure.
• The security landscape for system firmware is poor due to a lack of attention and expertise
• Supply chain attacks against machine vendors are difficult to solve and may not be prioritized by smaller companies
• The industry's approach to web security has been successful in identifying common problems, but this mindset needs to be applied to system firmware
• Spectre and Meltdown helped raise awareness about firmware vulnerabilities, but most press attention was focused on the bugs' implications for hardware rather than firmware itself
• Mitigating firmware vulnerabilities can take months or even years, unlike software patches which are typically resolved within days or weeks
• As cloud-like systems become more prevalent, there may emerge a set of best practices and common security considerations for infrastructure providers
• The shift to multi-tenancy and shared resources in cloud environments is changing the way security responsibilities are distributed among stakeholders.
• Vulnerabilities in security features due to misconfiguration or lack of enablement
• End of interview/conversation with guest Rick
• Show notes and contact information for listeners
• Credits for production team, theme music, and editing/publishing company