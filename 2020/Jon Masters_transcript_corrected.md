[0.00 → 16.46] Welcome to On The Metal, tales from the hardware software interface.
[16.92 → 20.18] I'm Brian Cantwell. With me, as always, is Jess Frizzell. Hey, Jess.
[20.56 → 21.00] What's up?
[21.58 → 25.36] Joining us in the garage is also our boss, Steve Duck. Hey, Steve.
[25.62 → 26.38] Pleased to be here.
[26.38 → 34.20] Also, we have an On The Metal first. We have got a live studio audience consisting of Oxide Computer Company founding engineer Robert Moustache.
[34.44 → 35.96] Hello, Robert, even though you're unmixed.
[36.54 → 36.98] Evening everyone.
[37.18 → 42.88] There you go. This is also a very special On The Metal because it is after dark in the garage.
[43.20 → 48.28] This is On The Metal after hours. Jess, do you want to introduce who we've got in the garage?
[48.64 → 56.66] So today we have John Masters, really well-known around ARM and that ecosystem, but also got a sweet new job.
[57.20 → 62.64] Sweet new job, well-known around ARM. And John, first, welcome to The Garage. It's great to have you.
[62.80 → 63.86] Thank you. It's great to be here.
[64.28 → 67.44] So it is all that's true, well-known about ARM and well-known.
[67.88 → 69.14] I'm awesome. I know. I agree.
[69.14 → 76.04] But you and I got to know one another in a little issue they call Spectre and Meltdown.
[76.76 → 83.56] So you want to walk us through, when did you learn and how about Spectre and Meltdown?
[83.62 → 88.88] Because I think you definitely got an earlier look at this than I and we did.
[88.98 → 91.06] What was your reaction when that all went down?
[91.06 → 100.10] Yeah, well, I think if anyone follows my Twitter, they can see that I'm very interested in computer architecture.
[100.64 → 104.72] And over the past few years, kind of interest has become an obsession.
[104.98 → 108.04] And we can talk about, you know, kind of where that ended up taking me professionally.
[108.26 → 114.04] But because of that interest in the fundamentals of how computers really work underneath
[114.04 → 122.22] and many of the things related to my interest in architecture, I ended up kind of tracking a lot of the academic research that was happening.
[122.80 → 128.48] There had been a lot of side-channel analysis papers using caches as a side-channel.
[129.32 → 135.50] And there was a blog post in the summer of 2017.
[136.44 → 139.40] Well, there were several, but there were, you know, it's one I'm thinking of in particular,
[139.40 → 145.34] which basically says, you know, this thing could happen, and then this thing could happen and then badness would result.
[145.70 → 147.32] But good news is none of that's true.
[148.22 → 152.88] And I read through this, and I'm like, okay, but there's not really any reason why this is not true.
[152.98 → 156.54] It just seems like you didn't write the next part of your blog post, right?
[157.18 → 163.30] And it turns out there were a lot of people thinking similarly, and they had presumably talked with one another
[163.30 → 168.44] or other companies have been involved, and they decided not to enumerate exactly what they had found.
[168.44 → 176.32] But it became increasingly concerning during the latter part of 2017 that something very, very bad was going on.
[176.94 → 181.44] And this is, you know about Spectre, but not yet Meltdown.
[181.72 → 184.22] No, it was Meltdown that we were concerned about.
[184.42 → 185.24] Well, yeah, Meltdown was...
[185.24 → 185.44] Well, yeah, Meltdown was...
[185.44 → 185.84] Yeah.
[186.06 → 188.28] Meltdown is just malpractice.
[188.38 → 188.56] I don't know.
[188.62 → 189.70] I mean, in terms of like Meltdown...
[189.70 → 192.48] Spectre feels at some level like original sin.
[193.34 → 194.34] It's forgivable.
[194.56 → 195.38] We're all humans.
[196.14 → 196.54] Meltdown.
[196.54 → 198.52] Were they found at the same time?
[199.10 → 199.80] Well, that's...
[199.80 → 200.62] I mean, this is what John's saying.
[200.70 → 202.14] What is the exact chronology there?
[202.24 → 204.56] Well, I think the researchers did find...
[204.56 → 206.86] They did sort of come together at the same time.
[206.96 → 211.26] And the reason that they came together at the same time was because, again, you know,
[211.28 → 212.64] these things don't happen in a vacuum.
[212.78 → 218.18] What happened was the security research community found many, many different issues with side channels,
[218.30 → 220.42] with caches over the course of several years.
[220.42 → 229.20] People were starting to wonder about if you can infer the state of execution, or you can monitor other threads that are running.
[229.78 → 231.30] You know, oh, what would happen if...
[231.30 → 239.00] And then they started thinking about this thing called speculative execution, which is how modern microprocessors give you the performance that you're used to.
[239.00 → 239.34] Right?
[239.46 → 249.30] So what a modern processor does in a phone or a server, pretty much any computing device, it's not a very, very simple Fitbit or widget, is it will speculate ahead.
[249.50 → 253.76] And it will say, I know this is the program you gave me, but I'd like to go faster.
[253.76 → 264.42] So I'm going to start to guess ahead about the course of execution while I wait for data to come in from memory or for other things to happen that would normally mean that I would have to just stop.
[264.60 → 264.82] Right.
[264.90 → 266.42] This is the way we got around the memory wall.
[266.78 → 271.78] In the late 90s, early 2000s, we were hitting the memory wall where we were just going to be stalled from memory all the time.
[272.00 → 272.26] Right.
[272.40 → 279.64] And this is when rampant speculation became frenetic speculation, became madness.
[279.88 → 281.50] Well, I mean, a load from memory is what?
[281.54 → 282.88] 100 nanoseconds, right?
[282.88 → 289.72] So if you sort of cost out, you know, modern computers are called, you know, load store machines, right?
[289.78 → 290.12] Basically.
[290.32 → 294.74] So you load something from memory, you do something with it, you store it back, or you write the results back.
[295.14 → 298.60] And if you have data in a we will answer your question, I promise.
[298.96 → 307.74] If you have data in a cache and an internal memory inside the processor, accessing it is progressively faster depending on which level of cache it's in.
[307.74 → 316.40] As the cache level, as the number goes down, like the L1 is like superfast, but really tiny and very close to where the execution is happening.
[316.72 → 321.70] And then you get these caches that are further and further away from the action, but they're bigger.
[321.84 → 325.96] Because the laws of physics say you can have small and fast or big and slow.
[326.22 → 326.64] Pick one.
[327.04 → 327.80] You don't get both.
[328.10 → 328.24] Right.
[328.24 → 346.38] Anyhow, so there was a lot of research happening in terms of abusing cache behaviour because an artifact of caches is that they are designed to speed up execution by caching things, by keeping copies of data that you've recently used or recently loaded from memory or stored to memory.
[346.38 → 351.70] And you can perform an analysis on how long it takes to perform, to read or write a value.
[351.84 → 355.90] And you can say, well, if it took me this many nanoseconds, then I got it from memory.
[356.08 → 361.24] Or if I only took this many nanoseconds, then it must have been in a cache.
[361.32 → 364.44] And if it was in a cache, then that meant somebody else was using it recently.
[364.58 → 368.64] And so you can infer things about other execution that's happening on the processor.
[369.18 → 369.36] Right.
[369.74 → 372.54] So many attacks have happened exploiting that.
[372.54 → 376.50] And then meltdown is, yeah, meltdown is an egregious mistake.
[377.36 → 377.54] Right.
[377.96 → 390.10] Meltdown is basically when you have a microprocessor, and you want to access some privileged data, what you're supposed to do is enforce permission checking.
[390.44 → 390.52] Right.
[390.60 → 394.98] Permission checking is basically that you have what are called page tables in memory.
[394.98 → 401.84] They translate the addresses used by programmers into the underlying physical addresses used by the hardware.
[402.62 → 409.58] And in meltdown, what happens is, or what's supposed to happen is, you're supposed to walk through these page tables describing these translations.
[410.68 → 418.62] And you're supposed to look at the page table, say, well, this address maps to this address, this address maps to this address, as I'm loading and storing and reading and writing memory.
[418.62 → 424.54] And as part of that entry, it also has various permission information about whether I should be able to read or write that.
[425.20 → 430.34] To speed things up, what the vulnerable processors do is they parallelize that piece.
[430.68 → 438.46] So I will check the permission in parallel with also doing the access, assuming that most programs, you know, assume good intent.
[438.84 → 438.96] Right.
[439.08 → 440.14] Assume good intent.
[440.18 → 440.34] Right.
[440.34 → 444.26] No, that is a motto in like an organization, not a motto in a CPU.
[444.70 → 449.14] Well, you know, I was listening to one of the older Oxides on the Metal podcasts.
[449.62 → 453.50] And, you know, there was a piece about some of these older machines.
[453.80 → 456.28] An ICL-286 got mentioned, I think.
[456.48 → 460.90] And I grew up in the UK, so I remember these ICL honking great machines too well.
[460.90 → 467.94] You know, and when you're at that stage of the evolutionary process, these machines really were a single user.
[468.24 → 468.36] Right.
[468.40 → 471.58] They were incredibly big and loud and slow and all these other things.
[471.68 → 477.54] And so, you know, you could assume they're one person using it and security is, this is my computer.
[477.74 → 478.94] They were basically Arduino's.
[479.42 → 479.70] Yeah.
[480.16 → 480.36] Yeah.
[480.40 → 481.78] And I have a key on the front as well.
[481.84 → 482.62] So this is my computer.
[482.84 → 483.76] And when I'm done, I lock it.
[483.86 → 484.96] I turn the key and everything's good.
[485.00 → 485.18] Right.
[485.18 → 488.68] So that kind of mentality is where we came from.
[488.86 → 492.54] And processors we have today just evolved versions of that.
[492.88 → 496.14] So it sort of did assume good intent.
[496.40 → 496.68] Right.
[497.10 → 498.32] Because that's where we came from.
[498.80 → 507.90] Anyway, so they will optimize for the safe path and access the data that it should not access.
[507.96 → 512.28] Again, speculatively, meaning that this is something that you're not supposed to see or even know happened.
[512.28 → 521.16] But because it leaves this cookie, these breadcrumbs in terms of the cache impact, you can then go and do this analysis afterwards.
[521.16 → 524.38] And you can say, oh, this data must have been accessed because the timing is different.
[525.10 → 526.36] So that's what Meltdown is.
[526.40 → 537.08] And in fact, if you go read Computer Architecture, which is a well-known book by Patterson and Hennessey, it actually has, I think, an appendix B page.
[537.58 → 540.10] I can't quite remember the page anymore, but it's an appendix B.
[540.10 → 545.20] There is actually a whole paragraph around making sure you get this permission check correct.
[546.44 → 548.00] Now, somebody did—
[548.00 → 551.28] Yeah, I think that page was ripped out of copies in Santa Clara or in Hillsboro?
[551.50 → 551.64] Or what?
[552.10 → 554.46] Well, I'm a very nice guy.
[554.64 → 555.78] And so I certainly did not—
[555.78 → 556.18] That's not true.
[556.28 → 556.86] Yeah, that's right.
[557.02 → 558.16] That's not even close to true.
[558.36 → 560.28] We can't let the listeners come away with that inference.
[560.50 → 562.88] I certainly did not buy a copy of that book.
[562.98 → 563.68] Okay, that might be true.
[563.68 → 571.06] And put a bookmark on that page and have it ready gift wrapped to send to anybody for—
[571.06 → 573.58] Right, Bob Swan has got a—
[573.58 → 578.24] I may have done that, and I may have gift wrapped it and had it ready to go for the holidays.
[578.58 → 579.26] There you go.
[579.56 → 582.68] And then I thought better in terms of self-preservation, and I didn't send it.
[582.74 → 584.68] But I did have that ready to go.
[585.02 → 586.90] This must have been Christmas of 2017.
[587.14 → 587.46] Yes.
[587.46 → 592.30] Because I heard about it—the rest of the world heard about this in—
[592.30 → 593.04] January 3rd.
[593.24 → 593.64] January.
[594.10 → 599.14] Well, I think the Hacker News post was on January 1st, where someone had gone through the Linux patches
[599.14 → 601.32] and was beginning to, like, piece it together.
[601.44 → 602.14] To figure it out.
[602.18 → 604.24] That something was going very, very wrong.
[604.52 → 610.70] And I just—it's like the—you know if you've seen Boogie Nights, when it goes from 1979 to 1980,
[610.96 → 613.70] that midnight in 1980, it starts with a gunshot.
[613.98 → 614.16] Yeah.
[614.16 → 615.70] That was January 1st, 2018 for me.
[615.70 → 617.04] There's a leap second in there somewhere.
[617.04 → 617.84] It's gone wrong.
[618.06 → 620.48] There was a gunshot that was Spectrum Meltdown.
[620.58 → 623.46] I remember reading that and thinking, like, I got to go talk to Robert.
[623.58 → 627.28] I really hope—are we both—this is definitely going to affect us.
[627.28 → 630.10] And then you begin to realize, like, oh, my God, we are so screwed.
[630.44 → 632.52] Well, I thought it would be front-page news.
[632.84 → 634.70] Everybody's cell phone is broken, right?
[634.76 → 639.68] Because I was thinking, you know, what's the exciting thing to attack today, right?
[640.06 → 642.24] It's—because Meltdown was, you know, everywhere.
[642.24 → 645.56] I mean, I'm not going to speak to exactly, you know, who had Meltdown and who didn't.
[645.56 → 647.56] But, you know, it was everywhere.
[647.70 → 651.32] And I thought that there would be a lot more—the news would be more sensationalist around,
[651.58 → 654.28] oh, your apps are spying on each other and all this kind of thing.
[654.28 → 656.42] You thought the news was not adequately sensationalist?
[656.42 → 657.64] Well, I thought it would be worse.
[657.64 → 662.46] I feel like it wasn't as bad for people who are outside, like, our circle.
[662.46 → 665.00] Because I remember exactly where I was when I found out.
[665.04 → 668.18] And I was picking out wedding dresses with my sister for her wedding.
[668.48 → 675.52] And, like, I was trying to tell her exactly the like, virality of this.
[675.70 → 677.44] And she was like, no, I don't get it.
[677.46 → 678.74] And I was like, no, like, this is also—
[678.74 → 681.44] She's like, also, like, are you trying to, like, yuck my wedding?
[681.62 → 682.44] Like, this is like—
[682.44 → 683.66] She was like, why are you trying to ruin my wedding?
[683.66 → 684.68] Why are you so distracted?
[684.82 → 685.94] Can you just, like, fucking focus?
[686.50 → 687.14] But, yeah, no.
[687.64 → 690.44] I really was because I was like, holy shit, like, this is crazy.
[690.44 → 690.78] This is bad, yeah.
[690.88 → 694.06] And so you'd think that, like, the New York Times would have, like, some sort of cover page on it.
[694.06 → 694.76] I was expecting front page.
[695.24 → 695.40] Yeah, yeah.
[695.52 → 700.04] No, but it was more the hacker news, like, very under—the very tech crowd.
[700.04 → 701.62] For the first two days, it was—
[701.62 → 702.18] Then it blew up.
[702.20 → 702.76] Then it blew up.
[702.84 → 702.94] I mean, it did blow up.
[702.94 → 704.32] No, but there was no hacker news.
[704.70 → 707.00] There was no, like, New York Times front page.
[707.34 → 709.92] It was—it felt damn near front page.
[709.92 → 710.52] By the time it blew up—
[710.52 → 712.22] It wasn't quite there.
[712.28 → 713.20] Maybe it just felt that way.
[713.20 → 716.86] I tell you, so Jess making that comment, she has—what is it?
[717.36 → 718.94] Containerize.AF, right?
[719.34 → 721.98] She has these, you know, please log into my machine and break it.
[722.54 → 725.20] And there was a little voice in my head that was, you know—
[725.76 → 726.82] That's not nice.
[726.92 → 728.26] That's not what Jess meant.
[728.36 → 728.86] No, no, no.
[729.08 → 732.06] I was like, I can't do it because it's an embargoed issue, and I'm not.
[732.34 → 735.42] And I hasten to say, I would never actually do that.
[735.62 → 737.84] But I did think for a minute, it's like, oh, I could break your machine.
[737.84 → 743.50] I am only the kind of person that buys a computer architecture manual and bookmarks the page that you ignored and gift strap it.
[743.62 → 745.74] I am not the kind of person that—there we go.
[745.82 → 746.26] It's a fine line.
[746.30 → 747.14] I use this example.
[748.14 → 750.06] Okay, so another example like that, right?
[750.10 → 753.28] So when I was in high school, we had a sailing club.
[753.28 → 758.64] And, you know, I'm the kind of guy who likes to know how to break things, but I don't like to be the one who actually breaks it myself.
[758.76 → 759.04] There you go.
[759.18 → 761.04] In a black hat kind of way, right?
[761.04 → 761.12] Right.
[761.56 → 770.66] So we had vending machines in the dock, in the boathouse there, where, you know, you could buy candy or whatever after you'd sailed.
[770.84 → 780.32] And I told the other kids, I said, well, you know, if you turn it off at the wall and turn it on, it goes into like a diagnostic mode for the first few minutes and dispenses free products.
[780.32 → 783.98] And they're like, no, can't possibly be true.
[784.22 → 785.12] But it is true, right?
[785.18 → 786.76] So they—I mean, that's not—don't do that.
[786.84 → 787.48] That's not good.
[787.54 → 789.60] And that's not true in most modern vending machines.
[789.64 → 790.44] But it was at the time.
[790.90 → 794.76] And so they turned it off and turned it on, and they dispensed—they cleaned the whole thing out.
[795.32 → 800.32] And we promptly got banned from ever going back into the—we were allowed to sail, but not ever to enter the building.
[800.62 → 800.98] What?
[801.38 → 802.58] I didn't get in trouble, though.
[802.66 → 805.86] I was the one kid who didn't get into trouble because I never actually used it.
[806.36 → 807.06] Until now.
[807.06 → 814.20] I'm sure you're going to have one of those now grown individuals who's listening to this and being like, oh, my God, that guy.
[814.34 → 815.38] He's gloating about it.
[815.50 → 816.42] Getting us in trouble.
[817.66 → 822.30] So let's actually turn the way back down a little bit because you obviously like to break things.
[822.38 → 823.32] You've got an interesting computer architecture.
[823.94 → 825.14] You're mentioning ICL.
[825.46 → 825.60] Right.
[825.62 → 827.12] What were some of your early machines?
[827.36 → 828.52] What were you—
[828.52 → 829.44] What was my experience?
[829.68 → 829.96] Yeah.
[830.36 → 831.32] What's your first machine?
[831.32 → 834.56] So way back when—so I grew up in the UK.
[835.00 → 838.32] My first computer was a 6502.
[839.02 → 839.66] It was a BBC.
[840.02 → 841.32] I was going to say, this has got to be a BBC.
[841.56 → 841.84] Yeah.
[842.12 → 844.36] It was literally a BBC micro.
[844.64 → 844.92] Right.
[845.22 → 848.72] So, you know, this is the—the modern-day version would be the Raspberry Pi.
[848.72 → 861.62] And it's sort of inspired by, you know, in the 80s in the UK, every sort of elementary school or primary school, as they would call it, you had these computers that were branded BBC, as in the British Broadcasting Corporation.
[862.08 → 865.96] And they were, you know, standardized in the sense that every school had one.
[866.36 → 868.62] And you would learn to write basic.
[868.62 → 874.80] So that was pretty much the first thing that I ever—my every computer experience was a BBC.
[875.06 → 880.56] Now, I had a BBC Master, which was cool because it had twice the memory of the BBC B.
[880.96 → 881.62] The BBC Master?
[882.52 → 882.70] Yeah.
[883.16 → 885.16] I think it had 128K of memory.
[886.02 → 886.50] 128K?
[886.68 → 886.82] Yeah.
[886.92 → 891.64] Were you lording it over the other kids with their 64K that you had conned into breaking into the vending machine?
[892.74 → 896.54] So, and then were you messing around?
[896.56 → 897.36] What were you doing on that machine?
[897.36 → 904.98] So, yeah, that was writing basic and, you know, mostly just messing around.
[905.38 → 909.86] My father was a high school computer teacher, right?
[909.90 → 917.60] He's actually a historian, and he took a break of 26 years, 25 years while he had kids.
[917.64 → 921.18] And then in my mid-20s, he decided to go and finish his PhD.
[921.40 → 922.90] So he is now Doctor Masters.
[922.90 → 929.62] And by the way, the reason I didn't do a PhD was because the only reason I wanted to have a PhD was so I could be called Doctor Masters.
[930.04 → 930.52] And I realized—
[930.52 → 931.88] It does sound pretty great.
[931.88 → 936.84] Yeah, but that's not a compelling, you know, like, in the trade-off, right?
[936.90 → 939.86] Like, that's the reason I would have done it, and it wasn't strong enough.
[939.90 → 940.64] It's an expensive name.
[940.76 → 942.46] It's an expensive name, right?
[942.46 → 942.50] Right.
[943.12 → 948.58] So because of that, my dad had a lot of machines at home and at school that I would play on.
[948.76 → 949.44] It gets worse.
[949.60 → 959.68] So he suggested when I was 11 or 12—no, maybe 11—that I take one of the high school exams that you normally take when you're 18 to go to college in the UK.
[959.68 → 962.26] So I did an A-level in computing.
[962.98 → 965.36] Is he trying to send you a hint that he wants you out of the house?
[965.44 → 965.94] Yeah, right.
[965.94 → 968.98] It's just like a like, boy, if I could get you out of here six years early.
[969.16 → 972.12] Yeah, so that happened, and I did well.
[972.20 → 977.80] So then we enrolled me in a local university, or an American version of college, of course.
[977.80 → 984.20] And I was enrolled as an associate when I was 13, and then I was a student there when I was 14.
[984.50 → 992.22] So briefly, I was very famous in the UK because, you know, computer aces off to university at the age of 14 or something was one headline.
[992.34 → 994.56] You were a veritable computer prodigy.
[995.00 → 996.04] I've been called that.
[996.56 → 999.82] I would dispute—well, I don't know if that's true, but I've been called that in the past.
[999.86 → 1003.78] All right, so you're hanging out with a bunch of 18-year-olds, getting them into much more serious trouble, presumably.
[1003.78 → 1009.40] And taking university courses and actually getting exposed to real machines.
[1009.62 → 1010.56] Right, right.
[1010.60 → 1011.36] A lot of Sun machines.
[1011.58 → 1013.70] We were reminiscing earlier about Sun.
[1013.88 → 1017.14] So, yeah, my first internship was actually with Sun UK.
[1018.06 → 1021.60] And weirdly enough, working with their sponsorships team.
[1021.92 → 1024.34] So they used to sponsor sailing races.
[1024.68 → 1025.52] They did, yeah.
[1025.62 → 1031.20] So Pete Goss, who was a famous sailor, we actually got to go and visit the boat.
[1031.20 → 1036.64] And I don't exactly remember what their use of Spot was.
[1037.16 → 1040.96] So, yeah, Sun also, if I recall correctly, Sun sponsored a vessel.
[1041.04 → 1044.74] I want to say it was like the Black magic 2, a New Zealand vessel that sank.
[1045.36 → 1051.78] And the Sun could not afford the sponsorship on the sail, if I recall, and had a sponsorship on the keel.
[1052.28 → 1052.52] Okay.
[1052.78 → 1055.62] And it's like, why are you putting your logo on the keel?
[1055.70 → 1058.42] No one ever sees the keel unless the boat sinks, which it did.
[1058.42 → 1063.18] And the last shot was of the Sun Microsystems logo inverted going under the waves.
[1063.30 → 1064.96] That was the legend.
[1065.16 → 1066.24] Is that foreshadowing something?
[1066.90 → 1068.18] Come on, stop that.
[1068.26 → 1071.14] You know, can't we reminisce about nice things?
[1071.38 → 1074.34] So I actually own a very large collection of old Sparks.
[1074.76 → 1077.02] But there was an acquisition a number of years ago.
[1077.28 → 1080.80] And so have you tried any speculative attacks on those?
[1080.96 → 1086.44] I don't think, part of the problem, I don't think the speculative execution was very effective for Spark.
[1086.44 → 1087.50] No, not Spark.
[1087.50 → 1090.04] That's probably why Spark had other architectures.
[1090.30 → 1090.52] Yeah.
[1090.64 → 1094.12] So I went through a phase a few months ago where I started buying up.
[1094.24 → 1095.02] I recall that phase.
[1095.08 → 1095.30] Yeah.
[1096.12 → 1099.44] I own many...
[1100.06 → 1103.44] So I'm going to back this up and say I have a very, very understanding fiancé.
[1104.00 → 1104.28] Right?
[1104.40 → 1105.32] Now, we have...
[1105.32 → 1106.90] She also works in tech.
[1107.34 → 1107.86] Hi, Sarah.
[1107.86 → 1112.92] But we have a rule now with the number of old computers that come through the apartment.
[1113.12 → 1113.20] Right?
[1113.24 → 1117.76] They come in through the front door, and they do not pass go as it's declared.
[1118.00 → 1118.14] Right?
[1118.18 → 1120.18] They go straight into the office and they don't.
[1120.20 → 1122.14] Oh, I was going to assume that one came in the front door.
[1122.26 → 1123.44] One has to go out the back door.
[1123.56 → 1123.88] Yeah, exactly.
[1123.88 → 1126.58] So now you're giving her ideas and that is something that has been...
[1126.58 → 1127.50] I'm sorry.
[1127.68 → 1128.92] That has been discussed.
[1129.20 → 1129.32] Right?
[1129.80 → 1131.30] So we're still...
[1131.30 → 1133.20] I mean, you're in a garage with like floppy drives.
[1133.20 → 1136.50] I mean, Jess has got the Mac SE in there, the 486.
[1136.74 → 1137.62] I feel at home right here.
[1137.62 → 1138.08] Yeah, exactly.
[1138.32 → 1139.06] You know, we have...
[1139.06 → 1142.94] I think we certainly have north of 30 or 40 computers in the apartment.
[1143.30 → 1144.30] Whoa, that's a lot.
[1146.70 → 1149.26] Jess is like, I do not actually have a problem.
[1149.40 → 1150.06] That's a problem.
[1151.00 → 1155.62] I have got a social computer enjoyment hobby.
[1156.26 → 1157.64] And then there's the storage unit.
[1158.34 → 1161.76] And the thing is, you know, my fiancé has never seen the storage unit
[1161.76 → 1164.22] because it just wouldn't end well if she's...
[1164.22 → 1165.68] I mean, you know, it would be a...
[1165.68 → 1167.10] God, please let that one be on Storage Wars.
[1167.26 → 1170.84] Please do not pay for that storage unit.
[1171.02 → 1173.46] I love to watch the expression when they throw that one open.
[1173.68 → 1176.36] Be like, oh my God, it's a bunch of PA Risk machines.
[1176.36 → 1180.24] Actually, I have a PA Risk at home in the office.
[1180.72 → 1182.84] So there's an 8,000 in the office.
[1182.96 → 1186.36] Now, as I recall, you actually spoke to some PA Risk engineers at some point.
[1186.38 → 1187.22] I did, yes.
[1187.22 → 1191.76] I went through the sort of back catalogue of different architectures
[1191.76 → 1193.22] and reached out to people I knew.
[1193.36 → 1196.86] And I was like, what do you think about this thing that you worked on?
[1196.92 → 1198.34] Do you think it would be horribly vulnerable?
[1198.52 → 1199.72] And they were like, oh yeah.
[1200.00 → 1200.52] Oh my gosh.
[1200.52 → 1201.82] That thing speculated everything.
[1202.02 → 1203.48] I'm sure it would break, you know.
[1204.16 → 1211.52] So I've accrued a collection of fairly esoteric machines.
[1211.64 → 1212.82] So I have a PA Risk.
[1212.82 → 1216.76] I already owned an Titanium because, of course, you have to have an Titanium.
[1217.26 → 1217.70] Yeah.
[1218.20 → 1220.72] That puts you in rarefied air right there.
[1221.00 → 1222.10] I own a Spark laptop.
[1222.44 → 1223.10] That puts me in rarefied air.
[1223.10 → 1223.86] I feel, okay.
[1224.58 → 1226.12] More Spark laptops than Titaniums.
[1226.90 → 1227.84] Italia, I guess.
[1227.94 → 1229.00] Italia, yeah.
[1229.26 → 1231.54] I mean, it was a true disaster.
[1231.82 → 1236.38] You know, so recall that HP's Titanium was codename McKinley.
[1236.82 → 1237.04] Yeah.
[1237.04 → 1242.42] And I wanted us to codename what I think ended up being Panther, but would have been competitive
[1242.42 → 1243.00] with McKinley.
[1243.24 → 1248.18] I wanted us to codename it Dollars after Leon Dollars, Kinley's assassin.
[1248.54 → 1249.38] Oh, that's good.
[1249.50 → 1249.74] Right?
[1250.02 → 1250.28] Yeah.
[1250.40 → 1251.06] I thought that was good.
[1251.14 → 1252.10] That joke did not kill.
[1252.30 → 1256.12] The microelectronics folks are like, Dollars has got a bunch of like CZs in there.
[1256.26 → 1257.54] It's like, and I don't know.
[1257.78 → 1258.36] Unsympathetic guy.
[1258.52 → 1259.36] Mine's called Tamasha.
[1260.10 → 1260.38] Okay.
[1260.46 → 1262.86] Which is a folly or something that shouldn't have happened.
[1263.74 → 1264.14] Okay.
[1264.20 → 1264.80] That's what that means.
[1264.80 → 1267.72] I think Tamasha's right there with Dollars on codenames.
[1267.94 → 1268.00] Yeah.
[1268.78 → 1270.50] I mean, I obviously think it's great.
[1270.76 → 1270.86] All right.
[1270.88 → 1275.60] So you've got a couple of, does Titanium must speculate?
[1275.84 → 1276.40] No, it does.
[1276.60 → 1279.58] Well, it does speculate, but it speculates under programmer control.
[1280.08 → 1280.36] Really?
[1280.46 → 1280.80] Yeah.
[1281.00 → 1285.70] So I can say, there are a couple of instructions.
[1285.70 → 1287.62] That is so on brand for Titanium.
[1287.80 → 1287.86] Yeah.
[1288.28 → 1288.48] Yeah.
[1288.86 → 1292.68] It's like the whole point of speculation is that the programmer doesn't have to have
[1292.68 → 1295.20] this kind of, that you don't rely on a magical compiler.
[1296.00 → 1296.24] Yeah.
[1296.26 → 1298.62] There's, there are a couple of instructions where you have the dot S.
[1298.68 → 1302.36] You can say, do this, but speculatively, and then I'll see if it had trapped
[1302.36 → 1303.94] or had an exception.
[1304.30 → 1304.52] Yeah.
[1304.68 → 1306.76] That is interesting at some level.
[1307.02 → 1307.18] Yeah.
[1307.18 → 1311.44] It's similar in a sense to, if you think about what some of the so Transmeta, right?
[1311.60 → 1312.36] Oh, there you go.
[1312.42 → 1312.68] Yeah.
[1312.68 → 1313.00] Yeah.
[1313.16 → 1314.30] I have the Transmeta machine.
[1314.30 → 1315.10] Jess, you're a Transmeta?
[1315.50 → 1316.06] Yeah, yeah, yeah.
[1316.12 → 1316.40] Okay.
[1316.82 → 1316.98] Yeah.
[1317.92 → 1318.80] Steve, Transmeta.
[1319.02 → 1319.68] No, Transmeta.
[1319.98 → 1320.30] Transmeta.
[1320.38 → 1321.40] You want to explain Transmeta to Steve?
[1321.56 → 1326.58] Well, so, so Transmeta had what they, what they called CMS, which was the code morphing
[1326.58 → 1326.96] software.
[1327.12 → 1331.44] So what they would do, this was a phase in time where, you know, Intel's-
[1331.44 → 1332.00] Yeah, take us back.
[1332.14 → 1332.38] Okay.
[1332.54 → 1332.84] All right.
[1332.84 → 1334.14] The sands of time, right?
[1334.20 → 1334.48] It is.
[1334.56 → 1336.76] And we're talking like 1999?
[1337.26 → 1337.98] Late 90s.
[1338.02 → 1338.30] Yeah.
[1338.50 → 1339.14] Turn of the century.
[1339.32 → 1339.50] Yeah.
[1339.60 → 1340.28] Turn of the century.
[1340.30 → 1340.92] Turn of the century.
[1341.12 → 1341.54] I think we have to call it that.
[1341.60 → 1341.70] Yeah.
[1341.70 → 1341.88] Right.
[1342.68 → 1344.10] So it's the go-go late 90s.
[1344.18 → 1344.40] Yeah.
[1344.50 → 1350.44] And, and so, you know, the mobile performance from most of the x86 vendors was really not
[1350.44 → 1351.10] great.
[1351.24 → 1351.94] I'll put it that way.
[1352.28 → 1358.34] And so what the startup Transmeta decided they could do is they could make a very, very
[1358.34 → 1361.76] energy, if this is Dave Ditzes and a bunch of others that decided they could make-
[1361.76 → 1361.84] X-Sun.
[1362.38 → 1362.68] Yes.
[1363.16 → 1364.04] X-Sun always comes.
[1364.16 → 1369.02] I mean, it's either Sun or it's Data General or DEX.
[1369.16 → 1369.62] Yeah, yeah, yeah.
[1369.62 → 1373.12] You know, and, and, you know, I used to work at Red Hat for the last 12 and a half years
[1373.12 → 1374.02] or 13 years.
[1374.64 → 1377.28] And, you know, I used to joke, and I mean this in the nicest way.
[1377.34 → 1377.84] I really do.
[1377.88 → 1379.14] Because I love everyone at Red Hat.
[1379.20 → 1380.00] I'm bracing for impact.
[1380.12 → 1380.30] Okay.
[1380.46 → 1384.26] But it used to be like 100% re-employment for people that worked at that, right?
[1384.26 → 1387.90] Because, you know, there were some perfect deck folks.
[1387.90 → 1391.84] And, you know, if you ever wonder why, you know, Red Hat's engineering headquarters is
[1391.84 → 1394.76] in West ford, Mass., just look at the map and-
[1394.76 → 1395.10] There you go.
[1395.14 → 1397.10] You will see why it's there.
[1397.94 → 1401.76] So Dave Ditzes and crew, Transmeta, they hire Linus Torvalds, famously.
[1402.00 → 1402.14] Yes.
[1402.14 → 1403.04] Is that Transmeta?
[1403.48 → 1406.20] They had footprints in the sand on the website.
[1406.34 → 1406.44] That's right.
[1406.44 → 1410.08] So you go to Transmeta.com, be like, oh, something's coming, but you don't know what it is.
[1410.08 → 1412.42] And you read the HTML comments to see if there's anything in there.
[1412.70 → 1414.40] Footprints in the Sand because it was the Crusoe-
[1414.92 → 1415.34] That's right.
[1415.34 → 1416.18] Microprocessor.
[1416.44 → 1416.74] It's like-
[1416.74 → 1417.00] Robinson Crusoe.
[1417.06 → 1417.20] Yeah.
[1417.44 → 1423.02] Are we, like, Robinson Crusoe, like, that seems like a very weird kind of analog to-
[1423.02 → 1423.20] Anyway.
[1423.36 → 1427.54] It turns out, though, that lots of processors have really odd names in this industry.
[1427.64 → 1427.66] It's true.
[1427.66 → 1428.84] Pollard, it would have been a good company.
[1428.98 → 1429.18] Yeah.
[1429.98 → 1430.18] Anyway.
[1430.46 → 1430.98] It would have worked.
[1431.06 → 1432.34] Did they make it through the Great Recession?
[1432.54 → 1433.76] Oh, no.
[1435.12 → 1437.80] No, they got kind of sued out of existence, I guess.
[1438.62 → 1442.40] Lots of things went wrong for Transmeta later, but I guess, I guess actually before that-
[1442.40 → 1443.44] There were many lessons in Transmeta.
[1443.54 → 1444.68] There were many lessons in Transmeta.
[1444.68 → 1452.30] But their idea was to take x86, which is a very complex instruction set, and stop me
[1452.30 → 1455.52] if you've heard this before, translate it into a RISC machine underneath.
[1455.52 → 1455.70] Right.
[1455.90 → 1456.26] Exactly.
[1456.46 → 1456.60] Right.
[1456.60 → 1461.34] But with a twist, which was that there was a lot of fancy software running underneath.
[1461.48 → 1463.44] So it was a lot more like a JVM.
[1463.44 → 1469.56] When you're running Java on a modern machine, it has a just-in-time compiler, which basically
[1469.56 → 1475.10] looks at the code, looks at hotspots, and says, oh, well, this is code that I'm interpreting
[1475.10 → 1478.76] all the time, and I should probably turn this into native machine code.
[1478.76 → 1480.64] And then it has all kinds of optimizations it runs.
[1481.14 → 1487.48] And so what Transmeta were doing is they would treat x86 in this kind of way, and your machine
[1487.48 → 1488.92] would run the code.
[1488.98 → 1492.50] The first time it encountered some code sequence, it would just interpret it.
[1492.60 → 1496.66] Like it would say, okay, well, this means this, and literally programmatically interpret
[1496.66 → 1498.16] each instruction, which is very slow.
[1498.70 → 1503.50] But then it would stash translations of these into its native underlying machine code.
[1503.50 → 1509.60] But then it would start to do really exciting things, like aggressively speculate ahead in
[1509.60 → 1510.80] software, right?
[1510.90 → 1515.98] And say, I've seen this sequence, and I know that this sequence is probably Windows doing
[1515.98 → 1521.40] this thing that I know Windows does, like weird page table update or whatever sequence
[1521.40 → 1522.62] that you see in a game.
[1523.28 → 1527.50] And it would say, I think the next thing it's going to do is this, because I know that whenever
[1527.50 → 1529.18] I see that, this happens, right?
[1529.18 → 1534.10] And so, you know, modern processors have a lot of hardware predictors and prefetches that
[1534.10 → 1535.08] do similar stuff.
[1535.16 → 1539.20] But this was like on steroids, because they had infinite ability, well, not infinite ability,
[1539.30 → 1544.04] but they could do everything you can do in software, which is always a lot more sophisticated
[1544.04 → 1548.14] than, you know, just forcing someone to build all of that into hardware.
[1548.30 → 1550.00] But very hard to do that in Make Clock, though.
[1550.44 → 1550.70] Yeah.
[1551.28 → 1554.46] And they, ultimately, they could not compete.
[1554.56 → 1556.68] Intel did come out with a mobile version, right?
[1556.68 → 1556.76] Yeah.
[1556.84 → 1557.92] The mobile Cameron, as I recall.
[1557.92 → 1558.08] Yeah.
[1558.62 → 1560.18] And they killed them in performance.
[1560.42 → 1563.20] And then there was a little bit of a patent issue that they had.
[1563.34 → 1563.94] A little bit.
[1563.96 → 1564.50] A little bit of one.
[1564.64 → 1566.56] And were they LAW under the hood?
[1566.66 → 1567.22] They were-
[1567.22 → 1567.94] Under the hood.
[1568.02 → 1568.58] They were interesting.
[1568.90 → 1569.08] Yeah.
[1569.20 → 1571.94] And there were a couple of efforts over the years to reverse engineer it as well.
[1572.04 → 1575.06] So that's kind of, that's another thing that I'd love to have time to really play.
[1575.26 → 1576.66] Can you, do you have a Transpantibox?
[1576.84 → 1577.22] I do.
[1577.90 → 1578.88] How many of those are there?
[1579.06 → 1579.90] That can't be that many.
[1580.08 → 1582.48] There's a bunch of one generation.
[1582.84 → 1583.10] Right.
[1583.10 → 1587.88] Still on eBay, but not a lot of, because they were two generations of Transpantibox.
[1587.88 → 1588.08] Okay.
[1588.28 → 1588.50] Yeah.
[1588.70 → 1590.32] And I've got both of those.
[1590.94 → 1594.94] So they'll be interesting from a speculative execution analysis viewpoint, because they
[1594.94 → 1596.44] basically speculate everything, right?
[1596.60 → 1596.74] Yeah.
[1597.42 → 1598.08] And feeding us back.
[1598.14 → 1600.52] So we've got PA Risk at home.
[1600.68 → 1602.96] We've got a bunch of Deck Alphas as well.
[1603.06 → 1603.30] There you go.
[1603.52 → 1605.26] Because, you know, they're always good for fun.
[1605.38 → 1605.54] Yeah.
[1605.54 → 1610.36] But Alpha was famously very aggressive in its performance optimizations.
[1610.68 → 1611.00] Yes.
[1611.44 → 1612.50] It was very aggressive.
[1612.90 → 1613.02] Yeah.
[1613.20 → 1613.40] Yeah.
[1613.54 → 1617.66] So, and, and, and, oh, and the other side of that, by the way, the other side of some
[1617.66 → 1622.06] of this is you get to work on mitigating these horrifying security disasters.
[1622.06 → 1624.16] You get to go and look at some of these old machines.
[1624.22 → 1628.12] And I'm looking at the old machines just because I can write a paper there and no one's going
[1628.12 → 1628.84] to yell at me, right?
[1628.88 → 1630.90] No one cares really about an Alpha at this point.
[1631.00 → 1631.14] Right.
[1631.44 → 1634.22] But if you write a paper on Transplant, I mean, do you mean a blog entry?
[1634.22 → 1635.54] Is anyone going to publish a paper on Transplant?
[1635.60 → 1636.14] I mean, that'd be great.
[1636.40 → 1638.36] Well, there was some interest in doing that.
[1638.60 → 1641.18] I talked with a bunch of security researchers about doing this.
[1641.28 → 1645.90] You know, we, we, we said, look, again, if we take old machines that no one cares about
[1645.90 → 1647.64] anymore, we could rip them apart.
[1647.78 → 1649.02] We could say they screwed this up.
[1649.06 → 1649.62] They screwed that up.
[1649.70 → 1651.30] No one's going to sue us and no one's going to care.
[1651.56 → 1651.76] Yeah.
[1651.98 → 1653.10] And actually that'd be great.
[1653.40 → 1653.56] Yeah.
[1653.98 → 1655.96] So, so that's the sort of side activity.
[1655.96 → 1657.96] It's kind of like a gangster antiques roadshow.
[1658.04 → 1658.62] What do you call this?
[1658.70 → 1660.42] I mean, you got to have a good.
[1660.76 → 1661.60] Speculation disasters.
[1661.82 → 1662.54] Oh, there you go.
[1662.54 → 1663.68] It's the whole series there.
[1663.88 → 1664.08] Yeah.
[1664.22 → 1669.02] Um, but the other side of this is that, you know, when you start going down this, this
[1669.02 → 1673.70] rathole of really trying to understand, you know, how modern machines actually optimize
[1673.70 → 1677.88] and speculate and guess ahead and, and, and all of these things, what you also get to do
[1677.88 → 1679.82] is you get to go and meet some of the people that built these.
[1679.88 → 1680.06] Yeah.
[1680.06 → 1680.26] Right.
[1680.48 → 1680.68] Right.
[1680.74 → 1688.52] So I got to give a presentation at Stanford as a guest lecturer at one point, which was
[1688.52 → 1689.16] kind of fun.
[1689.24 → 1689.68] It's great.
[1689.78 → 1689.94] Yeah.
[1689.94 → 1695.84] Um, and I'm, I'm chatting away and there's this guy asking a few questions, and I'm like,
[1695.90 → 1697.64] Oh, he seems like a very nice guy.
[1698.14 → 1699.46] I wonder who he is.
[1699.86 → 1701.18] And I, I didn't know.
[1701.88 → 1705.38] And then afterward we, we go and have dinner, and he's sitting there chatting with me and
[1705.38 → 1706.26] I'm like, Oh yeah.
[1706.26 → 1708.16] So who are you anyway?
[1708.24 → 1709.58] And he's like, John Hennessey.
[1709.58 → 1710.72] Uh, no, it was Dick Sites.
[1710.96 → 1711.28] Okay.
[1711.34 → 1711.80] There you go.
[1711.80 → 1716.72] Uh, you know, and, and, and he was involved in, you know, alpha and, uh, yeah.
[1717.00 → 1719.42] And, and Piranha, did you do Piranha as well?
[1719.50 → 1722.88] I may have, but he, he wrote a paper, you know, he's, he's written a number of papers.
[1723.00 → 1726.22] One of them famously is, you know, um, it's the memory stupid.
[1726.38 → 1726.60] Yeah.
[1726.66 → 1726.88] Right.
[1726.90 → 1729.34] And then another paper called, it's still the memory stupid.
[1729.76 → 1730.12] Right.
[1730.12 → 1734.58] About how performance is tied to memory latencies and optimizations.
[1734.58 → 1739.00] But getting to meet some of these people was the other, the other half of, of, of playing
[1739.00 → 1740.06] around with a lot of the old machines.
[1740.28 → 1740.36] Yeah.
[1740.44 → 1741.58] That, that is definitely exciting.
[1742.38 → 1746.38] It actually, you know, I've got a, I was actually at Stanford when John Crawford, the
[1746.38 → 1749.70] Titanium architect was lecturing about Titanium.
[1750.00 → 1750.96] It's back in the day.
[1751.16 → 1751.34] Yeah.
[1751.36 → 1753.86] And I was like, it was an open lecture.
[1753.98 → 1758.10] So I'm sitting there watching John Crawford and this guy at the back of the room just starts
[1758.10 → 1759.06] ripping him apart.
[1759.36 → 1762.98] And in particular, he's highlighting the fact that Titanium was doing very well.
[1762.98 → 1763.80] And this is Merced.
[1763.80 → 1765.00] This is the first embodiment of it.
[1765.20 → 1765.26] Right.
[1765.34 → 1771.40] Doing very well on every, all the spec benchmarks, except for GCC, which is the only one that
[1771.40 → 1774.30] actually approximates a real world work reload from just hitting the memory wall.
[1774.54 → 1777.22] And this guy is just ripping apart over it.
[1777.68 → 1782.38] And Crawford is kind of like stumbling around and this, and the guy at the back is like,
[1782.42 → 1785.72] this seems wilfully ignorant of everything we know about systems performance.
[1785.94 → 1786.68] And who was it?
[1786.86 → 1789.78] And I'll look back and, and it's like, oh my God, it's John Hennessey.
[1789.78 → 1795.26] It's like, talk about like a computer architecture gangland slaying circa late nineties.
[1795.38 → 1796.20] It was, it was amazing.
[1796.30 → 1796.60] It's great.
[1796.68 → 1797.56] It's, it's fun to, too.
[1798.10 → 1799.02] I have a Hennessey story.
[1799.16 → 1803.88] So I, I, uh, again, the, you know, getting to be involved in Spectrum Meltdown was kind
[1803.88 → 1805.82] of, actually it was super exciting.
[1805.92 → 1809.70] Now I'm sure a lot of people in the industry found it horribly painful and, and, and had
[1809.70 → 1811.82] lots of negatives associated with Spectrum Meltdown.
[1812.22 → 1813.60] I found it painful and exciting.
[1813.78 → 1813.94] Yeah.
[1813.94 → 1814.22] Okay.
[1814.28 → 1815.24] Painful and exciting, right?
[1815.56 → 1819.84] I mean, I'm kind of looking at, Robert had to implement kernel page table isolation
[1819.84 → 1822.22] for us under the while we were vulnerable.
[1822.36 → 1822.80] That's fun.
[1823.36 → 1824.32] It's like no pressure.
[1824.50 → 1824.88] No pressure.
[1825.08 → 1827.46] That seat you're sitting on is getting progressively warmer, but don't worry.
[1827.46 → 1827.74] Yeah, exactly.
[1828.28 → 1829.68] But it was, it was exciting.
[1829.90 → 1831.16] Honestly, it was terrifying.
[1831.76 → 1832.08] What's that?
[1832.40 → 1833.84] And for Steve, it was a little terrifying.
[1834.02 → 1834.24] Yes.
[1834.88 → 1836.96] Yeah, it was, but yeah, it was exciting.
[1837.20 → 1838.96] So, you know, so that's happening.
[1838.96 → 1844.24] Uh, you get to go and learn a lot about things that we sort of vaguely knew things about,
[1844.34 → 1847.06] but really diving in and getting paid to go and figure things out.
[1847.38 → 1850.70] And then the ability to go and talk about it.
[1851.22 → 1856.48] And at some point, I forget exactly how this came together, but I get an email asking, would
[1856.48 → 1861.36] you like to give a keynote at Hot Chips with John Hennessey?
[1861.60 → 1862.20] Oh, wow.
[1862.30 → 1864.58] And I'm like, no, no, I wouldn't like to give.
[1864.68 → 1865.36] No, actually, yes.
[1865.44 → 1865.66] Yes.
[1865.66 → 1866.82] It's the only answer to that.
[1866.84 → 1867.08] Right.
[1867.18 → 1868.38] You know, like, what am I going to say?
[1868.38 → 1868.68] Of course.
[1868.68 → 1869.08] Oh my gosh.
[1869.16 → 1869.32] Yeah.
[1869.34 → 1869.54] Right.
[1870.00 → 1873.38] So a couple of years ago, I mean, it was his keynote, and we were just hangers on.
[1873.44 → 1879.60] I mean, you know, myself and some, some really great co-presenters, but I, I fear that
[1879.60 → 1880.72] could be the high point of my career.
[1881.58 → 1884.50] I seriously fear that, you know, like that one time, right.
[1884.70 → 1885.72] That's pretty great though.
[1885.74 → 1886.98] I mean, that's a good high point.
[1887.14 → 1887.80] High point, right?
[1888.02 → 1889.18] I don't really know how you top that.
[1889.54 → 1889.80] Yeah.
[1889.86 → 1890.96] I think that's a good one.
[1891.12 → 1894.84] And then I'm like, I kind of want to take a selfie with him, but I just.
[1895.08 → 1896.16] Oh, you got to take a selfie.
[1896.16 → 1897.10] I didn't.
[1897.10 → 1897.46] I didn't.
[1897.46 → 1898.66] I think you got to go for the selfie.
[1898.78 → 1902.84] No, I went, I was like, I was like, I'm going to, even though I love selfies, like more
[1902.84 → 1903.92] than anyone, I'm just like.
[1903.92 → 1904.10] You know what?
[1904.22 → 1904.44] Okay.
[1904.44 → 1905.98] I think I say always go for the selfie.
[1906.10 → 1909.94] I think that if you'd gone for the selfie, he would remember you as the guy who took the
[1909.94 → 1910.18] selfie.
[1910.56 → 1913.20] There's no way he's going to remember you as the guy who didn't take the selfie, who
[1913.20 → 1914.60] had the self-control to not take the selfie.
[1914.80 → 1916.26] A little, a little too close to Siri.
[1916.60 → 1916.90] Yes.
[1916.92 → 1918.46] We just said, let me say it again.
[1918.60 → 1919.12] Hey Siri.
[1920.84 → 1921.76] She woke up quick.
[1921.76 → 1922.98] My phone was lighting up.
[1923.08 → 1923.26] All right.
[1923.58 → 1928.00] We are going to take a quick break, and then we are going to be back with more John Masters
[1928.00 → 1928.90] on the metal.
[1930.14 → 1933.38] On the metal is brought to you by the Oxide Computer Company.
[1933.60 → 1935.12] Wait, did you say computer company, Jess?
[1935.22 → 1935.90] Yes, indeed.
[1936.08 → 1936.72] But wait a minute.
[1936.80 → 1937.84] Everyone runs on the public cloud.
[1937.96 → 1940.18] Jack Bezos owns and operates every computer on the planet.
[1940.32 → 1942.20] Why would anyone start a computer company?
[1942.42 → 1943.46] That is so not true.
[1943.46 → 1948.98] I have spent a bunch of time talking to folks who are still running on premises and actually
[1948.98 → 1954.22] like the consensus among all of them is just a feeling of neglect because everyone thinks
[1954.22 → 1956.52] that like everything is moving to the public cloud, but it's not.
[1956.80 → 1959.64] If you're still running on premises, it's because you haven't heard of the cloud, right?
[1959.84 → 1965.68] No, there are perfect reasons for running on premises still for security, for latency,
[1965.94 → 1967.76] strategic reasons for your business.
[1968.10 → 1968.38] Wow.
[1968.46 → 1971.90] The people running on premises must feel like everyone has ignored them.
[1972.18 → 1972.60] They do.
[1972.60 → 1973.00] Indeed.
[1973.00 → 1978.84] So if this is you, please head on over to our website, Oxide. Computer, sign up for our
[1978.84 → 1982.06] mailing list, and we would love to get in touch and hear your stories.
[1982.18 → 1986.62] We acknowledge that you exist, and you've got some really hard technical problems that we're
[1986.62 → 1986.90] solving.
[1987.10 → 1988.62] Oxide. Computer, come join us.
[1990.88 → 1992.12] All right, we're back.
[1992.26 → 1999.34] So John, you were, when we last left you, you were ripping apart these ancient architectures
[1999.34 → 2002.22] trying to actually, have you actually found vulnerabilities in these things?
[2002.22 → 2004.16] Have you, it takes a long time is the problem.
[2004.26 → 2005.10] It does take a long time.
[2005.12 → 2005.64] It's not easy.
[2005.94 → 2010.00] Now I used to get, I mean, I left Red Hat fairly recently, but one of the things that
[2010.00 → 2014.56] I was doing was leading the Spectre Meltdown mitigation efforts.
[2014.70 → 2018.76] And actually the project was originally known as the Omega Project.
[2019.42 → 2024.58] Now, if you're a Star Trek fan, you would hopefully have the, ah, yes, the Omega Directive, right?
[2024.58 → 2030.80] So in, in, in Star Trek lore, there is a molecule that destroys subspace, prevents faster than
[2030.80 → 2031.34] light travel.
[2031.70 → 2036.10] And so Star fleet has a hidden directive called the Omega Directive, which is if you ever encounter
[2036.10 → 2037.72] Omega, you must stop everything else.
[2037.88 → 2040.76] It must be destroyed at all costs and all knowledge of it must be suppressed.
[2041.48 → 2046.72] And so I thought that is a great name for the secret Spectre Meltdown mitigation project.
[2046.92 → 2047.62] That's very good.
[2047.80 → 2048.00] Yes.
[2048.00 → 2048.50] Better than Olga.
[2048.50 → 2048.84] All right.
[2048.88 → 2052.12] So, so you, it's the Omega Project to actually go and.
[2052.42 → 2056.38] And I had my boss issue the Omega Directive, which is the Star Trek thing that they do.
[2056.48 → 2058.44] So she's like, why am I sending this email?
[2058.92 → 2059.98] I'm like, it's very important.
[2060.26 → 2061.06] It will be hilarious.
[2061.06 → 2062.86] It's very important because it will make me laugh.
[2063.00 → 2063.58] And that's funny.
[2064.28 → 2065.04] So, yeah.
[2065.10 → 2069.52] So we, we, you know, we, we had these projects going on for several years and at the beginning
[2069.52 → 2073.24] it was kind of very aggressive, like get ahead of this nasty disaster.
[2073.78 → 2074.04] Yeah.
[2074.04 → 2079.92] Uh, and then later on we got kind of better at quite getting ahead of it, but moving.
[2080.42 → 2082.56] And when you say it, the problem is it didn't stop.
[2082.64 → 2083.04] It didn't stop.
[2083.12 → 2084.44] And we, we all knew this.
[2084.80 → 2089.80] We all knew that when, when Spectre Meltdown broke, it's like, this is not the last one
[2089.80 → 2090.10] of these.
[2090.36 → 2096.10] In fact, this, what this has now done is because, you know, and as sitting as someone, it's
[2096.10 → 2101.92] not a security person knew that, that there had been hypotheses about speculation based
[2101.92 → 2106.92] attacks, but until Spectre Meltdown, none of those attacks actually borne fruit.
[2107.04 → 2110.10] Now, all of a sudden it's a beacon to every security researcher.
[2110.36 → 2110.54] Yeah.
[2110.92 → 2112.96] That there are tons of vulnerabilities here.
[2113.32 → 2118.18] I think there was a, uh, implicit assumption that hardware was somehow safe.
[2118.26 → 2118.72] All right.
[2118.76 → 2118.98] Right.
[2119.04 → 2123.14] Until Spectre Meltdown proved that actually, if you start digging there, you will find a
[2123.14 → 2125.60] lot of interesting things to find.
[2125.78 → 2126.04] Right.
[2126.42 → 2127.34] I want to come back to that.
[2127.34 → 2131.84] The, the point about, uh, I was sort of getting to with, uh, you know, running this mitigation
[2131.84 → 2136.64] effort and so on for several years was that we ended up having to create reproducers.
[2136.96 → 2137.32] Yeah.
[2137.38 → 2137.54] Right.
[2137.62 → 2141.52] So I haven't had a chance to do some of that on the older machines that I've been acquiring
[2141.52 → 2145.88] because I haven't been under that, like immense time pressure of, oh God, we have to figure
[2145.88 → 2146.24] it out.
[2146.32 → 2148.64] Your reproducer for Meltdown was great, by the way.
[2148.72 → 2149.02] Thank you.
[2149.12 → 2152.84] It was really, it, it was, I mean, just so terrifying.
[2152.84 → 2154.94] I mean, cause obviously, you know, academically.
[2155.18 → 2155.44] Right.
[2156.00 → 2160.86] And, you know, not doubting the severity of it at all, but to actually run the reproducer,
[2160.92 → 2162.44] you're like, holy God.
[2162.68 → 2162.86] Yeah.
[2162.94 → 2166.66] So, I mean, with a lot of these, it was like, we were given a vague description of what the
[2166.66 → 2169.60] actual problem, I mean, Meltdown was a bit different because we, we sort of understood
[2169.60 → 2172.80] what that, but with a lot of the other issues, we were given a vague description.
[2172.80 → 2177.54] Like this, something could happen and badness would result, and you would see this kind of thing
[2177.54 → 2181.58] happen, but they wouldn't be like, and here's how it is done.
[2181.58 → 2185.46] Because if they, a lot of companies, if they give you that level of detail, then that's
[2185.46 → 2187.08] sort of bad thing in their policy.
[2187.18 → 2187.34] Right.
[2187.42 → 2192.60] So I spent a lot of time creating reproducers for things that processor companies probably
[2192.60 → 2195.14] had internal reproducers of that they could not give to me.
[2195.40 → 2195.46] Right.
[2195.62 → 2198.06] You know, so for example, L1 terminal files.
[2198.24 → 2198.28] Yeah.
[2198.32 → 2198.94] I was going to say L1TF.
[2199.20 → 2201.54] I mean, I assume we're going to do the whole tour here.
[2201.78 → 2202.28] Oh, we can.
[2202.38 → 2206.52] I mean, you know, L1TF was funny because I was sitting on a plane halfway across the Atlantic
[2206.52 → 2210.74] on my laptop with a privacy filter on, hacking on a reproducer for this.
[2210.74 → 2215.78] And halfway during the flight, I think I yelled out loud, oh, expletive, expletive, expletive.
[2216.30 → 2217.20] And then I'm like, oh, I'm on a plane.
[2217.32 → 2217.78] I better not do that.
[2217.78 → 2219.46] Did you ring your flight attendant call button?
[2219.78 → 2220.52] It's like, excuse me.
[2220.58 → 2220.94] Do you understand?
[2221.04 → 2222.02] I just got this thing working.
[2222.22 → 2222.34] Right.
[2222.46 → 2222.66] Wow.
[2222.86 → 2223.00] Yeah.
[2223.00 → 2224.06] That must be, yeah.
[2224.12 → 2224.94] It must be very.
[2225.20 → 2225.42] Yeah.
[2225.80 → 2226.00] Yeah.
[2226.86 → 2230.74] What you're doing is so, I mean, if you'll forgive the pun, it's so fundamentally speculative
[2230.74 → 2232.04] in terms of like, I don't know.
[2232.18 → 2232.40] Right.
[2232.40 → 2235.14] I could dig here for a while and never actually be able to exploit it.
[2235.14 → 2235.30] Yeah.
[2235.34 → 2238.76] Like, you know the outcome, but you don't, you know, you don't know how close you got.
[2238.84 → 2241.02] You only know if you actually made it work, or you didn't make it work.
[2241.10 → 2241.22] Right.
[2241.56 → 2245.42] So in no, at none of these times, am I finding these, I want to be very clear.
[2245.52 → 2250.60] I'm not the discoverer of these issues, but I'm given a synopsis of the problem.
[2250.60 → 2253.26] And then, you know, we have to go and figure out how to reproduce it.
[2253.34 → 2257.08] So L1TF was funny in that, not funny, but kind of interesting.
[2257.08 → 2257.76] Not funny, ha ha.
[2257.88 → 2259.06] Funny, funny boo Hoo.
[2259.16 → 2263.14] I'm sitting on a plane, and I'm like, oh, I just managed to make a VM read things it
[2263.14 → 2264.00] shouldn't from the host.
[2264.20 → 2265.58] Oh, that's a bit scary.
[2266.38 → 2275.42] And then the it was recently an issue with VMs being able to cause badness in terms of
[2275.42 → 2278.46] host crashes and things that came out.
[2278.46 → 2282.42] And I can, I guess I can mention now that earlier this year, I got that working on a
[2282.42 → 2282.78] laptop.
[2283.04 → 2286.80] I'm sitting in my living room, and I'm like, oh, what would happen if, and finally,
[2286.80 → 2287.66] figured it out.
[2287.96 → 2289.56] And I'm like, it's going to run this.
[2289.66 → 2290.82] And then the laptop goes boom.
[2290.96 → 2292.68] And I'm like, oh, that's not good.
[2293.34 → 2295.28] That's a VM that just killed my laptop.
[2295.48 → 2296.44] That's not good.
[2296.64 → 2298.20] That must be, that's so gratifying.
[2298.30 → 2298.94] It really is.
[2298.94 → 2304.32] You know, that's what I truly do miss about, I really have not done kernel development on
[2304.32 → 2306.78] my own desktop in 15 years.
[2306.90 → 2308.02] And I definitely miss that.
[2308.08 → 2311.74] That's such a great visceral feeling when you, when you Bork your own laptop.
[2312.22 → 2312.62] Yeah.
[2313.08 → 2313.64] Triple fault.
[2313.90 → 2314.10] Yeah.
[2314.10 → 2315.48] Where do the names come from?
[2315.48 → 2318.80] Who sets the name for Meltdown, Spectre, Dracula?
[2319.40 → 2323.82] The researchers decide what is the most sort of PR newsworthy.
[2324.68 → 2328.94] And then, so we get the kind of, you know, this is, again, this is my, in my old life,
[2329.34 → 2330.04] recently changed.
[2330.10 → 2334.68] But in my old life, what would happen is we would get the academic name, right?
[2334.72 → 2337.02] So we would get, you know, MDS, right?
[2337.02 → 2337.16] Right.
[2337.16 → 2338.56] Microarchitectural data assembling.
[2339.42 → 2340.62] Also zombie load.
[2341.04 → 2341.30] Right.
[2341.30 → 2342.60] Which one sounds better?
[2343.26 → 2343.58] Right.
[2343.98 → 2345.68] Like we have this thing called MDS.
[2345.76 → 2348.36] Sounds like, you know, you went to the doctor, and you're all okay now.
[2348.66 → 2348.84] Right.
[2348.92 → 2349.06] Right.
[2349.26 → 2351.60] Zombie load sounds like, oh God, they're coming.
[2351.76 → 2351.94] Right.
[2351.98 → 2353.56] And then there was zombie load too recently.
[2354.20 → 2356.76] And what is the vulnerability that kicked that off?
[2356.86 → 2359.06] I was at Heart bleed or was it earlier than, I'm trying to think.
[2359.06 → 2360.24] Yeah, I think Heart bleed was.
[2360.24 → 2365.16] In terms of like the branding exercise for vulnerabilities, when did that start?
[2365.32 → 2369.56] I think it was probably pre-Heart bleed, but that's the most, like, that's the one that
[2369.56 → 2369.96] comes to mind.
[2369.96 → 2371.32] That's the one that comes to mind for me too.
[2371.46 → 2372.60] I'm not sure that there was one.
[2372.68 → 2375.02] Jess, can you think of one before Heart bleed that like.
[2375.68 → 2378.60] Heart bleed was significant because it needed to have the marketing.
[2378.82 → 2381.46] I think some of these don't necessarily need the marketing.
[2381.68 → 2384.64] Heart bleed was unbelievably bad.
[2384.64 → 2388.32] If there's any, like, if there's going to be a vulnerability that is going to like kick
[2388.32 → 2389.42] it off, it might as well be Heart bleed.
[2389.42 → 2393.98] I can tell you a funny story though about the names because what we figured out.
[2394.12 → 2399.00] So again, we would be told by, you know, on the processor companies, there is this thing
[2399.00 → 2400.10] that happens that's bad.
[2400.16 → 2404.28] And here's how we'd like to fix it using, you know, page table isolation or some particular
[2404.28 → 2404.68] fix.
[2405.36 → 2410.22] And they wouldn't say which, they say a researcher or researchers have found, but they wouldn't
[2410.22 → 2411.18] say which researcher.
[2411.18 → 2413.96] So I got perfect at figuring out of the academics.
[2413.98 → 2414.48] Oh, interesting.
[2414.64 → 2415.30] Which one hit that in?
[2415.32 → 2416.26] Which one was it?
[2416.40 → 2421.02] So we figured out before Spectre and Meltdown were public, we're like, ah, it's the folks
[2421.02 → 2422.28] at TU Graz, right?
[2422.42 → 2423.80] So we worked out it was them.
[2424.20 → 2430.54] And then I went onto a reverse DNS registrar and looked at all the domains that they'd registered
[2430.54 → 2431.06] recently.
[2431.42 → 2438.10] And so we found, oh, this is your meltdown. Help test domain where you did the testing for your
[2438.10 → 2439.78] SSL certificate on this date.
[2439.78 → 2440.04] Right.
[2440.24 → 2442.14] And then, oh, Spectre and Meltdown.
[2442.14 → 2444.74] Poor OPSEC around vulnerability marketing.
[2444.92 → 2446.22] They didn't do it again.
[2446.60 → 2447.42] Oh, okay.
[2447.52 → 2449.66] I told them, and they're like, oh, never again.
[2449.92 → 2450.40] Not doing that one again.
[2450.48 → 2450.56] Yeah.
[2450.56 → 2453.06] Now they use like anonymizes to even register the domains.
[2453.12 → 2453.34] Right.
[2453.34 → 2459.40] And, you know, but another one would be the Riddle paper, right?
[2459.46 → 2461.68] Which was a rogue in-flight data load.
[2462.48 → 2465.88] That was Leuven, I think, did that one.
[2465.88 → 2469.70] And they were good in almost every single way.
[2470.24 → 2475.56] But when we thought it might be them who were publishing, their bibliography on their
[2475.56 → 2479.08] departmental website started updating itself just a little bit too soon.
[2480.58 → 2481.76] What was this vulnerability?
[2483.34 → 2486.02] Riddle was, what was the branding for that one?
[2486.12 → 2488.28] That was not MDS.
[2488.52 → 2489.34] That was one of the other.
[2490.28 → 2491.00] Did it get branding?
[2491.20 → 2492.70] Did Eager FPU get branding?
[2492.70 → 2493.80] No, that was MDS.
[2494.20 → 2496.20] So MDS was a whole family of them.
[2496.48 → 2496.66] Right.
[2496.96 → 2499.64] And Riddle was one aspect of that particular family.
[2499.74 → 2503.72] But you get like, I mean, we're up to, I think, we're more than 25.
[2504.04 → 2504.22] Yeah.
[2504.42 → 2506.04] There were too many to keep track of.
[2506.04 → 2512.08] I remember at one point I had missed the morning call with Intel and I came in and Robert was
[2512.08 → 2513.86] like, you know, it's like, oh God, another one.
[2513.98 → 2514.40] I'm like, okay.
[2515.22 → 2518.26] And he's like, well, what's the only unit we haven't talked about yet?
[2518.68 → 2520.84] I'm like, I, the FPU?
[2521.00 → 2522.18] He's like, yeah, it's the FPU.
[2522.18 → 2523.84] It's like, oh, now it's the FPU.
[2524.12 → 2524.28] Yeah.
[2524.28 → 2524.54] Okay.
[2525.58 → 2526.64] Oh, yeah.
[2526.74 → 2530.60] It was just, and it, because I think it was just revealing that like unit after
[2530.60 → 2533.12] unit after unit, it's like we hadn't considered it anywhere.
[2533.38 → 2533.56] Right.
[2533.74 → 2535.66] None of these units had been tagged.
[2535.86 → 2538.80] Well, you know, just unrolling the stack slightly there.
[2538.84 → 2543.58] I mean, without giving away the exact date we're recording this on, but we're recording
[2543.58 → 2548.98] this on the anniversary of the original FDI bug.
[2548.98 → 2549.58] FDI bug.
[2549.70 → 2553.66] And you know, it's funny you said, and I saw your tweet yesterday about that.
[2553.82 → 2553.94] Yeah.
[2553.94 → 2555.16] It was 25 years ago, right?
[2555.32 → 2555.44] Yeah.
[2555.44 → 2557.88] 25 years ago on this date.
[2558.08 → 2558.30] Yeah.
[2558.36 → 2562.38] Was when IBM finally did a stop ship on Pentium.
[2562.64 → 2562.94] Right.
[2563.08 → 2563.88] Because of FDI.
[2563.94 → 2564.70] Because of FDI.
[2564.70 → 2566.68] And FDI was very bad.
[2567.22 → 2568.44] It was the wrong results.
[2568.66 → 2569.22] It was very bad.
[2569.36 → 2575.36] It had a, I forget how many decimal places, but it was effectively, if you did a very specific
[2575.36 → 2581.54] division, then due to the algorithm that they used, and they had these lookup tables and they
[2581.54 → 2584.58] missed five entries in one table in hardware.
[2584.58 → 2589.82] If you did a particular calculation that this professor, I think in New Hampshire had found
[2589.82 → 2593.80] originally and Intel had discovered it internally, you know, and they would, they already fixed
[2593.80 → 2597.04] it actually by the time this was public, they had already fixed it in new silicon, but this
[2597.04 → 2601.00] problem existed in the Pentium chips and this professor had found it.
[2601.10 → 2604.30] And it was something you could reproduce in an Excel spreadsheet by typing a division.
[2604.30 → 2604.74] Right.
[2604.88 → 2609.96] And the average person was never going to see this or care about it or, you know, like they're
[2609.96 → 2615.04] not doing this level of, of, of, of math in their, in their typical spreadsheet, but it
[2615.04 → 2618.68] was a very obvious thing that you could test on your own computer and get the wrong answer.
[2618.80 → 2619.08] Right.
[2619.34 → 2624.70] And it, and the reason I'm mentioning it is that on the metal before previously, there've
[2624.70 → 2627.80] been mentions of things like microcode and some of the tricks that are done behind the
[2627.80 → 2635.06] scenes, the modern era of microcoded x86 machines, I think dates back to about then.
[2635.50 → 2635.92] Interesting.
[2635.92 → 2639.88] Because post FDI, Intel and others said,
[2640.06 → 2641.00] We need to be able to update this.
[2641.08 → 2642.54] We need to be able to fix some of this.
[2642.72 → 2642.82] Yeah.
[2643.02 → 2643.38] Interesting.
[2643.84 → 2648.80] Well, and I, when I first saw your tweet, I, and I, before I did the, the, the calculation
[2648.80 → 2651.56] in my head of the years, I thought you might've been referring to FOOD.
[2651.98 → 2652.16] Right.
[2652.16 → 2652.24] Right.
[2652.50 → 2654.04] So FOOD was only a couple of years later.
[2654.16 → 2654.44] Yep.
[2654.94 → 2658.40] And FOOD, they got very, very lucky with FOOD.
[2658.48 → 2662.06] So FOOD was an it was an illegal instruction, but it was a prefix.
[2662.06 → 2664.96] But a prefix, that was a locked prefix on an illegal instruction.
[2664.96 → 2665.44] Right.
[2665.72 → 2670.60] And the CPU couldn't lock the bus and then tried to evaluate the illegal instruction
[2670.60 → 2671.44] with the bus locked.
[2671.68 → 2671.82] Right.
[2672.38 → 2673.62] And it just didn't proceed.
[2674.36 → 2680.48] And there was a moment of a there's like a 72-hour moment where any user could hang
[2680.48 → 2686.54] any, hard hang any box before Intel got, and actually we'd implemented one workaround
[2686.54 → 2689.60] of uncapping the first six entries of the IDT.
[2689.78 → 2689.94] Right.
[2690.00 → 2690.68] There was a, exactly.
[2690.68 → 2694.48] The IDT, you could, you also, there was a, there was a, right.
[2694.52 → 2697.54] And there was one with, with aligning some of the.
[2697.76 → 2698.10] Right.
[2698.24 → 2698.42] Right.
[2698.42 → 2703.62] Well, so I was very proud of myself because I would hear about this and implemented a
[2703.62 → 2706.96] mitigation very quickly, and we beat everyone else to a mitigation.
[2706.96 → 2711.88] And it was kind of hairy to have the first six entries of the IDT unmapped and kind of,
[2711.88 → 2712.70] and clean that up.
[2713.16 → 2714.68] And I was like, this is going to be great.
[2714.82 → 2716.50] And then they're like, actually we've got a much simpler mitigation.
[2716.94 → 2717.22] Right.
[2717.22 → 2718.86] If you just, a certain alignment of the IDT.
[2719.30 → 2720.82] It was a cross page, it was a cross page thing or something.
[2720.88 → 2721.00] Yeah.
[2721.00 → 2721.10] Right.
[2721.10 → 2723.42] There was some alignment where you forced a trap if you went.
[2723.82 → 2725.00] That was the original mitigation.
[2725.24 → 2729.08] And then what they found is actually if you just, I think if you make the IDT unwritable.
[2729.44 → 2729.82] Oh, okay.
[2730.02 → 2730.98] That mitigated it.
[2731.00 → 2731.20] Okay.
[2731.28 → 2732.22] You're like, oh, come on.
[2732.46 → 2732.64] Yeah.
[2732.86 → 2734.10] That's a much easier mitigation.
[2734.28 → 2737.54] I was very, I felt like, no, I've already implemented the hard mitigation.
[2737.74 → 2738.38] Like, can't be that.
[2738.62 → 2742.18] I seem to recall there were six or something different mitigations in the end for Ruth.
[2742.42 → 2742.60] Yeah.
[2742.72 → 2743.12] Yes.
[2743.18 → 2747.94] I think that there ended up being a lot, but it was also one of those early warnings.
[2748.34 → 2748.54] Yeah.
[2748.94 → 2751.36] That they might, these microprocessors are not infallible, obviously.
[2751.36 → 2754.66] But, but if you look at the timeframe for some of these things, so, you know, bugs that
[2754.66 → 2757.12] are being found in the early and mid-nineties, right.
[2757.12 → 2759.80] We don't have cloud computing.
[2760.12 → 2760.36] Right.
[2760.64 → 2764.62] We don't have the rise of very homogenous attack surfaces everywhere.
[2764.96 → 2765.16] Yeah.
[2765.40 → 2768.54] With untrusted users running third-party code on your machines.
[2768.68 → 2768.80] Yeah.
[2768.82 → 2770.88] I mean, you think about it, like Ruth today in the cloud.
[2771.08 → 2771.86] Oh my goodness.
[2772.34 → 2774.66] Like the consequences would be so much more grave.
[2774.90 → 2775.54] Ruth in your Lambda.
[2776.62 → 2777.38] It's like.
[2777.78 → 2779.30] And we've come so close to that.
[2779.56 → 2782.76] Serverless, serverless plus Ruth equals annihilation.
[2782.76 → 2785.32] It is serverless, but not in the way that they, actually.
[2785.32 → 2785.52] Right.
[2785.70 → 2785.88] Sorry.
[2785.88 → 2789.32] If it doesn't work at all, it's still serverless.
[2789.32 → 2789.76] It's still serverless.
[2789.84 → 2790.24] Congratulations.
[2790.42 → 2792.30] You are now officially serverless.
[2793.38 → 2793.78] Yeah.
[2794.28 → 2794.92] No, you're right.
[2794.96 → 2798.46] In terms of the attack surface has gotten much more, much scarier.
[2798.74 → 2798.90] Yeah.
[2799.10 → 2803.56] At this point in time, we're relying a lot on technology that was built for a very different
[2803.56 → 2803.88] use.
[2805.02 → 2807.72] And how do you think we kind of square on some of this stuff?
[2807.76 → 2810.94] Because I feel like it, I mean, like hyper-threading.
[2810.94 → 2811.64] Uh-huh.
[2811.74 → 2816.02] I mean, I know a lot of us believe it has to be a burial at sea for hyper-threading because
[2816.02 → 2823.02] it's too intimate to ever be able to completely mitigate.
[2823.02 → 2824.30] Yeah.
[2824.30 → 2824.34] Yeah.
[2824.34 → 2831.74] So hyper-threading or SMT, simultaneous multi-threading, is basically when you take a processor, a microprocessor
[2831.74 → 2839.96] core, a thing that does the computing, and you partition it into a smaller number of logical
[2839.96 → 2841.64] processors, threads, you know, whatever.
[2841.64 → 2847.84] Each of which has enough architectural state to look like a separate processor, but they
[2847.84 → 2849.88] share a lot of resources very closely.
[2850.38 → 2852.20] Like their caches, for example.
[2852.40 → 2852.52] Yeah.
[2852.52 → 2852.86] I bet you.
[2852.96 → 2853.18] Yeah.
[2853.32 → 2854.84] And a lot of other pieces.
[2855.06 → 2856.16] It's very, very tightly integrated.
[2856.32 → 2861.82] And the thing with hyper-threading or SMT in general is that it gives you about a 30% quick
[2861.82 → 2863.12] win in terms of performance.
[2864.10 → 2864.88] It's a sugar high.
[2864.98 → 2865.22] It's nice.
[2865.26 → 2865.84] It's a sugar high.
[2865.92 → 2866.28] It's great.
[2866.28 → 2866.32] Right.
[2866.84 → 2873.68] I have hated SMT for years as a concept because it's so tightly coupled, right?
[2873.72 → 2877.74] I've been an ARM fanboy forever, as I think you and others know.
[2878.30 → 2882.58] And when it comes to the history of ARM servers, which I've been heavily involved in as well,
[2882.74 → 2887.70] that there I've really pushed hard to kill SMT early on because it just seemed like a really
[2887.70 → 2888.28] bad idea.
[2888.38 → 2894.10] It seemed like a, you know, it looks great, but, you know, and it turns out in the context
[2894.10 → 2895.62] of security, I think I was right.
[2895.62 → 2896.06] Yeah.
[2896.60 → 2898.72] And so does ARM not, ARM has no SMT?
[2899.02 → 2901.60] There are very few ARM processors that do SMT.
[2901.80 → 2903.54] There's one server processor that does.
[2903.80 → 2906.02] It can do SMT one, two, or four, actually.
[2906.22 → 2907.50] So it can actually have four threads.
[2907.64 → 2907.96] Yeah.
[2908.10 → 2909.66] Which is pretty rare, but that does happen.
[2909.90 → 2910.00] Yikes.
[2910.54 → 2916.28] And ARM has one core they've announced, which is threaded, but, you know, not intended for
[2916.28 → 2916.74] server use.
[2916.90 → 2917.08] Right.
[2917.14 → 2919.18] So by and large, they have avoided SMT.
[2919.26 → 2921.04] By and large, they've avoided it so far.
[2921.16 → 2921.38] Right.
[2921.72 → 2922.12] Interesting.
[2922.48 → 2922.62] Yeah.
[2922.62 → 2923.06] Yeah.
[2923.42 → 2926.54] So talk about the when did you fall in love with ARM?
[2926.84 → 2927.44] Tell me about it.
[2927.62 → 2929.04] There's got to be an ARM love story here.
[2929.08 → 2931.20] Well, that roots back to the 6502, right?
[2931.26 → 2933.10] That's the BBC micro.
[2933.46 → 2936.24] That's ACORN, which followed on the ACORN Archimedes.
[2937.14 → 2937.28] Right.
[2937.64 → 2939.30] ACORN, as in ACORN.
[2939.72 → 2940.00] Yeah.
[2940.00 → 2946.60] And then Advanced Risk Machines becomes ARM, becomes lots of other things I've probably
[2946.60 → 2947.22] missed there.
[2947.40 → 2951.56] But yeah, I think a lot of it traces back to being a kid growing up in the UK at a certain
[2951.56 → 2951.88] point.
[2952.08 → 2952.40] Wow.
[2952.44 → 2953.62] It's an act of patriotism.
[2953.78 → 2953.90] Yeah.
[2953.90 → 2956.66] And it's weird because I just became a naturalized American citizen.
[2957.22 → 2957.24] So.
[2957.80 → 2958.06] Yeah.
[2958.14 → 2959.10] So now you are.
[2959.10 → 2959.74] Now I still love ARM.
[2959.86 → 2960.68] You still love ARM.
[2961.28 → 2962.34] It's the old country.
[2962.68 → 2962.94] Yeah.
[2962.94 → 2964.40] You got to bring the old country with you.
[2964.40 → 2970.16] I think it's because I've been a RISC fan person for a very long time.
[2970.42 → 2970.86] RISC is great.
[2971.16 → 2971.80] RISC is great.
[2972.58 → 2980.12] And so I got very interested in the prospect for diversification by using, you know, I mean,
[2980.12 → 2981.80] these days there's also things like RISC-V, right?
[2981.84 → 2984.42] Which is, I was just at the RISC-V summit this afternoon.
[2984.74 → 2985.78] I love RISC-V.
[2986.32 → 2986.54] Yeah.
[2986.70 → 2987.04] Don't you?
[2987.44 → 2989.08] I mean, I love the spirit of RISC-V.
[2989.32 → 2989.90] You know what?
[2989.90 → 2994.94] I love the zeitgeist of RISC-V in terms of trying to learn everything from every architecture.
[2995.40 → 2999.58] I mean, one, I hate to say this and someone's probably going to send me a nasty email or
[2999.58 → 3003.84] tweet or something after I say this, but one RISC machine is very similar to another RISC
[3003.84 → 3005.08] machine, right?
[3005.18 → 3006.32] I mean, fundamentally.
[3006.66 → 3008.02] Aren't they each special in their own way?
[3008.10 → 3008.28] Yeah.
[3008.36 → 3009.60] Well, each of them have weird quirks.
[3009.74 → 3010.00] Okay.
[3010.18 → 3011.02] That's kind of what I mean.
[3011.42 → 3014.14] But RISC-V has got fewer quirks, I feel.
[3014.56 → 3019.64] I think RISC-V is very clean because what they've done is, so take the original ARM, right?
[3019.64 → 3022.94] Original ARM had a lot of gunk in it.
[3023.48 → 3029.78] Even now, ARMv7, which is their 32-bit architecture, has a lot of baggage.
[3029.96 → 3030.06] Yeah.
[3030.14 → 3033.00] Explain thumb to me and still stay in love with ARM.
[3033.56 → 3034.14] I can't.
[3034.22 → 3034.36] Okay.
[3034.40 → 3034.76] Thank you.
[3035.18 → 3036.46] That's actually what I wanted to hear.
[3036.48 → 3040.88] You know, ARM had a lot of, you know, well, it was about code density.
[3041.38 → 3041.76] Right.
[3042.00 → 3042.80] I get it.
[3043.04 → 3043.64] Mistakes were made.
[3043.78 → 3044.36] Mistakes were made.
[3044.36 → 3050.56] Well, you know, and I think if you unwind that, you know, x86 is a variable width instruction set.
[3050.76 → 3054.26] So instructions can be as small as a single byte.
[3054.90 → 3055.54] Many are.
[3055.76 → 3055.96] Right.
[3056.08 → 3058.12] So the code density is pretty good.
[3058.32 → 3061.30] And you do waste memory with RISC machines.
[3061.50 → 3063.10] But our memory is pretty fast these days.
[3063.22 → 3065.02] And we have lots of tricks that we use.
[3065.10 → 3067.94] We do, you know, opcode fusion and things like this.
[3067.94 → 3072.88] We say, well, this instruction follows this instruction, and we'll just merge them together in our internal representation.
[3073.22 → 3073.32] Right.
[3073.68 → 3079.02] So we have lots of tricks we use today that actually mean that we're less worried about the need to do stuff like that, like thumb.
[3079.64 → 3081.44] And then ARM has a lot of other stuff.
[3081.52 → 3085.94] It has predicated execution where I can say, maybe I execute these instructions, maybe I don't.
[3086.36 → 3088.70] It lets you update the program counter directly.
[3088.90 → 3089.30] Right.
[3089.36 → 3091.94] Which tends to have a horrifying impact in implementation.
[3093.02 → 3093.14] Right.
[3093.14 → 3099.12] It's just one of those things that from a microprocessor architect perspective is just like, oh, my God, it's just brutal.
[3099.30 → 3099.36] Right.
[3099.58 → 3100.38] And then they cleaned it up.
[3100.60 → 3112.96] So ARMv8 is basically a clean sheet design where they took all the things that were not great about the older architecture, and they ripped them out, and they've got a very clean design, which is very similar to RISC-V.
[3113.08 → 3113.26] Right.
[3114.14 → 3114.88] In the end.
[3114.92 → 3117.30] And the reason is that I think there's only so many ways to do it.
[3117.30 → 3123.52] And they've kind of all trended towards having, you know, certain set of instructions.
[3124.12 → 3128.80] I think the measurement, I think Chris, I can never get his last name right, Hello.
[3129.12 → 3129.96] I'm going to butcher that.
[3130.10 → 3142.24] I think he did an analysis, and it was sort of 1% performance difference or 2% in the optimal case between a hypothetical perfect, you know, RISC-V versus ARM decode or something.
[3142.46 → 3142.72] Interesting.
[3142.72 → 3145.42] You know, I think they're very close.
[3146.12 → 3151.64] Well, I thought it was interesting that in RISC-V, I mean, in the book, they really talk about code density a lot.
[3151.74 → 3160.92] I mean, they're definitely, they've got a spectre of code density clearly hanging over them, and they compare it a lot to x86 and show that actually the code density is pretty similar because of the instruction sets, basically better.
[3161.30 → 3161.82] Yeah, I mean.
[3162.02 → 3165.10] Also, x86 is getting some variable width instruction.
[3165.30 → 3167.74] I mean, okay, the good variable width instruction, like one or two bytes.
[3167.74 → 3173.30] It's, there are some like monsters out there now, like you have this kind of the seven, nine bytes.
[3173.50 → 3175.12] I mean, what's the longest instruction in x86?
[3175.34 → 3175.66] 15.
[3176.08 → 3176.32] 15 bytes.
[3176.32 → 3177.14] Is that true?
[3177.50 → 3177.66] Yeah.
[3178.02 → 3181.26] Theoretical maximum instruction decode is 15 bytes.
[3181.44 → 3182.06] Holy God.
[3182.10 → 3182.84] What instruction is that?
[3183.20 → 3183.50] Do you know?
[3183.58 → 3184.86] I don't think it exists.
[3185.16 → 3185.36] Okay.
[3185.46 → 3186.36] This is a theoretical instruction.
[3186.60 → 3189.18] But they've got actual instructions that are getting up there, I feel.
[3189.58 → 3190.54] Maybe halfway, yeah.
[3190.54 → 3190.74] Yeah.
[3190.86 → 3194.42] Because the thing with x86 is they have all these prefixes you can add to instructions, right?
[3194.42 → 3199.92] So you can do this, but also I'd like you to lock the bus and these other things as well as you run this instruction, right?
[3200.60 → 3206.56] So my interest in ARM was, I think, partly an artifact of the time and place I grew up in.
[3206.76 → 3214.80] And then I was living in the US when I got really interested in what could be done with ARM server because you could see the progression of, you know, these mobile devices.
[3215.48 → 3217.94] And at the time, the BeagleBoard.
[3218.34 → 3218.74] Right.
[3218.84 → 3219.02] Right.
[3219.20 → 3219.38] Yeah.
[3219.38 → 3224.94] So this is pre-Raspberry, well, maybe not pre-Raspberry Pi, but similar timeframe to the Raspberry Pi starting up.
[3225.20 → 3231.76] And I'm looking at this board, and I'm thinking, not many generations hence, this could be an interesting server.
[3231.92 → 3233.30] They would need to be 64-bit.
[3233.40 → 3236.46] They would need lots of other things for it to actually get there.
[3236.54 → 3237.82] But I could see a path.
[3238.02 → 3245.32] And my interest spawned because I saw a very small competitive landscape of servers out there.
[3245.52 → 3245.70] Yeah.
[3245.70 → 3248.42] And it will, interestingly, I think that will change.
[3248.56 → 3255.02] I think x86 will change in the next few years because most of the original x86 patents are expiring next year.
[3255.50 → 3256.42] That is interesting.
[3256.62 → 3258.00] So that will be interesting to see.
[3258.26 → 3259.86] That will definitely be interesting.
[3259.98 → 3260.16] Yeah.
[3260.18 → 3263.16] I think it might be open season on people building interesting stuff there.
[3263.48 → 3272.46] But at the time, when I'm looking at alternatives, I'm thinking, well, ARM is a very interesting alternative because it has a lot of traction with, you know,
[3272.46 → 3276.26] very big companies using it in mobile phones and elsewhere.
[3276.70 → 3282.00] And so that will fund a lot of the investment needed to grow this up and put it into more interesting places.
[3282.32 → 3284.54] And it's certainly interesting what AWS is up to, right?
[3284.78 → 3287.78] With Graviton, I thought, was a pretty interesting announcement.
[3288.12 → 3289.88] I mean, it's a pretty interesting CPU.
[3290.14 → 3291.42] The Graviton 2 that they just announced.
[3291.42 → 3292.26] Right, the Graviton 2, right.
[3292.26 → 3295.08] Yeah, is an ARM Ares design.
[3295.22 → 3296.08] That's the name of the core.
[3296.20 → 3306.44] The thing with the Graviton 2 is it is kind of the first mainstream ARM server that anyone can just get access to, right?
[3306.46 → 3308.54] Without having to go through crazy hoops to do it.
[3308.80 → 3311.34] That's of a very high performance and at a good price point.
[3311.54 → 3311.76] Right.
[3311.76 → 3317.70] And what that will do is, I mean, it's actually, you know, it performs, I think, 20% better than x86.
[3318.56 → 3322.88] And their TCO numbers were like 40% cheaper than running an x86.
[3323.22 → 3323.76] Some metrics.
[3323.98 → 3324.38] Some metrics.
[3324.38 → 3327.84] Yeah, I'm not trying to sell AWS or Graviton.
[3328.08 → 3333.36] But I think it's interesting because you'll get people that will now do a comparison, and they will say,
[3333.52 → 3338.36] I'm not just taking my workload and giving something up.
[3338.68 → 3338.88] Right.
[3338.88 → 3339.12] Right.
[3339.24 → 3344.56] I'm, you know, this idea that you have like, you know, a lot of companies appear and say,
[3344.70 → 3345.94] I'm going to have a sea of cores.
[3346.38 → 3346.64] Right.
[3346.68 → 3353.46] I'm going to give you all these amazing things, but you have to take your workload and run it on a thousand cores and change everything you're running.
[3353.60 → 3354.32] You've got to go C-Micro.
[3354.74 → 3355.20] C-Micro.
[3355.20 → 3358.30] Well, so the interesting thing with the early ARM servers that killed a lot of them,
[3358.36 → 3362.82] and I was a real broken record going into these companies and trying to give them business advice,
[3363.44 → 3366.32] which, you know, sometimes I think I give good business advice, by the way.
[3366.32 → 3372.28] I would tell them, look, the thing is that at the time I was with Red Hat, if you are running software,
[3373.24 → 3377.44] you pay whether you're paying licensing or subscriptions or whatever the model is,
[3377.48 → 3382.52] you are paying based on the number of nodes that you're running on, number of servers you're running on.
[3382.88 → 3383.04] Right.
[3383.04 → 3390.10] And no company is incentivized to say, oh, yeah, you know, this emerging architecture is wonderful and great,
[3390.10 → 3394.36] and you need three times as many computers to do the same thing.
[3394.54 → 3396.52] We'd love to give you a three times discount.
[3396.62 → 3397.52] That would be fabulous.
[3397.76 → 3397.94] Right.
[3398.12 → 3399.40] Like what company is going to do that?
[3399.50 → 3400.16] None were.
[3400.16 → 3405.58] So the actual cost in a lot of these early machines was higher because you had to go and have three times as many.
[3405.76 → 3408.20] And three times as many means three times as much memory.
[3408.34 → 3415.92] I mean, you know, this building real machines, that the cost of the processor is actually a relatively small piece.
[3416.10 → 3416.18] Right.
[3416.40 → 3422.44] You actually want as powerful a host CPU as you can possibly have within the limits of the system.
[3422.66 → 3427.00] I mean, you really do not want to waste time with this kind of, I mean, and I feel like, you know,
[3427.00 → 3431.04] C-Macro did this, a bunch of companies did this where you had, and Moonshot did this too, right?
[3431.06 → 3434.32] Because weren't they 32-bit ARM cores for Moonshot?
[3434.80 → 3442.46] Moonshot, I think they had a Canada reference, but the first one they really came out with in a big way was the applied micro X-gene.
[3442.58 → 3443.50] So it was 64-bit.
[3443.62 → 3443.88] Okay.
[3444.24 → 3445.30] Funny backstory on Moonshot.
[3445.38 → 3448.74] When it shipped, it was, you know, these are little cartridges.
[3448.90 → 3450.24] They look like PCI cards.
[3450.34 → 3454.64] You could put 45 of them in a 4.3, I think, U.
[3455.20 → 3456.16] So it's not 4U.
[3456.16 → 3457.44] It's not 5U.
[3457.74 → 3458.12] Yeah, yeah, yeah.
[3458.20 → 3459.68] It's the old 4.3U.
[3459.68 → 3462.56] It's the old 4.3U because everybody has that in their rack.
[3462.70 → 3466.56] Does that at least multiply out to some reasonable number from a metric perspective?
[3466.70 → 3469.20] Because, I mean, a U is a goofy number to begin with.
[3469.78 → 3472.52] I'm going to rant here about the U.S. units of measurement.
[3473.44 → 3474.38] Listen, go for it.
[3474.40 → 3475.26] We've got to come in for it.
[3475.30 → 3476.06] We've got to come to us.
[3476.66 → 3479.18] But didn't we get, I mean, it's an imperial system of measurement.
[3479.32 → 3481.28] We got it from our former overlords.
[3481.28 → 3485.04] There's British imperial units and there's U.S. customary.
[3485.30 → 3486.94] And they are not the same, my friend.
[3487.10 → 3488.16] They are not the same.
[3488.24 → 3490.90] They tried in 1850 to fix it, I think, but it was not.
[3491.06 → 3493.34] Anyway, if one had read a little bit about that.
[3494.48 → 3499.12] But so Moonshot, so you have this sort of 45 cartridges in 4.
[3499.20 → 3500.42] whatever U, right?
[3500.50 → 3502.24] Which is a weird unit, but whatever.
[3503.22 → 3505.68] So firstly, you get this problem of licensing, right?
[3505.68 → 3509.16] When they shipped the first Moonshot cartridge, they shipped it with,
[3509.64 → 3512.88] and this is going to sound like I'm ranting about a particular Linux distribution.
[3513.18 → 3513.50] I'm not.
[3513.56 → 3514.30] It happened to be Ubuntu.
[3514.46 → 3515.62] This is not an anti-Ubuntu comment.
[3515.82 → 3517.16] I actually like every Linux distro.
[3517.26 → 3517.70] They're all great.
[3518.20 → 3521.32] But they shipped this with a hacked up Linux because they're like,
[3521.38 → 3522.46] oh, it's just Linux, you know?
[3522.50 → 3524.96] So they did a deal with Canonical, and they said,
[3525.04 → 3528.54] oh, well, you can buy this server now, and it comes with a free Linux.
[3528.62 → 3531.78] And they hacked it up because it was still this sort of embedded platform.
[3532.32 → 3532.76] Right, right.
[3532.76 → 3536.62] So Moonshot, the first Moonshot cartridge is a weird form factor.
[3537.56 → 3540.82] And oh, by the way, it only runs this one weird operating system build
[3540.82 → 3543.56] that stopped being supported in the future, right?
[3543.88 → 3546.30] And I went back to HP.
[3546.92 → 3548.96] Actually, what I did was I went to Applied Micro
[3548.96 → 3550.42] who had made the processor at the time.
[3550.90 → 3552.64] And I said, you got the firmware wrong.
[3553.04 → 3554.54] What you should have done is this.
[3554.66 → 3557.38] And I know we joked earlier about my favourite being UEFI, right?
[3557.76 → 3559.48] I have never met.
[3559.48 → 3564.10] I just didn't know the pro-UEFI demographic existed.
[3564.44 → 3567.40] It's basically, I mean, is this like the same person
[3567.40 → 3571.22] that wants to, you know, buy a Transmeta machine so they can exploit it?
[3571.28 → 3574.06] I mean, do you enjoy UEFI because it's so terrible?
[3574.42 → 3575.48] Well, yes, of course.
[3575.66 → 3576.38] I like the pain.
[3576.54 → 3577.18] Oh, you like the pain.
[3577.28 → 3578.02] You like terrible in this.
[3578.16 → 3578.60] No, I don't.
[3578.86 → 3580.36] So the thing is, things like UEFI,
[3580.58 → 3584.80] these are specifications that don't have to relate to the implementation.
[3584.80 → 3587.70] You know, but my colleague at Oxide, Josh Recall,
[3587.88 → 3591.54] was fond of saying that UEFI is like MS-DOS from 2099.
[3591.88 → 3593.80] It really does look like futuristic DOS.
[3593.92 → 3594.70] It is so weird.
[3594.90 → 3597.60] If DOS actually was ever evolved over time,
[3597.60 → 3599.26] it would end up looking like this.
[3599.90 → 3602.36] So I like the UEFI specification.
[3602.62 → 3605.52] I think Tiana Core, the implementation has some issues.
[3606.94 → 3611.04] But anyway, I said, you know, if you had used a standard on here,
[3611.08 → 3613.24] you could run anything on these platforms.
[3613.32 → 3614.26] And wouldn't that be great, right?
[3614.26 → 3616.10] So, well, I thought it'd be great
[3616.10 → 3618.58] because I was building an operating system that was UEFI-based.
[3618.76 → 3620.28] So clearly, it would have been great
[3620.28 → 3621.86] because we could have run my operating system.
[3621.94 → 3622.34] Great for me.
[3622.34 → 3624.58] And also, I was trying to convince Red Hat to go to market
[3624.58 → 3626.44] because we kept doing these dev previews.
[3626.52 → 3628.14] And I'm like the number one ARM fanboy.
[3628.32 → 3630.70] So, you know, please, please ship this thing
[3630.70 → 3632.30] that we've spent years and years and years building.
[3632.38 → 3633.90] And they were like, well, son,
[3634.70 → 3636.62] when a server comes along from an OEM,
[3636.84 → 3638.30] and I'm like, great, here's an OEM.
[3638.48 → 3641.40] Oh, crap, you shipped it with firmware that we can't support
[3641.40 → 3643.54] because it doesn't add any of the specs, right?
[3643.54 → 3646.04] So I went back to Applied Micro
[3646.04 → 3648.96] and conspired with a friend of mine over there.
[3649.10 → 3654.32] And we hacked up a UEFI runtime that ran from memory.
[3654.64 → 3656.58] So what happened is this thing booted with Boot.
[3656.64 → 3658.62] That was its bootloader in the cartridge, right?
[3659.00 → 3660.58] It loaded something it thought was a kernel,
[3660.92 → 3662.16] which was actually UEFI.
[3662.44 → 3662.76] Oh, my God.
[3662.76 → 3665.72] And it then reinitialized itself without retraining memory
[3665.72 → 3666.62] because we had to have that up.
[3667.40 → 3672.16] Reinitialized all the IOS and then chain loaded basically a UEFI environment.
[3672.40 → 3675.26] And then, but it got better because it would load this over the network
[3675.26 → 3676.22] because I didn't want to modify,
[3676.36 → 3678.70] I didn't want to rely on any local storage to make this happen
[3678.70 → 3680.14] because I couldn't access the flash.
[3680.14 → 3682.38] They locked that down in these shipping units.
[3683.24 → 3688.72] So Boot would TFTP, but not the Pixie TFTP.
[3689.04 → 3689.70] This is very important.
[3689.84 → 3693.68] So it would load from one location that Boot was expecting.
[3693.92 → 3695.64] It would load my modified firmware.
[3696.64 → 3699.90] And then that would then do another network boot
[3699.90 → 3701.54] and then load the operating system.
[3701.74 → 3704.86] But the thing is, the outcome was you could take this cartridge
[3704.86 → 3706.60] and you could show that it could run a standard OS.
[3706.80 → 3706.90] Right.
[3706.96 → 3708.20] It only took 25 minutes to boot.
[3708.20 → 3709.90] It did take about 10 minutes to boot.
[3710.12 → 3710.34] Okay.
[3710.50 → 3710.72] Okay.
[3710.94 → 3712.90] But then I went to HP and said,
[3713.00 → 3714.50] this is what you should have shipped.
[3715.76 → 3716.12] And?
[3716.22 → 3718.90] And they relaunched the cartridge.
[3719.26 → 3720.00] Oh, with?
[3720.42 → 3722.36] With not, well, no, it was not my firmware, right?
[3722.42 → 3724.88] They did do it professionally.
[3725.08 → 3726.20] And it didn't have like, you know,
[3726.28 → 3730.28] JCM handy dandy firmware banner printed when it loaded, right?
[3730.36 → 3730.76] And they did.
[3731.06 → 3732.18] And they got some good firmware people
[3732.18 → 3733.44] and it was nothing related to my thing.
[3733.72 → 3735.82] But I use that as an argument to say,
[3735.90 → 3736.90] here's what you should have done.
[3737.14 → 3737.38] Right.
[3737.38 → 3737.64] Right.
[3737.76 → 3739.02] And they relaunched Moonshot.
[3739.16 → 3739.42] Wow.
[3740.48 → 3741.44] And I did a lot,
[3741.52 → 3743.64] I ended up doing that a lot in the ARM server space,
[3743.68 → 3744.36] going in and saying,
[3744.44 → 3746.04] I know you think that that's how you should have,
[3746.28 → 3747.54] how you want to do this.
[3747.74 → 3748.86] How often was it successful?
[3749.26 → 3750.96] Well, I'm a very persuasive,
[3752.12 → 3752.90] I can be very annoying.
[3753.24 → 3754.06] Just keep showing up.
[3754.48 → 3755.52] I keep, I, you know,
[3755.56 → 3757.36] I would show up and, you know,
[3757.42 → 3758.30] these executives,
[3758.42 → 3760.54] these different companies would come to know me pretty well.
[3760.62 → 3762.44] Don't I have a restraining order against you?
[3762.44 → 3765.26] Well, I also became the patron saint of lost causes.
[3765.50 → 3769.64] So like I would go in when companies were shutting down various efforts and I would go and help them.
[3770.02 → 3771.82] I mean, I think I'm probably sure that I don't know if I can share this.
[3771.92 → 3772.90] I'm going to share the story anyway.
[3773.00 → 3773.66] That's the spirit.
[3773.96 → 3775.26] That's the on the metal spirit.
[3776.22 → 3776.74] So, you know,
[3776.74 → 3777.12] Damn the lawyers.
[3777.22 → 3778.04] I'm going to share this story.
[3778.04 → 3780.22] So Broadcom had an ARM server.
[3780.32 → 3780.92] Oh, here we go.
[3781.02 → 3781.14] Right.
[3781.24 → 3782.08] Called Vulcan, right?
[3782.50 → 3787.24] And that effort kind of ran out of money and patience from the executive.
[3787.36 → 3791.96] Well, Arago brought Broadcom, and now it's kind of Newcomb, right?
[3792.06 → 3794.42] It's called Broadcom, but it's not Broadcom.
[3794.60 → 3795.16] It's very different.
[3795.42 → 3795.70] Yes.
[3796.64 → 3799.72] Everything is now Broadcom is basically what I've, yeah.
[3799.96 → 3800.28] Right.
[3800.42 → 3804.88] So that happened, and they realized we don't really care about ARM server stuff.
[3804.88 → 3811.62] We're investing tons of money into because, you know, that's not the way that their economics tend to work over there.
[3811.74 → 3812.38] I'll put it that way.
[3812.42 → 3813.66] That's very, that's a very nice way to put that.
[3814.00 → 3818.82] So they killed this project and all the OEMs were telling me, oh, well, it's all shut down.
[3818.94 → 3819.52] It's all gone.
[3819.58 → 3819.78] Right.
[3819.88 → 3826.98] So, but then a couple of us who came to, who came to call ourselves the Rebel Alliance became very annoying.
[3827.12 → 3833.16] So we would go and talk to CEOs around the valley, and we would, you know, kind of try to sell this company that we were not employees of.
[3833.16 → 3836.66] And we were just very interested in saving and making sure it landed somewhere.
[3837.44 → 3837.46] So.
[3837.58 → 3838.68] You're just trying to find a home for it.
[3838.70 → 3838.90] Yeah.
[3838.96 → 3848.18] So I played a not major, but a reasonably significant role in persuading those assets to land in what became Calcium's Thunder X2.
[3848.46 → 3848.84] Got it.
[3849.08 → 3853.66] And went back to the OEM that had just told me we're shutting everything down and said, no, no, no, no.
[3853.72 → 3854.14] Just wait.
[3854.30 → 3854.78] Just wait.
[3854.94 → 3856.62] We'll be back in a few weeks.
[3856.74 → 3857.76] This will all be fine.
[3858.04 → 3860.22] I, John Masters, will orchestrate the future.
[3860.88 → 3861.88] And some others too.
[3861.96 → 3862.08] Right.
[3862.08 → 3872.20] It wasn't just me, but I do remember that you had the design team for that part were at super computing talking to potential customers, and they'd just been shut down, but they wanted to keep going.
[3872.34 → 3877.92] So they were in my Airbnb sleeping on my couch, which is, you know, kind of fun backstory.
[3877.92 → 3881.24] At that point, did you own the company by sharing it?
[3881.36 → 3885.60] I mean, it's like how many nights stay would have yielded you the assets at that point?
[3885.60 → 3893.08] But there's in the book version that I'm sure I'll never write because I plan to work again in this industry.
[3893.38 → 3897.80] There are a lot of these stories where, you know, you go into these companies, and you say-
[3897.80 → 3898.68] What is this book called?
[3901.18 → 3902.48] Fixing things the way they should be?
[3902.54 → 3902.92] I don't know.
[3903.08 → 3907.78] But like I would go in, and I would say, here's the film where you should have done, or here's, you know, here's how you should have tweaked this.
[3907.94 → 3908.88] Unify a love story?
[3908.88 → 3909.32] Yeah.
[3909.98 → 3911.36] Well, you know, there is, okay.
[3912.36 → 3915.26] I'm certain you have seen the book Savaged by System D.
[3916.04 → 3916.72] I, yes.
[3916.80 → 3917.10] Yes.
[3917.14 → 3917.66] I have.
[3917.74 → 3918.36] Have you seen this?
[3918.72 → 3918.98] Yes.
[3919.32 → 3920.26] I saw it on Amazon.
[3920.44 → 3921.48] I'm the one who showed you.
[3921.66 → 3922.48] Oh, hey.
[3923.02 → 3923.54] That is probably-
[3923.54 → 3924.54] I have it on my Kindle.
[3924.88 → 3925.96] That is true.
[3926.28 → 3927.10] You did show me that.
[3927.22 → 3927.40] Okay.
[3927.54 → 3928.52] I have it on my Kindle.
[3929.16 → 3929.52] Okay.
[3929.92 → 3930.66] A little, so yeah.
[3930.78 → 3932.24] So, you know.
[3932.26 → 3933.34] So it could be that bad.
[3933.64 → 3934.70] Unchained by UEFI?
[3934.86 → 3938.32] What's the I'm trying to think, what's the what's the Savaged by System D?
[3938.32 → 3940.68] I have that get commit murder inside.
[3940.88 → 3941.24] Oh.
[3943.04 → 3946.36] But I also feel like, I mean, do you feel like you're in good company there with like,
[3946.44 → 3948.02] it's like the System D and UEFI?
[3948.14 → 3949.46] I mean, UEFI is hated.
[3949.64 → 3950.38] I mean, it's reviled.
[3950.78 → 3951.14] Right?
[3951.26 → 3951.76] It is hated.
[3952.04 → 3952.30] Okay.
[3953.28 → 3953.54] Yeah.
[3953.82 → 3958.12] There are a lot of things that are hated in this world and totally relied on.
[3958.38 → 3963.00] I mean, you know, I would meet people doing Core Boot, for example, Linux Boot, or, you
[3963.00 → 3967.18] know, various different other stuff that I ought to, in all rational sense, prefer.
[3967.38 → 3967.70] Right.
[3967.70 → 3968.10] Right.
[3968.10 → 3969.44] And I do.
[3969.82 → 3974.14] But I'm like, first you have to build it the boring way that the industry is used to.
[3974.34 → 3974.60] Right.
[3974.68 → 3975.92] And then you can go and throw it away.
[3976.10 → 3979.88] I mean, and that's also code for, you also need to run things like Windows as well.
[3979.96 → 3980.12] Right?
[3980.14 → 3983.30] If you want to be successful, you have to, you do have to run Windows.
[3983.32 → 3983.44] All right.
[3983.44 → 3984.28] We're going to take a quick break.
[3984.32 → 3988.68] On that note, we're going to come back in just a bit with more On the Metal from John Masters.
[3988.68 → 3994.20] On the Metal is brought to you by the Oxide Computer Company, where we're going to try
[3994.20 → 3998.96] a new feature, shamelessly ripped off of Reply All's Yes, Yes, No, where our boss, Steve
[3998.96 → 4001.58] Tuck, brings us a tweet he does not understand.
[4002.06 → 4003.36] And Jess and I try to explain it to him.
[4003.40 → 4004.10] Steve, do you have a tweet?
[4004.76 → 4005.46] I sure do.
[4005.60 → 4006.00] Go for it.
[4006.00 → 4012.22] The tweet in question, UEFI reboot network stack engaged the onboard nick in such a way
[4012.22 → 4017.06] that it would write back DMA to particular physical memory pages sometime after control
[4017.06 → 4018.24] was passed to the bootloader.
[4018.36 → 4021.80] Corruption would occur somewhere in the user parts of the RAM disk.
[4022.58 → 4023.98] No idea.
[4024.24 → 4024.84] No idea.
[4024.94 → 4025.78] Jess, do you understand this tweet?
[4026.44 → 4032.74] So I understand definitely the part about the UEFI reboot networking stack, but the part
[4032.74 → 4034.38] about DMA is in question marks.
[4034.38 → 4037.62] So it's like, I guess you're not really sure where that's going.
[4037.62 → 4038.94] You're overthinking it.
[4039.06 → 4040.00] I understand this tweet.
[4040.32 → 4042.20] Running on-prem is painful.
[4042.34 → 4045.14] This is dealing with an awful, awful firmware bug.
[4045.30 → 4050.56] Firmware has overwritten part of the operating system in a way that is extremely painful to
[4050.56 → 4050.84] debug.
[4051.10 → 4052.22] So who do you go to in that case?
[4052.32 → 4053.20] Who do you go to?
[4053.28 → 4055.30] You definitely strangle one of your vendors.
[4055.70 → 4056.58] You strangle one of your vendors.
[4056.68 → 4061.44] And unfortunately, your vendor is a PC vendor because all the existing computer companies
[4061.44 → 4063.74] are selling personal computers.
[4063.74 → 4066.14] What we need is a new computer company.
[4066.30 → 4070.26] So this is just saying I'm in intense pain trying to run systems on-premises.
[4070.42 → 4071.60] That's exactly what it's saying.
[4071.68 → 4074.08] Steve, what can someone do if they're in intense pain running on-premises?
[4074.34 → 4077.94] Well, if someone is running in intense pain on-premises, what they should do is go over
[4077.94 → 4082.50] to oxide. Computer to learn a little bit more about how we are going to take that pain away.
[4082.68 → 4084.40] Help is on the way.
[4084.66 → 4086.10] Join us at oxide.computer.
[4086.28 → 4087.42] You are not alone.
[4087.48 → 4088.04] All right.
[4088.04 → 4092.08] All right.
[4092.10 → 4092.56] We're back.
[4092.66 → 4094.58] John, you were just telling us that we've all got to run Windows.
[4094.80 → 4097.84] It just feels like such a terrible existence.
[4098.14 → 4100.54] Cor boot is now supporting the K-Exec of Windows.
[4101.88 → 4102.28] She's right.
[4102.44 → 4102.86] Wait a minute.
[4104.44 → 4104.68] UEFI.
[4105.48 → 4105.98] She's right.
[4105.98 → 4109.60] I really thought that Jess was going to come in and assail this idea that everything's
[4109.60 → 4111.60] going to run Windows, but actually she's pointing out that you do it via Cor boot.
[4111.70 → 4112.04] Well, all right.
[4112.06 → 4112.62] That's okay.
[4112.96 → 4113.08] Yeah.
[4113.32 → 4115.28] Windows has changed.
[4115.42 → 4120.00] I mean, until Windows 10, I had not run Windows since 1995.
[4121.08 → 4121.40] Right?
[4121.58 → 4123.18] That was my last Windows install.
[4123.38 → 4124.48] It was Windows 95.
[4124.66 → 4125.12] Yes, go on.
[4125.20 → 4125.96] That was a good OS.
[4126.04 → 4126.84] It was a good OS.
[4126.84 → 4130.56] I installed it on floppy disks and it worked.
[4132.00 → 4132.94] Actually, it didn't work.
[4133.00 → 4134.88] I feel that Bill Gates robbed me of my childhood.
[4134.88 → 4136.32] I really do believe this.
[4136.48 → 4140.56] I did not know that an MMU existed until I got to college.
[4140.66 → 4141.26] I did not know that.
[4141.34 → 4146.66] I mean, obviously from invitation to GL1, I just felt that computers would spontaneously
[4146.66 → 4147.16] reset.
[4147.66 → 4148.60] They still do that.
[4148.82 → 4151.08] They do, but they used to do it all the time.
[4151.36 → 4155.14] I mean, in the DOS days and the Windows 3.1 days, they used to do it all the time because
[4155.14 → 4155.72] there was no...
[4155.72 → 4160.08] I mean, it was an act of gross negligence that we actually had memory protection in the
[4160.08 → 4161.96] part that no one was using.
[4162.14 → 4164.16] And well, until recently, you can extend that.
[4164.16 → 4168.76] So, you know, you have memory management units and processors to protect memory.
[4168.94 → 4171.56] But for a very long time, you did not have that on the IO side.
[4171.78 → 4174.38] So you did not have full IO MMU isolation.
[4174.78 → 4179.26] And we have these attacks like, you know, I plug this malicious device into your laptop.
[4179.80 → 4183.94] And oh, because you're channelling something over...
[4183.94 → 4186.88] It looks like USB, but actually it's not, right?
[4187.32 → 4190.18] I can perform, you know, DMA attacks and so on.
[4190.24 → 4194.96] And, you know, famously, various operating systems have embraced IO and Muse everywhere
[4194.96 → 4195.48] and so on.
[4195.50 → 4197.80] So this stuff has continued, by the way, for decades.
[4197.98 → 4198.42] Yeah, fair.
[4198.42 → 4205.18] I remember installing Windows 95 on floppy disks, fewer than my first Linux install because
[4205.18 → 4207.72] my first Linux install was 200 floppies, my friend.
[4208.02 → 4208.48] That was...
[4208.48 → 4209.08] Whoa.
[4209.46 → 4210.58] Slackware 96.
[4211.22 → 4213.58] I have a Linux box over there.
[4213.58 → 4216.30] That's a lot of floppies.
[4216.96 → 4218.04] That's got floppies in it?
[4218.30 → 4218.78] It was two weeks.
[4218.78 → 4219.94] I think there's a CD in there.
[4220.34 → 4221.78] It was two weeks to download that.
[4222.14 → 4222.34] Wow.
[4222.34 → 4224.48] I had high-speed access once a week.
[4224.62 → 4230.96] So I downloaded it and I took all these disks home in this little briefcase and then
[4230.96 → 4235.82] discovered this X, whatever, you know, because Slackware had all these different letter and
[4235.82 → 4237.08] then number combinations.
[4237.64 → 4241.10] And I get very far through the installation and then the disk doesn't work.
[4241.10 → 4243.74] And you're like, oh, man, it's going to be a whole week, you know?
[4244.18 → 4244.34] Right, right.
[4244.34 → 4246.84] And at that point, you know, you can't ask anyone for...
[4246.84 → 4250.46] This is the point in my life where I would...
[4250.46 → 4254.74] My computer would be powered off uncleanly, and it would say something about needing to
[4254.74 → 4259.12] run FSCK and nodes and other scary-looking words.
[4259.46 → 4261.28] And we had no general file systems.
[4261.68 → 4263.54] And so I would reinstall my operating system.
[4263.90 → 4266.96] I would reinstall my OS because I had no idea what the heck this meant, right?
[4266.98 → 4269.22] I hadn't shut it down cleanly and bad things had happened.
[4269.22 → 4274.36] And you couldn't ask anyone because there was no one to just, you know, ask on a mailing
[4274.36 → 4277.64] list or, you know, Facebook chat or whatever it is now, you know?
[4278.00 → 4278.44] Ah, yes.
[4278.50 → 4281.34] Facebook Messenger, my first source for any technical question.
[4282.22 → 4286.50] There is a Linux patches Facebook group where people, you know...
[4286.50 → 4288.42] That's got to be run by bots, don't you think?
[4288.62 → 4290.06] It's run by...
[4290.06 → 4290.58] Who am I thinking of?
[4290.62 → 4291.22] Chris...
[4291.22 → 4292.06] What's his last name?
[4292.12 → 4292.38] Facebook.
[4293.46 → 4294.80] Oh, shit.
[4295.16 → 4296.18] Yes, exactly.
[4296.34 → 4296.86] Chris L. Shit.
[4296.86 → 4298.00] Yes, yes.
[4298.20 → 4300.56] We will both think of his name in a minute, but you know who I mean.
[4300.68 → 4301.24] Yeah, I know, totally.
[4301.50 → 4305.14] I have a thread with him about C Group something and I can't remember his last name.
[4306.02 → 4309.16] But, yeah, I like that idea, though.
[4309.22 → 4311.26] It's like, he's like, well, that's where the modern generation...
[4311.26 → 4312.40] I mean, he works with Mason, right?
[4312.60 → 4312.76] Yeah.
[4312.84 → 4312.98] Yeah.
[4313.18 → 4314.00] And like...
[4314.00 → 4314.98] Chris Mason, the Butteriest guy.
[4315.26 → 4316.34] I can help you out on that one.
[4316.48 → 4316.76] Yeah.
[4317.36 → 4318.02] Well, you didn't.
[4318.06 → 4318.50] You didn't.
[4318.60 → 4318.78] Yeah.
[4319.14 → 4319.70] Thank you.
[4319.80 → 4320.22] That's true.
[4320.64 → 4321.66] You were not helping us.
[4321.66 → 4323.16] Remonstrantly, I actually did not help you out.
[4323.52 → 4323.84] Yeah.
[4323.98 → 4324.18] All right.
[4324.18 → 4324.32] Fair.
[4324.32 → 4325.62] So, Windows...
[4325.62 → 4325.82] Right.
[4325.90 → 4328.30] I'm going to make that comment about Windows, right?
[4328.36 → 4331.32] So, I installed Windows 95 on floppy disks.
[4331.48 → 4333.60] It was not great, but I didn't hate Windows 95.
[4333.82 → 4336.12] I didn't use Windows for several decades after that.
[4336.18 → 4336.36] Right.
[4336.54 → 4336.78] Right?
[4336.88 → 4338.70] For good or bad or whatever reasons.
[4338.84 → 4339.64] I was...
[4339.64 → 4341.48] I mean, I was a true zealot, right?
[4341.50 → 4346.88] I used to run the virtual rich instalment on my computers, and it would tell me that I
[4346.88 → 4349.52] was running one piece of, you know, non-free software.
[4349.64 → 4351.98] I was running the Oracle Java...
[4351.98 → 4353.10] The Sun Java Runtime.
[4353.26 → 4353.50] Right.
[4353.50 → 4354.88] And I was a bad human being.
[4354.96 → 4355.90] And I felt bad.
[4356.48 → 4361.34] I really felt bad for running, like, one piece of, you know, non-free software.
[4361.52 → 4361.68] I'm like...
[4361.68 → 4364.38] Says, like, the UEFI jihadist.
[4364.50 → 4365.62] I just felt like, this is so...
[4365.62 → 4366.44] But then I got better, right?
[4366.50 → 4367.08] Like, over time.
[4367.08 → 4367.42] I got better.
[4367.60 → 4368.48] I can go...
[4368.48 → 4370.08] I can't understand this at all.
[4370.08 → 4371.08] But later on, I'm like, okay.
[4371.30 → 4372.00] I'm like...
[4372.00 → 4374.74] I'm like, so...
[4374.74 → 4376.24] Everything must be...
[4376.24 → 4379.80] Not just open source, but must be, like, free software all the way, baby.
[4379.90 → 4380.78] Like, no...
[4380.78 → 4382.12] You know, nothing else.
[4382.12 → 4385.14] And I'm still very fond of that model.
[4385.16 → 4385.68] Yeah, I think so.
[4385.74 → 4386.66] I really am.
[4387.48 → 4387.84] But I got...
[4387.84 → 4388.44] Open source firmware.
[4388.58 → 4388.86] Come on.
[4389.08 → 4389.66] Now's the time.
[4389.76 → 4390.54] I agree.
[4390.74 → 4394.12] But I got to a point of a bit more comfort with...
[4394.12 → 4398.10] I'm never going to run Windows on my, you know, primary desktop or whatever.
[4398.10 → 4402.26] But I got a bit more comfortable with the idea that, okay, I guess proprietary software exists.
[4402.98 → 4403.50] I don't know.
[4403.62 → 4405.96] I feel like the pigs are walking on their hind feet on this one.
[4406.04 → 4410.74] I feel that, like, you're such an idealist and now you...
[4410.74 → 4411.42] It's been crushed out of me.
[4411.42 → 4412.36] It's been crushed out of you.
[4412.44 → 4413.82] And now you're all about proprietary firmware.
[4414.46 → 4415.46] Oh, it is...
[4415.46 → 4416.84] Now is the time for open source firmware.
[4417.40 → 4417.74] I agree.
[4418.26 → 4418.58] Okay.
[4418.58 → 4427.44] So in my new role, running software at a processor startup, one of the things that we are going to do is have fully open source firmware.
[4427.62 → 4429.88] So are you joining Microsoft's Open UEFI?
[4430.06 → 4431.08] What do they even call that thing?
[4431.14 → 4431.80] The Open UEFI?
[4432.32 → 4433.22] Oh, they have a project.
[4433.32 → 4434.72] Well, we're just going to work on...
[4434.72 → 4435.10] K or something.
[4435.12 → 4435.62] Yeah, right.
[4435.70 → 4436.14] Yeah, yeah, yeah.
[4436.24 → 4437.70] We're going to work on Travancore.
[4438.04 → 4438.32] Okay.
[4438.48 → 4438.70] Right?
[4438.92 → 4439.28] Directly.
[4439.98 → 4443.92] And we will just contribute every change directly upstream into the Travancore project.
[4444.06 → 4444.26] Okay.
[4444.36 → 4444.90] So that's...
[4444.90 → 4445.10] All right.
[4445.32 → 4446.10] That's open source firmware.
[4446.10 → 4447.92] It happens to be UEFI.
[4449.48 → 4449.88] Yeah.
[4450.12 → 4450.86] But it's open source.
[4450.86 → 4451.42] It is open source.
[4451.70 → 4452.52] That's important, though.
[4452.64 → 4453.22] I mean, it is important.
[4453.32 → 4455.12] I'll give you another example of the UEFI because I know...
[4455.12 → 4455.28] All right.
[4455.28 → 4455.94] Everyone hates it.
[4456.56 → 4458.54] Boot, which is a popular embedded bootloader.
[4458.56 → 4458.76] Yes.
[4458.84 → 4458.96] Right?
[4459.22 → 4460.22] Somebody...
[4460.22 → 4461.92] I think it was Alex Graff actually started this.
[4462.04 → 4465.04] But somebody wrote a UEFI wrapper.
[4465.62 → 4465.86] Right?
[4465.94 → 4472.10] So you can have Boot complying with the UEFI specs and not run any of that horrible stuff.
[4472.40 → 4472.50] Right.
[4472.50 → 4474.08] I don't hate that.
[4474.08 → 4477.96] It boots everything the way that I want it to and doesn't touch Travancore.
[4478.08 → 4478.28] Great.
[4478.70 → 4478.98] Right.
[4479.70 → 4480.62] You welcome that.
[4481.02 → 4481.26] Yeah.
[4481.32 → 4482.20] It's fun for you.
[4482.34 → 4482.54] Yeah.
[4482.78 → 4486.70] Something that gets UEFI out of the way effectively by pretending to be UEFI.
[4487.72 → 4488.10] I guess...
[4488.10 → 4488.86] I guess, I mean, it is...
[4488.86 → 4489.42] I mean, I don't know.
[4489.66 → 4491.22] They just got it working on the Raspberry Pi.
[4491.38 → 4496.52] You can now run a very boring ARM server looking config on your Raspberry Pi.
[4496.68 → 4498.12] I mean, I don't know why you would want to...
[4498.12 → 4500.34] Well, I can see why developers might want to do that.
[4500.50 → 4501.04] It's kind of fun.
[4501.04 → 4501.16] Yeah.
[4501.42 → 4502.14] So, yeah.
[4502.18 → 4503.04] Talk about the...
[4503.84 → 4505.06] So you're looking...
[4505.06 → 4508.46] Embracing open source firmware at the microprocessor startup.
[4508.56 → 4509.38] Very exciting, by the way.
[4509.78 → 4510.02] Thank you.
[4510.14 → 4513.02] We think that we like crazy companies around here.
[4513.24 → 4514.88] So we like your crazy company.
[4515.96 → 4518.36] And how much of the software stack are you guys going to be developing?
[4518.50 → 4519.10] How...
[4519.10 → 4521.42] So the plan is...
[4521.42 → 4522.00] And I...
[4522.00 → 4524.00] You know, we haven't said what the architecture is.
[4524.18 → 4527.90] People have guessed based on the things that I've done in the past what it might be or might not be.
[4528.00 → 4528.54] You never know.
[4528.94 → 4536.60] But the plan is to build a very high performance server class processor that is compliant with my favourite word, which is boring.
[4537.30 → 4537.56] Right?
[4537.68 → 4539.32] Like marketing are...
[4539.32 → 4541.20] I think your favourite words are rampantly speculative.
[4541.20 → 4543.32] Are those your favourite words?
[4543.32 → 4544.94] Yeah, but I love the word boring as well.
[4545.02 → 4549.12] Like our head of marketing, John Carlisle, he's a great guy.
[4549.46 → 4551.70] I'm sure he would say, please don't use the word boring.
[4551.88 → 4552.06] Right?
[4552.16 → 4554.40] And I won't write that down.
[4554.54 → 4555.38] But it fundamentally...
[4555.38 → 4559.16] You just have the hope that he had a stroke sometime while listening to this and hasn't even made it this far into the podcast.
[4559.20 → 4560.58] Hopefully you're not listening this far, John.
[4560.70 → 4564.50] So the thing is, you know, I think computers should be boring.
[4564.50 → 4567.42] I think you should basically turn on your machine, right?
[4567.72 → 4568.32] Unpack it.
[4568.78 → 4571.44] And it should look like a normal enough computer, right?
[4571.48 → 4573.60] It should have a serial console if that's what you want.
[4573.68 → 4575.06] It should have these things.
[4575.52 → 4580.20] You should be able to plug it in and do a network install and have a non-experience.
[4580.28 → 4581.72] It should just work, right?
[4582.14 → 4583.84] It's very complicated to make it just work.
[4583.94 → 4584.16] Yes.
[4584.32 → 4585.88] It is very complicated to make it just work.
[4585.94 → 4590.28] And I know some people that are, you know, quite good at making things just work out of the box.
[4590.46 → 4593.18] And, you know, I think he wants my computer.
[4593.32 → 4594.00] Please buy one now.
[4594.00 → 4596.64] It's Oxide.computer.
[4596.88 → 4597.38] There you go.
[4597.82 → 4599.76] No, we're not even at an Droll yet.
[4599.84 → 4600.42] That's pretty good.
[4602.06 → 4605.16] But I think that should extend to the other components in the machine as well.
[4605.24 → 4606.32] So the microprocessor, right?
[4606.34 → 4613.64] We think we can make really, really fast, kick-ass processors that blow everybody out of the water in terms of single-thread performance.
[4613.70 → 4614.82] Because that's what people want.
[4614.88 → 4616.04] Coming back to our point earlier, right?
[4616.04 → 4624.60] Like, you can come up with some alternative, and you can say, please don't use your existing, you know, x86 server that you've got.
[4624.96 → 4628.54] Because I would like you to take your workload and do this thing that you're not going to do.
[4628.92 → 4633.86] Or you can say, I'm going to give you something that is superfast, much faster than what you have today.
[4633.86 → 4639.48] You don't have to do very much to move your workload onto it.
[4639.56 → 4640.84] So we're very keen on single-thread.
[4641.14 → 4644.40] And then we're very keen on basically embracing open source.
[4644.50 → 4645.90] So I came from an open source background.
[4645.90 → 4652.52] And is the end of Moore's Law, do you view that as an opportunity to make more architectural improvements?
[4653.02 → 4654.30] Is Moore's Law ending?
[4655.14 → 4655.48] Yes.
[4655.64 → 4656.00] All right, good.
[4656.02 → 4658.82] I was just making sure that Intel didn't place something into your brain.
[4659.50 → 4663.24] Well, Moore's Law was an observation about scaling, right?
[4663.58 → 4668.80] But regardless of whether they dig out of their manufacturing woes, right?
[4668.82 → 4670.52] Let's say that they bring the scaling back.
[4670.82 → 4673.08] The economic piece is the issue.
[4673.08 → 4679.58] Can you continue to manufacture at increasingly smaller geometries?
[4679.74 → 4683.12] And can you do that in a way that doesn't blow up your cost?
[4683.32 → 4683.58] Yes.
[4683.80 → 4684.02] Right?
[4684.18 → 4684.36] No.
[4684.66 → 4684.76] Yeah.
[4684.78 → 4688.08] And if you actually go back and read Gordon Moore's original paper, which is amazing,
[4689.10 → 4692.08] Moore's Law was not coined by Moore in that paper.
[4692.16 → 4693.70] It's coined by Carl from me 10 years later.
[4693.96 → 4696.52] And that paper is as much an economic paper as it is anything.
[4696.70 → 4696.94] Right.
[4697.30 → 4701.16] And an economic observation about the transistors per dollar.
[4701.60 → 4702.00] Right.
[4702.00 → 4706.38] And that's what we have been observing up until recently.
[4706.52 → 4710.92] Up until I would say up until whatever, up until 14 nanometers, 22 nanometers.
[4711.18 → 4716.44] But the, you know, I'm very troubled by the lie of nanometres.
[4716.72 → 4717.74] Does this bother you at all?
[4718.06 → 4718.30] Yeah.
[4719.22 → 4722.74] Because, you know, Intel had announced like, oh yeah, we're going from, you know,
[4722.76 → 4724.20] three nanometre, and we've got a roadmap.
[4724.50 → 4724.88] 1.4.
[4724.88 → 4727.16] To 1.4 nanometre to 0.8.
[4727.20 → 4731.32] It's like, when are we going to admit that that nanometre is a lie?
[4732.16 → 4733.30] These are marketing numbers.
[4733.40 → 4734.90] They are marketing numbers, but that's not right.
[4735.06 → 4735.32] No.
[4735.76 → 4735.96] Right?
[4736.02 → 4736.72] That's not right.
[4736.80 → 4740.22] But it's the same way that, you know, if you sell a computer to someone, they're going
[4740.22 → 4742.44] to say, oh, this has got eight cores and not four cores.
[4742.50 → 4746.42] And they don't know, you know, what the difference is in terms of performance between those.
[4746.42 → 4747.38] But eight is better than four.
[4747.38 → 4748.78] I feel this is a bigger lie.
[4748.88 → 4755.38] I feel this is a bigger lie because the industry kind of keeps it a bit of a secret that the
[4755.38 → 4759.90] actual number itself, there is nothing that is being measured.
[4760.22 → 4763.50] Well, one geometry somewhere vaguely resembles that number.
[4763.76 → 4764.04] Right.
[4764.18 → 4767.22] But the actual width of the gates, the actual structures are far bigger.
[4767.62 → 4767.98] It's far bigger.
[4768.10 → 4768.42] Yeah, yeah.
[4768.68 → 4768.82] Yeah.
[4769.22 → 4771.82] It's like, this would be the density.
[4771.82 → 4778.48] This would be the this is the equivalent gate width if we had kept a structure from
[4778.48 → 4780.22] whatever, five years ago, whatever.
[4780.38 → 4783.48] I mean, it's, what is it based on?
[4783.54 → 4787.56] It's based off of what, 22 nanometres, something like that, where were they kind of frozen times?
[4787.76 → 4793.06] So there was, there used to be, I forget the exact acronym now, but there used to be the
[4793.06 → 4797.86] International Roadmap for Semiconductors, ISAR, I think it was.
[4798.96 → 4800.46] Always get those letters the wrong way around.
[4800.46 → 4804.56] But there was, there used to be an established roadmap that would give you the process scaling
[4804.56 → 4806.36] forecast for the industry.
[4807.18 → 4812.38] And what, what happened was a few years ago, they realized that that didn't make any sense
[4812.38 → 4814.24] anymore, and they've replaced it with something else.
[4814.24 → 4815.62] And now that's being debated again.
[4815.62 → 4820.16] I mean, fundamentally we're hitting, we're hitting a point in time where everything as
[4820.16 → 4821.46] we used to know it is kind of.
[4821.76 → 4823.04] We are going to hit density limits.
[4823.26 → 4824.26] However you phrase it.
[4824.40 → 4825.68] We're going to hit economic limits.
[4826.04 → 4826.30] Economic limits.
[4826.30 → 4826.50] Right.
[4826.50 → 4833.98] I mean, but by the way, on your point about geometry, I saw a great fake ad yesterday,
[4833.98 → 4840.80] which had an Intel CPU and an AMD CPU, and it had a seven nanometre and 14 nanometers.
[4840.80 → 4843.32] And it said, you know, buy the, buy the 14 nanometre.
[4843.32 → 4844.46] Because it's twice the nanometres.
[4844.66 → 4844.90] Right.
[4844.98 → 4845.30] There you go.
[4845.30 → 4846.20] I was like, that's great.
[4846.28 → 4847.14] That's a perfect ad.
[4847.20 → 4847.76] Please make that.
[4847.84 → 4848.52] That would be hilarious.
[4849.38 → 4852.34] But I don't know if it just feels like it's, the lie seems annoying.
[4852.46 → 4853.60] We know that Moore's law is ending.
[4853.88 → 4854.12] Right.
[4854.12 → 4855.50] And you view that, I mean, that's.
[4855.68 → 4856.88] I think it's a fabulous opportunity.
[4857.02 → 4862.42] I think, I think if Intel had continued to, well, firstly, I think Intel could always be
[4862.42 → 4865.16] challenged by the right, the right competition.
[4866.08 → 4872.36] But the problem historically was that they had pretty good architecture, but they also had
[4872.36 → 4873.44] amazing manufacturing.
[4873.90 → 4874.30] Yeah.
[4874.34 → 4878.40] And they were, they were very good on process, and they were very good on, on execution.
[4878.52 → 4881.54] I mean, the speculative execution is a big part of the Intel story.
[4881.92 → 4882.14] Yeah.
[4882.14 → 4885.10] They were, they were better at speculative execution than anyone else.
[4885.22 → 4892.08] They did a lot of, so there's a guy, total tangent called Andy Glue, who is known as
[4892.08 → 4893.16] crazy glue in the industry.
[4895.12 → 4895.84] And hi Andy.
[4895.84 → 4897.32] Why have I never heard of crazy glue?
[4897.62 → 4901.22] And Andy works at, Andy works at Sci-5 these days, but he's worked everywhere in the industry.
[4901.30 → 4902.48] He's a really smart guy.
[4902.56 → 4902.80] Okay.
[4902.96 → 4906.24] But when you go and look at some of the original patents or things that, you know, in the
[4906.24 → 4910.26] early nineties, things that all have expired now, but some of the early speculative execution
[4910.26 → 4912.38] patents that Intel had, like his name's all over them.
[4912.40 → 4912.96] There's a few of them.
[4913.22 → 4916.56] They're, they're, they're like this guy, he graduates from college, and then he has this
[4916.56 → 4920.06] prolific couple of years of his life where he's coming up with one crazy idea.
[4920.24 → 4921.36] That's where he gets his name.
[4921.60 → 4921.92] Crazy glue.
[4921.94 → 4924.28] But he comes up with one crazy idea after another.
[4924.44 → 4925.78] The halcyon days of crazy glue.
[4925.90 → 4926.10] Okay.
[4926.10 → 4930.24] And, and, and the thing is that a lot of the stuff dates back to, you know, the early
[4930.24 → 4934.64] and mid-nineties, and they've continued to innovate, but you know, they, they had this
[4934.64 → 4939.68] fabulous period where they came up with a lot of these really advanced concepts that
[4939.68 → 4940.60] they then productized.
[4940.60 → 4944.08] But that's not even the reason I think why they were where they were.
[4944.14 → 4944.96] It was the manufacturing.
[4945.28 → 4952.12] And then on process, nobody on process and nobody else had a manufacturing that could even
[4952.12 → 4953.12] remotely challenge them.
[4953.12 → 4955.30] Are we going to get a book on Cannon Lake?
[4956.24 → 4957.68] The disaster of Cannon Lake.
[4958.20 → 4960.06] It's got to be like conflagration.
[4960.06 → 4960.26] Where is it?
[4960.38 → 4962.16] It's like conflagration at Cannon Lake.
[4962.26 → 4963.22] It's like a Hardy Boys mystery.
[4963.46 → 4964.40] Where is Cannon Lake?
[4964.58 → 4965.62] Where is Cannon Lake?
[4965.76 → 4966.36] The missing Cannon Lake.
[4966.42 → 4967.84] The mysterious absence of Cannon Lake.
[4967.88 → 4969.02] The mysterious absence of Cannon Lake.
[4969.26 → 4974.56] But it's like, because that is clearly a wall-to-wall disaster inside of Intel.
[4974.86 → 4975.58] I'm sure it is.
[4975.66 → 4979.96] I mean, there are very few companies that could weather the absence of a complete generation
[4979.96 → 4982.80] of their product and still, you know, kind of sort of be okay.
[4983.12 → 4983.34] Right?
[4983.46 → 4984.12] Kind of, sort of.
[4984.28 → 4987.92] I mean, the big problem we have as an industry even goes further than that.
[4987.92 → 4993.66] Because of the fundamental limitations on how many places actually, you know, someone
[4993.66 → 4997.38] can go to for third-party jabbing, third-party foundry service.
[4997.56 → 4997.64] Yeah.
[4997.84 → 5002.44] It basically means that, I mean, someone did these numbers, and they said, look, if AMD
[5002.44 → 5009.50] sold every processor that they could possibly push through TSMC, Intel would still have
[5009.50 → 5012.08] a very large majority of the market.
[5012.26 → 5013.00] Just based on fab.
[5013.14 → 5014.52] Just based on fab capacity.
[5014.62 → 5014.72] Yeah.
[5015.34 → 5015.60] Right.
[5015.78 → 5016.16] But, okay.
[5016.22 → 5018.56] So, I think that with the end of Moore's Law, that's going to change.
[5019.02 → 5020.44] So, there's something called the Wright's Law.
[5020.82 → 5024.74] This guy, Theodore Wright, observed that as we build more aircraft, they get cheaper.
[5025.00 → 5025.22] Yep.
[5025.22 → 5029.24] And I wonder if it actually has been Wright's Law all along.
[5029.64 → 5036.52] And as we more and more, as we coalesce on the same node, whether that's 7 nanometre
[5036.52 → 5040.32] or 5 nanometers or 3 nanometre node, we'll end up with more and more fabs.
[5040.32 → 5043.10] Because now that 7 nanometre fab is not obviated.
[5043.28 → 5047.82] That's actually, that can continue to make leading-edge silicon in perpetuity effectively.
[5048.42 → 5049.08] I hope that happens.
[5049.24 → 5052.34] I mean, what I've been hoping is that we do see a slowing.
[5052.76 → 5057.80] Because what's happened so far is every time you've gone from one node to the next, somebody's
[5057.80 → 5058.32] dropped out.
[5058.62 → 5059.54] Every time manufacturing.
[5059.94 → 5061.82] So, you know, I'll be careful using the words like node.
[5061.96 → 5063.66] I mean, people probably can look this up, I guess.
[5063.66 → 5068.64] But like, every time a generational improvement has happened in manufacturing, one of the companies
[5068.64 → 5071.00] has said, oh, too rich for our blood.
[5071.18 → 5071.66] Global foundries.
[5071.66 → 5072.24] Global foundries.
[5072.36 → 5073.12] Being the most recent one, yeah.
[5073.14 → 5073.28] Right.
[5073.32 → 5076.58] They said, nope, we're not going to continue this because it's crazy.
[5076.58 → 5078.48] We just can't keep the economics going.
[5078.94 → 5080.84] But every time this happens.
[5081.18 → 5082.94] So, I'm sort of hoping-
[5082.94 → 5084.74] Hats off to TSMC for keeping the party going.
[5084.86 → 5085.00] Yeah.
[5085.18 → 5086.58] TSMC is like, pour me another drink.
[5086.70 → 5086.92] Yeah.
[5088.02 → 5091.70] I mean, they're global foundries that had to go home.
[5091.86 → 5092.12] Not me.
[5092.28 → 5094.02] Not TSMC.
[5094.32 → 5096.86] But I think, you know, there's now three, right?
[5096.92 → 5098.92] At some point there'll be two and then there'll be one.
[5098.92 → 5104.76] And what I'm hoping is it, selfishly partly, what I'm hoping is the one remaining isn't Intel
[5104.76 → 5106.24] and everyone else is screwed, right?
[5106.24 → 5110.82] What I'm hoping happens is that we reach a point, this kind of equilibrium where we say,
[5111.32 → 5115.36] you can continue down this path, but the cost increases so much.
[5115.94 → 5121.24] And what you get back for that decreases to a point where people pursue other ways of innovating,
[5121.64 → 5121.78] right?
[5121.84 → 5127.96] Maybe more architectural innovation, maybe, you know, other, because it's been over the
[5127.96 → 5133.36] years so easy, not for the manufacturing folks, but for everybody else to just say,
[5133.36 → 5136.44] oh, next generation, it'll get faster because they'll improve manufacturing, right?
[5136.82 → 5137.70] Or it'll get denser.
[5137.82 → 5141.90] I mean, we did our scaling in a while ago, but it's gotten denser.
[5141.90 → 5142.18] Mm-hmm.
[5142.26 → 5148.10] So what will happen is over time, hopefully, you will see people focusing more on architectural
[5148.10 → 5152.08] innovation and then having equal access to perfect manufacturing.
[5152.60 → 5153.48] And I agree.
[5153.60 → 5156.46] Hopefully, that will drive down the cost, and it will lead to more interesting designs,
[5156.56 → 5158.06] hopefully ones that are much lower power.
[5158.70 → 5164.38] You know, our focus in just plugging Nivea a little bit, our focus is high performance
[5164.38 → 5165.32] single thread.
[5165.52 → 5165.70] Yeah.
[5165.84 → 5169.54] Perfect multicore and doing it at very low energy.
[5169.66 → 5171.38] And hyper-threading as far as the eye can see.
[5171.58 → 5172.64] And of course, oh, yeah.
[5173.04 → 5173.18] Yeah.
[5173.34 → 5173.70] Absolutely.
[5174.34 → 5175.26] 16-way SMT.
[5175.98 → 5176.34] Yeah.
[5176.90 → 5180.64] And so what do you think about, I mean, because we're going to, the end of Moore's Law also
[5180.64 → 5182.44] has consequences for DRAM, obviously.
[5182.78 → 5182.98] Right.
[5183.06 → 5185.20] I mean, DRAM drove Moore's Law for many, many years.
[5185.32 → 5185.40] Yeah.
[5185.80 → 5187.58] Intel may go back to being a memory manufacturer.
[5188.10 → 5190.74] Well, and so what do you think about PCM, about phase change memory?
[5190.74 → 5195.54] What's your, I mean, I feel like I've been waiting my entire career for-
[5195.54 → 5196.02] Practical.
[5196.38 → 5200.38] For non-vol, for DRAM speeds with non-volatility.
[5200.66 → 5200.86] Yeah.
[5201.42 → 5203.36] And have you heard of a company called Lantern?
[5203.82 → 5204.14] Yes.
[5204.28 → 5205.50] I may have heard of them.
[5205.60 → 5205.72] Yes.
[5205.78 → 5206.82] Carbon nanotube-based memory?
[5206.82 → 5207.04] Right.
[5207.14 → 5207.28] Yeah.
[5207.38 → 5208.08] They broke my heart.
[5208.20 → 5209.32] They're still around.
[5209.42 → 5209.92] They're still trying.
[5210.30 → 5210.62] Years.
[5211.10 → 5211.48] Years.
[5211.64 → 5211.90] Years.
[5212.06 → 5216.10] They've given hot chips presentation after hot chips presentation and still waiting to
[5216.10 → 5216.26] see.
[5216.36 → 5220.30] I mean, if you were sitting on something that was so transformative that it would upend the
[5220.30 → 5225.20] entire industry, maybe you'd want to sell it or put it somewhere or, you know, have it
[5225.20 → 5225.26] in your-
[5225.26 → 5226.14] You know, I get the sense that-
[5226.14 → 5226.96] Are we talking about Magic Leap?
[5227.18 → 5227.44] No.
[5227.60 → 5228.58] No, we're talking about-
[5228.58 → 5229.66] Sorry, you're just joining us.
[5229.66 → 5230.20] That's a good one too.
[5230.40 → 5231.64] No, but no, this is actually real.
[5232.26 → 5236.22] It's carbon nanotube-based memory, and it is, it's non-volatile.
[5236.22 → 5238.80] It's incredibly dense and incredibly fast on the bench.
[5239.32 → 5242.84] On the bench and not shipping in anything that I've seen.
[5242.98 → 5246.70] I mean, again, if this was such a magical thing, one would assume it would be everywhere.
[5247.00 → 5249.60] But do you think, are we, can magic happen?
[5249.60 → 5250.96] Are we going to see-
[5250.96 → 5251.78] Yes, magic is possible.
[5251.84 → 5252.60] Magic is possible.
[5252.70 → 5253.36] The Easter Bunny is real.
[5253.58 → 5254.04] Thank God.
[5254.06 → 5254.98] Santa Claus is real.
[5255.58 → 5259.26] Are we going to get phase change memory under the Christmas tree this year?
[5259.76 → 5260.30] Not this year.
[5260.60 → 5261.30] Yeah, not this year.
[5261.60 → 5266.90] I can confidently predict that at this point at the end of the year that that will not
[5266.90 → 5267.14] happen.
[5267.60 → 5268.42] Yes, it will happen.
[5268.62 → 5269.44] Do you think it'll be phase change?
[5269.56 → 5270.32] Do you think it'll be-
[5270.32 → 5272.98] Unclear where that goes.
[5272.98 → 5277.42] But I do, I do think that the, you know, look, the, the, one of the key things that
[5277.42 → 5282.08] has limited, well, not just processors, but has limited us for the past goodness knows
[5282.08 → 5285.98] how many years now is that you have these giant DDR interfaces.
[5286.34 → 5286.78] Yeah.
[5286.92 → 5288.80] That you, that suck a lot of power.
[5289.06 → 5289.32] Yeah.
[5289.32 → 5295.70] And, and they mean that you buy, you know, processors now with, you know, 4,000 pins coming
[5295.70 → 5297.68] off them to give you eight channels of memory.
[5297.92 → 5298.16] Right.
[5298.30 → 5299.26] I mean, that's crazy.
[5300.04 → 5304.00] There's, there's just so many things wrong with the way that we build machines today.
[5304.02 → 5307.72] And then you have to route all of the I mean, 4,000 little pins coming off a chip means
[5307.72 → 5312.82] 4,000 wires go somewhere, which means that these boards are, you know, you guys know this
[5312.82 → 5314.70] better than me, oxide.computer.
[5314.70 → 5318.88] Or, you know, you have to route all these signals somewhere.
[5319.00 → 5319.16] Yeah.
[5319.36 → 5324.80] You, you, you're, you're, you're throwing away so much energy just in, in, in pumping
[5324.80 → 5326.58] bits through memory.
[5326.94 → 5327.36] Yeah.
[5327.48 → 5330.38] And it's incredibly complicated to get all that to work, obviously.
[5330.80 → 5335.30] And so any innovation that happens in the memory, I mean, it, you know, as I said earlier,
[5335.40 → 5336.20] Dick Switz, right?
[5336.34 → 5339.94] He, his point about it's the memory stupid, right?
[5339.94 → 5343.82] Whether that's about performance or that's a statement about economics or energy, it turns
[5343.82 → 5346.14] out that it hits the memory stupid, right?
[5346.18 → 5352.80] Like if we can find ways to optimize that, optimize for cost of memory for, you know,
[5352.88 → 5353.62] disaggregation.
[5353.70 → 5357.64] I mean, there's a lot of interest in the industry in disaggregation and saying, I have some whiz
[5357.64 → 5361.84] bang fancy bus that lets me put all my memory over here and all my compute over here.
[5361.84 → 5365.96] You know, I'm going to channel Jeff Rothschild, a guest on the first On The Metal.
[5366.40 → 5369.22] Jeff, he's like, why are we calling this disaggregation?
[5369.22 → 5371.48] It's aggregation, not disaggregation.
[5372.74 → 5374.00] He's got a point, you know?
[5374.02 → 5377.64] I used to call it nonsense, and I try to be a bit nicer.
[5377.82 → 5378.36] Yeah, exactly.
[5379.28 → 5381.26] But I think there's, I think, you know, the problem-
[5381.26 → 5382.96] But do you think we're going to have aggregation of memory like that?
[5385.16 → 5385.48] No.
[5385.86 → 5389.24] And I think one of the problems is that you have to go from the sort of PowerPoint phase
[5389.24 → 5391.94] to the what's practical in real life phase.
[5391.94 → 5392.06] Right.
[5392.06 → 5397.54] When there was a system that, was it an Aussie or SOAP paper I saw that they were doing this
[5397.54 → 5401.38] kind of disaggregation of memory and showing, it's like, oh, it's only a 3x performance
[5401.38 → 5401.74] head.
[5402.04 → 5403.90] It's like, oh, that's, I mean, it's great.
[5404.10 → 5408.60] I think it's worth considering all things because they're, you know, maybe with the right
[5408.60 → 5411.16] memory hierarchy, we could make that work.
[5411.82 → 5414.52] You know, the jury is still out on what's possible.
[5414.52 → 5419.72] I think there's a lot of people looking at things like HBMs, so very high bandwidth memories
[5419.72 → 5421.38] that you stack on top of your chip.
[5422.04 → 5423.88] And if you look at the number one-
[5423.88 → 5424.86] Where does the heat go?
[5426.96 → 5428.12] Upward and outward, my friend.
[5429.88 → 5432.44] Yes, this can create hotspots.
[5432.82 → 5433.18] Exactly.
[5433.68 → 5434.52] Burning data centres.
[5434.98 → 5436.16] It can create real problems.
[5436.26 → 5440.54] But on the other hand, though, if you look at the number one computer in the green top
[5440.54 → 5443.72] 500, right, which is, I hasten to add, the green top 500.
[5443.90 → 5444.90] It's not top 500 yet.
[5444.92 → 5446.10] It's all slow, terrible machines.
[5446.22 → 5446.54] Well, no.
[5446.76 → 5449.50] So it may also end up being, when it's certified, one of the top-
[5449.72 → 5450.06] Okay.
[5450.10 → 5451.78] 500 as well in the top 10.
[5451.86 → 5452.64] So this is the new Fujitsu.
[5452.64 → 5453.74] It's got to be in our part.
[5453.98 → 5456.20] Yeah, it's the Fujitsu ARM supercomputer.
[5456.20 → 5457.24] Yeah, I'm wrong with that, yeah.
[5457.28 → 5458.20] Yeah, exactly.
[5458.42 → 5459.26] Of course, I was going to get to that.
[5459.30 → 5460.10] Yeah, yeah, yeah, yeah.
[5460.32 → 5464.72] But it's number one in the green top 500, and it uses HBM.
[5464.92 → 5468.74] So you don't have lots of sticks of DDR attached to this thing.
[5469.06 → 5469.20] Yeah.
[5469.46 → 5475.18] But you have the trade-off that you have a fixed amount of memory on the package.
[5475.54 → 5475.78] Right.
[5475.82 → 5476.34] And that's it.
[5476.70 → 5476.92] Right.
[5476.92 → 5477.32] Right.
[5477.32 → 5477.44] Right.
[5477.50 → 5479.66] So if you can fit your workload in that, amazing.
[5480.28 → 5482.22] If you cannot fit your workload in that-
[5482.22 → 5482.86] Very amazing.
[5482.90 → 5484.20] Very amazing very quickly.
[5484.42 → 5484.68] Right.
[5485.04 → 5485.22] Right.
[5485.36 → 5488.40] But imagine if you had that, and you combined it with one of these memory technologies,
[5488.40 → 5490.92] and you actually managed to get this kind of caching.
[5490.92 → 5491.22] That is interesting.
[5491.56 → 5492.12] And it could be interesting.
[5492.34 → 5495.60] I mean, you look at when we pay a price for that expandability.
[5496.60 → 5499.10] A terrible, terrible price around.
[5499.22 → 5499.34] Yeah.
[5499.38 → 5501.08] So yeah, maybe that's interesting.
[5501.08 → 5505.68] I mean, I spent the last couple of years sort of pursuing some of these crazy advanced buses
[5505.68 → 5508.58] that, you know, people look, well, crazy, I don't mean that in a bad way.
[5508.86 → 5513.90] There are things like, you know, Gen Z, which is about letting you put your memory over here.
[5514.08 → 5514.50] And then-
[5514.50 → 5515.56] There's a bus called Gen Z?
[5515.66 → 5516.62] There's a bus called Gen Z.
[5516.68 → 5516.80] Okay.
[5516.84 → 5518.30] But Gen Z, my 15-year-old is Gen Z.
[5518.44 → 5518.64] Yeah.
[5518.98 → 5520.90] Well, this is the bus for the new generation.
[5521.08 → 5522.92] This is like a bus that's on TikTok or something?
[5523.08 → 5524.36] What is this?
[5524.36 → 5527.70] This is like a bus that replies like-
[5527.70 → 5528.42] Well, I'll make a-
[5528.42 → 5534.04] If you make a PCI request to Gen Z, it responds, okay, boomer?
[5534.26 → 5534.40] Yeah.
[5534.52 → 5535.08] They have a Z-bridge.
[5535.28 → 5537.64] And it goes over this.
[5537.76 → 5539.32] I will make a TikTok joke.
[5539.46 → 5541.80] So Intel used to call their manufacturing TikTok.
[5541.80 → 5542.78] Yes, it was TikTok, yes.
[5542.78 → 5546.50] And it became process architecture optimization, which rolls off the tongue.
[5546.76 → 5547.20] Is that-
[5547.20 → 5548.02] Are we at the joke now?
[5548.14 → 5548.76] So-
[5548.76 → 5549.94] I don't know about the joke yet.
[5549.94 → 5555.02] I took the TikTok logo and I made a process architecture optimization.
[5555.78 → 5556.90] It's very nerdy.
[5557.06 → 5557.68] That is funny.
[5557.84 → 5558.54] No, it's not.
[5558.64 → 5560.44] It's really not funny unless you're you or me.
[5562.00 → 5562.80] Jess, is that funny?
[5563.54 → 5564.98] Jess is the arbiter of humour around here.
[5565.00 → 5565.82] It's not funny.
[5566.02 → 5566.82] No, no, no, no.
[5567.64 → 5568.90] Jess likes the nerdy jokes.
[5569.54 → 5570.38] I do, actually.
[5570.84 → 5576.98] So there is a bus called Gen Z, which is about letting you disaggregate or aggregate or great
[5576.98 → 5577.56] things.
[5577.56 → 5580.16] And you can aggregate things in gregarious ways.
[5580.32 → 5580.56] Right.
[5580.80 → 5584.66] And you can put things like your PCI all over here and your memory all over here.
[5585.10 → 5588.38] There's just one little issue we're doing this, which is that there's the speed of light.
[5588.60 → 5589.38] I was going to say, thank you.
[5589.52 → 5592.62] There is this time of flight where you have to go from here to here.
[5592.84 → 5594.80] It is actually a constant, as it turns out.
[5594.82 → 5595.00] Really?
[5595.44 → 5595.68] Yeah.
[5595.74 → 5596.36] That's what I keep hearing.
[5597.00 → 5598.96] You need the entangled particle bus.
[5599.42 → 5599.60] Ah.
[5600.42 → 5600.68] Yeah.
[5600.94 → 5604.10] So we can get through entangled supremacy or whatever they're going to call it.
[5604.80 → 5606.68] Quantum supremacy, does that term piss you off?
[5606.72 → 5606.98] Yes.
[5607.10 → 5607.34] Thank you.
[5607.34 → 5607.54] Yeah.
[5607.84 → 5609.14] Quantum computing pisses me off.
[5609.20 → 5609.48] Okay.
[5609.56 → 5609.82] Go on.
[5609.84 → 5610.84] You want other things that piss me off?
[5610.84 → 5611.00] Yeah.
[5611.08 → 5611.36] Blockchain.
[5612.10 → 5612.36] Okay.
[5612.64 → 5614.68] And even better is quantum blockchain.
[5615.42 → 5616.54] Quantum blockchain is not a thing.
[5616.72 → 5617.50] Now, so I-
[5617.50 → 5618.38] Is quantum blockchain a thing?
[5618.54 → 5619.30] Or are you just-
[5619.30 → 5619.96] No, it's bullshit.
[5620.30 → 5620.66] It's-
[5620.66 → 5621.16] No, but is it-
[5621.16 → 5621.48] You know.
[5621.60 → 5622.86] Do people claim it's a thing?
[5622.88 → 5623.66] But that is a thing.
[5623.66 → 5628.00] Well, so, you know, I used to work at Red Hat, and they were acquired by IBM.
[5628.38 → 5629.06] And I hastened to go out.
[5629.12 → 5631.16] This is not an anti-IBM comment.
[5631.64 → 5632.74] Because I don't actually hate IBM.
[5632.74 → 5634.86] I didn't leave for that reason.
[5634.86 → 5639.22] But, you know, they're a company that's built great, amazing things over the years.
[5639.62 → 5644.32] And when I see the advertising around blockchain, I just feel sad because I'm like, there are so many cool things.
[5644.54 → 5647.32] And why are you trying to hype on the blockchain thing?
[5647.40 → 5648.46] Like, get over it.
[5648.46 → 5650.20] It's just a ledger.
[5650.40 → 5653.90] It's just a way of sharing things.
[5654.00 → 5656.28] It's a bad distributed-
[5656.28 → 5656.96] It's not a strategy.
[5657.10 → 5657.28] Yeah.
[5657.82 → 5659.92] Like, if that is your corporate strategy, please rethink it.
[5659.92 → 5661.44] But is quantum blockchain a thing?
[5662.72 → 5664.42] I've tried to make it a thing.
[5664.50 → 5665.54] Are you just making that up?
[5665.78 → 5666.60] Yes, I'm making that up.
[5666.60 → 5667.68] Okay, so you can be angry about it.
[5667.68 → 5668.92] The sad thing is that it's plausible.
[5668.94 → 5669.80] The thing is it's plausible.
[5670.04 → 5670.70] Right, exactly.
[5670.90 → 5674.84] You know, one thing I've done over the years, and I've not done this tonight, of course.
[5674.84 → 5683.82] But one thing I've done over the years is invented technology that doesn't exist, and then speak very convincingly about it to see people's reaction, which I know is terrible.
[5683.92 → 5685.60] But I used to do this, for example, in PC stores.
[5685.72 → 5688.12] So you go in there, and they ask you, can I help you?
[5688.44 → 5689.60] And you're like, no, thank you, I'm fine.
[5689.90 → 5691.00] But then they come back.
[5691.12 → 5701.74] And I had a rule where at about between three and five times, I've told the same person, now I'm not just being an asshole because you really asked me to, you know.
[5701.74 → 5705.04] So I used to ask them for USB frame relay adapters.
[5705.70 → 5706.32] That's great.
[5706.62 → 5707.50] Because it's plausible.
[5707.90 → 5709.80] I feel you could make one of the Raspberry Pi.
[5710.52 → 5712.12] Okay, yeah, I'd love to see that.
[5712.12 → 5712.66] That'd be great.
[5712.78 → 5714.00] Yeah, okay, you probably could make one.
[5714.20 → 5715.06] You know why not?
[5715.56 → 5719.20] But they would go off, and they would look for it, and they would diligently try to get it.
[5719.28 → 5721.70] And I'm like, oh, no, but could you order it in?
[5721.72 → 5722.66] I've got one at home.
[5723.08 → 5723.50] Yeah, right.
[5724.90 → 5727.94] Well, don't torture the poor sales associate.
[5728.08 → 5728.90] You know, I used to work.
[5729.00 → 5729.82] I used to work.
[5729.88 → 5730.46] Yeah, like I said.
[5730.64 → 5730.96] Sales.
[5730.96 → 5732.08] It's a hard job.
[5732.08 → 5734.82] Only if you're at the three to five times, right?
[5734.86 → 5735.74] Otherwise, I'm nice.
[5735.86 → 5740.52] But when you're at the point where I really just wanted to go and get the thing, and then I'm inventing something.
[5740.66 → 5742.26] Take it back and just torture machines.
[5742.68 → 5743.42] But blockchain, right?
[5743.46 → 5744.52] So quantum blockchain, right?
[5744.76 → 5746.00] I mean, no, it doesn't exist.
[5746.12 → 5749.44] But, I mean, it's about as plausible as half of the rest of it, right?
[5749.50 → 5749.64] Right.
[5750.00 → 5753.82] But quantum computing, you are not—I mean, I think quantum computing is fine.
[5753.86 → 5755.46] It's just extraordinarily limited in its scope.
[5755.46 → 5763.14] I think, firstly, I'm not an expert in quantum computing because I've read, like, a bunch of stuff about as much as anybody else who's vaguely interested in it.
[5763.14 → 5775.74] And I always like to see these Twitter threads where someone who's like a decade or two decades worth of studying something, and they say, just because you read something on Wikipedia for 10 minutes does not make you the world's expert.
[5775.74 → 5779.46] So I'm not claiming to be an expert in anything to do with quantum computing.
[5779.88 → 5780.04] But—
[5780.04 → 5780.52] But—
[5780.52 → 5781.28] There we go.
[5781.36 → 5781.98] Here it comes.
[5782.90 → 5788.98] But one thing I do know is that it does not replace all the classical computing that we have, right?
[5788.98 → 5789.08] Right.
[5789.24 → 5801.00] The vast majority of the computing that we do today, and we will do for many, many, many, many years to come, is going to involve little transistors switching on and off and running little state machines and microprocessors.
[5801.00 → 5812.38] We will also hopefully have these wonderful quantum supremacy machines that can solve certain problems, some of them terrifying, but those will be kind of really fancy accelerators that make certain things go really fast.
[5812.44 → 5815.56] And meanwhile, it will be a von Neumann machine that actually does the heavy lifting.
[5815.62 → 5816.36] Johnny von Neumann.
[5816.46 → 5817.36] Johnny von Neumann, baby.
[5817.36 → 5817.38] He dances underneath.
[5818.16 → 5818.30] Yeah.
[5818.34 → 5821.68] No, I'm a von Neumann dead-ended for sure.
[5822.80 → 5823.98] John von Neumann's great.
[5824.10 → 5824.52] I want to—
[5824.52 → 5827.66] You know, I want to get a bust of John von Neumann.
[5827.82 → 5829.06] I've actually wanted to do this for many years.
[5829.06 → 5834.32] Institute for—Institute of Advanced Science, wasn't that the one that he was at?
[5834.40 → 5835.02] Yes, that's right.
[5835.90 → 5836.08] Yeah.
[5836.28 → 5837.48] And he—I mean, you know what?
[5837.70 → 5841.24] This is von Neumann's gift, and we should not be squandering it.
[5842.12 → 5845.22] Well, I think that's a great note on which to wrap it up.
[5845.34 → 5852.82] John, thank you very much for sharing all of your unvarnished thoughts, telling the stories that you maybe shouldn't have told.
[5853.80 → 5854.70] Thank you, yes.
[5855.32 → 5856.16] But this has been terrific.
[5856.28 → 5858.40] Thank you so much for joining us in the garage tonight.
[5858.40 → 5859.42] Thank you for having me.
[5860.74 → 5864.80] You've been listening to On The Metal, tales from the hardware software interface.
[5865.22 → 5871.24] For show notes, to learn more about our guests, or to sign up for our mailing list, visit us at onthemetal.fm.
[5871.66 → 5877.48] On The Metal is a production of Oxide Computer Company and is recorded in the Oxide Garage in Oakland, California.
[5878.10 → 5881.08] To learn more about Oxide, visit us at oxide.computer.
[5881.08 → 5887.26] On The Metal is hosted by me, Brian Cantwell, along with Jess Frizzell, and we are frequently joined by our boss, Steve Tuck.
[5887.50 → 5891.40] Our original and awesome theme music is by J.J. Wrestler at Pollen Music Group.
[5891.64 → 5895.36] You can learn more about J.J. and Pollen at pollenmusicgroup.com.
[5895.36 → 5899.54] We are edited and produced by Chris Hill and his crew at Humble Pod.
[5899.86 → 5905.74] From Jess, from Steve, from me, and from all of us at Oxide Computer Company, thanks for listening to On The Metal.
[5905.74 → 5935.72] On The Metal.
[5935.74 → 5965.72] On The Metal.
