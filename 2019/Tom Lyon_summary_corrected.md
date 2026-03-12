• Guest Tom Lyon introduces himself and brings a gift of an IBM mainframe ready light
• Discussion about the origin of "ready" versus "idle" terms for computer states
• Tom's collection of computing artifacts, including a 26-inch and 31-inch magnetic platters from 1961
• Criteria for collecting rotating media, with the goal of having one of every size made
• Discussion on the challenges of large-scale data storage, including angular momentum and temperature fluctuations
• Discussion about a machine from Burroughs and Data Products
• Memory tubes from an IBM 704, including CRT displays with detectors to read back bits
• Phosphorescence-based memory storage and refresh mechanism
• Comparison to DRAM technology
• Mercury delay lines as an early form of memory
• Explanation of how mercury delay lines work using a wave in a vat of mercury
• Discussion of the volatility and challenges of working with mercury delay lines
• Inefficient early hardware design led to difficulties in debugging and development
• Software refresh memory was used, which was later obsoleted by Sun's hardware advancements
• Andy Bechtolsheim's approach to hardware design was discussed, including his belief that the processor could handle address implementation
• The origins of Network File System (NFS) were mentioned, with the architecture being drawn on a whiteboard in 1984 and still remaining largely intact today
• The concept of network storage was considered radical at the time, but had precursors in the Xerox Alto world and Data Point
• Data Point's claim to having invented the microprocessor, personal computer, and local area network (Artnet) was discussed
• Unix's growth on Artnet and its later support for the technology
• AppleTalk, including its implementation and challenges
• Comparison of AppleTalk with other protocols such as TCP/IP and IBM S&A
• The development of Sun's DMA-based board and AppleTalk implementation
• The use of AppleTalk in devices like the Mac and Laser Rider
• The evolution of TCP/IP and its superiority over other protocols
• Interoperability of TCP and its importance for success
• Open-source nature of TCP and NFS contributing to their adoption
• Importance of a protocol specification in making the protocol work
• Novel emphasis on interoperability at the time
• NFS as connective tissue between different machines, including mainframes and PCs
• Criticism of NFS due to poor implementation or automounter issues, but not necessarily inherent flaws in the protocol itself
• CAP problems stem from partitions or transients in the network
• NFS vs POSIX compatibility, with POSIX being less compatible with networks
• The CAP theorem's fundamental importance for addressing semantics on a network
• The liberating realization that CAP is not solvable and requires trade-offs between consistency, availability, and partition tolerance
• Early NFS design decisions prioritizing availability over consistency due to limitations in understanding the CAP theorem at the time
• Comparison of file-based (NFS) vs block-based storage protocols (Fibre Channel, iSCSI)
• The original network disk (ND) protocol's flaws and its eventual replacement by NFS
• Object storage and file semantics
• Relaxing consistency for scalability
• POSIX compatibility limitations
• History of TCP development and congestion control
• The "great internet collapse" of 1986
• Van Jacobson's congestion theorem-based exponential back off solution
• Comparison of lossless networks (X.25) vs. TCP/IP
• Larry Roberts' role in ARPANET and his preference for lossless networks
• Engineer's appeal to reliability through guaranteed delivery of packets
• Ethernet fabrics vs PCI Express fabrics
• Reliability built into link layer vs best effort approach
• Advantages and disadvantages of network fabrics over traditional buses
• PCI-based fabrics as a solution for simplifying servers and reducing complexity
• Challenges with cabling and partitioning in network architectures
• Comparison between public cloud and on-premises computing
• Mention of Oxide. Computer website and mailing list
• Discussion of Ethernet history and competing networking substrates (802.x standards)
• Introduction of token ring and IBM's involvement in its development
• Personal anecdote about implementing token ring drivers and demonstrating TCP/IP and NFS on token ring at Comdex
• Description of hacking a VME bus to CAT bus adapter for the Sun 4
• Humorous story about being mistaken for a suit due to wearing a business suit at Comdex
• Mention of the success of token ring in the market
• Token ring networks, an alternative to Ethernet
• How token ring works: polling system with a token passed around nodes
• Advantages of token ring: orderly, efficient, and reliable message delivery
• Disadvantages of token ring: complex error recovery procedures, potential for lost tokens
• History of token ring: IBM, Protein, FDDI (100 megabit optical), Artnet, etc.
• Why token ring didn't win out over Ethernet: complexity, economics, and ultimately replacement by faster Ethernet technologies
• The narrator's first experience with computers and programming was through their father bringing home a Fortran manual
• They gained access to a CDC 3100 computer at the university, which led to an interest in computing and engineering
• The narrator comes from a family of engineers and academics, which influenced their career choices
• Several of the narrator's siblings pursued technical careers, with some notable accomplishments in fields like programming and hearing research
• Distributed systems
• Personal background and experience with Legato startup, Sun Microsystems, and NFS group
• Navigating hierarchical work structures and reporting to a sibling
• Early experiences with computers and programmable calculators (Olivetti Programma 101)
• Comparison of calculator brands and generational differences in first loves for calculators or other technology
• Cheating with calculators on exams
• Early HP calculators (HP 35, HP 48) and their impact on math education
• Large family dynamics and birth order (six of nine siblings)
• Parental influence on children's interests in technology and science
• Growing up with limited access to personal computers and longing for one
• Saving money to buy a computer and the excitement of having one
• Early computer systems and mainframes
• Porting Unix to mainframes at Dahl
• Founding of Sun Microsystems
• Differences between mainframe and personal computers
• The "Halt and Catch Fire" era in Silicon Valley
• Technical advisors on TV shows and authenticity
• Personal preference for tabs vs. spaces in coding
• Preference for hard tabs versus spaces in coding
• Origins of bias towards hard tabs due to Unix background
• Importance of adapting to community conventions and editor settings
• Discussion of Vim, ED, and Emacs editors
• Personal experiences with learning and using different text editors
• Porting Unix from PDP 11 to the IBM 370 at Princeton
• First Unix port ever attempted (according to recent findings)
• Work on APL 360 time-sharing system at Princeton Computer Centre, including operating an APL keyboard with custom font and characters
• Discussion of APL's origins in math, its dense information presentation, and comparison to K programming language
• Description of APL's unique character set and typing requirements for pre-ASCII era
• The speaker and a group of Unix users suggested installing a PDP-1170 with a time-sharing system on campus
• Computer centre reacted negatively, not knowing about Unix or PDP systems
• IBM offered an additional 370 due to Princeton's high profile status
• Virtual machines were used, but the Unix gang was initially disappointed
• A C compiler was discovered at Bell Labs, making it possible to port Unix to the mainframe
• Eric Schmidt organized a project and arranged for credit and technical work
• The speaker worked on demonstrating a shell and kernel on the mainframe, but was hindered by networking issues
• Long serial lines and analog concepts were unfamiliar to the speaker as a digital specialist
• Virtual machine setup for porting Unix to PDP 11
• Porting difficulties and testing process
• Fork working successfully in a shell environment
• Interview process at Dahl and meeting Ken Thompson
• Porting Unix to the Interdata and being impressed by Tom's work
• Working with the Unix group during the summer of '75 or '76
• Serendipitous events leading to job opportunities at Dahl
• Converting V6 into portable V7 and its widespread adoption
• Lawyers are restricting discussion about public cloud customer experience and unit economics
• The company has received a statement from lawyers that can be used to summarize their response
• Discussion of the rapacious bandwidth pricing of public cloud vendors is being censored
• The conversation takes a tangent discussing Bell Labs in its heyday, hiring 30% of all PhDs in the US
• The speakers reminisce about working at Bell Labs and encountering talented individuals such as Greg Cresson
• Discussion about Joseph Osaka's death and the possible circumstances surrounding it
• Mention of Brian Caravan's book on Enough and its potential explanation for some of the code's mysteries
• Porting of Enough from Assembler to other languages and platforms
• Analysis of Enough's code, which contains "magic numbers" and appears to be loosely typed
• Story about Brian Caravan's experience trying to modernize Enough and its surprising complexity
• Discussion of the software's permanence despite hardware changes and its origins in the 1970s
• Explanation of Roth's history, including its development from the CTSS system and a version written by Brian Kernighan for an IBM mainframe
• Personal anecdote about using the IBM mainframe version of Roth to write papers at Princeton
• Main pages written in original language
• Use of macros on main pages
• Printing on IBM line printers (IBM 1403)
• Early computer technology from 1959-1960s
• Restoration of an IBM 1403 at a computer museum
• Porting Unix to mainframes at Dahl
• Interview process and arrival at Dahl in 1978
• Silicon Valley allure attributed to good weather
• Consulting on Unix project for Dahl, using deck tapes
• The speaker visits a computer museum and is amazed by the preservation of old computers from the 1970s.
• Dahl Corporation's early work with Unix, including version 6, which was still in development when they started using it.
• Writing device drivers for IBM terminals under Unix, particularly for the IBM 3270 terminal.
• The challenge of adapting Unix to run on Dahl mainframes due to their record-oriented architecture and the need to avoid disturbing the mainframe unless necessary.
• How Dahl Corporation initially used Unix as a time-sharing system for electronic design automation people before integrating it into their operating systems.
• Development of ITS (Unix Time-Train System) and its popularity in the Bell system and universities.
• The speaker's departure from Dahl Corporation due to a "crazy company" that was starting, which turned out to be Sun Microsystems.
• The speaker's experience working with Bill Joy and being part of the West Coast Unix universe
• Being recruited by Scott Mc Neely to join a startup related to the Sun board
• Joining Sun Microsystems due to personal desire for a startup experience and cultural influence in Silicon Valley
• Bringing together knowledge of Unix and Xerox Alto technology at Sun
• The development of Xerox Park, including the creation of a PDP-10 clone and innovative software features
• Observations about the early days of computing and the impact of Xerox Alto on personal computing
• Discussion of a seminal group from Silicon Valley's early days
• Comment on financial discipline and the importance of taking risks in one's career
• Story about joining a startup and the author's brother also joining soon after
• Details about Sun Microsystems' rapid growth and success
• Mention of John Gage and his role at the company
• Reference to artwork found with an optical mouse in a garage
• The invention of the optical mouse
• Comparison with the roller ball mouse
• Reliability and precision advantages of the optical mouse
• Independent development of the optical mouse by two individuals
• Early use of colour laser printers in Xerox technical reports
• Timeline for the invention and introduction of the optical mouse (1980s)
• Differences between various optical mice technologies, including orientation dependence and grid patterns on the mouse pad
• The telco protocol, which metered internet usage, was widely disliked.
• ATM (Asynchronous Transfer Mode) was developed for synchronous phone networks with low buffering requirements.
• ATM switches had fixed packet sizes, making them appealing but also limited in flexibility.
• Epsilon proposed operating ATM switches with IP routing to create "IP switching" and faster speeds.
• The approach allowed for separating control from switching functions, a precursor to software-defined networking (SDN).
• The company's innovation enabled faster data transfer rates compared to traditional routers.
• Epsilon (a company) and its sale to Nokia
• Missed opportunities in the Ethernet switching market
• Departure of key personnel and their subsequent success at Juniper Networks
• Confusion over what Nokia wanted from Epsilon, with a focus on IP routing expertise instead of ATM
• The speaker's time at Nokia and their experiences there
• The popularity of Nokia phones, particularly the one that could play Snake
• The speaker's work after leaving Nokia, including consulting, playing with Linux, and starting another startup called Cotillion
• The discussion appears to be about a computer company called Nova and its history.
• A team of engineers, including MPLS (Mario, Prim, Luca, and Sony), left Cisco to start Nova in the early 2000s.
• The speaker was involved with Nova as a co-founder.
• The conversation takes a break to discuss a tweet about an UEFI firmware bug causing issues on premises.
• The speakers try to explain the technical details of the tweet, but it remains unclear.
• The discussion is interrupted by a commercial for Oxide Computer Company and their new feature "On the Metal".
• The speakers return to discuss computer companies and the challenges of running systems on premises.
• The formation of Nova Systems and its acquisition by Cisco
• Development of a 10 gig Ethernet switch, considered an economical first for the industry
• Challenges faced by Cisco in understanding how to sell servers, leading to difficulties in developing server products
• Creation of the UCS system, featuring a smart NIC (VIC) that controls what happens on the PCI bus through the network rather than the server
• Development of firmware and BMC work in collaboration with Intel
• Challenges with BMCs (Baseboard Management Controllers) in making things more manageable
• Discussion of Cisco UFS and server profile control for MAC addresses and UUIDs
• Lessons learned from the last attempts at taking things from scratch not in hyperscalers, resulting in UCS (Unified Computing System)
• How everything became VMware-centric and led to an uneasy tension between Cisco and VMware
• Comparison of firmware work with open firmware vs. proprietary firmware
• Nova's complex system design, including local switches and fabric extenders
• Drive Scale time and investment in peace at Cisco
• The speakers discussed a recent conference they attended and how it reminded them of the "good old days" of computing.
• They expressed appreciation for smaller, more intimate conferences where attendees can connect with each other.
• The conversation turned to the topic of programming languages, specifically the rise of Rust as a replacement for C.
• One speaker mentioned that it's sad to see new projects still being written in C++ or C, and that Rust is a significant step forward.
• They also discussed how some people who remember when C replaced Assembly are now seeing similar reasons why Rust is replacing C.
• Discussion of programming languages and learning curve
• Comparison of Rust with C and other programming languages
• Explanation of the ownership model in Rust
• Introduction to Drive Scale and its goals for server simplicity
• Mention of a podcast hosted by Tom Lyon and invitation to learn more about Drive Scale through it
• Personal discussion about the speaker's family reunion and computer history
• Closing remarks and thanks from the hosts
• On the Metal production details (mailing list, hosts, crew)
• Credits for theme music and editing/production team
• Thank you message from hosts and Oxide Computer Company