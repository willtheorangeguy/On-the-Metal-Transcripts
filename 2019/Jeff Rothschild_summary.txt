• Introduction to guest Jeff Rothschild and the topic of computer manuals
• Discussion of IBM PC manuals from the early days and their significance
• Jeff's experience with MS-DOS disassembly in his 20s, creating comments for the code
• How this experience helped him understand file control blocks and state association
• Using the commented code to create an IO redirector for moving data between MS-DOS and a Unix system
• The creation of PC Interface software that allowed MS-DOS programs to access a Unix host as a remote file system
• The technology being purchased by Sun Microsystems and becoming part of NFS client-side functionality
• The speaker implemented a simple IPUDP protocol in assembler for a machine with only 64K bytes of RAM
• They worked on the AT&T 3B2, an early Unix and C-centric computer that supported upward stack growth
• The Sigma 7 was mentioned as another influential computer, a 32-bit machine developed by Scientific Data Systems (SDS) in the early 1970s
• The speaker reminisced about working with limited resources and coding for efficiency, including eliminating bytes to save half a grade
• They contrasted this era with modern computing, where resource management is less emphasized
• Working with paper tape and PDP-8 and PDP-10 machines
• Coding without an assembler on a PDP-10 machine in octal
• Discussion of using binary representation directly versus assembler
• Experience working at Honeywell's large information systems division
• Description of the Honeywell system, including 36-bit architecture and mixed byte sizes (6, 8, and 9 bits)
• Explanation of EPSIDIC character encoding used by IBM in the past
• Honeywell's mainframe and GCOS operating system
• 7400 LS logic and its implementation in computers of the 1970s
• Texas Instruments TTL data book and small scale integration components
• Comparison with IBM, Burroughs, Univac, NCR, Control Data, and Honeywell as computer companies in the 1970s (FANG equivalent)
• Honeywell's H200, an IBM 1401 clone
• Discussion of CML (current mode logic) implementation at Honeywell and its comparison to ECL (emitter-coupled logic)
• Micro-coded machines and their use of micro-instructions to implement target instruction sets
• Microcode and architecture team work
• Calculating savings vs debt
• Working at Intel on memory production and disk emulators
• Project issues with slow performance of solid-state disks compared to physical disks
• Interview process for a job at Intel
• Solution to the project issue being already in place, eliminating the need for the candidate's services
• Discussion of IBM's solid-state disc development in 1979
• Volatility and motor generator system used for power supply
• Potential corruption from wall power glitches and battery backup systems
• Capacity and performance metrics, including rotational latency and IO request times
• Quarter billion dollar backlog due to release criteria being too high and OS scheduling strategies
• Single instruction set with many implications and low-level programming considerations
• Discussion of a specific single instruction that caused significant delay in older memory systems
• Channel programs: how IO is performed by a separate computer with an interface to the mainframe
• Comparison of CISC (Complex Instruction Set Computing) and RISC (Reduced Instruction Set Computing)
• Use of AMD 2900 series logic family to re-implement control program for improved performance
• Bit slice processor design that allows custom instruction sets
• Mention of AMD 29K and its relationship to the 2900 series
• Historical context and impact of CPU design choices on computer architecture.
• Customizing error messages in an assembler to address developers by name and scold them based on their habits.
• Working with the Intel development system, a single-user workstation that was not network-connected.
• The shock of receiving a customized error message on a standalone computer, which was unexpected and unnerving.
• The importance of custom error messages for software developers working on premises.
• Oxide Computer Company's efforts to acknowledge and support users who are still running on-premises due to security, latency, and strategic reasons.
• A discussion about the optimization techniques used in an assembler, specifically pipeline optimization to reduce delays.
• Instruction scheduling and variable delays in modern processors
• Early assembler development and potential bugs
• Working with AMD architecture at Intel in the early 1980s
• Competitive relationship between Intel and AMD
• Introduction of PC market and its impact on Intel's business
• Development of operating systems for workstations and PCs, including RT11, MS-DOS-like, and CPM
• Discussion of file path notation, forward slash vs backslash, in different operating systems
• Differences between DOS and Unix file systems
• Equivalence of forward and backward slashes in file paths
• Handling of file close operations and the loss of context on Unix
• Implementation of a cache to accommodate DOS-style file closing
• F-truncate operation added to support DOS behavior on Unix
• Performance issues with original truncate implementation on Unix
• The lack of F-truncate functionality prior to its introduction
• Why F-truncate was added (to address slow file closing times)
• The origin story of F-truncate and its addition to Unix
• A personal anecdote about optimizing a Unix system call for an office automation project
• The concept of "gourmet mode" as a terminal line discipline for efficient keystroke handling
• The speaker discusses a Unix project that handled a large number of keystrokes without issue.
• A specific function called ftruncate caused the speaker to introduce a bug in the kernel due to missing code paths.
• Gourmet Mode was implemented by the kernel group within ICL, and it handled mode changes for terminal emulators.
• The speaker worked with ICL, then Locus Computing Corporation on a distributed Unix project that ran over Ethernet.
• The Locus project allowed for processes to be migrated between machines and provided a fully distributed Unix environment.
• Early development of distributed systems using Unix
• Ethernet and coaxial cables for communication between machines
• Commercialization of distributed systems through IBM's productization
• Influence of Locus and IBM on the field of distributed computing
• Amoeba, another transparently distributed system, and its relationship to Unix
• History of Unix's adoption in commercial computing
• Personal anecdotes about working with distributed systems in the 80s
• The company had achieved commercial success with its fault-tolerant computers.
• A new direction was considered to build "shoebox machines" for lower cost and higher availability.
• The notion of replication between machines was introduced for environments requiring high availability.
• The company evolved in a different direction after the speaker moved to Europe.
• Fault-tolerant computing became less relevant as people realized they didn't need nonstop capability, but rather better availability and data integrity.
• A new software company, Veritas Software, was formed to provide higher availability and better file system and data integrity than Unix systems.
• The original company, Tolerant Systems, was sold off after it went bankrupt.
• Veritas Software was created from scratch with a focus on building a heavily customized version of Unix using well-defined interfaces.
• Mark Leslie became the CEO of Veritas Software and suggested changing the company's name to "Veritas" which means "truth".
• The company developed a logical volume manager, supported replication and software RAID 5, and allowed dynamic growth and shrinking of volumes.
• FSCK times increased from 35 minutes to 12 hours for some Unix systems
• Recovery from system crashes took too long, making Unix unviable for mission-critical environments
• Veritas' VXFS file system addressed this by logging metadata changes, allowing rapid recovery without structural scan
• VXVS was an extent-mapped file system with logged metadata, not a log-structured file system
• Software RAID implementation in VXVS obviated the need for structural FSCK
• RAID at the time was mainly hardware-based; Veritas' software solution effectively implemented RAID capabilities
• The use of Veritas volume manager was primarily for storage migration and logical extent management
• Tweet about UEFI preboot networking stack and DMA
• Discussion of debugging firmware bugs
• Vendor stranglehold and pain of running on-premises systems
• Introducing oxide.computer to alleviate pain
• Veritas technology, its impact, and legacy
• Frenemy relationship between Sun and Veritas
• Founding and history of Veritas software company
• Early online gaming experiences, including latency issues
• Co-locating game servers with internet service providers (PSINET)
• Optimizing traffic and prioritizing game traffic on networks
• Hiding latency in game protocols and algorithms
• Developing multiplayer gaming capabilities
• Converting Quake to IP from Novell network protocol
• Consulting work after leaving the game industry, including helping Walmart.com and Rhapsody Networks
• Getting involved with a social network startup (later identified as Facebook) through Excel Partners
• First impression of Facebook as a small team with no rules or process
• Early days at Facebook involved working closely with the development team
• Email inbox was overwhelming with 75,000 unread messages due to inadequate management
• Users were expressing deep emotional connections and gratitude for the social network
• The speaker compares Facebook's approach to other companies' marketing strategies
• The focus on user happiness and relationships is what made Facebook special
• The power of increasing information flow between people is highlighted as a key factor in creating happiness
• The speaker met the interviewee in 2007 when Facebook was gaining popularity
• The interviewee shared a personal anecdote about having a second child born quickly
• The interviewee discussed working at Facebook and dealing with technical problems
• A specific problem mentioned was with memcache, a distributed hash table that needed to be improved for scalability and performance
• The solution involved making it multi-threaded and reducing variability in request times
• Another problem mentioned was buffer overflow and packet drop due to TCP variable retries and congestion control
• Problems with memcache code and TCP protocol
• Buffer overflows caused by deterministic code path
• Importance of configuration management in avoiding similar issues
• Resolution of a specific bug involving release code for configuration management
• Experience with finding and resolving the memcache problem as one of the most frustrating and gratifying
• Genesis of the Open Compute Project at Facebook
• The Open Compute Project and its significance in hardware optimization
• The evolution of server architecture and the rise of serverless computing
• The potential of non-volatile RAM technologies (e.g. Intel's Optane)
• Historical parallels between past innovations (e.g. Multics) and current developments
• Database design and performance optimization, particularly with regards to memory usage
• Advantages of a change in the market
• Impact of non-volatility on main memory speeds
• Potential disruption and opportunities for new players
• Jeff's track record and influence in computing
• Limiting engineers' sales meetings to avoid complacency
• Saying goodbyes and closing conversations
• Acknowledging requests to have one's needs met
• Mention of YPS going for two more minutes
• Reference to an event being the first time
• Repeated messages wishing a nice day
• Conversation about dates or scheduling