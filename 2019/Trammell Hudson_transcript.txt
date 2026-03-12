[0.00 --> 15.78]  Welcome to On The Metal, tales from the hardware software interface.
[16.20 --> 18.96]  I'm Brian Cantrell. With me, as always, is Jess Frizzell. Hey, Jess.
[19.22 --> 19.90]  Hey, Brian.
[20.12 --> 22.52]  And joining us is our boss, Steve Tuck. Hey, Steve.
[22.72 --> 23.36]  Glad to be here.
[24.08 --> 26.88]  Jess, you want to introduce who we've got in the virtual garage today?
[26.88 --> 36.30]  Yeah, so today we have Trammell Hudson. He is remotely in Amsterdam, but I discovered Trammell, I guess, through the internet.
[36.68 --> 43.62]  He does crazy cool things with computers. It always seems like he's on a train or a boat or something, hacking on something.
[43.90 --> 45.72]  So, yeah, pretty excited.
[46.54 --> 48.84]  Trammell, welcome to the Virtual Oxide Garage.
[49.72 --> 50.88]  I'm glad to be there.
[50.88 --> 57.00]  I think it's wonderful that you all have started a Silicon Valley company in a literal garage.
[57.14 --> 58.72]  In a literal garage, I know.
[58.96 --> 65.82]  When Jess said her garage was perfect for us to get started in, we were like, that seems a little too cliche, but it's a great garage, actually.
[66.12 --> 67.94]  So, it's great to have you here.
[68.10 --> 69.88]  So, Trammell, I have a little bit of a confession.
[70.12 --> 74.22]  I was attending a conference recently, and they were asking me,
[74.22 --> 79.02]  what website do you read that other people are not going to be aware of?
[79.14 --> 81.86]  You're like, oh, boy, all right, I got to find something really interesting now.
[82.30 --> 87.84]  And I was thinking that, you know, what website do I go to that other people should be aware of but maybe aren't?
[87.92 --> 90.98]  And I'm like, you know, I'm going to give them trmm.net.
[91.98 --> 96.72]  Your website is delightful, and there's so much interesting stuff there.
[96.72 --> 101.68]  So, maybe you want to kick it off with, I mean, you've done so much of the hardware-software interface.
[101.96 --> 104.44]  How did you first discover it when you were coming up?
[105.38 --> 112.78]  Well, so, right out of school, I went to work for Sandia National Labs out in Albuquerque on the high-performance computing team.
[113.46 --> 119.70]  And at the time, we were writing a custom operating system for the supercomputers.
[119.70 --> 126.32]  And so, because performance was absolutely critical, we were running everything on the bare metal.
[126.82 --> 133.62]  And we really had to do a lot of work to make all of the compute resources available to the users.
[134.22 --> 142.12]  And as a result of spending so much time at the operating system and the message passing and the network driver sort of layer,
[142.58 --> 145.54]  I really came to love that sort of interface.
[145.54 --> 154.06]  And, you know, really realized how much capability came about just from understanding how does the machine work
[154.06 --> 157.96]  and how can we best take use of it from software.
[158.70 --> 160.18]  And plus, I really like taking things apart.
[160.66 --> 165.70]  And it's fun to document what I learn when I'm doing that.
[166.72 --> 169.60]  And that's really what my website is full of.
[169.60 --> 170.82]  It was just random.
[171.26 --> 176.96]  Essentially, it's my project notebook over the past, I guess I've been running it for about 10 years now.
[177.80 --> 181.70]  And the big issue is my attention span is pretty short.
[182.34 --> 190.28]  So, a lot of these projects I'll work on for two, three, maybe six weeks, document them, and then move on to the next shiny thing.
[190.62 --> 192.36]  So, there's a lot of unfinished stuff there.
[192.36 --> 195.20]  But also, hopefully a lot of things that people might find useful.
[195.20 --> 199.12]  Yeah, there's a lot of stuff there that's useful and interesting.
[199.56 --> 204.50]  First of all, on that supercomputer at Sandia, what kind of machine was that that you were first exploring?
[205.66 --> 211.24]  So, the very first one that I worked on was an Intel Paragon.
[211.68 --> 213.86]  It was an i-60-based machine.
[214.06 --> 214.64]  Yeah, right.
[215.26 --> 218.04]  And it was the world's fastest supercomputer.
[218.04 --> 221.48]  We were number one in the top 500 for many, many years.
[221.48 --> 232.08]  And the sort of fun story with that one is it shipped with a single system image Unix called OSF1.
[232.84 --> 234.84]  You actually ran OSF1.
[235.46 --> 237.24]  Well, so we tried to.
[237.72 --> 244.78]  The problem is that OSF1 consumed about 12 megabytes of memory out of the 16 megabytes that we had per node.
[245.00 --> 247.86]  Remember, this is the 1990s.
[248.32 --> 250.52]  So, that was still a lot of memory.
[250.52 --> 259.38]  And that didn't make our users very happy to have this massive machine and so much of the resources going to the OS.
[259.76 --> 267.08]  So, what the group that I worked in did was we built our own lightweight kernel that only used a couple hundred kilobytes.
[268.24 --> 272.34]  And that ended up becoming the official OS for the Paragon.
[272.56 --> 274.90]  So, an all i-860-based.
[275.70 --> 279.28]  So, an i-860 risk microprocessor, right, if memory serves?
[279.28 --> 279.40]  Yes.
[280.10 --> 280.40]  Yes.
[280.60 --> 282.22]  And, you know, risk is going to change everything.
[282.56 --> 282.92]  Right.
[283.38 --> 283.78]  Nice.
[284.44 --> 286.58]  And i-960 was the following.
[286.78 --> 288.50]  Did they end up running that as well?
[288.64 --> 291.98]  Or by that point, had they moved on to other CPUs?
[291.98 --> 296.92]  So, at that point, we had moved on to another CPU.
[297.26 --> 300.62]  The next machine we built after that was ASCII Red.
[300.84 --> 302.90]  Excuse me, ASCII Red Storm.
[304.00 --> 304.64]  No, no, sorry.
[304.88 --> 306.10]  ASCII Red was the next one.
[306.56 --> 308.34]  And that was Pinium Pro-based.
[308.34 --> 309.96]  So, by that.
[309.96 --> 311.78]  And so, we had the...
[311.78 --> 319.64]  The Pinium Pro was a really weird design with like a multi-die package, incredibly low yields.
[319.64 --> 328.72]  And Intel gave us a special spin of it to, I think, with the Xeon core in the same package, which was super buggy.
[328.72 --> 340.64]  And my attempts to get some patches into the Linux kernel were rejected since there were only a few thousand of those, I think 50,000 of those CPUs in the world, and we had all of them.
[341.38 --> 341.64]  Wow.
[342.52 --> 343.88]  Hard for others to test.
[344.72 --> 344.96]  Yeah.
[345.08 --> 347.28]  So, Linus did not accept my patches.
[348.20 --> 350.06]  That seems to be a common theme.
[350.06 --> 357.64]  Especially when you're sitting on all of a particular breed of microprocessor that it sounds like a very strange hybrid.
[358.54 --> 360.82]  It was a really weird sort of design.
[361.48 --> 365.48]  And then the follow-on from that was the ASCII Red Storm, and that was Opturon-based.
[366.02 --> 372.06]  One of the things I really enjoyed about working on the Paragon was how tightly the network was coupled to the CPU.
[372.68 --> 376.56]  That we could use the DMA engines for doing like a mem copy.
[376.56 --> 384.56]  And it was faster to ask it to DMA 128 bytes than it would be to do a byte-by-byte copy from the CPU.
[385.60 --> 403.06]  And when you compare that to going out to PCIE, where you have 500 to 1,000 nanoseconds, just to do a round trip out to that bus, being able to do something so quickly to the NIC was really quite fun to play with.
[403.06 --> 410.54]  Especially when you have so many cores presumably harnessed together in a network, I imagine that was essential to be able to have that kind of networking performance.
[411.50 --> 411.60]  Yeah.
[411.76 --> 419.34]  And at that point, because of the relatively small memory, communication was much, much more important for the HPC machines of that era.
[420.34 --> 422.74]  And is this 10 megabit, maybe?
[422.88 --> 425.56]  I'm trying to think what would be the interface speed at that time.
[425.56 --> 429.70]  Well, we spent a lot of money on the NIC.
[429.90 --> 434.52]  With these machines, you'd usually estimate that a third of your money was just going to the network.
[435.48 --> 441.88]  So it's been a long time, but dredging back into those neurons, I think we were doing 400.
[442.40 --> 445.64]  And then we were able to push that to 800.
[446.28 --> 449.44]  800 megabit in the mid-90s or late-90s.
[449.50 --> 450.12]  That's really good.
[450.92 --> 453.16]  That was in the, yeah, the, like, 94, 95.
[453.16 --> 460.06]  When 16 megs is the amount of DRAM you've got to be able to push 800 megabit, that's impressive.
[461.30 --> 462.80]  Yeah, it was a really fun machine.
[463.32 --> 469.52]  The other thing, though, that it really colored my view on how to design large-scale systems,
[470.04 --> 479.32]  that we partitioned these machines so that we would have some number of nodes that were connected to the outside world,
[479.56 --> 481.34]  and we ran an interactive OS on them.
[481.34 --> 487.20]  We had some number of nodes that were connected to disks, and we ran a file servers on those.
[487.58 --> 491.94]  And then most of the nodes in the middle had no external network connection and no disk connection.
[492.18 --> 493.42]  They were just pure compute.
[494.60 --> 498.84]  And this meant that we could, with a fairly small staff,
[499.22 --> 504.58]  we could maintain effectively tens of thousands or hundreds of thousands of systems,
[504.58 --> 510.54]  where you might expect a Unix system admin not to scale to quite that sort of scale,
[511.32 --> 516.04]  but doing it where there was no state on most of the nodes,
[516.34 --> 519.48]  where there were no moving parts on most of them,
[519.90 --> 521.38]  they would all boot off the network,
[521.88 --> 524.28]  they all would reconfigure on the fly.
[524.28 --> 530.02]  This was a really elegant way to manage and administer hundreds of thousands of cores.
[530.14 --> 535.48]  Yeah, I mean, this has been very futuristic in the mid to late 90s,
[535.52 --> 539.94]  to have that kind of quantity of certainly that many CPUs,
[540.10 --> 542.58]  and managing them in that manner.
[543.28 --> 545.78]  You must have wondered how anyone else was doing it.
[546.24 --> 547.64]  It seems like such an elegant way to do it.
[547.64 --> 554.74]  Yeah, when most folks tap out around a few dozen computers per admin,
[555.06 --> 556.82]  it was really quite something to be able to say,
[556.94 --> 561.88]  oh, we measure our computers not in core count, but in acres.
[563.56 --> 564.54]  That's awesome.
[565.46 --> 569.60]  And so was that your first exposure to firmware?
[569.80 --> 574.30]  When did you begin to discover all of the software that was beneath the software?
[574.30 --> 580.44]  That was really where I started spending most of my time sort of in the firmware world.
[581.46 --> 589.50]  I think with ASCII RedStorm, we had a coprocessor in the NIC that we were able to write code for.
[590.08 --> 595.30]  So my group developed something called Portals that ran underneath MPI,
[596.28 --> 599.92]  the message passing interface that all of the big Fortran codes use.
[599.92 --> 609.42]  And so we wrote code that ran in the NIC to do all of the OS bypass and message matching, offload.
[609.92 --> 616.24]  And that really was the eye-opener that, oh, everything in the system is just another computer,
[616.52 --> 619.36]  and we can program it, and we can make it do what we want.
[620.04 --> 625.64]  Yeah, that must have been a real aha moment to realize how much software was beneath the software
[625.64 --> 628.06]  that you thought was the lowest level software in the system.
[628.06 --> 635.64]  Yeah, ring zero in the CPU or in the OS is not the bottom of the stack by far.
[636.46 --> 639.16]  Yeah, I mean, I don't even know where the bottom of the stack is anymore.
[639.42 --> 642.88]  I feel like every time I feel I've found the bottom, there's some hidden ring.
[643.00 --> 646.52]  I mean, Jess, you had a great article going into what you got to ring negative three, I think.
[646.98 --> 650.40]  Yeah, I mean, it depends who you ask, though, because a lot of people are like,
[650.46 --> 655.44]  eh, those are just made-up rings, because once you've reached the lower levels, it's all just like, eh.
[655.44 --> 659.10]  How low does it go? Is negative three the bottom?
[659.76 --> 665.76]  I mean, again, it kind of depends on who you ask, but what you've got is this firmware that's at a very low level of the system
[665.76 --> 667.58]  that can control the entire system.
[667.98 --> 675.30]  And so it's hard to argue that that software isn't beneath the software that thought it was controlling the whole system.
[676.26 --> 681.36]  Jess's article really did a wonderful job of laying out a lot of the sort of hidden pieces
[681.36 --> 687.36]  inside the commodity machine between the SMM and the management engine.
[688.00 --> 692.54]  Once you get even further down where you're dealing with the BMC or the embedded controllers,
[693.16 --> 697.94]  there's just a lot of unexamined code that has way too much privilege.
[698.64 --> 707.24]  And it's a big concern for not just runtime security, but also for things like resale and decommissioning.
[707.24 --> 713.68]  How do you know that the systems that you're turning over don't have any state still on them?
[714.08 --> 719.18]  And more importantly, how do you know the systems that you're buying haven't been compromised somewhere in the supply chain
[719.18 --> 725.12]  in one of these tiny microcontrollers sitting on an important bus somewhere?
[725.12 --> 730.84]  That's a good segue into your talk at, what was it, 34C?
[731.08 --> 732.34]  I always forget the numbers.
[732.94 --> 733.56]  Mod chips of the state?
[733.56 --> 734.60]  Yeah, Mod chips of the state.
[734.70 --> 742.18]  The notorious talk where you basically prove that what happened in the Bloomberg article is entirely possible,
[742.40 --> 746.08]  although it's skeptical as to whether that happened in real life.
[746.20 --> 747.54]  But it's a great talk.
[747.74 --> 749.06]  No, that was a terrific talk.
[749.58 --> 753.18]  And for folks who have not seen that, and they definitely should, we'll link to it in the show notes,
[753.18 --> 756.16]  but describe a bit what you were able to show there, Trammell.
[757.00 --> 762.78]  So the part that really struck me in the Bloomberg article was some of the detailed descriptions
[762.78 --> 770.84]  of how a hardware implant on the spy bus between a flash chip and the BMC could take control
[770.84 --> 772.58]  and potentially wreak havoc.
[772.96 --> 776.88]  And I think a lot of those details came from Fitz, who was one of the consultants on the article.
[776.88 --> 784.96]  So I set out to see, well, could we actually replace a signal conditioning coupler, in this case,
[785.04 --> 791.84]  a small resistor on the board, with an active component that could inject its own payload
[791.84 --> 793.64]  into the BMC while it booted?
[794.46 --> 801.82]  Figuring out how to do that without power, without clock, without a lot of the niceties of the spy bus
[801.82 --> 803.20]  was a really fun challenge.
[803.20 --> 806.48]  It was also my first intro into FPGAs.
[807.10 --> 814.00]  And I've really come around to realize that they are a wonderful tool for doing a lot of these
[814.00 --> 817.30]  very timing-critical sort of hardware interface things.
[817.46 --> 821.32]  So many of the projects I had done with Arduinos, I've gone back to and realized,
[821.42 --> 823.66]  ah, it would have been easier to do this with an FPGA.
[824.18 --> 829.72]  Wow, not something you necessarily think of, that like an Arduino project would have been easier with an FPGA.
[829.72 --> 833.46]  Anything that's really timing-critical.
[833.78 --> 840.76]  And the spy bus, which is where the firmware that the BMC or the x86 lives,
[841.34 --> 843.72]  is a really timing-critical bus.
[843.94 --> 851.02]  It needs to be able to deliver bytes in response to commands in single-digit nanoseconds.
[851.66 --> 855.98]  So it's the sort of thing where you really need that programmable hardware to make it happen.
[855.98 --> 858.98]  It was operating, what, at 20 megahertz? A little faster?
[859.28 --> 861.36]  What's the speed of that bus operates?
[862.42 --> 867.38]  So when the x86 boots up, it starts it at 16 megahertz,
[867.56 --> 871.82]  and then we'll ramp it up to see if the chip says it can handle it.
[872.68 --> 877.24]  Although I've just recently ported some of these things over to one of the newer A-speed BMCs,
[877.24 --> 885.10]  and they do an interesting thing where they will read a section of the flash and checksum it,
[886.02 --> 888.74]  and then they will just increase the clock speed,
[888.96 --> 891.42]  rereading that section until they get a bad checksum.
[892.38 --> 895.76]  And then they'll back their speed down a little bit, and that's the speed they'll use.
[896.84 --> 897.20]  Wow.
[898.34 --> 900.70]  So they actually just push it to the breaking point
[900.70 --> 902.82]  and then conclude that that's the fastest that they can operate.
[902.82 --> 904.82]  And how fast can that stuff operate?
[904.90 --> 907.30]  How fast does the spy flash, are they able to push it?
[907.96 --> 912.36]  Usually 50 to 80 megahertz is a reasonable speed
[912.36 --> 914.78]  if you have very short connections
[914.78 --> 918.60]  and not a lot of loading on the, passive loading on the bus.
[919.22 --> 922.62]  One of the projects that I've turned the mod chips talk into
[922.62 --> 924.40]  is something called the Spy Spy,
[924.86 --> 928.34]  which is now a general purpose flash emulator
[928.34 --> 933.82]  that is really a lot of fun to poke at systems when they're booting,
[933.94 --> 937.66]  because you can learn a lot both about the security of the system
[937.66 --> 940.80]  as well as a lot of the various other components.
[941.76 --> 946.26]  So with the Spy Spy, we can monitor the data that's going across that spy bus,
[946.26 --> 951.34]  and we can also modify it or swap it out with our own content.
[952.02 --> 953.54]  Spy Spy is amazing.
[953.54 --> 957.50]  And I actually have to tell you that I went to see
[957.50 --> 960.84]  what the Hacker News discussion of Spy Spy was when it came out,
[960.92 --> 964.30]  and was dismayed to find that it had never been submitted to Hacker News.
[964.68 --> 967.16]  So I think months after you'd released it,
[967.24 --> 969.08]  I'm like, well, I'm going to obviously submit this to Hacker News.
[969.36 --> 974.10]  I feel that Hacker News revealed that it is not, in fact, Hacker News
[974.10 --> 976.92]  when the fact that Spy Spy was not there
[976.92 --> 980.76]  should have been a total indictment on the yellow website, the orange website,
[980.76 --> 984.12]  because it is a really terrific piece of work.
[984.22 --> 987.94]  It's very interesting and allows you to get this total view
[987.94 --> 989.38]  into this unseen part of the system.
[990.38 --> 992.22]  And I really like that aspect of it,
[992.26 --> 994.64]  that it's the sort of microscope of what's happening
[994.64 --> 997.68]  during the first few microseconds when your system turns on.
[997.68 --> 1000.30]  A lot of the security research that I've done
[1000.30 --> 1002.78]  is focused on that early boot time,
[1003.36 --> 1007.36]  and it's a fairly short window,
[1007.36 --> 1011.84]  but if malware or an attacker is able to take control during that time,
[1012.32 --> 1015.34]  they can really do a lot of nefarious things.
[1015.94 --> 1020.40]  And getting into those negative rings that Jess mentioned
[1020.40 --> 1021.94]  is a definite possibility.
[1022.52 --> 1026.90]  Getting into other hardware that perhaps trusts the firmware
[1026.90 --> 1029.38]  during the startup phase is a possibility.
[1029.74 --> 1032.34]  There's just a lot of really difficult problems
[1032.34 --> 1035.08]  for how do we secure systems against an attacker
[1035.08 --> 1039.06]  who can modify the data on that bus that early.
[1039.72 --> 1041.84]  And maybe it's worth explaining to folks
[1041.84 --> 1044.40]  why that bus is so critical,
[1044.54 --> 1046.64]  because effectively that is where the system
[1046.64 --> 1048.24]  is bootstrapping itself from, right?
[1049.20 --> 1052.00]  That's where effectively the first instruction
[1052.00 --> 1054.96]  that the x86 is going to execute comes from.
[1055.52 --> 1057.02]  That's where the first instruction
[1057.02 --> 1060.56]  that the BMC tends to run comes from there.
[1060.56 --> 1064.50]  The management engine has a onboard ROM,
[1064.94 --> 1067.46]  so it is actually able to do some validation of it
[1067.46 --> 1068.42]  before it starts,
[1069.00 --> 1071.80]  which is a nice thing for security,
[1072.20 --> 1074.02]  but also a somewhat frustrating thing
[1074.02 --> 1075.42]  in terms of user freedom.
[1075.84 --> 1079.76]  It means that it's not possible to swap out that code
[1079.76 --> 1082.92]  the way Core Boot or Linux Boot wants to be able to do,
[1083.36 --> 1087.06]  or OpenBMC or MicroBMC on the BMC side of things.
[1087.86 --> 1089.44]  So there's definitely a trade-off between
[1089.44 --> 1092.58]  how do we secure the systems against an attacker
[1092.58 --> 1093.88]  who can modify the flash
[1093.88 --> 1096.90]  versus how do we allow the computer owner
[1096.90 --> 1098.50]  to modify the flash
[1098.50 --> 1101.78]  to install their own firmware of their own design?
[1102.30 --> 1103.92]  Well, this is a really important tension, right?
[1104.08 --> 1106.00]  In terms of like, whose computer is it?
[1106.74 --> 1109.46]  And if I bought it and it's my computer,
[1110.04 --> 1112.90]  I should be able to load kind of arbitrary things on it.
[1113.26 --> 1115.12]  But if I can load arbitrary things on it,
[1115.12 --> 1119.24]  then arbitrary malware can do arbitrarily bad things to me, right?
[1119.52 --> 1120.90]  How do we resolve this tension?
[1121.90 --> 1124.62]  This is where a lot of my current research
[1124.62 --> 1126.42]  is going into with attestation,
[1126.68 --> 1131.70]  that if we can have the systems prove to an outside observer
[1131.70 --> 1133.92]  what they ran during startup,
[1134.28 --> 1136.98]  then perhaps we don't care so much about who put it there,
[1137.22 --> 1138.94]  as long as we can say,
[1138.94 --> 1141.24]  this is the code that we expected to be there.
[1142.08 --> 1144.28]  And I think that's an elegant way
[1144.28 --> 1146.56]  to get around a lot of that tension.
[1147.18 --> 1148.94]  Where a company like Apple
[1148.94 --> 1151.04]  has done some amazing work
[1151.04 --> 1153.16]  at building secure-by-default systems,
[1153.58 --> 1155.26]  they unfortunately have done that
[1155.26 --> 1156.60]  at the expense of user freedom.
[1157.34 --> 1158.82]  Things like Chromebooks, I think,
[1158.88 --> 1160.28]  are doing a much nicer job,
[1160.34 --> 1162.42]  where you can swap out the firmware in the Chromebook,
[1162.42 --> 1166.44]  but if you go to log into Google with modified firmware,
[1166.94 --> 1168.28]  Google's able to know that.
[1168.78 --> 1170.02]  And it's able to then prompt you
[1170.02 --> 1171.40]  on a different device to say,
[1171.52 --> 1173.84]  hey, the Chromebook that you're trying to log in on
[1173.84 --> 1175.50]  is potentially compromised.
[1175.92 --> 1176.92]  Do you still want to do it?
[1177.58 --> 1180.16]  And that attestation, I think,
[1180.24 --> 1182.54]  is really liberating
[1182.54 --> 1185.18]  because it allows the computer owner
[1185.18 --> 1186.60]  to swap everything out
[1186.60 --> 1189.58]  and still be able to tell exactly what was running,
[1190.02 --> 1191.36]  even though it's not signed by Google,
[1191.36 --> 1193.74]  so that they can sign it for themselves.
[1194.60 --> 1196.44]  Yeah, I love the design of the Chromebook.
[1196.54 --> 1197.72]  I remember when it came out.
[1197.78 --> 1199.56]  And also the fact that Chrome OS
[1199.56 --> 1200.78]  is entirely open source,
[1200.90 --> 1202.48]  so you can actually just go and fork it,
[1202.56 --> 1205.18]  which is something that Core OS ended up doing.
[1205.48 --> 1206.86]  And then when I decided
[1206.86 --> 1208.96]  to make a bespoke operating system,
[1209.16 --> 1210.04]  I did as well.
[1210.30 --> 1212.72]  But the design of the Chromebook,
[1212.76 --> 1214.16]  I think, was really revolutionary
[1214.16 --> 1218.28]  when it came to open source security
[1218.28 --> 1220.20]  because it's something that Apple
[1220.20 --> 1221.92]  had closed off for such a long time.
[1222.44 --> 1223.80]  And the Chromebooks, I think,
[1223.90 --> 1226.02]  are one of the only widespread uses
[1226.02 --> 1230.00]  of attestation in the non-mobile space
[1230.00 --> 1234.40]  that computers have been shipping with TPMs
[1234.40 --> 1236.18]  for well over a decade now,
[1236.32 --> 1239.34]  and most of them go unused.
[1239.62 --> 1242.14]  The Linux community has never really embraced them,
[1242.50 --> 1245.16]  and Windows really only uses it for BitLocker,
[1245.16 --> 1248.00]  and then only if you have a version
[1248.00 --> 1249.40]  that has that support.
[1250.22 --> 1252.58]  So it was really wonderful to see Chromebooks
[1252.58 --> 1254.66]  requiring TPMs and actually using them
[1254.66 --> 1257.72]  and actually using them for this attestation
[1257.72 --> 1258.20]  to be able to say,
[1258.36 --> 1260.66]  this is the firmware that is running on the machine.
[1260.98 --> 1263.36]  Can I ask what a TPM is?
[1263.82 --> 1264.24]  Yes.
[1264.56 --> 1265.00]  Thank you.
[1265.00 --> 1269.80]  So the TPM is a trusted platform module,
[1270.38 --> 1272.34]  and it's a small security coprocessor
[1272.34 --> 1274.88]  that can hold secrets,
[1275.54 --> 1280.32]  and it can measure the code
[1280.32 --> 1282.30]  that's running on the main CPU.
[1282.98 --> 1285.92]  Well, there's a hand-wavy bit there.
[1286.04 --> 1287.84]  It actually can't measure directly,
[1288.14 --> 1290.80]  but it can be asked to measure things,
[1290.80 --> 1293.02]  and then it can do a cryptographic signature
[1293.02 --> 1299.04]  to prove that a real TPM has measured those values,
[1299.32 --> 1301.72]  which then allows an outside observer to say,
[1301.88 --> 1303.88]  the firmware running on this machine
[1303.88 --> 1306.46]  matches the expected measurements,
[1306.96 --> 1310.30]  the expected hashes for the firmware that I installed,
[1310.56 --> 1313.56]  and the TPM attests that this is actually
[1313.56 --> 1314.22]  what's running there,
[1314.62 --> 1317.36]  and therefore perhaps you can trust this computer
[1317.36 --> 1320.14]  or this server or this Chromebook.
[1320.80 --> 1321.46]  Thank you.
[1321.56 --> 1323.42]  And it sounds like a TPM is necessary,
[1323.58 --> 1324.54]  but not sufficient,
[1325.40 --> 1326.46]  as you were describing earlier.
[1327.10 --> 1329.16]  So the TPM definitely needs
[1329.16 --> 1331.06]  a fairly tight interaction
[1331.06 --> 1332.72]  with the early boot firmware
[1332.72 --> 1335.92]  to actually be able to get any of those security guarantees.
[1336.64 --> 1337.88]  That if you don't have that,
[1338.52 --> 1341.24]  a malicious software could perhaps
[1341.24 --> 1343.18]  put fake measurements into the TPM
[1343.18 --> 1345.38]  and then get a quote from it.
[1345.88 --> 1348.40]  So it's necessary that every stage
[1348.40 --> 1349.50]  during the boot process
[1349.50 --> 1352.64]  has to be able to measure the next stage
[1352.64 --> 1354.70]  into the TPM before jumping into it.
[1354.70 --> 1356.84]  And this creates what's called the chain of trust.
[1357.78 --> 1359.06]  And the big problem right now
[1359.06 --> 1360.74]  is that most commodity firmware
[1360.74 --> 1362.98]  doesn't maintain that chain.
[1363.22 --> 1365.74]  So it's possible to get unmeasured code
[1365.74 --> 1367.92]  executing during the boot process,
[1368.14 --> 1368.70]  at which point...
[1369.34 --> 1369.64]  You're done.
[1369.64 --> 1369.78]  Yeah.
[1371.20 --> 1373.98]  The security guarantees completely evaporate.
[1374.48 --> 1375.80]  And Steve, just to make you feel better,
[1375.98 --> 1377.54]  I was relatively certain
[1377.54 --> 1379.50]  that TPM stood for tamper-proof module.
[1379.74 --> 1381.36]  I think I've probably thought that for years.
[1382.14 --> 1382.54]  All right.
[1382.70 --> 1384.56]  So thank you for asking the question.
[1385.22 --> 1386.96]  I'm like, of course it stands for tamper-proof.
[1387.04 --> 1387.42]  No, wait a minute.
[1387.52 --> 1387.72]  Oh, wait.
[1387.78 --> 1388.68]  Trusted platform module.
[1389.14 --> 1391.06]  I was definitely expecting a oof.
[1391.50 --> 1391.86]  Yeah, sure.
[1391.90 --> 1392.84]  We can explain that to you, Steve.
[1392.84 --> 1394.56]  And it is designed to be...
[1394.56 --> 1396.52]  I mean, part of the reason I thought
[1396.52 --> 1397.46]  it stood for the wrong thing
[1397.46 --> 1399.96]  is these things are designed to be tamper-proof.
[1400.06 --> 1402.10]  I mean, this actually is a...
[1402.10 --> 1404.00]  And there's important countermeasures
[1404.00 --> 1405.40]  that go into designing these things
[1405.40 --> 1407.88]  such that if you try to actually physically tamper
[1407.88 --> 1408.74]  with one of these things,
[1408.92 --> 1410.64]  it won't actually operate.
[1411.26 --> 1411.98]  Yeah, I mean, actually,
[1412.12 --> 1415.46]  one of the things that termal is most widely known for,
[1415.54 --> 1416.74]  or at least I think so,
[1416.86 --> 1418.40]  the evil mate attack.
[1419.12 --> 1422.34]  And the tamper resistance of TPMs
[1422.34 --> 1424.48]  is typically not particularly strong.
[1425.00 --> 1426.94]  They may have some hardening features
[1426.94 --> 1428.88]  in the chip design,
[1429.34 --> 1432.62]  but they are not tamper-proof by any means.
[1433.26 --> 1433.98]  Just, all right,
[1434.16 --> 1436.86]  the trample just twisting the knife a little bit.
[1437.14 --> 1439.88]  I was like, let me just jump in here
[1439.88 --> 1441.30]  to be like, I don't know how anybody
[1441.30 --> 1443.32]  could think of this as tamper-proof.
[1443.54 --> 1443.92]  Not even tamper-resistant.
[1443.92 --> 1444.80]  I'm feeling better by the minute.
[1444.96 --> 1446.18]  No, you should feel, yeah, exactly.
[1447.08 --> 1449.42]  And so going back to what Jess mentioned
[1449.42 --> 1450.64]  about evil mate attacks,
[1450.64 --> 1454.42]  there are actually quite a few physical attacks
[1454.42 --> 1455.88]  against the TPM chips
[1455.88 --> 1457.70]  that people have pulled off from,
[1458.10 --> 1459.24]  you know, some of them are more invasive
[1459.24 --> 1460.76]  that involve decapsulating them.
[1461.18 --> 1462.42]  There's the TPM genie
[1462.42 --> 1464.70]  that is basically, it's like the spy spy,
[1465.06 --> 1467.90]  but it's for the LPC bus that the TPM's on,
[1468.34 --> 1470.78]  and it's able to subvert the measurement process.
[1471.54 --> 1473.26]  So even if you can't pull a,
[1473.34 --> 1477.18]  I think Travis Armandi did a full decap on a TPM,
[1477.18 --> 1478.70]  and that's pretty invasive,
[1479.02 --> 1481.04]  that's probably not a realistic threat model
[1481.04 --> 1481.64]  for most people,
[1482.14 --> 1484.80]  but someone being able to hook some probes up
[1484.80 --> 1487.10]  to the TPM on the main board during boot
[1487.10 --> 1489.26]  and bypass the measured trust
[1489.26 --> 1492.14]  is, you know, a little more realistic.
[1492.64 --> 1494.82]  And are you saying evil mate attack?
[1494.92 --> 1495.80]  Is that, am I hearing that correctly?
[1496.08 --> 1496.26]  Yeah.
[1496.26 --> 1497.20]  Like an evil mate?
[1497.42 --> 1499.70]  Yeah, because like if you were to leave your computer
[1499.70 --> 1500.82]  in a hotel room, basically.
[1500.82 --> 1501.62]  Oh, it's the evil mate.
[1501.96 --> 1504.26]  The evil mate could attack your computer.
[1504.44 --> 1507.02]  The diabolical state actor maid.
[1507.12 --> 1507.56]  Got it, okay.
[1508.18 --> 1510.28]  Which is why when I travel, I use a Chromebook.
[1510.86 --> 1511.54]  All right then.
[1512.90 --> 1514.84]  Hopefully its TPM has not been decapped.
[1514.94 --> 1516.14]  I guess it's got Titan,
[1516.24 --> 1516.64]  which is good.
[1516.80 --> 1518.94]  It's got a pretty good reputation anyway.
[1519.56 --> 1521.70]  Yeah, the Titan chip has taken over
[1521.70 --> 1524.12]  several different roles in the Chromebook.
[1524.12 --> 1525.92]  It's both acting as the TPM.
[1526.48 --> 1529.00]  It's also acting as the closed case debugger,
[1529.38 --> 1531.32]  which is a really handy feature.
[1532.28 --> 1533.68]  If you look at, as you pointed out,
[1533.72 --> 1535.86]  a lot of my photos are pulling apart
[1535.86 --> 1537.74]  hard computers while traveling,
[1538.44 --> 1541.52]  which, you know, occasionally gets weird looks
[1541.52 --> 1542.90]  on the train or the plane
[1542.90 --> 1544.94]  when you're hooking debugging probes
[1544.94 --> 1546.94]  up to bare circuit boards.
[1547.58 --> 1548.74]  With the newer Chromebooks,
[1548.84 --> 1549.56]  with the Titan chip,
[1549.84 --> 1551.58]  you can actually do firmware updates
[1551.58 --> 1553.62]  and debugging through the Titan.
[1554.12 --> 1557.18]  Which then shows up as a special device
[1557.18 --> 1559.08]  externally on the USB.
[1559.82 --> 1561.84]  That's a great feature, actually.
[1561.92 --> 1562.60]  Do they document that?
[1562.76 --> 1564.26]  That sounds terrifically useful.
[1564.92 --> 1568.12]  There was a talk at OSFC 2018
[1568.12 --> 1569.92]  about how to use it.
[1570.22 --> 1570.82]  Oh, nice.
[1571.02 --> 1572.36]  Some of this stuff is undocumented
[1572.36 --> 1573.46]  because I know at least,
[1573.58 --> 1576.18]  like with my Chromebook on the side,
[1576.28 --> 1578.36]  the power button doubles as a security key.
[1578.74 --> 1580.48]  And so that was actually undocumented,
[1580.48 --> 1582.14]  but then people kept hacking it
[1582.14 --> 1585.02]  and adding it to two-factor auth mechanisms.
[1585.02 --> 1585.86]  And then they were like,
[1585.92 --> 1586.32]  okay, whatever.
[1586.40 --> 1586.86]  It's a thing.
[1587.80 --> 1588.52]  That is awesome.
[1588.60 --> 1590.28]  Hey, so we're going to take a quick break
[1590.28 --> 1592.36]  and we will be right back
[1592.36 --> 1594.00]  with more Trammell Hudson.
[1594.00 --> 1598.12]  On the Metal is brought to you
[1598.12 --> 1599.98]  by the Oxide Computer Company.
[1600.16 --> 1601.72]  Wait, did you say computer company, Jess?
[1601.80 --> 1602.50]  Yes, indeed.
[1602.64 --> 1603.32]  But wait a minute.
[1603.40 --> 1604.44]  Everyone runs on the public cloud.
[1604.56 --> 1605.82]  Jack Bezos owns and operates
[1605.82 --> 1606.78]  every computer on the planet.
[1606.92 --> 1608.78]  Why would anyone start a computer company?
[1609.00 --> 1610.04]  That is so not true.
[1610.20 --> 1611.82]  I have spent a bunch of time
[1611.82 --> 1612.82]  talking to folks
[1612.82 --> 1614.30]  who are still running on-premises
[1614.30 --> 1616.60]  and actually like the consensus
[1616.60 --> 1617.64]  among all of them
[1617.64 --> 1618.98]  is just a feeling of neglect
[1618.98 --> 1620.80]  because everyone thinks
[1620.80 --> 1621.98]  that like everything is moving
[1621.98 --> 1622.62]  to the public cloud,
[1622.62 --> 1623.22]  but it's not...
[1623.22 --> 1624.44]  If you're still running on-premises,
[1624.56 --> 1625.52]  it's because you haven't heard
[1625.52 --> 1626.24]  of the cloud, right?
[1626.44 --> 1628.56]  No, there are really good reasons
[1628.56 --> 1630.16]  for running on-premises still.
[1630.30 --> 1632.28]  For security, for latency,
[1632.54 --> 1634.36]  strategic reasons for your business.
[1634.70 --> 1636.28]  Wow, the people running on-premises
[1636.28 --> 1638.48]  must feel like everyone has ignored them.
[1638.78 --> 1639.66]  They do, indeed.
[1639.86 --> 1641.20]  So if this is you,
[1641.62 --> 1643.72]  please head on over to our website,
[1643.86 --> 1644.80]  Oxide.computer,
[1644.94 --> 1645.86]  sign up for our mailing list
[1645.86 --> 1647.64]  and we would love to get in touch
[1647.64 --> 1648.66]  and hear your stories.
[1648.78 --> 1650.98]  We acknowledge that you exist
[1650.98 --> 1652.32]  and you've got some really hard
[1652.32 --> 1652.96]  technical problems
[1652.96 --> 1653.52]  that we're solving.
[1653.70 --> 1655.22]  Oxide.computer, come join us.
[1660.00 --> 1661.16]  All right, we're back
[1661.16 --> 1662.14]  with Trammell Hudson.
[1662.50 --> 1663.92]  There's some terrific tales
[1663.92 --> 1665.12]  of the hardware-software interface.
[1665.38 --> 1666.08]  So Trammell,
[1666.16 --> 1667.80]  you had mentioned the OSFC,
[1667.94 --> 1669.16]  the Open Source Firmware Conference.
[1669.84 --> 1671.18]  Jess and I went to OSFC
[1671.18 --> 1672.20]  out here in Silicon Valley,
[1672.48 --> 1673.06]  whatever it was,
[1673.10 --> 1673.74]  in the fall.
[1673.84 --> 1674.38]  It was terrific.
[1675.06 --> 1675.94]  Do you want to speak a little bit
[1675.94 --> 1676.82]  about what you're seeing
[1676.82 --> 1678.82]  in the open source firmware movement?
[1678.82 --> 1683.24]  Yeah, it's a really wonderful resurgence
[1683.24 --> 1686.46]  in interest in building open firmware
[1686.46 --> 1687.32]  for these machines.
[1687.76 --> 1688.82]  A lot of it goes back
[1688.82 --> 1691.14]  to the Linux BIOS project,
[1691.28 --> 1693.74]  which was started by Ron Minnick
[1693.74 --> 1695.64]  at Los Alamos National Labs.
[1695.82 --> 1696.94]  They were one of our competitors
[1696.94 --> 1698.28]  in New Mexico.
[1698.28 --> 1701.70]  And he had similar problems.
[1701.98 --> 1705.08]  When they moved to commodity hardware
[1705.08 --> 1706.58]  or commodity CPUs
[1706.58 --> 1708.28]  for their large-scale supercomputers,
[1709.04 --> 1710.64]  managing them with the BIOS
[1710.64 --> 1713.16]  was not really working well for them.
[1714.14 --> 1715.44]  That trying to pixie boot
[1715.44 --> 1717.28]  tens of thousands of systems
[1717.28 --> 1719.34]  on a 100 megabit Ethernet
[1719.34 --> 1720.88]  just was not feasible.
[1721.82 --> 1724.32]  So Ron and one of his,
[1724.76 --> 1725.38]  some of his colleagues,
[1725.48 --> 1726.00]  had the idea of,
[1726.00 --> 1728.30]  let's just put Linux in this buy flash
[1728.30 --> 1729.68]  on these main boards
[1729.68 --> 1732.06]  and be able to k-exec
[1732.06 --> 1734.12]  into an actual payload.
[1734.86 --> 1736.12]  So rather than being stuck
[1736.12 --> 1738.22]  with whatever closed-source
[1738.22 --> 1739.62]  pixie booting things
[1739.62 --> 1741.36]  that were shipped in their machines,
[1741.58 --> 1743.42]  they were able to take advantage
[1743.42 --> 1744.92]  of all the flexibility of Linux.
[1745.44 --> 1747.08]  That turned into a core boot,
[1747.58 --> 1749.52]  and then Google selected that
[1749.52 --> 1750.88]  for all of their Chromebooks.
[1751.86 --> 1753.36]  And unfortunately,
[1753.36 --> 1755.00]  there were really no servers
[1755.00 --> 1756.90]  that were available with core boot
[1756.90 --> 1758.70]  due to licensing issues
[1758.70 --> 1760.80]  and NDAs from Intel
[1760.80 --> 1762.48]  for many years.
[1763.02 --> 1764.48]  Intel, just recently,
[1764.74 --> 1765.90]  we started a project
[1765.90 --> 1766.92]  called Linux boot,
[1767.44 --> 1768.76]  which took the idea
[1768.76 --> 1770.04]  that we could use
[1770.04 --> 1772.54]  just the DRAM initialization part
[1772.54 --> 1775.44]  out of Intel's proprietary FSP,
[1775.76 --> 1777.06]  their firmware support package,
[1777.94 --> 1779.20]  graph that onto Linux,
[1779.20 --> 1781.18]  and be able to jump
[1781.18 --> 1782.04]  very quickly
[1782.04 --> 1783.44]  from the reset vector,
[1783.94 --> 1784.78]  initialize DRAM,
[1785.12 --> 1786.10]  and then let Linux
[1786.10 --> 1787.64]  do absolutely everything else.
[1788.40 --> 1789.14]  And this project's
[1789.14 --> 1790.54]  attracted attention
[1790.54 --> 1791.26]  from a lot of the
[1791.26 --> 1792.10]  Hyperscale folks.
[1792.58 --> 1793.50]  Ron is now at Google.
[1793.80 --> 1794.60]  There are folks at Facebook
[1794.60 --> 1795.68]  who are also contributing.
[1796.54 --> 1798.12]  And we're working closely
[1798.12 --> 1799.62]  with the Open Compute project
[1799.62 --> 1801.28]  to try to make
[1801.28 --> 1802.32]  open system firmware
[1802.32 --> 1803.10]  a requirement
[1803.10 --> 1805.46]  for their open hardware branding.
[1805.46 --> 1807.52]  And it really is wonderful
[1807.52 --> 1809.76]  to have all of this flexibility.
[1810.28 --> 1811.48]  So rather than being stuck
[1811.48 --> 1814.36]  with whatever limited shell
[1814.36 --> 1815.58]  UEFI provides,
[1816.18 --> 1818.16]  you get Bash or Go or Python
[1818.16 --> 1821.10]  or whatever tools you want.
[1821.58 --> 1823.34]  I think Ron had a wonderful quote
[1823.34 --> 1824.82]  when we were getting started
[1824.82 --> 1826.56]  about Linux boot
[1826.56 --> 1828.98]  turns all of your Linux engineers
[1828.98 --> 1830.00]  into firmware engineers.
[1830.52 --> 1832.18]  So it takes it from something
[1832.18 --> 1833.38]  where you had to have
[1833.38 --> 1834.56]  really specialized knowledge
[1834.56 --> 1836.42]  and writing real mode assembly
[1836.42 --> 1838.32]  and all this arcane stuff
[1838.32 --> 1840.36]  to suddenly it's just Linux.
[1840.90 --> 1842.48]  And we all know
[1842.48 --> 1843.12]  how to use Linux.
[1843.38 --> 1845.06]  So suddenly we can do
[1845.06 --> 1846.62]  much, much more interesting things.
[1847.40 --> 1848.48]  It's a terrific development.
[1848.62 --> 1849.34]  I mean, here at Oxide,
[1849.44 --> 1850.76]  we are huge believers
[1850.76 --> 1851.84]  in the open source
[1851.84 --> 1852.50]  firmware movement.
[1852.66 --> 1853.86]  So it's great to see it
[1853.86 --> 1855.64]  have this kind of critical mass
[1855.64 --> 1856.72]  and good on you
[1856.72 --> 1858.40]  for getting the Open Compute project
[1858.40 --> 1859.46]  on board as well
[1859.46 --> 1861.06]  in terms of getting them
[1861.06 --> 1862.06]  any hardware
[1862.06 --> 1863.46]  we're going to brand open
[1863.46 --> 1864.74]  should have open firmware.
[1865.14 --> 1866.64]  So it's great to see
[1866.64 --> 1867.96]  that movement really swelling.
[1868.96 --> 1870.18]  Yeah, I think it really
[1870.18 --> 1870.98]  should be a requirement
[1870.98 --> 1872.76]  that if you're going to be
[1872.76 --> 1874.08]  making anything called open,
[1874.38 --> 1875.24]  it needs to be open
[1875.24 --> 1877.22]  at as many levels as possible.
[1877.38 --> 1878.62]  From the schematics
[1878.62 --> 1880.92]  and the board design files
[1880.92 --> 1883.10]  to all of the pieces
[1883.10 --> 1884.74]  that are running inside of it.
[1885.18 --> 1886.24]  There have been a few projects
[1886.24 --> 1887.78]  to try to build
[1887.78 --> 1889.80]  a completely open source system.
[1889.80 --> 1892.76]  Bunny made his Novena laptop
[1892.76 --> 1894.10]  that had every part
[1894.10 --> 1896.28]  had a non-NDA data sheet.
[1897.16 --> 1897.56]  Unfortunately,
[1897.86 --> 1899.10]  in sort of the large-scale
[1899.10 --> 1899.82]  server space,
[1899.90 --> 1901.10]  that's not really feasible
[1901.10 --> 1902.20]  right now.
[1902.76 --> 1904.94]  But perhaps with RISC-V,
[1905.08 --> 1905.78]  we'll start to see
[1905.78 --> 1906.64]  something there.
[1907.22 --> 1908.10]  Yeah, that would be nice
[1908.10 --> 1909.02]  down the road for sure.
[1909.70 --> 1910.74]  Hey, speaking of RISC-V,
[1910.84 --> 1911.34]  what do you think
[1911.34 --> 1912.50]  of OpenTitan?
[1912.62 --> 1913.42]  That's a very exciting
[1913.42 --> 1914.72]  announcement recently
[1914.72 --> 1915.52]  that we're certainly
[1915.52 --> 1916.24]  excited about.
[1916.48 --> 1917.08]  What's your take
[1917.08 --> 1917.70]  on OpenTitan?
[1917.70 --> 1920.90]  So I'm really encouraged
[1920.90 --> 1922.26]  that Google is making
[1922.26 --> 1923.66]  the Titan chip
[1923.66 --> 1924.78]  more widely available.
[1925.58 --> 1926.78]  Hopefully, it's going to be
[1926.78 --> 1927.34]  one of those things
[1927.34 --> 1928.26]  that starts to become
[1928.26 --> 1929.12]  a standard feature
[1929.12 --> 1930.14]  on systems,
[1930.30 --> 1931.42]  not just on Chromebooks
[1931.42 --> 1932.92]  and on Google servers.
[1933.58 --> 1935.32]  And I think it's really vital
[1935.32 --> 1937.26]  that anything that we're
[1937.26 --> 1938.52]  putting that much trust in
[1938.52 --> 1940.62]  needs to be as open
[1940.62 --> 1941.14]  as possible.
[1941.94 --> 1945.44]  And the source tree
[1945.44 --> 1945.98]  is astounding.
[1945.98 --> 1947.72]  It has the full CPU.
[1948.18 --> 1949.88]  It's got all of the software
[1949.88 --> 1951.10]  and firmware that runs on it.
[1951.46 --> 1953.46]  It's really an exceptional
[1953.46 --> 1955.30]  resource for learning
[1955.30 --> 1957.74]  how this sort of a complex
[1957.74 --> 1959.44]  security coprocessor is built.
[1960.04 --> 1961.72]  My one disappointment
[1961.72 --> 1963.70]  right now is that it only
[1963.70 --> 1965.78]  builds for a closed source
[1965.78 --> 1966.38]  FPGA.
[1967.14 --> 1968.98]  I started looking to see
[1968.98 --> 1970.06]  if I could port it over
[1970.06 --> 1971.12]  to the Project Trellis
[1971.12 --> 1972.78]  and NextPNR
[1972.78 --> 1974.56]  for open source development.
[1974.56 --> 1976.08]  But thus far,
[1976.30 --> 1977.54]  I've not yet been successful.
[1978.32 --> 1978.34]  Interesting.
[1978.50 --> 1979.76]  You have the actual tool chain
[1979.76 --> 1981.30]  itself is proprietary.
[1982.20 --> 1982.68]  Right.
[1982.78 --> 1983.62]  That if you want to build
[1983.62 --> 1985.44]  for their test board,
[1985.64 --> 1986.52]  you need the vendor
[1986.52 --> 1987.54]  FPGA tools.
[1987.74 --> 1988.88]  It's like a 50 gig download
[1988.88 --> 1990.52]  and it's locked
[1990.52 --> 1992.32]  to your one machine.
[1992.88 --> 1994.80]  And it's just not a very
[1994.80 --> 1996.16]  developer-friendly
[1996.16 --> 1996.98]  sort of environment
[1996.98 --> 1998.54]  compared to the
[1998.54 --> 2000.60]  UoSys and NextPNR
[2000.60 --> 2002.26]  that are very much
[2002.26 --> 2003.42]  coming out of
[2003.42 --> 2004.68]  the open source movement.
[2004.82 --> 2005.72]  So all of the tools
[2005.72 --> 2007.26]  play well with make files.
[2007.42 --> 2007.84]  They play well
[2007.84 --> 2008.80]  with version control.
[2010.10 --> 2011.48]  It's just an absolute
[2011.48 --> 2012.92]  delight to develop for
[2012.92 --> 2014.34]  compared to the vendor tools.
[2015.34 --> 2016.14]  So maybe on that note,
[2016.26 --> 2017.10]  I mean, for those folks
[2017.10 --> 2017.98]  who are interested
[2017.98 --> 2018.82]  in getting involved
[2018.82 --> 2020.84]  in FPGA exploration,
[2021.28 --> 2022.08]  what would you recommend?
[2022.46 --> 2023.20]  How do they start?
[2023.30 --> 2024.00]  How do they start
[2024.00 --> 2024.90]  messing around with FPGAs?
[2024.90 --> 2026.90]  There are some
[2026.90 --> 2028.62]  really low-cost
[2028.62 --> 2029.74]  FPGAs out there.
[2030.52 --> 2030.98]  Low-cost,
[2031.10 --> 2032.14]  open-source FPGAs.
[2032.68 --> 2033.38]  The Ice40
[2033.38 --> 2034.56]  comes in a lot
[2034.56 --> 2035.40]  of different variants.
[2036.04 --> 2037.20]  There's the Icebreaker
[2037.20 --> 2038.82]  is a really nice one
[2038.82 --> 2040.46]  with a very well-designed
[2040.46 --> 2042.12]  board with lots of I.O.
[2042.60 --> 2043.54]  I've been using
[2043.54 --> 2045.28]  the Upduino V2,
[2045.42 --> 2047.24]  which is like a $9 board.
[2047.82 --> 2050.06]  And it's serviceable
[2050.06 --> 2051.10]  for a lot of these things.
[2051.94 --> 2053.10]  And if folks want to do
[2053.10 --> 2054.18]  sort of larger projects,
[2054.18 --> 2056.26]  the ULX3S
[2056.26 --> 2057.58]  from Radiana
[2057.58 --> 2058.94]  Hackerspace in Croatia
[2058.94 --> 2060.30]  is a really
[2060.30 --> 2061.36]  full-featured board.
[2061.58 --> 2062.72]  It has HDMI
[2062.72 --> 2064.80]  and Wi-Fi
[2064.80 --> 2067.16]  and SD card.
[2067.52 --> 2068.68]  Lots of really
[2068.68 --> 2069.68]  useful features
[2069.68 --> 2070.72]  for building things.
[2070.88 --> 2071.28]  A lot of people
[2071.28 --> 2071.94]  are doing cool
[2071.94 --> 2072.86]  retro projects
[2072.86 --> 2073.94]  where they're
[2073.94 --> 2075.28]  emulating old consoles
[2075.28 --> 2075.72]  on it
[2075.72 --> 2077.36]  and then using
[2077.36 --> 2078.36]  the HDMI port
[2078.36 --> 2079.70]  to display the video.
[2080.68 --> 2081.76]  But at the low end,
[2082.06 --> 2082.86]  the Ice40s
[2082.86 --> 2084.10]  are really capable.
[2084.56 --> 2085.10]  It's surprising
[2085.10 --> 2086.12]  how much you can fit
[2086.12 --> 2088.10]  in a few thousand gates.
[2088.94 --> 2089.96]  I love the retro stuff,
[2090.02 --> 2090.60]  I have to say.
[2090.94 --> 2091.18]  Jess,
[2091.26 --> 2091.52]  you've got
[2091.52 --> 2093.38]  PDP-10, right,
[2093.46 --> 2094.44]  in the other room?
[2094.50 --> 2095.28]  PDP-11
[2095.28 --> 2096.32]  and PDP-8.
[2096.48 --> 2097.18]  But they're the
[2097.18 --> 2097.64]  replicas.
[2098.02 --> 2098.30]  They're the
[2098.30 --> 2099.04]  PIDPs.
[2099.86 --> 2101.10]  It's so much fun
[2101.10 --> 2101.90]  to be replicating
[2101.90 --> 2103.04]  these old machines
[2103.04 --> 2104.00]  on the much
[2104.00 --> 2104.62]  newer silicon.
[2105.96 --> 2106.18]  Trem,
[2106.20 --> 2106.62]  will you want to talk
[2106.62 --> 2107.20]  about some of the
[2107.20 --> 2108.10]  retro computing projects
[2108.10 --> 2108.38]  you've done?
[2108.42 --> 2108.76]  Because you've done
[2108.76 --> 2109.50]  a bunch of them.
[2109.50 --> 2110.98]  So,
[2111.66 --> 2112.36]  at my
[2112.36 --> 2113.16]  previous employer,
[2113.34 --> 2114.26]  we had a
[2114.26 --> 2115.30]  small retro computing
[2115.30 --> 2115.72]  museum
[2115.72 --> 2116.42]  with some
[2116.42 --> 2117.30]  PDP-11s,
[2117.38 --> 2118.14]  some actual
[2118.14 --> 2119.00]  PDP-11s,
[2119.10 --> 2119.22]  which,
[2119.88 --> 2120.98]  unlike Jess's,
[2121.46 --> 2122.60]  small version,
[2122.88 --> 2124.10]  consume a bit
[2124.10 --> 2124.62]  more power
[2124.62 --> 2125.08]  and a bit more
[2125.08 --> 2125.74]  floor space.
[2126.12 --> 2126.64]  But I saw
[2126.64 --> 2127.52]  when you were
[2127.52 --> 2128.14]  soldering together
[2128.14 --> 2129.14]  the PDP
[2129.14 --> 2129.62]  and it looked
[2129.62 --> 2130.00]  very,
[2130.10 --> 2130.50]  very fun.
[2131.38 --> 2131.52]  So,
[2131.70 --> 2132.34]  we actually
[2132.34 --> 2132.90]  found that
[2132.90 --> 2133.40]  one of the
[2133.40 --> 2134.06]  PDP-11s
[2134.06 --> 2134.78]  on Craigslist
[2134.78 --> 2135.58]  of all places.
[2136.24 --> 2136.36]  Oh,
[2136.42 --> 2136.56]  whoa,
[2136.70 --> 2137.84]  that would not
[2137.84 --> 2138.70]  be where I would
[2138.70 --> 2139.16]  think that you
[2139.16 --> 2139.72]  would find that.
[2139.72 --> 2140.66]  You found a
[2140.66 --> 2142.30]  PDP-11 on Craigslist?
[2143.28 --> 2144.14]  That is amazing.
[2144.74 --> 2145.06]  We actually
[2145.06 --> 2145.78]  ended up with
[2145.78 --> 2146.42]  an entire
[2146.42 --> 2147.36]  late 70s,
[2147.40 --> 2147.98]  early 80s
[2147.98 --> 2148.62]  data center
[2148.62 --> 2149.78]  that
[2149.78 --> 2152.04]  Mount Sinai
[2152.04 --> 2153.36]  had basically
[2153.36 --> 2154.14]  taken
[2154.14 --> 2155.72]  this massive
[2155.72 --> 2156.50]  amount of
[2156.50 --> 2156.78]  hardware
[2156.78 --> 2157.62]  and just put it
[2157.62 --> 2158.18]  in storage.
[2158.84 --> 2159.42]  And sometime
[2159.42 --> 2159.86]  in the
[2159.86 --> 2160.88]  the mid-80s.
[2161.28 --> 2161.30]  So,
[2161.38 --> 2161.96]  it was local
[2161.96 --> 2162.62]  in New York
[2162.62 --> 2162.98]  if it was
[2162.98 --> 2163.46]  Mount Sinai,
[2163.54 --> 2163.76]  right?
[2164.32 --> 2164.72]  Yeah.
[2164.96 --> 2165.24]  Oh,
[2165.26 --> 2165.56]  that's nice.
[2165.64 --> 2166.18]  You've got to
[2166.18 --> 2166.60]  ask the question
[2166.60 --> 2167.02]  anytime you get
[2167.02 --> 2167.36]  to think on
[2167.36 --> 2167.72]  Craigslist,
[2167.80 --> 2168.14]  but especially
[2168.14 --> 2168.64]  PDP-11.
[2169.04 --> 2169.74]  Was it stolen?
[2169.94 --> 2170.38]  It had to be.
[2170.38 --> 2170.84]  This has to be
[2170.84 --> 2172.10]  a stolen PDP-11.
[2172.84 --> 2173.56]  I think they
[2173.56 --> 2174.00]  had put it
[2174.00 --> 2174.60]  in storage
[2174.60 --> 2175.34]  and then 25
[2175.34 --> 2175.98]  years later
[2175.98 --> 2176.96]  they said,
[2177.12 --> 2177.72]  why are we
[2177.72 --> 2178.20]  still paying
[2178.20 --> 2179.12]  for the storage
[2179.12 --> 2179.42]  fee?
[2180.68 --> 2181.24]  And so,
[2181.40 --> 2182.66]  it was a
[2182.66 --> 2183.62]  basically,
[2183.82 --> 2184.28]  you have to
[2184.28 --> 2184.92]  take it all.
[2186.06 --> 2186.34]  So,
[2186.46 --> 2187.00]  we ended up
[2187.00 --> 2187.42]  with a couple
[2187.42 --> 2188.40]  PDP-11s,
[2188.52 --> 2189.46]  a pallet of
[2189.46 --> 2190.42]  terminals and
[2190.42 --> 2190.84]  dot matrix
[2190.84 --> 2192.02]  printers and
[2192.02 --> 2193.16]  a lifetime
[2193.16 --> 2193.94]  supply of
[2193.94 --> 2194.32]  eight-inch
[2194.32 --> 2195.06]  floppies.
[2196.04 --> 2197.08]  It was really
[2197.08 --> 2197.48]  quite the
[2197.48 --> 2197.70]  haul.
[2198.26 --> 2198.64]  That is quite
[2198.64 --> 2198.96]  the haul.
[2199.32 --> 2199.88]  Was it listed
[2199.88 --> 2200.42]  that way on
[2200.42 --> 2200.96]  Craigslist or
[2200.96 --> 2201.54]  was it just
[2201.54 --> 2202.52]  take whatever
[2202.52 --> 2203.30]  is in mystery
[2203.30 --> 2203.64]  locker,
[2203.98 --> 2204.48]  old computer
[2204.48 --> 2204.82]  equipment?
[2205.38 --> 2206.30]  It was
[2206.30 --> 2207.72]  old computer
[2207.72 --> 2208.22]  equipment,
[2208.44 --> 2209.00]  must take it
[2209.00 --> 2209.22]  all,
[2209.36 --> 2209.76]  but there was
[2209.76 --> 2210.18]  a photo
[2210.18 --> 2211.10]  and that
[2211.10 --> 2212.32]  made it
[2212.32 --> 2213.00]  very clear
[2213.00 --> 2213.48]  that it was
[2213.48 --> 2214.78]  a PDP.
[2214.78 --> 2215.72]  So,
[2215.78 --> 2215.88]  yes,
[2215.90 --> 2216.26]  we rented
[2216.26 --> 2216.62]  a panel
[2216.62 --> 2217.52]  truck and
[2217.52 --> 2218.24]  spent a
[2218.24 --> 2218.58]  week in
[2218.58 --> 2219.24]  cleaning out
[2219.24 --> 2220.06]  this locker
[2220.06 --> 2221.10]  and then
[2221.10 --> 2221.84]  we were able
[2221.84 --> 2223.06]  to restore
[2223.06 --> 2223.46]  and get
[2223.46 --> 2223.80]  two of the
[2223.80 --> 2224.44]  PDP-11s
[2224.44 --> 2224.80]  boot in,
[2225.00 --> 2225.44]  quite a few
[2225.44 --> 2225.60]  of the
[2225.60 --> 2226.54]  VT-100s
[2226.54 --> 2228.48]  and it
[2228.48 --> 2229.30]  also included
[2229.30 --> 2229.94]  quite a bit
[2229.94 --> 2231.14]  of software
[2231.14 --> 2231.94]  and
[2231.94 --> 2232.90]  including
[2232.90 --> 2233.66]  some source
[2233.66 --> 2233.90]  code.
[2234.48 --> 2234.52]  So,
[2234.60 --> 2234.90]  we've put
[2234.90 --> 2235.18]  all that
[2235.18 --> 2235.62]  up on
[2235.62 --> 2236.50]  archive.org
[2236.50 --> 2237.98]  and I
[2237.98 --> 2238.24]  have some
[2238.24 --> 2238.60]  documentation
[2238.60 --> 2239.46]  on my
[2239.46 --> 2239.74]  website
[2239.74 --> 2240.54]  about some
[2240.54 --> 2240.72]  of the
[2240.72 --> 2241.26]  paper tapes
[2241.26 --> 2241.70]  and things
[2241.70 --> 2242.30]  that we
[2242.30 --> 2242.74]  retrieved
[2242.74 --> 2243.16]  as well.
[2243.16 --> 2244.30]  That's great.
[2244.66 --> 2245.12]  What was
[2245.12 --> 2245.50]  the Opnix
[2245.50 --> 2245.80]  system?
[2245.98 --> 2246.22]  Was it
[2246.22 --> 2246.94]  running
[2246.94 --> 2247.28]  Unix?
[2248.24 --> 2248.98]  This one
[2248.98 --> 2249.34]  was running
[2249.34 --> 2250.02]  RT11
[2250.02 --> 2251.04]  because it
[2251.04 --> 2251.34]  was being
[2251.34 --> 2251.88]  used in
[2251.88 --> 2253.38]  data collection
[2253.38 --> 2254.36]  experiments.
[2255.08 --> 2255.10]  So,
[2255.18 --> 2255.62]  they needed
[2255.62 --> 2256.70]  the real-time
[2256.70 --> 2258.82]  OS and
[2258.82 --> 2259.26]  that actually
[2259.26 --> 2259.96]  gave rise
[2259.96 --> 2260.32]  to one of
[2260.32 --> 2261.20]  the funniest
[2261.20 --> 2262.32]  finds was
[2262.32 --> 2263.24]  a nine-track
[2263.24 --> 2264.18]  tape labeled
[2264.18 --> 2265.06]  digitized
[2265.06 --> 2265.98]  monkey brains.
[2267.74 --> 2268.62]  What was
[2268.62 --> 2268.86]  on it?
[2268.86 --> 2269.38]  I mean,
[2269.44 --> 2269.78]  obviously,
[2269.96 --> 2270.22]  yeah,
[2270.34 --> 2270.56]  right.
[2270.70 --> 2271.28]  That's the
[2271.28 --> 2271.62]  question.
[2272.40 --> 2272.88]  Well,
[2272.88 --> 2273.86]  we were
[2273.86 --> 2274.32]  unable to
[2274.32 --> 2274.60]  read the
[2274.60 --> 2274.88]  tape.
[2275.96 --> 2276.32]  Wait,
[2276.42 --> 2276.80]  that story
[2276.80 --> 2277.08]  has no
[2277.08 --> 2277.28]  ending?
[2277.54 --> 2277.88]  That's the
[2277.88 --> 2278.10]  end of
[2278.10 --> 2278.46]  the story?
[2278.54 --> 2278.78]  That's
[2278.78 --> 2279.28]  really sad.
[2281.02 --> 2281.72]  The digitized
[2281.72 --> 2282.28]  monkey brains
[2282.28 --> 2282.98]  had that,
[2282.98 --> 2283.70]  that's it?
[2284.12 --> 2284.48]  We don't,
[2284.48 --> 2284.98]  we don't have
[2284.98 --> 2285.18]  them.
[2285.76 --> 2286.40]  We don't have
[2286.40 --> 2286.68]  the monkey
[2286.68 --> 2287.00]  brains.
[2287.14 --> 2287.54]  We were
[2287.54 --> 2288.22]  unable to
[2288.22 --> 2288.44]  get the
[2288.44 --> 2288.86]  tape drive
[2288.86 --> 2289.70]  working,
[2289.92 --> 2290.32]  unfortunately.
[2290.98 --> 2291.52]  We did
[2291.52 --> 2292.14]  get the
[2292.14 --> 2292.52]  eight-inch
[2292.52 --> 2293.06]  floppy drive
[2293.06 --> 2293.68]  working as
[2293.68 --> 2294.42]  well as the
[2294.42 --> 2295.20]  disk packs.
[2295.56 --> 2296.16]  It's been a
[2296.16 --> 2296.48]  few years.
[2296.58 --> 2296.70]  I don't
[2296.70 --> 2296.90]  remember if
[2296.90 --> 2297.18]  that's the
[2297.18 --> 2297.94]  RLO1 or
[2297.94 --> 2298.96]  the RKO5.
[2299.98 --> 2301.02]  And on
[2301.02 --> 2301.44]  there were
[2301.44 --> 2301.76]  some,
[2302.14 --> 2302.44]  actually,
[2302.44 --> 2302.78]  quite a bit
[2302.78 --> 2303.16]  of interesting
[2303.16 --> 2303.58]  things,
[2303.72 --> 2304.66]  including some
[2304.66 --> 2305.26]  email schools
[2305.26 --> 2306.60]  that we did
[2306.60 --> 2307.40]  not upload to
[2307.40 --> 2307.84]  the archive.
[2308.24 --> 2308.70]  But one of
[2308.70 --> 2309.34]  them was a
[2309.34 --> 2311.56]  draft of a
[2311.56 --> 2312.48]  speech that one
[2312.48 --> 2312.90]  of the doctors
[2312.90 --> 2314.16]  gave to a
[2314.16 --> 2314.64]  convention of
[2314.64 --> 2315.70]  doctors talking
[2315.70 --> 2317.00]  about his
[2317.00 --> 2317.70]  department's
[2317.70 --> 2318.36]  decision to
[2318.36 --> 2318.78]  buy a
[2318.78 --> 2319.18]  computer.
[2319.18 --> 2319.22]  doctor.
[2320.02 --> 2320.84]  And he
[2320.84 --> 2321.54]  spent several
[2321.54 --> 2322.00]  hundred thousand
[2322.00 --> 2322.56]  dollars on
[2322.56 --> 2322.74]  it.
[2323.34 --> 2324.42]  And he
[2324.42 --> 2324.94]  warned the
[2324.94 --> 2325.50]  other doctors
[2325.50 --> 2327.04]  that if they
[2327.04 --> 2327.66]  bought one,
[2328.18 --> 2328.82]  they might not
[2328.82 --> 2329.74]  do any more
[2329.74 --> 2330.76]  science or
[2330.76 --> 2331.48]  doctor work
[2331.48 --> 2332.10]  because it was
[2332.10 --> 2332.66]  so much fun
[2332.66 --> 2333.12]  to program
[2333.12 --> 2334.08]  that he found
[2334.08 --> 2334.40]  that he was
[2334.40 --> 2334.84]  spending all
[2334.84 --> 2335.44]  of his time,
[2335.96 --> 2336.40]  all of his
[2336.40 --> 2337.02]  free time now,
[2337.20 --> 2338.24]  writing basic
[2338.24 --> 2338.96]  programs that
[2338.96 --> 2339.88]  would help with
[2339.88 --> 2340.58]  data analysis
[2340.58 --> 2342.06]  and processing
[2342.06 --> 2342.58]  things.
[2342.58 --> 2344.08]  Oh my gosh,
[2344.16 --> 2344.60]  that must have
[2344.60 --> 2345.88]  been mesmerizing
[2345.88 --> 2346.44]  to find.
[2347.64 --> 2348.14]  I mean,
[2348.30 --> 2349.96]  what a tale
[2349.96 --> 2350.92]  from the crypt.
[2351.48 --> 2352.04]  Did you find
[2352.04 --> 2352.46]  the physician?
[2352.66 --> 2352.78]  I mean,
[2352.80 --> 2353.80]  did you locate
[2353.80 --> 2354.20]  any of these
[2354.20 --> 2354.46]  folks?
[2355.10 --> 2356.10]  I found the
[2356.10 --> 2356.86]  physician's son
[2356.86 --> 2358.10]  and forwarded
[2358.10 --> 2358.74]  the contents
[2358.74 --> 2359.76]  over to him.
[2359.88 --> 2360.28]  The physician
[2360.28 --> 2360.70]  had passed
[2360.70 --> 2361.88]  away quite
[2361.88 --> 2362.60]  some years
[2362.60 --> 2362.96]  earlier.
[2364.42 --> 2365.02]  Wow.
[2365.54 --> 2365.82]  Well,
[2365.92 --> 2366.74]  speaking as
[2366.74 --> 2367.64]  the son of
[2367.64 --> 2368.06]  a physician
[2368.06 --> 2368.88]  who discovered
[2368.88 --> 2370.18]  that he
[2370.18 --> 2371.12]  loved software,
[2371.62 --> 2372.40]  I'm sure
[2372.40 --> 2373.40]  that his son
[2373.40 --> 2374.18]  appreciated getting
[2374.18 --> 2374.34]  it.
[2374.42 --> 2375.32]  That's amazing.
[2376.22 --> 2376.58]  Yeah,
[2376.60 --> 2377.06]  it was really
[2377.06 --> 2377.56]  quite an
[2377.56 --> 2378.16]  interesting find.
[2378.90 --> 2379.46]  So the
[2379.46 --> 2380.28]  PDP-11
[2380.28 --> 2380.68]  is definitely
[2380.68 --> 2381.38]  a fun one.
[2381.84 --> 2382.22]  I also did
[2382.22 --> 2382.48]  a lot of
[2382.48 --> 2382.80]  fun work
[2382.80 --> 2383.72]  with teletypes,
[2384.26 --> 2384.90]  one of which
[2384.90 --> 2385.60]  we hooked up
[2385.60 --> 2386.16]  to the PDP
[2386.16 --> 2386.56]  because that
[2386.56 --> 2387.60]  was period
[2387.60 --> 2388.22]  appropriate,
[2388.58 --> 2389.86]  the ASR-33.
[2391.10 --> 2391.70]  And that
[2391.70 --> 2392.02]  was the
[2392.02 --> 2392.90]  teletype
[2392.90 --> 2393.56]  that Unix
[2393.56 --> 2394.06]  was originally
[2394.06 --> 2394.64]  written on.
[2395.06 --> 2395.24]  Oh,
[2395.32 --> 2395.54]  wow.
[2395.66 --> 2396.00]  Not the
[2396.00 --> 2396.50]  specific one,
[2396.56 --> 2397.06]  but that
[2397.06 --> 2397.54]  model.
[2398.40 --> 2399.56]  And if
[2399.56 --> 2400.22]  you go to
[2400.22 --> 2401.28]  even a
[2401.28 --> 2402.04]  modern Linux
[2402.04 --> 2402.94]  system and
[2402.94 --> 2403.32]  look in
[2403.32 --> 2403.80]  Etsy
[2403.80 --> 2404.08]  term
[2404.08 --> 2404.42]  cap,
[2404.60 --> 2404.92]  you'll
[2404.92 --> 2405.68]  find a
[2405.68 --> 2405.96]  term
[2405.96 --> 2406.42]  definition
[2406.42 --> 2407.42]  for the
[2407.42 --> 2408.64]  TTY-33,
[2409.66 --> 2410.30]  which is
[2410.30 --> 2411.70]  this paper
[2411.70 --> 2412.22]  output,
[2412.34 --> 2413.30]  110 baud,
[2413.62 --> 2414.46]  caps-only
[2414.46 --> 2415.20]  teletype.
[2416.00 --> 2416.58]  And TTY
[2416.58 --> 2417.28]  comes from
[2417.28 --> 2417.98]  a teletype,
[2418.02 --> 2418.16]  right?
[2418.26 --> 2418.38]  I mean,
[2418.42 --> 2418.74]  isn't that
[2418.74 --> 2419.48]  where the
[2419.48 --> 2420.66]  origin of,
[2420.74 --> 2420.84]  I mean,
[2420.86 --> 2421.38]  we talk about
[2421.38 --> 2422.04]  TTYs all the
[2422.04 --> 2422.32]  time,
[2422.42 --> 2422.86]  and that's
[2422.86 --> 2423.44]  without
[2423.44 --> 2423.94]  thinking of
[2423.94 --> 2424.20]  it as
[2424.20 --> 2424.86]  being a
[2424.86 --> 2425.34]  teletype.
[2425.82 --> 2426.02]  Yeah.
[2426.28 --> 2427.06]  So we had
[2427.06 --> 2427.26]  that one
[2427.26 --> 2427.74]  hooked up to
[2427.74 --> 2428.92]  the PDP-11,
[2429.18 --> 2429.54]  and it was
[2429.54 --> 2430.06]  quite fun,
[2430.06 --> 2430.82]  but we
[2430.82 --> 2431.22]  didn't want
[2431.22 --> 2431.62]  to run
[2431.62 --> 2432.34]  the PDP-11
[2432.34 --> 2432.60]  all the
[2432.60 --> 2432.84]  time,
[2432.94 --> 2433.22]  so we
[2433.22 --> 2434.12]  moved it
[2434.12 --> 2434.48]  over to
[2434.48 --> 2435.52]  an emulated
[2435.52 --> 2436.50]  PDP-11,
[2436.68 --> 2437.02]  run it on
[2437.02 --> 2437.92]  Raspberry Pi.
[2438.92 --> 2439.22]  But it
[2439.22 --> 2439.58]  definitely,
[2440.48 --> 2441.24]  using that
[2441.24 --> 2441.64]  for a little
[2441.64 --> 2442.00]  while,
[2442.28 --> 2443.18]  reinforces
[2443.18 --> 2444.96]  or reminds
[2444.96 --> 2445.78]  you why
[2445.78 --> 2446.62]  all of the
[2446.62 --> 2447.26]  Unix commands
[2447.26 --> 2447.74]  are one or
[2447.74 --> 2448.44]  two characters,
[2449.00 --> 2449.52]  and why
[2449.52 --> 2450.36]  the default
[2450.36 --> 2451.18]  behavior is
[2451.18 --> 2451.48]  not to
[2451.48 --> 2452.38]  output anything
[2452.38 --> 2453.02]  if everything
[2453.02 --> 2453.74]  worked fine.
[2454.26 --> 2455.00]  Because 110
[2455.00 --> 2455.58]  baud is
[2455.58 --> 2456.50]  really slow.
[2456.66 --> 2457.18]  Really slow,
[2457.26 --> 2457.72]  that's really
[2457.72 --> 2458.08]  interesting,
[2458.28 --> 2458.48]  yeah.
[2458.48 --> 2459.54]  And you
[2459.54 --> 2459.90]  can type
[2459.90 --> 2460.52]  way faster
[2460.52 --> 2461.12]  than 110,
[2461.88 --> 2462.88]  except that
[2462.88 --> 2463.90]  the ASR-33
[2463.90 --> 2465.46]  is entirely
[2465.46 --> 2466.00]  mechanical.
[2466.34 --> 2466.88]  It has no
[2466.88 --> 2467.56]  electronics
[2467.56 --> 2468.06]  whatsoever.
[2469.04 --> 2469.94]  So there's
[2469.94 --> 2470.56]  no keyboard
[2470.56 --> 2471.14]  buffer,
[2471.84 --> 2472.18]  that when
[2472.18 --> 2472.86]  you hit a
[2472.86 --> 2473.10]  key,
[2473.60 --> 2474.46]  it has to
[2474.46 --> 2475.14]  finish
[2475.14 --> 2475.76]  transmitting
[2475.76 --> 2476.56]  that key
[2476.56 --> 2478.20]  before you
[2478.20 --> 2478.46]  can hit
[2478.46 --> 2479.00]  another one.
[2479.54 --> 2479.90]  So there's
[2479.90 --> 2480.32]  a mechanical
[2480.32 --> 2481.50]  lockout that
[2481.50 --> 2482.26]  when you hit
[2482.26 --> 2482.60]  a key,
[2483.00 --> 2483.40]  none of the
[2483.40 --> 2483.76]  other ones
[2483.76 --> 2484.50]  will go down
[2484.50 --> 2485.22]  until the
[2485.22 --> 2485.62]  transmission
[2485.62 --> 2486.26]  is finished.
[2486.64 --> 2486.86]  Wow.
[2486.86 --> 2487.90]  And what's
[2487.90 --> 2488.70]  the distance
[2488.70 --> 2489.80]  from the
[2489.80 --> 2490.28]  teletype
[2490.28 --> 2490.48]  to the
[2490.48 --> 2490.76]  actual
[2490.76 --> 2491.26]  machine?
[2491.42 --> 2491.52]  I mean,
[2491.62 --> 2492.08]  how long
[2492.08 --> 2492.30]  does it
[2492.30 --> 2492.66]  take for
[2492.66 --> 2492.86]  it to
[2492.86 --> 2493.30]  propagate,
[2493.78 --> 2494.06]  had the
[2494.06 --> 2494.40]  signal be
[2494.40 --> 2494.88]  confirmed to
[2494.88 --> 2495.32]  get back?
[2495.40 --> 2495.50]  I mean,
[2495.54 --> 2496.22]  is that a,
[2496.54 --> 2496.86]  I guess you
[2496.86 --> 2497.34]  said 110
[2497.34 --> 2497.78]  bauds,
[2497.80 --> 2497.98]  I guess
[2497.98 --> 2498.22]  that's what
[2498.22 --> 2498.60]  it is.
[2499.74 --> 2500.06]  Right,
[2500.12 --> 2500.24]  right.
[2500.30 --> 2500.66]  So this
[2500.66 --> 2501.24]  is not a
[2501.24 --> 2502.10]  latency of
[2502.10 --> 2502.54]  communication
[2502.54 --> 2502.96]  to the
[2502.96 --> 2503.28]  machine,
[2503.42 --> 2503.88]  but just
[2503.88 --> 2504.20]  in terms
[2504.20 --> 2505.32]  of clocking
[2505.32 --> 2505.86]  out the
[2505.86 --> 2506.34]  eight bits
[2506.34 --> 2507.06]  of data.
[2507.78 --> 2508.34]  And it's
[2508.34 --> 2509.02]  done via a
[2509.02 --> 2509.42]  mechanical
[2509.42 --> 2510.44]  rotor that
[2510.44 --> 2511.32]  spins around.
[2512.08 --> 2512.44]  So it's
[2512.44 --> 2513.36]  actually being
[2513.36 --> 2514.56]  driven by a
[2514.56 --> 2515.44]  AC synchronous
[2515.44 --> 2516.32]  motor for
[2516.32 --> 2516.68]  timing.
[2516.86 --> 2518.88]  And,
[2518.96 --> 2519.06]  you know,
[2519.06 --> 2519.38]  it has to
[2519.38 --> 2519.68]  make,
[2520.04 --> 2520.46]  after the
[2520.46 --> 2520.68]  gearbox,
[2520.92 --> 2521.22]  it has to
[2521.22 --> 2521.56]  make one
[2521.56 --> 2522.86]  revolution to
[2522.86 --> 2523.58]  transmit those
[2523.58 --> 2524.12]  eight bits.
[2525.18 --> 2525.90]  And so
[2525.90 --> 2526.56]  until that
[2526.56 --> 2527.46]  revolution finishes,
[2527.62 --> 2527.94]  you can't
[2527.94 --> 2528.26]  hit another
[2528.26 --> 2528.56]  key.
[2529.14 --> 2529.48]  Wow.
[2530.16 --> 2530.56]  I mean,
[2530.58 --> 2531.12]  this is like
[2531.12 --> 2531.68]  steam-powered
[2531.68 --> 2532.08]  computing.
[2532.28 --> 2532.58]  This is,
[2532.76 --> 2533.40]  this is,
[2533.86 --> 2535.14]  you must feel
[2535.14 --> 2535.60]  like you're
[2535.60 --> 2536.30]  going back to
[2536.30 --> 2536.78]  the actual
[2536.78 --> 2537.62]  dawn of
[2537.62 --> 2538.20]  computing to
[2538.20 --> 2538.68]  have such a
[2538.68 --> 2539.12]  mechanical
[2539.12 --> 2539.72]  mechanism
[2539.72 --> 2541.16]  enforcing
[2541.16 --> 2542.26]  your baud
[2542.26 --> 2542.50]  rate
[2542.50 --> 2542.96]  effectively.
[2542.96 --> 2544.32]  right,
[2544.48 --> 2544.74]  right.
[2544.82 --> 2545.42]  It's very
[2545.42 --> 2545.98]  steampunk.
[2546.54 --> 2546.90]  In fact,
[2547.00 --> 2548.36]  I made that
[2548.36 --> 2549.14]  observation that
[2549.14 --> 2550.30]  real computers
[2550.30 --> 2550.82]  are ones that
[2550.82 --> 2551.76]  have oil-fill
[2551.76 --> 2553.12]  ports and
[2553.12 --> 2553.96]  grease nipples
[2553.96 --> 2554.36]  for,
[2554.84 --> 2556.02]  to ensure
[2556.02 --> 2556.88]  proper operation.
[2557.56 --> 2558.32]  I don't think
[2558.32 --> 2558.74]  I've ever worked
[2558.74 --> 2559.04]  on a real
[2559.04 --> 2559.38]  computer.
[2559.74 --> 2559.92]  I feel,
[2560.06 --> 2560.42]  this makes
[2560.42 --> 2560.76]  me,
[2561.30 --> 2562.34]  that's,
[2562.34 --> 2562.66]  that's
[2562.66 --> 2563.18]  absolutely
[2563.18 --> 2563.54]  amazing.
[2563.88 --> 2563.96]  So,
[2564.16 --> 2565.04]  did this
[2565.04 --> 2565.64]  whole experience,
[2565.72 --> 2565.78]  I mean,
[2565.80 --> 2566.26]  the experience
[2566.26 --> 2567.46]  of resurrecting
[2567.46 --> 2568.46]  this incredibly
[2568.46 --> 2569.06]  old machine
[2569.06 --> 2569.50]  with so much
[2569.50 --> 2570.24]  functional software,
[2570.24 --> 2571.28]  and you
[2571.28 --> 2571.74]  think about,
[2571.92 --> 2571.96]  like,
[2572.06 --> 2572.20]  you know,
[2572.26 --> 2572.78]  we obviously,
[2573.06 --> 2573.64]  we no longer
[2573.64 --> 2574.34]  have the,
[2574.46 --> 2574.80]  we no longer
[2574.80 --> 2575.70]  pour oil into
[2575.70 --> 2576.32]  our machines,
[2576.96 --> 2577.66]  and yet the
[2577.66 --> 2578.38]  software that
[2578.38 --> 2578.84]  was designed
[2578.84 --> 2579.30]  around those
[2579.30 --> 2579.92]  machines has
[2579.92 --> 2580.64]  persisted.
[2581.36 --> 2581.66]  I mean,
[2581.84 --> 2582.46]  it's just amazing
[2582.46 --> 2583.70]  how much longer
[2583.70 --> 2584.16]  the software
[2584.16 --> 2584.80]  survives than
[2584.80 --> 2585.42]  the hardware
[2585.42 --> 2585.94]  that contains
[2585.94 --> 2586.14]  it,
[2586.32 --> 2586.84]  in many ways.
[2587.60 --> 2588.30]  There's a
[2588.30 --> 2589.14]  quote from
[2589.14 --> 2589.96]  one of the
[2589.96 --> 2590.92]  original Unix
[2590.92 --> 2591.66]  newsletters
[2591.66 --> 2592.60]  about that
[2592.60 --> 2593.28]  there are now
[2593.28 --> 2594.32]  10 installations
[2594.32 --> 2594.84]  around the
[2594.84 --> 2595.10]  world,
[2595.22 --> 2595.74]  and that number
[2595.74 --> 2596.22]  is expected
[2596.22 --> 2596.70]  to grow.
[2597.50 --> 2597.62]  And,
[2597.70 --> 2597.78]  you know,
[2597.78 --> 2598.22]  I really wonder
[2598.22 --> 2599.12]  how many Unix
[2599.12 --> 2599.92]  machines are
[2599.92 --> 2600.42]  there now.
[2600.64 --> 2601.16]  We have them
[2601.16 --> 2602.02]  in every pocket.
[2602.50 --> 2603.36]  They're probably
[2603.36 --> 2604.12]  in a lot of
[2604.12 --> 2604.64]  light bulbs
[2604.64 --> 2605.54]  and doorknobs.
[2606.08 --> 2606.20]  You know,
[2606.22 --> 2606.84]  it really is
[2606.84 --> 2608.28]  a phenomenal
[2608.28 --> 2610.34]  how long-lived
[2610.34 --> 2611.26]  the,
[2611.26 --> 2612.04]  kind of the
[2612.04 --> 2612.72]  Unix philosophy
[2612.72 --> 2613.30]  has been.
[2614.04 --> 2614.80]  When you think
[2614.80 --> 2615.48]  about how many,
[2615.54 --> 2615.82]  when you've got
[2615.82 --> 2616.70]  a single system,
[2616.94 --> 2617.78]  how many different
[2617.78 --> 2618.56]  Unix systems
[2618.56 --> 2619.24]  are on that
[2619.24 --> 2619.88]  single system
[2619.88 --> 2620.58]  where you've got,
[2620.92 --> 2621.42]  you've got,
[2621.50 --> 2621.74]  you know,
[2621.78 --> 2622.46]  the BMC,
[2622.62 --> 2623.00]  you've got all
[2623.00 --> 2624.14]  these other CPUs,
[2624.24 --> 2624.92]  microcontrollers,
[2624.94 --> 2625.42]  and so on,
[2625.42 --> 2625.84]  that are running
[2625.84 --> 2627.26]  their own variant
[2627.26 --> 2628.30]  inside of that
[2628.30 --> 2628.62]  larger,
[2628.78 --> 2629.30]  supposedly,
[2629.30 --> 2629.98]  single system.
[2630.98 --> 2631.42]  Right.
[2631.64 --> 2632.32]  We really need
[2632.32 --> 2632.90]  to think of
[2632.90 --> 2633.38]  our computers
[2633.38 --> 2634.02]  more as
[2634.02 --> 2635.22]  distributed systems
[2635.22 --> 2636.04]  that happen to be
[2636.04 --> 2636.90]  built onto the same
[2636.90 --> 2637.90]  board rather than
[2637.90 --> 2639.32]  single systems.
[2640.02 --> 2640.50]  Trem,
[2640.54 --> 2641.22]  I was going to ask you,
[2641.30 --> 2641.92]  it seems like
[2641.92 --> 2642.68]  the sources
[2642.68 --> 2643.44]  of some of your
[2643.44 --> 2644.36]  interesting projects
[2644.36 --> 2645.12]  have been
[2645.12 --> 2646.06]  pretty creatively
[2646.06 --> 2646.84]  sourced.
[2646.96 --> 2647.54]  You found
[2647.54 --> 2648.92]  stuff on Craigslist,
[2649.50 --> 2650.32]  stuff in storage
[2650.32 --> 2650.78]  lockers.
[2650.88 --> 2651.50]  Before we started,
[2651.76 --> 2652.38]  you were talking
[2652.38 --> 2653.06]  about a project
[2653.06 --> 2653.66]  that stemmed
[2653.66 --> 2654.12]  from finding
[2654.12 --> 2655.38]  some equipment
[2655.38 --> 2655.94]  on the side
[2655.94 --> 2656.32]  of a road
[2656.32 --> 2656.78]  in Brooklyn,
[2657.28 --> 2658.18]  and it seems
[2658.18 --> 2658.66]  like that has
[2658.66 --> 2659.06]  been a good
[2659.06 --> 2659.94]  source for
[2659.94 --> 2660.68]  some interesting
[2660.68 --> 2662.00]  projects like
[2662.00 --> 2663.16]  the Mac SE ROM
[2663.16 --> 2664.26]  that you wrote
[2664.26 --> 2664.96]  up on your page.
[2665.88 --> 2666.32]  Right.
[2666.44 --> 2666.56]  So,
[2666.64 --> 2668.12]  literally found
[2668.12 --> 2668.50]  on the side
[2668.50 --> 2668.88]  of the road
[2668.88 --> 2670.14]  in Brooklyn,
[2670.94 --> 2672.42]  an old Mac SE
[2672.42 --> 2674.34]  with a bad hard disk,
[2674.88 --> 2675.54]  and that turned
[2675.54 --> 2676.38]  into a really fun
[2676.38 --> 2676.88]  project.
[2677.36 --> 2677.96]  One of the things
[2677.96 --> 2678.54]  I like to do
[2678.54 --> 2679.40]  when I encounter
[2679.40 --> 2679.92]  old machines
[2679.92 --> 2681.26]  is to dump
[2681.26 --> 2682.00]  the ROMs.
[2682.60 --> 2683.16]  As we talked
[2683.16 --> 2683.54]  about earlier
[2683.54 --> 2684.04]  in the program,
[2684.26 --> 2684.78]  there's so much
[2684.78 --> 2685.54]  interesting stuff
[2685.54 --> 2686.68]  that lives
[2686.68 --> 2687.70]  in that firmware,
[2688.32 --> 2688.88]  and it's
[2688.88 --> 2690.24]  very instructive
[2690.24 --> 2690.86]  to see
[2690.86 --> 2691.54]  what's there.
[2692.12 --> 2692.56]  With a lot
[2692.56 --> 2693.26]  of the old ones,
[2693.42 --> 2694.38]  you find really
[2694.38 --> 2695.68]  fun bitmap fonts
[2695.68 --> 2697.06]  or icons,
[2697.48 --> 2698.14]  or in the case
[2698.14 --> 2698.80]  of the Mac SE,
[2699.38 --> 2700.18]  a really neat
[2700.18 --> 2700.86]  Easter egg
[2700.86 --> 2701.86]  of the team
[2701.86 --> 2702.24]  that worked
[2702.24 --> 2703.00]  on producing
[2703.00 --> 2704.12]  that machine.
[2705.04 --> 2705.66]  This is really cool.
[2706.48 --> 2707.70]  And your blog post
[2707.70 --> 2708.50]  goes into how
[2708.50 --> 2709.08]  exactly,
[2709.42 --> 2709.60]  I mean,
[2709.66 --> 2710.26]  that's what I love
[2710.26 --> 2711.06]  about your work,
[2711.14 --> 2711.82]  is you don't just
[2711.82 --> 2712.78]  describe what you
[2712.78 --> 2713.18]  found,
[2713.18 --> 2714.46]  but how you
[2714.46 --> 2714.96]  found it.
[2715.02 --> 2715.50]  Someone could
[2715.50 --> 2716.24]  actually go
[2716.24 --> 2717.64]  replicate this
[2717.64 --> 2719.14]  and learn about
[2719.14 --> 2720.36]  the whole tool
[2720.36 --> 2720.90]  chain that you're
[2720.90 --> 2722.26]  using to actually
[2722.26 --> 2723.12]  learn about this
[2723.12 --> 2723.38]  stuff.
[2724.16 --> 2725.00]  I think that's
[2725.00 --> 2725.90]  the really important
[2725.90 --> 2727.40]  part for documenting
[2727.40 --> 2729.14]  is to ensure
[2729.14 --> 2729.74]  that other people
[2729.74 --> 2731.50]  can do it as well.
[2732.00 --> 2733.10]  Usually in all
[2733.10 --> 2734.18]  of my conference
[2734.18 --> 2734.58]  talks,
[2735.06 --> 2735.66]  I don't want to
[2735.66 --> 2736.40]  just talk about,
[2736.56 --> 2737.18]  oh, here's a cool
[2737.18 --> 2737.70]  thing I did.
[2738.02 --> 2739.02]  I want to be able
[2739.02 --> 2740.04]  to help people
[2740.04 --> 2741.82]  do that and then
[2741.82 --> 2742.36]  go further.
[2742.36 --> 2743.28]  Most of the
[2743.28 --> 2743.82]  projects that I
[2743.82 --> 2744.24]  work on,
[2744.32 --> 2744.88]  as I mentioned,
[2745.68 --> 2746.86]  I only spend a
[2746.86 --> 2747.46]  few weeks on it
[2747.46 --> 2748.04]  before finding
[2748.04 --> 2748.72]  something else.
[2749.34 --> 2751.00]  So getting it
[2751.00 --> 2751.54]  to a state where
[2751.54 --> 2752.36]  someone else can
[2752.36 --> 2753.34]  pick it up and
[2753.34 --> 2754.70]  go forward
[2754.70 --> 2755.98]  makes me happy.
[2757.04 --> 2757.84]  Most of my
[2757.84 --> 2758.36]  really successful
[2758.36 --> 2758.92]  projects,
[2759.34 --> 2760.14]  I've really only
[2760.14 --> 2760.64]  gotten off the
[2760.64 --> 2761.62]  ground and then
[2761.62 --> 2762.62]  handed the commit
[2762.62 --> 2763.64]  keys over to
[2763.64 --> 2764.42]  the community.
[2765.36 --> 2766.00]  There's the joke
[2766.00 --> 2766.68]  about the two
[2766.68 --> 2767.70]  happiest days are
[2767.70 --> 2768.70]  when you start a
[2768.70 --> 2769.64]  new Git repo,
[2769.64 --> 2771.14]  and then the
[2771.14 --> 2771.62]  second happiest
[2771.62 --> 2772.14]  day is when you
[2772.14 --> 2772.60]  hand the keys
[2772.60 --> 2773.20]  off to another
[2773.20 --> 2773.60]  developer.
[2774.42 --> 2775.62]  That's pretty much
[2775.62 --> 2777.20]  how I treat most
[2777.20 --> 2777.82]  of these projects.
[2778.60 --> 2779.90]  And trying to
[2779.90 --> 2780.96]  document it both so
[2780.96 --> 2781.62]  that I can remember
[2781.62 --> 2782.30]  what I did,
[2782.42 --> 2783.24]  if I ever go back
[2783.24 --> 2783.62]  to it,
[2783.86 --> 2785.06]  as well as so
[2785.06 --> 2785.96]  that the next
[2785.96 --> 2786.96]  maintainer can
[2786.96 --> 2788.06]  continue to work
[2788.06 --> 2788.42]  on it,
[2788.64 --> 2789.36]  I think are really
[2789.36 --> 2790.14]  key things.
[2791.22 --> 2791.52]  Yeah, I think
[2791.52 --> 2792.02]  that's one of the
[2792.02 --> 2792.76]  greatest powers of
[2792.76 --> 2793.60]  open source is
[2793.60 --> 2794.84]  building on top of
[2794.84 --> 2795.74]  the work of others.
[2796.10 --> 2796.60]  Absolutely.
[2796.60 --> 2797.98]  And being able to
[2797.98 --> 2798.78]  see how things
[2798.78 --> 2799.68]  work for yourself,
[2799.72 --> 2800.30]  I think is just
[2800.30 --> 2800.74]  amazing,
[2801.10 --> 2801.98]  and then that
[2801.98 --> 2803.24]  whole tool chain.
[2803.76 --> 2803.82]  So,
[2803.90 --> 2804.74]  you've been able to
[2804.74 --> 2806.04]  figure out so
[2806.04 --> 2807.48]  much about so
[2807.48 --> 2807.92]  much.
[2808.58 --> 2809.18]  What are some of
[2809.18 --> 2809.70]  the things that
[2809.70 --> 2810.90]  have stumped you
[2810.90 --> 2811.50]  the longest,
[2811.64 --> 2812.04]  or some things
[2812.04 --> 2812.38]  that kind of
[2812.38 --> 2813.56]  stick out as
[2813.56 --> 2814.42]  things that were
[2814.42 --> 2815.56]  really hard to
[2815.56 --> 2815.96]  crack?
[2816.46 --> 2817.14]  It feels like so
[2817.14 --> 2817.80]  much of what you've
[2817.80 --> 2818.34]  done is hard to
[2818.34 --> 2818.90]  crack, it may be
[2818.90 --> 2819.44]  hard to pick out
[2819.44 --> 2819.90]  an example,
[2820.62 --> 2822.16]  but is there a
[2822.16 --> 2823.62]  favorite defect or
[2823.62 --> 2824.56]  artifact that took
[2824.56 --> 2825.20]  you a while to
[2825.20 --> 2825.62]  figure out?
[2825.62 --> 2827.34]  My favorite quote
[2827.34 --> 2828.20]  on that goes to
[2828.20 --> 2829.28]  Matthew Garrett,
[2829.58 --> 2830.96]  who said he's not
[2830.96 --> 2831.50]  very good at
[2831.50 --> 2832.48]  computers, he's just
[2832.48 --> 2833.32]  really bad at
[2833.32 --> 2833.82]  knowing when to
[2833.82 --> 2834.22]  give up.
[2835.32 --> 2835.96]  That's good.
[2837.10 --> 2838.80]  And I think for
[2838.80 --> 2840.58]  a lot of these
[2840.58 --> 2841.76]  projects, there's a
[2841.76 --> 2842.88]  surprising amount
[2842.88 --> 2844.56]  of banging against
[2844.56 --> 2845.42]  the same problem
[2845.42 --> 2846.62]  over and over and
[2846.62 --> 2848.12]  saying, what if I
[2848.12 --> 2849.94]  send this byte?
[2850.10 --> 2850.66]  What if I send
[2850.66 --> 2851.06]  that byte?
[2851.06 --> 2852.48]  And occasionally I
[2852.48 --> 2853.78]  feel sort of like a
[2853.78 --> 2855.00]  human fuzzer
[2855.00 --> 2856.20]  for approaching
[2856.20 --> 2856.86]  new systems,
[2857.14 --> 2858.52]  where I'll just
[2858.52 --> 2859.12]  keep tweaking
[2859.12 --> 2860.54]  inputs or
[2860.54 --> 2861.72]  parameters until
[2861.72 --> 2863.28]  things start to
[2863.28 --> 2863.52]  work.
[2864.18 --> 2865.00]  With some
[2865.00 --> 2866.04]  recency bias, my
[2866.04 --> 2867.10]  most recent
[2867.10 --> 2868.96]  headbanging has
[2868.96 --> 2869.88]  been against the
[2869.88 --> 2871.72]  ZigBee encryption
[2871.72 --> 2872.26]  protocols.
[2873.28 --> 2874.96]  And this is
[2874.96 --> 2875.66]  frustrating because
[2875.66 --> 2877.04]  they've documented
[2877.04 --> 2878.70]  them in a fairly
[2878.70 --> 2880.04]  massive data sheet.
[2880.66 --> 2881.18]  But rather than
[2881.18 --> 2881.96]  saying, here's a
[2881.96 --> 2882.40]  little bit of
[2882.40 --> 2883.40]  Python or something
[2883.40 --> 2884.22]  to show you how
[2884.22 --> 2885.42]  it's done, it's
[2885.42 --> 2885.98]  written out in
[2885.98 --> 2887.52]  prose, like a
[2887.52 --> 2888.66]  15th century
[2888.66 --> 2890.14]  alchemist textbook.
[2890.56 --> 2891.58]  Oh, God.
[2892.18 --> 2892.54]  Wow.
[2892.70 --> 2893.80]  You know, you
[2893.80 --> 2895.38]  form the message
[2895.38 --> 2897.38]  by concatenating
[2897.38 --> 2898.66]  these things,
[2898.72 --> 2899.34]  except for the
[2899.34 --> 2900.38]  leftmost bytes of
[2900.38 --> 2901.26]  this thing, and
[2901.26 --> 2904.18]  then it's
[2904.18 --> 2904.84]  completely
[2904.84 --> 2905.46]  impenetrable.
[2905.98 --> 2906.60]  And where is
[2906.60 --> 2907.60]  ZigBee used?
[2908.08 --> 2909.06]  Isn't that IoT?
[2909.34 --> 2909.74]  Yeah, isn't it
[2909.74 --> 2910.20]  used for like
[2910.20 --> 2911.32]  street lamps and
[2911.32 --> 2911.78]  things like that?
[2911.78 --> 2912.40]  Are they ZigBee
[2912.40 --> 2912.76]  connected?
[2912.98 --> 2914.12]  Where is ZigBee?
[2914.88 --> 2915.52]  What's the use for
[2915.52 --> 2915.84]  ZigBee?
[2916.58 --> 2917.98]  Well, my personal
[2917.98 --> 2919.30]  use case is that
[2919.30 --> 2920.22]  all of the IKEA
[2920.22 --> 2921.74]  smart devices use
[2921.74 --> 2921.96]  it.
[2922.64 --> 2924.40]  And I'm working
[2924.40 --> 2925.64]  on a project to
[2925.64 --> 2926.32]  let people write
[2926.32 --> 2927.54]  their own firmware
[2927.54 --> 2928.50]  extensions for
[2928.50 --> 2929.36]  these smart home
[2929.36 --> 2929.74]  devices.
[2930.96 --> 2932.66]  So, similar to my
[2932.66 --> 2933.34]  Magic Lantern
[2933.34 --> 2934.30]  project for the
[2934.30 --> 2935.04]  Canon cameras,
[2935.74 --> 2937.00]  the goal here is
[2937.00 --> 2938.40]  to let people
[2938.40 --> 2939.06]  write their own
[2939.06 --> 2940.12]  custom behaviors or
[2940.12 --> 2940.96]  add new sensors,
[2940.96 --> 2942.38]  sensors onto the
[2942.38 --> 2943.98]  actual light bulbs
[2943.98 --> 2945.64]  and LED drivers.
[2946.60 --> 2946.94]  That's awesome.
[2947.20 --> 2947.68]  Is this going to
[2947.68 --> 2948.24]  mean that we can
[2948.24 --> 2949.62]  make Jess's house
[2949.62 --> 2950.66]  less physically
[2950.66 --> 2951.44]  dependent on the
[2951.44 --> 2951.60]  internet?
[2951.72 --> 2952.16]  We've been working
[2952.16 --> 2952.94]  out of Jess's
[2952.94 --> 2954.28]  garage and there
[2954.28 --> 2954.74]  have been moments
[2954.74 --> 2955.38]  where when the
[2955.38 --> 2956.18]  internet goes out,
[2956.26 --> 2956.90]  we are unable to
[2956.90 --> 2957.54]  adjust the heat.
[2957.94 --> 2958.90]  I definitely don't
[2958.90 --> 2961.18]  use the IKEA light
[2961.18 --> 2961.38]  bulbs.
[2961.50 --> 2962.38]  I use the
[2962.38 --> 2963.38]  Philips ones.
[2963.78 --> 2964.38]  So, that would
[2964.38 --> 2964.98]  need a different
[2964.98 --> 2965.42]  protocol.
[2965.74 --> 2966.28]  Different protocol,
[2966.54 --> 2966.80]  different
[2966.80 --> 2968.34]  incompatibility, I'm
[2968.34 --> 2968.50]  sure.
[2968.50 --> 2969.30]  I think the
[2969.30 --> 2970.02]  Hue Bridge is
[2970.02 --> 2971.18]  also Zigbee, but
[2971.18 --> 2973.22]  I think Philips
[2973.22 --> 2974.14]  made a deliberate
[2974.14 --> 2975.56]  change to break
[2975.56 --> 2976.80]  compatibility a year
[2976.80 --> 2977.34]  or two ago.
[2977.68 --> 2978.96]  This is light bulb
[2978.96 --> 2980.72]  firmware incompatibility.
[2980.94 --> 2981.56]  Just to be clear,
[2981.66 --> 2982.28]  this is like the
[2982.28 --> 2983.00]  light bulbs are
[2983.00 --> 2983.48]  making themselves
[2983.48 --> 2984.64]  deliberately incompatible
[2984.64 --> 2985.06]  with one another?
[2985.42 --> 2985.68]  Yes.
[2985.86 --> 2986.58]  Yeah, Philips went
[2986.58 --> 2987.70]  so far as to even
[2987.70 --> 2989.48]  disallow, well, you
[2989.48 --> 2990.30]  can do it so that you
[2990.30 --> 2991.14]  don't need the bridge
[2991.14 --> 2992.30]  and you just use pure
[2992.30 --> 2993.48]  Bluetooth to communicate
[2993.48 --> 2994.22]  with your light bulbs,
[2994.38 --> 2994.92]  which is also
[2994.92 --> 2995.34]  interesting.
[2995.58 --> 2996.52]  Oh, thank goodness.
[2996.52 --> 2997.08]  I know.
[2998.02 --> 3000.60]  So, like, how many
[3000.60 --> 3001.34]  rings does my light
[3001.34 --> 3001.68]  bulb have?
[3002.40 --> 3002.84]  Why?
[3003.76 --> 3004.38]  Like, is there a
[3004.38 --> 3005.10]  ring negative three
[3005.10 --> 3005.70]  on my light bulb?
[3005.84 --> 3006.80]  I mean, is there an
[3006.80 --> 3007.92]  SMM on my light bulb?
[3008.62 --> 3009.20]  Trammell, one of the
[3009.20 --> 3010.20]  things that you talked
[3010.20 --> 3011.20]  about was your, the
[3011.20 --> 3012.72]  Canon firmware reverse
[3012.72 --> 3013.10]  engineering.
[3013.34 --> 3014.30]  Could you describe how
[3014.30 --> 3014.92]  you got into that?
[3015.02 --> 3016.42]  That, I mean, the guts
[3016.42 --> 3018.22]  it takes to load new
[3018.22 --> 3019.26]  firmware on your camera,
[3019.40 --> 3020.50]  on your SLR camera,
[3020.86 --> 3021.84]  is just more guts than
[3021.84 --> 3022.30]  I've got.
[3022.42 --> 3023.26]  I mean, that was, that
[3023.26 --> 3024.32]  was very impressive.
[3024.32 --> 3028.74]  That was a, a big
[3028.74 --> 3029.26]  decision.
[3030.20 --> 3032.94]  And that's actually
[3032.94 --> 3033.56]  a relief to know.
[3034.28 --> 3034.72]  Yeah.
[3034.88 --> 3035.78]  The first time I did
[3035.78 --> 3038.12]  it, I tried to boot my
[3038.12 --> 3039.56]  own firmware on it
[3039.56 --> 3040.86]  after, you know,
[3040.86 --> 3042.02]  spending a month or
[3042.02 --> 3043.06]  so reverse engineering
[3043.06 --> 3045.14]  and trying to make
[3045.14 --> 3046.04]  certain that I was
[3046.04 --> 3047.34]  doing, that everything
[3047.34 --> 3048.10]  was going to work.
[3048.42 --> 3048.90]  Yeah.
[3048.94 --> 3049.48]  So I sat down with my
[3049.48 --> 3050.08]  partner and said,
[3050.14 --> 3053.14]  well, here's what I'm
[3053.14 --> 3053.56]  going to try.
[3054.98 --> 3055.86]  I want you to say
[3055.86 --> 3056.64]  goodbye to the Canon
[3056.64 --> 3057.42]  camera, please.
[3058.14 --> 3058.34]  Yeah.
[3059.30 --> 3060.90]  You know, worst case,
[3061.14 --> 3062.92]  you know, maybe I can
[3062.92 --> 3063.66]  get it repaired under
[3063.66 --> 3064.00]  warranty.
[3064.40 --> 3065.40]  But it turns out that I
[3065.40 --> 3066.86]  was able to get new
[3066.86 --> 3067.80]  code running on it.
[3068.30 --> 3070.00]  And I found a really
[3070.00 --> 3072.12]  neat trick that doesn't
[3072.12 --> 3073.12]  modify the camera at
[3073.12 --> 3073.40]  all.
[3073.82 --> 3074.74]  That there is a
[3074.74 --> 3076.30]  developer mode or a
[3076.30 --> 3078.02]  debug mode that if you,
[3078.16 --> 3079.38]  if you have a specially
[3079.38 --> 3080.74]  named SD card with a
[3080.74 --> 3081.96]  specially named file on
[3081.96 --> 3084.02]  it, the camera will
[3084.02 --> 3086.06]  ignore what's in ROM and
[3086.06 --> 3087.82]  copy that file into RAM
[3087.82 --> 3089.00]  and jump into it.
[3089.46 --> 3089.78]  Whoa.
[3090.08 --> 3090.82]  That is scary.
[3091.00 --> 3091.90]  That's a good find.
[3092.04 --> 3092.90]  That's great, though.
[3093.80 --> 3094.84]  See, that's your first
[3094.84 --> 3095.62]  reaction is that's
[3095.62 --> 3096.04]  terrifying.
[3096.14 --> 3096.82]  My first reaction is
[3096.82 --> 3097.32]  that's great.
[3097.68 --> 3097.94]  Right.
[3098.18 --> 3098.96]  I guess it's great and
[3098.96 --> 3099.34]  terrifying.
[3099.68 --> 3100.12]  That's great.
[3100.22 --> 3100.48]  Yes.
[3100.80 --> 3102.34]  So this meant that it
[3102.34 --> 3103.40]  no longer was necessary
[3103.40 --> 3104.94]  to, to reflash the
[3104.94 --> 3105.74]  camera at all.
[3106.16 --> 3106.48]  Right.
[3106.48 --> 3107.80]  You just had to, you
[3107.80 --> 3108.68]  know, rename the card
[3108.68 --> 3110.68]  and suddenly we could
[3110.68 --> 3113.00]  run firmware and that
[3113.00 --> 3114.44]  switched it from a
[3114.44 --> 3115.56]  incredibly terrifying
[3115.56 --> 3118.86]  sort of, you're going
[3118.86 --> 3120.20]  to break a $3,000 camera
[3120.20 --> 3122.16]  to hopefully this won't
[3122.16 --> 3122.96]  damage things.
[3123.26 --> 3125.36]  And to the best of my
[3125.36 --> 3126.48]  knowledge, we've never
[3126.48 --> 3127.96]  bricked any of the, any
[3127.96 --> 3128.52]  of the cameras.
[3128.70 --> 3129.86]  That is amazing.
[3130.54 --> 3131.80]  And how did you discover
[3131.80 --> 3132.24]  that mode?
[3132.32 --> 3133.02]  How did you discover the
[3133.02 --> 3134.24]  debug mode from reverse
[3134.24 --> 3134.76]  engineering it?
[3135.32 --> 3135.64]  Yeah.
[3135.64 --> 3136.66]  From, from walking
[3136.66 --> 3138.14]  through the, the boot
[3138.14 --> 3139.50]  path in the firmware to
[3139.50 --> 3140.50]  try to figure out sort
[3140.50 --> 3142.52]  of where do I need to
[3142.52 --> 3143.96]  hook things in order to
[3143.96 --> 3145.80]  be able to, to get my
[3145.80 --> 3147.26]  code execution work in
[3147.26 --> 3147.54]  there.
[3148.96 --> 3149.32]  Wow.
[3149.66 --> 3150.56]  And it was one of those
[3150.56 --> 3151.72]  sort of, huh, that's
[3151.72 --> 3152.06]  funny.
[3152.64 --> 3154.10]  And it's, it's an actual
[3154.10 --> 3155.86]  string on the SD card.
[3155.94 --> 3157.20]  The name of the SD card
[3157.20 --> 3158.18]  is how, is what it keys
[3158.18 --> 3158.46]  on.
[3159.12 --> 3159.38]  Yeah.
[3159.42 --> 3159.58]  Yeah.
[3159.58 --> 3161.60]  So if you, and that was
[3161.60 --> 3162.88]  one of those things, you
[3162.88 --> 3163.26]  know, one of the points
[3163.26 --> 3163.94]  I've made in a few of the
[3163.94 --> 3165.62]  talks that debug strings
[3165.62 --> 3167.62]  are incredibly useful for
[3168.18 --> 3169.62]  the reverse engineer that,
[3170.30 --> 3171.42]  you know, so seeing
[3171.42 --> 3173.30]  something like, you know,
[3173.34 --> 3175.08]  a plain text string show
[3175.08 --> 3176.40]  up in there, you know, was
[3176.40 --> 3177.14]  one of those things like,
[3177.22 --> 3178.68]  huh, let me see what's
[3178.68 --> 3179.18]  happening there.
[3179.28 --> 3180.06]  Let me, let me walk
[3180.06 --> 3181.02]  through that code path.
[3181.24 --> 3181.78]  You know, what, what
[3181.78 --> 3182.64]  references that?
[3183.12 --> 3184.16]  So in terms of reverse
[3184.16 --> 3185.00]  engineering, it's always
[3185.00 --> 3185.94]  something, and I noticed
[3185.94 --> 3187.28]  that Rick Alther did this
[3187.28 --> 3188.84]  as well in his USB
[3188.84 --> 3189.74]  Anywhere exploit.
[3189.90 --> 3190.50]  I mean, one of the things
[3190.50 --> 3191.88]  that originally keyed him
[3191.88 --> 3193.52]  on it was the, looking at,
[3193.52 --> 3195.16]  at an interesting string in a
[3195.16 --> 3196.00]  binary, it's like, wait a
[3196.00 --> 3196.80]  minute, what, what is that
[3196.80 --> 3197.50]  string doing there?
[3197.58 --> 3198.42]  How is it used?
[3199.14 --> 3199.34]  Right, right.
[3199.34 --> 3199.90]  And how can I better
[3199.90 --> 3200.52]  understand it?
[3201.74 --> 3203.54]  Colin Molnar gave a, a
[3203.54 --> 3205.34]  fun talk at, um, either
[3205.34 --> 3207.18]  HushCon or SummerCon, where
[3207.18 --> 3209.58]  he pointed out that if you
[3209.58 --> 3212.10]  are a vendor and trying to
[3212.10 --> 3213.84]  keep tabs on the people
[3213.84 --> 3214.92]  reverse engineering your
[3214.92 --> 3216.28]  product, that you could
[3216.28 --> 3218.60]  embed some fairly unique,
[3218.60 --> 3220.80]  but tantalizing strings in
[3220.80 --> 3222.40]  there and then buy Google
[3222.40 --> 3223.78]  AdWords for them.
[3224.58 --> 3224.98]  Oh yeah.
[3225.58 --> 3226.58]  I think that was a
[3226.58 --> 3228.36]  Usenix talk or something.
[3229.00 --> 3231.06]  Usenix security or, yeah.
[3231.44 --> 3232.64]  That is so dark and
[3232.64 --> 3232.92]  genius.
[3233.04 --> 3234.10]  I'm, I'm afraid to Google
[3234.10 --> 3234.56]  anything.
[3235.24 --> 3235.56]  Yeah.
[3236.48 --> 3237.42]  Because of course the first
[3237.42 --> 3238.20]  thing we do when you see
[3238.20 --> 3238.86]  these strings, you're like,
[3238.94 --> 3239.06]  oh.
[3239.56 --> 3240.24]  Oh, I'm going to Google it.
[3240.94 --> 3241.20]  Yeah.
[3242.04 --> 3243.88]  That is, that is hilarious.
[3244.34 --> 3245.08]  And then, I mean, you could
[3245.08 --> 3246.54]  buy an ad that would really
[3246.54 --> 3248.58]  give people a, a start.
[3248.58 --> 3250.66]  Well, you don't even need
[3250.66 --> 3252.66]  to display the ad to them.
[3253.00 --> 3254.30]  It's just the, did you
[3254.30 --> 3256.32]  suddenly get charged for it?
[3256.60 --> 3258.14]  Then that means that someone
[3258.14 --> 3259.34]  has gotten, you know, to
[3259.34 --> 3260.24]  someone somewhere that
[3260.24 --> 3261.66]  stage in their, in their
[3261.66 --> 3262.74]  firmware reverse engineering.
[3263.10 --> 3263.50]  Yeah.
[3263.52 --> 3265.56]  That's, that's darkly genius
[3265.56 --> 3266.68]  and terrifying.
[3267.24 --> 3268.48]  Uh, it makes me afraid to
[3268.48 --> 3269.60]  Google arbitrary strings.
[3269.88 --> 3270.80]  But yeah, it's definitely one
[3270.80 --> 3271.80]  of those things where, you
[3271.80 --> 3272.44]  know, when you see something
[3272.44 --> 3273.68]  interesting like that, you
[3273.68 --> 3274.58]  know, you kind of dig into
[3274.58 --> 3275.26]  it, like, why is that
[3275.26 --> 3275.56]  there?
[3275.56 --> 3277.76]  So there's one feature in
[3277.76 --> 3279.08]  the camera that I've not
[3279.08 --> 3281.54]  figured out that, or I've
[3281.54 --> 3283.40]  not found the pads for the
[3283.40 --> 3285.12]  debug UART, but I found
[3285.12 --> 3286.78]  that I did find the password
[3286.78 --> 3288.88]  for the debug UART, uh, in
[3288.88 --> 3289.30]  the string.
[3290.24 --> 3291.74]  So there's a debug UART
[3291.74 --> 3292.44]  somewhere.
[3292.60 --> 3293.42]  Now, is it possible that it's
[3293.42 --> 3294.42]  only on like a dev board?
[3294.50 --> 3295.48]  Is it possible that it's not
[3295.48 --> 3297.40]  on the camera as shipped?
[3298.20 --> 3298.64]  Sure.
[3298.94 --> 3299.16]  Yeah.
[3299.18 --> 3300.80]  It's, it's really hard to
[3300.80 --> 3301.04]  know.
[3301.24 --> 3302.02]  You know, we, we didn't,
[3302.36 --> 3303.62]  Canon doesn't ship, uh,
[3303.62 --> 3304.76]  schematics for, for, for
[3304.76 --> 3305.10]  those.
[3305.56 --> 3306.20]  Anymore.
[3306.98 --> 3307.14]  Right.
[3307.90 --> 3309.44]  But going back to a
[3309.44 --> 3310.42]  previous point about that,
[3310.54 --> 3312.38]  once I ported it from the,
[3312.38 --> 3314.14]  the Canon 5D Mark II, which
[3314.14 --> 3317.02]  is $3,000 camera to the T2i,
[3317.16 --> 3318.86]  which was a $400 camera,
[3319.36 --> 3320.58]  suddenly the number of
[3320.58 --> 3322.70]  people willing to use it and
[3322.70 --> 3324.26]  try it out and develop for
[3324.26 --> 3326.70]  it just went from, uh,
[3326.70 --> 3330.02]  literally one to, you know,
[3330.08 --> 3330.62]  dozens.
[3330.62 --> 3334.44]  Uh, and the, uh, the, uh,
[3334.44 --> 3335.54]  wonderful community developed
[3335.54 --> 3337.34]  around it and, uh, some
[3337.34 --> 3339.06]  really motivated folks really
[3339.06 --> 3341.42]  wanted to keep developing it.
[3341.52 --> 3343.04]  So I handed the commit keys
[3343.04 --> 3345.10]  over to Alex and they've been
[3345.10 --> 3346.66]  running a, you know, an
[3346.66 --> 3348.48]  absolutely amazing project, uh,
[3348.48 --> 3349.00]  ever since.
[3349.00 --> 3350.56]  We just celebrated the 10th
[3350.56 --> 3352.14]  anniversary of that project.
[3352.72 --> 3353.06]  That's great.
[3353.12 --> 3354.20]  And what does Canon feel about
[3354.20 --> 3354.38]  this?
[3354.38 --> 3355.22]  I mean, I'm sure they had
[3355.22 --> 3357.28]  very mixed feelings at the
[3357.28 --> 3358.28]  outset, but they've, they've
[3358.28 --> 3359.12]  got to, you got to embrace
[3359.12 --> 3359.76]  it at some point.
[3360.22 --> 3361.22]  They've never mentioned
[3361.22 --> 3362.52]  anything to me or anything
[3362.52 --> 3363.02]  publicly.
[3363.42 --> 3366.24]  So I personally know that it's
[3366.24 --> 3368.64]  sold a lot of cameras, but I
[3368.64 --> 3370.56]  don't know if they recognize
[3370.56 --> 3371.00]  that.
[3371.54 --> 3373.50]  There was a talk at, uh, Black
[3373.50 --> 3375.66]  Hat and, uh, Hack Lou from a
[3375.66 --> 3378.38]  group that found a vulnerability
[3378.38 --> 3379.86]  in, in the, uh, the PTP
[3379.86 --> 3381.40]  protocol on the cameras.
[3381.88 --> 3383.86]  And Canon did fix that.
[3383.86 --> 3385.92]  They actually issued CVEs and,
[3385.92 --> 3386.78]  and patched that.
[3387.38 --> 3388.08]  So somebody is paying
[3388.08 --> 3388.46]  attention.
[3389.16 --> 3390.42]  It seems that remotely
[3390.42 --> 3391.94]  exploitable ones, which this
[3391.94 --> 3393.48]  was, you know, are going to
[3393.48 --> 3394.02]  get fixed.
[3394.46 --> 3396.46]  Locally exploitable perhaps are
[3396.46 --> 3398.36]  not, uh, a high priority.
[3399.00 --> 3399.48]  Interesting.
[3399.64 --> 3399.74]  All right.
[3399.74 --> 3400.62]  We got to take another quick
[3400.62 --> 3401.98]  break and then we'll be back
[3401.98 --> 3403.72]  with more Trammell Hudson and
[3403.72 --> 3404.16]  On The Metal.
[3407.48 --> 3408.98]  On The Metal is brought to
[3408.98 --> 3410.20]  you by the Oxide Computer
[3410.20 --> 3411.18]  Company, where we're going to
[3411.18 --> 3413.32]  try a new feature shamelessly
[3413.32 --> 3413.84]  ripped off of our
[3413.84 --> 3415.08]  reply all's yes, yes, no,
[3415.16 --> 3416.60]  where our boss, Steve Tuck,
[3416.90 --> 3417.64]  brings us a tweet.
[3417.80 --> 3418.80]  We, he does not understand.
[3419.12 --> 3420.44]  And Jess and I try to explain
[3420.44 --> 3420.70]  it to him.
[3420.74 --> 3421.46]  Steve, do you have a tweet?
[3422.24 --> 3422.80]  I sure do.
[3422.94 --> 3423.36]  Go for it.
[3423.36 --> 3424.80]  The tweet in question,
[3425.52 --> 3427.58]  UEFI preboot network stack
[3427.58 --> 3429.08]  engaged the onboard Nick in
[3429.08 --> 3430.08]  such a way that it would write
[3430.08 --> 3432.40]  back DMA to particular physical
[3432.40 --> 3433.90]  memory pages sometime after
[3433.90 --> 3435.12]  control was passed to the
[3435.12 --> 3435.56]  bootloader.
[3435.70 --> 3436.94]  Corruption would occur somewhere
[3436.94 --> 3438.74]  in the user parts of the RAM
[3438.74 --> 3439.14]  disk.
[3439.92 --> 3441.32]  No idea.
[3441.58 --> 3442.16]  No idea.
[3442.28 --> 3442.92]  Jess, do you understand this
[3442.92 --> 3443.14]  tweet?
[3443.80 --> 3445.44]  So I understand definitely the
[3445.44 --> 3447.52]  part about the UEFI preboot
[3447.52 --> 3450.06]  networking stack, but the part
[3450.06 --> 3451.70]  about DMA is in question marks.
[3451.70 --> 3454.20]  So it's like, I guess you're not
[3454.20 --> 3455.38]  really sure where that's going.
[3455.38 --> 3456.28]  You're overthinking it.
[3456.38 --> 3457.34]  I understand this tweet.
[3457.68 --> 3459.54]  Running on-prem is painful.
[3459.66 --> 3460.98]  This is dealing with an awful,
[3460.98 --> 3462.46]  awful firmware bug.
[3462.64 --> 3464.16]  Firmware has overwritten part of
[3464.16 --> 3465.98]  the operating system in a way that
[3465.98 --> 3468.16]  is extremely painful to debug.
[3468.16 --> 3469.56]  So who do you go to in that case?
[3469.68 --> 3470.54]  Who do you go to?
[3470.62 --> 3472.22]  You definitely strangle one of
[3472.22 --> 3472.64]  your vendors.
[3473.04 --> 3473.94]  You strangle one of your vendors.
[3474.02 --> 3475.44]  Unfortunately, your vendor is a PC
[3475.44 --> 3477.50]  vendor because all of the existing
[3477.50 --> 3480.14]  computer companies are selling
[3480.14 --> 3481.08]  personal computers.
[3481.58 --> 3483.00]  What we need is a new computer
[3483.00 --> 3483.44]  company.
[3483.62 --> 3484.88]  So this is just saying I'm an
[3484.88 --> 3486.48]  intense pain trying to run
[3486.48 --> 3487.58]  systems on-premises.
[3487.76 --> 3488.94]  That's exactly what it's saying.
[3489.00 --> 3490.12]  Steve, what can someone do if
[3490.12 --> 3491.38]  they're intense pain running on-premises?
[3491.70 --> 3493.04]  Well, if someone is running an
[3493.04 --> 3494.36]  intense pain on-premises, what they
[3494.36 --> 3495.50]  should do is go over to
[3495.50 --> 3497.46]  oxide.computer to learn a little
[3497.46 --> 3498.86]  bit more about how we are going to
[3498.86 --> 3499.84]  take that pain away.
[3500.04 --> 3501.74]  Help is on the way.
[3502.00 --> 3503.44]  Join us at oxide.computer.
[3503.64 --> 3504.76]  You are not alone.
[3508.34 --> 3510.76]  We're back with Trammell talking
[3510.76 --> 3512.60]  every kind of hardware software
[3512.60 --> 3513.88]  interface you can imagine.
[3514.70 --> 3516.92]  So Trammell, what have you been up
[3516.92 --> 3517.46]  to recently?
[3517.60 --> 3519.40]  You mentioned the Zigbee protocol.
[3519.64 --> 3521.52]  What's struck your fancy recently?
[3521.52 --> 3524.82]  So like Jess mentioned, you know,
[3524.94 --> 3526.78]  it'd be really nice to have all of
[3526.78 --> 3528.98]  these home automation projects not
[3528.98 --> 3530.00]  dependent on the internet.
[3530.74 --> 3534.18]  So that's something that I think is a
[3534.18 --> 3535.58]  really worthwhile goal.
[3536.08 --> 3538.00]  And along with my partner, we're
[3538.00 --> 3539.86]  trying to put together some workshops
[3539.86 --> 3544.44]  on how to build non-internet connected
[3544.44 --> 3545.22]  things.
[3545.34 --> 3547.06]  So it's not only Jess that has this
[3547.06 --> 3547.58]  problem then.
[3547.76 --> 3549.30]  I was giving Jess maybe too much
[3549.30 --> 3550.92]  grief, but this is a common problem.
[3550.92 --> 3552.50]  Are poorly integrated.
[3552.72 --> 3554.02]  There is like, have you, have you
[3554.02 --> 3555.92]  looked at Home Assistant Trammell?
[3556.50 --> 3557.42]  The open source project?
[3558.34 --> 3560.30]  I've, we ran it for a little while.
[3561.44 --> 3563.64]  It's a, it's a bit of a beast to get
[3563.64 --> 3564.12]  up and running.
[3564.56 --> 3565.20]  Oh no, it is.
[3565.24 --> 3565.90]  It is totally.
[3566.04 --> 3567.94]  I actually decided that I hated it
[3567.94 --> 3568.62]  after I did that.
[3568.72 --> 3568.82]  So.
[3569.38 --> 3570.40]  What is Home Assistant?
[3571.00 --> 3572.92]  It's an open source kind of
[3572.92 --> 3574.64]  integrates or tries to integrate with
[3574.64 --> 3576.62]  every single kind of IoT device out
[3576.62 --> 3576.84]  there.
[3577.22 --> 3578.66]  But of course it's a bear to configure.
[3578.66 --> 3579.14]  Yeah.
[3579.14 --> 3581.06]  It's just a Python monolith.
[3581.64 --> 3581.96]  Right.
[3582.36 --> 3583.04]  Pretty large.
[3583.74 --> 3585.46]  So we've been playing around with a
[3585.46 --> 3588.10]  Node-RED, which is sort of a fun box
[3588.10 --> 3590.60]  and string programming model for, for
[3590.60 --> 3591.54]  doing some of the home automation.
[3591.86 --> 3592.46]  Oh, nice.
[3593.06 --> 3595.60]  And it has plugins for Zigbee and HomeKit
[3595.60 --> 3597.26]  and a variety of other ones.
[3597.62 --> 3599.34]  The other one that I'm looking into
[3599.34 --> 3602.04]  playing with is the Mozilla IoT gateway
[3602.04 --> 3605.02]  that they have a fairly nice JSON object
[3605.02 --> 3607.88]  description where devices can describe
[3607.88 --> 3609.38]  to the gateway how they want to be
[3609.38 --> 3609.94]  controlled.
[3610.44 --> 3611.40]  That looks very flexible.
[3611.82 --> 3612.26]  That's cool.
[3612.70 --> 3614.36]  But the Zigbee ones are nice because
[3614.36 --> 3617.10]  they're so very, very inexpensive.
[3617.50 --> 3619.40]  The IKEA ones are pretty high quality.
[3619.56 --> 3622.92]  They've got nice Silicon Labs modules
[3622.92 --> 3625.18]  inside for doing all of the wireless.
[3625.90 --> 3628.26]  So I have enough reverse engineering done
[3628.26 --> 3629.74]  on there to be able to boot
[3629.74 --> 3632.42]  MicroPython and either interface with
[3632.42 --> 3635.30]  the proprietary Ember stack that IKEA is
[3635.30 --> 3637.76]  using, although it turns out to be
[3637.76 --> 3638.78]  really space constrained.
[3639.32 --> 3641.26]  I only have a few tens of kilobytes
[3641.26 --> 3643.24]  to fit the MicroPython.
[3643.72 --> 3646.30]  Or what I'm working on now is trying to
[3646.30 --> 3648.56]  build a fairly complete Zigbee stack
[3648.56 --> 3651.54]  in Python that can then run, you know,
[3651.56 --> 3653.42]  standalone in the MicroPython environment
[3653.42 --> 3653.90]  on there.
[3654.68 --> 3654.88]  Nice.
[3655.42 --> 3657.64]  Obviously, this is all neat and
[3657.64 --> 3658.68]  intellectually interesting.
[3659.20 --> 3661.26]  In terms of like, I have to confess,
[3661.26 --> 3663.80]  I'm a bit of a Luddite on home automation.
[3664.08 --> 3666.34]  I'm still with the light switches.
[3666.94 --> 3668.60]  The nice thing is that you can actually
[3668.60 --> 3671.26]  like program at, like, I can make it so
[3671.26 --> 3672.80]  that when I leave the house, certain lights
[3672.80 --> 3675.08]  turn on or when I'm like entering the house,
[3675.14 --> 3676.04]  certain lights turn on.
[3676.42 --> 3677.42]  Or when someone's in the house,
[3677.48 --> 3678.84]  you can turn the lights off on them.
[3678.98 --> 3680.22]  Yeah, for sure.
[3680.56 --> 3683.08]  You can set up almost like Cron job
[3683.08 --> 3686.16]  like behavior for on an event,
[3686.30 --> 3686.90]  something happens.
[3686.92 --> 3688.60]  I just don't want to administer my house.
[3688.60 --> 3689.04]  Yes.
[3689.12 --> 3691.68]  Maybe I'm, you know, again, I'll break your house.
[3691.82 --> 3692.76]  I'll break my house.
[3692.86 --> 3693.16]  Exactly.
[3693.32 --> 3694.92]  So if you're extremely wealthy,
[3694.92 --> 3697.76]  what you can do is output this to like
[3697.76 --> 3699.02]  a remote sysadmin.
[3699.24 --> 3701.02]  So you have like this smart house
[3701.02 --> 3702.56]  and then this remote sysadmin
[3702.56 --> 3705.38]  has power over your entire house
[3705.38 --> 3707.62]  and all of your smart controls,
[3707.70 --> 3709.20]  which that sounds horrifying.
[3710.16 --> 3711.38]  What hours do they work?
[3712.24 --> 3713.82]  I mean, I mean, it's more like,
[3714.02 --> 3715.06]  what are they going to do
[3715.06 --> 3717.52]  when they actually have like the power
[3717.52 --> 3718.78]  to control all your lights?
[3718.80 --> 3720.82]  Are they going to like just totally mess with you
[3720.82 --> 3722.48]  while you're watching some horror movies?
[3722.66 --> 3724.16]  I just like getting malware in my house
[3724.16 --> 3725.42]  just sounds horrifying.
[3725.62 --> 3727.04]  I mean, it's, I don't know.
[3727.28 --> 3729.04]  Tram, well, my, my, my,
[3729.10 --> 3730.36]  it sounds like you're much more optimistic
[3730.36 --> 3732.28]  about this stuff than, than I am.
[3732.86 --> 3735.62]  Well, there's a few features that I really like.
[3735.62 --> 3738.00]  One of which is a, having a,
[3738.00 --> 3742.48]  a big LED panel that slowly fades up
[3742.48 --> 3743.62]  starting about a half hour
[3743.62 --> 3745.50]  before my alarm goes off.
[3745.72 --> 3748.40]  And it's able to then also adjust color temp
[3748.40 --> 3750.84]  during the day so that, you know,
[3750.88 --> 3751.92]  in the morning it's,
[3751.92 --> 3753.72]  it's a much more bluish light
[3753.72 --> 3755.60]  and then it's more yellow at night.
[3756.24 --> 3757.06]  That's handy.
[3757.28 --> 3759.96]  Being able to turn various
[3759.96 --> 3762.12]  small localized heaters on
[3762.12 --> 3764.50]  so that we don't have to heat
[3764.50 --> 3767.02]  the entire house to 22 or 23 degrees,
[3767.12 --> 3769.34]  we can just augment, you know,
[3769.34 --> 3772.38]  in, in, in my office or in the bedroom.
[3773.52 --> 3775.56]  These are some nice, some nice features.
[3775.94 --> 3777.58]  I also really like the ability
[3777.58 --> 3780.24]  to keep track of things like power usage
[3780.24 --> 3781.80]  so that we can see how much,
[3782.24 --> 3784.20]  how much are we using across the entire house?
[3784.76 --> 3787.38]  And, you know, can we change behaviors
[3787.38 --> 3790.52]  to try to reduce our, our power consumption?
[3791.30 --> 3791.68]  Interesting. Yeah.
[3791.74 --> 3792.98]  Being able to observe it.
[3792.98 --> 3795.72]  And, you know, much like a magic lantern,
[3796.04 --> 3798.12]  you know, scratched one itch of mine
[3798.12 --> 3799.80]  that I needed, that I really wanted,
[3799.94 --> 3801.58]  you know, one feature on the camera.
[3802.08 --> 3803.50]  What got me started down this road
[3803.50 --> 3807.06]  is I wanted a, a dimmer dim
[3807.06 --> 3808.56]  for the LED panels.
[3809.42 --> 3811.36]  That the IKEA ones have,
[3811.44 --> 3813.18]  have eight brightness steps
[3813.18 --> 3815.52]  and the dimmest one is still
[3815.52 --> 3817.00]  much, much too bright
[3817.00 --> 3818.64]  for, for any sort of nightlight.
[3818.64 --> 3822.52]  So the first hack was, uh,
[3822.78 --> 3824.92]  be able to swap out the PWM curve
[3824.92 --> 3827.22]  for one that actually goes, uh,
[3827.22 --> 3827.98]  much, much dimmer.
[3828.72 --> 3829.60]  And success on that front?
[3830.54 --> 3831.08]  Yeah. Yeah.
[3831.12 --> 3832.34]  And that, that's a,
[3832.50 --> 3834.54]  that was a very straightforward binary patch
[3834.54 --> 3837.12]  where there's no boot time security
[3837.12 --> 3838.56]  on the, uh, on the code.
[3838.56 --> 3840.86]  So I was able to, you know,
[3840.86 --> 3842.70]  modify the, uh, the firmware in place.
[3843.42 --> 3845.40]  Uh, since then I've reverse engineered
[3845.40 --> 3847.60]  the, uh, the over-the-air firmware update protocol.
[3847.60 --> 3850.46]  So I no longer have to open up the devices
[3850.46 --> 3853.10]  to, to physically, uh, reprogram them.
[3853.30 --> 3855.62]  Now you must have incredible mixed feelings
[3855.62 --> 3856.18]  about that.
[3856.24 --> 3857.28]  Because on the one hand,
[3857.34 --> 3858.98]  it must be a great relief to you
[3858.98 --> 3860.72]  that you're able to so easily interpose
[3860.72 --> 3861.94]  on your own things
[3861.94 --> 3863.26]  and run your own software on them.
[3863.66 --> 3864.32]  On the other hand,
[3864.34 --> 3865.62]  it's gotta be somewhat horrifying
[3865.62 --> 3868.56]  that a, a bad actor could do the same thing.
[3870.22 --> 3873.18]  And this goes back to, uh,
[3873.64 --> 3875.28]  what, uh, what Jess was talking about
[3875.28 --> 3877.12]  with the internet dependence of them.
[3877.50 --> 3879.22]  That most of the threats
[3879.22 --> 3881.50]  that I'm concerned about are, uh, remote.
[3881.92 --> 3884.58]  You know, someone on close enough
[3884.58 --> 3886.56]  to join the, uh, the Zigbee network
[3886.56 --> 3887.48]  and, and do that.
[3887.78 --> 3889.30]  I probably have other problems
[3889.30 --> 3890.20]  to be worried about.
[3890.68 --> 3892.08]  So, uh, you know, I think as long as
[3892.08 --> 3893.84]  we can keep these things off the internet,
[3893.84 --> 3896.66]  uh, I'm reasonably comfortable
[3896.66 --> 3899.52]  having sort of a lack of security posture on them.
[3900.12 --> 3901.54]  And basically relying on
[3901.54 --> 3902.66]  whatever physical security
[3902.66 --> 3903.64]  one has in one's home
[3903.64 --> 3904.70]  or the fact that it's gonna be
[3904.70 --> 3906.20]  just not economically viable
[3906.20 --> 3908.44]  for me to try out 500,000 homes
[3908.44 --> 3910.22]  to find one that's vulnerable.
[3910.22 --> 3912.34]  But if you're internet connected,
[3912.34 --> 3913.64]  it's much easier for someone
[3913.64 --> 3915.16]  to actually do that work.
[3915.88 --> 3917.90]  As we saw with the Mariah
[3917.90 --> 3919.62]  webcam vulnerability
[3919.62 --> 3921.70]  that, you know, spread across the,
[3921.70 --> 3923.82]  I don't remember how many, uh, millions
[3923.82 --> 3925.30]  of, uh, vulnerable webcams.
[3926.44 --> 3930.10]  That's a much, much more significant concern
[3930.10 --> 3933.48]  than, you know, someone war drive
[3933.48 --> 3936.24]  in to find a light bulb to, to hack.
[3937.18 --> 3937.22]  Interesting.
[3937.60 --> 3938.98]  So, so your thrust is like,
[3939.06 --> 3939.78]  hey, let's not even,
[3940.00 --> 3941.88]  let's not spend our time
[3941.88 --> 3943.80]  on, uh, preventing these things
[3943.80 --> 3944.88]  from being tampered with,
[3944.98 --> 3946.34]  but let's take them off the internet.
[3947.28 --> 3948.08]  Right, right.
[3948.08 --> 3951.32]  And they do have, uh, a gate,
[3951.48 --> 3952.60]  Ikea does sell a gateway
[3952.60 --> 3954.26]  that does connect to the internet,
[3954.26 --> 3957.00]  uh, although it's very,
[3957.00 --> 3958.96]  it's very thoughtfully designed
[3958.96 --> 3960.78]  that it connects to
[3960.78 --> 3962.66]  Ikea.ntp.org
[3962.66 --> 3964.84]  to get a, uh, uh, update the time.
[3964.84 --> 3966.84]  And then it fetches a,
[3966.84 --> 3969.84]  a JSON file from Ikea.com
[3969.84 --> 3973.18]  of, uh, all the firmware versions
[3973.18 --> 3974.28]  for the different devices.
[3975.24 --> 3976.84]  It will download those
[3976.84 --> 3978.64]  and then it validates a, uh,
[3978.66 --> 3979.82]  RSA signature on them
[3979.82 --> 3981.46]  before pushing them out
[3981.46 --> 3982.60]  to the devices.
[3983.48 --> 3985.34]  So if you don't give it,
[3985.34 --> 3986.40]  uh, network access,
[3986.58 --> 3988.10]  it still works perfectly well.
[3988.32 --> 3989.88]  You just don't get firmware updates
[3989.88 --> 3990.66]  for your devices.
[3991.24 --> 3991.72]  Interesting.
[3992.46 --> 3993.98]  You know, compared to
[3993.98 --> 3994.96]  a lot of these other ones
[3994.96 --> 3996.26]  that if you're not online,
[3996.44 --> 3997.74]  they just don't work at all.
[3998.38 --> 3998.84]  Yeah.
[3998.86 --> 3999.54]  And I can tell you
[3999.54 --> 4000.50]  when it's the heater
[4000.50 --> 4001.96]  and you're in a garage
[4001.96 --> 4003.68]  and the, uh,
[4003.68 --> 4004.50]  and the, uh,
[4004.50 --> 4005.26]  the internet's out,
[4005.26 --> 4006.00]  it's, uh,
[4006.00 --> 4006.84]  it can be uncomfortable.
[4007.36 --> 4008.46]  It could be a problem.
[4009.14 --> 4009.58]  Yeah.
[4009.82 --> 4010.18]  Yeah.
[4010.28 --> 4011.58]  And yeah,
[4011.58 --> 4012.06]  I think the,
[4012.08 --> 4013.10]  the concerns
[4013.10 --> 4014.08]  with local attackers,
[4014.08 --> 4015.14]  uh, you know,
[4015.14 --> 4016.62]  perhaps if somebody's
[4016.62 --> 4017.40]  wants to, uh,
[4017.40 --> 4018.40]  prank someone,
[4018.66 --> 4019.96]  they could do things.
[4020.08 --> 4020.56]  But again,
[4021.14 --> 4022.16]  these devices are not,
[4022.44 --> 4022.72]  uh,
[4022.72 --> 4023.20]  they're not on,
[4023.32 --> 4023.84]  on the wifi.
[4024.28 --> 4025.80]  They don't have connectivity
[4025.80 --> 4027.64]  to the internet proper.
[4027.96 --> 4029.32]  There's not a whole lot
[4029.32 --> 4030.60]  that capabilities
[4030.60 --> 4031.60]  that they really have.
[4031.60 --> 4033.06]  Interesting.
[4033.48 --> 4034.56]  So just limiting
[4034.56 --> 4035.40]  their surface area
[4035.40 --> 4036.08]  to keep them off
[4036.08 --> 4036.48]  the internet
[4036.48 --> 4037.88]  is probably
[4037.88 --> 4038.42]  the single most
[4038.42 --> 4038.86]  important step,
[4039.00 --> 4039.64]  which a lot of these
[4039.64 --> 4040.34]  device manufacturers
[4040.34 --> 4041.22]  don't necessarily want to do.
[4041.34 --> 4041.78]  They, I mean,
[4041.80 --> 4042.84]  their whole business model
[4042.84 --> 4043.68]  is around getting you
[4043.68 --> 4044.42]  connected, right?
[4045.10 --> 4045.54]  And I,
[4045.54 --> 4046.50]  I don't fully understand
[4046.50 --> 4047.92]  why, you know,
[4047.92 --> 4049.12]  what, what the motivation
[4049.12 --> 4050.14]  is to have all these
[4050.14 --> 4051.48]  things online.
[4051.68 --> 4052.06]  You know,
[4052.06 --> 4052.90]  are they really collecting
[4052.90 --> 4054.10]  that much valuable data
[4054.10 --> 4055.66]  about how often
[4055.66 --> 4056.38]  the lights are on?
[4057.08 --> 4057.36]  Well, that's what
[4057.36 --> 4057.76]  they're telling their
[4057.76 --> 4058.12]  investors.
[4058.12 --> 4058.86]  You know,
[4059.00 --> 4059.34]  you gotta,
[4059.76 --> 4061.10]  you gotta give the,
[4061.30 --> 4062.58]  you're using your AI
[4062.58 --> 4063.86]  on your data
[4063.86 --> 4065.44]  to, uh,
[4065.80 --> 4066.38]  question mark,
[4066.46 --> 4066.90]  question mark,
[4066.98 --> 4067.50]  question mark.
[4067.62 --> 4068.56]  I don't necessarily know
[4068.56 --> 4068.82]  that they're,
[4068.82 --> 4070.02]  they're doing that much
[4070.02 --> 4070.28]  with it,
[4070.34 --> 4071.02]  but they say they are.
[4071.54 --> 4071.64]  Yeah.
[4072.08 --> 4073.38]  And I think the,
[4073.80 --> 4074.24]  there's a,
[4074.26 --> 4075.00]  there's a big push
[4075.00 --> 4076.26]  in, you know,
[4076.26 --> 4076.90]  some of these communities
[4076.90 --> 4078.04]  to sort of regain
[4078.04 --> 4079.04]  digital sovereignty.
[4079.16 --> 4080.76]  And I think it's a
[4080.76 --> 4081.74]  good way to think
[4081.74 --> 4082.24]  about it.
[4082.24 --> 4083.06]  Um, you know,
[4083.06 --> 4084.30]  both for things like
[4084.30 --> 4085.22]  these automation devices
[4085.22 --> 4086.44]  that they should be
[4086.44 --> 4087.80]  contained to networks
[4087.80 --> 4088.88]  that we can control
[4088.88 --> 4090.10]  as well as to things
[4090.10 --> 4090.58]  like, uh,
[4090.58 --> 4091.02]  we were talking about
[4091.02 --> 4092.00]  earlier with servers
[4092.00 --> 4093.32]  that we should be,
[4093.66 --> 4095.10]  uh, we should be
[4095.10 --> 4095.96]  controlling the firmware
[4095.96 --> 4097.32]  that's running on there.
[4097.40 --> 4098.08]  We should control
[4098.08 --> 4099.06]  the root of trust
[4099.06 --> 4100.80]  with our laptops.
[4100.80 --> 4101.28]  We should be able
[4101.28 --> 4102.26]  to change out the firmware,
[4102.26 --> 4103.26]  but we should be able
[4103.26 --> 4104.14]  to do it in a way
[4104.14 --> 4106.38]  that, that we can detect
[4106.38 --> 4107.18]  if someone else
[4107.18 --> 4108.94]  has, has modified them.
[4108.94 --> 4109.58]  You know,
[4109.58 --> 4110.10]  I think the,
[4110.18 --> 4111.44]  the digital sovereignty,
[4111.44 --> 4112.76]  you know,
[4112.76 --> 4114.12]  does span everything
[4114.12 --> 4114.40]  from,
[4114.52 --> 4115.14]  from these smart home
[4115.14 --> 4116.26]  devices all the way
[4116.26 --> 4117.90]  to, to, to our
[4117.90 --> 4118.92]  general purpose computers.
[4119.12 --> 4119.78]  But there are
[4119.78 --> 4120.72]  different trade-offs
[4120.72 --> 4121.70]  that we need to make
[4121.70 --> 4122.30]  along the way.
[4123.26 --> 4124.14]  Yeah, that's interesting.
[4124.26 --> 4124.92]  It's interesting to kind
[4124.92 --> 4125.56]  of think of it as,
[4125.62 --> 4126.44]  as sovereignty.
[4126.72 --> 4127.42]  I, and I think,
[4127.56 --> 4128.56]  and you've got to describe
[4128.56 --> 4129.74]  the Intel boot guard
[4129.74 --> 4130.62]  issue you found,
[4130.70 --> 4131.74]  I think is too hilarious
[4131.74 --> 4132.56]  to not describe.
[4132.56 --> 4132.92]  Oh, it's so good.
[4133.48 --> 4134.50]  Uh, which one?
[4135.26 --> 4137.72]  Well, I guess the one
[4137.72 --> 4138.28]  I'm aware of,
[4138.40 --> 4139.28]  it sounds like there's
[4139.28 --> 4139.84]  more than one,
[4139.90 --> 4140.64]  but the one that you
[4140.64 --> 4141.66]  found where,
[4141.76 --> 4142.96]  when you, um,
[4142.96 --> 4143.88]  I believe you,
[4143.96 --> 4145.88]  you had a bad Dixie
[4145.88 --> 4147.20]  and as a result
[4147.20 --> 4148.38]  you could boot anything.
[4148.98 --> 4149.72]  Am I remembering
[4149.72 --> 4150.10]  that correctly?
[4150.70 --> 4150.94]  Okay.
[4151.00 --> 4151.84]  So that's, um,
[4152.08 --> 4152.92]  that, that one is a
[4152.92 --> 4154.32]  fairly straightforward one.
[4154.92 --> 4155.86]  This is what I'm thinking
[4155.86 --> 4157.38]  of that in that case,
[4157.52 --> 4159.16]  the, the way the
[4159.16 --> 4160.60]  UEFI firmware is organized
[4160.60 --> 4161.70]  in, in these sort of
[4161.70 --> 4162.80]  different firmware volumes,
[4162.80 --> 4164.72]  a lot of vendors will put
[4164.72 --> 4166.10]  all of the PEI,
[4166.18 --> 4167.84]  the pre EFI ones on one
[4167.84 --> 4168.78]  firmware volume,
[4168.84 --> 4169.82]  all the Dixies on another
[4169.82 --> 4170.14]  one.
[4170.14 --> 4171.66]  And then a lot of times
[4171.66 --> 4172.88]  they'll put, uh, sort of
[4172.88 --> 4174.92]  ancillary things like, uh,
[4174.92 --> 4176.94]  boot logos or microcode
[4176.94 --> 4178.70]  updates in additional
[4178.70 --> 4179.22]  volumes.
[4179.48 --> 4180.82]  And a lot of times those
[4180.82 --> 4182.26]  volumes will not be signed.
[4182.36 --> 4183.20]  They will not be covered
[4183.20 --> 4185.62]  by boot guard because, uh,
[4185.62 --> 4187.34]  the OEMs might change
[4187.34 --> 4188.02]  out the logos.
[4188.18 --> 4189.44]  And also they want to be
[4189.44 --> 4190.46]  able to swap out the
[4190.46 --> 4192.54]  microcode without requiring
[4192.54 --> 4193.92]  that the whole firmware
[4193.92 --> 4195.02]  get, get re-signed.
[4195.40 --> 4196.72]  So that way if you, you
[4196.72 --> 4198.00]  know, when the next, um,
[4198.00 --> 4199.08]  side channel attack comes
[4199.08 --> 4200.12]  out, you can, you
[4200.12 --> 4201.08]  can install that
[4201.08 --> 4202.04]  microcode without having
[4202.04 --> 4203.76]  to, uh, get the OEM
[4203.76 --> 4204.30]  involved.
[4204.86 --> 4205.28]  Oh, I was going to say
[4205.28 --> 4205.88]  the next corporate
[4205.88 --> 4206.98]  rebranding changes the
[4206.98 --> 4208.02]  logo, but you're taking a
[4208.02 --> 4209.22]  much more, uh, a much
[4209.22 --> 4210.10]  more elevated path.
[4210.82 --> 4213.02]  Well, both of those, um,
[4213.20 --> 4214.38]  well, it turns out that
[4214.38 --> 4216.14]  the UEFI reference code
[4216.14 --> 4217.88]  would scan every
[4217.88 --> 4219.48]  firmware volume for
[4219.48 --> 4222.06]  executables and, uh,
[4222.06 --> 4223.58]  would at least run the
[4223.58 --> 4225.02]  initialization code out of
[4225.02 --> 4226.68]  them, whether or not that
[4226.68 --> 4227.68]  firmware volume was covered
[4227.68 --> 4228.54]  by the, uh, by the
[4228.54 --> 4229.28]  boot card signatures.
[4230.28 --> 4231.84]  So that particular attack
[4231.84 --> 4233.68]  was quite simple that, you
[4233.68 --> 4235.28]  know, add a new Dixie or a
[4235.28 --> 4236.42]  new PEI module to that
[4236.42 --> 4237.10]  firmware volume.
[4237.50 --> 4238.76]  It would get automatically
[4238.76 --> 4241.14]  detected and, uh, run by the,
[4241.22 --> 4243.18]  um, you know, by the, by the,
[4243.18 --> 4245.84]  by the CPU without ever
[4245.84 --> 4248.24]  getting measured or validated.
[4248.24 --> 4250.82]  That seems very problematic.
[4251.54 --> 4253.24]  So very problematic.
[4253.24 --> 4255.10]  Um, and because it was in the
[4255.10 --> 4256.58]  reference implementation that
[4256.58 --> 4258.80]  affected pretty much every, uh,
[4258.82 --> 4259.22]  OEM.
[4260.06 --> 4260.50]  Wow.
[4260.62 --> 4261.70]  And it shows the challenge of
[4261.70 --> 4262.64]  this, that you've, you know,
[4262.64 --> 4263.68]  you've got this whole mechanism
[4263.68 --> 4266.78]  that's designed to, to, to
[4266.78 --> 4267.80]  measure things that you're
[4267.80 --> 4268.84]  booting so you don't boot the
[4268.84 --> 4269.40]  wrong thing.
[4269.98 --> 4272.62]  And effectively one bug or
[4272.62 --> 4274.10]  issue or nuance, whatever you
[4274.10 --> 4275.14]  want to call this, this kind of
[4275.14 --> 4277.54]  legacy, uh, the capacity to
[4277.54 --> 4279.26]  evaluate these, these things
[4279.26 --> 4280.82]  for, for executable bits or
[4280.82 --> 4282.26]  executing the, the initialization
[4282.26 --> 4284.36]  section resulted for the, in
[4284.36 --> 4285.22]  the whole mechanism being
[4285.22 --> 4285.70]  so compatible.
[4286.58 --> 4288.14]  It turns out that a lot of
[4288.14 --> 4289.96]  these, uh, chains of, of trust
[4289.96 --> 4291.54]  fail kind of brutally in that
[4291.54 --> 4294.14]  way that if you get one, if you
[4294.14 --> 4296.26]  can get one instruction executed
[4296.26 --> 4298.16]  that's not measured, you can
[4298.16 --> 4300.42]  basically use that to, uh, load
[4300.42 --> 4301.84]  arbitrary payloads and, and do
[4301.84 --> 4303.80]  things, which is one of the other
[4303.80 --> 4304.88]  boot guard vulnerabilities.
[4305.14 --> 4307.32]  Uh, that I found along with a
[4307.32 --> 4308.86]  Peter Bosch from a university of
[4308.86 --> 4311.16]  Leiden, which is that when
[4311.16 --> 4313.24]  after boot guard has validated
[4313.24 --> 4315.38]  all of the signatures, it's
[4315.38 --> 4316.42]  supposed to do that entirely
[4316.42 --> 4317.60]  running out of cache.
[4317.86 --> 4319.92]  So that way, uh, it never goes
[4319.92 --> 4321.60]  back to the, to the flash chip,
[4321.60 --> 4325.34]  but there was a, a bug in the
[4325.34 --> 4327.38]  way boot guard switched from
[4327.38 --> 4328.84]  what's called caches Ram mode
[4328.84 --> 4330.74]  into normal DRAM mode.
[4330.74 --> 4333.94]  And when it did that one
[4333.94 --> 4335.98]  instruction, or I think four
[4335.98 --> 4337.90]  instructions would be loaded from
[4337.90 --> 4339.50]  the flash and executed.
[4339.92 --> 4340.80]  Oh boy.
[4341.38 --> 4345.16]  So this is, this was the, uh, my
[4345.16 --> 4347.32]  first, my second FPGA project
[4347.32 --> 4350.54]  watched the flash chip accesses for
[4350.54 --> 4352.58]  that second access, and then would
[4352.58 --> 4354.22]  provide a different instruction.
[4354.22 --> 4357.48]  So this is a time of check, time of
[4357.48 --> 4359.24]  use vulnerability, you know,
[4359.24 --> 4360.76]  essentially a, a hardware race
[4360.76 --> 4363.48]  condition, uh, that, that allowed a
[4363.48 --> 4364.50]  boot guard bypass.
[4365.24 --> 4366.34]  Via an FPGA.
[4366.56 --> 4366.72]  Wow.
[4366.76 --> 4367.38]  That's amazing.
[4367.90 --> 4368.74]  And also terrible.
[4369.14 --> 4372.06]  It's also, I mean, you, and just
[4372.06 --> 4373.56]  think there's a four instruction,
[4373.92 --> 4375.06]  just four instructions.
[4375.26 --> 4377.34]  I mean, it's so few instructions and
[4377.34 --> 4379.20]  yet it doesn't take, it doesn't take
[4379.20 --> 4380.70]  many unmeasured instructions to be
[4380.70 --> 4381.76]  able to circumvent the whole thing.
[4381.76 --> 4383.42]  You know, the first instruction you
[4383.42 --> 4385.32]  send is a jump somewhere else.
[4385.72 --> 4389.58]  And, you know, then you're off to
[4389.58 --> 4391.86]  whatever location of code in the ROM
[4391.86 --> 4393.12]  that you want to run from.
[4393.42 --> 4395.10]  So given the challenge of this, are,
[4395.14 --> 4396.90]  are you optimistic that we can
[4396.90 --> 4400.12]  actually get a, a, a full chain of
[4400.12 --> 4402.52]  trust and, and be able to actually
[4402.52 --> 4405.44]  have, uh, nice things in the server
[4405.44 --> 4405.74]  space?
[4405.82 --> 4407.30]  Can we actually have a, a hardware
[4407.30 --> 4409.48]  trust and get full firmware out of
[4409.48 --> 4409.74]  station?
[4409.74 --> 4414.16]  I think we can get a, I think we
[4414.16 --> 4415.18]  can actually start to get there.
[4415.34 --> 4416.84]  And I think we can start to apply,
[4416.84 --> 4418.76]  uh, some higher level language
[4418.76 --> 4421.58]  techniques to give us measurements
[4421.58 --> 4423.82]  of which code paths we've, we've
[4423.82 --> 4426.54]  gone down and, you know, are
[4426.54 --> 4429.24]  basically do, uh, uh, uh, tainting to
[4429.24 --> 4431.78]  ensure that everything that we, that
[4431.78 --> 4433.50]  we execute has come from a measured
[4433.50 --> 4434.00]  path.
[4434.24 --> 4436.98]  The, uh, the U root project that,
[4436.98 --> 4438.18]  that, uh, Linux boot, uh, depends
[4438.18 --> 4440.46]  on has re-implemented all of the
[4440.46 --> 4441.44]  firmware in go.
[4442.22 --> 4444.28]  And it's really sort of amazing to
[4444.28 --> 4447.42]  think that we can, we can throw such
[4447.42 --> 4449.06]  a high level language at such a low
[4449.06 --> 4449.78]  level problem.
[4450.54 --> 4453.04]  And, you know, go gives a lot of, uh,
[4453.10 --> 4455.60]  neat introspective capabilities that
[4455.60 --> 4457.60]  would be very difficult in, in C.
[4458.28 --> 4458.64]  Yeah.
[4458.68 --> 4459.04]  Interesting.
[4459.16 --> 4460.78]  Well, I've been playing around with,
[4460.78 --> 4463.34]  with Rust on the TNC and the, uh, all
[4463.34 --> 4464.58]  the embedded Rust work has also been
[4464.58 --> 4465.10]  very interesting.
[4465.10 --> 4466.80]  It's, it's fun to see these higher
[4466.80 --> 4468.42]  level languages be able to get into
[4468.42 --> 4469.36]  these small places.
[4470.02 --> 4470.46]  Yeah.
[4470.62 --> 4473.26]  And on, on the RISC-V side, there's a,
[4473.26 --> 4475.24]  um, uh, project called, uh, Orboot.
[4475.80 --> 4476.28]  Yes.
[4476.34 --> 4477.24]  Which is, uh.
[4477.24 --> 4477.76]  We love Orboot.
[4478.44 --> 4478.88]  Yeah.
[4478.98 --> 4480.70]  It's like Corboot, but in Rust.
[4481.32 --> 4483.58]  It's, it is Corboot without the C, I
[4483.58 --> 4484.00]  believe.
[4484.42 --> 4485.38]  Hence, Orboot.
[4486.12 --> 4486.46]  Yes.
[4486.52 --> 4486.78]  There you go.
[4487.28 --> 4489.06]  So many, uh, so many wonderful, uh,
[4489.12 --> 4490.40]  metal-based puns.
[4490.40 --> 4492.84]  But Orboot is great.
[4493.00 --> 4493.92]  We do, we, there was a great
[4493.92 --> 4495.58]  presentation on that at, at OSFC.
[4495.78 --> 4497.02]  Folks can check out online.
[4497.88 --> 4499.90]  So Tram, I assume that the place to
[4499.90 --> 4502.98]  find you online is, is tram.net,
[4503.06 --> 4503.80]  trm.net.
[4504.68 --> 4507.12]  Uh, that's certainly to keep up with a
[4507.12 --> 4509.34]  lot of the projects and, uh, my talk
[4509.34 --> 4509.72]  schedule.
[4509.88 --> 4514.14]  I'm also on, uh, QRS at mastodon.social
[4514.14 --> 4517.28]  or QRS on, on, uh, the bird site.
[4517.98 --> 4518.30]  Nice.
[4518.30 --> 4518.74]  Nice.
[4519.64 --> 4520.62]  Well, that's great.
[4521.20 --> 4523.50]  Trammell, thank you so much for
[4523.50 --> 4524.88]  joining us today on On the Metal.
[4525.38 --> 4527.04]  It's hard to imagine anyone who's
[4527.04 --> 4529.80]  done such more varied work at the
[4529.80 --> 4531.78]  hardware software interface, um, and
[4531.78 --> 4533.34]  then documented it so thoroughly.
[4533.64 --> 4535.94]  So thank you on behalf of all of us
[4535.94 --> 4536.88]  for all of your contributions.
[4537.18 --> 4538.84]  They're, they're mesmerizingly good.
[4539.06 --> 4539.70]  Thank you so much.
[4539.84 --> 4541.30]  It's been wonderful chatting with
[4541.30 --> 4541.54]  you all.
[4541.72 --> 4544.92]  And, uh, uh, I wish you the best of
[4544.92 --> 4546.44]  luck in your garage startup.
[4547.36 --> 4547.76]  Excellent.
[4547.76 --> 4548.38]  Thank you.
[4548.38 --> 4549.40]  We'll provide it the internet stays
[4549.40 --> 4550.50]  on so we can get the heat on.
[4550.62 --> 4550.86]  And the heat.
[4551.50 --> 4551.90]  Excellent.
[4552.90 --> 4553.76]  Thank you, Trammell.
[4553.88 --> 4556.04]  And I thank you for, for joining us
[4556.04 --> 4557.22]  for On the Metal.
[4557.22 --> 4560.20]  You've been listening to On the Metal,
[4560.40 --> 4562.44]  tales from the hardware software interface.
[4562.44 --> 4564.34]  For show notes, to learn more about our
[4564.34 --> 4566.14]  guests, or to sign up for our mailing list,
[4566.56 --> 4568.88]  visit us at onthemetal.fm.
[4569.32 --> 4571.00]  On the Metal is a production of Oxide
[4571.00 --> 4572.90]  Computer Company and is recorded in the
[4572.90 --> 4575.08]  Oxide Garage in Oakland, California.
[4575.72 --> 4577.60]  To learn more about Oxide, visit us at
[4577.60 --> 4578.70]  oxide.computer.
[4579.18 --> 4581.06]  On the Metal is hosted by me, Brian Cantrell,
[4581.18 --> 4582.94]  along with Jess Fussell, and we are
[4582.94 --> 4584.88]  frequently joined by our boss, Steve Tuck.
[4584.88 --> 4587.14]  Our original and awesome theme music is by
[4587.14 --> 4589.02]  JJ Wiesler at Pollen Music Group.
[4589.28 --> 4591.38]  You can learn more about JJ and Pollen at
[4591.38 --> 4593.00]  pollenmusicgroup.com.
[4593.34 --> 4595.70]  We are edited and produced by Chris Hill and
[4595.70 --> 4597.18]  his crew at HumblePod.
[4597.46 --> 4600.00]  From Jess, from Steve, from me, and from all
[4600.00 --> 4602.46]  of us at Oxide Computer Company, thanks for
[4602.46 --> 4603.36]  listening to On the Metal.
[4603.36 --> 4603.42]  On the Metal.
[4630.00 --> 4633.44]  www. Games.org of возможности mar jember Live
[4633.44 --> 4634.62]  Do it bougie there's Schrittottom Do it this way.
[4634.62 --> 4635.00]  Having fun is that?
[4635.00 --> 4636.00]  Both of us at the Alaph College, when we're
[4636.00 --> 4637.68]  using the Alaph College, it's a round of
[4637.68 --> 4638.42]  various programs.
[4638.42 --> 4638.70]  We have literally built and veurects online
[4638.70 --> 4639.98]  range for Career Services.
[4640.12 --> 4641.02]  We are using private ciert as erfahren
[4641.02 --> 4641.94]  lists.
[4641.94 --> 4642.04]  WIW Sweats le知' τα
[4642.04 --> 4642.14]  titles.
[4642.14 --> 4643.04]  We have redesigning said
[4643.04 --> 4643.54]  a multiple rink of roc迎ers and
[4643.54 --> 4644.44]  a 3rd양.
[4644.64 --> 4647.30]  We welcome all the various
[4647.32 --> 4648.46]  tools we allisy looks like and
[4648.46 --> 4649.30]  observing it.
[4649.30 --> 4650.10]  It's been widely known as a
[4650.10 --> 4651.24] irs,entre US.
[4651.50 --> 4652.08]  Things like to ask for
[4652.08 --> 4654.26]  this episode with unites
[4654.26 --> 4655.40]  Quando is covered,
[4655.48 --> 4656.80]  the GLO кат woman's
[4656.80 --> 4657.40]  on January 5th,
[4657.40 --> 4657.48]  which is actually thearter
