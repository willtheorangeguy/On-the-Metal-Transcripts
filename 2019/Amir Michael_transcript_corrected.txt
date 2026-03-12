[0.00 → 16.64] Welcome to On The Metal, Tales from the Hardware Software Interface.
[16.94 → 20.16] I'm Brian Cantwell. With me, as always, is Jess Frizzell. Hey, Jess.
[20.40 → 21.00] Hey, Brian.
[21.32 → 23.92] Joining us as well is our boss, Steve Tuck. Hey, Steve.
[24.20 → 24.56] Present.
[24.84 → 26.60] All right. Keep us in line.
[26.60 → 29.68] And Jess, you want to introduce who we have in the garage with us today?
[29.68 → 34.86] Yeah. So today we have Amir Michael. And yeah, we're hanging out in the garage like usual,
[35.08 → 40.84] talking about hardware and going to production with hardware. So we're really excited to hear
[40.84 → 44.06] all the stories that he has to tell because he has a lot of experience in this area.
[44.28 → 45.64] And Amir, welcome to the garage.
[45.88 → 46.88] Thank you. It's great to be here.
[47.26 → 51.96] You are a true child of Silicon Valley. You grew up here. You're a local.
[52.34 → 54.58] I am. Born and raised in Foster City, California.
[54.74 → 57.54] There you go. So your parents must have been in tech?
[57.54 → 62.92] My dad was in tech. My mom was a teacher. My dad came here in the early, early 70s
[62.92 → 68.46] and studied at Berkeley and joined Fairchild Semiconductor. He had a couple of internships.
[68.74 → 73.48] And once he finished, he joined one of the pioneers of Silicon Valley when they're actually
[73.48 → 75.70] making silicon in the valley.
[76.06 → 80.18] That is amazing. And do you remember him working at Fairchild? Did you?
[80.72 → 86.20] Not at Fairchild. By the time I was born and have memories, he was already at AMD.
[86.20 → 91.62] Wow. And so you must have had stuff lying around the house. Was he bringing home interesting things?
[91.62 → 97.60] Oh, yeah. You know, they had wafers that they went through the fab process and which got rejected.
[98.26 → 102.98] And he would bring them back home in carriers. And I'd take the wafers and hang them up on the wall
[102.98 → 106.92] with some tape. And that's how I decorated my room with wafers.
[107.26 → 112.40] Whoa, that is so dope. Instead of like those glow in the dark stars, it's so much better.
[112.66 → 115.16] Okay. So how old are you at this point putting wafers up on the wall?
[115.48 → 117.46] Oh, it was elementary school, I think. Yeah.
[117.46 → 122.32] That is, I mean, so it wouldn't be child of Silicon Valley. This is a true child of Silicon Valley.
[122.48 → 123.20] That is dope.
[123.44 → 127.24] This is a bedroom adorned with wafers versus posters.
[127.78 → 133.74] Yep, exactly. And he'd also bring back these small plastic boxes that they would put finished
[133.74 → 139.60] chips in them. And I would take the chips and store them somewhere else and use the boxes to
[139.60 → 140.74] keep my Legos in them.
[140.74 → 146.18] So that is awesome. And so were you messing around with electronics then at that age?
[146.22 → 147.72] Or were you, how are you getting into it?
[147.80 → 152.84] Oh yeah. I think by the time I was fifth grade, I'd already learned how to solder.
[153.70 → 157.56] My dad taught me how to connect some batteries to motors and lights and the wires would keep
[157.56 → 161.96] popping off. So eventually he trusted me with a soldering iron and I learned how to solder
[161.96 → 168.24] wires and devices together. And I'd try and fix toys sometimes with solder. Didn't always stick,
[168.24 → 172.40] but I've been doing electronics since a really young age.
[173.68 → 178.36] But this is, I mean, this is like post PC revolution, right? Because we're in the late
[178.36 → 182.24] eighties at this point. I mean, I don't, I don't mean to date you too much here, but late eighties,
[182.28 → 186.92] early nineties even. Okay. So, I mean, a lot of kids are playing with software at this point,
[186.94 → 188.06] but you're, you're in the hardware.
[188.42 → 194.76] Yeah. Not that I didn't play computer games, right? We had no XT was my first computer. I think it ran at
[194.76 → 199.88] two megahertz and maybe a little faster when you hit the turbo button. But yeah, it was into
[199.88 → 206.90] electronics. I loved building circuits. I loved attaching motors to different devices, making
[206.90 → 212.14] them spin. If it was Lego, I'd put a fan on it and blow the car around the living room or whatever
[212.14 → 218.14] it was. I just always liked the physical nature of it, being able to put something together and
[218.14 → 225.86] actually feeling and touching it. I would buy kits and go to Radio Shack and buy parts and put
[225.86 → 232.62] together different types of kits and sensors. I remember once I put a motion sensor onto a buzzer
[232.62 → 239.32] and hit it under my bed. But anytime anyone walked by it, it would start to beep and startle them.
[239.84 → 244.44] My mom was not happy, especially when she came in to clean my room or vacuum or whatever,
[244.44 → 247.84] but it would annoy her. But those are the types of things I love doing.
[248.16 → 250.62] That is great. Jess, do you know what the turbo button is?
[250.86 → 253.58] I of course know what the turbo button is. I have a computer.
[253.90 → 257.90] You don't have to be so indignant. You know, there's a generational divide. You don't always
[257.90 → 260.48] know what the audio is. But I have a computer inside with a turbo button.
[260.52 → 264.24] Okay. Well, I have found there's an entire generation that does not know what the turbo button is.
[264.24 → 266.48] So just wanted to. I'm not a part of that generation.
[266.52 → 269.24] All right. That's fine. And there's going to be a future generation that's not going to know
[269.24 → 272.94] what Radio Shack is, sadly. That's another one that's a little more recent.
[272.94 → 277.30] So I grew up messing around with hardware, scaring your mom.
[278.46 → 281.88] And then when you went to school, you knew this is what you were interested in?
[282.14 → 288.44] Oh, yeah. Even before that, we had our own computer. It took a while until my dad agreed
[288.44 → 293.30] to upgrade that. But when he was willing to fund it, then I had fun picking out parts and
[293.30 → 297.60] deciding what I wanted to build. Obviously, it was all what they call today white boxes,
[297.60 → 302.32] where you'd go and buy your own motherboard, your CPU, hard drives, and kind of piece everything
[302.32 → 311.84] together. And I built my first computer myself, which was a good experience. And the types of
[311.84 → 317.44] friends I had been really into that as well. We'd talk about graphics cards and monitors and
[317.44 → 321.66] processors and what we wanted to get and how we'd update them.
[321.66 → 328.52] I'm envisioning like Lil Rascal's Foster City, mid-80s, like Silicon Valley youth gang,
[328.68 → 330.98] you know, making their own machines.
[331.30 → 331.44] Yep.
[331.80 → 334.58] It sounds like a dream childhood, honestly.
[334.72 → 335.44] That's really dope.
[335.60 → 340.78] And of course, we'd swap around floppy disks with different programs or games on them.
[340.78 → 346.36] And then once everyone, you know, my first friend got a modem, that was a game changer too.
[346.68 → 347.14] Oh, yeah.
[347.14 → 347.44] Connected.
[347.64 → 347.80] Yeah.
[347.90 → 353.04] We'd dial into different BBSs and, you know, you'd get programs or whatever it was.
[353.38 → 354.38] All right. Don't flip out on it.
[354.38 → 355.34] I know what a BBS is.
[355.34 → 355.58] Okay.
[355.78 → 359.06] I knew it was coming and like-
[359.06 → 364.00] Again, it's like, it's a generational thing. It's not a condemnation. But did you ever use
[364.00 → 364.26] a BBS?
[364.26 → 368.72] Okay. So I know what they are, but no, it's almost like how I have the IBM basic manual.
[368.84 → 368.98] Okay.
[368.98 → 369.84] Like it wasn't my manual.
[369.98 → 372.24] So it is a reasonable question to ask you what a BBS is.
[372.24 → 372.34] Yes, yes.
[372.68 → 375.76] Now, Steve, you and I are roughly the same vintage, but I think you were probably too
[375.76 → 376.84] cool to be using BBSs.
[377.04 → 379.68] I don't know about too cool, but was not using BBSs.
[379.68 → 383.12] Yeah. Steve was too cool, which is good. I mean, that's a compliment. That's praise.
[384.00 → 389.36] So you are, so tell us about the machine that you, that early machine that you pulled the
[389.36 → 391.04] motherboard for and everything else.
[391.04 → 397.28] Yeah. It was a Pentium 100 megahertz. I think I had maybe eight megabytes of RAM on it,
[397.38 → 402.92] which was a lot in the days. Maybe a couple of hundred megabytes on the hard drive. Don't
[402.92 → 407.64] quite remember then. But yeah, eventually installed the modem in that guy too and started dialling
[407.64 → 412.56] in and playing different online games with my friends too. Well, online wasn't quite the
[412.56 → 417.06] word. It was point to point. So you would dial their home and their computer would pick
[417.06 → 419.18] up, and then you'd play your multiplayer game that way.
[419.54 → 420.26] Yeah, that's cool.
[420.26 → 425.20] And multiple, so this is now, we've got to be in the early nineties at this point. Is
[425.20 → 425.34] that?
[425.46 → 425.64] Yep.
[425.80 → 429.14] With a hundred megahertz. You can always date someone from their, their clock speed.
[429.32 → 431.94] I think I got that in 95.
[432.20 → 437.14] 95, right. Yeah. Yeah. Something like that. Okay. So you are, so the internet is beginning
[437.14 → 437.58] to happen.
[437.84 → 438.02] Yep.
[438.28 → 441.32] And so you're actually doing, actually able to do some interesting things online.
[442.60 → 444.38] Cool. Sorry. So then you head off to school.
[444.60 → 448.10] Yep. Went to UCSB, studied electrical and computer engineering.
[448.10 → 456.42] Again, it was good as far as developing good social relationships with other hardware geeks
[456.42 → 461.86] like myself. And that's primarily what we did is we had something called the LAN at the
[461.86 → 463.42] time in the dorms, and you could-
[463.42 → 464.32] Could you repeat that word?
[465.04 → 466.72] The LAN, the local area network.
[466.72 → 470.00] I'm going to be saying this because I like to call it LAN.
[470.22 → 472.28] So Jess calls it a LAN.
[472.60 → 474.78] Okay. But it's only for troll.
[475.16 → 477.86] Can we describe the look that Amir just gave you?
[477.98 → 478.16] Yeah.
[478.16 → 479.96] I know. I saw it. I saw it.
[480.06 → 480.98] I did not hear this.
[481.52 → 482.10] That is troubling.
[482.10 → 488.22] Yeah. It's so it's like when you say you like to call it a LAN, it is a LAN.
[488.58 → 489.34] It is a LAN.
[489.50 → 490.12] It is a LAN.
[490.26 → 495.92] Okay. I will admit that, but I do like to say WLAN because it makes the cringe look.
[496.10 → 497.10] I just cringed again.
[497.72 → 498.12] Just again?
[498.70 → 502.86] It's very cringe. I think, you know, those cringes are social cues that you should stop
[502.86 → 507.24] doing it. All right. Amir, I'm so sorry. You never know where you're going to step on
[507.24 → 508.16] a LAN mine around here.
[508.28 → 509.06] Or a lawn mine.
[509.90 → 515.48] All right. So yes, you're on the LAN.
[516.02 → 521.60] Yep. Made it even easier to share files and being even more geeky with your friends.
[522.22 → 527.54] Obviously, back then you were doing a lot of things like running wares where you would
[527.54 → 534.22] share programs that maybe you weren't supposed to be sharing with your friends. And you had
[534.22 → 538.78] corporations who paid for software, but almost no one else did pay for software back then.
[539.06 → 544.30] You know, you're raising kind of an important point about the role of mischief in it. Because
[544.30 → 549.00] I think for certainly when I look back, mischief played an important and if it was phone freaking
[549.00 → 553.92] or if it was kind of wares sharing. And as a parent, like I'd want to discourage mischief.
[554.26 → 554.56] Oh, yeah.
[554.74 → 558.32] But as a kid, like mischief was an important part for like, and you're talking about, you
[558.32 → 561.78] know, scaring your mom when you're, I mean, mischief plays an important role.
[561.78 → 565.36] Yeah. That's how you learn. I mean, if you wanted to do cool things, you had to figure
[565.36 → 568.90] out, you didn't have money back then. You had to figure out how to, how the technology
[568.90 → 572.22] worked and how to get it to work in your favour. CD burning was a big one too.
[572.36 → 572.86] That's right.
[573.18 → 573.32] Yeah.
[573.90 → 575.36] And now I'm not even going to ask for that one.
[575.54 → 578.86] No, I also know of wares. I mean, I got in trouble for that a lot.
[579.38 → 580.16] I can imagine.
[580.62 → 581.90] Oh, I thought you were going to ask about CD burning.
[582.58 → 583.88] That'd be tough if she didn't know that.
[583.88 → 589.84] So, so you're messing around on the land and presumably doing things in software as
[589.84 → 591.94] well. I mean, doing both computer science and computer engineering or what?
[592.10 → 596.62] Yes. Software started actually early. I think in, well, another hobby I had was radio control
[596.62 → 600.58] cars. I love them. And that's how I learned actually a lot of electronics too and mechanics.
[601.12 → 606.04] There wasn't much software, which was a problem because you go to, you'd want to race your friends
[606.04 → 612.42] and how did you know who was faster? And so on my XT, that slow computer, I actually built
[612.42 → 620.00] a program that tracked the time of these cars going around this course, and you'd get lap
[620.00 → 624.44] times from them, and it would show you who was faster. And in the end of the race, it
[624.44 → 629.96] would tell you who did the most laps in the least amount of time. And I would drag my computer
[629.96 → 635.10] out to the field with some extension cords and my friends would get our car set up.
[635.28 → 640.48] And then someone had to be behind the keyboard to key in the appropriate buttons when the car
[640.48 → 644.60] crossed the start finish line. And so I wrote a program, I called it Race Master.
[644.84 → 650.62] Race Master. Oh, that is such an 11-year-old name for a program.
[650.88 → 652.24] Yep. I wrote it in Turbo Pascal.
[652.54 → 658.24] Oh, Turbo Pascal. You're close to a Turbo Pascal manual, I think. After you write somewhere,
[658.34 → 661.88] there's a Turbo Pascal manual. I've got such fond memories of Turbo Pascal.
[662.24 → 668.50] Yep. And that was the first program I wrote. I was living in Israel at the time. My dad had
[668.50 → 673.76] relocated there for a job over at National Semiconductor. And I had a group of friends
[673.76 → 682.48] who liked to race cars and were geeks as well. And we wanted to be able to keep time. And so I said,
[682.66 → 688.52] my friend had taken a private class in Turbo Pascal programming. It was popular then for parents to get
[688.52 → 692.92] programming tutors for their middle school kids. I don't know why.
[692.92 → 697.74] And that's awesome. I just, I had a book and I said, can I just borrow the book and taught myself
[697.74 → 700.76] how to program Turbo Pascal? All right. Do you remember what version of Turbo Pascal?
[701.18 → 703.04] No idea. Are we talking like 5.5? Are we talking?
[703.34 → 711.36] I don't remember. Turbo Pascal is amazing. It is so, it was then fast. This is Anders Heidelberg,
[711.36 → 718.84] who, who, yeah. Oh, yeah. Of TypeScript? Of, yes. And of Microsoft name. And Anders was at
[718.84 → 726.98] Boland where they did Turbo Pascal. And it was very fast on a, on a PC AT or on a 386SX or on a
[726.98 → 732.90] 100 megawatts Pentium. I, we should get Turbo Pascal running today on a modern CPU. I mean, it would,
[733.34 → 738.02] it would. So what happened to it? It would travel backwards in time. It was so fast. I think it's,
[738.02 → 742.16] I don't know what happened to it. Where the actual artifact is. I don't know. But it was,
[742.16 → 746.74] side note, there is a current player on the Golden State Warriors, Eric Pascal. And the nickname that
[746.74 → 751.72] people are trying to get to stick is Turbo Pascal. Turbo Pascal. That is awesome. That would be
[751.72 → 757.04] amazing. That is awesome. That is trying to connect two demographics that I'm not sure. In the Bay Area.
[758.84 → 762.82] In the Bay Area, you could pull it off. God, Turbo Pascal. I would, I, you know,
[762.92 → 767.88] I'd go to a Warriors game just to watch Turbo Pascal play. Just to watch. That's great.
[768.02 → 771.68] That's awesome. So that was, all right. So you were, you're messing around with software with
[771.68 → 777.14] Turbo Pascal. Yep. Yep. In school, we actually, I was somewhat disappointed. The first programming
[777.14 → 786.04] class that was on the curriculum was Fortran. And I was trying to figure out why in 97,
[786.58 → 793.20] they were teaching incoming freshmen Fortran. And I did eventually figure it out. The, the instructor
[793.20 → 799.86] we had many years before had written a book on Fortran and likely needed to increase his book sales.
[799.86 → 801.88] So that was the first, first class we took.
[801.88 → 806.30] Okay. Well, so F77 or F90. Do you remember?
[806.46 → 806.66] No.
[806.98 → 811.80] Because I actually feel Fortran, there's still a lot of Fortran being written.
[812.48 → 815.62] Yeah. No, people definitely use Fortran.
[815.66 → 820.54] Because they got these mathematical codes correct for, especially in the sciences, there is still,
[820.94 → 823.90] Fortran being written is maybe a bit strong. There's a lot of Fortran that's out there.
[824.14 → 824.44] Maintained.
[824.76 → 828.64] Why am I defending your teacher's terrible decision to teach you Fortran? I'm sorry. I don't want to be,
[828.64 → 832.96] so, all right. So you were being deprived with, with Fortran programming in high school or?
[833.58 → 834.22] In college.
[834.36 → 838.16] In college. Okay. That, college that is bad. I don't know why high school feels like it's less
[838.16 → 839.76] child abuse than, than college, but.
[839.76 → 844.80] Yeah. Maybe because the, the, the teacher had also been as part of the college of engineering
[844.80 → 847.88] and the electrical engineering department, not necessarily the computer science.
[848.02 → 848.34] Uh-oh.
[848.56 → 851.38] Perhaps thought it was a better lower level language. I'm not sure.
[851.52 → 856.72] Yeah. No. All right. So you're, so you're getting a bad taste for software from Fortran.
[856.72 → 862.04] Yeah. Uh, luckily it was only a quarter's worth, uh, and then quickly moved on from there to
[862.04 → 866.58] more, more modern languages. Call it C for, for example.
[866.90 → 870.70] Well, you were lucky you were in C because I feel that that is a time that is now,
[870.78 → 876.46] because now we're in the 2000s, right? Maybe the, the early 2000s. I feel like Java kind of
[876.46 → 878.36] displaced everything for a while there.
[878.62 → 883.94] Yeah. Incoming, uh, uh, freshmen in computer science started with Java. The electrical and
[883.94 → 886.54] computer engineers started with Fortran and then C.
[887.16 → 890.78] Fortran and then C. So I actually think you, you kind of got the better half of that deal.
[890.92 → 891.26] I agree.
[891.56 → 897.06] Fortran is a is, is a little bit of an annoying price to pay, but, um, at least you got something
[897.06 → 899.26] that's closer to the metal with, with C.
[899.48 → 907.54] Yeah. Yeah. And I actually wrote some code for Facebook, I'd say probably in 2010 for Meccas.
[907.54 → 909.44] That was all in C. So that, that came in handy.
[909.56 → 913.46] Oh God, I was so hoping that was going to be Fortran. I was really, really, I was, as soon
[913.46 → 915.92] as you went to Facebook, I'm like, please let there be some Fortran on Facebook. But no,
[915.98 → 921.48] of course. Yeah, there you go. So it came in handy. Um, but coming out of school, um, you were
[921.48 → 924.00] still, you're doing hardware effectively in school.
[924.24 → 930.56] Yeah. Uh, graduated in, in 2001, basically did hardware, built a, um, a four bit microprocessor
[930.56 → 931.94] as one of our final projects.
[931.94 → 933.90] That was great. That is so much fun.
[933.90 → 939.24] That was a tough one. And I remember it was, uh, due basically the week before finals and
[939.24 → 944.46] we had spent maybe three weeks in the lab on the fifth floor of the engineering building.
[944.46 → 949.76] You stare down, um, from the engineering building at the beach below, uh, and you had all the
[949.76 → 958.18] history majors and communication majors studying in quotes, uh, on the beach, uh, in the sand.
[958.18 → 961.66] Yeah. And we're up in the lab trying to finish this project. Uh,
[961.94 → 963.86] and we did finish it and it worked. Um,
[963.86 → 966.60] See the cruelty there is that you had, they had windows. They shouldn't have had windows.
[966.68 → 969.02] If there were no windows, then you would have been just in a cell.
[969.22 → 972.08] Yeah. Yeah. It wouldn't have known anything about the reality outside.
[972.22 → 977.20] Right. I think most engineering campuses have just, just have no windows. So, um,
[977.26 → 980.76] what was the four bit microprocessor? I mean, was that, was that an FPGA that you were putting into
[980.76 → 981.40] or what were you?
[981.66 → 987.36] One, one portion wasn't FPGA. A lot of the glue logic was done in FPGA, but, uh, the majority of
[987.36 → 991.72] it was just in discrete logic chips. So we had an ALU, we had some, uh, memory,
[991.94 → 999.40] we had shift registers, we had mixes, probably we built it on bread boards. Uh, those are,
[999.46 → 1004.46] those are, uh, boards, uh, plastic usually with lots of holes and conductors underneath.
[1004.46 → 1009.94] So you could put in a dip package, a dual inline package, which had a, um, which is how a lot of
[1009.94 → 1014.70] microchips used to be packaged back then. Basically a piece of plastic with these small conductors
[1014.70 → 1019.06] coming out of them that you'd stick into these, these boards with holes in them, and they would make,
[1019.06 → 1024.10] you would conduct underneath, and then you'd take wires or old like telephone wires and then, uh,
[1024.10 → 1025.66] connect between the chips that way.
[1026.44 → 1029.12] And then spent a lot of time with the logic analyzer on that project for sure.
[1029.36 → 1034.78] Logic analyzer, uh, oscilloscopes, voltmeters, everything. Uh, and so you, you would take
[1034.78 → 1038.62] this, and we had three breadboards where, so I think about maybe something that was,
[1038.62 → 1045.60] oh, I don't know, maybe 18 inches by 12 inches of a big rat's nest of wires. Um,
[1045.60 → 1050.74] which was made it hard to debug. We started off very neat, but once you, it was fairly complex.
[1050.74 → 1052.28] We had a lot of wires going everywhere.
[1052.72 → 1054.72] And it was a group project or individual project?
[1054.74 → 1058.90] Yeah, there was, it was a group project, three of us. Um, and you would write and, uh,
[1058.90 → 1064.78] came up with your own assembly code that would run the processor. Uh, and then you would program
[1064.78 → 1071.50] that into, uh, some, some EEPROM, uh, which is like today you might think of EEPROM as flash,
[1071.50 → 1077.90] perhaps. Um, and, uh, your, your goal was to have it execute a certain series of its instructions.
[1078.22 → 1081.40] Uh, and that was actually fun because it was glorious to get it all working.
[1081.40 → 1084.48] Oh yeah. Once it was working, it was, you didn't want to sneeze on it because
[1084.48 → 1088.54] if one of the wires came loose, it would have been hard to figure out what happened.
[1089.36 → 1093.68] And then, uh, and then you could, you could adjust the clocks manually and then basically
[1093.68 → 1097.94] you would turn it up to see how fast or how much you could overclock that little four bit
[1097.94 → 1099.74] processor. And what'd you get to?
[1099.74 → 1101.18] I think we got it to about eight megahertz.
[1101.40 → 1103.86] That is great. Isn't that, that is great. What a project.
[1104.00 → 1104.18] Yeah.
[1104.38 → 1108.54] You know, I've always fantasized about having a project where you build your own microprocessor,
[1109.18 → 1113.34] then you build your own operating system, you build your own, you have a, a, an entire
[1113.34 → 1119.08] systems curriculum where you build it all from the bottom. But I know, because I mean, you,
[1119.16 → 1122.24] you learn so much about the way things work from that.
[1122.24 → 1126.72] Oh yeah. You have to get into every little detail. That's amazing. It was a it was a fun
[1126.72 → 1130.54] project for sure. A good way to finish off the four years of undergraduate electrical
[1130.54 → 1130.94] engineering.
[1131.10 → 1134.42] Yeah. And meanwhile, you know, that, that history concentrator that was out there, you know,
[1134.42 → 1137.90] throwing the Frisbee around, you know, they're, they're wishing they understood the four bit
[1137.90 → 1138.48] of my capacitor.
[1138.98 → 1139.84] I'm sure they are.
[1139.86 → 1143.50] I, you know, I'm just pointing off into the distance. I'm not, you know, I'm not pointing.
[1143.84 → 1146.78] First, I mean, Wisconsin was too cold for the Frisbee eyes.
[1146.78 → 1148.26] At least with sweaters and sweatpants.
[1149.48 → 1149.88] Exactly.
[1150.18 → 1150.32] Yep.
[1151.06 → 1156.78] The best part was you called the project, the burp, the basic undergraduate risk processor.
[1157.22 → 1159.84] That is a good name.
[1160.00 → 1160.80] That's a good name.
[1161.10 → 1165.50] The burp is good. And so, all right. So then you are now into your career.
[1166.24 → 1172.10] Not really. So that was a graduate in 2001.com bubble had just exploded.
[1172.10 → 1180.50] Uh, and in the first part of my senior year, I had offers, uh, for jobs. Uh, I had internet
[1180.50 → 1187.44] Cisco Systems for two years. Uh, HP, you know, wanted to interview me for a position in their
[1187.44 → 1194.00] AIO department, which was all in one printer scanner, fax machine, whatever it was. Uh, and
[1194.00 → 1197.74] that, that was when I started my senior year and things were great. And I said, look, uh,
[1197.74 → 1201.80] I'm not going to decide where I'm going to work now. Let's talk towards the end of my
[1201.80 → 1207.50] year. Uh, then January came around, everything had crashed. I'd called up,
[1207.92 → 1208.62] Oh man.
[1208.84 → 1212.12] Called a bunch of these companies and said, look, we're not hiring. We're actually laying
[1212.12 → 1216.22] off people. So I graduated without a job.
[1216.90 → 1221.50] Isn't that, it's amazing to think about that, about that time. I mean, I feel like this is
[1221.50 → 1227.38] like our role is like, and I think, you know, Jess, this is, this is, uh, too, too old for
[1227.38 → 1231.26] you. Right. I mean, you were in 2001, you were not in the, in the labour market, certainly.
[1231.26 → 1235.12] Yeah. Yeah. So you don't know what it was like. I mean, I feel like Steve, you, uh, you, Amir
[1235.12 → 1238.90] and I were, we're children of the depression in this regard, explaining like, actually.
[1238.90 → 1244.02] Got there in late 99 and went to Dell in October 99, just to watch the bottom fall
[1244.02 → 1247.36] out. Yeah. I mean, you got there when the times were still good for a few months.
[1247.56 → 1254.08] Yeah. We, and I hired an undergraduate in 2001, and it had to be approved by the CEO. It was
[1254.08 → 1256.74] a huge deal to get a single undergraduate hired.
[1256.74 → 1260.04] That's insane. Yeah. It was bad. So you come out without a job.
[1260.16 → 1264.22] Yeah. I had friends who graduated with a four-year engineering degree and went to go work at Best
[1264.22 → 1266.06] Buy. Whoa. Whoa.
[1266.36 → 1267.62] Yeah. That's how bad times were.
[1268.14 → 1273.50] Yep. So I decided I didn't want to work at Best Buy. Instead, I spent a year volunteering.
[1273.50 → 1280.22] Uh, I did a program similar to Peace Corps in Israel, uh, where you work both with Jewish and
[1280.22 → 1286.72] Muslim children, um, some coexistence programs. Largely, if you're an English speaker there,
[1286.80 → 1292.92] you're naturally going to be used for teaching English. Uh, and so I taught English, uh, for a year
[1292.92 → 1300.86] to kids, uh, in, in marginalized neighbourhoods, uh, both, uh, inside a Bedouin village. It was a lot of fun.
[1300.86 → 1306.96] Um, that is amazing. That is an amazing experience. Yeah. Yeah. I'm now embarrassed about the way that
[1306.96 → 1312.44] I and the rest of humanity spent that year, like wishing for just wishing for the bubble to come
[1312.44 → 1316.60] back. Meanwhile, you're actually doing something meaningful. Yeah. That must be cursing the fact
[1316.60 → 1320.82] you can only get one undergrad. Exactly. I'm right. Exactly. I'm cursing the fact that that must
[1320.82 → 1326.66] have been a hell of a year. Yeah. Yeah. A lot of fun. Um, came back from that, uh, started, uh,
[1326.66 → 1332.28] a small little company. I made battery chargers for model airplanes, uh, and they actually plugged
[1332.28 → 1337.22] into the parallel port of a PC and kept statistics on the batteries that you were charging.
[1337.22 → 1342.00] Are your parents concerned for you at this point? Uh, it's like, mom, don't worry. I've got a plan.
[1342.40 → 1346.74] I know the economy has cratered and there's no future friend sharing. I'm starting a company
[1346.74 → 1354.52] to recharge model planes. Yep. Uh, I, you know, didn't know much back then. Didn't know how to size up
[1354.52 → 1360.04] markets. Right. Uh, I was like, this is a cool device on that one. Yeah. I'm going to use this
[1360.04 → 1365.00] because I love flying model planes. So I want this. Other people must want it too. I'm going to,
[1365.12 → 1368.44] I'm going to do this. And my dad gave me a couple of thousand bucks to help build the first one.
[1368.48 → 1372.76] Yeah. Good for dad. That's great. Yeah. It was awesome. Um, then I quickly found out,
[1372.76 → 1380.66] I think I sold six of them, uh, and didn't, and you saturated the market. Exactly. Uh, you know,
[1380.66 → 1386.76] I didn't realize most of the people who flew these planes were retirees, um, and didn't see the need
[1386.76 → 1391.34] for using a computer to charge batteries. Probably still the case today. Plenty of time on their hands.
[1391.34 → 1397.50] Yep. Uh, and so, you know, I had a girlfriend at the time and she, I'd started looking for a job
[1397.50 → 1403.40] and she found an ad on Craigslist, uh, for a company that needed, uh, someone to help them,
[1403.40 → 1409.56] uh, repair servers. And I said, great, I can do that. Uh, not a problem. Uh,
[1409.56 → 1414.98] and then I sent in my resume and I get a response and the recruiter was from this company called
[1414.98 → 1421.40] Google. Wow. And, uh, I said, wow, the search engine, I guess they should have quite a bit of
[1421.40 → 1427.08] servers. Uh, it should be a lot of, a lot of work to do there. Um, funny part is first time I didn't,
[1427.16 → 1431.88] I didn't, uh, I sent in my resume, I didn't get a response. I sent it in again. I don't remember why,
[1431.94 → 1437.94] but I updated it and I wrote some of the experience I had working with Linux, uh, the second time. And that,
[1437.94 → 1442.66] that got me a response from the recruiter. Really? A four bit mic? It's like, I'm sorry,
[1442.72 → 1447.60] I implemented burp like that. That doesn't wake you up, but like, okay. Yeah. Like, and I, by the
[1447.60 → 1452.50] way, I know how to administer Linux. Like, Oh, now we're interested. Okay. Yep. Yep. Uh, so I went
[1452.50 → 1457.18] and interviewed and got the job there and then was thrown immediately into the trenches. And there was
[1457.18 → 1463.56] almost a hazing there, uh, from the other data centre technicians where, you know, to be a part of that,
[1463.56 → 1469.52] that, uh, culture. Um, they would give you a hard time over, over some of the work you did. I
[1469.52 → 1474.54] remember once, uh, I got yelled at by a senior technician because I put too much grease on the
[1474.54 → 1479.36] CPU. Oh my God. Thermal compound. Yeah. Uh, and that was a hard one to get over, and you know,
[1479.36 → 1483.90] it's your first job, and you take that seriously initially. Well, to be so, okay. That is,
[1484.04 → 1487.58] do you know what he's talking about in terms of the thermal grease? The grease? No. No. Okay.
[1487.58 → 1493.12] This is like, you should explain like the thermal grease because you're actually connecting the CPU
[1493.12 → 1497.68] into the socket at that point. Yep. Uh, this is actually something that will come back to bite
[1497.68 → 1505.22] me later on. Uh, but there, the, the CPU has a, uh, a metal casing around it and that interface is a
[1505.22 → 1510.98] heat sink, which dissipates the heat that the CPU generates to make that connection between the metal
[1510.98 → 1516.94] case of the CPU and the heat sink, uh, more efficient. You can put thermal compound, which is a
[1516.94 → 1522.30] can conduct thermal energy from one material to the next. And it creates a better connection between
[1522.30 → 1527.36] the CPU and the heat sink itself. It makes the cooling more efficient, and you can, you can put too
[1527.36 → 1532.50] much. If that layer is too thick, it doesn't conduct heat as well. If it's just right, it conducts
[1532.50 → 1538.92] heat really well. And so I put too much in that barrier between the CPU and, and the heat sink was,
[1539.16 → 1545.64] uh, not as efficient as a result. And it would have worked fine, but someone was looking for
[1545.64 → 1550.14] something to pick at. Right. And yeah, it was more than an aesthetic issue. Cause there's an
[1550.14 → 1554.42] aesthetic issue too. If you put too much on, right. I mean, I do not have the guts to do this myself.
[1554.64 → 1558.14] It's out this side. It's not a big deal. Yeah. It's not the side, but it's okay. Not a big deal.
[1558.88 → 1563.94] Um, but there's an actual efficiency consequence. Yeah. Yeah. You're you, you won't conduct as much
[1563.94 → 1570.86] heat and then your fans need to spin up to compensate. Wow. And, and in 2002, is that the year at this
[1570.86 → 1576.46] point? 2002, 2003? Yep. Started in 2002. In 2002, the in the Google data centre, this is,
[1576.68 → 1582.10] this is a newbie mistake, I guess. Yep. Yep. So then the hazing begins. One day in the hot aisle,
[1582.20 → 1585.60] one day in the cold aisle. Yeah. It lasted, it lasted about three months. I wasn't even sitting on
[1585.60 → 1591.26] that one. Whoa. Yeah. But you know, eventually you get past that, and you're, you're no longer the new guy.
[1591.66 → 1596.24] And, uh, at that point, you know, things get easier, and then you're training other people. And that was an
[1596.24 → 1603.52] interesting time. We couldn't get racks into data centres fast enough. Um, and, uh, it was expansion,
[1603.70 → 1609.24] expansion, expansion. So it changed quickly from repairing the fleet that they had to building out
[1609.24 → 1615.00] more and more clusters of servers. And this is after the Velcro days, right? Or is this, are the
[1615.24 → 1619.18] there was still Velcro then. There's still Velcro. Do you know about the Velcro? Yeah. Do you guys know
[1619.18 → 1622.66] about the Velcro? Yeah. You should explain the Velcro because the Velcro is definitely a big part of
[1622.66 → 1628.68] Google lore for sure. Right? Oh, for sure. If you think about hardware back then and scale out
[1628.68 → 1633.88] servers, you could, they didn't really exist. You could buy rack mount servers. They weren't at all
[1633.88 → 1639.38] cost-effective. And even from, from the founders, from Larry and Sergey, they had decided that they
[1639.38 → 1645.36] weren't going to pay the enterprise premium on servers. And a lot of the initial Google servers will,
[1645.36 → 1650.66] were built from components with they had, which they had purchased from a local, uh, hardware
[1650.66 → 1656.26] retailer called Fry's Electronics. They would go there. Oh, Fry's. Wow. Oh, Fry's. That's going to
[1656.26 → 1660.64] become a thing in the past too. It is. Oh, it's, it's there. It is. It's a carcass right now.
[1660.74 → 1665.72] That's sad. And they would, they would buy 20 motherboards and CPUs and drives and DRAM,
[1665.86 → 1672.28] put them together and, and, uh, put them on what they called cork boards. Uh, and if you think about,
[1672.28 → 1678.54] well, there was something before that too. Um, you think about a bread rack, uh, at a, at a bakery,
[1678.54 → 1686.00] they have these tall racks that you can slide, uh, basically pans into and bake bread, uh, in volume.
[1686.26 → 1690.56] So they took that concept and said, look, we're going to use that same idea to hold servers.
[1690.80 → 1695.40] We're not going to buy a traditional 19-inch racks. And we're just going to build these very
[1695.40 → 1702.02] inexpensive bread racks and, uh, have a tray and then snap the motherboards on there and the CPUs
[1702.02 → 1708.26] and put some DRAM, some drives and some fans, and that will be our server. And those were largely built
[1708.26 → 1714.42] from commodity components that you could buy at Fry's. Um, I mean, true, not just commodity,
[1714.56 → 1719.10] but consumer grade. Consumer. Yeah. I mean, this is gigabyte motherboards, whatever, whatever was
[1719.10 → 1725.60] there. The initial versions, uh, had a layer of cork between the metal rack and the motherboard
[1725.60 → 1733.20] in order to insulate it. So it wouldn't conduct. Um, and, and that worked fine except for the inspector,
[1733.20 → 1740.24] uh, the fire marshal who would come by the data centre saw the cork, and it was a flammable material,
[1740.24 → 1745.06] which you weren't allowed to have out on the data centre floor. And so eventually they had to get rid
[1745.06 → 1749.60] of the cork. Uh, and so the cork boards were phased out, and they had these things called bread racks
[1749.60 → 1755.76] instead that held the motherboards on standoffs. Uh, so that solved that problem. But there was this
[1755.76 → 1762.54] ongoing evolution of very inexpensive consumer hardware being brought into data centres and being
[1762.54 → 1767.30] used for enterprises, uh, for an enterprise application, call it a scale out application at
[1767.30 → 1772.34] the time. And that was really the first version of scale out hardware, uh, that I think started at
[1772.34 → 1778.32] Google. It was super cheap. Um, they would, the joke was they would buy DRAM that was swept off the
[1778.32 → 1783.74] floor at the factory because it would, it was cheaper, and it had more errors. But if you wrote
[1783.74 → 1789.62] good software that could take into account the errors, it would, it would be cheaper. Right.
[1789.82 → 1794.82] And so you couldn't, the, the, the, the premise was you couldn't rely on the hardware. The software
[1794.82 → 1800.52] had to accommodate that. But as a result, you get cheaper hardware. So this is non-ECC DRAM.
[1800.96 → 1806.68] Oh no, non-ECC. Bad non-ECC DRAM. No error correction at all. There's only so much that software can do
[1806.68 → 1811.78] for, for, for Byzantine DRAM. That can be, uh, that can be a challenge. Yeah. You know, if,
[1811.78 → 1816.64] if it caused a kernel panic or something, that's fine because they had the software could just use
[1816.64 → 1820.30] another server instead. Yeah. Just don't, don't bother debugging that one. That one will be strange.
[1820.70 → 1826.94] That, that was exactly, that was the debug process was very crude. Uh, and you would just
[1826.94 → 1832.28] on mass rip out components and replace them until you found the combination that worked.
[1832.82 → 1836.28] And, and you would throw. It's a real first principles kind of operation there.
[1836.28 → 1841.80] You would throw a lot of good components into the RMA, into the return bin. Uh, I'm sure the
[1841.80 → 1847.20] the false positives on bad hardware was probably very large at that point.
[1847.40 → 1850.72] Right. I mean, it truly is penny wise and pound foolish. I mean, you're actually, uh,
[1850.90 → 1854.56] in the Velcro, does the Velcro predate the cork or postage the cork?
[1854.62 → 1858.78] That's right. We started with Velcro. Uh, no Velcro was from the beginning in the cork boards and in
[1858.78 → 1863.64] the bread racks. And basically you needed a way to hold these hard drives in place. And, uh,
[1863.64 → 1868.14] they would just have a simple mount for the drive, and you would just use a strap of Velcro
[1868.14 → 1872.96] to tie it into place. The interesting thing, the whole premise of that was that you wanted to
[1872.96 → 1878.06] make this server. They had so many of them easy to maintain, right? You had armies of data centre
[1878.06 → 1884.92] techs trying to fix unreliable hardware. So you had lots of failures. And if you could save, uh,
[1885.32 → 1890.78] a few minutes on the maintenance, uh, it was a win-win. And so they made everything really easy for
[1890.78 → 1896.10] the technicians to, to maintain, to rip components in and out. And the Velcro was a key component of
[1896.10 → 1904.82] that. But the Velcro did not survive. Um, yes, it did not survive. Uh, at some point they became
[1904.82 → 1913.02] more serious about the hardware, and they started using ECC, uh, and, uh, the principle of easy
[1913.02 → 1919.20] maintenance remained. They found other solutions, uh, that still made the service just as easy,
[1919.20 → 1924.44] but just happened to not have Velcro. All right. We're going to take a quick break. Um, then we
[1924.44 → 1929.92] are going to be right back with, um, some terrific tales in the hardware software interface with Amir
[1929.92 → 1936.30] Michael. On the Metal is brought to you by the Oxide Computer Company, where we're going to try a new
[1936.30 → 1941.98] feature, shamelessly ripped off of Reply All's Yes, Yes, No, where our boss, Steve Tuck, brings us a tweet.
[1942.14 → 1945.78] He does not understand. And Jess and I try to explain it to him. Steve, do you have a tweet?
[1945.78 → 1953.76] I sure do. The tweet in question, UEFI reboot network stack engaged the onboard Nick in such a
[1953.76 → 1958.94] way that it would write back DMA to particular physical memory pages sometime after control was
[1958.94 → 1963.48] passed to the bootloader. Corruption would occur somewhere in the user parts of the RAM disk.
[1964.24 → 1970.54] No idea. No idea. Jess, do you understand this tweet? So I understand definitely the part about the
[1970.54 → 1976.64] UEFI reboot networking stack, but the part about DMA is in question marks. So it's like,
[1976.78 → 1981.68] I guess you're not really sure where that's going. You're overthinking it. I understand this tweet.
[1982.02 → 1987.50] Running on-prem is painful. This is dealing with an awful, awful firmware bug. The firmware has
[1987.50 → 1992.50] overwritten part of the operating system in a way that is extremely painful to debug.
[1992.78 → 1994.86] So who do you go to in that case? Who do you go to?
[1994.96 → 1996.98] You definitely strangle one of your vendors.
[1996.98 → 2000.40] You strangle one of your vendors. And unfortunately your vendor is a PC vendor because
[2000.40 → 2007.34] all the existing computer companies are selling personal computers. What we need is a new computer
[2007.34 → 2011.92] company. So this is just saying I'm an intense pain trying to run systems on-premises.
[2012.10 → 2015.72] That's exactly what it's saying. Steve, what can someone do if they're intense pain running on-premises?
[2016.00 → 2019.84] Well, if someone is running an intense pain on-premises, what they should do is go over to
[2019.84 → 2024.18] oxide. Computer to learn a little bit more about how we are going to take that pain away.
[2024.18 → 2027.76] Help is on the way. Join us at oxide.computer.
[2027.76 → 2029.10] You are not alone.
[2033.94 → 2042.80] All right, we're back. All right, so Amir, we were with you at Google and Google was beginning to
[2042.80 → 2050.20] realize that having junk components everywhere might not be the best long-term approach.
[2050.20 → 2059.48] Yeah, there was some change in philosophy around that. And I think at some point the supply chain
[2059.48 → 2064.76] perhaps drove a lot of that when they started negotiating for hardware directly with the
[2064.76 → 2074.02] actual vendors. They realized that they could get, you know, there just wasn't enough DRAM on the floor
[2074.02 → 2079.04] of the factory that they could get. There's not enough bad DRAM to sell you.
[2079.10 → 2083.56] The scale had grown so much, right? And so you had to work with the vendors directly,
[2083.68 → 2086.20] meaning you had to be a little bit more grown up at that point.
[2086.20 → 2090.88] It's like we have to buy legit DRAM because there's not enough bad DRAM. That's pretty funny.
[2091.10 → 2097.68] There was that. And quite frankly, the hardware and the designs had started to show some weak points
[2097.68 → 2105.16] too. Not a lot of time was put into the engineering behind it. So for example, we had servers that were
[2105.16 → 2109.26] over-cooled, meaning we were running too much air through them, which made the facility run less
[2109.26 → 2116.84] efficiently. The power supplies, for example, that we wanted to use, we wanted to increase efficiency
[2116.84 → 2120.50] on them. And so you had to start doing custom designs at that point. Interesting.
[2120.50 → 2128.48] Right. Everything had sort of matured along with the supply chain, along with the designs.
[2129.02 → 2134.48] And so when you're at that scale, you're going to spend more time on the design so that you
[2134.48 → 2139.54] have less risk involved. If you made a mistake early on, it wasn't that bad because you didn't
[2139.54 → 2144.12] have that much hardware. But if you're deploying tens of thousands of servers and there's a bug,
[2144.24 → 2146.50] that's a fairly expensive mistake at that point.
[2146.50 → 2151.64] And so you had come into Google as kind of data centre tech answering a Craigslist ad.
[2151.86 → 2154.62] But at this point, it sounds like you're moving on to the design side.
[2154.94 → 2161.58] Yes. So after around nine months to a year of travelling, debugging servers, deploying new
[2161.58 → 2166.24] servers in the data centres, they started becoming more serious around the hardware design.
[2167.24 → 2173.84] And that's really what I wanted to spend my time on. And a lot of the work that they were
[2173.84 → 2178.66] focusing on was around efficiency. They saw big inefficiencies and how traditional servers
[2178.66 → 2185.08] and data centres worked at scale together. And a lot of the ideas were around combining
[2185.08 → 2189.30] the two, the facility, the actual building, the power distribution, the cooling in the
[2189.30 → 2194.96] building and the servers. And that's a really important principle. That's actually what we
[2194.96 → 2199.30] brought, what I brought forward into Open Compute as well, which happened later on in my career.
[2199.30 → 2204.30] But when you can control both the facility and the server, you can do fairly amazing things
[2204.30 → 2205.50] as far as efficiency goes.
[2205.74 → 2210.50] So really, not just rack scale design, but really at that point, even thinking about
[2210.50 → 2212.14] data centre scale design.
[2212.28 → 2214.86] Yeah. They called it warehouse computing at the time.
[2215.10 → 2217.32] Oh, yeah. That's like the book from Earth.
[2217.48 → 2218.86] Yep. That's where it came from.
[2219.02 → 2224.94] Yeah. But that thinking was really very early then. So that's in 2005, it sounds like.
[2224.94 → 2231.48] Yeah. Somewhere around 2004, I remember they had a number of different brainstorming sessions.
[2231.74 → 2238.20] I got to participate in a few of them over how they're going to make this holistic design
[2238.20 → 2242.64] way more efficient. And they looked at things as far as putting microturbines on the roof
[2242.64 → 2248.40] to generate electricity around different types of cooling systems, backup solutions.
[2248.40 → 2253.68] The container was an interesting one as well, the shipping containers.
[2254.40 → 2260.94] And the first sort of custom server facility that they wanted to put together was in a shipping
[2260.94 → 2268.14] container. And so that was about a year that we spent on with optimized cooling, optimized
[2268.14 → 2269.06] power distribution.
[2269.52 → 2270.14] In the shipping container.
[2270.32 → 2271.08] In the shipping container.
[2271.08 → 2275.46] It's so cool. That shipping container is in the Google New York office, and you can have
[2275.46 → 2277.30] meetings in it. It was my favourite spot.
[2277.30 → 2282.52] Well, so I wonder if that was, so Sun had this thing called Operation or Project Black
[2282.52 → 2282.96] Box.
[2283.26 → 2283.44] Yep.
[2283.52 → 2285.16] That was a bunch of compute in a shipping container.
[2285.16 → 2286.82] Everybody had a shipping container at one point.
[2286.96 → 2287.14] Yep.
[2287.28 → 2290.20] All right. Listen, I find it was nothing special.
[2290.50 → 2295.78] I heard that the I was never inside it when it was operating. The airflow that you have to
[2295.78 → 2300.06] get inside the shipping container, it's like a tornado inside the shipping container in
[2300.06 → 2305.12] order to keep things cooled was my, a shipping container is not a great place to put a data
[2305.12 → 2307.10] centre was kind of my read on it. Is that a fair?
[2307.30 → 2308.26] Assessment or no?
[2308.96 → 2313.74] It is, it is in some ways a very good place. There are some operational things that make
[2313.74 → 2319.82] it a challenge. The, and we were watching other containers as well. We were ahead of
[2319.82 → 2325.70] them, I think by around six months to a year. The principles that went into that were really
[2325.70 → 2330.84] important. It's, it's a power that had to travel a short distance. It's a very short
[2330.84 → 2334.70] loop for your cooling air. The more, the further you have to move air, the more energy you're
[2334.70 → 2340.98] going to spend the container made that loop very short. And so you spent a lot less energy
[2340.98 → 2349.34] on moving air. It made everything in a nice tight package that we thought would be useful
[2349.34 → 2355.98] for quickly deploying infrastructure at the time. And shipping containers are cheap. I think
[2355.98 → 2362.70] can, at the time we bought an old container for two or $3,000. Fabrication was fairly expensive.
[2362.70 → 2367.66] There was a vendor who did a lot of the fabrication, drilling holes in the side, putting up a
[2367.66 → 2374.22] unistrut, which is a metal bracing that was used to hold up a lot of the racks and things like that
[2374.22 → 2380.98] inside. We had to do a custom cooling system with control algorithms for the fans, valves,
[2380.98 → 2388.10] controlling how much water went in and out of the container. The first version had 1,200 servers in it.
[2388.10 → 2395.54] So it was fairly dense. Yeah. It was downstairs in the garage, the Google garage. At that point,
[2395.54 → 2399.70] they're at the campus in Mountain View, the old SGI buildings. Yeah. Right.
[2399.70 → 2404.82] And so we, we lifted some greats, and we got a big, a big crane, and it dropped the container down
[2404.82 → 2409.70] into the garage. And then we put tarps on top so you couldn't see it from above. And we surrounded it
[2409.70 → 2415.94] with a cage, a fence, and they had a security guard in front. And in the winter it dripped, you know,
[2415.94 → 2423.54] rain would drip on top of it. And we had a table outside that would get wet from the rain. But we,
[2423.54 → 2428.10] we did a lot. We, that was a good learning experience. And, and Google did eventually
[2428.10 → 2434.90] deploy tens of those into a data centre, into Atlanta. And the important part were the principles.
[2435.38 → 2442.18] So the efficient cooling, the efficient power distribution, the lack of a UPS or uninterruptible
[2442.18 → 2449.14] power supply, a traditional system that you had in the data centre was, was in the, in the container.
[2449.14 → 2454.66] All the servers had their own local batteries on them too. And there's a lot of learning. You learned
[2454.66 → 2459.62] what not to do. You learned how to make things more efficient. Ultimately it was, it was the
[2461.06 → 2466.42] sort of the platform that carried forward into their next generation designs.
[2466.42 → 2471.62] But so why not, why do we not have shipping container based DCs today? I mean, was there,
[2471.62 → 2473.30] what were the problems with the form factor?
[2473.30 → 2480.10] The idea behind it was that you could put it down anywhere that had power and water, right? And
[2481.14 → 2486.98] some of the initial concepts had them out laying in fields. And you would just run a spine of power
[2486.98 → 2493.78] and water and plug these containers into them. That didn't sit too well with some of the management.
[2493.78 → 2498.34] And they were concerned about security, and they wanted to put them inside a warehouse.
[2498.90 → 2503.78] So you're building another shell around your existing container, and you've in a sense built
[2503.78 → 2509.46] two roofs around them. Also moving them inside that warehouse was challenging.
[2509.46 → 2509.86] Right.
[2509.86 → 2515.62] There was a custom crane system that was built to move the containers. And it ended up being overall
[2515.62 → 2519.62] more expensive. You also needed redundant fire suppression, both in the container and in the
[2519.62 → 2520.98] warehouse too. Interesting.
[2520.98 → 2525.14] So the cost actually went up. So it's nothing about the form factor per se. And if you wanted
[2525.14 → 2529.78] to drop it into a field, it would have been fine. Because I always assumed that there was something
[2529.78 → 2535.78] about the actual physical form factor that made that a non-cert. Because a bunch of folks investigated
[2535.78 → 2540.50] it kind of at the same time and all came to the same conclusion, but it sounds like it's got nothing
[2540.50 → 2541.70] to do with its management.
[2541.70 → 2546.58] Yeah. Yeah. It's more around the facility cost around it, which ended up being too high. And
[2546.58 → 2551.14] we looked at it and said, look, lots of great engineering principles here. Let's take those,
[2551.14 → 2555.94] but let's just do them in a standard warehouse or a standard, wasn't really a standard data centre,
[2555.94 → 2558.58] but in a data centre. But we'll call a data centre.
[2558.58 → 2559.54] Interesting.
[2559.54 → 2562.90] So we took out the shell of the container, but kept almost everything else.
[2562.90 → 2570.02] Kept everything else. Interesting. And so what year is it now? Are we now 2007, maybe?
[2570.02 → 2571.78] Yeah, probably around there. Yep.
[2571.78 → 2575.78] And you learned a lot from the container experience. And now we're beginning to take
[2575.78 → 2579.54] out the shell of the container and just taking it by the rack effectively.
[2579.54 → 2580.50] Yep. Yep.
[2580.50 → 2588.42] And so what were the kind of, what was the education from that? I mean, it sounds like,
[2588.42 → 2590.82] so that approach is obviously working at that point.
[2590.82 → 2595.70] Right. So bringing the water as close as you can to the loads. So you can minimize the distance
[2595.70 → 2602.50] of the air travel to cool the servers, getting rid of building wide UPS systems so that you can have
[2602.50 → 2608.18] localized UPS son every server. Just overall, how do you design a more thermally efficient system?
[2608.18 → 2615.62] Running with as few power conversions as possible. In a traditional data centre, you have high voltage
[2615.62 → 2620.50] coming in to a medium voltage transformer outside the building and then smaller transformers inside the
[2620.50 → 2627.70] building feeding each server. And so can you take out some of those? And then you'd have your traditional UPS
[2627.70 → 2632.98] system, right? Doing an AC to DC, DC to AC conversion. Can you take out as many of those conversions?
[2632.98 → 2638.10] So everyone, you might lose 5%, but if you can get rid of those conversions, you can be even more
[2638.10 → 2643.78] efficient. So that was part of the learning. Serviceability, how do you deploy them quickly
[2643.78 → 2648.82] in data centres? How do you repair them quickly? All those were the main learnings from that project.
[2648.82 → 2654.10] And were you engaged at all with the kind of traditional vendors in the space? Because it,
[2654.10 → 2662.26] I mean, the tragedy is that, I mean, today, you know, if I go buy a machine from an extant company,
[2662.26 → 2666.18] it doesn't have any of that education that we're doing the power, you've got all these different
[2666.18 → 2669.70] power conversions and everything else. I mean, and you already come to the conclusion that
[2669.70 → 2672.26] the existing vendors were not going to really...
[2672.26 → 2676.98] Yeah, the existing vendors were never really a think of traditional server vendors were never
[2676.98 → 2683.70] really a part of the story at Google because it had started from home built hardware, uh, or in-house
[2683.70 → 2687.54] built hardware. The, those vendors were never really a part of the conversation.
[2687.54 → 2691.46] They went straight to the vendors that were willing to do custom work for them.
[2691.46 → 2692.10] Interesting.
[2692.10 → 2694.02] Typically meant going straight to Taiwan. Yeah.
[2695.46 → 2698.50] And then, so about this time, when do you go to Facebook? About this time?
[2698.50 → 2699.46] Uh, 2009.
[2699.46 → 2700.50] 2009. Okay.
[2701.54 → 2706.02] And so what, what is the Facebook that you arrive at? I mean, what's the what are they running at that point?
[2706.02 → 2710.90] So they were working with traditional vendors at the time, and they were in, uh, co-locations.
[2710.90 → 2716.98] So a shared data centre. They had a few facilities that they had occupied themselves entirely,
[2716.98 → 2721.78] but we're still leasing them from vendors, uh, traditional data centre vendors, like
[2721.78 → 2730.18] digital realty trust or whatever it was. Um, and there, what was similar was the growth curve.
[2730.18 → 2737.30] So they had projections around how much infrastructure they would need, and it appeared to be very large.
[2737.30 → 2743.14] And the cost of that was a challenge, uh, going down the traditional route.
[2743.14 → 2751.62] And it was, it was, uh, and I credit the leadership a lot at Facebook at this time. They said, look,
[2751.62 → 2756.90] we need something more cost-efficient. Come in and figure it out. Uh, what do we need to do?
[2756.90 → 2762.90] Uh, how do we reduce the price so that we continue, can continue to scale Facebook with, uh, while
[2762.90 → 2767.70] still maintaining a business that allows us that we can operate, uh, without paying so much for the
[2767.70 → 2774.10] infrastructure itself. And, uh, I was there, uh, there was another engineer who had done a lot of
[2774.10 → 2782.18] work on data centre design and construction before at J park. Uh, and we basically sat together for six
[2782.18 → 2787.54] months and said, look, if we can start from scratch, what would we build? How would we do this integration
[2787.54 → 2794.18] of the server and the facility again? Uh, and what do we know not to do? And we spent six months coming up
[2794.18 → 2799.78] with ideas. I came up with slide decks and projections around what efficiency savings would be both on
[2799.78 → 2805.70] energy consumption, on cost and presented that to leadership. And they said, that's great. That's,
[2805.70 → 2811.62] you guys want to, the, the, the proposal was to do everything from scratch, right? And so you come to them
[2811.62 → 2817.46] and you say, Hey, we'd like to just do a whole new server and building design. If it doesn't work, we'll be,
[2817.46 → 2822.58] we'll be in a lot of trouble because we need this capacity. And we've also, you know, breaking ground on a
[2822.58 → 2827.54] facility isn't a cheap proposal. You're talking, you know, $200 million project. And if it doesn't
[2827.54 → 2834.42] work, you're out of luck. Uh, but they said, okay, we, we trust you guys. Uh, go ahead and try to make
[2834.42 → 2841.38] this big bet work for us. There must've been a moment where you're like, oh, shit, they bought it.
[2842.02 → 2847.38] That is, I mean, they, I just think back to times of my career, you make some big audacious proposal
[2847.38 → 2852.90] and, and you kind of are, you're so focused on making that proposal. You don't really think
[2852.90 → 2856.90] about like, oh my God, what if they buy it? Yeah. They bought it. They bought it. And that
[2856.90 → 2861.30] feeling stated with me for, for the next year and a half as we're actually building it.
[2861.30 → 2862.34] Oh my God.
[2862.34 → 2867.38] It was, it was never a, I could never take my, my foot off the gas pedal. Cause what if it didn't
[2867.38 → 2872.50] work in the end? Right. Uh, and, and it was a big bet, and they were willing to take big bets.
[2872.50 → 2877.94] How many people were involved at that point? So we, we, uh, we expanded the team. I think by the
[2878.66 → 2883.38] by the time we had, uh, launched or went to production with the first set of servers in
[2883.38 → 2888.42] the custom facility, there are probably 10 people on the hardware team and probably a similar number
[2888.42 → 2893.62] on the data centre facility team. And surely some things went very wrong and rude.
[2894.34 → 2900.98] They, they, things did go wrong along the way. Uh, every single one of the things we were able to
[2900.98 → 2904.74] overcome them. Right. Of course. But, but there must've been something memorable though.
[2904.74 → 2909.70] A lot of luck, uh, that when we actually went in there and put in, we called them the Marines,
[2909.70 → 2915.86] the first thousand or so servers and powered them on, they actually were, uh, I'm sure a lot of
[2915.86 → 2923.22] luck was involved, but we did have some, some very, uh, uh, hairy moments where we thought
[2923.22 → 2927.46] everything was not going to work. All right. So take us through, there's got to be a hairy moment.
[2927.46 → 2931.38] We love the hairy moments. Yeah. Yep. Yep. There was, uh, there's a couple of,
[2931.38 → 2935.86] well, so we, we did a lot of very aggressive things with the design. Part of that was, you know,
[2935.86 → 2940.26] a custom motherboard. And when you're doing a custom motherboard, basically everything we did
[2940.26 → 2944.74] was custom from the power supply, even the power strip was custom, but this motherboard was interesting.
[2945.22 → 2949.94] We picked a completely different form factor, 13 by 13 inches. Uh, that was an industry standard.
[2949.94 → 2956.90] And we were, uh, lining up with Intel's, uh, Salem processor, which was the first time Intel had
[2956.90 → 2962.50] connected the DRAM directly to the CPU. Typically, it went through a North bridge, another chip. Uh,
[2962.50 → 2966.26] this was the first time they, they connected the DRAM directly to the CPU.
[2966.26 → 2967.70] And that's via CPI. Is that right?
[2967.70 → 2973.14] Uh, not CPI. CPI was inter-processor communication. This was, this was a standard DRAM interface.
[2973.14 → 2983.54] Okay. Yep. Um, and so, uh, they, they did that, uh, and we had brought up a couple boards and, uh,
[2984.34 → 2989.78] we did our PVT or production verification tests, which is when you have several hundred systems
[2990.50 → 2996.18] and, uh, you're making sure that you don't have bugs at a larger scale, right? There are things that
[2996.18 → 3001.94] get by in earlier phases of development, like EAT or DVT, which are the first two phases of tests.
[3001.94 → 3007.06] And they're smaller volumes. So you may not see bugs that crop up on only 2% of the servers.
[3007.06 → 3012.66] But if 2% of the servers have a bug, that's a big deal. Uh, and so in PVT, we came across this bug
[3012.66 → 3020.34] where we would boot the boxes and half the memory was missing. And this is on several hundred systems.
[3020.34 → 3024.74] And we're trying to figure out exactly what it is that's going on. Uh, and...
[3024.74 → 3027.62] And so the operating system is booting normally. Everything is fine.
[3027.62 → 3028.10] It'll boot.
[3028.10 → 3031.38] It's just only seeing half the DRAM that's physically in the box.
[3031.38 → 3031.94] Yep. Okay.
[3031.94 → 3033.70] Yep. A couple of Simms would just go missing.
[3035.46 → 3038.74] They would physically be in there, but just wouldn't, wouldn't recognize them.
[3039.70 → 3043.86] What made this so challenging was that we had a deadline that we needed to approve the
[3043.86 → 3048.50] motherboard design in order to hit our mass production date. And it was only about a week
[3048.50 → 3054.66] away. So we needed to figure out this bug as soon as we could. Uh, and we basically all went down into,
[3054.66 → 3060.74] to, to a mode where everyone just focused on this one particular bug. Uh, and there were long nights
[3060.74 → 3064.90] in the data centre, um, with a lot of smoke breaks outside in between.
[3064.90 → 3071.22] And is it reproducible once one machine only sees half the DRAM? Will that machine only see half the
[3071.22 → 3074.98] DRAM? Or if it does a power reset change what it sees?
[3074.98 → 3079.38] Uh, it was intermittent. So sometimes it would come back. Sometimes it wouldn't. Uh, it happened on a very
[3079.38 → 3082.90] small percentage of machines. So every time it happened, we would try and capture what was going
[3082.90 → 3088.82] on. We had excellent partners who were helping us out. So, uh, Quanta, who was doing the motherboard
[3088.82 → 3095.06] design and Intel, whose platform it was based on, uh, all went in with us, and they were working a lot
[3095.06 → 3099.06] with us too. Uh, so you have them at least somewhat convinced that this might be their problem.
[3099.62 → 3104.58] Uh, yes, we didn't take any convincing. Everyone wanted us to succeed, and they said,
[3104.58 → 3106.58] look, if there's a problem, we're going to jump in and help you.
[3106.58 → 3110.90] Oh, that's great. So it was great. Eventually we roped in the DRAM manufacturers as well.
[3110.90 → 3116.82] Oh, wow. And, uh, and you know, it took a lot of engineering resources. Eventually what we found
[3116.82 → 3122.98] out was that there's a, um, well, the DRAM, when it starts up, the BIOS takes it through a training
[3122.98 → 3129.14] portion, and it tests the DRAM, and it does different, uh, um, tests to understand at what speed it can
[3129.14 → 3136.42] clock the DRAM at. Uh, and that procedure, I'll just tell you what the problem was, was, uh,
[3136.42 → 3141.22] causing some, uh, vendors DRAM to go into a debug mode.
[3141.22 → 3143.94] Oh, so, so the bit bang.
[3143.94 → 3151.38] So the actual DRAM, the training of the DIM that was causing the DIM to go in, it's exactly the
[3151.38 → 3152.74] opposite of training.
[3152.74 → 3159.46] Exactly. Uh, and so the, the DRAM manufacturer didn't necessarily, there's a device on there
[3159.46 → 3163.78] called an SPD on the DRAM that is responsible for setting clock speeds and everything else,
[3163.78 → 3168.58] went into this training mode. And as a result, it didn't initialize the DRAM properly. And the
[3168.58 → 3172.26] BIOS said, well, there must not be any DRAM there. And then the DRAM disappeared.
[3172.26 → 3177.78] Wow. Uh, and now that's software that's doing the training. That is just, that's very proprietary
[3177.78 → 3179.46] software historically. Yes.
[3179.46 → 3180.58] Did you guys have access to that or?
[3180.58 → 3187.94] Uh, we did not have access to the actual code, but Intel who had written it was, uh, helping us debug it.
[3187.94 → 3193.14] And together with the DRAM vendor, they figured this out after lots of probing of logic signals
[3193.14 → 3198.34] and things like that, uh, made a quick change to the DRAM and problem went away.
[3198.34 → 3203.54] And so was that a software change then to make, uh, to the, well, I can't recall if they actually
[3203.54 → 3209.30] changed the SPD on the DRAM or if they changed the training, the training to accommodate for that
[3209.30 → 3212.42] defect in the DRAM. Yep. Wow.
[3212.42 → 3217.54] But before we had solved it, I got a call. I remember it was a Friday night. I was at a family
[3217.54 → 3222.34] dinner and the vendor, Quanta called and said, look, we need to make a call. Are we going to
[3222.34 → 3227.46] move forward with manufacturing or not? And I needed to decide together with my team,
[3228.50 → 3231.94] if we felt confident we'd find a solution or not. If we said-
[3231.94 → 3234.98] It's a hardware problem or a software problem. It's effectively what they're asking you.
[3234.98 → 3239.70] Exactly. Do we go forward with manufacturing thousands of these boards, knowing we may have to
[3239.70 → 3245.06] rework them later on or perhaps trash them even, or are we confident we're going to find a solution?
[3245.06 → 3245.54] Wow.
[3245.54 → 3249.22] And so, so the deadline had actually come before we'd found the solution.
[3249.78 → 3253.38] And so we decided to go forward with production. And, and luckily-
[3253.38 → 3255.78] You were all in, this can be fixed in software.
[3255.78 → 3261.46] Yep. Yep. And it worked. And, uh, and everything from there was relatively smooth sailing.
[3261.46 → 3262.34] Wow.
[3262.34 → 3263.22] That's cool.
[3263.22 → 3263.78] Yeah.
[3263.78 → 3265.46] That-Taking a page out of your Google days.
[3265.46 → 3266.66] Exactly.
[3266.66 → 3272.50] Well, and you, I mean, and we, we, we talk about bugs at the hardware software interface a lot,
[3272.50 → 3279.06] but that's an exciting one because you're having to make a bet that whatever this defect is,
[3279.06 → 3282.18] we will be able to work around it effectively without pulping the hardware.
[3282.18 → 3283.22] Correct. Yep.
[3283.22 → 3284.10] That's fucking crazy.
[3284.10 → 3289.30] Yep. And hardware engineers, I'm sure, uh, go through this quite often. You don't hear about
[3289.30 → 3290.10] the stories often.
[3290.10 → 3291.30] Right. You really don't. Yeah.
[3291.30 → 3293.70] But it's, it wasn't the last time that happened.
[3293.70 → 3299.06] Yeah. And from a software perspective, we are not often at that point of actionability,
[3299.06 → 3302.10] where it's just like, no, no, this hardware is already broken, like figure out a way to deal
[3302.10 → 3305.54] with it. So it's like, all right, we're just going to have to work around it in some way. But to
[3305.54 → 3310.58] actually be at that decision point, it must have been, uh, very anxiety producing.
[3310.58 → 3312.58] Yeah. I mean, there was, there was a lot on the line.
[3312.58 → 3317.54] All right. Well, good for you. Oh, you, you, boy, that must have been a great sense of relief
[3317.54 → 3318.50] when that was found.
[3318.50 → 3319.06] Good choice.
[3319.06 → 3324.90] It was, it was. And the actual first deployment of, we didn't call them OCP servers at the time.
[3324.90 → 3329.94] It was, it was called Project Freedom, um, because we wanted freedom to do our own designs.
[3330.74 → 3336.82] Other people had, had taken that and interpreted that as freedom to, uh, escape from Dell and HP,
[3336.82 → 3338.18] which were our vendors. Yeah.
[3338.18 → 3341.94] That's, that's not why we called it Project Freedom. We wanted the freedom to do our own designs.
[3341.94 → 3343.46] Uh, and...
[3343.46 → 3346.90] Aren't those, those aren't the same thing? I mean, aren't they a little bit the same thing?
[3346.90 → 3350.18] I don't want to pick it that way. So, okay.
[3350.18 → 3354.34] Not, not necessarily. I mean, we were looking for good vendors who could work with us. I,
[3354.34 → 3359.06] you know, had traditional vendors stepped up and said, look, we like your designs.
[3359.06 → 3363.06] We'll build them for you. That would have been fine too. We didn't, we didn't have a bias around
[3363.06 → 3366.50] who would have worked, worked with us at the time. We ended up going with vendors we thought
[3366.50 → 3370.50] would be most flexible, uh, to deliver what it was we asked for.
[3370.50 → 3373.46] I'm not saying I don't want to be your child anymore. I'm just saying I don't want to live at home.
[3373.46 → 3378.82] Well, you could say that or, or yeah, or you should remodel your home if you'd like us to
[3378.82 → 3379.78] continue living here.
[3379.78 → 3384.90] Right. There you go. Exactly. Um, but it sounds like no remodel was forthcoming or...
[3384.90 → 3390.10] There, there, there were, uh, they came a little bit late. Uh, we needed to have
[3390.74 → 3395.94] a contingency plan. So we had built this custom facility that couldn't work with a standard 19
[3395.94 → 3401.38] inch server any longer. It didn't have a UPS system. And, uh, there were vendors who had
[3401.38 → 3407.86] rack level UPS sat the time, and we had built up a contingency plan with them to use our custom
[3407.86 → 3412.82] motherboards inside their own racks. So could you talk about the rack width a little bit?
[3412.82 → 3415.70] Because the 19-inch rack obviously dates back to whatever.
[3415.70 → 3420.18] Old telco days. Old telco days. Yeah. It's, and dates back to the railroads, right?
[3420.18 → 3423.14] I mean, it's a it's a it's a super dated notion. I guess that's false.
[3423.14 → 3424.90] Yeah, that's false. That's false. We've been over this.
[3424.90 → 3425.86] That's an internet falsehood.
[3425.86 → 3429.78] That's like a Slopes. You keep perpetrating it. I keep, I keep perpetrating it. But the
[3429.78 → 3432.98] point is it's a very old idea, the 19-inch rack. Right.
[3432.98 → 3436.18] And it sounds like you guys put everything on the table. What did you come with in terms of the
[3436.18 → 3443.06] rack width? I mean, the first rack design was a three column rack. So a lot of the principles that
[3443.06 → 3448.74] drove, uh, the efficiencies came from marginal gains. And a lot of those marginal gains came from
[3449.38 → 3455.30] amortizing cost of infrastructure across more servers. So if you can have a rack and instead of putting
[3455.30 → 3460.98] 40 servers in it, you could put 120 servers in it, that cost of that rack is amortized across
[3460.98 → 3467.06] more boxes. Everything becomes cheaper at that point. So we said, let's put three columns of servers
[3467.06 → 3473.46] together and roll them in. The cost of the rack went up, but we had more servers. And so the actual
[3473.46 → 3478.74] cost per server went down of the rack. Uh, it also made it faster to deploy. You're deploying three
[3478.74 → 3480.82] columns at a time instead of just one at a time.
[3480.82 → 3485.86] And so, and why three? Why, why, why not two or four? Is there, was it just that that was where
[3485.86 → 3486.50] the sweet spot was?
[3486.50 → 3491.70] Yeah. We, we, we looked at, um, how you'd line them up in the aisles of the data centre.
[3491.70 → 3497.62] Three made sense. A lot of it had to do with our backup system, which was a single column of lead
[3497.62 → 3503.94] acid batteries. And we thought we could, we had enough capacity in that, in that localized UPS in that
[3503.94 → 3510.66] column of lead acid batteries to maintain power to three columns of servers on one side, and then
[3510.66 → 3516.42] another three columns of servers on the other side. So six servers. So we would sandwich a stack
[3516.42 → 3519.22] of batteries between six, uh, three columns of servers.
[3519.22 → 3519.70] Interesting.
[3520.82 → 3525.62] A lot of it came down to network ports too. How do you use all the network ports on a switch,
[3527.06 → 3529.38] and amortize the cost of the switch across more servers.
[3529.38 → 3534.34] Got it. So three made sense there too. And so, and then does the width then come from that?
[3535.06 → 3540.42] The width we decided could be arbitrary. Uh, we, we said, let's do what makes sense and not try and
[3540.42 → 3543.30] fit it into any constraint that was defined by the facility.
[3543.30 → 3543.78] Got it.
[3543.78 → 3550.10] Yep. Yep. And so that, that was a, uh, interesting design because the weight also went up. So
[3551.78 → 3557.22] packaging became a challenge and shipping them became a challenge. Uh, not so much with compute
[3557.22 → 3561.70] servers because they didn't have hard drives in them, which meant they didn't weigh too much.
[3562.50 → 3568.34] But in some of our initial calculations around doing a storage server and filling up, uh, we called
[3568.34 → 3574.42] it a triplet, a triplet rack with hard drives, you were looking at, uh, the weight of a rack that was
[3574.42 → 3576.50] almost equivalent to a large SUV.
[3576.50 → 3576.90] Right.
[3576.90 → 3581.06] Right. And pushing an SUV down your data centre floor didn't seem like a good idea.
[3581.86 → 3585.54] Well, you also have issues, right? Where you're depending on how you are going to load those
[3585.54 → 3590.74] spindles and how high they're going to be, you end up with a lot of weight potentially high up in the
[3590.74 → 3596.66] rack that it can be, you end up with a lever basically. You can put the rack tipping over.
[3596.66 → 3600.42] Right. You, you'd put your, your heavier weights towards the bottom. So you'd get a lower centre of
[3600.42 → 3601.30] gravity. Right.
[3601.30 → 3606.98] Um, it is, it is a consideration. More so of how do you remove that off of a shipping truck
[3606.98 → 3611.38] onto a loading dock and then from the loading dock onto your, into your data centre.
[3611.38 → 3615.78] That is real systems thinking to be, I have to think of like really end to end about kind of
[3615.78 → 3618.10] all those different steps. Yep. Yep.
[3618.10 → 3622.74] Wow. So did you end, did you end up making the rack a bit smaller as a result of that?
[3622.74 → 3627.54] Yeah. So the second generation rack, which was the open rack, which came after the triplet was built
[3627.54 → 3633.14] on a single column. Uh, and that lent itself better for, uh, storage servers. It increased
[3633.14 → 3636.66] the cost of the rack per server more. Uh, but that was a trade-off you had to make.
[3636.66 → 3639.94] And is that the rack we have today? That 600 millimetre rack? Does that come from that?
[3639.94 → 3642.02] That form factor came from that. That form factor. Yeah. Right.
[3642.02 → 3646.02] They're onto different versions of open rack. There's V2 and whatnot, but it came from that.
[3646.02 → 3649.06] It seems like the width has stayed somewhat constant over the...
[3649.06 → 3656.34] Yeah. At some point the, you know, the data centres are built around floor tiles, which are 24 by 24 inches.
[3656.34 → 3661.70] And so you want a rack to take up two floor tiles, uh, because then you can put them in standard
[3661.70 → 3667.14] data centres. And that was something that, you know, when we first started, uh, OCP, we said,
[3667.14 → 3670.50] it doesn't matter, uh, what kind of floor tiles you're going to have. We're not going to have floor
[3670.50 → 3674.58] tiles in our data centres. They're going to be on concrete floors. Therefore, you can go for any sort
[3674.58 → 3682.26] of width you want. And, um, and once we had realized that there were benefits, uh, to allow deployments in
[3682.26 → 3687.46] traditional data centres, uh, we moved back to the standard floor tile width for the rack.
[3688.10 → 3692.10] And that made it easier for other people to adopt OCP or our designs as well.
[3692.10 → 3696.90] Interesting. All right. So we're going to take another quick break. Um, and we'll be back,
[3696.90 → 3699.38] um, with Amir Michael on the metal.
[3699.38 → 3706.10] On the metal is brought to you by the oxide computer company. Well, bad news. I just got
[3706.10 → 3710.74] back from a meeting with the attorneys. Oh boy. They are not going to let us say much in these ads.
[3711.14 → 3715.46] We can't talk about the customer experience today for on-premises infrastructure.
[3716.02 → 3720.74] So we can't do my idea to be like, are you being gaslit by your vendors? Because that's what they're
[3720.74 → 3725.30] doing. They're gaslighting people into thinking that these bugs only exist on one of their machines
[3725.30 → 3729.94] when it exists on like everyone's. God, no. They called that, I think, quote, a third rail.
[3729.94 → 3733.22] They must be following Jess on Twitter. I knew that that was a bad idea to let the lawyers follow
[3733.22 → 3738.58] Jess on Twitter. Uh, they also said we can't talk about public cloud customer experience.
[3738.58 → 3742.18] Oh, come on. We can't talk about the rapacious bandwidth pricing. I mean, it's practically criminal.
[3742.18 → 3745.54] No, can't talk about the unit economics of that. Can we use the word criminal with respect
[3745.54 → 3750.90] to public cloud vendors? Definitely not. Oh boy. What can we do? Well, they did say they gave us
[3750.90 → 3753.38] a statement we can use, which is... Are you going to read from it?
[3753.38 → 3759.06] Oxide Computer Company is building something that should help some people.
[3759.06 → 3763.14] Wow. That seems very direct. Come on. Can we at least send them over to oxide. Computer?
[3763.14 → 3767.46] We can. We can. The other bit of bad news is all the lawyers were there in the meeting.
[3767.46 → 3770.66] Oh, wait a minute. Not just the cheap one, but the expensive one?
[3770.66 → 3774.90] Yeah. They were all there. So we paid a fortune to get this terrible ad. Oh my God. Please,
[3774.90 → 3777.86] listener, go to oxide. Computer and learn what we're actually doing.
[3777.86 → 3785.30] All right. We're back. So we were talking a little bit about OCP and the Open Compute Project. How did
[3785.30 → 3792.66] that get going? That was a result of the effort. So Project Freedom was the name of the first custom
[3792.66 → 3797.46] design. We looked at that and said, wow, that's great savings. It was 38%
[3797.46 → 3806.82] more energy efficient, 24% more cost-efficient. And there was an idea that other people should have
[3806.82 → 3812.98] access to that as well. And if you thought about Facebook's business model, it wasn't at all based
[3812.98 → 3818.18] on their ability to deploy efficient infrastructure. It was based on social network. The two things were
[3818.18 → 3824.42] completely different. As a matter of fact, the social network was built on many open source technologies
[3824.42 → 3831.06] that Facebook was able to benefit from and deploy in their own infrastructure, like Meccas, like MySQL.
[3831.06 → 3837.78] And so why should we keep this amazing innovation for ourselves? Because it's not our competitive
[3837.78 → 3842.90] advantage. Let's let everyone have those same efficiencies. It's better for the next generation
[3842.90 → 3849.38] of companies. It's better for the environment. You're using less energy. And so we said, great, let's open source this.
[3849.38 → 3852.34] You know, I feel this is something that gets a little bit misinterpreted out there,
[3852.34 → 3859.14] because I think people treat Facebook's inception of the OCP pretty cynically as like, oh, they're just
[3859.14 → 3864.98] trying to make their own gear cheaper or what have you. But my read on it is that just exactly what
[3864.98 → 3870.18] you said, that there's a very earnest desire to give back this important innovation.
[3870.18 → 3875.94] That was the primary driver. There was always an idea that if other people adopted, volumes go up,
[3875.94 → 3880.34] prices go down. That was maybe 10th on the list. Interesting.
[3880.34 → 3884.26] Other things there were collaboration. Hey, maybe we don't need to engineer everything. If other
[3884.26 → 3888.50] people adopt, we can work together with them, build the next generation together.
[3889.46 → 3895.30] And creating collaboration across engineers is always interesting. It makes you an attractive
[3895.30 → 3900.50] employer, right? Engineers like to work on projects that are out in the open, right? You can hire an
[3900.50 → 3904.18] engineer easier if you tell them you're going to work on this public project, and you're going to be able
[3904.18 → 3908.50] to drive it. That's always another benefit too. It is a benefit. Yeah. Isn't it?
[3908.50 → 3912.58] Yeah. And I, I, you know, I think maybe everyone's got different motivations for that. I'm sure some
[3912.58 → 3917.70] of the motivation for that is the like, I want to be able to people to see the work that I do.
[3917.70 → 3920.74] I always do. But also it has more of an impact. I mean,
[3920.74 → 3924.34] it has an impact outside just the company that you're working at.
[3924.34 → 3928.50] I also... Was there selling you had to do internally? Were there anyone,
[3928.50 → 3930.34] folks that were concerned about opening it up?
[3930.34 → 3934.34] Chris- Surprisingly enough, there was very little resistance internally. Everyone just got on board
[3934.34 → 3939.30] and said, this is the right thing. This is the right thing to do. Legal, obviously, we needed to
[3939.30 → 3944.26] give us the sign-off, but even that wasn't, there was some hesitation, but even that went fairly
[3944.26 → 3950.26] smoothly with them. You know, there were more college challenges trying to figure out what to call
[3950.26 → 3956.02] the project than it was if we should actually do it or not. What were some of the other names?
[3956.02 → 3961.70] I don't remember any of them specifically, but we couldn't decide within the immediate team that
[3961.70 → 3969.22] was running the project. And I think, you know, someone was having a chat with Mark Zuckerberg about
[3969.22 → 3974.58] the name, and he said, well, you should just call it the Open Compute Project. And it came back.
[3974.58 → 3977.70] There's a reason he's the boss. I mean, that makes sense. It's a good name.
[3977.70 → 3979.94] Yeah. And that's really where the name came from.
[3979.94 → 3980.82] Yeah. Interesting.
[3980.82 → 3985.06] And that's, it's a good name. It's definitely a good name. And I think it, I would love to know
[3985.06 → 3989.94] what some of the dustbin names were, but that's a that's a good one. So, and then that is now,
[3989.94 → 3991.54] are we like 2011? Is that right?
[3991.54 → 3996.58] That was 2011. Correct. In April 2011 is where they did the public launch of the project.
[3996.58 → 4004.18] Right. And I remember, I mean, that turned a lot of heads on the vision was great, but it took,
[4004.18 → 4009.54] I mean, it's just slow-going to get people kind of bought into it is what is my read on it.
[4009.54 → 4013.86] Yeah. A lot different from an open source software project, which you can just download and start
[4013.86 → 4021.14] using. This is hardware. It moves slower. People have existing solutions. A big part of it is the
[4021.14 → 4027.22] ecosystem. So who am I going to buy from? Who's going to support it? That doesn't really exist as much
[4027.22 → 4036.50] in software today. And so I remember the first OCP summit we did have, you know, a couple of hundred
[4036.50 → 4042.74] people there. And it was largely vendors too, who wanted to come by and see what, what Facebook was
[4042.74 → 4049.54] up to. There were more progressive companies who ran large infrastructures, some banks.
[4049.54 → 4057.22] Rackspace was one of them too. We said, look, we buy a lot of this stuff. We don't have the resources
[4057.22 → 4062.90] to do our own custom design. Let's work together. And we sort of latched onto a lot of those partners
[4062.90 → 4071.46] too. And from there, just slowly, slowly started to grow. And the second summit was maybe a little bit
[4071.46 → 4077.38] bigger and then the third, a little bit bigger. And then eventually other large infrastructure companies,
[4077.38 → 4082.50] I'm talking, you know, some of the mega scalers like Microsoft and Google said, hey, this is, this is actually
[4082.50 → 4088.34] a good thing. We need to take a lot of these principles in and do them in our own designs. Let's start working
[4088.34 → 4094.82] together. And for those who haven't been to OCP summit, I think Steve, Jess, and I can all recommend it. It's,
[4094.82 → 4100.98] it's super fun. It was fun. The, the, the technical communities there are really great. I think that we,
[4100.98 → 4107.22] you know, we walked into some of those breakout rooms and they're just great. The vibe was great. It was,
[4107.22 → 4112.34] it was people, it's big, big, very well attended. Yeah. It's fun. And it's got a lot of, a lot of
[4112.34 → 4116.18] neat hardware on the floor. And it's, you know, it's, it does feel like it's one of these things
[4116.18 → 4120.10] that is kind of been slowly growing, but it's actually getting, I mean, I know it takes,
[4120.10 → 4123.46] these things take longer to build than anyone wants, but it feels like it's got some critical
[4123.46 → 4128.42] mass. The hardware on the floor is great. Like, uh, seeing all the like racks from Facebook and
[4128.42 → 4132.98] then comparing those with like racks from other places. Like, and there are a lot of nutty ideas that there,
[4132.98 → 4135.94] there was the rack that was being dunked in water. Like mineral oil.
[4135.94 → 4137.94] Mineral oil. Right. Exactly.
[4137.94 → 4138.34] That one was insane.
[4138.34 → 4138.90] Fully submerged.
[4138.90 → 4139.94] Fully submerged.
[4139.94 → 4140.42] That's.
[4140.42 → 4144.34] And then the demo was, you know, ask for your cell phone and drop your cell phone in there. And
[4144.34 → 4145.86] you're like, whoa, whoa, whoa. Okay.
[4145.86 → 4146.26] Okay.
[4146.26 → 4147.30] No, thank you.
[4147.30 → 4151.78] It's like some sort of weird oil though, because there's like a residue. Like I have to put my finger
[4151.78 → 4152.10] in it.
[4152.10 → 4152.98] Yeah.
[4152.98 → 4156.82] And then I think the thing that just liked the most on SCP Summit is no Kubernetes talks.
[4156.82 → 4161.70] It was great. It was refreshing. It was so, no, it's like, and then like actually having
[4161.70 → 4165.78] like a physical thing, like you were saying that you can like touch and feel. Like I, I, I felt bad
[4165.78 → 4170.82] badly because I made like one of the people at the Facebook booth, like pull out this like sled,
[4170.82 → 4174.74] like 14 times so that I could see it. And he was like, you know, this thing is like fairly heavy.
[4174.74 → 4177.14] I'm kind of sweating.
[4177.14 → 4179.70] He was like, could you just do it maybe two or three more times?
[4179.70 → 4181.54] It was like a bunch of GPUs. It was dope.
[4181.54 → 4182.34] That's great.
[4182.34 → 4187.14] So, but I, one question about software, because software was not a big part of OCP.
[4187.14 → 4192.26] And was there any thought in terms of like firmware into OCP, or maybe it was just one step at a time
[4192.26 → 4195.06] in terms of, of, it's hard to get something like that launched.
[4195.06 → 4202.74] Yeah. The initial deployment, uh, was designed to be plug and play with, uh,
[4202.74 → 4206.10] That's just a low flying Oakland police department helicopter. That's nothing to be allowed.
[4206.10 → 4206.66] I'm worried about.
[4206.66 → 4208.50] If someone jumps through the backyard, it's fine.
[4208.50 → 4213.54] Yeah. And so the initial deployment was designed to be, uh, plug and play with existing infrastructure
[4213.54 → 4218.74] that Facebook had had. So changing the software wasn't really part of the equation at that point.
[4218.74 → 4224.82] Uh, and also with a relatively small team, you had to understand, we took a lot on as far as scope
[4224.82 → 4226.66] goes, and you had to understand what not to do as well.
[4226.66 → 4230.82] Totally. No, no. It makes sense. So there was no, it was not deliberately trying to keep software out
[4230.82 → 4235.22] of it. It was just like, this is the part we can go to now. Yeah. Right. Right. Right. Not at all.
[4235.22 → 4238.90] Yeah. Eventually it did make its way in through different initiatives, through other companies,
[4238.90 → 4244.50] some through Facebook as well, but not, not a large part of it. A lot of it started coming into play when
[4244.50 → 4250.82] networking became bigger and bigger and inside OCP. Yeah. It seems like, and that seems like a
[4250.82 → 4258.34] that was where OCP had its first huge impact across the industry. The, um, in terms of like
[4258.34 → 4263.86] networking and the, and the, that seems where it's had a really outsized impact. Yeah. That was a lot
[4263.86 → 4271.38] of fun to experience where servers for a long time, uh, hadn't become commoditized and networking gear
[4271.38 → 4276.98] still came at a premium. And a lot of the same thoughts around taking things and just doing them
[4276.98 → 4282.34] yourself and realizing that a lot of the networking gear became much simpler to implement and less
[4282.34 → 4288.26] specialized, um, really changed the landscape of how you built networks. A lot of it had to do with
[4288.26 → 4296.18] the infrastructure going from, uh, switches that were, uh, you know, specialty high-speed switches that were
[4296.18 → 4302.74] large and required a vendor to really put, put together a fairly complex project to taking top
[4302.74 → 4307.94] of rack switches and joining them together in a mesh network to be able to, uh, replace some of the
[4307.94 → 4315.54] larger switches there really, um, brought together the networking project in a way which, uh, allowed it
[4315.54 → 4321.06] to do a lot of the same things that commoditized hardware. Right. And basically bringing that revolution.
[4321.06 → 4325.46] And, and, and with the, the silicon, I mean, you, you, obviously there, you need that top of rack
[4325.46 → 4331.14] silicon, but you don't need that expensive surround around. Correct. Yep. Exactly. Um, that's great.
[4331.14 → 4336.98] So, uh, and then, so, so where to then beyond, I mean, you had your, uh, you had your own company,
[4336.98 → 4344.74] you did the startup journey. I did. I did. So after four years, we had gone from, uh, a world where
[4344.74 → 4350.58] Facebook had purchased, uh, servers from the traditional OEMs, uh, to going to a hundred percent custom
[4350.58 → 4356.02] servers. So it was a four year, uh, evolution there starting off with compute and storage and
[4356.02 → 4361.22] then flash. Eventually everything was brought under one roof. Uh, and they were, the organization had
[4361.22 → 4367.46] grown significantly. It was no longer a team of 10 people. Uh, there was probably around 200 people.
[4367.46 → 4373.70] If you took into account the engineering and the supply chain, uh, everything that, that required
[4373.70 → 4380.10] Facebook to continue to deploy their infrastructure, uh, the physical infrastructure at least.
[4380.10 → 4385.06] And so things that had slowed down a little bit, um, obviously when, when you're larger,
[4385.06 → 4389.94] you have your business model figured out and tend to take less risks, risks on these things.
[4390.74 → 4396.98] Um, and that was, uh, a good natural progression. That's really where you want to get to,
[4396.98 → 4401.14] um, because you know that, that you've sort of won at that point. Yeah. I figured out a good formula
[4401.54 → 4405.94] and now we're just repeating that, and we still get to benefit and gain from all these,
[4405.94 → 4410.98] these cool innovations. That's been very satisfying. Like I've come a long way from the guy got chewed
[4410.98 → 4417.62] out for using the thermal paste incorrectly at the, the Google DC. Yep. Yep. Exactly. And I think
[4417.62 → 4423.54] most satisfying was, was really seeing the impact it had as far as energy usage, uh, as far as costs,
[4423.54 → 4428.98] uh, as far as the community that was built around it and allowing other people to benefit from the same
[4428.98 → 4436.42] benefits that faith Facebook had. I tend to, to like, uh, uh, the, the feature I like the most is
[4436.42 → 4444.66] really the energy efficiency that came with it. I think that at a high level, um, is a problem that
[4444.66 → 4448.74] doesn't get a lot of attention. It doesn't. And it should. Right. I mean, you think about like the
[4448.74 → 4454.18] greenhouse gas emission from our DCs effectively. Right. I mean, these are coal burning, natural gas
[4454.18 → 4458.34] burning power plants that are providing power to these things. Right. Right. And I think the last
[4458.34 → 4463.46] statistic I heard is 2% of all energy produced goes to feed data centres. Wow. There are some estimates
[4463.46 → 4469.78] that say it'll get up to 10%. That's a big deal. It's a big deal. And it's, and it's not a good thing
[4469.78 → 4476.66] for society or our world in general. And people don't focus on that. Even within the OCP really enabled a
[4476.66 → 4480.98] whole new supply chain, whole new set of vendors. But really what I like to think about is all the
[4480.98 → 4486.66] the emissions that it offset. Uh, and so how do you continue that? Yeah. How do you get OCP into,
[4486.66 → 4491.62] into more hands of more people? How do you, it doesn't even need to be OCP, just the same design
[4491.62 → 4496.58] principles. Energy efficiency designs. Exactly. And it does feel like it were, uh, there's,
[4496.58 → 4501.06] there's a lot still to be done there in terms of getting, because some of these designs, I mean,
[4501.06 → 4506.34] it's not controversial that, that having fewer places for power conversion, for example, is so much
[4506.34 → 4512.58] more efficient. Right. And yet it's still not yet as mainstream as it should be. Yep. Yep. And I think,
[4512.58 → 4521.62] you know, focusing on that part of it, um, is, is really, it doesn't, uh, it can, you can try and
[4521.62 → 4526.58] push that along through the OCP foundation. I don't think you'll find very many people who will disagree
[4526.58 → 4532.42] that it's a good thing in general. So enabling traditional vendors or ODMs to build those designs
[4532.42 → 4537.78] is really a problem that I'm interested in. Uh, how do you, how do you get that into the hands of
[4537.78 → 4542.18] more people? Interesting. It's too important not, not to pay attention to. There's too much on the
[4542.18 → 4545.94] line. There is too much on the line. Yeah. It's a big, and we don't talk about it enough. I mean,
[4545.94 → 4552.26] I, I've always wondered, you know, we, as software engineers, and you can have a, a software bug that
[4552.26 → 4557.30] effectively results in a lot more power being consumed and a lot more greenhouse gas emission,
[4557.30 → 4561.62] albeit very indirectly. And we don't really think of it that way right now. Right. Um, but we really,
[4561.62 → 4566.34] we should. Yeah. Yeah. Every line of code uses some amount of energy, right? You can,
[4566.34 → 4571.22] you can count the number of rules that it's using, uh, to execute your for loop or whatever,
[4571.22 → 4576.02] whatever part of code you're writing. And I feel with cryptocurrency that, that got a bit
[4576.02 → 4581.38] more attention where people began to realize like, wow, this is really stupid that we are spending this
[4581.38 → 4588.58] much energy trying to solve math problems. Yeah. I hope, I hope that's how people view it. I'm not sure yet.
[4588.58 → 4594.42] Right. Um, it is a very inefficient way of solving a problem that you could be done more efficiently.
[4594.98 → 4601.14] Uh, and it's, it's, it's fairly sad to see these big crypto farms popping up, consuming massive
[4601.14 → 4604.82] amounts of energy, um, without much thought to, to that part of it.
[4604.82 → 4608.66] Without much thought. And let's hope that's going to be, let's hope that the consequences for that will
[4608.66 → 4614.34] be natural and, and self-enforcing. So is that what, was that part of what, what drove you to Kuhn? I mean,
[4614.34 → 4618.82] to, to kind of solving that problem more broadly. Ah, yes. We were talking about my, my company then.
[4618.82 → 4626.34] No, uh, that, that wasn't it. Um, so naturally going back to, uh, uh, where we were at Facebook,
[4626.34 → 4631.70] things had, had slowed down. We're making good progress. Uh, I always had growing up in the
[4631.70 → 4635.94] valley of this bug that I needed to do a startup. Uh, it was something that I was just curious about,
[4635.94 → 4642.10] uh, something that I wanted to experience. And I decided after my, my, uh,
[4642.10 → 4645.94] we empathize with this issue, by the way, if it's not obvious.
[4645.94 → 4653.94] I can tell. Yeah. Uh, my, uh, my, uh, younger daughter was born, and I figured I had a new baby
[4653.94 → 4657.54] at home. What a better time to go ahead and start a startup at that point.
[4657.54 → 4657.94] Perfect.
[4659.54 → 4660.42] Right there with you.
[4660.42 → 4668.18] Yep. Uh, and a very supportive family. Uh, and so I left my job at Facebook and me, uh,
[4668.18 → 4671.54] became more or less an entrepreneur in residence at a VC firm. And I spent
[4672.10 → 4679.86] about a year thinking about what it was I wanted to do. Um, a lot of, uh, what I thought about was
[4679.86 → 4686.26] how, how do we get efficient designs and efficient management of servers downstream? Uh, larger
[4686.26 → 4691.94] companies had great engineering teams, lots of resources that could build management systems.
[4691.94 → 4698.74] A big part of, of running efficient infrastructure is utilization. Uh, one metric we looked around
[4698.74 → 4704.02] was mean time to repair. How do you get a server back online after it's failed as quickly as possible?
[4704.02 → 4709.94] So it's not sitting there idle consuming resources. You needed good management tools. Management tools
[4709.94 → 4715.86] that existed, uh, were designed for enterprise. We're talking scales of maybe several hundred servers.
[4715.86 → 4722.18] Nothing was really designed to allow the management of thousands of servers. We'd built systems both
[4722.18 → 4727.46] at Google and at Facebook to manage thousands, hundreds of thousands, a million servers at a time.
[4728.26 → 4733.30] Is that a product that we can actually, um, sell, right? Is that something we could sell? Allow people
[4733.30 → 4739.22] to, as these more and more companies are beginning to scale out, can you sell a product like that? That'll
[4739.22 → 4742.10] help them manage their fleet so they don't need to reinvent the wheel around that.
[4742.10 → 4746.90] And manage a hardware fleet. So you're going to be writing software that is going to be talking
[4746.90 → 4753.86] to a lot of firmware, a lot of BMCs, a lot of biases out there. Yeah. Um, and interesting and,
[4753.86 → 4762.18] and presumably discovering how the rest of the world was living in terms of, I mean, I don't know,
[4762.18 → 4766.26] you know, Jess, you coined the term, I'm sure you coined it, but the you talk about the infrastructure
[4766.26 → 4772.26] privilege that folks at Google and Facebook had had. Yep. And how do you realize just how little
[4772.26 → 4776.82] things have progressed since you built your own server back in the day? That's really when I
[4776.82 → 4781.22] started realizing that. When I started digging and seeing who is, who is deploying OCP? What are,
[4781.22 → 4784.90] are there, is there anything meaningful out there as far as deployment goes? What are people still
[4784.90 → 4790.98] buying today? And it really hadn't changed. It had not changed. It looked very similar to the world
[4790.98 → 4795.46] five years prior. Five? It looked similar to the world. 15. Fries, right? When you were,
[4795.46 → 4800.74] I assume you assembled that box from fries. It looks pretty, you know? Yeah. Uh, you know,
[4800.74 → 4804.42] traditional 19 inch one use servers. Right. And there are lots of reasons why that,
[4804.42 → 4810.02] that's not a good design. Um, but it's what people are used to, and it does work, not efficiently,
[4810.02 → 4816.58] but it does work. And so, uh, that was eye-opening. Um, it wasn't part of the problem we were trying to solve.
[4816.58 → 4824.42] Right. Exactly. Yeah. Right. Uh, and so, um, raised some venture funds, uh, built a small team around
[4824.42 → 4831.06] it, uh, build the product that again, uh, had lots of ways it could go wrong, but surprisingly enough,
[4831.06 → 4837.70] worked fairly, really well. Uh, and we're able, was able to collect millions, millions of data points
[4837.70 → 4843.14] from server fleets, large server fleets. Again, I had, you must have discovered some really
[4843.14 → 4850.02] strange hardware behaviour as part of doing this. For sure. I think the, the first behaviour we,
[4850.02 → 4854.10] we discovered was that people were, weren't necessarily paying attention. Uh, and there
[4854.10 → 4859.94] was so little known about their fleets. Um, the, the, the most interesting one was, was, uh,
[4859.94 → 4865.06] just utilization and just how poor it was. Yep. It's something we tracked at, at scale,
[4865.06 → 4870.18] at larger companies fairly closely, but smaller companies just didn't have time to pay attention to
[4870.18 → 4873.70] that. Interesting. Uh, and you would think they would, if they're buying, how do they know how
[4873.70 → 4879.46] many servers to buy? Where's the capacity planning? Uh, if your utilizations are that low are within
[4879.46 → 4886.66] 2%, 3%. Um, that, you know, one, one engagement we had, we actually discovered CPU utilization hovered
[4886.66 → 4893.06] around 3%. Uh, drives were only around 10% full for spinning drives. Flash was just slightly higher than
[4893.06 → 4897.46] that. I mean, if you think about the millions of dollars you spend on infrastructure, and you're only
[4897.46 → 4902.58] using it 10% of the time or 10% of its capacity, that's a lot of money you're leaving on the table.
[4902.58 → 4906.02] Right. And you can see why a lot of those folks honestly went to utility completing, went to,
[4906.02 → 4909.54] went to the cloud where it probably does make sense for a bunch of those folks to.
[4909.54 → 4913.14] Yes. Although in traditional cloud deployments, you can make those same mistakes.
[4913.14 → 4914.02] Sure. Right.
[4914.02 → 4918.34] You reserve, you reserve an instance, you buy, you check out an instance, and you can still just
[4918.34 → 4925.22] under utilize it as well. Uh, fortunately in that scenario, the cloud provider may realize and
[4925.22 → 4930.66] add more tenants onto that particular box. So at least, uh, someone is utilizing it.
[4930.66 → 4933.70] Yes. But you've, you've paid for the full utilization, which you may not be getting.
[4933.70 → 4937.38] Yeah. When you do wonder, I mean, if we could just be omniscient for a moment,
[4937.38 → 4943.54] I mean, how much DRAM is actually being used? You know, because I, if I provision a four gig instance
[4943.54 → 4948.42] in AWS, I'm not going to get that DRAM is not going to be that oversubscribed. I'm basically going to
[4948.42 → 4950.50] have four gigs of DRAM more or less. Right.
[4950.50 → 4955.14] Right. And how much of that DRAM is actually being used and how much inefficiency is there and,
[4955.14 → 4960.42] and under utilization is there. Right. I mean, how many capacitors are we lighting up that we
[4960.42 → 4966.18] actually do not need to be lighting up? Yeah. I think that's, that's a very true statement where
[4966.74 → 4971.30] most of it is not being utilized. And with certain things like DRAM, the problem is that there's no
[4971.30 → 4975.14] power variability. So if you're using it or not, it's consuming the same amount of power.
[4975.14 → 4977.78] It's got to be refreshed at the same frequency, right?
[4977.78 → 4981.70] At least CPUs can adjust, but things like DRAM cannot.
[4981.70 → 4987.46] So that must have been interesting to discover that the rest of the world was not as deliberate
[4987.46 → 4992.74] about their infrastructure. Yeah. I guess I wasn't too surprised. But we did see a couple
[4992.74 → 4998.58] interesting trends. Utilization was low. There was a constant battle at some of these vendors,
[4998.58 → 5002.50] like to call them second tier companies. So they're not quite hyperscalers. They're a step below.
[5002.50 → 5010.18] They're running maybe 5,000 to a hundred thousand servers. Just the resources they had to run efficient
[5010.18 → 5015.46] fleets were very small relative to the hyperscalers. There were no good solutions for them
[5016.58 → 5023.86] on the market to help them run that efficiently. And a lot, a lot was lacking there. There was very
[5023.86 → 5028.58] little awareness at the leadership level at these companies that was actually a problem. A lot of them
[5028.58 → 5033.54] were just happy running the way they were. And so education and awareness was a big part of that.
[5035.30 → 5040.18] The challenge there is then, once you show them that there's an inefficiency, how do you get them to
[5040.18 → 5047.46] change? And those solutions were lacking as well. So we were more of a visibility solution. There were
[5047.46 → 5053.46] actions around, hey, here's how you can repair this server faster. Here's the error we saw. Therefore,
[5053.46 → 5058.50] this component must be swapped. But to actually get them to put in operational procedures to do
[5058.50 → 5061.86] those things were a challenge too. Well, also, if I'm managing physical infrastructure,
[5061.86 → 5065.38] I'm a little bit afraid of your software. I don't know that I want your software to show
[5065.38 → 5070.02] all the dark corners and to show that like just how poor my utilization is. And I mean, there's a
[5070.66 → 5075.86] kind of human fear of this almost. Yeah. Yeah. You know, CYA.
[5075.86 → 5081.86] Yeah, absolutely. I need to keep myself employed. And so we didn't run into that very often. Most of
[5081.86 → 5086.58] them were very open to understanding what their infrastructure was doing and then use that in
[5086.58 → 5093.14] order to make a case that they needed more resources. Right. Which was good. There was a
[5093.14 → 5098.34] trend that we were battling, which was the cloud. And so a lot of people, like you mentioned, were just
[5098.34 → 5102.82] fed up and said, look, it's easier to do these types of things in the cloud because we get all these
[5102.82 → 5108.26] amazing tools that help us manage. And the hairy problems that we don't want to deal with,
[5108.98 → 5113.62] well, our cloud vendor takes care of that hardware and things like that. And for many businesses,
[5113.62 → 5120.10] it is absolutely the right decision to make to go into the cloud. Not for every business. There are
[5120.10 → 5124.26] those with requirements where they can be a lot more efficient on their own too. And so it's all,
[5124.26 → 5129.70] it's all case by case. And we would help customers understand that and at least provide more data so
[5129.70 → 5134.50] they can make a decision that was right for them. And did you find that it was hard? I mean,
[5134.50 → 5138.50] so one of the challenges that you have is you're writing this layer of software that's sitting
[5138.50 → 5142.50] pretty low in the stack. Because you're talking directly, I assume you're talking to firmware
[5142.50 → 5147.46] to get a lot of information out of the box. Yep. Yep. And I mean, you must discover like things that are,
[5147.46 → 5152.10] are numbers that are wrong, things that are being. Yeah, there, there was a lot of,
[5152.10 → 5159.62] when it comes down to low level firmware, there are a lot of areas where vendors don't do a good job
[5160.50 → 5166.66] writing the firmware. Some examples that made things a challenge, really basic things. You would
[5166.66 → 5174.02] get a box or a customer would have a fleet of systems from HP and you would query a field that
[5174.02 → 5178.74] was supposed to tell you what vendor manufactured the box. And sometimes you would get Hewlett Packard.
[5178.74 → 5184.66] Sometimes you get HP, sometimes you get HPE. Uh, sometimes you would, you would get, you know,
[5184.66 → 5189.22] different spellings of different things, and it made it hard to actually understand what you're
[5189.22 → 5193.30] dealing with. And so we solved a lot of that through software. Right.
[5193.30 → 5198.10] We would look at the different variations and then understand that they were, um, that they were the same
[5198.10 → 5202.18] thing and then normalize those variables. And the customers always like that. Right.
[5202.18 → 5207.62] Lots of DRAM vendors would forget to program registers that identified their part number.
[5209.06 → 5214.10] And so you had to stick a DRAM, and you'd look at the model, and it would be zeros. Right. Or,
[5214.10 → 5222.10] or it's OEM. Exactly. Or, or something else. Uh, and so creating, you know, and consumers wouldn't
[5222.10 → 5226.90] realize this. No one looks at those details until you actually want to do something with that and say,
[5226.90 → 5232.02] hey, I'd like to find out where all of my micron memory is, but surprise, surprise,
[5232.02 → 5237.14] it's not all labelled. Uh, and if you have an error, that's very costly, right? Right.
[5237.14 → 5242.74] You don't know which, which boxes to swap if you needed to, for example. Uh, and so those were some
[5242.74 → 5249.30] of the things that we came across, and it just requires you, it's hard to solve those in software.
[5249.30 → 5255.22] It requires humans to do the right thing in writing specifications and, uh, asking vendors to follow
[5255.22 → 5259.94] those specifications. Yeah. And I think we in software end up like, we're the ones that end
[5259.94 → 5263.62] up having to paper over it. Like, I don't know, like make the different spellings of Hewitt Packard
[5263.62 → 5268.58] look the same, right? I mean, you have to end up, end up having to bury all the bodies there.
[5268.58 → 5272.82] Yeah. And depending on what version of firmware you had, errors would be reported differently.
[5272.82 → 5277.62] For example, you could count errors, single bit errors in DRAM, which were covered by ECC. But then
[5277.62 → 5282.90] you wanted to understand which ones had more errors. Uh, and the counting of the errors was
[5282.90 → 5287.94] different. Some of them would report a raw number. Some of them would count one error for every 10
[5287.94 → 5293.62] physical errors. So you didn't know if you had, uh, one error or 10, uh, and just the standards that
[5293.62 → 5300.26] were fairly, fairly lax across all the, um, firmware vendors. And so, uh, it was, it was always a
[5300.26 → 5304.82] challenge to really understand what was going on with the hardware. Oftentimes you'd have to go to the
[5304.82 → 5309.14] vendor and ask what they were doing. And this stuff is super important because those error counts,
[5309.14 → 5313.22] I mean, those can be your wisps of smoke that can indicate something serious.
[5313.22 → 5313.70] Exactly.
[5313.70 → 5319.14] I mean, the that you may, those correctable may actually be the thing that you need to be able
[5319.14 → 5320.34] to react to. Right.
[5320.34 → 5324.58] To be able to resolve a serious problem. Right. You'd like to know what the trends are. If it stays,
[5324.58 → 5329.14] and we found fascinating trends, right? If errors stayed somewhat constant at a constant rate,
[5329.14 → 5333.86] well, the DRAM would usually chug along. As soon as there was an uptick in those errors,
[5333.86 → 5337.22] you knew it was going to fail within a certain confidence level. Right.
[5337.22 → 5341.30] Uh, and, but you know if you can't even count what they are, it's going to be a hard time.
[5341.30 → 5344.18] And if you know that something's going to fail, you can actually react in advance.
[5344.18 → 5344.66] Right.
[5344.66 → 5345.62] You can actually take action.
[5345.62 → 5350.02] Right. That was a lot of our selling points. Uh, look, we will predict a failure, and you can
[5350.02 → 5353.94] do that fairly well today on hard drives, on DRAM and things like that. There are a number of papers
[5353.94 → 5356.66] that are written about it. There's one company called Back blaze.
[5356.66 → 5358.90] Yeah. Right. Their, their stats are great.
[5358.90 → 5360.82] Right. And they share a lot of those.
[5360.82 → 5362.58] They share a lot of them. I know it's so great.
[5362.58 → 5366.42] Yep. And, uh, that was a good way for us to train some of our algorithms initially.
[5366.42 → 5367.06] All right.
[5367.06 → 5368.26] You use the Back blaze data.
[5368.26 → 5368.58] Oh yeah.
[5368.58 → 5369.14] Yeah. Interesting.
[5369.14 → 5371.94] Yeah. We worked with them on that. We found a number of things.
[5371.94 → 5373.46] Jess, have you looked at the Back blaze data?
[5373.46 → 5375.94] No, I didn't realize that it was open, but I know of Back blaze.
[5375.94 → 5382.02] Well, so Back blaze, yeah. And they basically looked at their, their failure rates across the fleet
[5382.02 → 5384.82] and they basically name and shame ultimately by,
[5384.82 → 5385.46] That's dope.
[5385.46 → 5385.78] Yeah.
[5385.78 → 5388.02] By, by Spindle and firmware rev.
[5388.02 → 5388.42] Right.
[5388.42 → 5388.90] Right.
[5388.90 → 5392.82] And speaking as someone for whom a particular firmware rev from a particular drive vendor
[5392.82 → 5397.22] had a like a serious impact crater in my life. Like this is, this is great information.
[5397.22 → 5397.38] Yep.
[5397.38 → 5398.02] You can go look at it.
[5398.02 → 5400.34] And they would nervously anticipate the release of the next report.
[5400.34 → 5404.34] Oh, absolutely. Oh, I think you are terrified if you,
[5404.34 → 5405.70] Oh, Back blaze reports coming out.
[5405.70 → 5413.14] Well, especially if they don't buy very many. So if they buy a hundred of them and two of them fail,
[5413.78 → 5418.18] their numbers are going to be off the chart. So it's like, you want to sell Back blaze nothing,
[5418.18 → 5422.42] or you want to sell them as much as you physically can, because then the numbers are,
[5423.14 → 5426.90] and because they are not many folks do that. I mean, they don't.
[5426.90 → 5429.30] I definitely tip my hat to them for starting that trend.
[5429.30 → 5429.78] Yes.
[5429.78 → 5435.46] The idea with Coolant and every customer that sent us data, part of our legal agreement was that
[5435.46 → 5437.30] we could use that data anonymously.
[5437.30 → 5438.26] Really? Oh, interesting.
[5438.26 → 5444.26] And the idea was to do what Back blaze was doing, but do it across more components at a larger scale too.
[5444.26 → 5450.02] Now you have it coming from different environments, different systems. How does OneDrive interact
[5450.02 → 5451.86] with one particular motherboard? Right.
[5451.86 → 5457.94] How does one firmware fan control algorithm, which cools differently in an HP system than a Dell system,
[5459.06 → 5465.38] result in failure rates across different components. And so to have a much larger pool of data and be able to
[5465.38 → 5470.18] share that anonymously, because there's only so much data you can crunch yourself. But with the
[5470.18 → 5472.18] community was part of the idea too.
[5472.18 → 5473.06] That's a great idea.
[5473.06 → 5474.18] Yeah.
[5474.18 → 5477.70] It's still something we didn't quite get to that, unfortunately.
[5477.70 → 5484.58] It's a hard one, because you would ideally, all the vendors should want to collaborate to get these problems solved.
[5484.58 → 5485.22] Yes.
[5485.22 → 5487.46] But that's not always the idea we're on.
[5487.46 → 5488.18] Should want.
[5488.18 → 5492.34] What we found was that vendors wanted access to the data.
[5492.34 → 5492.98] Yeah.
[5492.98 → 5497.46] Some of them were even willing to pay for it, because it's hard for them to get field data.
[5498.18 → 5500.82] That was step one that we discovered.
[5502.18 → 5507.78] We didn't quite get to publicly posting any of the data.
[5507.78 → 5510.98] Yeah. And that basically had to do with the business of the startup.
[5510.98 → 5511.38] Right.
[5511.38 → 5519.22] It would have taken a few more years to get there. And continuing the business became a challenge for us.
[5519.22 → 5526.42] It's tough. It's a tough software to write, and then it's tough to sell.
[5526.42 → 5529.14] But unfortunately, Salesforce obviously saw a lot of value in it.
[5529.14 → 5536.58] Yeah. So at some point, we came to get funding. And this is a good point for you guys.
[5536.58 → 5538.10] And that's when the clock starts ticking.
[5539.62 → 5547.78] And you have a certain window for where you need to show enough value so that other investors will come and agree to give you more money.
[5548.90 → 5552.98] You can get enough revenue from customers to keep yourselves afloat.
[5554.02 → 5557.70] Or you can shut down the company. Or you can sell the company.
[5558.58 → 5562.50] And we got far along enough where we had some value. We had revenue coming in.
[5562.50 → 5566.10] And we had a hard time raising more money from ventures.
[5567.62 → 5578.82] Primarily because a lot of venture operators had this thesis that things were moving to the cloud and infrastructure, owned infrastructure was going away.
[5578.82 → 5579.86] We are familiar with this thesis.
[5580.90 → 5582.10] We are very contrarian.
[5582.10 → 5584.18] We've heard this a couple of times.
[5584.18 → 5584.42] Yep.
[5585.14 → 5592.58] And so I had a hard time convincing them that infrastructure was going to continue to run outside the hyperscalers.
[5593.14 → 5598.10] Some of them weren't even interested in hearing some of the reasoning behind it.
[5598.10 → 5601.54] They said, sorry, we operate in this way. We're not going to entertain a conversation.
[5601.94 → 5602.10] Right.
[5602.10 → 5607.36] And when you kind of phrase it, it's like, so do you believe that Jeff Bezos is going to own and operate every computer on the planet?
[5607.44 → 5608.36] Like, well, no, of course not.
[5608.64 → 5610.78] We just think that everything is moving to the public cloud.
[5611.02 → 5612.74] And on that public cloud is going to be an WS.
[5612.78 → 5613.22] I'm like, okay.
[5614.14 → 5614.42] Exactly.
[5614.78 → 5619.02] And like I said before, there are many reasons why running your own infrastructure makes sense.
[5620.64 → 5621.94] Before you didn't have a choice.
[5622.26 → 5623.32] Now you have a choice.
[5623.56 → 5626.28] And you have to make the evaluation if it makes sense.
[5626.28 → 5631.02] And I don't know if you want to go into the reasons of when it does, but it does in some cases.
[5631.46 → 5636.30] And I don't think many companies are equipped to make that evaluation on their own.
[5636.66 → 5638.62] It's a fairly thorough evaluation.
[5639.14 → 5640.22] I've done it several times.
[5640.92 → 5644.86] But no, everyone, there will be infrastructure outside the cloud.
[5644.98 → 5646.10] There's no doubt about that.
[5646.78 → 5648.02] I mean, we definitely believe that.
[5648.28 → 5653.96] And even as that expertise is being lost, I mean, I remember in, boy, it was in 2011 at Surge,
[5653.96 → 5657.26] asking show of hands how many people had stood up their own physical infrastructure.
[5657.48 → 5659.70] And only a quarter of the hands went up in 2011.
[5660.06 → 5660.08] Wow.
[5660.80 → 5662.62] And that number is not going.
[5662.78 → 5666.44] I mean, so I think that that's part of the challenge is that those people that are still
[5666.44 → 5671.04] deploying physical servers feel like the world has left them behind.
[5671.30 → 5671.42] Right.
[5671.80 → 5672.84] It doesn't need to be that way.
[5672.90 → 5674.04] Look, it's not rocket science.
[5674.10 → 5680.18] With a team of 10 people, we did a completely custom rack and server and power supply design for Facebook.
[5680.18 → 5684.18] It's not, you're not sending an orbiter to the moon or anything like that.
[5684.24 → 5686.10] You're building server infrastructure.
[5686.34 → 5688.78] And with talented software engineers, you can manage it well.
[5689.06 → 5689.36] Okay.
[5689.42 → 5691.24] It doesn't require huge armies.
[5691.26 → 5694.56] Thank you very much for differentiating this from the Apollo program.
[5694.98 → 5698.22] I get so sick of being like, wow, this is a moonshot.
[5698.40 → 5700.68] It's like, easy, easy, easy.
[5700.74 → 5701.96] This is not a moonshot.
[5702.54 → 5704.18] The actually, the Apollo program was actually-
[5704.84 → 5705.62] A little more tricky.
[5705.78 → 5706.46] A little more tricky.
[5706.68 → 5707.64] A little more ambitious.
[5708.18 → 5708.34] Yep.
[5708.34 → 5717.10] And, you know, because the flip side of all of this is that the infrastructure is more accessible than ever before.
[5717.24 → 5720.60] I mean, if somebody, you know, OCP, you look at how much is available via OCP.
[5720.86 → 5721.00] Yep.
[5721.70 → 5724.00] Open source software, open source firmware.
[5724.28 → 5728.56] And if people want to get interested in this stuff, it's way more accessible than it ever has been.
[5728.68 → 5728.84] Yep.
[5729.12 → 5729.30] Yep.
[5729.30 → 5735.52] You have to have right sponsorship, right leadership directions, a small willingness to invest in smart people to do this.
[5735.60 → 5736.58] But it's totally possible.
[5736.58 → 5740.14] And a lot of people have worked out some of the really hard problems.
[5740.30 → 5744.22] I mean, you were, like the bus bar in the OCP design.
[5744.22 → 5747.76] And you had a great anecdote about the safety of that.
[5747.94 → 5748.14] Right.
[5748.48 → 5748.66] Right.
[5748.74 → 5750.82] A lot of it, I would call it FUD, right?
[5750.92 → 5752.16] Fear, uncertainty, and doubt.
[5752.16 → 5756.48] And that came up many times throughout the development of the project.
[5756.98 → 5759.20] The bus bar you mentioned runs 48 volts.
[5759.20 → 5764.78] And it was used to back up the servers when the main primary power source failed.
[5764.92 → 5773.80] And so you'd get these large copper bu sways with, this was in the battery cabinet, with, you know, thousands of amps running through them at 48 volts.
[5773.80 → 5782.84] And it's counterintuitive, but 48 volts aren't enough potential to draw enough current through the human body to cause any sort of, you don't even feel it.
[5782.90 → 5783.02] Right.
[5783.02 → 5785.76] So it was like, on the way, like you can think of the 48 volts.
[5785.82 → 5790.00] On the other hand, thousands of amps is enough to absolutely kill you.
[5790.12 → 5790.18] Right.
[5790.18 → 5792.74] So it's like, you've got to like, you touch that first.
[5792.90 → 5793.04] Right.
[5793.12 → 5795.66] So we'd sit there and almost play chicken, right?
[5795.78 → 5795.98] Right.
[5796.16 → 5797.04] Who wants to touch it?
[5797.08 → 5798.46] We know it's not going to do anything.
[5798.58 → 5798.68] Okay.
[5798.68 → 5799.84] I have the software guy.
[5799.94 → 5801.10] I'm at the back of the line.
[5801.20 → 5802.72] I will let everyone else touch it first.
[5802.76 → 5803.82] So who touched it first?
[5803.88 → 5804.00] Right.
[5804.04 → 5807.10] So our power engineer, Pierre Luigi, said, come on, guys.
[5807.40 → 5807.94] Get out of my way.
[5808.04 → 5813.04] And he is like stepped aside, touched the bus bar as we were discharging the batteries into it.
[5813.20 → 5814.20] And nothing happened.
[5814.26 → 5814.42] Right.
[5814.46 → 5815.26] So I said, oh, cool.
[5815.54 → 5815.72] All right.
[5815.76 → 5816.06] Me next.
[5816.18 → 5819.34] And then I think we're the only two who touched it.
[5819.90 → 5823.94] But, you know, the fear of, hey, something could happen.
[5824.02 → 5825.10] I don't quite understand it.
[5825.10 → 5825.98] I don't see it.
[5826.92 → 5828.58] Definitely was a factor there.
[5828.68 → 5832.22] And it kept going for many things within the project, too.
[5832.80 → 5836.50] One other thing we did, quick anecdote, was we took off the BMC from the server.
[5837.28 → 5839.80] How do you run a server without a management controller?
[5840.16 → 5844.14] For those who don't know, it's a small little processor that sits on the server, and it pulls
[5844.14 → 5848.56] a couple of bits of information and sends them back over a management network.
[5848.74 → 5853.56] So you could still control the server, even though your operating system had crashed or
[5853.56 → 5854.50] your kernel had crashed.
[5854.50 → 5859.82] And we looked at it, and we said, look, it's primarily used to reboot boxes.
[5860.32 → 5861.24] And that is all.
[5862.16 → 5864.68] No one was using it for much more other than that.
[5864.76 → 5868.98] If you want to collect metrics from the box, it's always better to go through the operating
[5868.98 → 5869.54] system.
[5869.66 → 5869.92] Yeah, exactly.
[5870.10 → 5871.72] Way more information that way.
[5871.82 → 5876.42] You're limited by whatever the whoever wrote the BMC firmware, the management controller
[5876.42 → 5877.68] firmware did.
[5877.80 → 5881.46] And they never thought of every bit of information you wanted to pull from the box.
[5881.52 → 5883.42] So you just went from the operating system.
[5884.38 → 5885.16] We said, great.
[5885.36 → 5889.16] We're just going to get rid of this BMC because we're not using it except for rebooting the
[5889.16 → 5889.46] box.
[5889.70 → 5891.28] And of course, up in arms.
[5891.50 → 5891.58] Right.
[5891.74 → 5892.10] Heresy.
[5892.40 → 5892.80] Heresy.
[5892.98 → 5893.76] How could you run?
[5893.84 → 5899.98] What if someone messes something up, and you need to get to the box and the kernels crashed?
[5900.74 → 5902.60] And I said, look, then you got other problems.
[5903.84 → 5905.50] But we'll be able to reboot the box.
[5905.60 → 5910.72] What we did is we took this thing called the magic packet, which was a special Ethernet
[5910.72 → 5915.14] packet you could send to a host, and it would cause the host.
[5915.24 → 5917.68] At the time, it was designed to cause it to wake.
[5918.02 → 5921.46] So you'd put a host in a sleep state, and you sent it the magic packet, and it would wake
[5921.46 → 5922.90] on LAN is what we called it.
[5923.22 → 5923.84] Wake on LAN.
[5925.44 → 5926.22] It depends.
[5926.68 → 5927.60] It doesn't depend.
[5927.84 → 5928.64] It's wake on LAN.
[5928.84 → 5929.70] It doesn't depend on anything.
[5929.70 → 5930.62] It's not waked on LAN.
[5930.74 → 5931.30] It depends.
[5932.20 → 5934.92] I was actually saying LAN is the magic packet for Jess.
[5934.98 → 5936.32] That's what actually wakes Jess up.
[5937.42 → 5937.76] Exactly.
[5938.20 → 5938.48] Nice.
[5939.20 → 5944.88] So instead of tying that to the wake on LAN signal from the Ethernet controller, we tied
[5944.88 → 5947.18] it to the reboot signal.
[5948.20 → 5954.22] Obviously, we did some things to make it secure because you don't want to broadcast this packet
[5954.22 → 5954.84] across your network.
[5954.84 → 5956.16] Oh, but what a story that would be.
[5956.22 → 5957.80] What a story that would be.
[5957.88 → 5959.22] We didn't want the whole cluster to reboot.
[5959.22 → 5964.90] But we implemented that in the first version of OCP, and we cut our $40 from the bill of
[5964.90 → 5967.18] materials from a box, which was fairly significant.
[5967.40 → 5967.50] Right.
[5967.68 → 5968.28] To eliminate the ESA.
[5968.56 → 5970.56] And we deployed and it worked.
[5970.72 → 5974.04] And it was working just fine until...
[5974.04 → 5975.78] The PFC industrial complex got wind of this.
[5975.78 → 5978.04] No, not quite.
[5978.04 → 5983.34] Until someone fat-fingered a command and re-IP'd several hundred teacake servers in the cluster.
[5983.96 → 5989.68] So think of a cluster that the teacake server sits between the database and the web server
[5989.68 → 5995.50] and it serves out 99% of the queries because everything's hot and cached and your database
[5995.50 → 5998.72] can be much smaller at that point.
[5998.80 → 5998.98] Right.
[5999.54 → 6002.34] And so these teacake servers went offline, and you take the cluster...
[6002.34 → 6002.64] No problem.
[6002.68 → 6003.34] We'll just go to the database.
[6004.22 → 6004.90] Doesn't work.
[6005.38 → 6011.92] You take the cluster down and to bring it back up takes about 24 hours because you have to warm up the teacake servers again.
[6011.92 → 6021.06] And that happened, and they said, look, luckily this had happened in an older cluster that didn't have OCP servers in.
[6021.12 → 6022.48] And what did they do to fix it?
[6022.70 → 6028.12] They logged in through the BMC and re-IP'd all the machines to their proper addresses that way
[6028.12 → 6031.60] because you could get console access through the BMC and re-IP them.
[6031.70 → 6033.94] They said, look, thank God we had this BMC.
[6034.76 → 6039.06] We didn't require us to wait 24 hours to restart this cluster.
[6039.06 → 6041.86] And they came to me and said, look, Amir, this is a problem.
[6042.02 → 6042.64] See what happened.
[6042.74 → 6044.76] This is why you need a BMC on the box.
[6045.28 → 6046.88] And I said, is that really the problem?
[6046.98 → 6052.88] Or is the problem that you allowed someone to re-IP a bunch of servers and didn't have any safety protections in there?
[6053.04 → 6053.24] Right.
[6053.58 → 6053.76] Right?
[6054.40 → 6055.40] They don't want to hear that answer.
[6055.42 → 6056.00] That wasn't the problem.
[6056.08 → 6056.46] Yeah, yeah, exactly.
[6056.46 → 6057.26] The problem was the BMC.
[6057.34 → 6057.60] Exactly.
[6057.70 → 6058.56] The problem is the BMC.
[6058.68 → 6062.04] So in the next generation of servers, the BMC came back.
[6062.14 → 6063.84] The BMC returned.
[6063.94 → 6064.20] Nice.
[6065.72 → 6066.12] Interesting.
[6066.12 → 6066.20] Interesting.
[6067.04 → 6075.06] So in terms of going forward, I mean, we feel that the lost art of deploying hardware is going to come back.
[6075.44 → 6076.56] What's your take on it?
[6076.68 → 6078.48] I don't think it ever disappeared.
[6078.80 → 6084.54] I think people's willingness to want to do that has been diminishing.
[6084.54 → 6087.14] But the talent is still there.
[6087.24 → 6096.58] The ability to do that is even more so present today than it used to be with, like you mentioned, lots of open source tools that can help you deploy.
[6096.90 → 6098.92] I mean, you can make your own microprocessor, right?
[6098.96 → 6103.96] You think it is like, in terms of like people taking, it's amazing how much you can go do.
[6104.14 → 6104.36] Yeah.
[6105.12 → 6109.52] And people being able to do FPGAs on their own.
[6109.72 → 6112.20] A logic analyzer is like a hundred bucks now or whatever.
[6112.20 → 6112.68] Yep.
[6113.04 → 6113.22] Yep.
[6113.34 → 6117.06] You have to have the right people and the willingness to do it, but it's definitely possible.
[6117.32 → 6121.56] And for the right cases, you can save a ton of money and be more efficient that way too.
[6122.24 → 6126.28] So, you know, with that, it's going to be a constant pool.
[6126.46 → 6134.58] And if you think about who's making the decisions oftentimes, it's not necessarily an infrastructure-based decision always.
[6134.58 → 6141.42] It's around agility and your ability to put your product out on the market faster.
[6142.72 → 6151.46] If you don't have a team that's performing well and as far as your infrastructure goes, and you want to release a product, and they become a bottleneck, well, it doesn't really matter.
[6151.80 → 6155.98] You're just going to go to the cloud because you have a business to run, and your business is selling a product.
[6155.98 → 6162.12] And if you don't have a factory internally that can build your product for you, then you go to the cloud.
[6162.84 → 6170.90] If there's an easy way to do that, I think then there's a much better case for building your own infrastructure.
[6171.44 → 6173.92] God, someone should start a company.
[6174.24 → 6174.62] I agree.
[6174.94 → 6176.42] I like the way you're thinking, Amir.
[6176.66 → 6176.92] Good.
[6177.56 → 6178.18] That is great.
[6178.18 → 6180.18] Well, Amir, this has been great.
[6180.86 → 6188.86] This has been a lot of fun to hear about your career and a lot of interesting, exciting stuff at the hardware-software interface.
[6189.84 → 6195.06] People want to learn more about you and about your, what's your social media of choice?
[6195.50 → 6198.60] Yeah, you can find me at facebook.com slash Amir.
[6199.08 → 6202.24] On Twitter, I'm D-G-A-M-I-R, D-I-G-I-A-M-I-R.
[6203.76 → 6205.38] And I'm more than happy to connect.
[6205.80 → 6206.24] Awesome.
[6206.24 → 6209.38] Well, thank you very much for your time.
[6209.50 → 6210.64] Thank you for joining us in the garage.
[6210.78 → 6212.16] This has been a lot of fun.
[6212.26 → 6212.74] Yeah, thank you.
[6212.78 → 6213.06] Thank you.
[6213.24 → 6213.64] My pleasure.
[6213.78 → 6214.46] Thanks for having me.
[6215.48 → 6219.50] You've been listening to On The Metal, tales from the hardware-software interface.
[6219.90 → 6225.24] For show notes, to learn more about our guests, or to sign up for our mailing list, visit us at onthemetal.fm.
[6226.38 → 6228.78] On The Metal is a production of Oxide Computer Company.
[6228.94 → 6232.14] It is recorded in the Oxide Garage in Oakland, California.
[6232.44 → 6235.80] To learn more about Oxide, visit us at oxide.computer.
[6235.80 → 6239.30] On The Metal is hosted by me, Brian Cantwell, along with Jess Fri sell.
[6239.50 → 6241.96] And we are frequently joined by our boss, Steve Tuck.
[6242.18 → 6246.08] Our original and awesome theme music is by J.J. Wrestler at Pollen Music Group.
[6246.34 → 6250.06] You can learn more about J.J. and Pollen at pollenmusicgroup.com.
[6250.40 → 6254.24] We are edited and produced by Chris Hill and his crew at Humble Pod.
[6254.68 → 6258.80] From Jess, from Steve, from me, and from all of us at Oxide Computer Company,
[6259.08 → 6260.42] thanks for listening to On The Metal.
[6260.42 → 6261.14] On The Metal.
[6261.14 → 6265.92] NVMe
[6266.46 → 6267.58] No water, please.
[6268.62 → 6269.84] Yes, there, please.
[6279.00 → 6285.34] We are we ready, Tony, and I'll see you next time.
[6285.34 → 6287.26] We will see you next time to catch this call.
[6287.26 → 6317.24] Thank you.
