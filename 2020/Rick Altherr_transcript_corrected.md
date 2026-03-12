[0.00 → 14.42] Welcome to On The Metal, tales from the hardware software interface.
[14.64 → 18.52] I'm Brian Cantwell. With me, as always, is Jess Frizzell. Hi, Jess.
[18.82 → 19.34] Hi, Brian.
[19.92 → 23.84] You know, what's so hysterical about that? You know, I can't say my name without you.
[24.00 → 26.74] It was mostly because you told me to say, hi, Brian.
[26.74 → 29.38] So then I was like thinking of something else to say really fast.
[29.38 → 32.28] You kept saying hello as opposed to like, sounds like-
[32.28 → 33.08] Yeah, it's like hello. Hey.
[33.24 → 33.40] All right.
[33.46 → 34.48] I thought it was a dramatic intro.
[34.70 → 38.92] All right. So, and speaking of whom, Steve Tuck also with us, our boss. Steve, welcome.
[39.30 → 40.12] Glad to be invited.
[40.34 → 41.26] Be on your best behaviour.
[41.66 → 41.86] Always.
[42.30 → 44.90] And Jess, you want to introduce our esteemed guest?
[45.30 → 50.02] Yeah. So our guest today is Rick Alter. He was one of the first people who I met, honestly,
[50.18 → 55.14] in the Firmer space. And I've learned a lot from him over just the past few months.
[55.14 → 60.86] And most recently, he found a vulnerability in a lot of super micro BMCs.
[61.16 → 62.52] A lot of BMCs.
[62.74 → 67.76] Called USB Anywhere. So do you want to maybe tell us a little bit about that?
[68.22 → 74.62] Sure. So hello. Yeah. USB Anywhere was a fun one in that I work for a company now that
[74.62 → 79.96] explicitly looks for security vulnerabilities in system firmware and produces an enterprise
[79.96 → 81.96] product around this. So like, this is my day job now.
[81.96 → 85.66] I mean, that's a target-rich environment, as Don Rumsfeld would say.
[85.96 → 90.70] It definitely is. And, you know, things have been getting slightly better in the firmware
[90.70 → 94.88] scene. I'm sure we'll talk about that in more depth in a bit. But, you know, USB Anywhere
[94.88 → 102.32] was really started from just me saying, I know that this feature exists where I can mount a ISO
[102.32 → 108.18] image as a CD-ROM drive on a server over the internet. I wonder how that works. And did they do it
[108.18 → 114.22] correctly? And it turns out, no, they didn't. And it was done in probably one of the most dangerous
[114.22 → 119.70] ways possible. So after doing a bunch of research about a lot of reverse engineering, working with
[119.70 → 125.42] Supermicro to get fixes developed, and announced that and give a talk about it at OSF.
[125.68 → 128.10] A great talk. OSF, the open source firmware conference.
[128.18 → 128.42] Right.
[128.42 → 129.50] Loved it. Great conference.
[130.04 → 135.80] And also, you know, with that revealed that I had actually scanned the internet and found 47,000
[135.80 → 139.08] servers just sitting on the internet waiting to be exploited via this.
[139.42 → 142.70] I mean, that is 47,000 BMCs on the internet.
[143.02 → 143.18] Right.
[143.32 → 146.00] I mean, that is like we put the brain stem on the internet.
[146.76 → 151.88] Yeah. Yeah, exactly. It's, you know, here's your best practice. Here's what people really do.
[151.88 → 156.82] I got in contact with some of the larger network operators that had these on there, and everyone
[156.82 → 161.84] was just as mystified as I was. It's, no one clearly knew why these were on the internet,
[162.10 → 163.66] and, but everybody knew they shouldn't be.
[163.98 → 167.26] Was that number higher than you thought it was going to be? That is such an astonishingly
[167.26 → 167.70] high number.
[168.12 → 172.50] It's somewhere in the range that I was expecting. There have been people in the past that have
[172.50 → 176.72] done similar scans looking for BMCs, and they've found significantly higher numbers in
[176.72 → 178.28] the past. So this is actually a reduction.
[178.68 → 179.40] It's the good news.
[179.52 → 179.88] Yeah.
[179.88 → 184.36] Yeah. Were these highly clustered, or was it distributed and kind of everyone had one?
[184.80 → 188.46] It kind of came in lumps. Like if you broke it down geographically, the highest density
[188.46 → 194.28] was in the United States, but then they were scattered all over Europe, Asia, South America.
[194.52 → 198.72] Fairly well distributed, but definitely concentrated in the US. There were a couple of network operators
[198.72 → 201.34] that were very heavily affected by it.
[201.50 → 201.72] Interesting.
[201.76 → 206.66] And I got in touch with them directly to say, look, this is a real problem. You should figure
[206.66 → 209.86] out who these machines are owned by and do something about it.
[209.88 → 214.44] I mean, you seem like a very law-abiding person, but it must have been tempting to be like,
[214.68 → 221.10] wow. I mean, especially to go through the 47,000, like, do I have any of my enemies list
[221.10 → 222.20] on here, by any chance?
[222.20 → 228.02] I mean, we did look up as to, part of after getting 47,000 IP addresses, right? Because
[228.02 → 233.22] that's really what happened. I scanned the entire IPv4 address space. And so I only knew the IP
[233.22 → 236.76] addresses initially. And so trying to do like reverse DNS lookups and then look up what
[236.76 → 242.18] autonomous system they're attached to and things like that, trying to narrow down who it was,
[242.36 → 247.12] kind of taking a peek through it and going, is there anybody that I like know personally or that I,
[247.12 → 251.00] you know, have some interaction with that company that I can talk to them about this.
[251.32 → 255.70] And thankfully, like it wasn't anybody I knew, but like, as I said, there were some very large
[255.70 → 259.30] network operators that were affected by it. And it was just terrifying.
[259.56 → 263.64] You know, thankfully they got in touch and asked good questions about how to fix it.
[263.80 → 267.42] So how did you, I mean, I've got a question about how you actually found that vulnerability.
[267.60 → 270.78] What was the process of reverse engineering for you? I mean, you obviously you're going into this
[270.78 → 273.70] piece of functionality thinking, if this hasn't been implemented properly,
[273.70 → 277.54] there's likely a vulnerability here. What was your tool set, your mindset? How did you go about
[277.54 → 281.42] doing that? So I actually gave a talk about this at Mountain View reverse engineering group recently.
[281.76 → 286.86] So unfortunately those usually aren't recorded, but the main thing was I knew what the external
[286.86 → 293.50] functionality was and having been in the BMC space for quite a while developing or being part of early
[293.50 → 299.86] part of open BMC and developing BMC firmware, I kind of knew what the capabilities of the chip actually
[299.86 → 303.66] were. And so it was really just a question of what was all the in-between, like,
[303.70 → 308.28] if I knew on the host side that this looks like a USB device and I know that the hardware,
[308.86 → 316.10] like the BMC SOC actually has the ability to look like a USB device, practically any USB device,
[316.24 → 320.80] then clearly that's the feature that's being used here. What does the full stack look like?
[321.12 → 326.60] And that's going to be split between the firmware actually on the BMC and the Java application
[326.60 → 329.56] that was running on my laptop, you know, my remote workstation.
[329.56 → 335.78] And I'm one to really dig into protocols, like that's sort of my thing is getting into,
[335.78 → 340.50] you know, serialized binary formats. So I just grabbed the packet capture of the network and
[340.50 → 350.04] looked to see what was going on. And as soon as I saw a TCP 623, which was the port that this service
[350.04 → 356.58] was running on, and I saw strings of USB in them, you know, it was just sort of like a telltale,
[356.68 → 362.64] like something is very wrong. The actual making a proof of concept was the more difficult part.
[362.76 → 369.30] So like the early that there is something wrong was, you know, an hour of work, and it really involved
[369.30 → 376.08] Wireshark, and that's about it. Actually understanding the protocol enough to implement my own client
[376.08 → 383.50] so that I could then use it in malicious ways. That involved getting the firmware updates,
[383.74 → 390.80] unpacking it. BMCs are often a Linux-based system on an ARM processor. And so you can just unpack the
[390.80 → 396.38] file system and start opening binaries and things. And then using tools like Hydra to actually
[396.38 → 400.46] decompile the binaries and start looking through how do they actually work.
[400.46 → 408.06] This is presumably an A-speed 2400, 2500? Yes. Well, some of them. Some of them were A-speed.
[408.28 → 413.60] Some of them were Puritan. Oh, really? Wow. Older Puritan. Interesting. I have a slightly
[413.60 → 420.30] off-topic question. What is your favourite computer that you've ever owned and why? Oh, see, you added
[420.30 → 426.32] that I ever owned. Well, okay. That makes it hard. Or, you know, came into contact with.
[426.92 → 429.42] Jess is looking for a love story. Is that a fair statement? I am.
[429.42 → 432.88] Well, see, so- She wants to know when you first fell in love with a computer.
[433.10 → 441.90] So my love for a computer would definitely be the Cray, the large circular Cray computers.
[441.94 → 445.32] With the seats? Yeah, like the AMP? Like a Cray YMP1?
[445.54 → 448.00] Yeah, yeah. Wow. The seats are cool.
[448.10 → 455.14] How? Okay. And it's interesting that I've actually got to sit on one. Like, I mean,
[455.14 → 456.76] these are museum pieces. Right. Yeah, exactly.
[457.18 → 459.20] Okay, this is not a home computer. No.
[459.20 → 466.30] No, no, no, no, no. No. They actually show this in the movie Sneakers, right? Or a related model.
[466.84 → 473.00] But yeah, so the Deutsche's Museum in Munich actually has one, and it's just out there. And they're like,
[473.06 → 478.70] yes, you may sit on it and enjoy the machine. So I've actually had a discussion with my wife
[478.70 → 481.44] about whether we can incorporate this into the decor at home.
[482.14 → 482.88] How did that go?
[482.88 → 486.90] Yeah. She actually worked with me on it. We found a location that it would work if I could actually
[486.90 → 492.46] find one. So I'm open for it. If somebody has one that would like to sell one, please get in touch.
[492.74 → 498.30] And is your wife actually interested in this thing? Or does she just, is her love for you that
[498.30 → 502.62] unconditional that she's willing to tolerate a Cray supercomputer around the house?
[502.62 → 505.82] I think it's more, she can appreciate the aesthetic.
[506.20 → 509.88] There you go. It actually, the aesthetic, I mean, if people haven't seen a picture of it,
[509.94 → 511.04] they should. It is.
[511.14 → 511.26] It's cool.
[511.44 → 514.82] It looks like a canonical supercomputer. It looks very bad.
[514.82 → 516.42] It looks like 2001 Space Odyssey.
[517.14 → 519.12] It does. Steve, you have ever seen a photo of these things?
[519.26 → 521.70] Well, I asked if it was a home computer, so I think the answer is no.
[521.70 → 525.46] No. They're cylindrical. So they-
[525.46 → 527.10] Well, they make a letter C from above.
[527.62 → 528.38] Did they?
[528.52 → 528.84] Interesting.
[528.84 → 530.78] God, Seymour. Oh, Seymour.
[530.90 → 532.36] Oh, that makes so much sense.
[532.36 → 536.10] I did not actually know that. I'm embarrassed to say I did not know that. Yeah. And have
[536.10 → 537.26] you ever programmed one of those machines?
[537.32 → 539.06] Oh, no. I've never even seen one powered up.
[539.16 → 542.60] Okay. So it's just, it is, for you, the Cray is purely the aesthetic.
[542.86 → 546.24] Yeah. Oh, yeah. Well, I mean, there's a bunch of aspects to it. Like when you get
[546.24 → 551.38] into the details of how it actually works and the intricacy of design internally. I mean,
[551.38 → 552.14] they're fascinating.
[552.24 → 552.86] They are amazing.
[553.04 → 557.88] It would be completely pointless to have one that you powered up and tried to use these
[557.88 → 562.28] days. I mean, it would be fun from a nostalgia perspective, but it's hard to justify the
[562.28 → 563.98] power budget to run one of those.
[564.12 → 568.64] You also just have to love the fact that Seymour Cray did not believe in SMP. It's like
[568.64 → 572.34] did not believe that God intended multiprocessors. He's like, no, we are going to make this single
[572.34 → 575.04] processor bigger and faster. Get out of my way.
[575.30 → 576.08] And put seats.
[576.48 → 577.02] And seats.
[577.52 → 579.22] Just in case you want to like to sit and watch it.
[579.36 → 581.24] Oh, no. There's, and his, I don't know if you're, if you're,
[581.24 → 587.52] his machines from CDC, like the 1604 to the 6600, amazing machines. Now he was a ridiculously
[587.52 → 589.18] amazing guy.
[589.58 → 594.36] Now in terms of machines I've owned, probably the best machine I ever had, or my favourite
[594.36 → 599.60] was I had a deck station or sorry, an alpha station. So it was, it was still branded digital,
[599.74 → 600.68] but it had an alpha station.
[600.80 → 604.02] Nice. What operating system did you run on the alpha station?
[604.18 → 608.44] Well, see, interestingly enough, I got this at a time when I was actually administrating
[608.44 → 609.06] True64.
[609.62 → 610.56] Ooh, there you go.
[610.66 → 612.98] So, so that was my, like my day job.
[613.20 → 615.52] True64 without the E, there is no E in True64.
[615.56 → 616.68] There is no E in True64.
[616.92 → 617.62] T-R-U.
[617.82 → 620.22] T-R-U 64. It sounds like a pack of like cigarettes.
[621.36 → 624.62] It's like, are those, do you have any True64 lights, please?
[624.88 → 626.72] They were very much ahead of their times in branding.
[626.72 → 627.58] They were.
[627.76 → 628.24] They were.
[628.38 → 628.78] Yes.
[629.20 → 630.48] True.ly 64.
[631.46 → 631.90] Yeah.
[632.00 → 636.66] So I had, I had that at home and, you know, interesting thing with the that generation
[636.66 → 640.26] of alphas is you could run True64, you could run Windows NT.
[640.38 → 640.78] Yes.
[641.26 → 641.64] Yes.
[641.66 → 644.10] Which was always a little awkward and interesting.
[644.72 → 644.88] Yes.
[644.88 → 645.94] You could run Windows NT.
[646.08 → 650.32] Well, in the NT, you could run NT on, this was the era that NT was going to be everywhere.
[650.60 → 650.86] Right.
[651.04 → 652.30] And they ported it to the Alpha.
[652.72 → 652.90] Yep.
[653.08 → 654.38] Which was an amazing CPU.
[654.72 → 656.72] And the they also had.
[657.18 → 657.80] Go on.
[658.20 → 658.60] Spark.
[658.82 → 659.10] Yes.
[659.18 → 659.44] And.
[659.70 → 662.04] Oh, and what was the other?
[662.04 → 662.62] Oh, they had PowerPC.
[662.82 → 663.38] They had PowerPC.
[663.70 → 664.56] There's another ISA.
[664.74 → 665.22] And MIPS.
[665.54 → 666.28] Very good.
[666.36 → 666.64] MIPS.
[666.88 → 667.04] Nice.
[667.04 → 667.30] Okay.
[667.60 → 668.70] So I had.
[668.70 → 669.10] You know what's really sad?
[669.18 → 672.28] I had to think of the actual folder structure inside the installer.
[672.56 → 673.64] That's, that's very good.
[673.82 → 679.36] I, the only reason that I, that I had to have NT on MIPS on the mind is because back in
[679.36 → 685.36] the day, the Palo Alto Goodwill was a glorious place to go because you'd go into the t-shirt
[685.36 → 691.10] bin and for a nickel, you could buy corpses effectively because everyone would get these,
[691.16 → 694.18] all these t-shirts for various initiatives, and then they would give them away.
[694.50 → 698.04] So I, for, I think it was actually 25 cents, not a nickel.
[698.04 → 706.18] I bought a t-shirt from SGI that had the top 10 reasons to run NT on MIPS on the back.
[706.78 → 707.10] What?
[707.30 → 707.98] Like listed.
[708.14 → 710.30] And the reasons, this is not sophisticated ad copy.
[710.54 → 713.26] I think number five was Spark Shark.
[713.64 → 716.14] It was just like, I mean, come on.
[716.70 → 718.70] So SGI made these shirts.
[718.86 → 723.26] SGI made these shirts because SGI was banking on SGI, Silicon Graphics.
[723.26 → 729.48] Um, I mean, I know Rick knows this because he's dropping NT on MIPS, but it's crazy.
[729.66 → 733.78] I mean, it's just like how, this is one of these things you wonder how many people ran
[733.78 → 734.68] NT on MIPS?
[735.00 → 739.54] Oh, I, I mean, I've not encountered many people who ran NT on alpha, and I'm pretty sure that
[739.54 → 740.48] was much more common.
[740.72 → 741.02] Yes.
[741.44 → 745.00] When you had NT on all these different platforms, one of the issues was the binary compatibility,
[745.28 → 745.46] right?
[745.50 → 749.20] It's still, if you got an application, it had to be for that specific architecture.
[749.20 → 749.44] Right.
[749.44 → 752.32] But on the alpha, they had a program called FX32.
[752.58 → 757.18] So you could take an x86 binary, drop it on FX32, and it would convert it to run on,
[757.18 → 758.06] on alpha.
[758.22 → 762.18] And this is at a time when alpha is so much faster than x86 that it may have been faster
[762.18 → 763.28] than x86 to do that.
[763.60 → 764.94] It may have been.
[765.04 → 768.14] I, you know, I never actually got around to playing with NT on it.
[768.20 → 770.98] I just, I know all the details and I looked into how it worked.
[771.02 → 776.02] And, uh, yeah, it, it actually took me like six months to acquire the correct RAM to boot
[776.02 → 776.58] the machine.
[776.58 → 780.96] And true 64, if I'm, that's an ILP 64 kernel, right?
[781.08 → 781.30] Yes.
[781.56 → 781.72] Yeah.
[781.80 → 783.68] So I, so integers were 64 bit.
[783.86 → 786.00] It's like, that's going to break some software.
[786.36 → 789.16] And that was not a good approach as it turns out.
[789.22 → 791.98] I think we, humanity went a different direction on that.
[792.06 → 793.00] Went to LP 64.
[793.68 → 794.16] That was great.
[794.20 → 795.40] So you, you own that box?
[795.64 → 796.34] Uh, not anymore.
[796.50 → 798.00] I had that for quite a while.
[798.10 → 798.58] That's dope.
[798.66 → 799.30] Is that as sufficient?
[799.40 → 801.04] That's a good answer.
[801.22 → 803.20] I mean, I wanted a love story and we got two.
[803.40 → 803.92] We got two.
[804.16 → 805.78] Are you counting NT on MIPS as a love story?
[805.78 → 806.42] I don't think that one counts.
[806.42 → 806.58] No, the Cray.
[806.84 → 807.88] Oh, the Cray got away.
[807.96 → 809.52] The one that got away and the one that he had.
[809.62 → 809.88] Yeah.
[810.60 → 813.90] I found a Cray, by the way, sold in 2002 for $45,000.
[814.58 → 816.66] See, I mean, that's a worthwhile investment.
[816.80 → 816.92] Yeah.
[817.28 → 821.48] I feel there is a lost art of making computers as furniture.
[821.78 → 824.04] It's clearly something that needs to come back.
[824.08 → 824.56] It does.
[825.38 → 827.52] Maybe there's something that the Amish could pick up.
[827.66 → 830.74] You know, they seem to, they've got the furniture or craftsmanship.
[830.74 → 833.32] They don't, they distinctly don't like power.
[833.52 → 836.58] You know, but they're willing to resell people what they want.
[836.66 → 837.78] I think that they should pick this up.
[837.82 → 838.88] I think this should be an Amish thing.
[839.42 → 844.22] I'm saying they should buy old computer gear and, you know, put some niche.
[844.46 → 844.68] Nice.
[844.92 → 845.36] A little niche.
[845.60 → 845.84] All right.
[846.26 → 846.92] I'd buy it.
[847.38 → 851.58] Can I ask one question back to the BMC exploits?
[851.74 → 851.88] Yeah.
[851.88 → 852.86] Or just the vulnerability.
[853.28 → 857.54] So with 45,000 hanging out on the internet, seven, right?
[857.58 → 858.26] 47,000.
[859.08 → 861.60] How vulnerable is someone at that point?
[861.66 → 863.22] Like, is this easily exploitable?
[863.36 → 863.62] I know.
[863.68 → 864.02] Oh my God.
[864.04 → 865.52] I almost spit up Diet Coke under my mic.
[865.86 → 868.68] How vulnerable is someone with a BMC on the internet?
[868.96 → 874.24] I know it's like, you know, hanging wires into water, but I mean, is it easy?
[874.34 → 874.86] Go ahead, Rick.
[874.86 → 878.64] How vulnerable am I buy hanging my BMC out on the internet?
[879.50 → 880.62] Oh, so many ways.
[880.62 → 886.32] I mean, the thing is that like BMCs fundamentally were designed in the 90s.
[886.96 → 893.32] And a lot of the standards that are implemented around BMCs actually never evolved much past the early 2000s.
[893.80 → 900.32] And so a lot of the what you see today as the state of the art is actually things like PMI version two,
[900.48 → 904.90] where according to the standard, you have to support things like no authentication.
[904.90 → 906.80] Like it's, it's a required mode.
[906.94 → 908.00] Can't turn that off.
[908.00 → 913.30] The only mandated ciphers are all things that are, have known weaknesses.
[913.84 → 920.14] And ultimately the PMI implementers forum, I forget what the actual standards organization is.
[920.18 → 922.10] They're like, we're just not going to support this anymore.
[922.10 → 927.62] So there's this new thing called Redfish that isn't actually done yet, but the spec is there.
[927.72 → 929.00] So you should just do that instead.
[929.80 → 936.98] But what it means is that pretty much any BMC that gets put on the internet today is, it's terrible.
[937.62 → 938.06] There are-
[938.06 → 938.66] You're walking right into-
[938.66 → 942.88] Well, also you're, you're talking about the vulnerabilities absent the actual vulnerability that you found.
[942.88 → 943.46] Yeah, yeah.
[943.48 → 944.24] I mean, it's a reminder.
[944.52 → 944.68] Yeah.
[944.78 → 953.00] Like Rick found a vulnerability in which, and like, if your BMC gets owned by someone who's sophisticated, you are done.
[953.88 → 954.28] Yeah.
[954.62 → 960.72] I mean, it's, it's also hard to get at yourself a guarantee about, have I actually removed the exploit from this machine?
[960.72 → 961.04] Right?
[961.14 → 965.32] Like you can maybe ref lash the BMC, but what else has been contaminated on the system?
[966.48 → 974.80] So when you start working through firmware security and everything, it gets into these situations where at what level do I just write off the hardware and, and feed it through a shredder?
[974.94 → 975.04] Yeah.
[975.06 → 980.46] I mean, Rick is saying it gently, but he's saying if Rick owns your BMC, you got no way of getting him out.
[980.92 → 982.28] I mean, you got to pulp the machine.
[982.36 → 983.86] If you are a sophisticated actor.
[984.30 → 984.62] Yeah.
[984.98 → 985.16] Yeah.
[985.28 → 990.32] I mean, a lot of folks wouldn't like, that's, that's hard to justify as a business model, right?
[990.32 → 990.92] Oh yeah.
[991.18 → 991.74] Like, absolutely.
[991.90 → 993.08] It's criminal almost certainly.
[993.22 → 1000.74] So people are going to say, well, if this level of attack happens, like I'm, I'm just going to do these things to recondition it and call it good.
[1000.88 → 1007.74] But yeah, I mean, this is kind of what my research is, is looking at ways that you can own the machine and at deeper and deeper levels.
[1008.08 → 1016.16] But with BMCs, because of the way the standards are written, because of the practices in that era, ultimately sort of the stagnation in that space,
[1016.16 → 1022.68] you see things like machines that are shipped with a default username and password for the BMC where it's admin, admin.
[1023.38 → 1027.08] And the expectation is that you will change it, but there's no enforcement on that.
[1027.18 → 1028.30] Or root Calvin, right?
[1028.72 → 1031.04] Root Calvin is, is the Dell Dirac one.
[1031.16 → 1031.24] Yeah.
[1031.34 → 1032.08] Who is Calvin?
[1032.64 → 1033.24] Do we know this?
[1033.44 → 1033.72] No.
[1033.90 → 1034.68] Calvin and Hobbes.
[1035.02 → 1035.68] Is that what that is?
[1035.72 → 1036.20] No, I don't know.
[1036.24 → 1036.88] I just made that up.
[1037.38 → 1037.70] Yeah.
[1037.70 → 1040.08] I, it's a it's a long-lost mystery.
[1041.46 → 1049.34] But at least some of the vendors like HPE are starting to do things like generate random eight character passwords for each machine.
[1049.34 → 1051.20] And so each machine comes with a password.
[1051.36 → 1057.34] But one of the things I also mentioned at the, the talk at Open-source Firmware Conference was like,
[1057.42 → 1063.30] you can rent machines with massive amounts of GPUs and run password crackers on them.
[1063.30 → 1069.90] And so like, I actually have two HPE machines in my lab, and they have the default passwords and I didn't actually know what they were.
[1070.34 → 1074.52] So I ran a password cracker across all the BMC passwords.
[1074.92 → 1078.88] And, you know, those took a little bit longer, but we're talking like 20 hours.
[1079.42 → 1085.74] So, I mean, there are so many different ways that you have to have done things right to make sure that somebody isn't getting into your BMC.
[1085.82 → 1090.46] And then you look at things like USB Anywhere where I didn't need any credentials.
[1090.46 → 1099.60] The, you know, one of the failures found was actually the ability to just use the service as an existing user without actually logging in at all.
[1099.86 → 1100.62] Absolutely terrifying.
[1100.98 → 1102.92] And, and this is, it's the brain stem of the box.
[1103.00 → 1104.04] This controls everything.
[1104.28 → 1105.84] So can I ask you, you mentioned Redfish.
[1106.10 → 1110.26] Jess, you and I both did a very good job of not exclaiming anything when you said Redfish.
[1110.50 → 1112.24] I was more chill than you were.
[1112.74 → 1113.04] Okay.
[1113.20 → 1114.92] Now you're reflecting that back on me.
[1114.98 → 1115.14] Fine.
[1115.58 → 1117.06] Redfish does drive me crazy though.
[1117.34 → 1118.58] I mean, is this just me?
[1118.58 → 1124.32] I think because Redfish says, hey, the way we're going to manage these BMCs is we're going to hang them out over the internet.
[1124.62 → 1127.46] And then we discover vulnerability, and it's like, or we're hanging them out over the network rather.
[1127.88 → 1129.60] And then we discover any of these vulnerabilities.
[1129.60 → 1132.96] And it feels like the vendors say like, well, you shouldn't have had your BMC hanging out over the network.
[1133.04 → 1135.08] It's like, you told me to do that, to take advantage of this functionality.
[1135.60 → 1135.70] Yeah.
[1135.74 → 1137.20] There's sort of this back and forth, right?
[1137.22 → 1141.66] So keep in mind that PMI was created by Intel, like I said, back in the nineties.
[1142.70 → 1144.52] No standards have intelligent in the name.
[1145.00 → 1145.28] Sorry.
[1145.56 → 1146.20] It was the nineties.
[1146.40 → 1147.16] I guess it was the nineties.
[1147.16 → 1147.88] Does that feel intelligent?
[1147.88 → 1150.28] It's never going to feel intelligent in retrospect.
[1150.64 → 1153.52] But in the nineties, it was intelligent.
[1153.68 → 1155.08] I'm not sure if it was intelligent in the nineties.
[1155.42 → 1159.48] The nineties, there were, anyway, maybe we had the standards of like NT on MIPS.
[1159.58 → 1160.00] It was intelligent.
[1160.26 → 1160.40] Sorry.
[1161.86 → 1162.22] PMI.
[1162.46 → 1162.88] I'm sorry.
[1163.24 → 1163.50] Yeah.
[1163.74 → 1169.62] So with Redfish, it's actually being developed from DMTF, which is a proper standards organization,
[1169.62 → 1175.14] but it kind of suffers the same fate, which is your have a standards group that meets and as
[1175.14 → 1179.48] a committee amongst many different companies, they develop the standard for what it should
[1179.48 → 1183.64] be able to do as far as system management, but they don't actually produce a reference
[1183.64 → 1185.34] implementation of this, right?
[1185.34 → 1188.22] They publish the spec, and then they wait for people to actually implement it.
[1188.22 → 1193.30] So Redfish is actually something where it's been around for years, at least five.
[1193.66 → 1196.18] Only now are implementation starting to show up.
[1196.28 → 1199.54] And if you look at what the state of the art was when they began the standards process,
[1199.72 → 1203.72] it was clear that they just sort of took the checklist of where the industry like had
[1203.72 → 1210.72] gone or where the rest of computing had gone to microservices and RESTful APIs and
[1210.72 → 1211.42] things like that.
[1211.42 → 1216.08] And they were looking at the pitfalls of PMI, where most of the issues with PMI were actually
[1216.08 → 1219.28] around the security model and the data interchange.
[1219.64 → 1222.92] Like you had to write, it was all a custom binary format.
[1223.60 → 1227.86] So on one hand, it's like, okay, I understand you're trying to solve the problem by moving
[1227.86 → 1231.26] towards standardized interfaces that everybody's like well vetted.
[1231.82 → 1236.64] But on the other hand, now my BMC, I mean, it was going to run an HTTP server anyway, but
[1236.64 → 1238.14] now I have to run a JSON parser.
[1238.38 → 1240.78] There's a whole host of issues that that opens up.
[1240.78 → 1246.40] And then now you also have to do things like WebSockets because the KVM support is not
[1246.40 → 1247.72] going to run over a custom protocol.
[1247.86 → 1248.80] It's going to run over HTTP.
[1249.14 → 1250.08] So you've got to do something.
[1250.56 → 1251.74] It's easy to get a lot of that stuff wrong.
[1251.88 → 1253.28] It's easy to get it wrong.
[1253.46 → 1258.50] And like they're hedging on that they can use existing implementations that have been
[1258.50 → 1259.10] well-tested.
[1259.60 → 1264.30] The problem is, is that usually those well-tested implementations don't fit on a BMC, right?
[1264.32 → 1266.80] You're dealing with a very constrained resource.
[1266.80 → 1272.06] The other side of it was they really didn't, the folks that were specking out this protocol
[1272.06 → 1277.52] really didn't talk with actual deployment, like operators that are doing real deployments.
[1277.74 → 1278.56] Who did they talk with?
[1278.88 → 1279.50] Well, they-
[1279.50 → 1281.26] This is a question I frequently have when I look at Redfish.
[1281.34 → 1282.16] Who did we talk to?
[1282.22 → 1285.86] Well, they have a lot of representatives from the actual system manufacturers and system
[1285.86 → 1286.30] integrators.
[1286.30 → 1287.30] I know they talk with themselves.
[1287.64 → 1292.26] And they also, you know, they talk with the BMC chip vendors, and they talk with some of
[1292.26 → 1295.98] the larger like consulting companies that actually do deployments, right?
[1296.02 → 1298.96] There are companies that will just like to build a data centre for you and then hand it off.
[1299.26 → 1302.44] So they talked to some of those, but they didn't really think about or interact with
[1302.44 → 1304.70] the people who actively-
[1304.70 → 1305.22] Use this stuff.
[1305.22 → 1306.62] Operate data centres.
[1306.86 → 1311.94] And they weren't really looking at what the existing industry practices were like at the
[1311.94 → 1312.66] hyperscale, right?
[1312.66 → 1317.06] Where this is solved because PMI was such a terrible solution, but it's solved where
[1317.06 → 1320.68] every vendor like hyperscaler has done their own implementation.
[1321.22 → 1325.44] It turns out that one of the things that really drives everybody batty about Redfish is actually
[1325.44 → 1327.64] the host to BMC interface.
[1328.16 → 1330.88] Because on PMI, it was well-defined.
[1330.96 → 1335.04] You speak the same protocol, but you do it over an interface that makes sense.
[1335.10 → 1340.36] So you might use, you know, LPC or I2C or one of these like system buses to actually
[1340.36 → 1341.66] talk from the host down.
[1341.66 → 1343.56] Well, in Redfish, they're like, well-
[1343.56 → 1344.22] Just go over the network.
[1344.38 → 1348.48] We built the entire security model and design around an HTTP endpoint.
[1348.62 → 1348.80] Yeah.
[1348.92 → 1354.50] So clearly, if you want your BIOS on your host system to be able to read the temperature
[1354.50 → 1360.54] sensors to show it on the screen when it's booting, you have to implement a USB networking
[1360.54 → 1366.54] stack to be able to send an HTTP request and then parse the JSON result that comes back
[1366.54 → 1368.14] to show this information.
[1368.34 → 1369.64] This does not feel like progress.
[1369.64 → 1371.72] This feels like a big step in the wrong direction.
[1371.80 → 1375.04] Especially then, I mean, even absent vulnerabilities, it sounds incredibly complicated.
[1375.10 → 1375.88] Then you have all these vulnerabilities.
[1376.46 → 1376.58] Right.
[1376.86 → 1381.70] So the firmware world has gotten very, very complex as we keep shifting more and more
[1381.70 → 1386.94] complexity down into system firmware as we are building, you know, bigger and more complex
[1386.94 → 1387.34] systems.
[1387.34 → 1388.12] All right.
[1388.12 → 1391.34] So we are going to take a quick break, and then we are going to come back.
[1391.40 → 1393.86] And I think Jess is going to want to ask you some more love stories, Rick.
[1394.32 → 1396.28] After a quick break and a word from our sponsor.
[1397.60 → 1400.84] On the Metal is brought to you by the Oxide Computer Company.
[1401.04 → 1402.60] Wait, did you say computer company, Jess?
[1402.68 → 1403.36] Yes, indeed.
[1403.54 → 1404.18] But wait a minute.
[1404.24 → 1405.28] Everyone runs in the public cloud.
[1405.42 → 1407.62] Jeff Bezos owns and operates every computer on the planet.
[1407.78 → 1409.64] Why would anyone start a computer company?
[1409.84 → 1410.90] That is so not true.
[1410.90 → 1416.44] I have spent a bunch of time talking to folks who are still running on premises and actually
[1416.44 → 1421.66] like the consensus among all of them is just a feeling of neglect because everyone thinks
[1421.66 → 1423.96] that like everything is moving to the public cloud, but it's not.
[1424.24 → 1427.08] If you're still running on premises, it's because you haven't heard of the cloud, right?
[1427.30 → 1433.14] No, there are perfect reasons for running on premises still for security, for latency,
[1433.38 → 1435.20] strategic reasons for your business.
[1435.56 → 1435.82] Wow.
[1435.90 → 1439.34] The people running on premises must feel like everyone has ignored them.
[1439.62 → 1440.06] They do.
[1440.06 → 1440.52] Indeed.
[1440.52 → 1446.28] So if this is you, please head on over to our website, Oxide. Computer, sign up for our
[1446.28 → 1449.50] mailing list, and we would love to get in touch and hear your stories.
[1449.64 → 1454.06] We acknowledge that you exist, and you've got some really hard technical problems that we're
[1454.06 → 1454.36] solving.
[1454.54 → 1456.08] Oxide. Computer, come join us.
[1458.26 → 1459.86] All right, we're back.
[1460.62 → 1462.38] Jess, love story questions.
[1462.66 → 1462.88] Okay.
[1463.56 → 1470.18] This one's more, it's on the border of a nightmare and a love story though, but it is the
[1470.18 → 1475.38] most interesting or like the weirdest bug you've ever found.
[1475.38 → 1477.42] Oh, so many stories here.
[1477.78 → 1478.92] Hard to choose again.
[1479.06 → 1482.66] I mean, for someone who's been in the places that Rick has been, this is like legitimately
[1482.66 → 1483.72] triggering potentially.
[1484.48 → 1486.98] It could be, but we're going to stay away from those.
[1486.98 → 1487.30] Okay.
[1487.40 → 1487.80] That's good.
[1488.02 → 1489.52] That's good on doctor's orders.
[1489.68 → 1492.78] And I'm going to limit it to the ones that I actually had direct involvement with because
[1492.78 → 1496.58] there's one that is absolutely fascinating, but it wasn't actually something that I've
[1496.58 → 1497.14] only no second.
[1497.14 → 1504.36] Probably my worst one was actually a bug that I inherited.
[1504.82 → 1510.12] So I joined a team, and I was on their hardware team doing firmware work.
[1510.42 → 1514.58] And I got this bug assigned to me because I was now the owner of that system.
[1514.88 → 1516.46] And I looked at how old the bug was.
[1516.56 → 1517.60] The bug was five years old.
[1517.78 → 1521.96] The bug was that the machine would not stay powered off.
[1522.80 → 1523.24] What?
[1523.24 → 1526.76] So you, you would log into the machine.
[1526.94 → 1528.04] You would run shutdown.
[1528.46 → 1530.38] It would go through the whole shutdown sequence.
[1530.58 → 1532.04] The power would actually turn off.
[1532.48 → 1536.28] And about two seconds later, it would turn right back on and go right back up.
[1536.42 → 1537.38] That's brutal to the bug.
[1538.86 → 1539.70] It's a ghost.
[1540.12 → 1540.42] Zombie.
[1540.46 → 1543.64] Well, no, you just think about like, how do you go debug something like that?
[1544.24 → 1545.16] I mean, that is, that is.
[1545.18 → 1545.84] Because it's off.
[1545.90 → 1546.78] Well, it's off.
[1547.24 → 1548.12] But it's not off.
[1548.38 → 1548.84] Air quotes.
[1548.98 → 1549.90] It's clearly not off.
[1550.14 → 1551.84] Well, and so thankfully.
[1551.84 → 1552.52] Or maybe it was off.
[1552.52 → 1557.80] Thankfully, the people in the past who had dealt with this bug understood what the actual issue was.
[1557.86 → 1558.88] They had done all the hard work.
[1559.40 → 1563.56] So I mostly just got to live through the, oh, this is one of those.
[1565.14 → 1569.72] It turns out that that particular generation of chipset.
[1570.00 → 1575.48] So the actual like Northridge and Southbridge had a SMBs controller on it, as they usually do.
[1575.96 → 1577.42] And SMBs has an alert pin.
[1577.42 → 1586.06] And the concept of the alert pin is that your SMBs slave devices can raise the alert pin to cause an interrupt and say, hey, something happened.
[1586.22 → 1586.96] All fine and good.
[1587.22 → 1592.50] Well, in this particular version of the chipset, that was a nonbankable interrupt.
[1592.70 → 1595.22] It will actually wake the system from sleep if it gets asserted.
[1595.22 → 1598.78] Now, that normally wouldn't be an issue.
[1599.28 → 1602.36] What would actually be causing the alert pin to go high?
[1602.36 → 1611.00] Well, it turns out that the employer at that time was also making their own custom power supplies that were built off of, they would run off utility power.
[1611.10 → 1614.22] But they also had a battery charger and automated cutover.
[1614.32 → 1616.02] So they had sort of a built-in UPS in them.
[1616.02 → 1620.62] And it makes perfect sense that if you lose power, you want to have an alert, of course.
[1620.62 → 1625.88] You want to set the alert and notify the host system that something's happening, but nothing clears it.
[1626.04 → 1636.46] So the very first time you do a cutover from utility power to battery, doesn't matter when that happens, it would set this alert flag, and then it would never clear it.
[1636.46 → 1641.52] And so when the machine went to sleep, the alert was set high, it would NMI, and it would wake the system back up.
[1641.88 → 1644.04] Which is just this whole Rube Goldberg machine, right?
[1644.36 → 1649.76] Now, the reason this got to be really bad was you have to do testing on your batteries to actually make sure they work.
[1650.18 → 1658.18] So you were guaranteed that at least once a month you were going to go from utility power to battery power, which meant this bug would show up often.
[1658.52 → 1658.60] Right.
[1658.80 → 1661.72] And I assume this was dead reproducible or nearly.
[1661.80 → 1662.20] It should have been.
[1662.32 → 1665.90] Once you understood what was happening, it's really easy to reproduce.
[1665.90 → 1668.40] Like no machine would stay powered off, it sounds like.
[1668.48 → 1669.96] Well, only that particular generation.
[1670.40 → 1677.48] For that particular generation, because, you know, I've often thought that bugs may be psychotic or non-reproducible, but not both.
[1677.84 → 1678.02] Yeah.
[1678.24 → 1680.58] And that's a psychotic bug, but it's dead reproducible.
[1680.80 → 1680.90] Yeah.
[1681.12 → 1684.18] Because presumably it took an analyzer or, I mean.
[1684.52 → 1687.00] Oh, I mean, it took six months for people to figure out.
[1687.00 → 1687.28] Right.
[1687.34 → 1687.72] Originally.
[1688.26 → 1692.92] Now, my favourite part of this is actually recognizing that there is no way to fix this.
[1693.98 → 1694.42] Right.
[1694.42 → 1701.22] The series of events and design decisions were locked into the hardware, and it was always going to do this.
[1701.88 → 1703.02] So what is your fix?
[1703.26 → 1704.86] Because you do want the machines to shut off.
[1705.48 → 1705.72] Anybody?
[1706.34 → 1707.22] I don't know.
[1707.42 → 1707.60] Yeah.
[1707.74 → 1713.14] And I feel that we in low-level software are often asked to make up for hardware sins.
[1713.40 → 1716.40] I feel like we're often engaged in kind of cover-up, honestly.
[1716.62 → 1716.94] Always.
[1717.22 → 1717.88] A cover-up.
[1718.00 → 1718.10] Yeah.
[1718.10 → 1719.08] It feels that way.
[1719.08 → 1721.96] It feels like, look, we have to like, look, dad's a drunk.
[1722.12 → 1722.40] Okay.
[1722.44 → 1724.86] So we just have to like, can we pretend like we're a normal family?
[1725.02 → 1725.42] Look alive.
[1725.58 → 1726.18] Look alive.
[1726.28 → 1726.82] It's like, no.
[1726.94 → 1728.16] Well, in this case, look dead.
[1728.88 → 1729.24] Yeah.
[1729.60 → 1730.44] Everybody look dead.
[1730.44 → 1736.10] But this is a tough one to cover up because you, yeah.
[1736.16 → 1736.80] How did you do it?
[1736.80 → 1737.20] I don't know.
[1737.54 → 1741.60] You got the because NMI, I mean, NMI, there's a reason they call it NMI.
[1741.84 → 1742.72] It's nonbankable.
[1742.90 → 1743.10] Yeah.
[1743.10 → 1747.16] But see, it's really caused by that, that power supply flag setting the alert.
[1747.34 → 1747.60] Okay.
[1747.68 → 1749.42] And it was possible to clear that from software.
[1749.64 → 1749.98] Ah, okay.
[1750.40 → 1752.92] So a cron job calls out and clears that once a day.
[1753.38 → 1754.12] Oh my gosh.
[1754.16 → 1754.44] Nice.
[1754.66 → 1758.04] And so the bug comes back when somebody actually removes that cron job because they say,
[1758.12 → 1759.16] why do you have this cron job?
[1759.66 → 1763.18] And so, and so the cron job would set the bit on the power supply.
[1763.54 → 1763.70] Yeah.
[1763.72 → 1766.84] It would clear the flag that, that power had failed.
[1767.04 → 1767.96] That power had failed.
[1768.38 → 1768.94] Got it.
[1768.94 → 1773.26] And so, so now if you managed, if you powered it off twice in the same day,
[1773.34 → 1774.58] wouldn't you also see the problem or no?
[1774.84 → 1779.72] Uh, only if you, I mean, if you had lost utility power at some point, that flag would get set.
[1779.84 → 1780.02] Right.
[1780.36 → 1781.20] And it would stay set.
[1781.30 → 1782.62] And so you wouldn't be able to turn off.
[1782.72 → 1782.92] Right.
[1783.08 → 1785.32] But as soon as the as soon as the cron job fires,
[1785.42 → 1787.94] as soon as the cron job fires, it's going to clear that flag, and then you're good to go.
[1787.96 → 1790.52] And where is the, is the cron job, where's the cron job running?
[1790.96 → 1793.42] Is it running on the BMC?
[1793.54 → 1794.18] Oh, no, no, no.
[1794.30 → 1795.54] This, this was running on the host.
[1795.80 → 1795.98] Yeah.
[1796.20 → 1796.76] Okay, nice.
[1796.76 → 1797.06] Yeah.
[1797.06 → 1800.24] That is one where you'd be like, so this is just like someone logs into this machine.
[1800.34 → 1802.24] It's like iron tab minus L and there's that.
[1802.34 → 1802.82] There it is.
[1802.96 → 1803.04] Right.
[1803.12 → 1807.88] I mean, that's like all the machines that I've ever used were obviously pets because people
[1807.88 → 1810.98] would log in and be like, oh, there are some cron jobs just set up.
[1811.42 → 1813.04] Like, yeah.
[1813.14 → 1817.14] It's hard to know if this is a pet or a cattle, but that's a cron job.
[1817.34 → 1818.64] You think that like, what was that name?
[1818.70 → 1819.90] You think you would want to name it?
[1819.92 → 1821.32] Like, do not delete me.
[1821.38 → 1821.84] I'm serious.
[1821.92 → 1822.50] You've been warned.
[1822.84 → 1823.02] Yeah.
[1823.02 → 1827.18] No, it was something more like PSU fix, which is always great, right?
[1827.18 → 1829.00] Like, I don't even know what this is for.
[1829.24 → 1830.46] But it's fixing something.
[1830.60 → 1831.18] It's fixing something.
[1831.26 → 1832.30] It's like, ah, we don't need that.
[1832.40 → 1832.96] I deleted it.
[1833.00 → 1833.42] It was fine.
[1833.54 → 1833.72] Right.
[1833.88 → 1834.84] It was fine.
[1835.04 → 1835.24] Yeah.
[1835.44 → 1836.42] Systems seem to work.
[1836.84 → 1837.78] Until the next month.
[1837.98 → 1838.16] Yeah.
[1838.20 → 1839.56] That is, uh, that's grisly.
[1839.64 → 1842.18] So was the cron job was, uh, was your doing?
[1842.76 → 1843.66] Uh, no, actually.
[1843.72 → 1844.76] I mean, somebody else had written that.
[1844.84 → 1847.86] And so I just came up with better ways of making sure the cron job didn't get removed.
[1848.00 → 1848.80] There you go.
[1849.02 → 1849.38] Nice.
[1849.44 → 1849.70] Nice.
[1849.70 → 1850.76] That's good.
[1851.02 → 1852.08] That's an important role.
[1852.88 → 1857.58] Uh, so, and then how, in terms of, I mean, you have been up, down, and all around.
[1857.68 → 1861.88] You've been at, I think, um, I mean, you've done disc controller stuff.
[1862.04 → 1867.26] You've done, um, and I assume that at every level you've got horror stories.
[1867.48 → 1867.92] Oh, yeah.
[1868.28 → 1870.38] I mean, that's, that's the nature of hardware, right?
[1870.42 → 1874.44] And, and firmware is, as you said, firmware is making up for, for the mistakes of hardware.
[1874.52 → 1877.02] And there's always interesting things that have occurred.
[1877.02 → 1881.08] Depending on which field you get into, you bring in more interesting failure modes.
[1881.26 → 1884.42] But it's always the case of something will go wrong in the hardware.
[1884.62 → 1886.24] And firmware is your first chance of fixing that.
[1886.34 → 1891.08] You start moving higher up the stack as you work on situations that have to bring in more
[1891.08 → 1894.18] data or more context to actually decide what to do in this failure scenario.
[1894.58 → 1899.34] So I'm curious where you've had bugs where the hardware is in danger of physically destroying
[1899.34 → 1901.10] itself if software doesn't do the right thing.
[1901.18 → 1904.94] So the at that level, this is not true for, for most of us that are even at the hardware
[1904.94 → 1905.68] software interface.
[1906.18 → 1908.82] Most of the time, hardware is pretty good at not destroying itself.
[1909.66 → 1913.42] But I, I have to believe that some of the layers you've been, that you, you've seen some things
[1913.42 → 1914.48] where it's like, no, no, no.
[1914.50 → 1918.66] If we don't actually, you know, certainly if you're writing firmware for a disk controller,
[1918.82 → 1920.88] I mean, you can actually, a lot of bad things can happen.
[1921.74 → 1922.84] Very bad things can happen.
[1922.84 → 1927.92] There, there was actually a mailing list internally at one of my employers that was nothing but
[1927.92 → 1931.26] pictures of equipment that had caught fire in the data centre.
[1931.50 → 1932.86] Whoa, that's dope.
[1932.86 → 1934.80] That's like a Reddit that I would subscribe to.
[1934.98 → 1935.04] Yeah.
[1935.16 → 1935.30] Yeah.
[1935.32 → 1938.54] And the thing was, it was like, there was always a new contribution about every week.
[1938.64 → 1944.00] I mean, so the rate at which things would just burst into flames, um, was relatively
[1944.00 → 1944.32] high.
[1944.40 → 1946.88] Now you have to keep in mind, I, I used to work at hyperscalers.
[1946.88 → 1953.70] And so like at the volume they work at, the probability of any event occurring is almost
[1953.70 → 1957.30] certainty for this to be happening this often is just a consequence of scale.
[1957.72 → 1960.44] But yeah, that, that was definitely a thing in the hard drive space.
[1960.44 → 1961.70] There's a fascinating one though.
[1961.70 → 1967.18] Uh, there was a particular generation of hard drives that there was a mistake in the actual
[1967.18 → 1968.30] calculations they did.
[1968.94 → 1973.44] So hard drives are really, really, fascinating because internally, right, you've got the platters
[1973.44 → 1974.80] spinning at high speeds.
[1974.80 → 1974.98] Yeah.
[1974.98 → 1979.28] The heads are actually trying to move back on a servo motor, but the heads are actually
[1979.28 → 1980.26] airfoils.
[1980.64 → 1980.88] Yes.
[1981.12 → 1987.02] They're relying on the speed of the air from the platter spinning to actually fly, literally
[1987.02 → 1989.40] fly above the surface of the media.
[1989.40 → 1994.48] So you have to do these calculations around number of impurities that you might expect
[1994.48 → 1998.92] and what those heights would be to decide how high to fly the head, uh, to the disc
[1998.92 → 2000.14] of the lifespan of the drive.
[2000.24 → 2004.04] And there's a different height that you use for reading versus writing because you need
[2004.04 → 2008.14] to be lower when you're writing so that you, uh, change the magnetism over a much smaller
[2008.14 → 2008.54] area.
[2008.54 → 2013.64] And it turned out that they had just, they had taken the previous generation and like
[2013.64 → 2018.92] the calculation from that and, and like multiplied it by two, but they forgot that it was an error
[2018.92 → 2020.94] bound like both directions.
[2021.16 → 2021.44] Uh-oh.
[2021.68 → 2028.08] And so they ended up making the error very tight for the actual fly height of the head.
[2028.26 → 2028.56] Wow.
[2028.98 → 2029.30] So.
[2029.48 → 2034.04] And the fly heights, it should be said, these are very, very small distances.
[2034.16 → 2034.38] Yeah.
[2034.72 → 2034.96] Yeah.
[2035.06 → 2035.78] I mean, we're talking.
[2035.78 → 2039.64] The number that was given to me that I honestly still don't believe.
[2039.74 → 2043.46] So if you tell me this is false, I, but the number was given to me by someone who works
[2043.46 → 2048.14] for a disc manufacturer, the fly height during a White 0.8 nanometres.
[2048.44 → 2049.08] Yeah, that's about right.
[2049.38 → 2051.08] That is, that's insane.
[2051.20 → 2052.22] That's 800 picometres.
[2053.30 → 2054.38] That's insanity.
[2055.08 → 2055.24] Yeah.
[2055.60 → 2058.16] And especially as they've gotten into things like the helium filled drives.
[2058.28 → 2058.46] Yeah.
[2058.54 → 2058.68] Right.
[2058.98 → 2059.18] Yeah.
[2059.18 → 2060.28] This is definitely a helium filled drive.
[2060.46 → 2063.78] They, because they ran into the problem of, uh, with natural air.
[2064.30 → 2064.66] Molecules.
[2064.66 → 2070.00] Well, the air turbulent, the turbulence effects of the platter spinning would actually cause
[2070.00 → 2071.00] too much variation.
[2071.00 → 2073.68] So you couldn't fly any closer because you'd be in the turbulent flow.
[2074.10 → 2079.10] And so that's why they switched to helium was actually that helium has lower drag on the
[2079.10 → 2079.36] surface.
[2079.52 → 2080.78] And so you can actually fly closer.
[2081.40 → 2081.54] Yeah.
[2081.76 → 2083.88] So this thing was flying too close then.
[2083.90 → 2084.82] It was flying too close.
[2084.82 → 2085.30] Man.
[2085.30 → 2092.14] And so in a hard drive, like you expect surface impurities, and you expect to, to encounter
[2092.14 → 2099.02] them with the drive head, AKA the head literally slamming into a mountain on the surface of the
[2099.02 → 2101.46] disc at 7,200 RPM.
[2101.86 → 2102.08] Right.
[2102.20 → 2105.10] A mountain, a four nanometre high mountain.
[2105.34 → 2105.58] Right.
[2105.78 → 2107.78] I mean, just to put this in scale.
[2107.94 → 2110.60] But I mean, from a visual perspective, right?
[2110.60 → 2110.94] Yeah, exactly.
[2111.06 → 2111.30] Absolutely.
[2111.30 → 2113.42] The platter is supposed to be perfectly flat.
[2113.50 → 2115.66] So these things are big like peaks.
[2116.16 → 2116.18] Peaks.
[2116.30 → 2118.48] And you're going to have this head smash into it.
[2118.76 → 2123.28] And so the failure mode is actually that the head itself becomes deformed from repeated
[2123.28 → 2123.84] impacts.
[2123.84 → 2130.34] So this was where we had to like to ask for electron microscope photography of the heads of failed
[2130.34 → 2136.34] drives to root cause that in fact, yes, this really was a case where the fly height had
[2136.34 → 2137.20] been miscalculated.
[2137.42 → 2141.20] And so these drives were actually destroying their heads faster than anticipated.
[2141.38 → 2146.28] But you raise a fascinating point about that you've got a hardware that is designed
[2146.28 → 2149.36] for this kind of mechanical impact over and over again.
[2149.36 → 2153.92] And it's actually hard to find the software defect, even though if the poor head could
[2153.92 → 2155.80] speak, it would say, hey, you know what?
[2155.82 → 2157.02] I'm running into a lot of things.
[2157.18 → 2158.70] I'm running into more things than you would expect.
[2158.82 → 2164.22] I mean, because it's so designed to have, you know, to be able to take another lap effectively
[2164.22 → 2166.28] and hit the track that it missed.
[2166.50 → 2166.68] Yeah.
[2166.74 → 2169.62] I mean, this is kind of the nature of the beast when you're down this low in the firmware
[2169.62 → 2174.74] stack is when you're truly interacting with the hardware at this level, you can usually
[2174.74 → 2175.64] do dangerous things.
[2175.64 → 2179.22] Um, and often the effects are hard to tell.
[2179.44 → 2184.24] So it's the same as when you're building like critical systems for industrial control or
[2184.24 → 2186.12] spacecraft or whatever, right?
[2186.18 → 2191.14] There's always this case where I'm dealing with hardware that has some effect that I can
[2191.14 → 2195.42] only measure through my sensors, and it has a risk to human safety.
[2195.62 → 2197.02] So what do I do?
[2197.42 → 2199.32] Um, and how do you design that hardware?
[2199.32 → 2205.02] And often the tendency has been to shift more and more control over to the software and assume
[2205.02 → 2206.40] that the software can do the right job.
[2206.52 → 2210.30] And there's always this back and forth of, well, in some cases that's fine, right?
[2210.32 → 2214.36] Like in the hard drive case, yes, having the fly height controlled by the firmware makes
[2214.36 → 2214.72] sense.
[2215.12 → 2218.46] But when you get it wrong, it's going to have massive effects.
[2218.58 → 2222.86] On the other hand, when you have like actual, you know, critical devices, you actually want
[2222.86 → 2227.06] to build the hardware in a totally different way so that if there's a failure in the software,
[2227.06 → 2229.26] that it's intrinsically safe, right?
[2229.32 → 2231.92] It cannot possibly do the thing that would be dangerous.
[2232.04 → 2234.40] Unfortunately, these are not actually dangerous to people, but they're definitely dangerous
[2234.40 → 2234.88] to the device.
[2234.96 → 2236.74] At least the failures you're talking about.
[2237.02 → 2237.28] Yeah.
[2237.36 → 2240.46] It just happens to be that I've worked on other systems where it was much more about not
[2240.46 → 2241.08] hurting humans.
[2241.30 → 2241.64] Yeah.
[2241.86 → 2242.90] We definitely shouldn't hurt the humans.
[2243.42 → 2246.34] Are you familiar, Jesse, are you familiar with the legend of the walking drives?
[2246.90 → 2247.26] No.
[2247.52 → 2247.70] Do you?
[2248.00 → 2248.22] Oh, yeah.
[2248.22 → 2248.82] Yeah, right.
[2248.82 → 2256.32] So where the drives, when you would have a spindle that was sufficiently large, there's enough
[2256.32 → 2257.44] angular momentum on that thing.
[2257.52 → 2262.66] You can actually make the drive lurch by seeking to the same location over and over again.
[2262.84 → 2265.78] And this is when like a hard drive was the size of a washing machine.
[2265.94 → 2266.16] Right.
[2266.30 → 2267.10] Oh, Geez.
[2267.72 → 2271.20] So there is actually, there's a great story in the new hacker's dictionary, which I hate
[2271.20 → 2271.40] to.
[2271.58 → 2272.82] I have that inside.
[2272.98 → 2275.26] I hate to encourage people to buy it because he's such a.
[2275.52 → 2276.00] It's good.
[2276.44 → 2276.90] It is good.
[2276.90 → 2279.58] It's a good, it's a good book written by a bad man.
[2279.66 → 2281.80] No, just it's written by he who must not be named.
[2281.92 → 2282.84] He who must not be named.
[2282.84 → 2287.80] But there's a good story in there about hackers getting into a Xerox machine and making the
[2287.80 → 2288.42] drives walk.
[2289.36 → 2291.90] So Rick, let's talk about the future of firmware a little bit.
[2292.12 → 2295.46] Because, you know, Jess and I were at, and Steve, you missed the open source firmware
[2295.46 → 2295.98] conference.
[2296.40 → 2297.82] But Jess and I went down there.
[2297.84 → 2298.70] It was a lot of fun.
[2298.98 → 2299.34] It was dope.
[2300.04 → 2302.68] It was like an old school conference.
[2302.94 → 2305.14] Like people actually wanted to help each other.
[2305.26 → 2306.12] People were nice.
[2306.34 → 2308.42] There wasn't like vendor booths everywhere.
[2308.72 → 2310.38] Like it was like actually legit.
[2310.60 → 2311.22] I thought it was great.
[2311.22 → 2312.52] Yeah, I mean, Rick, is that your read too?
[2312.56 → 2313.46] I thought that was a lot of fun.
[2313.68 → 2314.06] Yeah, yeah.
[2314.14 → 2318.48] I mean, it's definitely a conference that is by and for a particular group of developers.
[2318.96 → 2322.12] And it's not become a commercial venue.
[2322.32 → 2323.74] It's not become a commercial venue.
[2324.22 → 2325.02] And I don't know, it did.
[2325.10 → 2329.66] I was telling Jess when I said this did kind of date back to an era when you had no other
[2329.66 → 2333.84] way of connecting to people in your incredibly small demographic.
[2334.60 → 2338.84] Other than, and you would kind of walk in the room like, oh my God, there are 200 people
[2338.84 → 2340.86] here that are interested in open source firmware.
[2340.86 → 2341.46] I thought it was great.
[2341.52 → 2342.06] It was dope.
[2342.44 → 2343.58] It was so much fun.
[2343.78 → 2348.76] And tons of people, the BMC track had like, I mean, the track that you were in, like 100
[2348.76 → 2349.36] people in there.
[2349.72 → 2349.98] Yeah.
[2350.16 → 2350.38] Yeah.
[2350.38 → 2352.16] And a lot of that's all relatively recent.
[2352.38 → 2357.96] I mean, the idea of an open source BMC stack actually only came about like two and
[2357.96 → 2358.84] a half, three years ago.
[2359.46 → 2361.08] And it seems like a lot of interest from a lot of folks.
[2361.20 → 2363.18] So what's your thinking on the future of open source firmware?
[2363.36 → 2367.38] I feel that we're kind of on the cusp of this becoming real.
[2367.44 → 2367.84] What do you think?
[2367.84 → 2368.74] I think so.
[2369.42 → 2374.62] It's going to be different as we talk about different devices that use firmware.
[2375.00 → 2380.48] Like there's EFI for an x86 system and has a large amount of it that's been open since
[2380.48 → 2382.54] the very beginning, but portions of it aren't.
[2382.76 → 2386.04] And similar to BMCs, BMCs are getting to be more open.
[2386.40 → 2391.28] There's this fine line of happening between firmware being open source, but there being
[2391.28 → 2395.80] aspects of it that are closed because of the security concerns or the security model around
[2395.80 → 2396.02] it.
[2396.02 → 2401.68] So you might need a signing key that you can't get unless you have an NDA, which kind of
[2401.68 → 2401.92] sucks.
[2402.52 → 2406.00] And so there are other things like, you know, can I actually get the data sheets to even
[2406.00 → 2406.78] implement the firmware?
[2406.96 → 2410.62] So there's, there are issues that the industry is still figuring out how to adopt it, but
[2410.62 → 2415.68] they've also definitely seen the success stories of using open source in firmware.
[2415.68 → 2420.88] You know, part of the background of the Chrome books using Core boot is actually that, you know,
[2420.94 → 2425.14] a person was flagged down in the hallway as he was working in that, that building, not
[2425.14 → 2428.80] on firmware at all, but he had a past of working on Core boot.
[2428.92 → 2432.40] And they said, Hey, we are trying to work out a firmware situation for these Chromebook
[2432.40 → 2432.80] things.
[2433.32 → 2435.24] What do you think about trying to port Core boot to it?
[2435.28 → 2438.90] And so they did it, and they got it done, and it worked better than the actual reference
[2438.90 → 2440.34] firmware from, from the vendor.
[2440.34 → 2442.88] And it's actually a similar story for Open BMC.
[2443.08 → 2447.50] So I was at Google when that happened, and I was managing a team that was starting to
[2447.50 → 2454.56] work on BMCs, and we got a machine in, and we were actually trying to talk with the sales
[2454.56 → 2460.50] folks at a major vendor of BMC firmware and just get a quote from them on what it would
[2460.50 → 2462.12] cost to license their product.
[2462.34 → 2466.30] You would expect that this is something that they would be wanting to do, but it had been
[2466.30 → 2468.66] going on long enough that I just said, you know what?
[2468.66 → 2472.82] I'm going to port Open BMC to this, and we will see who wins first.
[2473.04 → 2474.76] It is actually faster than your sales cycle.
[2474.86 → 2478.54] I can port this faster than I can get your sales folks to call me back to license it.
[2478.56 → 2484.60] Yeah, I had an entire Linux environment booting on the BMC and then actually causing the host
[2484.60 → 2487.24] CPU to power on in about two days.
[2487.38 → 2488.14] That's impressive.
[2488.22 → 2495.58] And we actually didn't get a quote from said major vendor for another week, at which point
[2495.58 → 2498.08] we're just like, I'm sorry, we've got a different solution.
[2498.08 → 2499.36] Yeah, thanks to your delay.
[2499.62 → 2501.62] We actually have a that's terrific.
[2502.00 → 2507.70] So certainly it seems like open source firmware is alive and well and thriving in the BMC.
[2508.96 → 2512.56] And hopefully on the for the BIOS as well, I mean, can we please?
[2512.84 → 2517.62] BIOS is, I mean, as I said, like most of EFI is open source.
[2518.00 → 2521.28] You can build EDK2 and get a reference implementation.
[2521.28 → 2527.12] What you're missing is a lot of the fit and finish that makes it a production BIOS and the
[2527.12 → 2530.96] specific per board configuration stuff that has to happen.
[2531.16 → 2532.20] That you actually need to boot.
[2532.56 → 2533.40] Yeah, yeah, yeah.
[2533.40 → 2539.20] And that's kind of where the difficult divide is in that the silicon vendors tend to feel
[2539.20 → 2543.76] that if they give you the raw documentation for how to interact with the system, that they're
[2543.76 → 2545.38] handing over too many trade secrets.
[2546.00 → 2550.86] So instead they want to hand you some sort of blob that is, you know, just call these
[2550.86 → 2554.30] functions in this prebuilt library, and it will do the thing.
[2555.00 → 2556.36] Do you think that that is well-informed?
[2556.48 → 2560.10] Do you think that that's just out of embarrassment for you seeing all the dirty laundry?
[2560.10 → 2562.04] It's a bit of both.
[2562.98 → 2569.42] If you go way back, like these companies were burned by relying on external parties to write
[2569.42 → 2575.72] firmware and them having to produce accurate developer information and provide it to folks
[2575.72 → 2577.40] in an OpenSSH way.
[2578.20 → 2583.14] And as part of actually having to write the documentation, right, and maintain it as a business
[2583.14 → 2583.58] cost.
[2583.76 → 2588.30] And also the it does actually tell a lot about the design of your hardware.
[2588.30 → 2592.28] If you tell somebody how to initialize your memory controller, they now know how your
[2592.28 → 2593.96] memory controller actually works under the hood.
[2594.58 → 2596.80] And that, that can be quite damaging as well.
[2596.88 → 2600.68] So there's, there's some validity to it, but there's also a side of, but come on, you're,
[2600.82 → 2603.64] the machine that I'm interested in is three generations old.
[2603.78 → 2604.00] Right.
[2604.24 → 2604.66] You actually.
[2604.82 → 2606.56] Why can't you give me information on this?
[2606.68 → 2606.88] Right.
[2606.90 → 2607.90] Because it might be embarrassing.
[2608.00 → 2609.66] Well, I mean, they get embarrassed anyway.
[2610.02 → 2610.28] Right.
[2610.54 → 2611.22] Yeah, exactly.
[2611.28 → 2612.66] They can get embarrassed the easy way or the hard way.
[2612.86 → 2613.86] Open compute project.
[2614.08 → 2616.10] Open compute seems very vibrant.
[2616.10 → 2618.86] It seems like the OCP summit was another one that was, that was exciting for us.
[2618.94 → 2619.76] What's your take on that?
[2620.30 → 2620.48] Yeah.
[2620.86 → 2622.92] OCP has gone an interesting direction.
[2623.76 → 2628.50] You know, I, when Facebook first started it, it, it seemed like a unique approach to
[2628.50 → 2634.82] getting, stirring up the, the existing ODM manufacturer business to build things that
[2634.82 → 2637.92] were different from the, the 19-inch rack standard.
[2638.18 → 2641.14] A standard that doesn't like to go back to like, isn't that half of a horse's butt or whatever?
[2641.14 → 2643.32] Is this going to be another Roman chariots thing?
[2643.34 → 2646.20] 19 inches is half, half of a horse's butt.
[2646.30 → 2646.74] Is that what you're saying?
[2646.74 → 2648.02] Maybe it's like a full horse's butt.
[2648.10 → 2648.88] I feel like a horse's butt.
[2648.98 → 2649.24] Isn't it?
[2649.46 → 2650.58] No, because doesn't this go?
[2650.78 → 2651.02] Railroad ties.
[2651.10 → 2651.24] Yeah.
[2651.30 → 2651.60] This is good.
[2651.66 → 2654.64] The railroad ties and the railroad ties ultimately go to like, you have to have two horses.
[2654.90 → 2656.18] That was disproven.
[2656.58 → 2656.78] Yeah.
[2656.78 → 2657.38] I'm so sorry.
[2657.72 → 2657.98] I know.
[2658.00 → 2661.12] I mean, because horse's butts are like actually pretty large.
[2661.50 → 2661.86] Yeah.
[2661.90 → 2662.54] It depends on the horse.
[2662.62 → 2663.46] Maybe a pony butt.
[2663.98 → 2664.60] Like a Shetland pony butt.
[2664.60 → 2666.42] Is that where the 24-inch standard came from?
[2666.42 → 2666.68] Yeah.
[2666.68 → 2667.28] There we go.
[2667.42 → 2667.74] Exactly.
[2668.10 → 2668.52] Steed butt.
[2668.52 → 2668.78] All right.
[2668.78 → 2671.18] Sorry to sidetrack us in the butts.
[2671.30 → 2672.74] Bring up internet lore.
[2674.04 → 2683.74] So over time, as they really brought more people on, it seems like it really gained a lot of movement once Google and Microsoft also joined.
[2684.28 → 2690.60] And so now you have sort of the structure of the hyperscalers are feeding into this and making it clear what they want.
[2690.60 → 2701.52] They're actually doing a lot of the design work as well and providing reference designs that are what they are using, but they might not be perfectly fit for others to consume.
[2702.24 → 2708.88] And so by handing the designs down to OCP, then OCP partners can actually pick that up and produce real designs.
[2708.88 → 2710.24] And you have different approaches.
[2710.24 → 2716.24] Like Google is well known for doing all of their own server development and working with their manufacturing partners directly.
[2716.56 → 2719.96] And, you know, these are very, very custom to them.
[2720.30 → 2722.40] This is what Jess calls infrastructure privilege.
[2723.56 → 2724.56] I like that term.
[2724.72 → 2725.52] It's a good term.
[2725.68 → 2726.06] It is.
[2726.24 → 2726.46] Yeah.
[2726.46 → 2736.06] It's because in talking to folks that work at hyperscalers, we have found that a lot of them don't understand the pain of literally, you know, off the shelf hardware.
[2736.38 → 2736.74] Oh, yeah.
[2736.88 → 2739.04] They haven't had to touch it in a long time.
[2739.52 → 2740.28] Or ever, maybe.
[2740.40 → 2740.52] Yeah.
[2740.56 → 2745.88] I feel like you've got now a whole generation that's just grown up thinking like everyone has these computers that are this awesome.
[2745.88 → 2753.04] At some point, I feel like I got gaslit into thinking that maybe Dell was not that bad by some people who were like, well, it can't be that bad.
[2753.06 → 2754.74] It's like, oh, no, like it actually is.
[2754.74 → 2755.82] No, it's bad.
[2755.82 → 2756.76] But ask Calvin.
[2757.10 → 2757.66] Wherever you go.
[2757.98 → 2758.88] So you can find that guy.
[2759.52 → 2760.42] Calvin and Hobbes.
[2760.68 → 2760.98] Maybe.
[2761.28 → 2761.48] Yeah.
[2761.80 → 2767.44] But then you end up with folks like Facebook who really put out more of an RFQ type thing to the community.
[2767.68 → 2770.60] Or they work with a partner to actually design a machine.
[2771.04 → 2775.52] And it's very clear that it's been significantly contributed to by the ODM, right?
[2775.52 → 2778.60] So the ODMs are still having a lot of direct involvement in those designs.
[2779.26 → 2781.56] But either way, you end up with a lot of options.
[2781.56 → 2795.22] You see new developments throughout the space in terms of not only like bleeding edge technology developments, but another interesting one is companies that buy older systems that are being decommissioned and refurbish them and sell them.
[2795.22 → 2796.00] Right?
[2796.00 → 2800.40] That was a non-existent market for the high end of computing.
[2800.56 → 2804.32] And not sell them as furniture, even though I think we would all buy them as furniture.
[2804.38 → 2809.40] You know, the last real one was the Mac Pros, the big aluminum cases.
[2809.50 → 2810.36] And those weren't that comfortable.
[2811.50 → 2811.74] Fair.
[2811.74 → 2811.76] Fair.
[2812.18 → 2815.82] So, yeah, I mean, it's interesting to see where this is all going.
[2816.08 → 2823.10] I think OCP is one of those, if you look at it from, well, I should be able to buy this infrastructure and play like the hyperscalers.
[2823.60 → 2825.20] It's not complete, right?
[2825.26 → 2830.80] There's an understanding that the hardware is there, the mechanical infrastructure, et cetera.
[2831.04 → 2832.62] You might be able to purchase it.
[2832.82 → 2834.28] The software story is still complicated.
[2834.66 → 2837.68] I feel like OCP Summit, there was no Kubernetes talk at OCP Summit.
[2837.98 → 2838.20] Thank God.
[2838.48 → 2840.12] Like you act like this is a bad thing.
[2840.12 → 2841.08] It's like, I'm relieved.
[2841.36 → 2849.42] I felt like it was, yeah, no, I was in a Kubernetes free zone, which is kind of ironic because it's like you'd think that these two demographics have a lot of overlap, but it's good.
[2849.46 → 2849.98] It was refreshing.
[2850.18 → 2850.92] It was refreshing.
[2851.50 → 2852.26] Especially for Jess.
[2852.42 → 2853.42] It felt great.
[2853.50 → 2855.38] I was like, wow, I like this conference a lot.
[2855.52 → 2856.52] It was a lot of fun.
[2856.78 → 2859.26] And I mean, who doesn't want to geek out over hardware?
[2859.48 → 2859.94] It's good stuff.
[2860.06 → 2863.52] No, that was, I mean, having the hardware there is like just a treat.
[2864.10 → 2866.78] Yeah, the vendor hall there is a lot more entertaining than other conferences.
[2866.96 → 2867.70] Oh, it was great.
[2868.12 → 2869.08] And so, Rick, what are you excited about?
[2869.08 → 2869.50] Looking forward.
[2869.50 → 2873.52] I mean, you're still having fun at the hardware software interface, clearly.
[2874.28 → 2874.38] Yeah.
[2874.50 → 2876.26] I mean, that's my career in a nutshell.
[2876.90 → 2877.08] Yeah.
[2877.26 → 2883.62] Right now, it's a lot of pushing on the security story around firmware, raising that awareness.
[2883.62 → 2895.06] It's amazing that for all the work that's gone into things like secure boot and verified boot on client-type devices, that in the server space, it's slower to catch on.
[2895.06 → 2900.56] Also, that all the periphery devices don't get audited nearly the same way.
[2900.56 → 2904.40] How do I know that my hard drive firmware is actually not malicious?
[2904.40 → 2907.90] These are hard questions that the industry hasn't really tackled.
[2907.90 → 2912.60] And talk about there is a domain where I don't think open firmware is ever going to come to the spindle.
[2912.74 → 2912.98] I don't know.
[2913.02 → 2913.70] What do you think on that?
[2914.08 → 2914.22] Yeah.
[2914.28 → 2914.66] I mean, that's...
[2915.22 → 2916.68] That's going to be proprietary forever.
[2916.82 → 2926.20] There are some low-level parts of that are fundamentally like you would be having to know the mechanical parameters of it and for the design.
[2926.20 → 2926.92] It would just be...
[2926.92 → 2927.66] It'd be awkward.
[2928.00 → 2930.68] Well, optimistic that it's going to get better on the server space, I think.
[2930.76 → 2941.44] We're going to actually get some actual true tested firmware and that the open firmware movement is going to continue to grow and blossom and hopefully OSF will be even bigger next year.
[2941.58 → 2944.18] But not lose the feel because I love the feel.
[2944.18 → 2944.62] Not use the feel.
[2944.72 → 2946.84] Also, could they change the currency to not be in euros?
[2947.02 → 2947.28] That was weird.
[2947.28 → 2948.00] No, I liked it.
[2948.04 → 2948.30] It's quaint.
[2948.30 → 2949.44] That was so weird.
[2949.66 → 2950.68] It makes it quaint.
[2950.90 → 2952.72] If they change it, then it would not be as weird.
[2952.72 → 2960.76] I mean, my wife was convinced that our credit card was stolen by someone in Berlin, and she was right to think that because it was like we were being charged 108 euros.
[2960.94 → 2964.72] I think that it's quaint and if they change it, then it will change the feel of it being...
[2965.38 → 2969.58] It's like, you know, I remember when I could go to this conference in Silicon Valley and pay euros for it.
[2969.78 → 2970.04] Yeah.
[2970.44 → 2971.60] Those are the glory days.
[2971.78 → 2974.36] I mean, Nine Elements is a European company.
[2974.36 → 2976.58] Oh, and I honour their European roots.
[2976.74 → 2977.14] I just...
[2977.14 → 2978.14] It was weird.
[2978.72 → 2979.24] But it was great.
[2979.28 → 2979.84] Great conference.
[2980.18 → 2981.04] Yes, it was amazing.
[2981.04 → 2984.70] And the eggs at Facebook are very good, if anyone was wondering.
[2984.80 → 2985.90] Yeah, did you have breakfast at Facebook?
[2986.08 → 2986.26] No.
[2986.82 → 2987.80] It was so good.
[2987.86 → 2989.30] I dream about it like every day.
[2989.38 → 2990.74] Those eggs were epic.
[2991.70 → 2995.34] I mean, normally I feel I would moderate Jess on this, but yeah.
[2995.66 → 2996.50] No, they were...
[2996.50 → 2997.74] They were divine.
[2997.98 → 3000.38] Well, Jess is the one that points out that Facebook kind of acts like your parents.
[3000.68 → 3004.44] No, so the second day we were walking in, and I was like, let's get egg drunk.
[3005.96 → 3007.14] You did get egg drunk.
[3007.38 → 3007.70] I know.
[3007.70 → 3008.82] You didn't just say let's get egg drunk.
[3008.90 → 3009.96] We actually got egg drunk.
[3009.96 → 3010.32] Still egg drunk.
[3010.48 → 3010.80] I know.
[3011.28 → 3013.06] We actually were strung out on protein.
[3013.16 → 3014.48] But they were like perfectly cooked eggs.
[3014.78 → 3015.58] They really are.
[3015.66 → 3016.66] And then we went to a hackathon.
[3016.66 → 3017.88] We went to a firmware hackathon.
[3018.28 → 3020.92] We were with Rick resoldering a...
[3020.92 → 3021.56] That was the best.
[3021.86 → 3022.38] It was the best.
[3022.42 → 3023.24] It was the best.
[3023.38 → 3024.02] That was so much fun.
[3024.22 → 3027.12] I mean, what's a conference without actually taking apart hardware?
[3027.44 → 3027.70] Oh.
[3027.80 → 3029.36] That was the best part.
[3029.62 → 3030.64] It was so much fun.
[3030.72 → 3031.46] And we still have...
[3031.46 → 3032.48] We got that box.
[3032.62 → 3032.86] It's still ripped.
[3032.86 → 3033.32] It was over there.
[3033.56 → 3034.10] We're going to Debra it.
[3034.10 → 3034.66] It's just hanging out.
[3034.84 → 3035.54] It's hanging out.
[3035.82 → 3036.56] All right, Steve.
[3036.56 → 3038.52] You look like you woke up over there.
[3038.70 → 3038.96] Yeah.
[3039.08 → 3040.26] Do you have any questions for us?
[3040.26 → 3041.12] Or there was an air gap.
[3041.52 → 3041.64] So...
[3041.64 → 3041.88] I hate that.
[3042.44 → 3044.42] I do lots of air gaps.
[3044.42 → 3049.18] So, again, having been operating thousands of machines, you know, less than six months
[3049.18 → 3053.12] ago, A, the BMCs that are hanging out on the internet, terrifying.
[3054.20 → 3055.76] But it doesn't seem like...
[3055.76 → 3060.50] I mean, I wouldn't have thought to go have, you know, our operations team or other teams
[3060.50 → 3065.56] go look into what sorts of vulnerabilities we have in the lower level software systems.
[3066.30 → 3068.70] Like, A, like, are people not worried about this?
[3068.76 → 3069.38] And should they be?
[3069.38 → 3074.30] And B, if they are, where does one even start to figure out how exposed they may be?
[3074.54 → 3080.16] So, a lot of it comes down to really having a security group that thinks through your threat
[3080.16 → 3080.80] model, right?
[3080.82 → 3085.74] So, it may be legitimate for you not to think about this space at all, depending upon if
[3085.74 → 3088.50] you are exposed in a lot of other ways that are much more significant to you.
[3088.88 → 3089.88] The security space...
[3089.88 → 3089.90] Okay.
[3090.54 → 3091.80] Well, the security space...
[3091.80 → 3092.62] You've got bigger problems.
[3092.62 → 3096.14] The entire model of security is like, you can't have perfect security.
[3096.28 → 3096.82] It doesn't exist.
[3097.32 → 3100.66] And so, it's a question of how do you allocate your resources to provide the best defences
[3100.66 → 3102.86] against what you anticipate your attacks to be.
[3103.22 → 3109.56] So, if you're really a, you know, public-facing website, you probably have an attack model that
[3109.56 → 3111.32] looks at that as the easiest venue.
[3111.52 → 3117.42] And so, someone doing a supply chain attack against your machine is very low on your list,
[3117.62 → 3117.80] right?
[3117.84 → 3119.06] It may be difficult to solve.
[3119.18 → 3122.04] It may be you're actually relying on your vendor to solve that for you.
[3122.04 → 3127.36] So, there are legitimate reasons why, especially smaller companies, you may not...
[3127.36 → 3128.72] It just may not be in your threat model at all.
[3129.12 → 3134.34] Now, why is the space so terrible in terms of the security today?
[3134.64 → 3139.92] Well, I like to think of it as how the industry changed around web security, right?
[3139.92 → 3143.88] If you look back to the early days of the web, like, there was...
[3143.88 → 3145.00] It was completely open.
[3145.12 → 3146.76] Nobody really was thinking through security at all.
[3146.90 → 3148.08] And over time, it evolved.
[3148.08 → 3153.10] But it got reached a point where the security community felt they needed to actually establish,
[3153.30 → 3156.48] these are the 10 most common problems that we see.
[3156.58 → 3158.44] And everybody keeps repeating these mistakes.
[3158.94 → 3163.46] And what we've found is that the complexity of actually building proper implementations
[3163.46 → 3169.46] that avoid all of these risks is so hard that we need to actually call attention to these
[3169.46 → 3172.26] problems that you need to focus on and do the right thing.
[3172.26 → 3174.78] That worked really well in that community, in that space.
[3174.78 → 3181.50] And so, that's driven a lot of what you see in terms of the security developments in the web arena.
[3181.72 → 3185.94] But when you look toward system firmware, because it's a smaller set of companies,
[3186.08 → 3194.18] because the idea of cloud-based system hosting and bare metal clouds and things like that is relatively new,
[3194.18 → 3199.16] you're dealing with a lot of folks who've not been exposed to the mindset of thinking like an attacker.
[3199.66 → 3203.36] So, they're not building the defences in, right?
[3203.40 → 3205.56] The assumption is the firmware is the first thing that runs.
[3205.68 → 3207.34] It needs to have full access to the machine.
[3207.46 → 3208.62] It needs to do what it does.
[3209.12 → 3211.42] And the only thing it's going to talk to is the OS.
[3211.48 → 3212.64] And I don't need to worry about that.
[3212.84 → 3214.04] That landscape is changing.
[3214.04 → 3217.78] Do you think that Spectre and Meltdown helped open eyes in terms of,
[3217.82 → 3223.14] I think Spectre and Meltdown were such a shock to the system about the bedrock that we've been relying on for so long.
[3223.72 → 3228.68] All of a sudden, the firmware vulnerabilities that have been found exploded after Spectre and Meltdown.
[3229.32 → 3235.58] Do you think that they played any role in kind of shining a bright light down Stack?
[3235.78 → 3237.60] I think it certainly helped gain a lot of awareness.
[3237.98 → 3241.90] I mean, there's been a lot of security vulnerabilities in firmware for a long time.
[3241.90 → 3245.28] Did they receive the same attention from the press?
[3245.80 → 3246.54] Not really.
[3247.00 → 3249.80] Spectre and Meltdown really had the implication of,
[3250.22 → 3252.74] these are bugs that cannot be fixed, right?
[3252.98 → 3254.46] That was kind of the big thing.
[3254.64 → 3257.26] You can mitigate them, but you cannot fix them.
[3257.42 → 3260.68] That was the message that really started to get people to think about,
[3260.92 → 3265.64] my hardware might be broken in a way where I have to take significant performance hits or do something about it.
[3265.88 → 3268.96] And the cycle for mitigating it might be months.
[3269.46 → 3270.50] And that's very uncommon.
[3270.50 → 3275.00] Like, if you think about, if I find a vulnerability in a software package,
[3275.38 → 3278.84] it's likely that there'll be a patch out in days, weeks.
[3279.14 → 3283.20] You know, three months is actually the normal vulnerability disclosure window.
[3283.90 → 3287.02] But in hardware, it could easily be a year.
[3287.36 → 3290.56] Do you think as people start running more cloud-like systems,
[3291.32 → 3294.20] there may emerge a top 10 or a top 5 or a, you know,
[3294.20 → 3300.32] make sure you've checked these aspects of your infrastructure as a best practice?
[3300.50 → 3300.90] Yeah.
[3301.06 → 3306.74] I guess I characterize it as the main thing that happens at to hyperscale and in the cloud place is that the
[3307.14 → 3310.48] in traditional enterprise, you had a machine owner, right?
[3310.52 → 3316.48] The end owner of the machine was running their application and they sort of owned that whole system top to bottom
[3316.48 → 3322.06] and relied upon your IT department to basically make sure that it was powered on and cooled.
[3322.06 → 3327.08] And if it needed hardware, that they would actually be the hands to go fix it.
[3327.08 → 3336.26] But when you look at the cloud space and how the world of running things like Kubernetes and OpenStack and various systems,
[3336.50 → 3338.74] you're starting to move more to a multi-tenancy.
[3339.16 → 3347.48] You're starting to move toward the owner of the machine is probably more of an operations group that deals with the job scheduling service.
[3347.48 → 3351.82] And they're relying on the physical hardware as a service from the IT department.
[3352.04 → 3355.58] And then you have actual application owners further up the stack.
[3355.98 → 3361.88] And so the assumption that it's the end application owner's responsibility for the whole machine.
[3361.88 → 3366.96] And so we don't need a lot of security because they just get the whole machine, and they're the only ones that are on it.
[3367.32 → 3368.66] It starts to break down a lot.
[3369.28 → 3375.92] And along with that, you see, well, okay, we had all these security features because we thought somebody might want this someday.
[3376.46 → 3377.66] Do they actually work?
[3378.76 → 3385.70] And a lot of times what we're finding are actually vulnerabilities in the security features where they've been either misconfigured or simply not enabled.
[3386.30 → 3386.44] All right.
[3386.46 → 3389.84] Well, Rick, thank you very much for being with us on The Metal.
[3390.32 → 3390.90] Yes, thank you.
[3390.90 → 3392.32] A terrific conversation.
[3392.50 → 3393.26] Thank you for having me.
[3393.34 → 3393.62] All right.
[3393.66 → 3394.10] Until next time.
[3394.26 → 3394.38] Thanks, Rick.
[3395.42 → 3399.46] You've been listening to On The Metal, tales from the hardware software interface.
[3399.88 → 3405.88] For show notes, to learn more about our guests, or to sign up for our mailing list, visit us at onthemetal.fm.
[3406.34 → 3408.74] On The Metal is a production of Oxide Computer Company.
[3408.96 → 3412.10] It is recorded in the Oxide Garage in Oakland, California.
[3412.76 → 3415.72] To learn more about Oxide, visit us at oxide.computer.
[3416.14 → 3419.24] On The Metal is hosted by me, Brian Cantwell, along with Jess Fresnel.
[3419.24 → 3421.90] And we are frequently joined by our boss, Steve Tuck.
[3422.16 → 3424.42] Our original and awesome theme music is by J.J.
[3424.50 → 3426.04] Wrestler at Pollen Music Group.
[3426.30 → 3427.42] You can learn more about J.J.
[3427.50 → 3430.02] and Pollen at pollenmusicgroup.com.
[3430.38 → 3434.20] We are edited and produced by Chris Hill and his crew at Humble Pod.
[3434.64 → 3440.38] From Jess, from Steve, from me, and from all of us at Oxide Computer Company, thanks for listening to On The Metal.
[3440.38 → 3470.36] We'll be right back.
[3470.38 → 3500.36] We'll be right back.
