[0.00 → 17.18] Welcome to On The Metal, tales from the hardware software interface.
[17.46 → 20.46] I'm Brian Cantwell. With me, as always, is Jess Terrell. Hey, Jess.
[20.82 → 21.30] Hey, Brian.
[21.56 → 23.74] And joining us is our boss, Steve Tuck. Hey, Steve.
[24.10 → 24.38] Present.
[24.84 → 28.64] All right, Jess, you want to introduce who we've got in the virtual garage today?
[28.64 → 35.32] Yeah, so remotely, which is a fun one, we have John Graham Cumming, who wrote The Geek Atlas.
[35.52 → 36.96] I was just looking at that this morning.
[37.54 → 42.90] And The Matebook that I also have, and also works at Cloudflare as a CTO.
[43.36 → 44.86] All right. John, welcome.
[45.78 → 48.96] Thank you very much. It's very nice to be able to talk to you from far away.
[49.54 → 53.78] Yeah, and this is a conversation we've really been looking forward to having for a long time,
[53.78 → 58.48] because when you dial up computer history, which we've been known to do on this podcast,
[58.64 → 66.16] you turned the dial all the way back. Do you want to talk about how you got into Babbage
[66.16 → 68.66] and his work with Lovelace and so on?
[69.58 → 76.60] Yeah, I mean, I think I probably knew about it at university because it was mentioned.
[76.80 → 81.04] It's like, oh, by the way, there was this other thing, and maybe it was a computer, Charles Babbage.
[81.04 → 87.36] And then what really happened was right at the time when I was at university in the UK,
[87.94 → 92.76] the Science Museum in London started building one of Babbage's machines,
[92.86 → 96.50] this thing called the Difference Engine, which is really a very big specialized calculator.
[96.68 → 98.44] It's not a computer, but...
[98.44 → 101.04] And they started actually taking his plans and building it.
[101.18 → 104.82] And I, because of where I lived when I was at college and when my parents were,
[104.82 → 106.32] I used to have to travel through London.
[107.00 → 110.54] And so I would literally go through London and sneak out of the tube,
[110.68 → 113.60] go into the Science Museum, look at this thing being built,
[113.82 → 116.54] and then slowly it would get bigger and bigger and bigger,
[116.66 → 117.78] because they built it in public.
[118.10 → 118.70] Oh, wow.
[118.76 → 119.60] Which is really, really cool.
[119.72 → 120.74] And so I kind of knew about it.
[120.76 → 124.52] And I remember at one point, I had this really strong memory of taking my girlfriend,
[124.68 → 127.22] who was also a mathematician, to see this thing.
[127.22 → 131.84] And then the two of us, okay, the method of difference is let's sit down.
[131.96 → 135.26] And we sat down on this, there's a little patch of grass outside the Science Museum.
[135.38 → 136.76] It's not a very grassy area.
[137.14 → 141.42] Sitting down on this patch of grass on a sunny day in London, that's why I remember it.
[141.52 → 141.88] Right.
[142.04 → 142.76] Very distinctive.
[143.70 → 145.96] And sitting with the two of us with a piece of paper working out, okay,
[145.96 → 146.92] how does this thing work?
[147.00 → 148.40] How does the method of differences work?
[148.94 → 152.06] So that was probably really when I got excited about Babbage.
[152.54 → 156.32] And then subsequently realized that the Difference Engine, as cool as it was,
[156.32 → 158.04] isn't actually programmable.
[158.16 → 159.06] And that was a bit sad.
[160.42 → 163.66] And did you already know at that point that you were interested in computing?
[163.80 → 165.46] I mean, had you grown up in computing at that point?
[165.70 → 166.06] Yeah.
[166.32 → 170.84] So I was doing mathematics and computation, as Oxford called it,
[171.24 → 172.64] because Oxford was very theoretical.
[172.84 → 174.56] It was all about the theory of computation,
[174.68 → 176.48] none of this messing around with real computers.
[177.00 → 180.80] But I had messed around with computers for a long time because,
[181.36 → 183.14] well, if you sort of go backwards, you have to work backwards.
[183.14 → 188.46] I was obviously a child of the 80s 8-bit revolution in the UK.
[188.72 → 193.96] I had a thing called the BBC Micro, which was this really cool computer with 48K of RAM.
[194.26 → 197.42] You know, I feel whenever the BBC Micro is mentioned on the podcast,
[197.52 → 198.60] it's been mentioned a couple of times,
[198.74 → 203.86] I feel that all of our English listeners play God Save the Queen in the background.
[204.12 → 206.68] I feel that there are tears in the eyes.
[206.68 → 208.36] There are two groups, right?
[208.44 → 212.32] So in the UK at that time, there was the Sinclair group, right?
[212.40 → 217.64] The ZX81, the ZX Spectrum, and then there was the BBC Micro people.
[217.86 → 219.70] And so, you know, we were sort of two camps.
[220.26 → 222.20] And the Sinclair machines were slightly cheaper.
[223.06 → 224.72] Okay, I've got so many follow-up questions.
[224.88 → 226.08] Is this a class divide?
[226.24 → 227.34] Is it geographical?
[227.64 → 229.40] What divides these two clans?
[229.40 → 232.52] I mean, there was definitely a price difference.
[232.94 → 235.16] The Sinclair machines were much, much cheaper.
[235.88 → 237.94] So I think they were much, much more widespread,
[238.40 → 240.56] whereas the BBC machines were in schools.
[240.74 → 242.68] So people got, you know, at them at school.
[242.80 → 246.74] And I ended up with a BBC machine because my parents, in their wisdom,
[246.92 → 250.48] had said, well, well, you know, they had two boys,
[250.60 → 254.14] and they're like, we'll let these two boys do the things they seem really interested in.
[254.16 → 256.66] And my brother had had years and years of piano lessons
[256.66 → 257.96] and played the piano really well.
[257.96 → 260.04] And I said, I want to have a computer.
[260.18 → 263.30] And they said, well, we probably spent that much money on piano lessons,
[263.30 → 267.74] so we'll buy you this machine, which I still have, which I treasure.
[267.96 → 268.32] Wow.
[268.78 → 269.32] That's cool.
[269.62 → 269.94] Wow.
[270.76 → 272.80] And so it's like, you know, it was a big, big deal.
[273.00 → 275.06] And it was very funny, actually.
[275.16 → 278.98] I switched it on a few years ago, and immediately the power supply blew up.
[279.12 → 280.14] So I had to replace the power supply.
[280.86 → 285.60] And I looked at the back of it, and it has the wattage of the machine,
[285.60 → 288.16] which was about the wattage of a light bulb.
[288.82 → 290.94] And I remember thinking...
[290.94 → 291.24] Really?
[291.24 → 295.90] I knew that my parents didn't have loads of money to burn,
[295.96 → 297.78] and they'd spent a lot of money on this machine.
[298.24 → 300.06] And I had this incredible feeling like, oh, my God,
[300.10 → 303.96] I can't run up their electricity bill with this machine.
[303.96 → 308.38] So I used to switch it on and then go and switch a light off somewhere in the house
[308.38 → 310.56] to be like net-zero.
[311.20 → 314.52] I actually don't think my parents had that little money,
[314.70 → 316.26] but it was more like I had this thing.
[316.26 → 322.48] If the draw is like 60 watts, this is like not even observable on the power bill, I assume.
[322.74 → 325.74] I guess, but I felt as a, you know, I was a child, right?
[325.84 → 327.40] I was just saying, I've got to do my bit.
[327.68 → 329.06] What a coach, you're just a child.
[330.86 → 331.94] Meanwhile, like my children...
[331.94 → 332.58] I'll take one of those.
[332.60 → 333.58] I'll take one of those too.
[333.70 → 337.22] I can't get my kids to be like, could you just get off the mobile network
[337.22 → 340.30] and onto the Wi-Fi so you don't bankrupt the household watching YouTube?
[341.26 → 342.56] It was a different time.
[342.70 → 343.68] It was a different time.
[343.68 → 347.04] Children were so mindful of the power bill.
[347.74 → 349.68] But actually, to continue answering your question,
[349.76 → 351.54] if you go really right back in time,
[351.64 → 353.48] at some point when I was about, I think, seven,
[354.22 → 356.40] I was very bright, and my parents were like,
[356.42 → 358.00] what the hell do we do with this bright kid?
[358.58 → 361.84] And they found, and of course it's pre-internet, right?
[361.90 → 362.84] This is like in the 70s.
[363.20 → 365.82] They found this association, which was, you know,
[365.86 → 368.54] for parents, for desperate parents of intelligent children.
[370.48 → 372.20] And they're like, what do we do with them?
[372.20 → 375.42] And they did this thing at Cambridge University in the summer
[375.42 → 377.86] where you could basically take your kids and dump them off
[377.86 → 380.32] and, you know, let your kids run wild.
[380.46 → 381.94] And so I went to that a couple of times,
[382.06 → 385.44] and I actually hated it because some of the kids were so snotty.
[385.84 → 389.26] But there was one person I went up to,
[389.52 → 391.92] and obviously this person was in either the mathematics
[391.92 → 393.90] or computer science department at Cambridge.
[394.38 → 396.74] And I said, oh, explain to me how a computer works.
[396.76 → 397.32] I want to know.
[397.38 → 398.66] Imagine I'm like seven years old.
[398.66 → 403.26] And what I remember of that is the person getting out a pad of paper
[403.26 → 406.56] and starting to draw this strip on it and little boxes on it
[406.56 → 408.46] and basically described a Turing machine.
[409.14 → 414.44] And I have at home my own little Turing things I've tried to do
[414.44 → 418.16] in strips of paper and come up with this computer thing.
[418.58 → 421.96] So I think I was infected with computer stuff pretty early on.
[421.96 → 426.36] And my mother would say, even as a baby, I was fascinated by things like,
[426.56 → 427.60] how does a clock work?
[427.66 → 428.96] I would stare at clocks.
[429.38 → 430.38] Like, how does that work?
[430.56 → 432.64] So, I don't know, something happens.
[432.92 → 434.08] Probably in the womb, maybe.
[435.16 → 439.00] So where is the like, the eight-year-old that explained the Turing machine?
[439.14 → 440.66] Where did he end up?
[441.04 → 441.58] Oh, no, no, no.
[441.62 → 442.36] This was a professor.
[442.58 → 443.00] Oh, a professor.
[443.18 → 443.74] Oh, excuse me.
[443.80 → 444.08] I'm sorry.
[444.20 → 444.82] It was an adult.
[444.98 → 449.34] I mean, whether he was, like, you know, 21 or 40, I have no idea.
[449.34 → 452.38] All right, as a child, somebody sat and explained this to me.
[452.42 → 453.86] I was like, whoa, this is amazing.
[454.36 → 456.58] And then, of course, later on, I go and actually go to do computer science.
[456.68 → 457.36] I was like, wait a minute.
[457.50 → 458.32] That's a Turing machine.
[458.54 → 462.24] You know, this guy Turing, and now I hear about all this stuff for real
[462.24 → 463.08] and some of the theories.
[463.40 → 465.94] So, you know, I was into computers from an early age.
[466.10 → 467.08] I was kind of nerdy.
[467.52 → 470.32] And you were obviously writing your own programs on the BBC Micro?
[471.14 → 472.34] Yes, yes, obviously.
[472.56 → 477.26] So I think I started out just playing with the machine, trying to understand it.
[477.26 → 480.16] And then I bought this book that was called The Advanced User's Guide,
[480.28 → 483.96] which was, it had a lot of stuff about how the operating system,
[484.40 → 488.04] the BIOS for this thing worked, and a lot of the gutsy.
[488.10 → 489.32] And I was very interested in that.
[489.40 → 491.58] So I really learned assembly language
[491.58 → 494.10] and then started doing assembly language stuff on the machine.
[494.64 → 496.74] And at the same time, I was programming another 8-bit machine,
[496.90 → 499.80] which was made by Sharp and called the MZ80K,
[500.44 → 502.62] and then some other Z80-based machines.
[503.20 → 506.70] So the MZ, to give you the 80K.
[507.26 → 507.70] Interesting.
[508.20 → 512.74] It's a bit like a Commodore PET as an integrated CRT and a tape player.
[513.60 → 515.94] And unusually, it had a keyboard where you could actually type
[515.94 → 518.08] every character that was in the character set.
[518.54 → 522.72] It was really weird because it had a basically, it didn't have ASCII.
[522.82 → 525.76] It had its own thing with all sorts of crazy symbols and stuff.
[526.20 → 527.60] And you could type everything.
[527.72 → 531.22] So anyway, I was really into assembly language programming
[531.22 → 536.06] and then basically to make my programs faster or to access bits of the operating system
[536.06 → 538.82] and build various things.
[539.32 → 543.22] Me with another boy at school, at high school, we wrote programs.
[543.88 → 547.20] So we wrote a statistical analysis package.
[547.20 → 549.04] We wrote a thing for time tabling.
[550.04 → 555.16] And then basically around this time there, we had an 800 kilobit per second, I think,
[555.24 → 557.28] local area network at school.
[557.56 → 562.68] And we disassembled the operating system and figured out how to make it work.
[563.72 → 568.66] And the funny thing was we disassembled how the operating system worked
[568.66 → 569.96] so we could get access to the network.
[569.96 → 574.06] And then we implemented our own packet send and receive routines,
[574.18 → 578.54] implemented our own stateful protocol on top of it so we could reliably send stuff,
[579.38 → 582.06] built a network management package, all of this in assembly language.
[582.22 → 585.80] And all of this very early for networking, for local area networking, right?
[585.82 → 586.48] Yeah, yeah, exactly.
[586.60 → 591.16] There was this company in the UK called Research Machines that sold computers to schools
[591.16 → 592.90] when they were first going on.
[593.14 → 595.84] And the school I was at, the high school I was at,
[595.84 → 597.44] the upper school in the UK,
[597.44 → 602.58] the head teacher died very suddenly of a brain hemorrhage.
[602.70 → 606.12] A lot of money was raised, and the money was spent on this new thing,
[606.20 → 607.96] which was a computer room.
[608.04 → 608.42] Ooh, cool.
[608.56 → 612.46] And in the computer room, they had a network of the Z80-based machines.
[613.36 → 617.18] And myself and another boy, we hacked them, basically.
[617.36 → 618.76] What was the substrate?
[618.92 → 620.78] Because this was going to be too early for Ethernet, right?
[620.92 → 623.64] Well, it was this thing called Zed net, which was their own.
[623.64 → 623.84] Zed net.
[624.40 → 624.80] Yeah.
[624.80 → 629.86] I mean, they made their own network stuff, really.
[630.12 → 633.84] So the central machine, so the machines were running CPM.
[634.68 → 635.02] Right.
[635.10 → 638.08] And then they were, and then they had the central machine that was running NPM,
[638.52 → 640.18] which had eight-inch disks.
[640.82 → 642.26] And then they had this networking thing.
[642.36 → 644.44] I think it was called, what was it called?
[644.48 → 647.80] It had a funny name, but it was 10-base-2, basically coax.
[647.80 → 650.64] It was 10-base-2, okay.
[651.24 → 651.54] Okay.
[651.62 → 655.48] So it was coax, chain, that's what they called it, called it chain.
[655.64 → 657.04] 800 kilobits per second.
[657.76 → 660.16] The MAC address was an 8-bit address.
[660.46 → 660.72] Okay.
[660.76 → 662.34] On a dip switch in the machine.
[663.50 → 664.78] Interesting experiment.
[664.78 → 667.88] I mean, it was a whole thing, but it worked.
[668.26 → 668.62] Wow.
[669.30 → 673.52] The best thing is that myself and Peter, who was the other boy who really got into this
[673.52 → 680.24] kind of stuff, we used to sit physically closest to the file server machine as you
[680.24 → 681.12] followed the network.
[681.12 → 688.42] Because it was coaxed, you could actually remove the connector at the end, terminate it with
[688.42 → 693.08] a BNC terminator, turning the network into a network with the file server and two machines,
[693.32 → 696.56] and then up the performance, because you just cut off the rest of the network.
[697.48 → 699.26] You just closed the door to the rest of the network.
[699.86 → 701.02] Wow, things get a lot faster.
[701.36 → 701.84] That's great.
[701.92 → 705.00] So you did a file transfer, and the other kids in the class were getting on your nerves,
[705.04 → 708.68] you just pop the network off, terminate it, do your file transfer, and put it back again.
[708.68 → 712.02] And you can hear the other kids complaining, why is the computer working?
[712.34 → 713.16] Well, I don't know.
[713.36 → 715.44] Maybe it's this BNC terminator we put on the end.
[717.50 → 718.14] That's great.
[718.44 → 723.30] Again, that is very, I feel, early for networking, especially in a school.
[723.68 → 725.00] So what year is it at this point?
[725.14 → 726.16] It was 1984.
[727.10 → 729.78] That is very early to be networking in a school.
[730.44 → 733.38] I mean, it was fascinating, because we got access to this thing.
[733.44 → 738.64] And then the really nice thing is that I wrote to the company and basically said,
[738.68 → 740.74] by the way, we've reverse engineered the entire operating system.
[740.82 → 742.16] We're doing all this stuff.
[743.58 → 745.18] Will you give us documentation?
[745.96 → 748.38] Because we're like, we'd like to actually have the real documentation.
[749.08 → 753.38] And somebody from the organization wrote back to us and said, essentially,
[753.50 → 755.16] and I actually published a letter on my blog,
[755.62 → 757.90] but they essentially said, don't tell anybody,
[758.26 → 760.50] but here's all the documentation for this thing.
[761.10 → 764.38] And did you reveal that you were 14 or whatever you were?
[764.46 → 765.90] Oh, yeah, yeah, yeah, yeah, yeah, yeah.
[765.92 → 768.56] They knew that this was a bunch of kids that had to be.
[768.56 → 769.12] Yeah, yeah.
[769.12 → 771.42] It was really, really, really encouraging, actually,
[771.42 → 774.54] because we were just hacking this stuff on our own.
[774.72 → 778.24] We didn't really have, we didn't know what we were doing.
[778.34 → 780.08] We were just reverse engineering everything.
[780.08 → 786.34] And when we were, like, we did things like we wrote a paint program,
[786.70 → 790.22] and we were sort of sitting there going, oh, how do we do, like,
[790.60 → 792.64] fill an area with a colour?
[793.40 → 796.16] And, you know, writing flood fill and all this kind of stuff.
[796.56 → 798.00] And this is for these machines?
[798.14 → 798.90] Yeah, for these machines.
[799.00 → 801.12] For this research machine, 480Z, it was cool.
[801.30 → 802.70] So I actually have the letter here.
[802.78 → 804.36] It's like, you know, thanks for the letter.
[804.48 → 806.12] Don't tell anybody, but here's the documentation.
[806.12 → 810.02] I'm just amazed that you're writing that it had the graphics horsepower
[810.02 → 812.84] to do a paint program in 1984.
[813.26 → 814.18] Yeah, it did.
[814.38 → 817.12] I mean, it was a very simple, simple graphics program.
[817.24 → 817.54] I'm trying to think.
[817.62 → 822.00] I think it was at the I think if you, in black and white mode,
[822.00 → 826.36] it was, like, 640 by 192, I think.
[826.54 → 830.10] And I think in, like, the colour mode, it was, like, 320.
[830.52 → 832.98] I mean, I think it was 16K of video memory.
[833.14 → 835.86] Still, though, I mean, you think of, like, this is before the Mac.
[836.44 → 837.62] It's about the time, right?
[837.70 → 838.24] Right, yeah.
[839.04 → 840.90] I mean, it's, that must have felt.
[841.38 → 842.94] That's very impressive to be.
[843.34 → 844.58] It must have felt like you were really.
[845.32 → 847.42] Did you feel like you were on the cutting edge of computing?
[847.56 → 849.92] Because you, certainly from a personal computing perspective,
[849.92 → 852.24] you more or less were in 1984.
[852.98 → 854.68] No, I don't think we had any perspective.
[854.88 → 856.52] I think we just had these machines, right?
[856.56 → 857.70] So I had the Sharp machine.
[858.04 → 859.86] I had the BBC Micro at home.
[860.28 → 863.92] And I had these other, these networked machines at school.
[863.92 → 866.28] And I just remember, more than anything,
[866.46 → 870.04] feeling like we could do whatever we wanted with these machines.
[870.04 → 873.92] Because we, you know, we knew every memory location, what it did.
[874.20 → 876.64] Like, you know, the memory mapped I.O.
[877.28 → 879.84] We completely disassembled the operating system.
[880.44 → 883.22] I think we, I think Peter wrote the disassembler as well.
[883.26 → 884.40] So a lot of stuff we wrote, right?
[884.42 → 887.18] Because we were like, oh, you know, it's getting boring
[887.18 → 889.48] just looking at the Z80 opcode.
[889.48 → 890.78] So let's write a disassembler.
[890.94 → 894.46] And then we were bootstrapping from whatever we had.
[894.68 → 895.68] And it was, it was fascinating.
[895.84 → 898.02] I mean, I still have a lot of the code.
[898.58 → 902.10] And we wrote this network management package for this network,
[902.24 → 903.98] entirely in assembler.
[904.66 → 907.66] So you could like to send, send a message to machines.
[907.66 → 910.80] So we wrote a chat program, all this kind of stuff.
[911.18 → 913.68] I mean, I feel like that was kind of pro-grade.
[913.80 → 915.42] It was pro-grade work at the time.
[915.42 → 918.42] I mean, that's what, that's what, I mean, effectively there were a bunch of companies
[918.42 → 921.38] that were endeavouring to do that same thing at that same time.
[921.56 → 922.78] I think, I think you're right.
[922.82 → 926.14] I think it's about the time when stuff was really taking off.
[926.22 → 929.06] And, you know, we probably, you know, I was a teenager.
[929.14 → 930.82] I probably could have gone and got a job somewhere else.
[930.96 → 931.52] But yeah, right.
[931.52 → 931.84] Exactly.
[931.92 → 933.92] You could have like dropped out of school entirely.
[934.32 → 937.80] Was it tempting at all to be like, I know everything there is to know about computing.
[937.80 → 942.12] So I'm going to set my, because I'm actually impressed that you studied computing
[942.12 → 944.94] or computation at university.
[945.62 → 949.42] Well, so here's a fascinating thing, which is that I was doing this, Peter was doing
[949.42 → 949.56] it.
[949.60 → 953.26] And that was really the two of us in the whole school who were really deeply into it.
[953.54 → 961.72] And I think that outside of that little world, it was not obvious in 1984, 1985, that this
[961.72 → 965.20] computing thing was a good career, particularly not in the UK.
[965.38 → 965.58] Yeah.
[965.64 → 966.00] Interesting.
[966.00 → 970.06] It was kind of a hobby thing, and you were messing around and wasting your time and you
[970.06 → 971.78] should go and get a proper job afterwards.
[971.78 → 972.10] Yep.
[972.28 → 979.04] And I actually really, really seriously considered being a lawyer because I thought maybe this
[979.04 → 980.58] computer, you know, what is this?
[980.62 → 982.56] This is, I'm going to, I'm going to mess around with this.
[982.62 → 983.66] I don't know what my job is going to be.
[983.68 → 988.68] And in particular, the sorts of jobs you're going to get are like technicians.
[989.04 → 989.28] Right.
[989.34 → 991.08] And it was really looked down on as well.
[991.14 → 995.28] Like there was no distinction between software engineer, which the term didn't even seem to
[995.28 → 996.74] exist, at least from my perspective.
[997.54 → 1001.08] And, you know, someone who installs a phone in your home.
[1001.08 → 1003.30] You know, that's a very important point.
[1003.30 → 1007.54] And you do actually forget that because I was in, I grew up slightly later, but in the
[1007.54 → 1007.94] eighties.
[1008.16 → 1008.56] Yeah.
[1008.92 → 1014.24] And actually my father who'd written software when he was at university didn't for a moment
[1014.24 → 1016.10] contemplate doing it for a career.
[1016.22 → 1020.92] He would become a physician because it was viewed so pejoratively at some level.
[1020.92 → 1023.32] I mean, it was viewed as something that you were like messing around with and having,
[1023.38 → 1027.90] having fun with, but not something that, you know, I definitely remember my mother vividly
[1027.90 → 1029.94] telling me you can't play on the computer forever, you know?
[1030.48 → 1030.76] Yeah.
[1030.90 → 1031.38] Yeah, yeah, yeah.
[1031.46 → 1031.86] Absolutely.
[1032.04 → 1034.88] I mean, I think my parents will, you know, I was obsessed with the thing.
[1034.94 → 1040.34] I, one summer during the summer, I stayed inside the house basically the entire summer
[1040.34 → 1041.70] in front of a machine.
[1041.70 → 1044.50] This was in front of the sharp machine, writing a bunch of stuff.
[1044.50 → 1050.72] And I wore through the bottom of the trousers I was wearing just from shifting in the seat.
[1053.04 → 1055.64] So it was a little bit obsessive.
[1056.04 → 1058.86] At this point, are your parents thinking, we really need to get John a piano?
[1059.34 → 1062.30] Are they, are they thinking that we have overshot the mark?
[1063.36 → 1064.86] No, I don't think so, actually.
[1064.98 → 1069.30] I think that they, they were worried about me not going outside and socializing.
[1069.56 → 1071.50] They were worried about the computer.
[1071.50 → 1076.42] I think it was just, you know, why is he spending so much time inside?
[1076.66 → 1077.44] What is he doing?
[1077.70 → 1081.22] On the other hand, you know, I seem to be enjoying it, and I wasn't causing any trouble.
[1081.98 → 1083.72] And you were very mindful of the power bill.
[1083.84 → 1089.38] I mean, I just can't imagine such a considerate child.
[1090.38 → 1096.24] And so then you, you head off to, uh, to university, and it's not too much longer thereafter
[1096.24 → 1101.32] that you're, you're on the, the, the sunny lawn in London trying to figure out the difference
[1101.32 → 1101.56] engine.
[1102.52 → 1104.88] Well, I took a year out actually, because I had bumped up.
[1105.00 → 1106.12] I jumped a year at school.
[1106.12 → 1108.06] So I felt like I was a bit young to go to college.
[1108.06 → 1112.80] So I took a year out and I, um, went and did a bunch of electronic stuff.
[1112.88 → 1115.92] I went to a local technical college and just did electronics.
[1115.92 → 1120.08] So I was kind of interested in electronics to kind of learn about how the how things
[1120.08 → 1120.58] really work.
[1120.66 → 1124.50] But yes, then I get, then I got to Oxford, and I'm going back and forth to where my parents
[1124.50 → 1124.88] lived.
[1125.10 → 1127.68] And yes, Babbage, Babbage comes along.
[1127.80 → 1132.76] Although I will tell you one funny thing, which is that years after all of this, I, within
[1132.76 → 1135.92] the last few years, I read a school report of Alan Turing.
[1135.92 → 1140.96] And in it, the schoolmaster is saying, you know, you really ought to do better at all
[1140.96 → 1146.02] these other subjects other than just, you know, science and mathematics, because if you
[1146.02 → 1148.82] don't, you will grow up to be a mere technician.
[1149.36 → 1150.20] Oh, Geez.
[1150.32 → 1150.52] Yeah.
[1151.28 → 1152.22] Which happened really.
[1152.32 → 1154.84] I mean, he didn't do much really, I'm sure he was just a technician.
[1155.24 → 1156.52] He was really just a technician.
[1156.88 → 1157.06] Yeah.
[1157.32 → 1157.56] Yeah.
[1157.76 → 1157.94] Yeah.
[1158.52 → 1159.38] And it is interesting.
[1159.38 → 1164.44] And, you know, I, I've got mixed feelings about the fact that now there are, you know,
[1164.44 → 1170.10] most college campuses in the U S the introductory computer science course is the most popular
[1170.10 → 1170.78] course on campus.
[1170.78 → 1174.00] Having surpassed the introductory bio classes, introductory.
[1174.16 → 1174.62] It's amazing.
[1174.76 → 1175.02] Really?
[1175.22 → 1175.38] Yeah.
[1175.44 → 1177.16] Jess has given me a crazy look.
[1177.28 → 1178.10] No, that's true.
[1178.12 → 1178.94] Where did you read this?
[1179.10 → 1179.66] I don't know that.
[1179.90 → 1183.20] This is, I mean, if you talk to any university, yeah, yeah, no, that's the that's crazy.
[1183.24 → 1185.02] It was not popular when even I went to school.
[1185.06 → 1189.06] No, this is, well, it is, it's an economic thing as much as it is anything else.
[1189.10 → 1189.42] That's right.
[1189.60 → 1189.94] That's right.
[1189.98 → 1190.88] There's money in it, right?
[1190.96 → 1191.56] There's money in it.
[1191.56 → 1192.08] Oh, that's true.
[1192.08 → 1193.42] Like nursing was huge.
[1193.74 → 1194.10] Right.
[1194.10 → 1194.44] My year.
[1194.70 → 1198.58] And now, I mean, you can imagine if you're, if you're a parent of an 18-year-old, who's
[1198.58 → 1202.98] concerned about the economic viability of that 18-year-old, you're probably telling
[1202.98 → 1204.22] him to take the computer science class.
[1204.38 → 1205.68] That kind of ruins it a little bit to be honest.
[1205.70 → 1206.78] Well, that's the question, right?
[1206.88 → 1214.02] I mean, it's like there was something pure when nobody was pursuing it for economic reasons.
[1214.36 → 1216.24] There was like 12 people in my class.
[1216.60 → 1216.84] Right.
[1217.08 → 1217.34] 12 people.
[1217.52 → 1218.36] It was so small.
[1218.50 → 1219.62] And then I was the favourite.
[1219.62 → 1220.26] I mean.
[1222.76 → 1223.16] Sorry.
[1223.16 → 1224.12] Did anyone ask the person?
[1224.12 → 1224.66] I didn't know.
[1224.90 → 1225.64] Just to make sure.
[1225.64 → 1226.32] I said to.
[1226.54 → 1226.84] Sorry.
[1226.84 → 1233.48] You know, I have in doing this, I've heard so many stories of Jess and her adventures
[1233.48 → 1234.00] in math class.
[1234.12 → 1238.26] So Jesse should know is the person who sets up like all the trapper keepers around
[1238.26 → 1242.48] her math exam to make sure that you cannot see anything that she's working on.
[1242.48 → 1243.34] Well, I want to be the favourite.
[1243.58 → 1244.96] And I want to get the 100%.
[1244.96 → 1246.64] Like, I don't want people to cheat off of me.
[1247.04 → 1247.22] I know.
[1247.28 → 1248.22] I feel like it's reasonable.
[1248.22 → 1250.68] I feel like I was in your math classes with you.
[1250.80 → 1253.34] It's just your descriptions of math class are so vivid.
[1253.86 → 1259.58] But it does feel like there is something when you are drawn to it, kind of despite societal
[1259.58 → 1260.96] pressures to do something else.
[1261.76 → 1265.58] The people that you end up that end up being there are the ones who are really deeply,
[1265.70 → 1266.50] deeply drawn to it.
[1266.76 → 1267.00] Yeah.
[1267.00 → 1272.56] I mean, I think the thing I really felt was as much as Peter and I were working on stuff
[1272.56 → 1274.96] together, there was an intense amount of competition.
[1274.96 → 1280.60] And I know I was incredibly annoyed when he did something clever because I really wanted
[1280.60 → 1283.70] just to master the whole machine and prove how brilliant I was.
[1283.94 → 1286.04] So dare we ask, where is Peter today?
[1286.04 → 1286.70] I was going to ask.
[1287.02 → 1291.66] You know, I have seen him, and he does something that's designing something for the British
[1291.66 → 1294.12] government and can't tell you about it.
[1294.12 → 1297.34] So I don't know what it is, exactly, but it's some electronic things.
[1298.00 → 1300.70] Is this an elaborate multi-decade plan to get even with you?
[1300.92 → 1304.24] Maybe he's, you know, he's like, I'm going to show it to Graham Cumming.
[1305.88 → 1307.96] A satellite is going to suddenly shoot me.
[1308.86 → 1309.74] I don't know.
[1309.90 → 1310.28] I don't know.
[1310.32 → 1311.54] It's been quite a few years.
[1311.74 → 1312.52] He went to Cambridge.
[1312.60 → 1313.30] I went to Oxford.
[1314.00 → 1315.66] And he's in a different direction.
[1316.06 → 1320.48] So then you're looking at the difference engine, which I, so I think both the difference
[1320.48 → 1324.10] engine and the analytical engine are so fascinating because they,
[1324.12 → 1326.36] they are mechanical, not electronic.
[1326.74 → 1328.96] And a couple of questions for you on that.
[1329.04 → 1332.52] And for those folks who haven't seen it, well, we'll obviously link to it in the show notes.
[1332.56 → 1335.94] I mean, you gave a great Ted talk on the reconstruction of this.
[1336.04 → 1337.96] I guess before it was really reconstructed.
[1338.00 → 1339.80] I mean, as you were showing the simulation.
[1340.42 → 1345.80] So in particular, you had some programs that Babbage had written for it.
[1346.10 → 1349.16] And I guess I didn't realize that he'd actually written programs for the thing that he had not
[1349.16 → 1349.48] built.
[1349.48 → 1349.92] Yeah.
[1350.64 → 1355.20] I mean, I think, so if you look at all the stuff that Babbage left behind about what's
[1355.20 → 1359.78] called the analytical engine, which is his, his computer, which is the thing that he worked
[1359.78 → 1360.86] on with Lovelace.
[1361.30 → 1366.10] There was simultaneously designing the machine and thinking about what the programming language
[1366.10 → 1368.18] would be, what the instruction set would be.
[1368.24 → 1373.84] Basically, basically came to this idea that the difference engine was limited in what it
[1373.84 → 1378.12] could do because it was fixed in terms of its essentially its program in a way.
[1378.12 → 1383.44] And also it couldn't really do much with its output, and it couldn't sort of fundamentally
[1383.44 → 1385.68] take its output and feed it back in and do something.
[1386.44 → 1389.82] And so he realized that there were functions he couldn't compute.
[1389.96 → 1393.70] And the thing is about Babbage is he was completely obsessed with mathematics.
[1393.82 → 1396.82] This is all about computing mathematical functions.
[1397.40 → 1401.14] And so he realized he could make this more flexible machine, programmable with punch cards.
[1401.34 → 1402.80] You know, why punch cards?
[1402.84 → 1405.44] Because they were widely used for looms, for weaving.
[1405.44 → 1407.52] That was a technology that was available.
[1408.22 → 1412.66] And he's kind of making the instruction set and thinking about what the machine will look
[1412.66 → 1415.58] like and how to optimize the machine at the same time.
[1415.62 → 1419.44] So there are in the science museum stacks of cards that were thrown together with programs
[1419.44 → 1419.78] on them.
[1419.82 → 1420.90] Fairly, very simple.
[1421.42 → 1425.04] You know, this is the sequence of things you would do to calculate some function.
[1425.42 → 1429.32] The problem was, first, I think Childhood Abuse was like many nerds, a little bit
[1429.32 → 1430.74] difficult to deal with.
[1431.60 → 1435.28] He also realized, like, it's the classic thing, right?
[1435.32 → 1437.76] He makes the difference, or he designs the difference engine.
[1437.86 → 1440.40] Then he just abandons it because it's like, I can make an even better one.
[1440.76 → 1441.76] I can make an even better one.
[1441.88 → 1446.78] So eventually the British government said to him, you know, we've spent as much as a
[1446.78 → 1449.34] battleship on this thing, and you haven't actually built anything.
[1450.02 → 1451.04] And he's like, yeah, yeah.
[1451.04 → 1454.50] But the next version is going to be the coolest because it's going to have, you know, there's
[1454.50 → 1455.34] such and such features.
[1455.34 → 1456.84] So eventually his funding got cut off.
[1457.48 → 1461.70] He was constantly optimizing the machine, adding instructions, making it faster.
[1462.66 → 1467.76] And he realized things like, well, I could essentially have instruction pipelining and
[1467.76 → 1468.58] data pipelining.
[1468.80 → 1474.42] Like, well, while the CPU bit is doing instruction, I could be moving the next data from the store,
[1474.54 → 1474.98] as it's called.
[1475.60 → 1476.66] He's just a classic nerd.
[1476.70 → 1480.90] And then in his notes, he's like, maybe I need a hundred memory locations.
[1481.44 → 1483.36] Maybe I need a thousand memory locations.
[1483.36 → 1484.90] You remember this thing's physical, right?
[1484.90 → 1487.26] So it's ending up the size of a locomotive.
[1487.46 → 1489.84] Well, it's physical, and it's also inbuilt.
[1489.98 → 1493.76] This is the thing that is so amazing to me is that he is doing all of these optimizations
[1493.76 → 1496.16] on a system that is not built at all.
[1496.30 → 1501.22] I mean, I think that this is, I think that the thing that sticks out the most to me about
[1501.22 → 1507.04] Babbage is like, how are you, most of us need to actually like mess around with something
[1507.04 → 1510.84] in front of us to really wrap our brains around the system.
[1510.84 → 1515.32] And yet he is able to truly, we talk about keeping the system in your head.
[1515.46 → 1517.04] He truly kept the system in his head.
[1517.14 → 1517.70] I mean, it's...
[1517.70 → 1517.90] He did.
[1518.04 → 1518.40] He did.
[1518.56 → 1518.72] Yeah.
[1518.98 → 1519.12] Yeah.
[1519.18 → 1519.92] And Lovelace too.
[1520.20 → 1522.30] Lovelace too, clearly from their interaction.
[1522.94 → 1524.48] She understood how it worked.
[1524.60 → 1526.82] She was able to imagine the sequence of events.
[1526.82 → 1531.16] I mean, what's funny about him is he's thinking both of it logically, right?
[1531.20 → 1532.08] And also physically.
[1532.96 → 1538.52] And at some point in his evolution, he realizes that he needs a hardware description language
[1538.52 → 1543.52] because it's complicated to describe the physical thing.
[1543.52 → 1543.72] Right.
[1543.72 → 1547.08] When really what you want to do is describe what the physical thing does.
[1547.52 → 1549.46] And so he invents a hardware description language.
[1549.46 → 1550.96] Like mechanical Verilog?
[1551.10 → 1551.88] What is this?
[1551.88 → 1552.18] Yes.
[1552.40 → 1552.66] Yes.
[1552.70 → 1553.04] Basically.
[1553.30 → 1554.06] So he's like...
[1554.06 → 1558.06] So for example, you know, he uses his hardware description language to describe a clock,
[1558.40 → 1559.78] how a clock operates.
[1560.36 → 1565.02] And he said, you know, if this component turns around 60 times, this component then moves
[1565.02 → 1566.62] one step, right?
[1566.62 → 1569.26] So it's like abstract without it being how that's actually implemented.
[1569.70 → 1570.14] Wow.
[1570.62 → 1571.20] And so he did that.
[1571.20 → 1575.08] And of course, classic nerd, he then along the way is like, oh, I'm going to change my
[1575.08 → 1575.98] hardware description language.
[1575.98 → 1579.96] So the problem with building the machine is it's a moving target.
[1580.16 → 1580.26] Right.
[1580.30 → 1584.02] So there are plans, there's pages and pages of hardware description language.
[1584.74 → 1588.50] There's also, funnily enough, in some of the best developed plans, there are whole sections
[1588.50 → 1590.68] that are left, you know, unfilled in.
[1590.74 → 1591.74] There's like a blank bit.
[1591.98 → 1596.42] And looking at his documentation and what he wrote down, because we have his lab notebooks,
[1596.54 → 1598.22] basically, thousands and thousands of pages.
[1598.66 → 1600.62] He's basically saying, oh, that bit's obvious.
[1600.62 → 1605.46] Yeah, it's obvious how we'll do that bit, you know, which might be the card reader or
[1605.46 → 1606.24] something like that.
[1606.92 → 1608.76] The other thing he did that's fascinating is microcode.
[1608.96 → 1614.92] So he basically, the punch cards describe an operation like addition.
[1615.76 → 1620.62] Then you've got to actually cause a physical thing to do addition by moving numbers around
[1620.62 → 1623.60] and, you know, carry operations and stuff like that.
[1623.66 → 1627.00] So there he's like, okay, well, essentially the microcodes that.
[1627.00 → 1631.78] And the way he does that it is on the sort of physical barrels, like in a barrel organ.
[1631.88 → 1633.48] They have a load of pins sticking out of them.
[1633.66 → 1637.90] So you have one of those for each instruction, which can then make the machine operate.
[1638.08 → 1639.20] And that's the microcode effectively.
[1639.38 → 1640.50] That's the microcode effectively.
[1640.90 → 1641.24] Wow.
[1641.70 → 1642.52] And then you have the machine.
[1642.66 → 1646.44] But it's, I mean, it's a very similar architecture to one you would recognize.
[1646.58 → 1647.62] It's got a central CPU.
[1647.86 → 1648.88] It's got a bunch of memory.
[1649.20 → 1653.36] It's got ingress and bus, which is, you know, especially the memory bus.
[1653.90 → 1655.94] So it's quite recognizable.
[1655.94 → 1660.54] I think that's what's so tempting about trying to build it is that anyone who's actually looked inside a computer will go,
[1660.62 → 1661.82] oh, yeah, I can see where the CPU is.
[1661.88 → 1664.94] I can see where, I can see all these, you know, analogies.
[1665.08 → 1668.20] And all the optimizations he was making is unbelievable.
[1668.58 → 1669.48] A stupid question.
[1669.70 → 1671.30] Was it buildable at the time?
[1671.42 → 1673.32] Could you have machined it or was it relying on?
[1673.54 → 1673.66] Yes.
[1674.06 → 1674.26] Okay.
[1674.28 → 1675.06] It was actually buildable.
[1675.14 → 1676.56] That's really the cool thing, actually, right?
[1676.62 → 1679.00] Which is that here's the other crazy thing about Babbage.
[1679.54 → 1682.82] The manufacturing techniques were, everything was hand-built.
[1682.82 → 1691.68] And so, for example, at the time, if you got nuts and bolts, you had to go back to the same nut and bolt manufacturer because there was no standardized threads.
[1691.68 → 1704.92] So Babbage, before actually embarking on building even the difference engine stuff, he went on a tour of England, going to visit people who did manufacturing to understanding the state of the art in manufacturing.
[1704.92 → 1711.56] And he eventually teamed up with someone in London who had an apprentice.
[1711.72 → 1717.60] And that apprentice was the person who ultimately would standardize screw and bolt threads.
[1718.80 → 1719.54] That's crazy.
[1719.74 → 1722.78] You mean like that's as a contribution to humanity?
[1722.94 → 1723.92] Like this is the standard?
[1724.14 → 1724.40] Wow.
[1724.60 → 1724.74] Okay.
[1724.84 → 1725.98] He's clearly good at hiring.
[1726.14 → 1726.28] Yeah.
[1726.38 → 1729.16] I mean, he is very good at hiring.
[1729.52 → 1729.72] Yes.
[1729.72 → 1731.02] He was very wealthy, right?
[1731.06 → 1732.18] That helped as well, right?
[1732.20 → 1732.58] Yes.
[1732.58 → 1736.84] But what's clear is he had to bootstrap the whole thing.
[1736.92 → 1738.76] He's like, oh, I don't have any manufacturing techniques.
[1738.84 → 1740.02] Okay, well, I'll figure that out.
[1740.62 → 1751.68] But what's important is when the Science Museum built the difference engine, they did it using materials and machined in such a way that is with the tolerances that were available.
[1751.82 → 1752.62] Oh, wow.
[1752.88 → 1753.18] Wow.
[1753.18 → 1758.86] So they know that the machine does what it should do and would have been reliable.
[1759.40 → 1766.04] And so I think we have a good sense that the analytical engine would also be reliable and actually operate.
[1766.04 → 1784.38] Another really fascinating story about this is if you think about electronic computers, when you have a signal going between components, you quite often have to make sure the signal is amplified in such a way that it's either a one or a zero clearly because we get some fan out cost, right?
[1784.38 → 1795.70] The equivalent in his machine is that he has the numbers that are stored in the memory are stored on a wheel with a cog on it, with a gear on it, zero to nine.
[1796.22 → 1800.84] And obviously, they might not move perfectly into position when you do additional something.
[1800.84 → 1809.32] So he has this little triangular thing that shoves in to the gear and actually pushes it into position into whatever the nearest number is.
[1809.70 → 1817.20] So it's exactly an analogy of an amplifier where you're going, say, in logic gates, where you're keeping the signal at the right level.
[1817.80 → 1822.80] It's fascinating to see these analogies between what happens in electronics and what happens in hardware.
[1822.80 → 1832.00] But we kind of shouldn't be surprised because, you know, many, many, many years later, church and Turing come along and tell us, oh, well, all this stuff is equivalent, right?
[1832.06 → 1833.18] It doesn't matter how you do it.
[1834.46 → 1837.10] So was this ever built before the Science Museum picked it up?
[1837.54 → 1838.90] The Difference Engine was not.
[1838.98 → 1839.80] No, never built.
[1839.90 → 1840.24] Never built.
[1840.36 → 1841.10] No one picked it up.
[1841.34 → 1844.64] So other people saw that Babbage talked a lot about.
[1844.70 → 1847.10] He built some little example pieces, components.
[1847.10 → 1852.16] And then other people saw them and said, oh, we can build a different engine, too.
[1852.24 → 1857.70] And so there were other people who built smaller models, not quite the same scale as what Babbage was doing.
[1857.76 → 1861.46] But then Babbage's machine eventually got built by the Science Museum, and you can go see it.
[1861.50 → 1867.86] And then there was a copy in the History Museum until it was taken aback by its billionaire owner.
[1868.26 → 1869.30] Who's the billionaire owner?
[1869.36 → 1870.48] Yeah, that's shitty.
[1870.66 → 1871.20] Who does that?
[1871.20 → 1871.62] It's dark.
[1872.48 → 1874.40] So they can throw it off the back of their yacht?
[1874.40 → 1879.94] So Nathan Jerrold, CTO, he paid two things.
[1880.18 → 1884.60] He asked the Science Museum to build one so he could have one, have his own Difference Engine.
[1885.18 → 1893.94] And he sweetened the deal by giving the Science Museum enough money to build the bit of the Difference Engine that they had never got around to building, which was the printer.
[1894.78 → 1898.96] And so the reason Babbage got into this whole Difference Engine thing is you have to go back.
[1899.44 → 1900.70] You're 1800s.
[1901.24 → 1903.04] Britain has this massive naval power.
[1903.04 → 1907.10] It needs really accurate information for navigation.
[1908.00 → 1912.06] And, you know, you may have heard about the longitude prize, which was to get to the accurate clock.
[1912.50 → 1920.90] But what you also need is you also need books of tables, of numbers, like log tables, sine, cosine, all that kind of stuff, so you can do calculations.
[1920.90 → 1927.90] And the problem was these things were created at the time by people who were called computers.
[1927.90 → 1928.92] Computers, right, yeah.
[1928.92 → 1931.12] So I was outgoing these things, and they printed these books.
[1931.86 → 1940.64] And Babbage famously said to a friend, I think at college, I wish this damn thing could be all computed by Steam because that would be accurate, right?
[1940.64 → 1942.72] Like that's what set him off in this whole path.
[1942.82 → 1955.62] And the reason he was thinking that is he and a friend from college had a fun time going through books of, say, log tables or sine tables and looking for errors, which sounds like a great evening thing to do.
[1955.62 → 1957.48] But there were lots of errors.
[1957.58 → 1958.98] The finding errors was a valuable thing.
[1958.98 → 1970.62] And so he was like, if I could just make a machine that did the calculation accurately, then not only that, but removed any problem of transcription, it will actually print out the results automatically.
[1971.54 → 1978.42] And so it would actually print out on paper and also print out in such a way that it was possible then to reproduce that mechanically in a book.
[1978.42 → 1985.80] So it would actually make you a lead sheet so you could just take it straight so you'd be absolutely certain your book of log tables was accurate.
[1986.46 → 1987.28] So he did the whole thing.
[1987.44 → 1989.26] And so, you know, this was actually built.
[1989.34 → 1990.84] It does actually work as well as prints.
[1990.90 → 1993.68] And it even does justification as well, the printer, all mechanically.
[1994.38 → 1994.74] Wow.
[1995.00 → 1995.46] That's cool.
[1995.56 → 1996.52] It's justification.
[1997.70 → 1998.96] That's such a good detail.
[1999.08 → 2002.08] It's such a detail for something that exists only in your head.
[2002.24 → 2005.02] I mean, it's just, it's remarkable to me.
[2005.02 → 2010.80] Yeah, but he was trying to, you know, he was trying to make this real thing that would be really valuable.
[2011.02 → 2015.38] And he was thinking through all the issues, you know, like what if it's off by a little bit?
[2015.54 → 2016.92] What if, how am I going to print out?
[2017.00 → 2018.00] How do I move a transcription error?
[2018.42 → 2019.92] What do I do if something goes wrong?
[2020.14 → 2021.56] And so, you know.
[2021.72 → 2022.06] Amazing.
[2022.20 → 2023.24] All right, we got to take a quick break.
[2023.32 → 2027.12] We're going to be back in just a moment with more John Graham coming.
[2031.04 → 2033.48] On the Metal is brought to you by the Oxide Computer Company.
[2033.48 → 2039.16] Well, I thought we had a bit of time to deal with this, but it sounds like the listeners are pretty restless.
[2039.42 → 2039.66] Uh-oh.
[2039.72 → 2040.40] Is this about the ads?
[2040.74 → 2041.00] Yes.
[2041.16 → 2041.56] Oh, no.
[2041.74 → 2042.52] The inbox is full.
[2042.74 → 2043.08] Oh, boy.
[2043.18 → 2050.54] They also have begun recording their own ads and sending them to us requesting mercy from the repetitive ads that we've been subjecting them to.
[2050.56 → 2050.88] Wait a minute.
[2050.94 → 2053.96] They're in such pain over the ads that they're sending us ads for Oxide?
[2054.20 → 2054.42] Yeah.
[2054.64 → 2055.26] I picked one out.
[2055.46 → 2055.90] Have a listen.
[2055.98 → 2057.42] This is from listener Paul Guam.
[2057.42 → 2063.30] I'm getting really, really, exhausted of listening to the same Oxide. Computer ads every week,
[2063.44 → 2072.80] talking about how the Oxide Computer Company is going to make your on-premises infrastructure faster, more efficient, more secure, and just all around less painful.
[2073.34 → 2076.06] So much so, in fact, that I wrote and recorded this ad.
[2076.36 → 2080.40] Head on over to Oxide. Computer to learn more and join the mailing list.
[2080.40 → 2082.32] I think we should just do what Paul said.
[2082.76 → 2082.96] Yeah.
[2083.20 → 2084.34] Let's just follow his instructions.
[2084.48 → 2085.46] Let's get back to the show.
[2089.56 → 2090.72] And we're back.
[2090.82 → 2097.14] We're talking about steam-powered computing, literal steam, and Babbage working on his printer.
[2097.32 → 2103.38] So when they put these things together, and we'll get to Nathan Gerald in a second and him taking back the...
[2103.38 → 2104.66] Yeah, that is just cruel.
[2104.90 → 2105.34] That's cruel.
[2105.68 → 2108.30] And we're going to calm out for it.
[2108.30 → 2110.30] But were there any...
[2110.30 → 2112.62] Surely there were bugs somewhere in this.
[2112.84 → 2115.32] Surely there were things that didn't work correctly.
[2116.04 → 2117.32] Or did Babbage really...
[2117.32 → 2118.84] Did he get this whole thing nailed?
[2119.64 → 2120.44] Well, I think he...
[2120.44 → 2121.62] No, he did get it nailed.
[2121.96 → 2125.72] So what we know is that when they built the difference engine in the Science Museum,
[2126.26 → 2129.12] there was a problem which they identified when they were looking at the plans.
[2129.80 → 2132.62] And the problem was that something was inverted.
[2132.62 → 2141.18] And the speculation is that Babbage may well have actually deliberately introduced the error so that someone, if they were copying it, would not be able to get a work on the sheet.
[2141.18 → 2141.34] Wow.
[2141.40 → 2141.64] Okay.
[2141.64 → 2142.22] All right.
[2142.58 → 2151.18] I mean, that is a testament to, like, your code is so bug-free that when I find a bug in it, I legitimately think that it was introduced deliberately.
[2151.18 → 2151.30] Exactly.
[2152.30 → 2152.74] Exactly.
[2153.04 → 2164.58] So, now, having said that, when they got onto the analytical engine and, you know, there are these letters between Lovelace and Babbage, this is where you get into the, you know, the program is actually bugging.
[2164.96 → 2171.44] And that's really where, you know, Lovelace and Babbage are going back and forwards over this program to calculate a sequence of numbers.
[2171.58 → 2172.86] And they're like, wait a minute, this doesn't work.
[2173.42 → 2177.32] And they're debugging on paper this thing for a machine that doesn't exist.
[2177.68 → 2177.88] Wow.
[2177.88 → 2178.40] That's so cool.
[2178.52 → 2179.16] That's amazing.
[2179.16 → 2181.36] And are they doing this via correspondence?
[2181.66 → 2182.52] So, yes, actually.
[2182.66 → 2187.66] So, obviously, they met a few times in person, but a lot of it is done by literally by letter.
[2188.08 → 2188.56] That's so slow.
[2188.56 → 2188.92] Wow.
[2189.06 → 2190.00] That's so slow.
[2190.40 → 2191.52] That development cycle.
[2191.72 → 2192.30] Like, just think.
[2192.44 → 2194.30] Like, that is, like, the overall slowest.
[2194.64 → 2195.04] Exactly.
[2195.64 → 2196.04] Yeah.
[2196.12 → 2199.20] I mean, people complain about, like, the speed of deploying to production.
[2199.34 → 2201.98] Why don't you try debugging via exchanging letters?
[2202.38 → 2205.40] Instead of, like, waiting to compile, you're waiting for the postman.
[2205.60 → 2206.62] Oh, my gosh.
[2206.62 → 2208.62] Yeah, for a machine that you don't have.
[2208.62 → 2208.98] Yeah.
[2209.06 → 2209.38] Yes.
[2209.68 → 2210.88] And that has never been built.
[2210.88 → 2211.84] It's not a computer yet.
[2213.18 → 2213.54] Wow.
[2214.18 → 2217.90] What I would really like to have, I mean, I sort of get how Babbage got into it, right?
[2217.96 → 2222.64] He sees this problem of these tables, and he thinks, yes, this could be mechanized.
[2222.68 → 2224.78] And he keeps going and going and going.
[2224.88 → 2226.54] And he's just building and building and building on it.
[2227.22 → 2228.66] But what was Lovelace's deal?
[2228.70 → 2229.80] She was like a teenager.
[2229.92 → 2233.34] She walks in, sees a demonstration piece of Babbage's thing.
[2233.44 → 2234.44] Babbage explains it to her.
[2234.44 → 2236.08] And she completely gets it.
[2236.36 → 2237.40] Like, well, it's her deal.
[2238.02 → 2238.78] She'd never seen a computer.
[2238.86 → 2240.36] She's like, great, I'll program that then.
[2241.24 → 2242.42] Where did she come from?
[2242.90 → 2244.24] Because I think that's the thing that's fascinating.
[2244.48 → 2246.02] You know, she obviously had a mathematical background.
[2246.02 → 2252.28] And actually, if you read Babbage's correspondence, she's really the only person who groks it.
[2252.70 → 2253.10] Interesting.
[2253.44 → 2253.60] Okay.
[2253.80 → 2254.12] Interesting.
[2254.30 → 2262.68] I mean, because I was going to ask, like, how is this scene more broadly by even others that are mathematically inclined or mathematicians?
[2262.76 → 2265.38] How do they view all of this work at the time?
[2265.82 → 2269.38] I think the big thing is they view it as he hasn't actually built the machine.
[2269.58 → 2269.82] Right.
[2269.82 → 2273.28] And he keeps asking for more money, and when are we going to get one of these things?
[2273.90 → 2275.20] And I think that's the big thing.
[2275.46 → 2282.64] People understood what he was trying to do, particularly around the difference engine, because that had a very, you know, a real purpose that everybody understood.
[2283.36 → 2289.54] It's not well understood, I think, widely what the analytical engine is about, because that was far out.
[2289.66 → 2293.06] It's like, we're going to make this program a whole thing and run arbitrary programs on it.
[2293.06 → 2297.00] And it's kind of the curse of the cross-disciplinarian as well, right?
[2297.06 → 2305.78] Because it's kind of straddling mathematics and mechanical engineering in a way that is probably at some level foreign to both disciplines, I would imagine.
[2306.06 → 2306.26] Yes.
[2306.34 → 2307.58] Is that a fair inference?
[2308.08 → 2320.64] I think that's not a bad point, actually, which is it being like, because it's very, you know, he's going from a very theoretical world, and then he's, yeah, we've got this physical machine and then people are wondering, you know, what is this, what is this guy on about?
[2320.84 → 2321.06] Right.
[2321.06 → 2336.84] And also, you talk about Banish as also dabbling in all sorts of other areas, like, oh, yeah, we could probably, one of his famous things, we could probably figure out what the ancient climate looked at by cutting down trees and looking at the rings, like how far apart they are.
[2336.84 → 2337.02] Huh.
[2337.82 → 2338.18] Huh.
[2338.94 → 2341.52] He's code-breaking things for the British government.
[2341.96 → 2343.32] It's like all sorts of stuff he's doing.
[2343.44 → 2344.68] His biography is fascinating.
[2345.20 → 2350.20] And at the same time, he's arguing with the establishment of Britain about various things.
[2350.20 → 2352.40] He's basically calling other scientists a bunch of idiots.
[2354.10 → 2356.38] And then he was offered a knighthood.
[2356.76 → 2363.04] He was going to be Sir Charles Banish, but the knighthood he was being offered was not the one he thought was the right one.
[2365.12 → 2366.46] So he turned it down.
[2367.72 → 2368.54] As one does.
[2368.66 → 2370.68] He's like building this machine and dissing everybody else.
[2371.48 → 2372.28] It's so good.
[2372.28 → 2374.84] It's not ideal situation.
[2375.72 → 2379.86] The only thing that's really, really tragic, of course, is that Ada Lovelace died very young.
[2380.04 → 2380.66] Oh, wow.
[2380.78 → 2381.86] I was going to ask where she went.
[2381.88 → 2384.02] And she had cervical cancer and died in her 30s.
[2384.20 → 2385.04] Oh, my gosh.
[2385.28 → 2385.60] Oh, wow.
[2385.62 → 2386.38] I did not realize that.
[2386.60 → 2388.30] It's like nobody understands him.
[2388.36 → 2390.70] This 16-year-old girl turns up and says, yeah, I get this.
[2390.72 → 2391.68] I'll program it with you.
[2392.10 → 2393.48] They go with this long correspondence.
[2393.86 → 2394.74] And then dies young.
[2394.74 → 2395.62] And then she dies.
[2395.80 → 2400.20] And then he lives for years afterwards, having lost the only collaborator he gets.
[2400.30 → 2408.66] And there's this one description, because he doesn't describe this himself, but he went to the U.S. at some point trying to raise money.
[2408.84 → 2410.38] Because here you go again.
[2410.54 → 2413.08] This is such an old but modern thing.
[2413.14 → 2418.80] He said, no one in Britain understands me, but Americans will understand, because they'll think, how can I make money out of this?
[2419.28 → 2421.74] Charles Babbage heads to Sand Hill Road.
[2422.52 → 2423.20] Yeah, exactly.
[2423.20 → 2424.58] He basically goes to the U.S. to try it.
[2424.60 → 2432.94] And in fact, what he does is he decides to make a machine that will play tic-tac-toe, which will show people in the U.S., therefore they'll give him a load of money, and he'll go build his machines.
[2433.14 → 2436.94] But while he's in the U.S., he, somebody asked him.
[2436.94 → 2437.54] That'd be so good.
[2437.96 → 2439.46] I mean, you just gotta pause.
[2439.68 → 2439.80] I know.
[2439.80 → 2440.48] I just think so good.
[2440.48 → 2441.02] I think so good.
[2441.02 → 2443.40] I have to go to the U.S. because they'll pay me money for tic-tac-toe.
[2443.40 → 2447.36] I envisioned him on Sand Hill Road when you said that, and then I just couldn't get over it.
[2447.36 → 2450.26] Oh, and then you envision all these VCs, these 19th century VCs.
[2450.26 → 2451.10] Turning him down.
[2451.10 → 2456.32] And they're saying, well, we'll be cheering for you from the sidelines and, you know, make us, yeah.
[2457.00 → 2462.06] Anyway, so he goes there, but somebody recounts, I can't remember what it is, and this is written up.
[2462.12 → 2467.24] Actually, somebody wrote a letter about it, that they had said something to Babbage about Ada Lovelace.
[2467.24 → 2470.30] And, you know, she had died not long before.
[2470.54 → 2475.08] And that this is just a description of this, him just falling apart in despair.
[2475.08 → 2475.16] Oh, my gosh.
[2475.90 → 2481.60] That she was gone and that, you know, this was his intellectual equal in this process.
[2481.60 → 2486.36] And he was probably in his 70s at this point, and she was, you know, in her 30s.
[2486.42 → 2487.74] But they got it.
[2487.94 → 2491.18] They understood how to make this, what this future was.
[2491.44 → 2498.66] And funnily, she understood it more than he did, because he very much was obsessed with this idea of these mathematical equations.
[2498.82 → 2500.02] You go to all this mathematics in it.
[2500.02 → 2502.96] And she's there, you know, and she says it in one of the papers.
[2503.08 → 2508.52] It's like, hey, but we could represent pretty much anything by numbers, like music or symbols or letters.
[2508.52 → 2510.36] And we could compute all sorts of other stuff.
[2511.42 → 2511.84] And it's like.
[2512.78 → 2515.46] And you call that the Lovelace Leap, I believe.
[2515.88 → 2519.46] I call it that because everyone talks about her being the first programmer, which is fine.
[2519.88 → 2522.52] But, you know, honestly, between her and Babbage, they were both coding.
[2522.72 → 2523.40] Right, right, right, right.
[2523.44 → 2523.94] Yeah, exactly.
[2524.34 → 2527.74] But this thing where it's like, hey, Babbage, you know you're building this machine.
[2527.74 → 2532.18] By the way, we could do text processing and music, and it could compose music and all this kind of stuff.
[2532.22 → 2534.06] It's like that is a huge leap.
[2534.10 → 2534.88] That is a huge leap.
[2534.90 → 2535.38] That's cool.
[2535.62 → 2537.36] It really is a huge leap.
[2537.42 → 2539.50] And to do that again on a machine that's not built.
[2539.64 → 2539.86] Yeah.
[2539.96 → 2540.86] No, exactly.
[2541.56 → 2541.96] So.
[2542.70 → 2544.10] It is a huge leap.
[2544.20 → 2549.92] And so when do they get kind of fully appreciated for their.
[2549.92 → 2557.98] Or I mean, at what point does kind of society realize that they were truly, I mean, ahead of their time by 100 years almost?
[2558.48 → 2561.06] Well, I think the thing that's interesting is they were definitely ahead of their time.
[2561.42 → 2568.66] But Babbage and the Lovelace are kind of like the uncle and aunt of the rest of computing because it's a complete dead end.
[2569.16 → 2569.56] Right.
[2569.56 → 2570.98] They do this stuff.
[2571.48 → 2571.78] He dies.
[2571.88 → 2572.36] She dies.
[2572.52 → 2573.02] He dies.
[2573.40 → 2576.12] His son carries on a little bit of the work, but it really goes nowhere.
[2576.84 → 2585.40] And it kind of stops like end of the end of the 19th century and then middle of the 20th century or, you know, in the 30s, maybe computing reappears again.
[2585.50 → 2587.70] But now electronically or electro mechanically.
[2588.10 → 2588.46] Right.
[2588.46 → 2595.46] And so it's like two separate tracks where there's no, there's not really a direct Babbage to modern computing connection.
[2596.38 → 2604.46] So I was going to ask, so with the kind of the census machines of the late 19th century, how did they even view themselves as, as inheriting any of that legacy?
[2604.66 → 2604.86] Or did they.
[2604.86 → 2605.50] I don't think so.
[2605.50 → 2605.86] Interesting.
[2606.04 → 2607.14] Totally separate track.
[2607.32 → 2611.26] You know, other mechanical things were there.
[2611.36 → 2612.96] And clearly people were aware.
[2612.96 → 2620.56] I mean, the folks who worked on the Harvard Mark I, they say, yeah, you know, there was this other attempt in the 19th century.
[2620.78 → 2628.00] And Turing, in one of his papers, like, yeah, there was, he talks about Ada Lovelace and was aware of, because Ada Lovelace was wondering whether this machine could think.
[2628.56 → 2628.84] Wow.
[2629.64 → 2631.02] That is so ahead of his time.
[2631.34 → 2631.60] All right.
[2631.66 → 2632.30] Ada Lovelace.
[2632.36 → 2634.46] Like, how much of the future are we going to envision here?
[2634.58 → 2635.70] I mean, it's like, wow, interesting.
[2635.92 → 2636.30] I know.
[2636.36 → 2636.60] I know.
[2636.62 → 2642.52] I do wonder if, like, you know, if she hadn't died, would she have kicked, you know, Babbage and be like, can you just build the damn thing?
[2642.52 → 2643.42] Like, I've got stuff.
[2643.52 → 2643.92] I've got to write.
[2643.92 → 2644.34] Oh, wow.
[2644.34 → 2645.44] I've got programs to write.
[2645.82 → 2647.22] That's an interesting thought.
[2647.36 → 2647.52] Yeah.
[2647.62 → 2650.06] If Lovelace had lived, would she have?
[2650.06 → 2661.54] The other thing I think is fascinating is right about this time, right at the same time as Babbage is here with his mechanical computer, Michael Faraday is in London with electromagnetism.
[2661.54 → 2665.52] And he's making transformers and relays and solenoids and all this kind of stuff.
[2665.52 → 2669.94] And it's quite clear that Babbage was obsessed with doing it all mechanically.
[2670.12 → 2676.16] And this electrical, electromechanical thing was way too new and wasn't reliable.
[2676.50 → 2680.92] And, you know, we knew how to handle, you know, gears and all this kind of stuff.
[2681.34 → 2685.62] And so you almost want, I've actually wondered sometimes, suppose Babbage has succeeded.
[2686.26 → 2688.20] Would he have actually set everything back?
[2688.20 → 2691.86] Because we would have perfected mechanical computing.
[2692.02 → 2693.18] We would have got it perfect.
[2693.26 → 2694.52] And we would have mechanical computers.
[2694.94 → 2696.12] You know, Faraday would be on the side.
[2696.22 → 2698.96] They're going, you know, you could do this about a thousand times faster with electricity, right?
[2699.60 → 2700.60] And we're like, no, no, no, no.
[2700.60 → 2702.16] That technology is too new.
[2702.26 → 2703.02] It's unreliable.
[2703.66 → 2704.08] Oh, yeah.
[2704.08 → 2704.52] Yeah.
[2704.52 → 2704.74] Hmm.
[2705.20 → 2708.58] That could have totally set a different, like, time in motion.
[2708.86 → 2710.64] Oh, well, you can just imagine a lot.
[2710.78 → 2715.12] Well, you can also then imagine, I mean, I think you can also imagine the machine gets built
[2715.12 → 2720.00] and people realize this could be done much faster with relays and so on.
[2720.08 → 2724.08] And then computing gets jump-started 60 years earlier.
[2725.14 → 2725.28] Yeah.
[2725.70 → 2726.18] Maybe.
[2726.34 → 2726.86] Who knows?
[2727.06 → 2729.46] Anyway, Babbage and Lovelace were really smart.
[2729.46 → 2734.20] And definitely Babbage was, you know, if Lovelace can be called the first programmer,
[2734.34 → 2736.64] then I really think Babbage is the first computer nerd.
[2736.98 → 2737.16] For sure.
[2737.28 → 2737.88] Well, it's all right.
[2737.90 → 2741.76] So here's another kind of question in terms of, because you, I mean, in terms of how the
[2741.76 → 2746.56] history of computing actually gets written, even the census machines and so on, and the
[2746.56 → 2752.08] kind of accounting machines of the early 20th century don't actually get us over the hump.
[2752.20 → 2757.78] It ultimately takes the existential threat of a world war to actually get humanity over the
[2757.78 → 2759.88] hump with respect to computing.
[2760.32 → 2761.74] Or maybe you didn't.
[2761.74 → 2762.06] Maybe.
[2762.30 → 2762.70] Maybe.
[2762.80 → 2764.84] Or maybe that was just, just happened, right?
[2764.94 → 2768.30] That in the 30s, you know, Turing is doing some theoretical work.
[2768.40 → 2769.46] Church is there.
[2769.98 → 2771.08] And some stuff is happening.
[2771.44 → 2773.94] And then, you know, and then, yes, the war is there.
[2774.14 → 2777.78] And, but I don't know, but maybe the war gave us some bunch of money.
[2777.90 → 2779.94] But it feels like the time was ripe.
[2780.18 → 2780.54] Interesting.
[2780.76 → 2781.02] Okay.
[2781.50 → 2786.12] Shannon is there thinking about, you know, we could do all this logic we want to do.
[2786.18 → 2787.02] We could do it with electronics.
[2787.02 → 2787.82] I don't know.
[2787.92 → 2789.30] I'm not sure the war was actually essential.
[2789.44 → 2792.46] I mean, the war certainly, you know, a lot of money got spent on computing.
[2792.66 → 2795.90] Well, it certainly focused the mind on the problems at hand.
[2796.40 → 2797.06] But interesting.
[2797.24 → 2799.12] So all of these things were kind of building up.
[2799.30 → 2802.44] And it was, do you think that there was, there was a bit of inevitability to it then
[2802.44 → 2803.06] at that point?
[2803.56 → 2805.08] I do think it was kind of inevitable.
[2805.32 → 2805.58] Yes.
[2805.58 → 2811.42] Because if you look at the way people were thinking about things and then, you know,
[2811.42 → 2816.72] there was, there was this process in mathematics where there was this idea that maybe we can
[2816.72 → 2820.20] mechanize a lot of stuff that was happening in mathematics before there were machines.
[2820.20 → 2824.22] So I think even from the theoretical side of things, mathematicians were thinking about
[2824.22 → 2825.88] these things, which is how Turing gets to it.
[2825.92 → 2827.80] Actually, he's trying to solve a problem in mathematics.
[2828.00 → 2829.32] He's not trying to invent a computer.
[2829.80 → 2833.84] But along the way, he's like, oh, so in order to mechanize this thing, I need some sort of
[2833.84 → 2834.18] machine.
[2834.18 → 2838.86] And then he describes this universal, what he called an A machine, with what we can have
[2838.86 → 2839.58] as a Turing machine.
[2839.94 → 2842.62] Was this a budding kind of theory of computation than in math?
[2842.74 → 2845.06] What's the outgrowth of math that Turing is coming from?
[2845.32 → 2850.48] Well, so there's this, there's this thing called the Enschede's problem, which was
[2850.48 → 2851.94] one of Hilbert's problems.
[2852.04 → 2857.08] So this mathematician called David Hilbert came along, and he said, well, there's a program
[2857.08 → 2858.20] of work we should do.
[2858.22 → 2859.30] This is in the 1920s.
[2859.76 → 2861.94] Basically, the idea was, you've got a lot of mathematics.
[2861.94 → 2867.08] He thought, well, maybe we could create this really solid, logical foundation for all of
[2867.08 → 2867.62] mathematics.
[2868.46 → 2872.80] And we could have a set of axioms, and we could do everything, just lay it all out.
[2872.90 → 2876.12] All mathematics could somehow be encompassed in this one project.
[2876.26 → 2880.72] So he's like, well, therefore, we need to figure out what the formal language would be
[2880.72 → 2881.20] for that.
[2881.48 → 2884.78] And then we need to see if we could find a system which has certain properties.
[2885.50 → 2887.50] So for example, is it complete?
[2887.64 → 2889.76] Could everything that's true actually be proved?
[2889.76 → 2891.28] Is it consistent?
[2891.62 → 2894.32] Are there no contradictions in this mathematics?
[2895.18 → 2897.50] And actually, the last one is, is it decidable?
[2897.72 → 2902.76] Which is, is there some algorithm to decide whether a mathematical statement is true or
[2902.76 → 2903.04] false?
[2903.56 → 2908.04] And so this was just a purely mathematical project.
[2908.04 → 2910.52] But you can see the seed of the halting problem for sure.
[2910.64 → 2911.46] Yeah, exactly.
[2911.60 → 2916.44] And Gödel comes along, Kurt Gödel comes along and comes up with this incompleteness serum
[2916.44 → 2918.70] and says, it doesn't matter what you try, it's going to be incomplete.
[2919.34 → 2921.64] Which kind of went, poof, you know, blew up the whole.
[2923.70 → 2924.42] Oh, sorry.
[2924.54 → 2926.16] Did I just burn your domain to the ground?
[2926.54 → 2930.04] I thought that like Hilbert's problem was one of the like unsolved math things.
[2930.04 → 2930.92] Yeah, yeah.
[2931.18 → 2932.08] But yeah, that's why.
[2932.42 → 2934.08] But you just ruined everything.
[2934.40 → 2939.22] And then, and then Turing is like, well, I think I'm going to go and think about this
[2939.22 → 2941.38] whole like decidability thing.
[2941.48 → 2945.22] And I'll go and look at this and, you know, what can we actually decide?
[2945.50 → 2950.16] And so Church was doing that with the Lambda calculus and Turing, the Turing machines.
[2950.72 → 2954.22] And, you know, the equivalent of Gödel's incomplete hysteria is a halting problem.
[2954.32 → 2956.76] It's like, yeah, actually there are some things you won't be able to decide whether these
[2956.76 → 2957.56] programs hold it.
[2957.56 → 2962.12] So, you know, at this point, David Hilbert's just like, oh, my whole program has gone.
[2963.88 → 2965.02] You know, thanks guys.
[2965.56 → 2969.70] But what comes out of that because of the this decidability is kind of mechanical is,
[2969.82 → 2970.54] is computers.
[2970.64 → 2973.52] So I think there was a lot was right in the twenties and thirties.
[2973.58 → 2974.90] And then of course, second world war happened.
[2975.10 → 2975.24] Right.
[2975.84 → 2976.92] We need a practical machine.
[2978.20 → 2982.74] And is this crew aware of Babbage and, and Lovelace?
[2982.86 → 2986.02] I mean, are they well enough known that they would have been aware that they had done this
[2986.02 → 2986.38] work?
[2986.38 → 2989.94] Like, so this references a little bit, but they're not building on it.
[2990.10 → 2994.52] They're off on the side doing mathematics, and they're not really thinking about this,
[2994.66 → 2995.12] this machine.
[2995.20 → 2997.46] It's only later that they sort of, oh yeah, that's kind of similar.
[2998.18 → 3000.24] That's some of what we're doing, but it's, it's much later.
[3000.34 → 3003.68] It's not a linear progression through these things.
[3004.04 → 3004.32] Huh?
[3005.42 → 3005.76] Wow.
[3005.76 → 3007.32] And so, I mean, I just, I mean, I don't know.
[3007.42 → 3010.44] And maybe it's the way you're describing it feels so cinematic.
[3010.70 → 3013.46] I mean, there's got to be a movie, right?
[3013.62 → 3018.82] There's gotta, we have to figure out like who stars as Babbage and who stars as Lovelace.
[3018.90 → 3019.58] It feels like, I don't know.
[3019.62 → 3023.28] It feels like there's like, there's a great movie to be made here about their story.
[3023.28 → 3027.84] So, and it must've been amazing too, to have all that correspondence between the two of
[3027.84 → 3028.04] them.
[3028.04 → 3028.28] Yeah.
[3028.68 → 3034.18] There are loads of correspondence, Lovelace's letters, and then, you know, Babbage's letters
[3034.18 → 3036.34] and Babbage's writing and her writing.
[3036.60 → 3040.56] And then, you know, a bunch of people that, you know, they spoke to and described what they
[3040.56 → 3041.04] were doing.
[3041.42 → 3045.24] It's very, it's very interesting to see it because it gives us a lot of background references.
[3045.84 → 3049.74] One of my favourite things about Lovelace is that her mother, because, because, right.
[3049.74 → 3057.66] So Lovelace's father was Lord Byron, who was, you know, a poet and quite, you know, famous
[3057.66 → 3060.20] and also a drug addict and many other things.
[3060.42 → 3065.30] And Lovelace's mother didn't want her daughter to have this poetical spirit because that was
[3065.30 → 3066.78] terrible for a girl, right?
[3066.80 → 3068.96] To have the poetry of her father.
[3069.28 → 3072.86] And so she made her learn mathematics as an antidote to that.
[3073.70 → 3074.76] That's how she was taught.
[3074.86 → 3077.72] And then one of her tutors was De Morgan of De Morgan's.
[3077.72 → 3078.26] Oh my gosh.
[3078.26 → 3079.72] Whoa, that is dope.
[3080.22 → 3080.66] Whoa.
[3080.98 → 3082.64] It's like, oh, and De Morgan is here.
[3082.86 → 3083.88] He's got a cameo.
[3084.60 → 3085.26] Yeah, exactly.
[3085.70 → 3088.72] It's like, De Morgan's like, you know, oh, who are we going to get, who are we going
[3088.72 → 3090.38] to get to teach, you know, math about as well?
[3090.52 → 3091.44] De Morgan, he'll do.
[3092.80 → 3093.52] He's available.
[3095.66 → 3099.12] So, you know, so she had this very strong mathematical background.
[3099.78 → 3103.54] The only thing about Lady Love is it does come across a little bit in her letters, but
[3103.54 → 3105.54] she does have quite a high opinion of herself.
[3106.50 → 3108.42] Well, I mean, hey, wait a minute.
[3108.42 → 3110.64] In her defence, it sounds like...
[3110.64 → 3113.74] If one is going to have a high opinion of themselves, it sounds like she qualifies.
[3113.92 → 3114.48] Yeah, exactly.
[3114.70 → 3116.26] She's like, I'm kind of acing it over here.
[3116.48 → 3117.40] Like, I don't know if you're...
[3118.40 → 3121.48] Like, do I need to remind you that music can be represented as information?
[3121.74 → 3122.40] Like, okay, yeah.
[3123.22 → 3124.22] Sorry, what have you done again?
[3124.22 → 3126.10] Like, I was tripping up to Morgan when I was 12.
[3126.54 → 3126.84] Yeah, exactly.
[3127.96 → 3132.20] Well, actually, De Morgan did say about her, you know, she really is an original thinker
[3132.20 → 3136.56] in mathematics and could actually be a first-rate, like, eminence, I think is what he said.
[3136.84 → 3138.40] So, you know, and she was very young as well.
[3138.54 → 3140.44] But incredible story for the two of them.
[3140.50 → 3144.34] And, you know, they obviously managed to get the poetry out of her, get the mathematics
[3144.34 → 3144.94] into it.
[3145.26 → 3146.10] Yeah, that's crazy.
[3146.52 → 3147.60] It is just...
[3147.60 → 3149.88] Yeah, it is just amazing to think about.
[3150.10 → 3154.10] And to think about all the kind of cast of characters that are...
[3154.10 → 3157.68] So, in terms of building the analytical engine, what's the progress on that?
[3157.74 → 3159.16] Because I think that the...
[3159.16 → 3162.36] And to kind of give you some of the context for the question, too, one of the things that
[3162.36 → 3166.38] has been so fun about doing this podcast is talking to people about how they got into
[3166.38 → 3166.74] computing.
[3167.42 → 3170.10] And we learned about this thing called Dr. Him.
[3170.10 → 3176.78] And this mechanical manifestation of Dr. Him that Ron Min nick described as being really
[3176.78 → 3178.26] inspirational to him.
[3178.34 → 3182.56] And based on that, there's this thing called Turing Tumble that's out there today, which
[3182.56 → 3183.26] is really neat.
[3184.00 → 3190.04] And there's something that's really great and approachable about these systems for mechanical
[3190.04 → 3194.46] computation because it's so visceral in a way that, you know, a smartphone is just not
[3194.46 → 3196.46] approachable in any kind of the same way.
[3196.46 → 3200.16] And in terms of introducing kids and people to computing.
[3200.50 → 3202.12] So, what's the progress on the analytical engine?
[3202.26 → 3203.82] Because has that yet been built?
[3204.42 → 3204.58] No.
[3204.76 → 3205.32] Goodness me, no.
[3205.42 → 3208.92] So, I created a little charity in the UK to try and get this thing together.
[3209.08 → 3212.72] And I found basically the two other giant Babbage nerds in the world.
[3212.82 → 3217.76] So, Don Suede, who actually was the person at the Science Museum who ran the project to
[3217.76 → 3218.68] build the Difference Engine.
[3219.00 → 3223.54] And a guy in the US called Tim Robinson, who has been building bits of the analytical engine
[3223.54 → 3224.46] out of Meccano.
[3224.46 → 3231.92] And the two of them have been poring over every page of Babbage's notes about the analytical
[3231.92 → 3232.22] engine.
[3232.34 → 3237.86] And we now have a massive cross-reference where we can look up anything about this.
[3238.48 → 3241.94] And so, the reason that's important is that Babbage kept changing his mind about stuff.
[3242.02 → 3245.98] So, for example, he's like, oh, yeah, we'll use base 10 for this machine.
[3246.10 → 3247.00] No, let's use binary.
[3247.48 → 3248.98] No, let's use base 12.
[3249.44 → 3250.46] No, let's use base 16.
[3250.46 → 3255.62] So, I was going to ask about the base because the 10 is effectively arbitrary.
[3256.26 → 3256.66] Yes.
[3256.88 → 3260.16] And you're presumably looking for something that has the best mechanical properties.
[3260.76 → 3260.98] Right.
[3261.44 → 3262.56] That's why he, yeah.
[3262.94 → 3265.20] And so, it sounds like there was some vacillation on that.
[3265.66 → 3266.18] Yes, there was.
[3266.26 → 3269.56] So, his decision was base 10 because it's easy for the UI, right?
[3269.56 → 3274.12] A human can inspect the state of the machine and know what's going on.
[3274.18 → 3274.84] It makes it easy.
[3275.18 → 3278.26] It makes the mechanics of the machine more complicated for addition.
[3278.48 → 3283.02] And one of the reasons why he wanted to have binary was to make an adder really simple,
[3283.10 → 3283.28] right?
[3283.76 → 3287.30] But he realized that if he had binary, then his memory locations, right?
[3287.36 → 3293.70] His bytes, which are literally stacks of years, would be so tall, mechanically, you'd have
[3293.70 → 3294.66] difficulty moving them.
[3294.66 → 3297.66] So, how much memory does he have in the analytical engine?
[3297.90 → 3299.48] It depends on which version you're talking about.
[3299.48 → 3299.76] Right.
[3299.86 → 3300.20] Yeah, right.
[3300.30 → 3300.88] Which base?
[3301.28 → 3301.46] Yeah.
[3301.62 → 3304.62] Somewhere between 10 and 1,000 memory locations.
[3304.88 → 3311.30] Each one being, depends on the spec exactly, but typically a 30-digit base 10 number.
[3312.16 → 3312.44] Wow.
[3312.64 → 3313.08] That's cool.
[3313.18 → 3313.78] That is cool.
[3313.82 → 3315.32] But it's also, that is small.
[3315.78 → 3316.40] But guess what?
[3316.64 → 3318.08] That is tiny.
[3318.08 → 3320.04] I might need double precision.
[3320.04 → 3324.38] I'll invent a system where I can link two memory locations together.
[3325.10 → 3327.78] So, if I need 60 digits, I'll be fine.
[3328.10 → 3328.60] That's crazy.
[3328.66 → 3331.04] So, yeah, the quad word, the mechanical quad word.
[3331.28 → 3331.62] Yes.
[3331.88 → 3332.14] Yeah.
[3332.60 → 3333.00] Wow.
[3333.16 → 3333.28] Okay.
[3333.36 → 3333.76] That's crazy.
[3334.00 → 3335.68] So, you're trying to, so there are efforts.
[3335.80 → 3338.82] You've got to figure out, like, which version of the analytical engine are we building here.
[3338.84 → 3339.02] Exactly.
[3339.02 → 3339.12] Exactly.
[3339.16 → 3342.02] So, the next step right now is, now that we have all this stuff together, is actually
[3342.02 → 3347.18] to take some of the hardware description language, the Verilog of the 1800s, and try
[3347.18 → 3354.06] to figure out, okay, which bits are missing, you know, do we have enough to actually create
[3354.06 → 3354.42] something?
[3354.58 → 3356.00] Has it been built in simulation?
[3356.96 → 3357.64] No, not yet.
[3357.82 → 3358.10] Not yet.
[3358.14 → 3363.72] Because there's literally, you know, 10 different written plans, and there are thousands of pages
[3363.72 → 3365.76] of, you know, oh, I'll try this out.
[3365.82 → 3366.34] Oh, I'll try this.
[3366.34 → 3369.46] Like a little sketch of some cogs, and maybe it'll work like this.
[3369.64 → 3370.92] And here's the microcode.
[3371.00 → 3372.90] And by the way, here's a program I produced on paper.
[3373.24 → 3376.08] It's a massive, you know, archaeological thing.
[3376.08 → 3380.94] Whereas the difference engine, before Babbage's death, he left behind a complete set of plans.
[3381.22 → 3385.92] So, it was the simple task, the mere task of, you know, interpreting those plans.
[3386.12 → 3386.26] Right.
[3386.90 → 3390.30] This is much more archaeology on what he was doing.
[3390.64 → 3395.00] Yeah, I was going to ask, because, like, I saw, I stocked these weird auctions online,
[3395.14 → 3400.28] and I saw, like, there's, like, some letters and stuff from Babbage and Lovelace, like, in
[3400.28 → 3401.12] a random auction.
[3401.12 → 3404.86] So, it's like, how do you collect all these things when it seems like they're almost also scattered
[3404.86 → 3405.90] across, like, the world?
[3406.56 → 3412.34] Well, the good thing is, his actual papers, whether he had, he arranged through his son,
[3412.68 → 3415.50] you know, they would be donated to the Science Museum in London.
[3416.04 → 3420.12] So, the Science Museum has kept them since the 1800s and preserved them, and then scanned
[3420.12 → 3420.40] them.
[3421.22 → 3422.54] So, there's a lot.
[3422.66 → 3424.22] So, sort of the definitive stuff is there.
[3424.48 → 3427.86] The letters are more interesting just from the historical context of what were they thinking,
[3427.86 → 3430.06] and who were they interacting with.
[3430.72 → 3436.28] Jess, Tim Robinson maintains the difference engine number two at the Computer History
[3436.28 → 3437.14] Museum in Mountain View.
[3437.26 → 3437.48] What?
[3437.74 → 3438.20] That's right.
[3438.66 → 3438.90] Yes.
[3439.26 → 3439.44] Oh.
[3439.80 → 3441.72] Responsible for operation and presentation of it.
[3442.02 → 3443.98] So, we're heading there in a couple of weeks, John.
[3444.22 → 3448.18] Yeah, he knew how, yeah, he's run it, really knows how it works.
[3448.24 → 3453.28] So, between Tim and DORAN, they've been going back and forth on, what are we going to build,
[3453.36 → 3453.96] and what does it look like?
[3453.96 → 3455.32] But the cross-referencing was massive.
[3455.42 → 3458.32] It meant, you know, transcribing thousands and thousands of pages.
[3459.00 → 3465.24] And, you know, talking about handwritten in Babbage's lab notebook, copy plate writing,
[3465.78 → 3468.82] which even just staring at one of them, you're trying to interpret what he's saying.
[3468.96 → 3469.36] Oh, right.
[3469.44 → 3473.08] Yeah, I mean, just imagine, there's a lot to be done, but it feels like this is an important
[3473.08 → 3474.88] thing for humanity to do, don't you think?
[3475.30 → 3479.52] Well, I know that computer nerds think that, but I'm not sure humanity thinks that.
[3480.66 → 3483.26] So, I know that I think it's really, really cool.
[3483.26 → 3484.90] And I'd like to see the machine.
[3485.08 → 3489.22] What I hope is that we can build a machine eventually that, you know, were Babbage to
[3489.22 → 3493.30] appear in the room, he would, first, look at it and recognize his machine.
[3493.76 → 3497.78] And then, in his typical curmudgeonly way, say, why the hell did you build this version?
[3498.16 → 3500.24] The next version is going to be much better.
[3500.88 → 3500.98] Right.
[3501.40 → 3505.54] Well, you wouldn't wonder what he would feel, because then, I mean, all of these things got
[3505.54 → 3507.64] so improved upon in the machine.
[3507.74 → 3508.88] He's like, why are you building this at all?
[3508.92 → 3509.94] You've already built this machine.
[3509.94 → 3513.64] I know, he probably just ranked us for being idiots.
[3513.90 → 3514.14] Right.
[3514.34 → 3515.76] You have these computers in your pocket.
[3515.94 → 3518.18] Why are you building this mechanical thing?
[3518.78 → 3521.06] But it just feels like it would be valuable to go.
[3521.16 → 3523.46] I mean, it's so important historically.
[3523.98 → 3527.78] You would think, and you've got to think one of these billionaires can actually, like,
[3527.84 → 3528.64] back up the truck.
[3528.80 → 3531.44] I mean, they spend money on so much dumb stuff.
[3531.96 → 3533.26] Sand Hill Road should fund it.
[3533.40 → 3533.56] Right.
[3533.56 → 3536.18] You mean all these, like, super yachts and all this other garbage?
[3537.06 → 3537.20] Yeah.
[3537.30 → 3539.22] Sand Hill Road, I'm not sure if that's fundable.
[3539.42 → 3540.70] I'm not sure if that's fundable.
[3541.16 → 3543.70] Speaking as ones who have started a computer company.
[3544.30 → 3546.50] I don't know that it would have made our pitch any easier.
[3546.78 → 3551.04] Now, if that helps people play tic-tac-toe on a social network, that's fundable.
[3551.32 → 3551.84] Yeah, exactly.
[3552.84 → 3555.98] I mean, and who doesn't need a locomotive-sized mechanical?
[3556.98 → 3557.40] All right.
[3557.40 → 3558.60] So that's a good question.
[3558.60 → 3563.74] Do we know even what the physical size of a completed analytical engine would be on the order of?
[3563.98 → 3565.94] It sounds like a locomotive size.
[3566.20 → 3566.32] Yeah.
[3566.62 → 3568.94] Like a small, small steam locomotive.
[3569.22 → 3569.48] That's cool.
[3569.72 → 3570.30] That's dope.
[3570.88 → 3571.02] Yeah.
[3571.68 → 3572.44] That's feasible.
[3573.28 → 3574.36] I think it'd be fantastic.
[3574.50 → 3575.52] I mean, very, very slow.
[3576.30 → 3582.74] You know, we know that, well, we have some idea about how fast it would run.
[3582.74 → 3592.78] It takes, so roughly based on the data we have, to fetch two numbers from memory and put it into the CPU for addition takes three seconds.
[3593.34 → 3593.82] Whoa.
[3594.62 → 3596.50] But that's why he invented pipelining.
[3596.76 → 3602.60] Because then he was like, hey, while I was adding, I could get the next two numbers and put them on the input bus.
[3602.60 → 3603.04] Wow.
[3603.48 → 3603.92] Wow.
[3604.06 → 3604.96] That is slow.
[3605.10 → 3609.76] So you do wonder, would that have been prohibitively slow?
[3609.88 → 3613.48] I mean, would that have been, would it have been able to do things that were otherwise, I'm sure.
[3613.72 → 3614.68] Not his next version.
[3615.12 → 3615.44] Exactly.
[3615.44 → 3615.96] Right.
[3616.06 → 3616.34] Exactly.
[3617.10 → 3617.50] Exactly.
[3617.74 → 3618.72] Why you built that one?
[3618.96 → 3620.50] I've got one for it in one second.
[3621.22 → 3621.56] Amazing.
[3621.68 → 3629.68] The other thing that's quite interesting in his stuff is he, he essentially has the whole risk versus risk in his head.
[3629.68 → 3633.38] Because he's like, well, I can make a simpler machine if I have simple instructions.
[3633.50 → 3633.92] Oh, interesting.
[3634.06 → 3641.28] But if I make complex instructions, then the machine will be faster because I can do something like, you know, square root operation or something.
[3641.58 → 3648.18] So he's like trying to decide, he's trying to play off what do I build versus what, you know, the performance of the machine.
[3648.40 → 3651.20] And does he have any inkling of the stored program computer?
[3651.30 → 3653.70] Does he think about putting these instructions in the memory itself?
[3654.02 → 3654.42] No.
[3654.70 → 3655.00] Interesting.
[3655.18 → 3656.12] That's a great question.
[3656.24 → 3657.72] He does not think about that at all.
[3657.72 → 3664.74] They're all on, they're all on the punch cards and there's definitely no sense that you could put the program in memory.
[3664.88 → 3667.78] He obviously has a sense of looping and things because he's going to need it.
[3667.78 → 3668.02] Right.
[3668.20 → 3668.46] Right.
[3668.52 → 3668.62] Right.
[3668.62 → 3668.74] Right.
[3668.86 → 3669.76] As a program.
[3670.14 → 3680.46] The only thing that's really wild is that he's an operator for this computer and the operator's job is to do what the analytical engine tells that operator to do.
[3680.94 → 3681.28] Fun job.
[3681.28 → 3681.42] Fun job.
[3681.86 → 3682.14] Yeah.
[3682.22 → 3682.62] Fun job.
[3682.68 → 3682.80] Right.
[3682.86 → 3690.96] So, so he, he envisaged there being a, a wooden cabinet full of programs and essentially subroutines.
[3690.96 → 3700.24] And at some point the machine rings a bell, which is handled by one of the punch cards and says, you need to load up, you know, the cosine subroutine right now.
[3700.24 → 3707.76] I need to do it because I haven't necessarily got it all because there will limit on, he thinks there's a limit on the number of punch cards you can have in a reel.
[3708.58 → 3710.08] There's going to be some physical limit.
[3710.22 → 3715.74] So, you know, the operator has to come over and either feed in new instructions or new, or new data to the machine.
[3715.74 → 3718.92] But no, he does not think about it as a store program at all.
[3719.66 → 3720.12] That is interesting.
[3720.24 → 3724.84] So, I mean, because I've always called this John von Neumann's gift, and it sounds like I can still call it John von Neumann's gift.
[3724.90 → 3729.56] It sounds like it is not John von Neumann's gift as stolen from Ada Lovelace and Charles Babbage.
[3729.84 → 3730.06] Yeah.
[3730.14 → 3730.82] I mean, I think so.
[3730.90 → 3733.16] I mean, to a certain extent, the Turing A machine.
[3733.24 → 3733.48] Right.
[3733.62 → 3733.74] Yeah.
[3733.74 → 3736.66] Being a universal machine that reads a, reads a program from the tape.
[3736.90 → 3738.06] Same, same kind of thing.
[3738.12 → 3742.52] But yeah, Babbage, I mean, his memory was so slow, and I think he liked the idea of punch cards.
[3742.52 → 3744.18] So, you know, that was where the program was.
[3744.18 → 3747.02] Just like the physical idea of punch cards.
[3747.52 → 3747.62] Yeah.
[3747.70 → 3748.86] I mean, go see them in the science museum.
[3748.98 → 3752.12] There's a stack of them standing there with a program on them.
[3752.40 → 3752.80] Wow.
[3752.92 → 3754.64] I find it so incredibly upsetting.
[3754.86 → 3758.18] Every time I look at that stack of cards, I'm like, there's a program trying to be run right there.
[3758.30 → 3758.62] It's waiting.
[3759.10 → 3759.90] Yeah, it is.
[3759.90 → 3762.64] It's waiting 150 years and no one's running it.
[3763.02 → 3763.76] So, I mean, you can run.
[3763.76 → 3764.68] No, that's so messed up.
[3764.78 → 3767.52] Well, it feels like you at least want to be able to do it in simulation.
[3767.94 → 3772.02] Not actually machining the thing, but actually being able to simulate a completed thing.
[3772.02 → 3772.16] Absolutely.
[3772.36 → 3773.38] And we'll get there, right?
[3773.38 → 3775.04] That's sort of the next thing.
[3775.12 → 3777.80] Once you say, okay, this is the machine.
[3778.00 → 3778.82] Okay, now we can simulate.
[3778.96 → 3779.46] We've got mice.
[3779.66 → 3780.90] We can simulate stuff.
[3781.12 → 3781.50] That's cool.
[3781.60 → 3785.86] It's interesting, actually, when they built the difference engine, because they were doing it in mid-80s,
[3786.48 → 3790.94] they couldn't do a simulation because simulation software wasn't enough on the computer at the time.
[3791.34 → 3794.80] But now, actually, yeah, we can simulate the whole machine physically, right?
[3794.90 → 3796.02] Do physic simulation.
[3796.66 → 3797.44] Whoa, that's cool.
[3797.44 → 3800.36] Yeah, which I think would be, I mean, I think that would be really valuable.
[3800.54 → 3803.36] I think that they may obviously make it easier to machine and debug and so on.
[3803.36 → 3804.48] But yeah, absolutely.
[3804.84 → 3805.18] Absolutely.
[3805.36 → 3805.90] We will.
[3806.24 → 3810.46] The thing is, it's very easy to design a mechanical computer, right?
[3810.46 → 3814.82] Because we can just go backwards, and we can just be like, oh, yeah, well, this is, we know all about computing.
[3814.82 → 3817.16] Let's design a thing online.
[3817.56 → 3822.64] We want to actually build the thing he wanted to build, not some fantasy version of what he wanted to build.
[3822.74 → 3823.88] That's what makes it a slow.
[3824.56 → 3825.00] Right.
[3825.12 → 3827.80] Because what he wanted to build is so ill-defined.
[3828.38 → 3828.70] Yes.
[3829.14 → 3829.42] Yes.
[3829.60 → 3830.30] Yeah, that's right.
[3830.52 → 3834.78] We've got to take another quick break, and we'll be back with more John Graham coming on the metal.
[3838.68 → 3841.28] On the metal is brought to you by the Oxide Computer Company.
[3841.60 → 3842.62] Take it from Paul Guam.
[3842.70 → 3844.92] Just go to Oxide. Computer and let's please get back to the show.
[3847.16 → 3849.64] All right, we're back.
[3850.10 → 3851.52] And Steve, I think you had a question for John.
[3851.52 → 3856.58] Well, yeah, I want to ask about another fascinating person in computer history, Douglas Engelhardt,
[3856.80 → 3864.20] that you mentioned in a 2013 OSCAN talk when you were talking about how a lot of the innovation of today are maybe recycled is too strong,
[3864.30 → 3867.40] but had been imagined and had been built before.
[3867.82 → 3871.84] But you talked specifically about him and what was called the mother of all demos.
[3872.10 → 3872.86] Mother of all demos, yeah.
[3872.98 → 3874.60] I want to ask a little bit more about that.
[3874.60 → 3880.64] Yeah, I mean, the thing that's fascinating about computing, and I can't ever quite reconcile this in my head,
[3880.72 → 3886.88] is that we both forget about what the past was and think everything is new.
[3887.42 → 3892.64] And we benefit from that and lose from it because we sort of reinvent stuff.
[3892.64 → 3899.70] And it almost seems like somehow it's necessary to reinvent stuff, that if we were stuck in the past, we would never invent new stuff.
[3900.10 → 3907.74] So this is a weird thing where it's like, you know, you look at stuff that gets invented today, and you do the cloud computing and VMs and stuff.
[3907.82 → 3910.10] And you're like, wait a minute, wasn't a lot of this done in mainframes?
[3910.64 → 3914.40] But it's almost like it got forgotten or like hidden away or looked down on.
[3914.40 → 3916.98] And I find it really weird.
[3917.16 → 3922.04] And the mother of all demos is fascinating because, you know, you're talking about forever ago.
[3922.36 → 3929.64] And here's a guy doing like desktop video conferencing, and he's got hypertext, and he's just interacting with the computer over a phone line.
[3930.30 → 3932.02] It's a little bit more complicated than that.
[3932.08 → 3934.02] But it's just fascinating to see.
[3934.02 → 3939.86] And then, you know, inventing the mouse because, hey, we need to have the mouse because we need some pointing device.
[3940.42 → 3942.54] And that for me is really, fascinating.
[3942.64 → 3949.08] But it's hard to reconcile with, you know, we in some ways seem to like to forget the history of computing and reinventing.
[3949.84 → 3960.20] So is it reinvention or to me, I think the present rhymes with the past because you look at, you know, take cloud computing and virtualization and so on.
[3960.20 → 3964.90] And there are certainly very, very important elements done very early in computing.
[3965.44 → 3970.96] But modern virtualization actually did have to solve a bunch of problems that had not been previously solved.
[3971.40 → 3978.04] I mean, my view has always been that you want to really look to the past to make sure you understand what has been done before.
[3978.18 → 3979.56] So you're not resolving the same problem.
[3980.22 → 3984.80] But I think sometimes we overly lionize the past, and we think that every problem has been solved.
[3984.90 → 3985.20] I don't know.
[3985.44 → 3986.26] No, I think that's true.
[3986.26 → 3989.56] I mean, certainly the case that every problem hasn't been solved.
[3989.56 → 4004.28] Although I think it's interesting as, you know, the amount of theoretical work that was done in universities, if you go back and look at, you know, Lam port clocks and all this kind of stuff, where it's all distributed computing stuff being done before we really had enough distributed computing to worry about that.
[4004.46 → 4004.54] Yeah.
[4004.70 → 4005.68] I find that fascinating.
[4005.74 → 4005.92] Yeah.
[4006.00 → 4006.60] It was all this work.
[4006.98 → 4009.80] And then, you know, Google comes along and builds massive things.
[4009.86 → 4013.02] It's like, oh, yeah, we can actually go back and look at all this research that was done.
[4013.02 → 4026.12] But I think people do need to look at the history, but also be kind of free to say, yeah, we can do this because now we have fast enough processes or, you know, enough processes or good enough networks.
[4026.12 → 4026.56] Yeah.
[4026.56 → 4027.00] Yeah.
[4027.08 → 4038.22] When also making it more robust, because I remember, I mean, being very trolled by an Alan Kay interview where he was lionizing how, you know, Unix was perfect in the in, in the seventies.
[4038.22 → 4047.80] And we, you know, how, how is it that we had, you know, a Unix kernel, a complete Unix system with, you know, 10,000 lines of code and, you know, what's, and I'm really thinking like, but I've been in that code.
[4047.80 → 4051.22] And yeah, there was, I mean, it's, it's very important work.
[4051.28 → 4055.22] I don't want to denigrate it, but there were also all sorts of conditions that it simply did not handle.
[4056.20 → 4062.10] And it would, you know, it would toss under very, I mean, if you ran out of processes, the machine would panic, you know?
[4062.12 → 4069.44] I mean, it's like, so like, like, you know, let's, let's take it easy here in terms of like, not everything that's been done since then is, so I don't know.
[4069.50 → 4071.12] I mean, I've got, I'm always of like mixed opinion.
[4071.12 → 4071.74] I agree with you.
[4071.82 → 4076.96] I mean, we've, we've made all this stuff works to the point at which we've managed to give the public supercomputers in their pockets.
[4076.96 → 4084.56] And those machines seem to work somehow, and they don't have to worry about, you know, I know it's running out or any nonsense like that.
[4084.62 → 4086.34] We've made stuff pretty, pretty reliable.
[4086.64 → 4087.64] I agree with you.
[4087.98 → 4089.58] I think it's difficult, right?
[4089.64 → 4099.32] If you're, if you see the perfection of the idea in Unix, but the implementation isn't quite there, it's easy as a program to be like, well, that's just an implementation detail.
[4099.50 → 4100.02] Right, right.
[4100.02 → 4100.34] Exactly.
[4100.70 → 4101.48] We'll get there.
[4101.56 → 4102.10] We'll get there.
[4102.10 → 4109.86] But we booked, but the real step was the structure of the system or the decision that everything's a file or whatever was the decision.
[4110.00 → 4111.94] So I think that's, that's easy.
[4112.02 → 4116.62] But yeah, making stuff actually work in the real world, it's really hard, really hard.
[4116.80 → 4122.64] And so you know actually what I really like as a technology that is very aware of the past, but still very forward-looking is risk five.
[4122.64 → 4131.04] I don't know how much you've gone into the, the kind of the innards of risk five, but I just love the way they have so deliberately learned from everything.
[4131.38 → 4132.04] Yes, I agree.
[4132.12 → 4134.16] I mean, that's one of, that's a fascinating project.
[4134.36 → 4138.70] It's one of those things that I probably wish I had more time to spend messing around with.
[4138.82 → 4139.06] Yeah.
[4139.66 → 4139.88] Great.
[4140.18 → 4145.00] What I just love, they got these tables of like all these mistakes that various architectures have made.
[4145.00 → 4156.60] Because it's like, and it's like all of these historic risk architectures have got these weird warts, you know, and they've kind of gone through and systematically eliminated them, at least in the instructions that architectures.
[4156.72 → 4161.32] I don't think people give enough like credit to past history when they build things.
[4161.38 → 4161.64] Right.
[4161.82 → 4167.52] And I think risk five is a model in that regard, you know, where it's like, Hey, we paid attention to the past, but we're not going to be confined by it.
[4167.58 → 4168.18] I do that.
[4168.26 → 4168.42] Yeah.
[4168.68 → 4168.88] Yeah.
[4168.88 → 4170.30] That's a that's a good way to look at it.
[4170.54 → 4170.74] Definitely.
[4170.74 → 4175.18] So not to fixate too much on the mother of all demos, but I, I was curious, was it actually a demo?
[4175.58 → 4175.72] Yeah.
[4175.80 → 4176.78] And who was in a demo too?
[4177.30 → 4178.06] And it's recorded.
[4178.16 → 4179.00] It's recorded on video.
[4179.16 → 4179.40] Okay.
[4179.44 → 4180.88] So he just recorded it on video.
[4181.18 → 4182.26] No, it was done live.
[4182.60 → 4186.50] So it was, it was done live in San Francisco, I think.
[4186.64 → 4186.78] Right.
[4186.86 → 4190.82] But I mean, so when it says it's recorded on video, I mean, it was, we have a video of the demo.
[4191.40 → 4191.96] Yes, we do.
[4192.16 → 4192.50] We do.
[4192.62 → 4195.38] It's 90, I think it's like an hour and a half, something like that, 90 minutes.
[4195.94 → 4197.26] And there's everything there.
[4197.26 → 4201.88] The mouse is there at video conferencing, real time editing, collaborative, real time editing
[4201.88 → 4203.08] with somebody else who's remote.
[4203.98 → 4207.58] And what was the reaction at the time for, to all this groundbreaking technology?
[4207.90 → 4212.56] I think everyone was, my understanding is that everyone was completely blown away because
[4212.56 → 4216.56] it was, you know, there was networked, and it was all this technology was actually happening.
[4217.12 → 4218.58] And you know, it's 1968.
[4219.12 → 4219.30] Right.
[4219.30 → 4220.80] So this is before park, right?
[4220.86 → 4228.30] This is, this is in the mother of all demos inspires a lot in park and park in turn inspires
[4228.30 → 4229.22] a bunch of the industry.
[4229.58 → 4230.02] That's right.
[4230.02 → 4230.74] This is SRI.
[4231.28 → 4231.64] Right.
[4231.76 → 4233.58] And I think I remember where it was.
[4233.66 → 4234.48] It was somewhere in San Francisco.
[4234.76 → 4234.90] Yeah.
[4234.90 → 4235.54] It was in San Francisco.
[4235.68 → 4236.00] I believe.
[4236.08 → 4237.74] And did this just shock everyone?
[4237.82 → 4239.52] I mean, were there teasers that this was coming?
[4239.68 → 4241.02] Did people know what he was working on?
[4241.22 → 4244.34] You know, it's like, who was it that said, what's the quote?
[4244.40 → 4245.50] Like the future is here.
[4245.52 → 4246.14] It's just well hidden.
[4246.14 → 4249.76] And what are you, what's the, Oh no, it's not evenly distributed.
[4249.96 → 4250.36] That's it.
[4250.40 → 4250.72] That's right.
[4250.80 → 4251.08] It is.
[4251.38 → 4251.56] Yeah.
[4251.92 → 4253.56] And who is that?
[4253.68 → 4255.92] That's a, right.
[4256.02 → 4256.60] Thank you.
[4257.48 → 4261.80] And I kind of feel the same way about like the, you know, folks that were kind of in
[4261.80 → 4265.06] the know knew about that, but it was just like, you know, when we were talking about
[4265.06 → 4269.92] like Tom Lyon was here who would describe going up to park where his brother worked.
[4270.38 → 4274.14] And there was a time in Silicon Valley when like one of his brothers, one of his brothers,
[4274.14 → 4279.68] one of his, one of his 5 million prolific brothers, you would walk into park, and it was like
[4279.68 → 4280.60] walking into the future.
[4281.14 → 4282.88] And a lot of people described that.
[4283.00 → 4283.48] That's cool.
[4283.94 → 4286.92] And, but it was, you know, it was all still, you know, it was in the, in the present.
[4287.00 → 4288.84] I don't know what the analog is for today though.
[4288.96 → 4289.62] You know, what is the.
[4289.76 → 4290.00] Quantum.
[4290.34 → 4292.70] Those people would claim that they were the future.
[4292.78 → 4295.74] I'm just saying, I'm not, I'm not defending it, but you know they were.
[4296.16 → 4297.04] Hey, maybe it is.
[4298.38 → 4299.04] Well, probably.
[4299.18 → 4299.32] Yeah.
[4299.32 → 4303.34] Although my understanding is at the time, some people thought that Engelhardt was a bit
[4303.34 → 4305.04] crazy until he did the demo.
[4305.76 → 4306.10] Oh, interesting.
[4306.48 → 4310.84] I had all these ideas that all this interactive stuff was going to happen and just too wacky.
[4311.26 → 4312.74] It was just too wacky and out there.
[4312.82 → 4315.72] And it was like, you know, drop the mic basically.
[4315.84 → 4316.68] It was like, by the way.
[4316.94 → 4317.12] Boom.
[4317.32 → 4317.48] Right.
[4317.48 → 4321.02] Because any one of those things would be groundbreaking to a certain extent.
[4321.02 → 4322.68] And he's like, oh no, wait, there's more.
[4322.82 → 4323.34] Wait, there's more.
[4323.42 → 4324.04] Yeah, exactly.
[4324.14 → 4326.12] It's like, by the way, we're doing hypertext.
[4326.22 → 4327.34] Now we're going to switch windows.
[4327.34 → 4331.16] Now we're going to do a video conference, and then we'll do real time editing.
[4331.90 → 4335.38] And then I had, I have to believe there's people that were like, oh, this demo's rigged.
[4335.62 → 4337.56] You know, does this actually work?
[4338.02 → 4338.26] Yeah.
[4338.28 → 4340.40] And it did actually work, although it was hell getting it working.
[4340.48 → 4345.42] I remember reading a thing about the it must've been going to probably, you know,
[4345.52 → 4350.14] Bell and asking to get the phone line, you know, the data connectivity between the two
[4350.14 → 4351.14] locations working.
[4351.30 → 4353.30] I think they had to use microwaves, actually.
[4353.62 → 4354.24] Oh, wow.
[4354.30 → 4354.68] That's cool.
[4354.68 → 4359.70] But I mean, it was, it was totally crazy because it was Menlo Park, the San Francisco, if I
[4359.70 → 4360.30] remember well.
[4362.30 → 4363.90] That is, that is amazing.
[4364.36 → 4367.32] Is there a book on the mother of all demos just on that?
[4367.56 → 4367.66] I don't know.
[4367.78 → 4368.32] There should be.
[4368.40 → 4369.22] There really should be.
[4369.28 → 4369.40] Yeah.
[4369.40 → 4370.92] It's kind of amazing that there isn't.
[4370.96 → 4374.94] I mean, it's certainly referred to a lot by the park folks.
[4374.94 → 4377.66] But you can just watch the videos on YouTube.
[4377.80 → 4381.14] If you go an hour and a half, you know, watch a black and white video of somebody making
[4381.14 → 4384.12] a shopping list and editing, you know, online.
[4384.64 → 4385.16] Pretty crazy.
[4385.16 → 4385.54] That's cool.
[4386.22 → 4387.28] It is amazing.
[4387.46 → 4392.72] And in 1968, it's just, it's just stunning.
[4393.10 → 4393.20] Yeah.
[4393.30 → 4394.46] And it's like, where is that?
[4394.56 → 4397.86] Where's the, the, that demo equivalent today?
[4398.80 → 4398.94] Yeah.
[4398.94 → 4400.06] I don't know if it's quantum or not.
[4400.14 → 4402.10] Maybe what's this crazy thing you're doing?
[4402.48 → 4403.82] Drilling holes in people's heads.
[4404.02 → 4404.34] Oh yeah.
[4404.86 → 4405.72] Oh wait, what?
[4405.92 → 4406.06] Fair enough.
[4406.22 → 4406.40] Yeah.
[4406.50 → 4406.84] Hello.
[4407.08 → 4407.88] He has a new company.
[4408.12 → 4409.18] The holes in heads.
[4409.34 → 4409.54] Yeah.
[4410.18 → 4411.36] It's like cerebral implants.
[4411.78 → 4413.34] Your head and connects you to her or something.
[4413.96 → 4415.90] It's like you're racking up your brain to the cloud.
[4416.32 → 4416.46] Yeah.
[4416.46 → 4417.50] They're doing POCs right now.
[4417.60 → 4418.08] Oh my God.
[4418.14 → 4418.26] Yeah.
[4418.44 → 4419.14] You first.
[4419.14 → 4423.54] I don't even know.
[4423.68 → 4424.28] Words fail.
[4424.62 → 4425.36] I mean, come on.
[4425.52 → 4431.52] I mean, it's just, and this is why I think maybe when, when you get these things that
[4431.52 → 4438.32] feel very, like a big leap, sometimes it is hard to differentiate those from the things
[4438.32 → 4440.94] that are leaps that don't actually amount to anything.
[4441.04 → 4446.40] I like the whole, like nanotechnology, there was a so there was a period when nanotechnology
[4446.40 → 4451.22] was absolutely going to be the future and K. Eric Dealer and the gray goo.
[4451.58 → 4454.32] And I mean, John, do you remember all this whole, this whole era?
[4455.30 → 4456.12] Yes, I do.
[4456.20 → 4461.80] And I remember being utterly fascinated by nanotechnology and then Neil Stevenson wrote
[4461.80 → 4464.26] the diamond age and made it seem like it was all coming.
[4464.68 → 4468.14] And it was, yes, I, I really wanted, you know what I really wanted?
[4468.26 → 4471.48] I wanted nanobot shaving cream.
[4471.48 → 4477.50] I wanted to be able to rub tiny robots on my face and have them shave.
[4477.72 → 4480.28] That's terrifying and captivating.
[4480.54 → 4481.00] Oh my God.
[4481.34 → 4485.78] Well, no, and this is the whole, so the nanobot shaving cream, Mike, that's unique to you.
[4485.88 → 4486.56] I didn't, I don't know anything.
[4486.64 → 4486.86] I heard that.
[4486.98 → 4487.52] That's my thing.
[4487.60 → 4488.14] That's my thing.
[4488.16 → 4488.92] That's your thing.
[4489.34 → 4491.68] But the whole, no, this is this whole nanobot idea.
[4491.76 → 4495.56] This is Feynman's idea of the bot that builds the smaller bot.
[4495.56 → 4501.84] And there was an era in the I would say what, late eighties, nineties, when this was a very
[4501.84 → 4503.08] captivating idea.
[4503.70 → 4508.00] And then you kind of realized that like, you know what, this is not coming.
[4508.44 → 4509.84] This is, I need to.
[4509.84 → 4509.96] That's that.
[4510.14 → 4510.70] This book, right?
[4510.84 → 4513.02] Dealer wrote this book called Engines of Creation.
[4513.20 → 4514.66] It was about these machines that make machines.
[4515.10 → 4517.66] And there was going to be this thing called the gray goo, which was like.
[4517.66 → 4518.08] The gray goo.
[4518.28 → 4518.42] Right.
[4518.80 → 4521.94] Over the whole world by making copies of themselves.
[4521.94 → 4526.22] Well, no, but, and, and he would give this very captivating talk about like your demo.
[4526.34 → 4530.94] And he would talk to especially folks in the military industrial complex about, you know,
[4531.18 → 4534.72] a, a cow is a machine that turns grass into steak.
[4535.34 → 4541.08] So based on that, like, why is it not possible for me to turn you into gray goo?
[4541.72 → 4542.92] And yeah.
[4543.00 → 4544.02] So the idea is.
[4544.06 → 4545.08] That doesn't line up though.
[4545.08 → 4551.80] Like, well, well, you know, the admirals for the admirals and the generals, they, they
[4551.80 → 4552.54] got very excited.
[4552.90 → 4553.12] A lot of head nodding.
[4553.26 → 4553.40] Yeah.
[4553.44 → 4554.26] A lot of head nodding.
[4554.58 → 4554.90] Yes.
[4554.92 → 4556.22] It was the it was the 80s.
[4558.44 → 4558.98] It did.
[4559.06 → 4560.12] No, there was some truth to it.
[4560.24 → 4564.46] And I feel that like in nanotechnology, I don't know, John, when did you have the conclusion
[4564.46 → 4566.12] that like, I need to stop waiting for this?
[4566.16 → 4566.76] It's not coming.
[4566.86 → 4568.04] I mean, I think actually.
[4568.40 → 4568.66] Yeah.
[4568.78 → 4569.24] I don't know.
[4569.30 → 4570.86] There are a lot of things I'm waiting for.
[4570.94 → 4575.04] I've stopped waiting for, I've stopped waiting for domestic robots that are of any use.
[4575.04 → 4579.58] And I've stopped waiting for flying cars and jetpacks and, you know, the gray goo
[4579.58 → 4580.82] was along the way, I guess.
[4581.04 → 4581.24] Yeah.
[4581.24 → 4584.46] But the big problem with it, I remember being fascinated by it.
[4584.50 → 4589.62] And then just the thing about, you know, the Drexel thing was, it'll all be done by having
[4589.62 → 4593.34] just a you have a whole load of chemicals, and we'll just assemble stuff out of chemicals.
[4593.34 → 4595.98] And it's like, wow, chemistry is actually really hard.
[4596.06 → 4600.20] And you can't just like link atoms together to make plastic, you know, it just doesn't
[4600.20 → 4600.92] work like that.
[4601.00 → 4603.62] So I think it was around then I was like, this isn't going to happen.
[4603.86 → 4604.00] Yeah.
[4604.12 → 4609.78] And so for me too, it was on when I read Engines of Creation and realizing, well, first,
[4609.78 → 4615.26] I, okay, I, this is, this is probably an overgeneralization, but I do feel that people that want to go by first initial
[4615.26 → 4619.24] name, name, there's a, there's, there's something there.
[4619.34 → 4621.00] There is no, it's like, it's K.
[4621.00 → 4622.58] Eric Dealer, J. Edgar Hoover.
[4623.24 → 4625.02] I mean, there's an E. Howard Hunt.
[4625.14 → 4626.72] There are, there are a bunch of ones that are, anyway, whatever.
[4627.18 → 4631.00] The theory about, you know, serial killers, right?
[4631.12 → 4632.26] They're all having names like that.
[4632.32 → 4633.18] They would have two names.
[4633.70 → 4634.02] Right.
[4634.18 → 4634.54] Yeah, exactly.
[4634.80 → 4636.18] That's actually, that's fair.
[4636.32 → 4636.48] Yeah.
[4636.60 → 4642.22] So there are, so there's something weird that, but honestly, and this is an interesting contrast
[4642.22 → 4646.24] to Babbage because also Babbage also had Babbage had not actually built anything.
[4646.24 → 4648.52] And yet what he was onto was very legit.
[4648.98 → 4649.38] Yeah.
[4649.38 → 4650.78] Eric Dealer never built anything.
[4650.84 → 4657.70] There was nothing, there was no demonstrable system at all demonstrating any of these ideas.
[4657.74 → 4659.58] It was all ideas.
[4659.58 → 4664.26] I mean, and when I realized that I'm like, wait a minute, there's, there's nothing.
[4664.26 → 4669.94] It's not like we can't point to anything that is getting towards what we would call an
[4669.94 → 4670.42] antimachine.
[4670.42 → 4674.40] There's not a micromachine, there's not a micromachine, let alone a antimachine.
[4675.56 → 4677.22] And then, you know, what did we get out of it?
[4677.28 → 4679.32] We got out of it like 3D printers.
[4680.08 → 4681.98] It's not fun, but yeah.
[4682.40 → 4683.12] Yeah, exactly.
[4683.36 → 4689.60] I got to ask you this because I definitely wonder if, you know, we've got the first snowflakes
[4689.60 → 4693.68] of the next AI winter are surely blowing.
[4694.58 → 4694.94] Yeah.
[4695.08 → 4699.36] I mean, I'm not a deep enough expert in this, but it sure feels like it.
[4699.36 → 4699.72] Yeah.
[4699.78 → 4702.94] And please, the lack of expertise, it does never prevent me from shooting my mouth
[4702.94 → 4703.16] off.
[4703.24 → 4705.32] So please do not let it prevent you from.
[4705.66 → 4713.88] But it, I do wonder if if AGI is going to be this generation's equivalent of moon bases
[4713.88 → 4719.06] in flying cars, where you're going to have, you know, when the Gen Zero, the Gen Zero,
[4719.22 → 4723.18] when they grow up, they're going to be like, yeah, the artificial general intelligence that
[4723.18 → 4726.52] I was promised when I was a teenager never arrived.
[4726.72 → 4728.02] I definitely wonder about that.
[4728.36 → 4730.02] Hey, I was promised that too, right?
[4730.10 → 4734.32] The first AI winter, I thought we were going to get, there was going to be, you know,
[4734.38 → 4739.10] expert systems that were going to get so good that they'd replaced doctors.
[4739.10 → 4739.54] That's right.
[4739.54 → 4740.84] All this kind of stuff was going to happen.
[4741.50 → 4744.56] And then I was like, yeah, no, no, that didn't happen.
[4744.82 → 4745.00] It is.
[4745.12 → 4749.24] So it's actually funny that you should mention it about medicine because that, that's exactly
[4749.24 → 4753.04] what my father was actually doing was working and working with another physician in San
[4753.04 → 4756.50] Diego who was using expert systems on medicine.
[4756.50 → 4761.42] And it was interesting what their, they were, there's a lot of value, but they were very
[4761.42 → 4763.60] limited in terms of what they were ultimately able to do.
[4763.66 → 4763.80] Right.
[4763.80 → 4768.90] Well, and then, you know, when IBM is pushed very hard, the idea that Watson is going to
[4768.90 → 4770.18] identify cancer and stuff, right?
[4770.78 → 4772.54] So it's the same stuff again.
[4773.48 → 4775.46] So I want to float past an idea for you.
[4775.56 → 4783.66] I believe that, um, that we in, in computing to prevent the further seasonal cycles in AI,
[4784.20 → 4789.68] AI is hereby ordered to change its name to automated pattern recognition.
[4789.68 → 4794.84] It may continue to exist as a discipline, but it must change its name because its very
[4794.84 → 4797.84] name is, is leading to this seasonality.
[4798.04 → 4798.74] I see.
[4799.00 → 4799.44] I see.
[4799.54 → 4800.80] They're overselling it basically.
[4801.08 → 4802.70] They have to oversell it because it's in the name.
[4803.28 → 4803.52] Yeah.
[4804.36 → 4805.56] I also, okay.
[4805.60 → 4810.58] I think that flying cars are not exactly dead by the way, because like, wait, you said this
[4810.58 → 4817.22] twice now and with electric VTOL and the flying taxis, if that works out, although it probably
[4817.22 → 4817.50] won't.
[4818.26 → 4818.70] Okay.
[4818.70 → 4818.82] Maybe.
[4819.40 → 4820.14] I, I, maybe.
[4820.44 → 4821.88] I'm just saying, I'm just saying.
[4821.88 → 4826.84] I mean, honestly, I, growing up, I was definitely promised flying cars, protein pills to eat
[4826.84 → 4827.44] everything.
[4827.96 → 4829.96] Um, all this domestic robots.
[4830.10 → 4830.42] Yeah.
[4830.50 → 4835.18] And literally the future has turned out to be trying to keep all my batteries charged.
[4837.32 → 4837.72] Great.
[4837.72 → 4839.24] It's like, great.
[4839.84 → 4840.68] That's what I got.
[4840.94 → 4842.42] I got, I need to charge stuff up.
[4842.54 → 4843.68] There are inventors to all that.
[4843.74 → 4845.52] Just saying it's just implementation details.
[4845.86 → 4846.96] It is just implementation.
[4847.04 → 4847.64] We're almost there.
[4847.64 → 4848.96] We're almost there.
[4849.10 → 4849.54] Yeah.
[4849.54 → 4849.62] Yeah.
[4849.64 → 4855.44] But I think the yeah, I think just that because I, I grew up in the past that John did where
[4855.44 → 4857.22] we were really promised flying cars.
[4857.32 → 4857.98] Like the Jet sons.
[4858.86 → 4859.32] The Jet sons.
[4859.32 → 4864.86] It's actually the if you really want to capture the zeitgeist, it is that final scene in back
[4864.86 → 4865.28] to the future.
[4865.28 → 4865.62] Back to the future.
[4865.74 → 4866.34] I was going to say, yeah.
[4866.54 → 4866.94] Yeah.
[4867.58 → 4870.50] That is what captures that eighties' zeitgeist.
[4870.64 → 4871.44] So what the future is going to be.
[4871.44 → 4871.60] We don't need roads.
[4871.74 → 4873.78] That's very different from the electric heat also.
[4874.28 → 4874.58] Yes.
[4874.92 → 4876.00] This is basically a helicopter.
[4876.48 → 4876.54] Right.
[4876.62 → 4877.62] Also moon bases.
[4877.78 → 4879.26] Frankly, I was promised moon bases.
[4879.32 → 4879.60] Yes.
[4880.04 → 4880.94] I was promised moon bases.
[4881.30 → 4882.26] And it's now Mars bases.
[4882.42 → 4882.72] It's fun.
[4882.84 → 4883.88] And I built them with Legos.
[4884.06 → 4884.96] Mars bases are coming.
[4885.94 → 4886.88] Mars bases are.
[4887.00 → 4887.20] Yeah.
[4887.44 → 4887.60] Yeah.
[4887.70 → 4888.48] Three flights a day.
[4889.08 → 4889.92] Just sit tight.
[4890.44 → 4890.64] Yeah.
[4890.70 → 4892.72] Is that for people who've had their skulls?
[4892.84 → 4894.48] Had holes drilled in their skulls?
[4895.12 → 4898.66] So actually your Tesla is going to drill into your skull and fly you to Mars.
[4898.66 → 4900.44] It's going to be a lot of latency back to earth.
[4900.80 → 4901.30] All right.
[4901.32 → 4903.68] Well, with that dystopian view of the future.
[4904.56 → 4905.94] John, thank you so much.
[4906.06 → 4907.44] This has been so much fun.
[4907.44 → 4908.48] This has been so much fun.
[4908.48 → 4913.20] And such an interesting tour through the history of computing.
[4913.70 → 4914.70] Thanks very much.
[4914.82 → 4915.72] Love you're chatting with me.
[4915.78 → 4916.70] Good luck with the company.
[4917.32 → 4918.04] Thanks, Joe.
[4918.44 → 4918.92] Thanks.
[4919.12 → 4919.32] All right.
[4919.86 → 4923.90] You've been listening to On The Metal, tales from the hardware software interface.
[4924.32 → 4927.62] For show notes, to learn more about our guests, or to sign up for our mailing list,
[4928.02 → 4930.34] visit us at onthemetal.fm.
[4930.78 → 4933.20] On The Metal is a production of Oxide Computer Company.
[4933.20 → 4936.58] It is recorded in the Oxide Garage in Oakland, California.
[4936.58 → 4940.22] To learn more about Oxide, visit us at oxide.computer.
[4940.68 → 4943.70] On The Metal is hosted by me, Brian Cantwell, along with Jess Fri sell.
[4943.92 → 4946.36] And we are frequently joined by our boss, Steve Tuck.
[4946.60 → 4950.50] Our original and awesome theme music is by J.J. Wrestler at Pollen Music Group.
[4950.76 → 4954.46] You can learn more about J.J. and Pollen at pollenmusicgroup.com.
[4954.84 → 4958.64] We are edited and produced by Chris Hill and his crew at Humble Pod.
[4959.12 → 4963.22] From Jess, from Steve, from me, and from all of us at Oxide Computer Company,
[4963.50 → 4964.84] thanks for listening to On The Metal.
[4966.58 → 4996.56] On The Metal.
[4996.76 → 4997.42] Uh, 1953otle.
[4997.42 → 4997.70] Yeah!
[4997.70 → 4997.78] On The Metal.
[4997.78 → 4998.34] It's over 38 industry.
[4998.34 → 4998.44] Uh, возвращ token.
[4998.62 → 4999.04] Coming soon.
[4999.20 → 4999.38] body BMW.
[4999.46 → 4999.76] On The Metal.
[4999.76 → 4999.80] On The Metal.
[5000.74 → 5001.90] On The Metal.
[5001.90 → 5003.22] On The Metal.
[5007.20 → 5007.46] On The Metal.
[5008.20 → 5021.12] On The Metal.
