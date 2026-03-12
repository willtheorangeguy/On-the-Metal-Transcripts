• Introduction to the podcast and its guests
• Kenneth Finnegan's background and experience in mechanical engineering and electrical engineering
• His work in semiconductor industry, including test engineering and work with gallium arsenide solar cells
• His transition to working with semiconductor fab equipment company Lamb Research
• The company's significance in the industry and its competitors
• The challenges and expenses involved in semiconductor fabrication and marketing
• The speaker had 12 customers and 12 Twitter followers at the start of a project
• The speaker worked with a friend at Cisco's TAC for 15 years
• The friend, Javier, suggested that the speaker start his own ISP, citing the proximity of his own data centre to Hurricane Electric's campus
• Javier proposed that the speaker run a rack as its own ISP, and the speaker was inspired to learn about the technical aspects of the internet
• The speaker learned about autonomous systems and the interconnection of different networks to form the internet
• Javier suggested that the speaker apply for an autonomous system number and buy a Cisco router on eBay, which would allow him to start his own ISP
• The speaker applied for an autonomous system number and was able to start his own ISP, which allowed him to bypass the challenge of finding available IP addresses
• Autonomous system numbers are assigned to networks and are not indicative of a network's legitimacy or age
• The speaker obtained an AS number (7034) after a company went out of business, freeing up its number
• The speaker wrote a blog post on setting up an autonomous system for fun and profit, which went viral on Reddit
• With an autonomous system, a network can connect to multiple other networks and become part of the internet mesh
• A group of friends with their own autonomous systems formed a "homebrew autonomous system club" and set up their networks in a Colo aisle
• They are building a part of the internet, not the entire internet, and are not using it for general internet access but for their own networks to interconnect
• The speaker and a group of six others run their own Autonomous System Numbers (ASNs) and are connected to each other
• The group can peer directly with each other, avoiding the need for external internet routes
• Hurricane Electric offers a good deal on cross-connects, charging a single-time fee for installation
• The group initially attempted to sneak in their own cables, but eventually had to connect officially due to the complexity of the network
• Illicit cabling is a common problem in data centres, with some businesses even going so far as to drill through floors to save money on cross-connect fees
• Breaking into data centres at night with a concrete drill or hammer drill to avoid detection
• Smuggling cables and equipment into data centres
• Setting up secret internet exchanges within data centres
• Disguising oneself as a legitimate employee to gain access to data centres
• Discussing the concept of internet exchanges and autonomous systems
• Explaining the benefits of using internet exchanges to reduce costs and improve network efficiency
• Discussing the overlap between autonomous systems and internet exchanges
• The Fremont Cabal Internet Exchange was started as a joke to solve a cabling problem in a building
• The exchange was initially small and only had 6 networks connected
• Hurricane Electric, a major internet exchange, showed interest in connecting to the Fremont Cabal Internet Exchange
• Hurricane Electric wanted a port on the exchange and offered to connect with the 10 gig interface
• The Fremont Cabal Internet Exchange was not prepared for the influx of new networks and needed to increase its capacity and security
• Hurricane Electric mandated that their salespeople pitch the Fremont Cabal Internet Exchange to other customers in the building, creating a potential incentive for other networks to join
• Hurricane Electric's Colo provider incentive to encourage an internet exchange
• Benefits of an internet exchange, including increased connectivity and value to Colo customers
• Hurricane Electric's business model and willingness to offer free connectivity to exchange users
• Rapid growth of exchange usage, leading to spare SFPs and optics shortages
• Solution of buying SFPs and optics from eBay and other sources to meet demand
• Discussion of internet exchange costs and the expense of purchasing optics
• Problem of running out of SFP cages and switch capacity
• Solutions through sponsorships from Flex Optics, Arista, and Hurricane Electric
• Explanation of the power of community and old school internet practices
• Discussion of the low wholesale cost of internet bandwidth and the high margin area of consumer pricing
• Explanation of how ISPs make money on internet sales despite low wholesale costs
• Understanding the wholesale internet market and how ISPs can stay in business despite saturated ports
• Internet exchanges as a shortcut with limited financial value
• Challenges of running an internet exchange as a business
• Obtaining a root DNS server from VeriSign for the Fremont Cabal internet exchange
• The ease of selling products when they are free, using the example of Hurricane Electric
• On the metal's sponsorship by the Oxide Computer Company
• A discussion about a tweet regarding a firmware bug and its debugging difficulties
• The speaker is experiencing pain from running systems on-premises
• The solution is to go to oxide. Computer to learn about taking the pain away
• The Fremont internet cabal is growing, with corporate America giving free gear
• SoftBank is expected to invest $200 million
• Content distribution networks (CDNs) like Netflix and Google have scalability problems
• Companies are embedding servers in ISPs to improve customer experience and reduce transit costs
• ISPs are incentivized to provide space and power for these servers
• This model is seen as an "original influencer model" where ISPs benefit from hosting content servers.
• The speaker's Firefly design is a one-cabinet web server, not a large-scale server farm.
• The speaker's ISP doesn't qualify for a YouTube cash node due to low traffic volume.
• The speaker worked with Google's network engineering team to create a cash node that aggregates traffic from multiple small ISPs.
• The cash node is hosted on the speaker's Firefly design, but is treated as a larger entity that includes all connected ISPs.
• The cash node is filled with hard drives and serves a large amount of content.
• Google shipped two Dell servers to the speaker, which were new in box and never seen by Google.
• The speaker signed a contract with Google that prohibits publishing raw statistics from the cash node.
• Google bought Dell servers and shipped them to the speaker with a URL to install their own OS
• The OS configures the servers and controls how traffic is steered, with Google's control plane determining which server to pull content from
• The speaker's cache node is used to serve popular content, with Google caching and serving videos from multiple servers
• The speaker's setup is managed remotely by Google, with minimal hands-on involvement
• Hurricane Electric's plan to connect to the internet in Fremont, CA has worked, providing tangible results for ISPs
• The speaker notes the importance of the San Jose area for internet connectivity, with key networks located in two buildings
• Google wants to expand to Fremont
• Internet exchanges serve the "long tail" of small ISPs and content providers
• Large ISPs like Comcast don't participate in internet exchanges and instead pay for peering
• This was a factor in the peering dispute between Netflix and Comcast
• Internet exchanges can be a way for companies to avoid paying large ISPs for peering
• The concept of net neutrality is complex and has many nuances
• The internet is often portrayed as a well-planned and structured system, but the reality is that it was often created through informal agreements and improvisation.
• Early internet agreements were often unorthodox and ignored formal procedures, with network engineers prioritizing speed over protocol.
• The Kenneth net, also known as the "FIX" (pronounced "fuck X"), is an internet exchange that is growing and becoming legitimate.
• The exchange has 50 networks connected, with peak traffic of 6–7 gigabits per second.
• Despite growing, the exchange is still free and has not had any major outages.
• The core function of an internet exchange is simple: it's just an Ethernet switch, and when it breaks, it's easily replaced.
• As the exchange grew, it ran out of ports on its Ethernet switch, requiring a maintenance window to add a second switch.
• The speaker is an internet exchange operator who was a beginner in internet engineering just a few years ago.
• He was a hobbyist who learned about BGP (Border Gateway Protocol) through a 72-hour crash course and then got into internet exchanges.
• BGP is a critical component of the internet that is often misunderstood by its users, and its design assumes trust between networks.
• The speaker describes how a misconfigured BGP route can bring down a significant portion of the internet, citing examples of real-world outages caused by mistakes.
• He notes that the internet is designed to be resilient and can route around damage, but a BGP misconfiguration can still have significant consequences.
• The speaker has transitioned from being an electrical engineer to a network consultant and is now interviewing for network engineering positions.
• The fragility and robustness of the internet
• The internet's ability to route around damage
• The importance of disaster recovery and failure modes in maintaining a reliable internet connection
• The Fremont Internet Exchange's smooth operation
• Technical difficulties and unexpected problems with internet connectivity and DNS resolution
• The concept of connecting people through the internet and the simplicity of its underlying technology
• Recent increase in signups attributed to end of year contract renewals
• Sales team's need for metrics has contributed to the increase
• Critical mass reached on contract rotation, making it easy to sell
• Half of new applications were discovered through stickers in the lobby, half through a sales rep
• M root server is located in the same aisle as the speaker's company
• The speaker discovers M root's presence and invites them to appear on the Fremont Cabal internet exchange
• A port is sold to M root on the exchange
• Discussion of various outages and issues, including free NAS problems and storage issues
• Issues with FCI X, including port problems and BGP timeouts
• Interaction between BGP timeouts and router connections
• Security policy on switch, shutting down ports with multiple MAC addresses
• Problem with a customer's router not seeing port shutdown, causing issues
• Solution and refund offered to the customer after understanding the issue
• Discussion of network timeout settings and their nuances
• Kenneth's humorous anecdote about a router routing around a problem
• Kenneth's online presence and blog (thelifeofkenneth.com) for long-form content
• Mention of Kenneth's Twitter handle (KWF) for short-form posting
• Conversation about the metal as a can compute substrate, storage substrate, and networking substrate
• Closing remarks and show notes for the podcast