• Amir Michael's childhood in Silicon Valley
• Growing up with a father in tech (Fairchild Semiconductor, AMD)
• Decorating room with wafers from his dad's work
• Learning to solder at age 5 or 6
• Early interest in electronics and building circuits
• Spending time at Radio Shack buying parts and building kits
• First computer experience with an XT running at 2 megahertz
• Early childhood experiences with computer hardware and friends who shared similar interests
• Using BBSs (Bulletin Board Systems) to access online content and interact with others
• Building a custom computer with a Pentium processor and playing online games in the early 1990s
• Studying electrical and computer engineering at UCSB and participating on the LAN (Local Area Network)
• Sharing files and software, including pirated programs, on the LAN
• Growing up and exploring technology
• CD burning and pirating software
• Building a program called "Race Master" in Turbo Pascal for radio control cars
• Learning programming with friends and self-teaching with Turbo Pascal
• The legacy of Turbo Pascal and its speed
• Connection to the Golden State Warriors player Eric "Turbo Pascal" Pascal
• Early exposure to programming in school with Fortran
• Legacy of Fortran in modern software development
• Fortran programming in high school and college
• Moving from Fortran to more modern languages like C
• Comparison of being taught Java versus Fortran/C in early 2000s computer science programs
• Building a four-bit microprocessor as a final project in 2001
• Designing the processor using discrete logic chips and FPGAs
• Debugging challenges with a complex breadboard setup
• Writing assembly code for the processor and programming it into EEPROM
• Discussion of building a custom microprocessor in college
• Memories of the 2001 tech bubble bursting and its impact on job market
• Job search struggles after graduating with an engineering degree
• Decision to volunteer for a year in Israel, teaching English in marginalized neighbourhoods
• Starting a small company making battery chargers for model airplanes
• The speaker started a company to recharge model planes but didn't realize there was no market demand
• He later applied for a job at Google and initially got rejected due to lack of relevant experience
• After revising his resume, he was hired by Google where he worked as a data centre technician
• He made a rookie mistake by putting too much thermal grease on a CPU, which led to inefficiencies in the cooling system
• The speaker went through a hazing period at Google, but eventually adjusted and became part of the team
• Google's early servers were built from commodity components, including motherboards purchased from Fry's Electronics.
• Initial servers used cork boards to hold the components, but this was later replaced with "bread racks" that held the motherboards on standoffs.
• Early servers used non-ECC DRAM, which had more errors, but was cheaper and could be accommodated by software.
• Software had to be written to handle the errors in the hardware, making it a challenge to debug issues.
• Velcro was used to hold hard drives in place, but was later phased out as Google became more serious about the quality of their hardware.
• UEFI reboot networking stack corruption issues
• Debugging firmware bugs in computer hardware
• Problems with running on-premises systems due to vendor-related issues
• Need for a new computer company to improve industry standards
• Google's transition from junk components to custom designs and efficient data centres
• Importance of holistic design and control over facility and server efficiency
• Project Black Box/Operation Black Box, a shipping container-based data centre
• Design considerations for efficient cooling and power distribution
• Use of local batteries on servers and lack of UPS in the system
• Deployment of tens of containers in Atlanta by Google
• Issues with facility costs and management concerns around security and layout
• Decision to adapt principles learned from container design into standard warehouse/data centre designs
• Designing thermally efficient systems for data centres
• Minimizing power conversions and energy consumption
• Designing modular, scalable data centre infrastructure
• Collaborating with vendors to create custom hardware solutions
• Facebook's transition from traditional data centre vendors to in-house design and construction
• The development of the first custom-built data centre at Facebook
• The team's audacious proposal and the feeling of "oh my God" when it was approved
• The hardware team and data centre facility team worked together to overcome various challenges.
• A custom motherboard was designed with a unique form factor (13x13 inches) and Intel's Salem processor, which connected DRAM directly to the CPU for the first time.
• During production verification tests, a bug was discovered where half of the memory would be missing on some systems.
• The team worked together with partners such as Quanta and Intel to identify and fix the issue.
• The problem was caused by a DRAM training procedure that put some vendors' DRAM into a debug mode, rather than initializing it properly.
• Proprietary software issues with training data
• Debugging with Intel and DRAM vendor to resolve defect
• Decision to proceed with manufacturing despite unresolved issue
• Software work-around for hardware defect
• First deployment of OCP servers (originally Project Freedom)
• Custom facility requirements and contingency planning
• The origins of the 19-inch rack standard
• Amortizing costs across multiple servers in a rack
• Design considerations for racks with high weight and capacity needs
• Standardization of rack width to fit floor tiles and facilitate deployment
• Evolution of rack design from initial 3-column design to open rack format
• Discussion of OCP (Open Compute Project) design standardization
• Limitations on discussing customer experience in ads due to attorney advice
• Oxide Computer Company statement allowed by lawyers for use in ads
• History and development of OCP, including collaboration and innovation sharing goals
• Facebook's founding motivation behind open-sourcing OCP
• Benefits of collaboration and public project work, including talent attraction
• Internal approval process and minimal resistance to opening up the project
• The origin and meaning of the name "OCP" (Open Compute Project)
• History of OCP's public launch in April 2011
• Challenges faced by OCP due to its complexity and slow adoption rate compared to open-source software projects
• Growth of OCP through partnerships with large infrastructure companies like Microsoft and Google
• Description of the OCP summit, including its size, attendance, and features (e.g. unique hardware demos)
• Discussion of firmware and software's role in OCP, with an emphasis on initial deployment design to be plug-and-play
• Scope of open-source networking and the Open Compute Project (OCP)
• Evolution of networking from specialty switches to commoditized hardware
• Impact of OCP on industry, including energy efficiency and cost savings
• Role of silicon in network design and its impact on costs
• Growth of Facebook's infrastructure and adoption of custom servers
• Importance of energy efficiency and reducing greenhouse gas emissions
• Opportunities for further innovation and expansion of OCP principles
• The importance of energy consumption in software development and its indirect impact on greenhouse gas emissions
• The inefficiency of cryptocurrency mining and its high energy demands
• The lack of efficient server management tools for large-scale companies
• The discovery of outdated infrastructure designs and practices in the industry
• The realization of "infrastructure privilege" held by large tech companies like Google and Facebook
• The decision to start a new company to address these issues and provide more efficient solutions
• Data collection from server fleets revealed low utilization rates
• Many companies were unaware of their fleet's performance and behaviour
• Utilization was often as low as 2-3%
• Companies were spending millions on underutilized infrastructure
• Similar issues exist in cloud deployments, where instances can be reserved but not fully utilized
• Power consumption is a major issue due to non-variable usage patterns (e.g. DRAM)
• Small and medium-sized businesses lack resources and awareness for efficient infrastructure management
• Education and visibility are key challenges in improving infrastructure efficiency
• Some companies may resist software solutions that reveal underutilization and inefficiencies
• Firmware vendors not doing a good job writing firmware
• Customers having trouble with inconsistent or missing information in hardware data
• Software solutions to normalize and make sense of variations in hardware data
• Challenges of dealing with errors in DRAM, including different reporting methods and standards
• Importance of accurate error counting for predicting hardware failure and preventing costly issues
• Use of external datasets, such as Back blaze's, to train algorithms and improve accuracy
• Back blaze's approach to monitoring failure rates across their fleet
• Firmwares and drive vendors contributing to high failure rates
• Comparison of OneDrive's data collection methods to Back blaze
• Challenges in collecting data from various components and systems
• Difficulty in collaborating with vendors to share data anonymously
• The role of funding and the pressure to show value to investors
• Contrarian views on cloud infrastructure vs. owned infrastructure
• Infrastructure outside the cloud will still be necessary
• Many companies lack expertise to evaluate and manage physical infrastructure
• Building server infrastructure is not rocket science, but requires talent and investment
• The flip side of increased complexity is also increased accessibility of infrastructure and open-source tools
• Fear, uncertainty, and doubt (FUD) can hinder progress and adoption of new technologies
• The management controller (BMC) was removed from servers
• Alternative method of rebooting boxes using magic packet (Wake on LAN)
• Removing BMC saved $40 per box in materials
• Cluster went down due to accidental IP change, and BMC used for recovery
• Discussion about whether BMC is necessary or if issue is with procedures allowing re-IP changes
• BMC (Baseboard Management Controller) issues with servers
• Importance of deploying hardware and infrastructure for efficient product development
• Role of talent and willingness in successfully building own infrastructure
• Comparison of traditional infrastructure vs cloud-based services
• Career discussion and social media presence of guest, Amir