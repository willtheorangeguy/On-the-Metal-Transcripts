[0.00 → 15.98] Welcome to On The Metal, tales from the hardware software interface.
[16.18 → 19.08] I'm Brian Cantwell. With me, as always, is Jess Frizzell. Hey, Jess.
[19.34 → 19.84] Hey, Brian.
[20.04 → 22.64] And joining us is our boss, Steve Tuck. Hey, Steve.
[22.90 → 23.68] Excited to be here.
[23.80 → 24.90] All right, keep us in line.
[25.16 → 27.16] And Jess, you want to introduce who we've got in the garage today?
[27.16 → 32.14] So today we have Ron Min nick, who I like to refer to as the godfather of open firmware,
[32.44 → 34.22] but I'm not sure if you'd even like that.
[36.54 → 39.22] But yeah, it's super exciting. We're in the garage as usual.
[39.94 → 42.04] Ron, welcome to the garage. It's great to have you.
[42.22 → 43.22] It's an honour to be here.
[43.66 → 47.16] So, well, first, the godfather of open firmware, do you find that disparaging or not?
[47.26 → 50.80] I view it as certainly praise, but hopefully you view that as... How do you view that?
[51.32 → 52.46] There's probably more than one.
[52.84 → 53.20] Okay.
[53.82 → 54.04] Yeah.
[54.04 → 58.24] So maybe that's a good place to start about where open firmware...
[58.24 → 61.34] Because you were certainly at the birthplace of open firmware in a lot of ways.
[61.72 → 62.90] How did that come about?
[63.08 → 64.26] How did you...
[64.26 → 65.96] Where did you see the need, and how did you fill it?
[66.34 → 67.18] Actually, it's weird.
[68.46 → 76.26] My hope of doing that work started in the early 90s with Sun Microsystems systems.
[76.26 → 81.92] When I looked at the Netbook program they had at the time, realized it was a quarter Meg.
[82.62 → 87.58] And a lot of it was sort of Sun would take these scripts and run them on their kernel
[87.58 → 93.24] and extract drivers from the kernel and compile them into the Netbook program.
[93.58 → 98.34] And we took one look at that and thought, well, why don't we just like to put the kernel in the flash?
[98.34 → 104.28] And that's when we hit the hard wall of, well, because it's licensed and the flash is too small
[104.28 → 106.08] and all these other problems applied.
[106.58 → 110.04] So that went on the shelf from about 1990, 1991.
[110.56 → 114.68] And in the intervening time, I actually helped design a PCI card.
[114.82 → 118.42] And that's when I realized PCI had self-defining hardware,
[118.42 → 123.72] which meant we were done with dip switches and jumpers and special knowledge and all that.
[123.84 → 128.86] And it was not the first self-defining hardware bus, but it was the first commodity one.
[129.08 → 129.10] Right.
[129.82 → 137.74] And so in 99, I had this god-awful VA Linux cluster with these Intel L440 GO motherboards
[137.74 → 139.26] that took five minutes to boot.
[139.96 → 146.74] And if you needed to ref lash the firmware, you had to rip the thing open and physically move a jumper
[146.74 → 150.78] and put it in a floppy disk that ran an autoexec.bat.
[150.90 → 151.76] Oh, my God.
[151.84 → 158.40] That ran, but because it was a sort of backup 64K firmware that burned the real firmware,
[158.52 → 162.98] you didn't have video or keyboard, which meant that their instructions were,
[163.18 → 167.86] put the floppy in, watch its LED light, listen for a couple beeps.
[168.42 → 168.60] Pray.
[168.60 → 169.68] Everything will be prayed.
[169.88 → 173.50] Praying was not in a manual, but it was in the activity, and you'll be fine.
[173.50 → 179.10] And so this was so terribly awful on every possible dimension that I thought,
[179.24 → 182.42] first off, wow, we've got a quarter Meg flash part in there,
[183.08 → 186.40] more than big enough to hold a Linux 2.2 kernel at the time.
[186.88 → 188.50] We have self-defining hardware.
[189.24 → 193.40] Developer.intel.com actually has chipset data sheets.
[193.54 → 195.46] It's no longer true, but it was true back then.
[195.46 → 201.56] And the pieces were all here in place that we could actually write a C-based thing
[201.56 → 204.82] that would load a Linux kernel into RAM and jump to it.
[205.66 → 209.10] The original Linux BIOS was intended to be about five instructions,
[209.52 → 214.56] which was taken this thing in flash, copy it to RAM, and jump to it.
[215.20 → 218.54] And what I didn't realize when I started the project is that wouldn't work anymore
[218.54 → 221.72] because DRAM was actually a little more complicated to set up.
[221.72 → 223.28] By then, it was synchronous DRAM.
[223.90 → 225.80] There were clocks and things that had to happen.
[226.22 → 229.22] So Linux BIOS grew a little bit from there,
[229.44 → 231.72] and then the kernel kept getting bigger,
[232.08 → 234.96] but we managed to kind of make that all work for a few years.
[235.36 → 235.84] That's amazing.
[236.16 → 238.94] And so at a time when DRAM training was getting more complicated,
[239.00 → 240.20] so where did you get the DRAM training code?
[240.38 → 240.66] Did you?
[240.92 → 242.24] Stefan Reindeer wrote that.
[242.36 → 242.72] Oh, wow.
[242.72 → 245.30] Yeah, so pretty sure it was Stefan.
[247.24 → 249.04] There were a lot of us looking at it,
[249.16 → 252.74] but by the time the Option came along, which needed DRAM training,
[253.00 → 257.28] again, in SDRAM, you just really needed to read the serial presence detect bits,
[258.44 → 261.82] do a computation, jam them in a register, you were done.
[261.92 → 264.00] There really kind of wasn't training on SDRAM,
[264.08 → 266.96] but DDR brought in the idea of training,
[267.06 → 268.80] and that just complicated our life a lot.
[268.80 → 271.00] So we had really smart people like Ying HAI Liu,
[271.82 → 275.86] who was, I think, at Than for a while, and then AMD,
[276.46 → 277.28] who got involved.
[277.40 → 279.68] Of course, Eric Lieberman, of course, Stefan Reindeer.
[280.24 → 283.26] And I would have to really go do a Git blame on the tree
[283.26 → 286.54] to really remember, actually, who really wrote the real training code.
[286.62 → 287.68] I only know it wasn't me.
[288.18 → 290.72] Well, and I just feel like DRAM training is one of those things that,
[290.80 → 292.94] I mean, as programmers, we take DRAM for granted.
[293.20 → 293.38] Yeah.
[293.48 → 296.72] And it's like, how complicated can it be to actually, like,
[296.72 → 298.94] get DRAM booted effectively?
[299.10 → 300.00] It's like, well, glad you asked.
[300.06 → 301.62] As it turns out, it can be quite complicated.
[301.88 → 302.04] Yeah.
[302.18 → 304.94] So probably in the early 2000s with DDR,
[305.42 → 309.38] it was order of several million instructions.
[309.78 → 310.86] I timed it on a...
[310.86 → 311.18] Whoa.
[311.52 → 311.74] Yeah.
[312.10 → 314.62] Instruction times, I should say, because there are a lot of loops.
[315.00 → 315.28] Right.
[315.62 → 319.38] I timed it on a Chromebook in 2012 when I joined Google,
[319.48 → 322.36] and by that point, it was up to billions of instructions.
[322.36 → 326.10] And so it's so bad and so slow, in fact,
[326.20 → 331.72] that typical BIOS will try and cache the computed parameters for DRAM training
[331.72 → 334.00] so that it doesn't have to do it more than once.
[334.88 → 339.90] Because there's a large, large chunk of time minimum on a server system,
[340.30 → 342.82] 10 seconds maybe, that is DRAM training.
[343.38 → 343.86] Wow.
[343.88 → 344.70] It's a long, long time.
[344.72 → 346.04] That's a long time.
[346.12 → 348.90] Now, compared to UEFI, it's really fast, because UEFI is 10 minutes.
[348.90 → 352.78] So UEFI is 60 times slower than the DRAM training step,
[353.02 → 354.60] but still, it's a long time.
[354.90 → 359.18] Well, and as someone who has never ventured into that kind of code,
[359.26 → 361.62] but who has suffered from a pandemic of DIMM failures,
[361.92 → 365.14] you really do wonder how robust that is to...
[365.14 → 366.48] I mean, because you're basically on the fly
[366.48 → 368.76] trying to determine the right parameters for this thing.
[369.08 → 369.28] Yeah.
[369.88 → 373.40] Over time, presumably, the system can change and invalidate those parameters
[373.40 → 374.60] at some level, you would think,
[374.72 → 377.14] or that you'd think that would be at least a possibility.
[377.14 → 381.14] You know, and I don't have the knowledge of that part of it, right?
[381.26 → 383.46] Once you compute, like a Chromebook, you know,
[383.50 → 386.24] they compute the parameters, and actually the ARM Chromebook,
[386.64 → 392.16] it'll come with, say, eight or four predefined sets of parameters.
[393.32 → 396.28] So based on that, I would guess that, you know,
[396.38 → 398.14] in some of these systems, it doesn't really,
[398.30 → 400.00] once you know it, it doesn't drift that much.
[400.12 → 400.98] Right, right, right.
[401.54 → 404.04] It's just amazing that all the work that's required,
[404.04 → 407.54] the billions of instructions that are required to get a part working
[407.54 → 408.86] that we just take for granted.
[409.16 → 409.30] Yep.
[409.60 → 411.58] And a little more disturbing is the fact that
[411.58 → 415.16] even though we opened that up in the early 2000s
[415.16 → 417.88] because the vendors decided a few years later
[417.88 → 419.58] they didn't want that to be opened up,
[419.96 → 422.26] it's now behind the wall of a binary blob.
[422.42 → 422.74] Right.
[422.74 → 427.24] So I always viewed Linux, BIOS, and then Core boot in part
[427.24 → 432.70] as sort of this open source reservoir of knowledge, right?
[432.74 → 434.34] Do you want to know how to do DRAM training?
[434.46 → 435.28] You can look at our code.
[435.50 → 436.48] You can see how it works.
[437.14 → 443.54] And that, sadly, is sort of falling behind the veil of binary blobs.
[443.60 → 443.84] Yeah.
[444.26 → 444.80] It's a problem.
[445.12 → 448.30] Well, when, Jess, when you and I were at the Open Source Firmware Conference,
[448.60 → 449.90] Ron, obviously with you and crew,
[449.90 → 451.56] it was a terrific conference,
[451.98 → 455.80] and I was telling Jess it reminded me of like an old school conference
[455.80 → 456.78] because it is.
[456.90 → 459.80] It's using open source as that repository of knowledge,
[460.06 → 463.54] which that used to be true in an all proprietary era.
[463.70 → 466.12] It's become less true for the world writ large,
[466.24 → 468.62] but it still really is true for firmware.
[468.98 → 469.12] It is.
[469.18 → 469.34] Yeah.
[469.62 → 471.18] That's why I love that conference so much.
[471.80 → 474.28] I tell the people involved in all those projects,
[474.48 → 475.44] and as far as I'm concerned,
[475.52 → 477.38] it's the best conference I go to every year
[477.38 → 479.38] because people show up with soldering irons.
[479.38 → 480.48] It was so great.
[480.86 → 484.32] The hackathon was honestly the coolest part because of that.
[484.48 → 487.62] Like, you don't see that at any other conference that I've been to, at least.
[488.24 → 492.10] Well, I also feel that, like, that was the spirit of open source.
[492.48 → 497.26] You know, there was a time when in an all proprietary world,
[497.42 → 498.52] you would go to these conferences,
[498.52 → 499.70] and you'd be delighted by,
[499.78 → 503.14] oh, my God, there are 200 people that are interested in the same thing I'm interested in,
[503.14 → 504.84] and it felt so arcane,
[504.84 → 507.72] and the social networking was so much fun.
[508.08 → 511.10] And now we're in this era where people are kind of exhausted by pull requests.
[511.42 → 514.26] It's like more commercialized versus the grassroots.
[514.48 → 517.16] The grassroots open source is like my favourite open source.
[517.56 → 517.76] Yeah.
[518.10 → 521.50] Well, actually, one of the reasons I started a Root project,
[521.62 → 526.90] which we now use in our open source firmware work at Google and other places,
[526.90 → 531.48] is it was the last time I tried to do a build root and it failed.
[531.74 → 537.86] And I watched just this gigantic, massive stack of config files fail to work correctly.
[539.00 → 540.98] So there are really two barriers.
[541.12 → 543.52] There's the binary blob barrier, which has kind of come back.
[544.36 → 546.26] But unfortunately, I feel in the open source community,
[546.38 → 553.72] one of the other barriers is we've just built these gigantic stacks of scripts and scripts and scripts.
[553.72 → 561.60] And it's very hard sometimes to get behind the wall of all that stuff and find out what's really going on.
[562.12 → 564.98] And so the goal with Root, I know I'm diverging a little,
[565.10 → 571.64] but the goal with Root was to get back that sense we had in the early Unix days that I would say,
[571.78 → 572.50] oh, where's cat?
[572.66 → 574.36] Oh, here's the source to cat right there.
[574.50 → 579.00] Not, oh, apt-get cat, which I think is, you know,
[579.06 → 582.42] it's wonderful that the source for cat can be found.
[582.42 → 586.64] It's not wonderful that very few people ever look at that stuff.
[586.72 → 590.86] Well, then you're like apt-get cat, and it's like, okay, I'm going to download 431 legs.
[590.90 → 592.10] It's like, oh my God.
[592.16 → 594.76] And it's like, we've got dependencies on, it's like, how is this?
[594.94 → 597.96] I mean, yeah, it's a complicated world.
[597.96 → 604.04] And you do wonder, is there a simplicity that we could be realizing that we're not realizing that?
[604.12 → 606.72] Certainly Unix, I mean, it's a pun on Multics, right?
[606.72 → 611.50] I actually think, ask anyone if they ever use the where is command.
[612.76 → 617.38] Where is command is a community used to run to tell you where the source to the command was, right?
[617.58 → 621.80] And one of the goals that we've had, we are in some sense growing up again,
[622.02 → 625.56] like, you know, our work doesn't end at the BIOS barrier, right?
[625.56 → 629.58] The goal is to make things accessible again in a way of source.
[629.58 → 635.50] And so my ideal system is I type where is, and Gen2 is somewhat in that spirit,
[635.62 → 640.66] but Gen2 is an enormously complex system that very few people I know really understand, to be honest.
[640.90 → 644.56] I love what they want to do, but wow, I'll type where is,
[644.60 → 647.28] and I'll immediately see a command, and it's small and short and concise,
[647.38 → 648.76] and it builds in a quarter second.
[649.00 → 650.38] That's the way I feel it ought to be.
[650.88 → 651.28] Yeah.
[651.60 → 653.02] I actually, I love Gen2.
[653.52 → 656.60] I used it for a long time to make like this custom OS,
[656.60 → 659.22] which is how also like Chrome OS is made.
[659.58 → 663.62] And I think it's like perfect for that use case because the static binaries,
[663.82 → 666.52] compiling an OS with just static binaries, I don't know, that was my goal.
[667.22 → 668.32] I love static binaries.
[668.54 → 668.74] Yeah.
[669.26 → 675.14] In fact, Root has built around that whole idea that binaries should be static.
[675.52 → 675.72] Nice.
[675.72 → 677.46] So I'm with you on that one totally.
[677.84 → 679.42] Sorry, can I ask what Gen2 is?
[680.02 → 682.36] And there's the Gen2 problem right in a nutshell.
[682.58 → 683.64] That is the Gen2 problem in a nutshell.
[683.64 → 685.52] I assume it's not generation, second generation.
[685.52 → 687.06] No, this is not you.
[687.26 → 688.02] This is Gen2.
[688.02 → 691.24] This is an entirely reasonable question.
[692.00 → 696.88] But the fact that you know about Ubuntu and you know about CentOS and these other things,
[696.98 → 698.82] but Gen2, you're like, what the hell is that?
[699.32 → 699.42] Yeah.
[699.58 → 703.20] My favourite Gen2 meme though, this is very subculture of Gen2,
[703.56 → 706.20] it's that when you are trying to compile GCC,
[706.44 → 709.10] like you're just starting out like your kind of distribution,
[709.30 → 712.84] like you have to go all the way to Germany and back basically
[712.84 → 717.00] to like to get the source code for GCC and compile the world,
[717.12 → 717.96] which I think is a funny thing.
[717.96 → 721.30] So you should explain for Steve what the zeitgeist is of Gen2 with the...
[721.30 → 722.94] Yeah, you build everything from scratch.
[722.94 → 726.68] Like everything is from like almost first principles of like building artifacts.
[726.68 → 730.68] So you have to compile everything from source, including the compiler itself,
[730.68 → 735.28] which is kind of like a chicken-and-egg problem because like you need a compiler to compile the compiler.
[735.28 → 737.90] And it's excruciating.
[738.38 → 744.08] And there is something that is obviously very satisfying about building a system from first principles,
[744.32 → 748.86] but the fact that it is so difficult to build a system from first principles today,
[749.36 → 753.28] and that's, I mean, in GCC, boy, in an LLVM world, it's even more complicated.
[753.74 → 757.04] And, you know, Ron, as you know, I'm a huge fan of Rust,
[757.30 → 760.18] but the big complexity of Rust is getting LLVM to work.
[760.36 → 762.06] I mean, there is so much working.
[762.06 → 766.32] And once you can get that working, you are opened up to this new kind of simplicity.
[766.56 → 767.54] But there's a lot of complexity.
[767.92 → 771.84] Getting just the compiler to compile is excruciating.
[772.20 → 778.06] That's where I think Ken Thompson's C compiler from Plan 9 is an incredible lesson in compactness.
[778.70 → 780.38] It compiles in about a second or two.
[781.16 → 783.36] It's about, well, it's under 24 files.
[784.12 → 786.78] Interesting thing in there is he actually doesn't use the C library.
[788.08 → 788.82] Old school.
[789.16 → 789.96] No, no, no.
[789.96 → 791.38] It's actually about...
[791.38 → 792.08] Does he make system calls?
[792.50 → 794.54] Yeah, but it's a trusting trust thing.
[794.66 → 797.48] The thing is, if you pull the C library in as part of your compiler,
[798.16 → 800.82] there's kind of an introduction of a vulnerability there.
[800.94 → 801.16] Right.
[801.26 → 804.70] And what Ken realizes is he can make that C compiler,
[805.58 → 807.64] and I'm reading into what he did, so maybe I'm wrong,
[807.70 → 810.42] but you can kind of make the C compiler a standalone entity
[810.42 → 811.94] that doesn't pull in any libraries,
[812.22 → 814.38] and it's kind of a neat idea to do it that way.
[814.66 → 816.04] So he has a couple of system calls.
[816.14 → 816.76] He only has four.
[816.76 → 819.82] The thing I totally love is his mallow is an S break,
[819.92 → 820.72] and his free is an empty.
[821.72 → 823.66] Free does never happen because, well,
[824.04 → 826.10] you're not ever going to get big enough that it matters.
[826.32 → 829.82] And it is kind of like a hardware root of trust analog for compiling.
[830.08 → 833.52] Like we want to have this thing, this one compiler that is super simple,
[833.52 → 836.78] and then we will use this compiler that we can reason about
[836.78 → 841.60] and we can verify putatively to actually then begin to bootstrap the world
[841.60 → 843.84] and build a much more complicated world.
[844.10 → 844.20] Yep.
[844.46 → 848.64] And actually every go through Go 1.3 was actually based on the Ken C compiler.
[848.76 → 848.92] Right.
[849.32 → 849.50] Yeah.
[849.70 → 852.34] The trust of trust paper is actually one of my favourite papers
[852.34 → 854.44] because it's very short, simple,
[854.64 → 856.40] and then it's just like, wow, this makes a lot of sense.
[857.00 → 857.78] Trusting trust.
[857.96 → 861.02] Like it goes down to first principles again of what you're building.
[861.02 → 863.96] And it really had to go to firmware, actually,
[864.46 → 867.54] because you trust all this firmware, and it's all really very bad code.
[868.52 → 868.96] Yes.
[869.12 → 872.66] It was not designed to be at the bedrock of humanity the way it is, certainly.
[873.00 → 876.66] So what was your first exposure to Plan 9 and the Unix philosophy?
[876.84 → 879.80] I mean, obviously, was that Los Alamos or before?
[879.94 → 880.86] I think I'll date myself.
[880.94 → 883.92] My first exposure to Plan Unix was 1976.
[884.58 → 885.14] There you go.
[885.44 → 886.58] On what machine?
[887.36 → 889.02] Version 6 on an 1145.
[889.96 → 890.40] Nice.
[890.40 → 890.92] Yeah.
[891.02 → 895.68] And the thing about, I wouldn't trade the time spent with that for anything.
[896.00 → 899.40] We were so circumscribed by the limits of the machine.
[899.76 → 901.48] You really had to think through what you were doing.
[902.00 → 904.34] And again, Ken is the master at this.
[904.44 → 907.74] All of Ken's code through the present day.
[907.88 → 909.36] I don't know if he's written recently,
[909.58 → 912.50] but you still see it, signature bits of Ken.
[913.98 → 915.76] And it's hard to describe,
[915.76 → 925.32] but it's sort of code that can kind of fold in on itself and do something additional in addition to the purpose it was described for.
[925.46 → 929.96] I don't possess the mathematical skill to kind of define the way his code works,
[930.08 → 931.78] but you kind of know it when you see it.
[931.86 → 932.32] Oh, interesting.
[932.32 → 940.70] And so you see a function, but then you see, you know, maybe multiple functions calling that and getting different behaviours, you know,
[940.70 → 941.60] in ways you wouldn't think of.
[941.60 → 945.16] So Unix back at that time, because of all the limits we lived with,
[945.72 → 949.36] made us think very, very, very hard about how you did things.
[949.60 → 952.94] And the result was, you know, you tended to write tight,
[953.42 → 956.14] and the code had to be clean, but tight, fast code.
[956.48 → 957.52] And so this is 1145.
[957.82 → 958.24] Where is it?
[958.28 → 959.74] Is this at a school or where?
[959.94 → 961.84] I gave the front panel to a friend of mine,
[961.92 → 964.06] but this was at University of Delaware back in the day.
[964.06 → 966.26] Okay, so you're a university student, I assume.
[966.86 → 967.98] Yeah, I was, yeah.
[968.42 → 971.68] And first exposure to computers, 1976,
[971.92 → 973.52] that's probably your first computer at that point, right?
[973.86 → 975.92] No, believe it or not, 69 was my first computer.
[976.18 → 977.94] I wrote my first program 50 years ago.
[978.18 → 979.76] Okay, we got to talk about that.
[979.80 → 980.42] What computer is that?
[980.78 → 981.82] It was a-
[981.82 → 983.36] 1969, okay.
[983.56 → 984.04] At home?
[984.90 → 988.00] So, well, and I built a little relay computers and things to it.
[988.10 → 990.78] So I hungered for more than eight bits of memory,
[990.78 → 992.88] because that's all I ever built-in my relay computers.
[992.88 → 996.96] But yeah, it was basic HP 2100 leased machine
[996.96 → 998.40] from a company called Lease Co.
[999.10 → 999.70] Lease Co?
[999.76 → 1001.42] It's long gone, long gone.
[1002.08 → 1006.22] And it was an ASR 33 paper tape punch and reader.
[1006.52 → 1006.90] Nice.
[1007.18 → 1007.42] Yeah.
[1008.02 → 1008.58] That was cool.
[1008.90 → 1010.44] And you had this at home somehow?
[1010.46 → 1011.64] No, no, no, that was in my high school.
[1011.76 → 1012.40] In your high school, okay.
[1013.26 → 1014.80] But they, well, it was a high school course,
[1014.80 → 1017.52] and I had to like petition to get in because I was 12,
[1017.68 → 1020.12] and they didn't want me to be doing that when I was 12.
[1020.72 → 1021.36] So, yeah.
[1021.36 → 1021.40] Yeah.
[1021.84 → 1023.94] So I had, you know, I had the usual things
[1023.94 → 1026.54] that a lot of people wanting to do computers back then had.
[1026.58 → 1029.18] I had a Dr. Him, for anyone who knows what a Dr. Him is.
[1029.30 → 1030.04] No, what's a Dr. Him?
[1030.24 → 1030.94] A Dr. Him.
[1031.06 → 1032.14] I'll bring it in some time.
[1032.44 → 1036.48] It was a plastic device that played the game in Him,
[1036.92 → 1039.90] and the flip-flops were actuated by marbles.
[1039.90 → 1042.28] So in some sense, the marble was sort of this,
[1043.12 → 1046.54] the input bit to these three plastic flip-flops.
[1047.56 → 1050.14] And it taught you a lot about,
[1050.46 → 1051.80] even though you didn't know you were being taught,
[1051.88 → 1053.96] it taught you a lot about sort of digital logic.
[1054.42 → 1056.88] This was a company called ESR, started in New Jersey.
[1057.16 → 1060.70] They built four different kinds of digital devices,
[1061.70 → 1062.72] cast in plastic.
[1062.72 → 1064.40] Like, where are these today?
[1064.56 → 1065.86] We got to, I mean, these are like,
[1065.92 → 1066.42] we need one of those.
[1066.50 → 1067.06] Yeah, this is,
[1067.10 → 1068.56] I put this on the Christmas list for the kids.
[1068.68 → 1069.52] I have three of them.
[1069.64 → 1069.98] Oh my gosh.
[1069.98 → 1070.94] I never got the fourth one.
[1070.98 → 1071.68] They went out of business.
[1071.80 → 1073.46] The first was Dr. Him.
[1074.20 → 1075.38] The next was Thinkable.
[1076.42 → 1077.60] The next was, and I really,
[1077.80 → 1080.02] it's on my list to kind of recover
[1080.02 → 1081.56] my poor little Digicam one.
[1081.56 → 1084.20] The Digicam one is what taught me
[1084.20 → 1086.16] the Oregon's theorem, Boolean algebra,
[1086.30 → 1086.98] that kind of thing.
[1087.18 → 1089.66] It was a three flip-flop device
[1089.66 → 1091.52] and you would realize the end and or
[1091.52 → 1094.44] of the state machine with these little plastic,
[1094.84 → 1095.46] believe it or not,
[1095.52 → 1096.76] little bits of plastic tubing.
[1097.64 → 1098.72] And then there were these,
[1099.22 → 1101.34] you know, you define your logic equations
[1101.34 → 1103.72] and a clock was this thing you moved back and forth.
[1103.82 → 1104.10] Oh my gosh.
[1104.10 → 1105.56] You really had a clock printed on it.
[1105.86 → 1108.04] And then you would watch the three bits change value
[1108.04 → 1109.42] as these things move back and forth.
[1109.42 → 1110.36] Oh my God, that's incredibly valuable.
[1110.50 → 1111.60] They are still available.
[1111.82 → 1112.64] They are not cheap.
[1113.06 → 1115.16] Are they, you should be able to buy a reproduction.
[1115.16 → 1116.20] Because these are, obviously.
[1116.20 → 1116.76] These are originals.
[1116.76 → 1118.40] These are originals that people are selling online.
[1118.40 → 1119.78] What a great idea though.
[1119.88 → 1121.52] Because I remember when I,
[1121.74 → 1123.42] certainly when I was coming up in the 80s,
[1123.62 → 1125.62] that was not a thing, unfortunately, anymore.
[1125.74 → 1125.88] Yeah.
[1126.18 → 1127.80] And I just remember being,
[1128.36 → 1129.54] as a young kid,
[1129.66 → 1130.02] thinking like,
[1130.04 → 1132.90] I don't understand how we've built computation
[1132.90 → 1134.38] on binary logic, you know?
[1134.46 → 1134.58] Yeah.
[1134.84 → 1136.62] And getting an intuition for that
[1136.62 → 1139.42] at such kind of physical level is great.
[1139.54 → 1140.88] That's a great idea.
[1141.10 → 1141.60] I mean, it's.
[1141.68 → 1143.24] It was really, well,
[1143.56 → 1144.80] it got me started, right?
[1144.80 → 1147.68] And so I kind of was a hardware designer
[1147.68 → 1148.54] for a long time
[1148.54 → 1149.96] while I was also doing software
[1149.96 → 1152.04] because of the Digicam 1.
[1152.26 → 1153.86] If I could find those guys
[1153.86 → 1155.30] and thank them,
[1155.56 → 1155.90] I wish I,
[1155.98 → 1156.98] I don't know where they are anymore,
[1157.16 → 1157.94] who they were even.
[1158.12 → 1158.98] They're on Wikipedia,
[1159.20 → 1159.76] it's ESR.
[1160.90 → 1161.62] There you go.
[1161.82 → 1162.04] Yeah.
[1162.04 → 1162.88] That's Dr. Him.
[1163.16 → 1163.40] Yeah.
[1163.40 → 1163.58] Yeah.
[1163.88 → 1164.90] Dr. Him was wonderful,
[1165.14 → 1165.36] you know,
[1165.36 → 1167.60] because you really would.
[1168.14 → 1169.30] If you'd hung on to a couple of them,
[1169.32 → 1169.94] they've been marked up
[1169.94 → 1171.34] to 145 bucks a piece now.
[1171.34 → 1172.06] You know,
[1172.32 → 1174.50] it's cheap at 10 times the price
[1174.50 → 1175.98] for the educational value, right?
[1176.18 → 1176.92] And so Dear Listener,
[1176.98 → 1178.66] Steve has done what you might well be doing
[1178.66 → 1180.00] is just going to the Wikipedia page
[1180.00 → 1180.26] and.
[1180.42 → 1182.14] Googling ESR Dr. Him.
[1182.48 → 1183.50] We'll put it in the show notes.
[1183.50 → 1184.60] We'll put it in the show notes for sure.
[1184.70 → 1184.88] That's,
[1185.06 → 1186.02] but that's amazing.
[1186.10 → 1186.92] What a great first exposure.
[1187.08 → 1188.58] And so that is in the
[1188.64 → 1190.16] it sounds like mid 60s.
[1190.76 → 1191.02] Yeah,
[1191.06 → 1191.44] I think.
[1192.10 → 1194.34] So the other sort of very early
[1194.34 → 1196.48] sort of learn about computers thing I got
[1196.48 → 1197.60] was called the ENIAC,
[1197.60 → 1202.00] which was literally perf board rotary dials
[1202.00 → 1203.74] and you would do plug board things
[1203.74 → 1204.06] and,
[1204.18 → 1204.92] you know,
[1204.96 → 1207.48] you would set up logic equations
[1207.48 → 1208.22] and do stuff.
[1208.42 → 1208.66] And then I.
[1208.74 → 1210.56] There's something great about the EAC era
[1210.56 → 1211.28] of like.
[1211.44 → 1211.46] Oh,
[1211.50 → 1211.74] yes.
[1211.74 → 1212.52] The Iliac.
[1213.30 → 1213.74] Iliac.
[1213.82 → 1214.66] The Maniac.
[1214.80 → 1215.44] All this stuff.
[1215.56 → 1216.46] The ENIAC now.
[1216.56 → 1217.10] That's great.
[1217.72 → 1218.24] But again,
[1218.36 → 1219.32] it's these,
[1219.48 → 1219.88] these,
[1219.96 → 1222.24] I think when you have limits,
[1222.24 → 1222.64] it's,
[1222.70 → 1223.12] it's good,
[1223.46 → 1223.68] right?
[1223.68 → 1227.60] Because you have to really think it through carefully.
[1227.92 → 1230.14] The ENIAC designed and developed by Edmund Berkeley.
[1231.06 → 1231.54] All right.
[1231.68 → 1232.00] Really.
[1233.28 → 1233.52] And,
[1233.60 → 1233.80] and,
[1233.90 → 1234.32] and you know,
[1234.36 → 1235.48] this isn't like,
[1235.82 → 1236.72] this hasn't ended.
[1237.38 → 1237.60] There,
[1237.72 → 1239.08] there's an artist in France
[1239.08 → 1243.44] who designed this incredibly beautiful digital clock
[1243.44 → 1247.34] and she built all the flip-flops using LEDs.
[1248.78 → 1249.30] And,
[1249.36 → 1249.54] and,
[1249.54 → 1251.24] and so I,
[1251.36 → 1252.00] and I've lost,
[1252.14 → 1253.46] I've lost the reference,
[1253.46 → 1253.80] right?
[1253.86 → 1255.96] But it's about six or eight feet tall.
[1256.06 → 1256.46] And,
[1256.54 → 1257.20] and it's just,
[1257.76 → 1262.14] you can kind of watch the computation as it occurs.
[1262.28 → 1262.50] Yeah.
[1262.50 → 1263.24] This digital clock.
[1263.34 → 1263.40] And,
[1263.50 → 1266.98] and so even where we not to do this stuff with plastic,
[1266.98 → 1268.72] this stuff could be done with,
[1269.04 → 1273.30] in ways that make it visually clear what's going on.
[1273.30 → 1277.42] Especially because the atomic particles of computation have not changed.
[1277.66 → 1277.90] Yeah.
[1278.34 → 1279.56] For all the talk of,
[1279.62 → 1279.86] you know,
[1279.98 → 1283.04] quantum computing and the very poorly named,
[1283.04 → 1283.26] I mean,
[1283.28 → 1285.64] I guess terrifically named from their perspective,
[1285.76 → 1286.58] a quantum supremacy.
[1286.58 → 1288.32] I hate that term because it makes my,
[1288.76 → 1289.00] you know,
[1289.04 → 1289.20] my,
[1289.22 → 1290.00] my mom's,
[1290.00 → 1293.44] my mom's book club is contemplating ritual suicide because,
[1293.44 → 1295.94] because Google has achieved quantum supremacy.
[1295.94 → 1296.38] It's like,
[1296.42 → 1296.78] Oh God.
[1297.58 → 1299.62] But people are reading too much Tom Clancy,
[1299.74 → 1300.06] I think,
[1300.12 → 1300.34] right?
[1301.34 → 1301.66] Supremacy.
[1302.14 → 1302.50] Exactly.
[1302.68 → 1303.00] Too much.
[1303.00 → 1304.50] But meanwhile,
[1304.68 → 1305.14] give me a break.
[1305.32 → 1305.42] Yeah.
[1305.50 → 1309.62] Back in the reality of a stored program computer and a von Neumann architecture,
[1309.76 → 1311.06] which is still what we're living with.
[1311.36 → 1313.02] These are still the atomic particles.
[1313.28 → 1313.38] Yeah.
[1313.38 → 1315.32] And it is still deeply,
[1315.44 → 1315.62] in fact,
[1315.66 → 1321.20] more so than ever in an era where we are further removed from that to be able to actually like,
[1321.60 → 1326.00] physically understand and get an intuition for what's actually happening on this.
[1326.00 → 1326.72] That's terrific.
[1327.22 → 1332.64] I think that's why it's pretty funny when we did the work in 1999 on Linux BIOS,
[1332.72 → 1334.26] I had a lot of people from vendors say,
[1334.34 → 1335.60] you can't write a BIOS in C.
[1337.04 → 1337.32] And,
[1337.32 → 1337.56] and,
[1337.56 → 1337.94] and,
[1337.94 → 1339.46] and about five years later,
[1339.46 → 1339.90] they said,
[1339.98 → 1340.12] well,
[1340.14 → 1342.02] thanks to Ron who showed us we could write a BIOS in C.
[1342.08 → 1342.18] Well,
[1342.20 → 1342.62] first off,
[1342.74 → 1347.80] I'd written a BIOS in a better language than C in 1978.
[1347.80 → 1349.20] So I knew I could write it in C.
[1349.30 → 1349.76] And secondly,
[1349.92 → 1350.36] arguably,
[1350.96 → 1353.48] Unix in many ways was a BIOS.
[1353.48 → 1355.06] Lives in the place of a BIOS,
[1355.20 → 1355.40] right?
[1355.40 → 1355.68] And,
[1355.68 → 1357.76] and so it was just so bizarre to me.
[1357.98 → 1358.22] Yeah.
[1358.34 → 1360.54] To hear these companies make this statement.
[1360.68 → 1360.80] I,
[1360.84 → 1361.28] I just,
[1361.68 → 1362.12] I,
[1362.12 → 1364.92] I couldn't understand why anyone would believe that.
[1365.02 → 1367.18] So that's actually a very interesting point that when,
[1367.34 → 1369.30] that you're kind of mentally saying,
[1369.44 → 1369.74] look,
[1370.06 → 1371.54] on an 1145,
[1372.66 → 1372.80] the
[1372.80 → 1373.86] the
[1373.86 → 1374.02] the
[1374.02 → 1376.46] the limited resources that that thing has.
[1376.56 → 1376.80] Yeah.
[1377.02 → 1378.78] That effectively is firmware.
[1378.90 → 1379.90] That was firmware.
[1380.16 → 1381.80] We had Unix on it.
[1382.08 → 1384.82] We absolutely know that we can do,
[1384.82 → 1386.38] Unix on a
[1386.48 → 1387.30] certainly on,
[1387.40 → 1387.58] you know,
[1387.58 → 1388.98] given the luxury that we,
[1389.06 → 1389.52] that we have,
[1389.58 → 1390.30] even in the mid-nineties.
[1390.30 → 1392.90] A 40 K instruction space was about all you got.
[1393.04 → 1393.28] Right.
[1393.40 → 1393.92] For Unix.
[1394.14 → 1398.54] And what's interesting when I look at sort of what people want you to do to
[1398.54 → 1401.46] discover interrupt routing today in ACPI,
[1401.46 → 1403.94] which is run the ACPI machine language,
[1404.46 → 1404.96] quote unquote,
[1405.10 → 1407.92] virtual machine to evaluate ACPI bike codes.
[1408.02 → 1409.50] And you can't find interrupts any other way.
[1409.58 → 1409.72] Well,
[1410.30 → 1414.44] the way you did it on those old machines is you basically literally poked a
[1414.44 → 1417.86] register somewhere and waited to be kicked in the ass basically.
[1418.24 → 1419.20] And then you said,
[1419.28 → 1419.48] Whoa,
[1419.56 → 1420.56] I just got an interrupt.
[1420.68 → 1421.90] Wonder what vector it was.
[1422.02 → 1422.20] Oh,
[1422.30 → 1425.02] must be that device that I just poked to interrupt me.
[1425.06 → 1428.40] Because you had no other way to find out what interrupt it was.
[1428.40 → 1429.06] You just didn't.
[1429.26 → 1430.14] And so,
[1430.32 → 1430.46] you know,
[1430.48 → 1434.02] you look at that, and then you look at what vendors come up with today,
[1434.02 → 1437.84] which is megabytes of software to do almost the same thing.
[1438.68 → 1439.04] And,
[1439.14 → 1439.60] you know,
[1440.00 → 1444.64] we've kind of lost a lot of the idea of simplicity.
[1444.64 → 1449.12] And what we tend to go to is every time anything gets a little tricky.
[1449.60 → 1450.96] And I see this all the time.
[1451.46 → 1455.04] The response is we'll put a firmware driver in place to paper over the mess.
[1455.30 → 1455.42] Yeah.
[1455.42 → 1456.34] So we've made a mess.
[1456.34 → 1460.66] Let's put something in firmware to paper over the mess and don't tell anyone.
[1461.24 → 1461.60] Yeah.
[1461.74 → 1462.72] And then it never speaks of it.
[1462.94 → 1467.42] It really kind of takes a lightning bolt to kind of have that simplicity cut
[1467.42 → 1468.52] through all that complexity.
[1468.52 → 1471.64] Because we accept that complexity as endemic and required.
[1471.90 → 1472.12] Right.
[1472.30 → 1473.58] And there's no other way to do it.
[1473.60 → 1473.88] Right.
[1473.92 → 1474.46] And it's like,
[1474.50 → 1474.90] you know,
[1475.20 → 1478.00] you can't do a bias and see because there's no other way to do it.
[1478.12 → 1478.82] You have to do assembly.
[1479.00 → 1479.74] You have to do assembly.
[1479.74 → 1481.54] And it really,
[1481.66 → 1484.34] it's difficult to overcome that inertia and be able,
[1484.64 → 1485.28] and I also,
[1485.46 → 1485.76] it has,
[1485.92 → 1492.28] gives you great reverence for what Ken and co did with Unix in,
[1492.28 → 1497.70] in terms of being able to have such powerful abstractions on such a small
[1497.70 → 1498.02] hardware.
[1498.14 → 1499.22] So it's just limited resources.
[1499.22 → 1500.76] And the key was the abstractions.
[1501.22 → 1501.82] You know,
[1501.88 → 1502.28] it's,
[1502.28 → 1505.92] it's so critical to pick the right abstractions.
[1506.18 → 1506.28] And,
[1506.36 → 1510.90] and this is one thing I think that's a little bit missing sometimes in the
[1510.90 → 1511.62] Linux discussion,
[1512.00 → 1513.62] which is it being,
[1513.62 → 1515.34] it's an absolutely brilliant piece of engineering.
[1515.62 → 1516.94] There's no way of getting around that,
[1517.12 → 1521.42] but there were a lot of competing operating systems to Unix in the early
[1521.42 → 1521.98] seventies.
[1522.24 → 1522.48] You know,
[1522.48 → 1523.46] why did Unix win?
[1523.66 → 1523.86] You know,
[1524.04 → 1525.72] they picked the right abstractions.
[1525.96 → 1526.08] They,
[1526.26 → 1526.38] and,
[1526.38 → 1526.66] and,
[1526.66 → 1527.00] and,
[1527.68 → 1527.98] you know,
[1527.98 → 1531.80] the abstraction was arguably that you could enumerate the resources in,
[1531.86 → 1532.22] in the
[1532.22 → 1533.28] in the namespace,
[1533.32 → 1533.82] so to speak,
[1533.90 → 1535.34] because it was all there in the file system.
[1535.34 → 1536.26] That was really novel,
[1536.36 → 1536.58] right?
[1536.70 → 1540.66] The fact that dev TTY was the thing was incredibly novel.
[1541.30 → 1541.80] You know,
[1541.86 → 1543.56] if you look at Windows NT today,
[1543.68 → 1544.52] there's still sort of,
[1544.58 → 1545.88] you name things with paths,
[1545.90 → 1546.30] but you,
[1546.34 → 1547.74] you can't LS those paths.
[1547.76 → 1548.44] That won't work.
[1548.92 → 1549.28] So,
[1549.42 → 1550.62] so the
[1550.64 → 1552.96] the fact that you could cat a file, and it would be a disc,
[1553.14 → 1553.74] right?
[1553.78 → 1557.32] Or you'd be writing to a printer, or it'd be a tape, or it'd be a real file or a
[1557.32 → 1559.02] TTY, and it didn't matter.
[1559.56 → 1559.88] Right.
[1560.80 → 1565.26] You'd be surprised how often people kind of don't get that point today.
[1566.52 → 1566.92] And,
[1566.92 → 1567.26] uh,
[1567.30 → 1568.14] as it turns out,
[1568.14 → 1569.14] like open read,
[1569.22 → 1569.90] write SEC,
[1569.92 → 1572.18] it's a very powerful abstraction.
[1572.56 → 1572.70] Yeah.
[1572.74 → 1574.04] And being able to,
[1574.10 → 1574.28] we can,
[1574.40 → 1576.04] we can put a lot through that abstraction.
[1576.28 → 1576.38] Yeah,
[1576.38 → 1576.72] we can.
[1577.02 → 1577.22] And,
[1577.30 → 1578.04] and so then,
[1578.34 → 1579.32] so segueing,
[1579.34 → 1579.76] actually you,
[1579.76 → 1580.84] you mentioned plan nine.
[1580.94 → 1583.92] I started hearing about plan nine around 88 or so.
[1583.92 → 1585.48] And,
[1585.62 → 1585.80] you know,
[1585.80 → 1587.32] read all the papers and was just,
[1588.38 → 1589.62] all I can think is this is,
[1589.82 → 1590.84] this is really cool.
[1591.00 → 1592.32] This feels like Unix again.
[1592.52 → 1592.66] Right.
[1593.26 → 1593.78] Bear in mind,
[1593.82 → 1596.80] this is only a dozen or so years after I started using Unix.
[1597.34 → 1597.74] But,
[1597.80 → 1600.92] but then Unix has become a monolith by,
[1601.06 → 1601.30] I mean,
[1601.34 → 1602.22] it's become,
[1602.32 → 1602.42] Oh,
[1602.44 → 1602.82] by even,
[1602.88 → 1603.78] even the late eighties,
[1603.94 → 1604.86] Unix has,
[1604.96 → 1605.26] Oh yeah.
[1605.38 → 1606.28] has diverged.
[1606.36 → 1606.54] I mean,
[1606.54 → 1606.78] it's like,
[1606.78 → 1608.02] it's amazing how,
[1608.24 → 1611.30] just how quickly the pigs were walking on their hind feet.
[1611.52 → 1611.74] Yep.
[1611.74 → 1612.22] Right.
[1612.40 → 1616.98] With respect to the Unix was going to throw out all this complexity.
[1617.34 → 1617.60] And it's,
[1617.60 → 1618.08] you know,
[1618.08 → 1618.46] it's actually,
[1618.60 → 1619.44] it's a little bit,
[1619.56 → 1620.08] I have to say,
[1620.14 → 1623.68] it's a little bit like the microservices' revolution today where microservices came in.
[1623.78 → 1624.02] We're going to,
[1624.28 → 1624.44] you know,
[1624.44 → 1626.12] we're going to throw out all this complexity,
[1626.20 → 1626.62] the monolith,
[1626.70 → 1627.84] we're going to replace it with the simplicity.
[1628.20 → 1628.60] Well,
[1628.62 → 1632.54] it doesn't take too long before that complexity grows again and metastasizes again.
[1632.54 → 1634.04] And the simplicity now is complicated.
[1634.46 → 1634.68] Yeah.
[1634.82 → 1635.20] I mean,
[1635.88 → 1640.66] so at some point the Unix did bring in a few good ideas in the eighties,
[1640.66 → 1642.40] like the idea of a synthetic file system.
[1642.58 → 1643.06] That was key.
[1643.54 → 1643.56] And,
[1643.62 → 1644.48] and if you kind of look,
[1644.62 → 1644.68] I,
[1644.98 → 1646.22] one of these talks I give is,
[1646.22 → 1647.30] you know,
[1647.94 → 1649.22] why did plan nine happen?
[1649.32 → 1651.24] And it's pretty funny.
[1651.32 → 1652.62] If you go back to about 1978,
[1652.62 → 1655.40] when they brought TCP and networking into Unix,
[1655.76 → 1658.60] there were a lot of discussions about how to do that.
[1658.60 → 1661.00] And you actually can find an RFC where someone says,
[1661.06 → 1662.88] let's put it in the file system namespace,
[1663.08 → 1664.18] dev TCP HARD.
[1664.24 → 1665.28] You can actually find that spring,
[1665.40 → 1665.50] right?
[1665.50 → 1665.62] Right.
[1666.20 → 1668.38] But looking back on it,
[1668.48 → 1670.64] we didn't really have the mental model.
[1670.72 → 1673.56] We didn't have the abstractions that would really let us do that.
[1673.96 → 1673.98] And,
[1673.98 → 1680.36] and Rob Pike gave a fantastic talk one time about how you can go wrong kind of
[1680.36 → 1680.70] with,
[1680.70 → 1681.46] with naming.
[1681.74 → 1682.58] For example,
[1683.12 → 1684.40] dev TCP HARD,
[1684.46 → 1685.14] as an example,
[1685.34 → 1688.12] putting a host name in that path didn't actually make sense because the
[1688.12 → 1688.78] question became,
[1688.78 → 1690.94] if I move dev TCP HARD,
[1691.00 → 1692.16] the dev TCP prep,
[1692.44 → 1693.58] which is the MIT machine.
[1695.04 → 1695.82] What does that mean?
[1695.82 → 1696.44] What does it mean?
[1696.58 → 1696.78] Exactly.
[1697.00 → 1697.92] Does that,
[1698.00 → 1699.90] does that mean I disconnect and reconnect?
[1700.28 → 1700.44] I mean,
[1700.44 → 1701.12] what happened here?
[1701.12 → 1701.36] And,
[1701.36 → 1701.56] and,
[1701.56 → 1702.10] and so,
[1702.76 → 1704.16] and weirdly enough,
[1704.16 → 1705.46] I reviewed a paper in,
[1705.64 → 1705.82] in,
[1705.90 → 1706.78] in the two thousands,
[1706.78 → 1707.38] uh,
[1707.38 → 1712.94] that was actually proposing putting networking in a namespace and proposing that
[1712.94 → 1714.52] exact same thing that,
[1714.60 → 1716.10] that if you move dev TCP,
[1716.48 → 1717.50] something to dev TCP,
[1717.50 → 1719.22] be something else that would disconnect and reconnect,
[1719.30 → 1719.62] it was just,
[1719.72 → 1719.88] you know,
[1719.88 → 1720.80] it was just fairly awful.
[1720.98 → 1721.08] So,
[1721.52 → 1721.72] and,
[1721.78 → 1724.68] and so land nine kind of worked really hard.
[1724.68 → 1725.46] And in the nineties,
[1725.56 → 1729.74] I think they got the abstractions right for sort of the namespace model of
[1729.74 → 1730.40] all these resources,
[1730.40 → 1731.74] like your networking stack,
[1731.86 → 1732.24] like your,
[1732.52 → 1732.72] you know,
[1732.72 → 1734.46] your process control and all that.
[1734.78 → 1735.40] But of course,
[1735.44 → 1735.96] by that time,
[1735.98 → 1737.50] it almost didn't matter because Unix,
[1737.66 → 1737.94] you know,
[1738.00 → 1739.38] had owned the world at that point.
[1739.50 → 1739.82] Right.
[1739.90 → 1740.14] And,
[1740.14 → 1740.34] and,
[1740.34 → 1745.36] and basically AT&T kept fouling up the release of plan nine.
[1746.00 → 1746.32] Uh,
[1746.32 → 1747.48] we finally got it right in 23rd,
[1747.50 → 1747.86] 13.
[1747.86 → 1749.58] And by then nobody really cared,
[1749.58 → 1751.22] but we did get it out under GPL,
[1751.32 → 1752.78] but it took like 25 years,
[1752.84 → 1753.08] you know,
[1753.14 → 1753.86] and,
[1753.92 → 1754.28] um,
[1754.62 → 1755.82] funny side story to that.
[1755.88 → 1757.86] And I can tell this tale out of school because every,
[1758.34 → 1760.56] literally most of the people involved are no longer alive.
[1760.56 → 1764.24] But when they were talking to an AT&T about releasing plan nine,
[1764.98 → 1766.82] one of the people no longer alive told me,
[1766.88 → 1767.08] look,
[1767.88 → 1769.18] the reason we didn't release it.
[1769.22 → 1772.86] The way we released Unix is that people at the company at the time were
[1772.86 → 1773.26] saying,
[1773.38 → 1773.90] well,
[1773.92 → 1774.54] look what happened.
[1774.64 → 1775.56] We released Unix.
[1775.64 → 1776.78] We don't want to do that again.
[1776.78 → 1778.24] Meaning from their point of view,
[1778.24 → 1778.60] right.
[1778.70 → 1779.30] They lost control.
[1779.30 → 1779.72] They lost control.
[1779.96 → 1780.08] Right.
[1780.60 → 1780.84] And,
[1780.92 → 1781.10] and,
[1781.10 → 1783.44] and they didn't kind of see that you lost control,
[1783.56 → 1786.20] but you set the standard for like the ages.
[1786.34 → 1786.78] Right.
[1786.90 → 1787.38] Didn't matter.
[1787.64 → 1789.68] And if you had not done that for Unix,
[1790.12 → 1792.48] Unix likely would have died on the vine.
[1792.60 → 1793.66] It had not been from lions.
[1793.86 → 1794.04] And there,
[1794.18 → 1794.32] there,
[1794.42 → 1794.66] I mean,
[1794.66 → 1798.42] I don't see how if Unix had been locked up inside of AT&T,
[1798.64 → 1799.86] I don't know what would be running today.
[1799.96 → 1801.44] I don't know what would be running today,
[1801.44 → 1805.72] but it would be in the confines of interesting systems that no one runs.
[1806.02 → 1806.10] Yeah.
[1806.50 → 1809.66] The abstractions flourished because they were made available.
[1810.04 → 1811.12] And in fact,
[1811.16 → 1812.04] in the late seventies,
[1812.14 → 1815.68] there was a lot of discussion that our future looked like an IBM mainframe,
[1815.90 → 1816.12] right?
[1816.14 → 1818.94] Because there were plug compatibles and IBM was everywhere.
[1818.94 → 1819.66] And we just,
[1819.94 → 1820.28] yeah,
[1820.32 → 1820.70] fine.
[1821.62 → 1824.20] We'd better accept that the future is going to look like,
[1824.20 → 1825.38] an IBM mainframe.
[1825.54 → 1826.12] And then I don't know,
[1826.50 → 1828.24] a lot of people don't remember this,
[1828.38 → 1830.70] but around 1998,
[1830.88 → 1833.40] DARPA announced they would only fund Windows NT efforts.
[1833.78 → 1834.56] Or you were there for that,
[1834.56 → 1834.74] right?
[1834.84 → 1834.86] No,
[1834.90 → 1835.46] I was going to say,
[1835.62 → 1836.94] thank you for mentioning that.
[1836.98 → 1838.14] Cause when you mentioned the mainframe,
[1838.24 → 1840.12] cause that's when I came up in the
[1840.12 → 1840.86] in the mid-nineties.
[1840.92 → 1841.30] And I decided,
[1841.38 → 1844.10] I graduated in 96 and decide that I want to do OS development.
[1844.40 → 1844.60] Yeah.
[1844.72 → 1848.60] And I was told explicitly that the world is going to windows.
[1848.78 → 1848.98] Right.
[1848.98 → 1850.94] So there is only,
[1851.02 → 1852.32] and I have to remind people of this,
[1852.40 → 1854.10] that the reason I went to Sun Microsystems,
[1854.10 → 1859.18] in 1996 is because Sun was the only computer company that believed in Unix.
[1859.44 → 1859.62] Yeah.
[1859.92 → 1860.96] This is before Linux,
[1861.06 → 1861.50] really Linux.
[1861.62 → 1861.72] Yes,
[1861.76 → 1862.54] it existed in 92,
[1862.66 → 1863.76] but like in 1996,
[1863.98 → 1865.24] Linux isn't really a thing.
[1865.48 → 1865.68] Right.
[1866.02 → 1869.52] Unix itself is now viewed because of,
[1869.58 → 1871.86] of these complicated monoliths that it's become.
[1872.28 → 1872.88] It is,
[1873.06 → 1874.36] Unix is dying of its own weight.
[1874.62 → 1874.78] Yeah.
[1874.80 → 1876.98] And everyone is mortgaging their future to Windows.
[1876.98 → 1878.14] But it's interesting to think of that,
[1878.44 → 1882.02] that looked a lot like the IBM mainframe from the late seventies.
[1882.02 → 1882.26] Yeah.
[1882.38 → 1883.24] It should be a mainframe.
[1883.76 → 1885.42] And I feel it's the same way today with AWS,
[1885.66 → 1885.94] honestly,
[1886.10 → 1886.58] where it's like,
[1886.62 → 1888.74] everything should just be on AWS because it's like,
[1888.84 → 1888.98] you know,
[1888.98 → 1890.82] we see this again and again in a test.
[1890.86 → 1891.02] Yeah.
[1891.12 → 1892.28] It happens again and again.
[1892.44 → 1892.54] And,
[1892.58 → 1894.30] and the thing that eventually wins,
[1894.44 → 1894.52] I,
[1895.50 → 1898.96] and I almost for a while had decided I was going to be wrong about firmware.
[1898.96 → 1900.52] And I'm still not sure if I'm going to be right,
[1900.52 → 1903.64] but the thing that's open source tends to win.
[1903.90 → 1904.24] Yes.
[1904.40 → 1907.54] And I don't know what that means for the world we're in today,
[1907.54 → 1909.88] but there really was a period of time.
[1910.12 → 1911.94] I remember at Los Alamos in 2001,
[1912.08 → 1913.02] a physicist said to me,
[1913.06 → 1913.20] well,
[1913.20 → 1915.62] it's all well and good to be playing games with this Linux toy,
[1915.74 → 1918.82] but we've got serious work to do here, and we're doing it on Unix.
[1919.00 → 1919.18] Right.
[1919.26 → 1919.66] And,
[1919.66 → 1921.36] and less than two years later,
[1921.36 → 1924.36] all the major computing infrastructure was Linux based.
[1924.44 → 1924.78] Right.
[1924.78 → 1929.64] So it happened like literally while people were had their backs turned almost.
[1929.78 → 1929.92] Well,
[1929.96 → 1931.14] and I think that people didn't appreciate that.
[1931.18 → 1934.32] What was actually happening is x86 was passing all the risk vendors.
[1934.56 → 1934.82] Yes.
[1935.42 → 1936.50] Nobody expected that.
[1936.86 → 1937.14] No.
[1937.86 → 1938.52] I mean,
[1938.52 → 1941.52] making ASCII ad before multiply operate at,
[1941.56 → 1941.84] you know,
[1942.28 → 1943.32] multiple gigahertz.
[1943.56 → 1943.70] Yeah.
[1943.70 → 1944.90] We never thought we'd see that.
[1945.36 → 1945.48] No,
[1945.54 → 1945.80] nobody.
[1945.98 → 1946.10] And,
[1946.10 → 1948.72] and you have to hand it to Intel.
[1948.88 → 1949.40] Oh my God.
[1949.40 → 1950.94] That's an incredible accomplishment.
[1951.34 → 1951.50] And,
[1951.68 → 1953.12] you know,
[1953.22 → 1953.38] we,
[1953.44 → 1953.64] we,
[1953.82 → 1954.04] in the
[1954.04 → 1954.76] in the 90s,
[1954.78 → 1955.36] you know,
[1955.40 → 1956.06] for a while,
[1956.18 → 1956.38] right.
[1956.46 → 1960.20] Power PC had the higher clock rate and alpha had the amazing high clock rate.
[1960.20 → 1962.34] And we all looked at the x86 and said,
[1962.40 → 1963.42] they're never going to get here.
[1963.48 → 1968.66] And we turned our back and turned around and all of a sudden it just blew right by everybody.
[1968.98 → 1969.58] It was amazing.
[1969.92 → 1971.78] And so you knew you were on the front lines of that happening really,
[1971.86 → 1972.46] because you,
[1972.56 → 1974.64] you guys are very performance sensitive clearly.
[1974.94 → 1975.08] Yep.
[1975.46 → 1976.82] And you're going to,
[1977.06 → 1978.30] whatever is going to be higher performing,
[1978.30 → 1979.86] you're going to use.
[1980.22 → 1980.42] Yep.
[1980.46 → 1981.50] And that was becoming x86.
[1982.00 → 1982.24] Well,
[1982.36 → 1983.66] interesting story about that.
[1983.76 → 1984.32] So we had,
[1984.32 → 1986.78] we had built a cluster at Los Alamos called Q.
[1988.34 → 1990.06] We ended up spending a hundred million,
[1990.50 → 1993.10] $120 million to get 20 teraflops,
[1993.18 → 1994.18] which is nothing now.
[1994.22 → 1995.44] It was a big deal back then.
[1996.06 → 1998.38] About the same year that was being delivered,
[1998.78 → 2001.24] we built an x86 Linux BIOS cluster.
[2002.16 → 2004.20] That for 6 million was 10 teraflops.
[2004.84 → 2004.94] Wow.
[2004.94 → 2008.58] So we essentially showed a few things.
[2008.58 → 2010.44] First is we were about a 10th the price.
[2010.80 → 2012.22] We were the same performance.
[2012.86 → 2014.62] The big machine with the alphas,
[2015.58 → 2016.30] basically the plan,
[2016.36 → 2022.12] the rule at the time was a hundred percent uptime means that you're up maybe all of a week,
[2022.18 → 2024.50] but for a couple of hours while we do plan maintenance.
[2024.50 → 2026.18] So the
[2026.18 → 2027.02] the system we built,
[2027.10 → 2027.90] which we called pink,
[2028.44 → 2029.90] because there was ASCII blue,
[2030.02 → 2030.18] red,
[2030.20 → 2031.02] and white and all this stuff.
[2031.08 → 2031.32] And we said,
[2031.38 → 2031.46] no,
[2031.48 → 2032.20] we're going to call it pink.
[2032.28 → 2033.48] That caused a lot of upset.
[2033.48 → 2034.42] I got to tell you,
[2034.54 → 2035.68] which is why we did it.
[2035.68 → 2038.76] But that basically was up continuously.
[2039.18 → 2041.64] So it had 110 or 20% uptime,
[2042.38 → 2042.56] right?
[2042.68 → 2042.92] So,
[2043.00 → 2044.92] so nobody was expecting that,
[2045.02 → 2045.50] but you know,
[2045.92 → 2047.72] the nodes were Linux BIOS nodes.
[2047.84 → 2048.84] They had no local disk.
[2048.98 → 2049.58] They were just,
[2049.64 → 2050.86] just far,
[2050.96 → 2051.08] far,
[2051.16 → 2053.58] far more reliable than the big expensive machines.
[2054.50 → 2056.02] So the lesson learned there is,
[2056.14 → 2056.36] you know,
[2056.38 → 2056.70] the joke,
[2056.74 → 2058.18] a friend of mine used to make a joke about,
[2058.28 → 2058.48] you know,
[2058.48 → 2061.84] you could buy a smaller disk than this big Cray disk that we used to get,
[2061.90 → 2063.40] but you'd have to spend a lot less money.
[2063.54 → 2064.26] So we would say,
[2064.34 → 2064.50] you know,
[2064.78 → 2065.02] you know,
[2065.02 → 2067.44] you could buy a much better cluster than that thing,
[2067.52 → 2069.08] but you'll have to spend one 10th of money.
[2069.22 → 2069.88] I hope that's okay.
[2069.98 → 2070.16] Yeah.
[2070.20 → 2070.44] Right.
[2070.68 → 2070.84] Well,
[2070.86 → 2071.24] you know what?
[2071.26 → 2072.28] It actually isn't sometimes.
[2072.34 → 2073.02] Sometimes it's not,
[2073.10 → 2073.68] especially with,
[2073.76 → 2073.92] I mean,
[2073.94 → 2075.08] someone who has spent,
[2075.18 → 2075.66] you know,
[2075.70 → 2076.46] a hundred million dollars,
[2076.54 → 2077.58] the taxpayers' money on,
[2077.84 → 2078.74] that's,
[2079.04 → 2081.12] you're not exactly making them look great.
[2081.24 → 2082.12] We weren't making friends.
[2082.12 → 2082.36] So,
[2082.38 → 2083.40] so being in the nineties,
[2083.50 → 2085.60] when I really first got started in a cluster game,
[2085.60 → 2086.54] I went up to,
[2086.72 → 2089.58] let's call it the nameless government agency and said,
[2089.62 → 2090.00] you know,
[2090.88 → 2094.84] about 95% of the cycles on your big vector Cray machines are not vector
[2094.84 → 2096.30] cycles or scalar cycles.
[2096.42 → 2101.12] And I can give you machines for literally a hundred times less money that
[2101.12 → 2104.18] will run just as fast based on commodity workstations.
[2104.40 → 2105.28] Isn't this cool?
[2106.02 → 2108.52] And I realized after I gave the talk that I,
[2108.76 → 2109.96] they were furious with me.
[2109.96 → 2110.38] And I thought,
[2110.38 → 2111.58] why are they so angry with me?
[2111.64 → 2113.12] I'm going to save them a lot of money.
[2113.40 → 2114.34] And then I realized,
[2114.68 → 2114.90] yes,
[2115.04 → 2119.40] that's a bad thing to do in the government because that means that guy's
[2119.40 → 2120.60] budget just got smaller.
[2120.60 → 2125.12] And it also means the fraction of budget that is represented by people just
[2125.12 → 2127.40] got a lot bigger because I've reduced this hard work cost.
[2127.40 → 2128.22] And further,
[2128.78 → 2132.66] the 95% of the people running scalar cycles in a vector machine are paying
[2132.66 → 2133.24] the rent.
[2133.24 → 2136.94] And the 5% of those people can't pay the rent.
[2138.16 → 2143.00] And so that was basically the dagger into the heart of the big vector machines
[2143.00 → 2143.28] was,
[2143.40 → 2143.58] you know,
[2143.58 → 2146.10] started in the early nineties when,
[2146.28 → 2146.44] you know,
[2146.44 → 2147.38] not just me,
[2147.38 → 2152.12] but we started showing that we could take a bunch of rack them stack them,
[2152.86 → 2154.38] spend 40 grand,
[2154.60 → 2159.02] literally 40 grand on my first cluster and outrun for,
[2159.16 → 2160.24] for many important apps.
[2160.24 → 2163.12] We just outran the Cray easily for,
[2163.26 → 2164.78] for apps that you would think would be vectored.
[2165.30 → 2165.58] They were,
[2165.70 → 2166.68] these weren't vector apps.
[2166.80 → 2167.18] That was all.
[2167.52 → 2167.64] Yeah.
[2167.74 → 2167.94] Yeah.
[2167.94 → 2170.86] These were scalar apps and we just left that thing in the dust.
[2170.86 → 2171.26] And,
[2171.26 → 2171.56] and,
[2171.56 → 2173.76] and so the same thing happened with the X86,
[2174.08 → 2174.26] right?
[2174.30 → 2176.76] People were spending hundreds of millions of dollars on,
[2176.84 → 2179.18] on what essentially were commodity clusters.
[2180.04 → 2181.00] And we showed that,
[2181.08 → 2181.16] well,
[2181.16 → 2182.86] if you want to do a commodity,
[2183.00 → 2184.36] get this cheap PC.
[2184.78 → 2185.60] And by the way,
[2186.48 → 2189.36] we are not sensitive to cosmic rays at 7,
[2189.36 → 2190.18] 200 feet.
[2190.24 → 2191.42] The way the alphas were.
[2191.64 → 2194.06] So you'll actually get a more reliable machine because you want to have
[2194.06 → 2195.70] single bit upsets in your L2 cache.
[2196.74 → 2200.18] So we spent less money and got a better machine,
[2200.28 → 2201.34] which was again,
[2201.42 → 2201.76] not a
[2201.76 → 2202.94] not a popular message.
[2204.30 → 2204.78] All right.
[2204.78 → 2205.94] We're going to take a quick break.
[2206.12 → 2206.24] Yeah.
[2206.28 → 2210.54] We're going to be right back with more Ron Min nick and his tales from the
[2210.54 → 2211.46] hardware software interface.
[2211.46 → 2217.64] On the Metal is brought to you by the Oxide Computer Company.
[2218.00 → 2218.24] Well,
[2218.50 → 2219.00] bad news.
[2219.14 → 2220.86] I just got back from a meeting with the attorneys.
[2221.04 → 2221.34] Oh boy.
[2221.52 → 2224.22] They are not going to let us say much in these ads.
[2224.68 → 2228.30] We can't talk about the customer experience today for on-premises
[2228.30 → 2228.86] infrastructure.
[2228.86 → 2228.98] Sure.
[2229.42 → 2231.38] So we can't do my idea to be like,
[2231.46 → 2233.28] are you being gaslit by your vendors?
[2233.28 → 2234.58] Because that's what they're doing.
[2234.70 → 2238.30] They are gaslighting people into thinking that these bugs only exist on one of
[2238.30 → 2240.54] their machines when it exists on like everyone's.
[2240.68 → 2240.84] God,
[2240.88 → 2241.00] no.
[2241.08 → 2241.72] They called that,
[2241.84 → 2242.00] I think,
[2242.10 → 2242.38] quote,
[2242.38 → 2243.22] a third rail.
[2243.46 → 2244.76] They must be following Jess on Twitter.
[2244.88 → 2247.24] I knew that that was a bad idea to let the lawyers follow Jess on Twitter.
[2248.16 → 2251.76] They also said we can't talk about public cloud customer experience.
[2252.18 → 2252.34] Oh,
[2252.38 → 2252.60] come on.
[2252.62 → 2254.28] We can't talk about the rapacious bandwidth pricing.
[2254.38 → 2254.54] I mean,
[2254.54 → 2255.42] it's practically criminal.
[2255.66 → 2255.84] No.
[2256.04 → 2257.50] Can't talk about the unit economics of that.
[2257.62 → 2259.86] Can we use the word criminal with respect to public cloud vendors?
[2260.30 → 2260.96] Definitely not.
[2261.10 → 2261.44] Oh boy.
[2261.56 → 2262.28] What can we do?
[2262.76 → 2262.98] Well,
[2263.06 → 2265.52] they did say they gave us a statement we can use,
[2265.64 → 2266.14] which is.
[2266.24 → 2266.88] Are you going to read from it?
[2266.88 → 2272.14] Oxide Computer Company is building something that should help some people.
[2272.38 → 2272.78] Wow.
[2272.84 → 2274.08] That seems very direct.
[2274.26 → 2274.66] Come on.
[2274.76 → 2276.54] Can we at least send them over to oxide. Computer?
[2276.68 → 2277.06] We can.
[2277.30 → 2277.70] We can.
[2277.84 → 2280.96] The other bit of bad news is all the lawyers were there in the meeting.
[2281.12 → 2281.22] Oh,
[2281.28 → 2281.72] wait a minute.
[2282.06 → 2283.04] Not just the cheap one,
[2283.06 → 2283.86] but the expensive one.
[2284.18 → 2284.40] Yeah.
[2284.48 → 2284.98] They were all there.
[2285.08 → 2287.04] So we paid a fortune to get this terrible ad.
[2287.20 → 2287.72] Oh my God.
[2287.94 → 2291.42] Please listen or go to oxide. Computer and learn what we're actually doing.
[2293.72 → 2294.28] All right.
[2294.38 → 2294.96] We're back.
[2295.74 → 2296.78] So Ron,
[2296.86 → 2298.46] you've just built pink.
[2299.10 → 2299.36] Yeah.
[2299.76 → 2300.48] This cluster,
[2300.48 → 2301.98] which is so good.
[2301.98 → 2307.04] It's profoundly unpopular because it's a dangerous cluster because it is.
[2307.46 → 2309.98] So there are other ways that we cause trouble.
[2310.46 → 2312.34] So remember the VA Linux node,
[2312.42 → 2313.64] he took five minutes to boot.
[2314.52 → 2317.56] So we put software on there that was written by Eric Hendricks,
[2317.64 → 2319.08] who's really neat guy.
[2319.18 → 2319.96] He's at Google now.
[2320.46 → 2321.82] It was called Deep Rock.
[2321.82 → 2323.96] And the way B Proc worked,
[2324.14 → 2326.52] we had a kernel and a demon in flash.
[2326.52 → 2327.72] And then,
[2327.72 → 2328.14] you know,
[2328.42 → 2328.56] it,
[2328.96 → 2329.42] B Proc,
[2330.06 → 2331.30] you'd have a thousand nodes,
[2331.50 → 2332.24] thousand 23,
[2332.44 → 2332.94] to be honest,
[2333.00 → 2334.30] with one node head end.
[2334.40 → 2338.58] And these nodes would come up, and they would all zero in on the home node and say,
[2338.62 → 2339.10] I want to boot.
[2339.10 → 2344.04] And what Eric implemented was this ad hoc tree.
[2344.70 → 2346.76] The first 32 nodes in would be,
[2346.90 → 2347.90] it was like the Godfather,
[2348.04 → 2348.20] right?
[2348.30 → 2348.44] Right.
[2348.56 → 2349.64] I'm going to ask you for a favour,
[2349.70 → 2350.40] or maybe it's like Trump.
[2350.50 → 2350.70] I don't know.
[2350.96 → 2351.10] So,
[2351.14 → 2353.50] so the first 32 nodes in would be said,
[2353.58 → 2354.08] here's the image.
[2354.12 → 2354.54] And by the way,
[2354.56 → 2355.70] I want you to hang around a while.
[2355.70 → 2359.16] Because I'm going to come back and very quickly and ask you to boot other nodes.
[2359.26 → 2359.50] Interesting.
[2360.00 → 2364.20] So now our boot scenario is 32 nodes boots, and they boot 32 more each.
[2364.36 → 2364.90] And now you're up.
[2365.00 → 2366.36] So you're gossiping boot images.
[2366.62 → 2366.88] Yes.
[2367.06 → 2367.38] That's cool.
[2367.70 → 2368.12] That's great.
[2368.24 → 2369.32] It was a beautiful thing.
[2369.32 → 2369.64] And,
[2369.64 → 2371.20] and Eric did the experiment with,
[2371.30 → 2375.48] do we lose IP multicast or point to point turned out point to point always one.
[2375.88 → 2376.70] That is interesting.
[2377.04 → 2377.14] Yeah.
[2377.16 → 2377.72] That is interesting.
[2377.92 → 2379.52] It was not a static layout.
[2379.70 → 2382.02] It was whoever got in the first 32 first.
[2382.40 → 2384.78] They were assigned all that codes available by the way.
[2384.82 → 2385.24] It's on GitHub.
[2385.48 → 2385.72] Yeah.
[2385.82 → 2385.94] Cool.
[2386.00 → 2387.76] And we've been wanting to rewrite it and go.
[2388.00 → 2388.90] Because it's so cool.
[2389.16 → 2389.38] Yeah.
[2389.50 → 2392.52] Trivially easy and go with go routines and channels.
[2393.26 → 2394.18] So we booted,
[2394.38 → 2394.54] right.
[2394.60 → 2396.10] We booted in a minute and a half.
[2396.10 → 2396.42] And,
[2396.42 → 2398.98] and most of that minute and a half was,
[2399.10 → 2399.60] I'm sorry,
[2399.66 → 2400.34] two and a half minutes.
[2400.50 → 2402.14] Most of that time actually was spent.
[2402.78 → 2405.44] Mira net was source routed, and you didn't know the routes.
[2405.54 → 2405.94] And so,
[2406.06 → 2406.98] so the
[2406.98 → 2407.64] the Mira net,
[2408.04 → 2410.56] the Miracom thing that,
[2410.56 → 2412.90] that mapped the network took four hours to run.
[2412.96 → 2413.48] So again,
[2413.54 → 2413.64] I,
[2413.90 → 2416.46] Eric is like Eric Hendricks is one of my like,
[2417.08 → 2417.24] man,
[2417.26 → 2418.52] that guy is smart type guys.
[2418.52 → 2418.80] Right.
[2418.80 → 2425.66] And he wrote his own Mira net configurator that would actually map the whole thing in seven seconds.
[2426.12 → 2426.52] Oh,
[2426.60 → 2426.82] wow.
[2427.14 → 2427.42] And,
[2427.48 → 2427.80] and so,
[2427.88 → 2428.10] okay,
[2428.18 → 2429.82] now we're booting in two and a half minutes.
[2429.90 → 2430.86] Where's a lot of that time spent?
[2430.92 → 2432.86] It's actually spent printing serial messages.
[2432.86 → 2434.18] Because you always want those messages.
[2434.18 → 2435.26] Now we're up.
[2436.26 → 2440.44] Now all these nodes are going to go to the high performance cluster file system.
[2440.44 → 2441.50] We bought from a company.
[2441.50 → 2445.24] I won't name that said it was super scalable and they never,
[2445.46 → 2446.02] please don't be signed.
[2446.12 → 2446.72] Please don't be signed.
[2446.80 → 2447.32] Please don't be signed.
[2447.32 → 2447.36] No,
[2447.44 → 2447.46] no,
[2447.46 → 2447.80] it's not signed.
[2448.16 → 2448.44] They,
[2448.54 → 2455.20] they had never been able to test what happened when a thousand 23 nodes came at their system
[2455.20 → 2456.74] simultaneously and said,
[2456.82 → 2457.92] we're ready to mount now.
[2457.98 → 2458.26] Right.
[2458.72 → 2459.36] You know what happened?
[2459.44 → 2459.56] Oh,
[2459.60 → 2460.28] the software falls over.
[2460.46 → 2460.62] Yeah.
[2460.74 → 2460.92] Yeah.
[2461.22 → 2461.92] You know what got blamed?
[2462.26 → 2462.44] Oh,
[2462.52 → 2462.72] the
[2462.72 → 2462.84] the
[2462.84 → 2464.22] the speed of the boot.
[2464.22 → 2465.20] Of course we got blamed.
[2466.20 → 2467.58] It's a bug in your system.
[2467.58 → 2467.90] Right.
[2468.52 → 2468.64] So,
[2468.82 → 2468.94] and,
[2468.94 → 2468.98] and,
[2468.98 → 2470.94] and even to say it's because you're booting so fast,
[2470.98 → 2472.34] they said it's a bug in your system.
[2473.00 → 2473.32] Right.
[2473.38 → 2473.66] That's crazy.
[2474.18 → 2474.84] And so,
[2474.94 → 2475.20] you know,
[2475.22 → 2477.20] we had to walk through and in the end,
[2477.58 → 2479.52] the really weird thing that came out of this is,
[2479.66 → 2480.58] uh,
[2480.58 → 2483.14] I was talking to somebody from Los Alamos a while ago, and they said,
[2483.42 → 2486.36] they said there are still some bad memories about Linux,
[2486.50 → 2486.80] BIOS,
[2486.88 → 2489.70] and BP ROC because of problems it caused.
[2489.80 → 2490.14] And I thought,
[2490.22 → 2490.40] well,
[2490.40 → 2490.88] what was that?
[2490.92 → 2491.14] Well,
[2491.18 → 2491.94] it was too fast.
[2492.02 → 2492.70] It was too fast.
[2492.84 → 2493.00] Right.
[2493.08 → 2496.24] And it's still some bad blood over the high performance.
[2496.46 → 2497.22] And then further,
[2497.34 → 2499.00] Eric implemented a scheduler that really,
[2499.22 → 2501.42] really took advantage of his BP ROC ideas.
[2502.50 → 2508.60] And he could start a 16 megabyte MPI image in about one to two seconds,
[2508.72 → 2509.08] call it,
[2509.12 → 2512.26] which was only about 60 times faster than anything else.
[2512.36 → 2515.82] And that used the same kind of ad hoc tree for distributing the binary.
[2516.08 → 2516.26] Yeah.
[2516.36 → 2516.70] Interesting.
[2517.00 → 2520.30] So it's still the best cluster system I've ever used,
[2520.30 → 2520.80] bar none,
[2520.80 → 2525.16] because the way his model worked is you would start the process up on the head
[2525.16 → 2527.18] node and then migrate it,
[2527.18 → 2528.74] but it would leave a slot,
[2529.10 → 2530.36] a zombie process slot.
[2530.52 → 2531.66] And when you type PS,
[2531.80 → 2534.02] you saw all your processes on the cluster at the head node.
[2534.46 → 2534.90] Right.
[2534.90 → 2535.86] It was a very,
[2535.94 → 2536.78] very nice model,
[2537.04 → 2537.50] but further,
[2537.74 → 2537.84] he,
[2538.08 → 2538.70] he,
[2538.84 → 2539.06] again,
[2539.14 → 2541.12] he would start his MPI job so quickly.
[2541.12 → 2545.40] They would all go to the quote unquote scalable storage system and crash it.
[2545.46 → 2545.94] And crash it.
[2546.10 → 2546.30] Right.
[2546.62 → 2547.50] So again,
[2547.60 → 2547.72] Oh,
[2547.74 → 2547.96] Eric,
[2548.04 → 2548.24] you've,
[2548.40 → 2549.44] you've done something terrible.
[2549.60 → 2549.76] Well,
[2549.80 → 2550.04] no,
[2550.08 → 2551.86] the terrible thing you did is you're a fast.
[2551.86 → 2554.06] And so I,
[2554.06 → 2554.62] I just,
[2554.70 → 2555.84] there's no way you know about mirror net.
[2555.98 → 2556.34] I would assume.
[2556.34 → 2556.64] Yeah.
[2556.78 → 2557.02] Yeah.
[2557.02 → 2558.22] Yeah.
[2558.22 → 2559.88] Mirror net is one of those things that's kind of lost to history.
[2559.90 → 2561.42] It was obviously big in HPC,
[2561.56 → 2562.00] but it was,
[2562.10 → 2562.32] yeah,
[2562.32 → 2562.82] it was,
[2563.04 → 2563.36] it was,
[2563.36 → 2567.10] it was actually Chuck Switz developed at a Caltech and,
[2567.24 → 2568.00] you know,
[2569.34 → 2570.06] in the night I,
[2570.06 → 2571.30] I first saw a talk on it,
[2571.36 → 2573.36] I guess in 1996,
[2574.26 → 2574.66] maybe.
[2574.92 → 2575.30] And,
[2575.36 → 2575.64] um,
[2575.64 → 2578.08] it was really kind of cool because it was so damn cheap,
[2578.08 → 2581.36] but it was two gigabit network when that was like 20 times faster than
[2581.36 → 2582.44] anything anybody else had.
[2582.74 → 2582.94] Yeah.
[2583.34 → 2585.06] Super low latency port to port.
[2585.44 → 2587.18] It had a lot of really neat ideas.
[2587.44 → 2587.66] All fibre,
[2587.88 → 2588.02] right?
[2588.14 → 2588.66] All fibre.
[2589.18 → 2589.34] Well,
[2589.36 → 2590.16] actually it was cable.
[2590.36 → 2591.26] It actually was copper.
[2591.44 → 2593.54] And the copper was the size of your index finger,
[2593.62 → 2594.10] the connector.
[2594.34 → 2594.50] Oh,
[2594.58 → 2594.74] wow.
[2595.00 → 2595.10] Okay.
[2595.32 → 2595.86] Insanely copper.
[2596.10 → 2596.34] Wow.
[2596.40 → 2596.54] Okay.
[2596.56 → 2597.18] I thought it was a fibre.
[2597.32 → 2597.46] Interesting.
[2597.60 → 2597.78] All right.
[2597.88 → 2599.86] And it had these little neat little routers.
[2599.86 → 2600.34] And the only,
[2600.52 → 2603.90] the only gotcha with the whole thing was the fact that it was a source
[2603.90 → 2604.68] routed network.
[2604.72 → 2607.76] And that meant you had to sort of in parallel,
[2607.76 → 2609.04] everybody had to figure out,
[2609.20 → 2609.30] well,
[2609.32 → 2612.42] what's the topology of my network and then store it as a source route.
[2612.72 → 2613.10] And,
[2613.18 → 2613.34] and,
[2613.38 → 2615.74] and the way it worked is every switch you went through,
[2615.84 → 2620.10] it would rip off the first end bits of your packet and say,
[2620.20 → 2620.38] ah,
[2620.40 → 2621.60] now I know your output port.
[2621.70 → 2622.24] And then,
[2622.38 → 2622.74] you know,
[2622.90 → 2623.90] you're now shorter pack.
[2623.92 → 2624.96] It would go to the next hop.
[2625.40 → 2626.42] It was really cool.
[2626.50 → 2626.78] Right.
[2626.88 → 2627.00] But.
[2627.52 → 2628.22] And simple.
[2628.22 → 2628.48] I mean,
[2628.52 → 2631.68] I remember the thing I was always impressed by is the performance was so
[2631.68 → 2633.30] much better than Ethan at the time.
[2633.52 → 2633.64] Yeah.
[2633.76 → 2636.22] And then you look at the card, and you're like,
[2636.28 → 2636.90] where is it?
[2637.04 → 2637.16] I mean,
[2637.16 → 2638.76] there's just like the card that was very lean.
[2638.96 → 2639.10] Yes,
[2639.16 → 2640.10] it really was.
[2640.18 → 2641.82] There was not a lot on there.
[2641.90 → 2642.20] You're just like,
[2642.24 → 2642.48] wow.
[2643.12 → 2643.46] Okay.
[2643.82 → 2644.34] Why did it die?
[2644.72 → 2644.88] Yeah.
[2645.02 → 2646.24] That's because it,
[2646.34 → 2646.74] I mean,
[2646.86 → 2647.92] ah,
[2648.22 → 2649.04] you know why it died?
[2649.38 → 2649.52] Well,
[2649.52 → 2650.22] it was up against Ethernet.
[2650.28 → 2650.36] I mean,
[2650.36 → 2651.46] it was up against commodity Ethernet.
[2652.12 → 2652.48] Yeah.
[2652.48 → 2652.94] It's interesting.
[2652.94 → 2654.94] It was kind of up against Infinite.
[2655.76 → 2655.96] Yeah.
[2655.96 → 2656.92] I beat you for a while.
[2657.44 → 2657.66] And it,
[2657.88 → 2658.12] and it,
[2658.12 → 2659.98] and to be honest,
[2660.08 → 2661.06] Infinite just had,
[2661.12 → 2662.46] I think more money and,
[2662.46 → 2663.32] and in the end,
[2663.54 → 2664.32] better performance.
[2664.44 → 2664.66] Yeah.
[2664.66 → 2665.12] In the end,
[2665.28 → 2666.68] at least for what people wanted.
[2666.82 → 2669.32] Now there's a guy named Patrick Joffrey.
[2669.78 → 2671.50] Now Google who worked at Miracom.
[2671.70 → 2672.14] Very,
[2672.26 → 2674.72] very smart guy who did a lot of really,
[2674.88 → 2677.20] really nice work in the year of the two thousands.
[2677.54 → 2678.80] And among other things,
[2678.80 → 2681.18] showing that you don't always need OS bypass.
[2681.18 → 2681.38] Yes.
[2682.16 → 2683.74] Really shaped a lot of my thinking.
[2684.04 → 2684.82] But anyway,
[2685.00 → 2686.60] everybody does OS bypass anyway.
[2686.80 → 2689.62] But arguably for some HPC applications,
[2689.82 → 2693.10] Sandra actually showed that Miracom would outrun Infiniband,
[2693.24 → 2698.48] but it really didn't matter because the theory was Infiniband was going to be the Ethernet of HPC.
[2698.62 → 2700.42] There'd be all these vendors selling Infiniband.
[2700.56 → 2700.90] In the end,
[2700.92 → 2701.50] there was only one,
[2701.58 → 2704.84] but there were going to be all these vendors selling Infiniband cards.
[2705.10 → 2705.24] And,
[2705.34 → 2705.48] you know,
[2705.50 → 2707.68] we'd all be happy with our Ethernet of HPC.
[2707.68 → 2707.86] Well,
[2707.86 → 2712.04] it turns out the Ethernet of HPC is probably Ethernet because they all became Ethernet.
[2712.26 → 2713.20] Like if you look,
[2713.30 → 2714.62] Miracom at some point said,
[2714.78 → 2715.52] Oh,
[2715.54 → 2715.96] by the way,
[2716.02 → 2716.16] our,
[2716.16 → 2716.38] our,
[2716.38 → 2717.38] our interfaces do,
[2717.46 → 2717.96] you know,
[2718.14 → 2718.58] Ethernet.
[2718.78 → 2720.54] And then Eleanor after a while said,
[2720.62 → 2720.70] Oh,
[2720.72 → 2721.12] by the way,
[2721.14 → 2722.48] our interfaces do Ethernet too.
[2722.72 → 2723.70] And you really look,
[2723.80 → 2725.32] everybody just converts on Ethernet.
[2725.56 → 2725.64] Well,
[2725.70 → 2725.90] and you,
[2726.02 → 2727.18] even Eleanor today,
[2727.18 → 2728.12] it's very hard for the
[2728.16 → 2730.52] get them to confess that like your Ethernet is actually,
[2730.58 → 2731.12] this is IB.
[2731.32 → 2731.94] Like you actually,
[2732.02 → 2732.24] you've got,
[2732.30 → 2732.54] there's an
[2732.64 → 2735.14] there's IB at the brain stem of a Eleanor card.
[2735.40 → 2735.64] Yeah.
[2735.64 → 2735.92] Well,
[2735.92 → 2736.16] it,
[2736.16 → 2737.92] and I don't know if this is true,
[2738.22 → 2738.86] but I know,
[2738.94 → 2739.84] you know,
[2739.88 → 2740.80] a while back,
[2740.82 → 2744.94] it was the case that the FI for all these networks was the same FI.
[2745.02 → 2745.32] That's right.
[2745.44 → 2745.58] Yeah.
[2745.76 → 2746.78] And it was all licensed.
[2746.90 → 2749.22] It was all licensed from dolphin of all places.
[2749.36 → 2749.58] Right.
[2749.70 → 2750.00] Wow.
[2750.32 → 2750.64] And,
[2750.74 → 2751.38] and you know,
[2751.38 → 2752.22] the weirdest thing,
[2752.26 → 2752.42] I mean,
[2752.42 → 2756.62] dolphin really knows how to do these FI's, and they had a FI for their shared memory network.
[2757.34 → 2759.12] But in the end,
[2759.26 → 2759.60] you know,
[2759.66 → 2760.92] everybody licensed their FI.
[2761.20 → 2761.36] Huh.
[2761.36 → 2762.76] And I was told that was a
[2762.76 → 2763.56] a big,
[2763.64 → 2766.14] good thing for them because people were actually,
[2766.16 → 2768.36] their network was really cool,
[2768.36 → 2771.46] but not as many people bought that as bought their FI.
[2771.96 → 2772.34] Huh.
[2772.42 → 2772.78] So.
[2773.34 → 2773.74] Interesting.
[2774.00 → 2774.26] Yeah.
[2774.38 → 2774.96] And then IB,
[2775.16 → 2775.42] of course,
[2775.48 → 2776.06] was itself.
[2776.22 → 2776.60] Talk about,
[2776.76 → 2776.92] I mean,
[2776.92 → 2777.68] you're talking about the
[2777.68 → 2779.66] the complexity versus simplicity.
[2779.80 → 2780.26] Oh man.
[2780.70 → 2780.90] Yeah.
[2780.90 → 2781.86] I mean,
[2781.86 → 2791.12] we used to joke that the only reason that it was the national labs buying IB because they had the indentured servants in the form of postdocs to actually go configure the thing.
[2791.32 → 2791.56] Yes.
[2791.56 → 2791.92] True.
[2792.12 → 2792.52] So we,
[2792.66 → 2793.24] we actually,
[2793.50 → 2802.28] so one of the Linux BIOS clusters we built in the early 2000s at LANL was the first Option cluster running Linux BIOS as well.
[2802.28 → 2803.66] And it had IB.
[2804.14 → 2808.60] And you may remember back then there was the Intel IQBAL.
[2808.92 → 2809.16] Right.
[2809.42 → 2810.48] And then there was the other one,
[2810.52 → 2811.78] which I've forgotten the acronym for.
[2812.24 → 2813.22] And as delivered,
[2813.36 → 2815.76] that system used IQBAL to bring the network up.
[2815.80 → 2817.42] And then it used the other one to actually do comps.
[2817.52 → 2817.92] It was just.
[2818.16 → 2819.26] Worst of all worlds.
[2819.38 → 2820.02] Worst thing ever.
[2820.02 → 2822.40] And at some point it was,
[2822.54 → 2826.00] I can't describe how much pain that Infinite thing was.
[2826.76 → 2827.24] And,
[2827.34 → 2827.74] you know,
[2827.78 → 2834.92] we had people walking through the spec and realizing at some point spec and code were going to be really,
[2835.10 → 2837.80] really an effort to deal with.
[2838.68 → 2840.90] And at some point what happened,
[2840.96 → 2841.32] and I,
[2841.38 → 2842.50] I really regret,
[2842.58 → 2844.58] I can't get his name in my head right now.
[2844.58 → 2844.74] So,
[2844.74 → 2848.98] we had these two enormous stacks of code.
[2849.50 → 2850.84] And we had a guy from,
[2851.76 → 2852.04] well,
[2852.10 → 2852.82] I'll just say it Intel,
[2852.92 → 2854.34] because you can find a discussion who said,
[2854.44 → 2856.84] we've got this really cool patch,
[2856.96 → 2859.76] the Linux kernel that will give you IB.
[2860.10 → 2862.70] And it's only 280,000 lines or something like that.
[2862.72 → 2863.60] And we just kind of said,
[2863.68 → 2865.42] that is a non-starter.
[2866.24 → 2867.90] This is just not going to happen.
[2868.08 → 2868.56] Oh my gosh.
[2868.70 → 2869.80] But one engineer,
[2870.12 → 2870.82] and again,
[2870.96 → 2871.86] I've known him forever,
[2871.86 → 2873.42] and I'm just blanking on his name,
[2873.42 → 2875.46] just came up and very quietly said,
[2875.72 → 2876.76] I'm starting from scratch.
[2877.54 → 2878.60] Here's my driver.
[2879.26 → 2880.30] It's really compact.
[2880.80 → 2883.34] I'm not really drawing on a lot of this other source code.
[2884.02 → 2887.88] And that is what eventually became sort of the kernel subsystem.
[2888.38 → 2889.30] Somebody just said,
[2889.40 → 2894.64] I realize there are millions of dollars placed in these other two gigantic stacks that are mutually incompatible,
[2894.86 → 2896.44] but this isn't going to work.
[2896.56 → 2896.66] Yeah,
[2896.74 → 2897.24] it's not going to work.
[2897.24 → 2899.26] And it just,
[2899.60 → 2899.82] yeah,
[2899.86 → 2901.60] it's just an example again of,
[2902.40 → 2905.08] sometimes a code base can be so large,
[2905.16 → 2906.66] it might as well be a binary blob.
[2906.78 → 2907.28] Oh my God.
[2907.38 → 2907.62] Right.
[2907.86 → 2909.18] And so sometimes you just say,
[2909.54 → 2911.04] shove it off the table and start clean.
[2911.14 → 2914.26] It's like the Broadcom SDK for the top of rack silicon.
[2914.84 → 2916.96] Someone had told me that it's 14 million lines of code.
[2917.16 → 2917.42] Wow.
[2917.76 → 2919.70] And I went to Robert Moustache,
[2919.88 → 2922.46] who's now an oxide engineer.
[2922.78 → 2923.34] And I'm like,
[2923.48 → 2923.70] Robert,
[2923.86 → 2924.30] 14 million.
[2924.40 → 2924.86] He's like,
[2924.98 → 2926.08] I don't know about that.
[2926.32 → 2927.22] That seems a little light.
[2927.30 → 2927.94] Let me count it.
[2928.66 → 2928.82] Yeah.
[2928.84 → 2929.54] The Broadcom SDK.
[2929.84 → 2930.56] It seems a little light.
[2930.62 → 2931.22] It seems light.
[2931.48 → 2931.68] Okay.
[2931.76 → 2932.10] And it was light.
[2932.20 → 2933.02] It's more than 14 million.
[2933.40 → 2934.24] Oh my gosh.
[2934.64 → 2936.66] And you just have the same thing of like,
[2937.00 → 2937.60] how?
[2938.20 → 2938.62] I mean,
[2938.70 → 2943.00] how do we have this much complexity to enable silicon?
[2943.00 → 2943.50] And you know,
[2943.50 → 2944.44] some of it's for good reason,
[2944.64 → 2945.42] but a lot of it's not.
[2945.42 → 2949.60] A lot of it is just this accretion and then people don't go back to first
[2949.60 → 2950.44] principles and say like,
[2950.50 → 2950.78] okay,
[2950.90 → 2952.38] let's actually write this.
[2952.56 → 2955.20] And this is what I so love about the open firmware movement about like,
[2955.24 → 2955.44] okay,
[2955.54 → 2956.82] what do we actually need here?
[2957.30 → 2961.32] Let's actually start over from scratch and let's build the stuff that we need
[2961.32 → 2965.42] as opposed to the stuff that we have along for the ride for a multi-decade
[2965.42 → 2966.42] long ride.
[2966.90 → 2967.02] Yeah.
[2967.20 → 2967.46] Oh,
[2967.46 → 2968.38] actually I'm a pro that.
[2969.00 → 2972.58] So we may not always be happy with what an individual company is doing,
[2973.08 → 2975.40] but we need to not forget there are perfect people at the time.
[2975.42 → 2975.94] Those companies.
[2976.20 → 2977.32] So just this morning,
[2977.64 → 2978.28] got a note.
[2979.46 → 2983.96] Intel has released firmware for the management engine called ignition.
[2984.88 → 2985.32] Firmware.
[2985.54 → 2985.84] Yes.
[2986.42 → 2986.74] Yes.
[2987.00 → 2987.76] Half a megabyte.
[2988.24 → 2988.66] Yes.
[2988.82 → 2988.90] Well,
[2988.92 → 2992.22] what's really cool is who really spearheaded getting this done?
[2992.84 → 2993.08] Well,
[2993.14 → 2994.44] it was four engineers from Intel.
[2994.54 → 2994.74] Yeah.
[2994.96 → 2995.54] That's amazing.
[2995.84 → 2996.04] Yeah.
[2996.04 → 2996.52] And,
[2996.52 → 2997.78] and they're great guys.
[2997.90 → 2998.78] You can find the note,
[2999.34 → 3000.18] but you know,
[3000.22 → 3000.72] we need to,
[3000.94 → 3003.40] we need to remember that there's some,
[3003.66 → 3003.82] just,
[3004.14 → 3005.44] there are really some terrific people,
[3005.52 → 3007.12] these companies who really are trying to do,
[3007.34 → 3007.60] you know,
[3007.60 → 3008.54] the best thing they can.
[3008.60 → 3009.24] So I confess,
[3009.46 → 3012.76] Jess and I have already read the note as have all of our engineers.
[3012.76 → 3013.44] That note,
[3013.64 → 3016.02] the note this morning about the ignition firmware.
[3016.28 → 3016.44] Yeah.
[3016.48 → 3017.96] That got around the internet very,
[3018.08 → 3021.40] because for the folks that have been watching this space closely.
[3021.80 → 3022.00] Yeah.
[3022.00 → 3027.00] Where the ME has been so tightly held to get anything that is redistributable,
[3027.82 → 3028.84] that is smaller.
[3029.24 → 3029.36] Yeah.
[3029.40 → 3029.82] It's like,
[3030.06 → 3031.14] it's incredible.
[3031.34 → 3031.78] It's incredible.
[3031.94 → 3033.08] And it shows that the
[3033.18 → 3033.72] you know,
[3033.92 → 3036.10] the companies can change, and you've got,
[3036.20 → 3039.64] especially you've got engineers boots on ground that are trying to make the
[3039.64 → 3040.34] right thing happen.
[3040.46 → 3040.68] It's a
[3040.76 → 3042.22] it's a big step forward.
[3042.58 → 3046.94] I would love to hear the organizational kind of battle that they had to get
[3046.94 → 3047.78] into about that.
[3048.26 → 3048.56] Yeah.
[3048.64 → 3049.52] I don't know,
[3049.52 → 3049.82] but I,
[3050.02 → 3051.28] the main thing I know is,
[3051.52 → 3051.60] boy,
[3051.60 → 3051.78] they,
[3051.90 → 3052.34] they,
[3052.46 → 3053.62] they fought the good fight.
[3053.82 → 3054.00] Yeah.
[3054.12 → 3054.38] They did.
[3054.48 → 3054.68] You know,
[3054.72 → 3055.34] it may be,
[3055.62 → 3056.20] because I felt,
[3056.28 → 3057.28] and I don't know that if you felt this way,
[3057.36 → 3060.60] I felt this way for years when you would speak with Intel in particular
[3060.60 → 3061.72] about firmware in particular.
[3062.04 → 3062.20] Yeah.
[3062.24 → 3063.62] Where you are,
[3063.68 → 3063.90] it's like,
[3063.92 → 3067.16] why does American megatrends still exist as a company?
[3067.42 → 3067.66] Why,
[3068.38 → 3068.56] you know,
[3068.56 → 3069.60] this is from my childhood.
[3069.84 → 3070.44] Why are we,
[3070.76 → 3072.26] why is this at the brain stem of humanity?
[3073.00 → 3073.36] And,
[3073.54 → 3073.78] you know,
[3073.80 → 3075.18] you ask Intel about open firmware.
[3075.18 → 3077.00] We were asking as a customer of Intel,
[3077.00 → 3078.34] asking about open firmware.
[3079.26 → 3081.22] Every meeting we would ask about open firmware.
[3081.22 → 3083.58] And every meeting you basically get the same response,
[3083.68 → 3087.50] which is people around the table more or less agreeing with you.
[3087.86 → 3088.18] Yeah.
[3088.18 → 3088.40] I'm like,
[3088.52 → 3088.72] yes,
[3088.86 → 3090.24] I like what you're saying is right.
[3090.48 → 3091.08] You're right.
[3091.24 → 3091.70] You're right.
[3092.00 → 3092.26] Yes,
[3092.30 → 3092.66] you're right.
[3092.72 → 3093.10] You're right.
[3093.18 → 3093.58] You're right.
[3094.02 → 3094.84] But yeah,
[3094.90 → 3095.06] no,
[3095.16 → 3095.30] it's,
[3095.36 → 3095.46] yeah,
[3095.46 → 3096.92] it's just not a decision we're making.
[3096.92 → 3097.44] And we,
[3097.52 → 3097.66] you know,
[3097.72 → 3098.02] we,
[3098.02 → 3099.94] the Intel folks that you're dealing with.
[3099.98 → 3101.88] We had great Intel folks that we were dealing with,
[3102.06 → 3105.30] but they did not feel empowered, and they weren't empowered.
[3105.36 → 3105.50] I mean,
[3105.50 → 3108.12] they didn't feel empowered for a very good reason because they were not empowered.
[3108.34 → 3109.58] And I think that when,
[3109.70 → 3110.08] you know,
[3110.18 → 3112.16] that I've got a question for you,
[3112.16 → 3112.26] Ron,
[3112.32 → 3112.78] because I was,
[3112.90 → 3114.48] just one quick thing again,
[3114.48 → 3116.38] before we beat up on AMI too much.
[3116.38 → 3116.74] Right.
[3116.74 → 3117.06] I mean,
[3117.14 → 3117.92] I admit that,
[3117.92 → 3118.52] you know,
[3118.52 → 3118.76] again,
[3118.76 → 3119.36] in my past,
[3119.54 → 3121.28] it wasn't something I needed,
[3121.28 → 3121.98] but they,
[3122.18 → 3124.72] they do provide a thing that people need.
[3124.94 → 3125.38] So,
[3125.60 → 3125.92] you know,
[3126.08 → 3126.54] I just would,
[3126.62 → 3128.36] I want it not to be a proprietary blob.
[3128.48 → 3130.24] I want it like open source it and,
[3130.24 → 3130.78] and,
[3130.78 → 3132.74] and let's find another revenue model for you.
[3133.38 → 3135.16] But that's what I,
[3135.30 → 3137.16] that's what the issue is.
[3137.16 → 3138.44] I think everybody would be happier,
[3138.66 → 3143.06] especially in light of all the security issues that have popped up in the last
[3143.06 → 3144.50] just five years.
[3144.50 → 3147.24] If all that stack were open source.
[3147.38 → 3148.00] So here's my question.
[3148.00 → 3148.62] What do you trust?
[3148.74 → 3149.40] I'll propose that.
[3149.64 → 3149.82] Yeah.
[3150.36 → 3155.52] I feel that Spectre and Meltdown have helped to accelerate open firmware at Intel.
[3155.66 → 3157.04] I feel that Spectre and Meltdown.
[3157.22 → 3157.40] Yeah.
[3157.82 → 3159.00] It'd be interesting to know your read on this,
[3159.04 → 3165.16] but my read on this is that I saw a real change in Intel after Spectre and Meltdown,
[3165.30 → 3169.54] where they realized that they had totally screwed up.
[3170.42 → 3172.56] And they're very accepting of that, actually.
[3172.56 → 3174.98] And there,
[3174.98 → 3175.98] around security,
[3176.18 → 3176.96] around vulnerabilities.
[3177.28 → 3177.94] And that's when I,
[3178.16 → 3179.46] we began to see the first cracks.
[3179.52 → 3180.66] I began to see the first cracks anyway.
[3180.76 → 3183.78] Maybe you saw the first cracks earlier with respect to accepting open firmware.
[3184.22 → 3184.66] I,
[3184.78 → 3185.46] I'm not sure.
[3186.00 → 3190.14] So I was not a directly involved with any of that.
[3190.34 → 3193.58] The thing I'm seeing is more.
[3193.70 → 3193.92] So,
[3194.04 → 3194.38] so I,
[3194.42 → 3197.72] I started showing people what could be done in,
[3197.72 → 3201.16] by way of bad things in firmware about 20 years ago.
[3201.40 → 3201.42] Oh,
[3201.46 → 3201.76] interesting.
[3201.92 → 3202.04] Wow.
[3202.24 → 3203.88] And the general response.
[3204.10 → 3205.20] What were you showing them 20 years ago?
[3205.22 → 3205.36] I mean,
[3205.38 → 3205.54] I,
[3205.54 → 3206.56] I can only imagine.
[3206.74 → 3206.88] Oh,
[3206.88 → 3207.38] it was a joke.
[3207.50 → 3208.60] I did this thing as a joke.
[3208.70 → 3208.82] I,
[3208.84 → 3209.18] I,
[3209.18 → 3212.24] I turned a machine on, and I ran a program that put the string,
[3212.32 → 3214.12] this is a secret message in flash.
[3214.74 → 3216.66] And then turned it off and turned it on and said,
[3216.70 → 3216.86] look,
[3216.92 → 3217.04] see,
[3217.06 → 3217.64] it's still there.
[3217.74 → 3218.74] And I pointed out,
[3218.84 → 3219.10] you know,
[3219.10 → 3223.58] there are organizations in this world that switch machines between different
[3223.58 → 3224.32] security levels.
[3224.32 → 3224.86] And I said,
[3225.10 → 3226.96] here's how you get bad things out.
[3227.18 → 3229.80] And the general response from everybody was,
[3229.86 → 3230.86] let's not talk about that.
[3230.90 → 3232.46] And it won't happen under windows anyway.
[3232.52 → 3233.60] You can't do that under windows.
[3233.60 → 3235.42] If you have the right service packs and all this nonsense.
[3235.42 → 3235.72] So,
[3235.86 → 3238.32] so I've been trying to get this out for a long time,
[3238.40 → 3239.36] but I think that,
[3239.36 → 3239.74] um,
[3239.78 → 3241.18] you can't do it under windows.
[3241.60 → 3242.00] Serious.
[3242.00 → 3242.96] That was the response.
[3243.12 → 3243.44] It's like,
[3243.46 → 3245.32] I have physical possession of the machine.
[3245.32 → 3245.64] Right.
[3245.70 → 3246.18] I can,
[3246.52 → 3247.28] I can do what I want.
[3247.40 → 3247.62] Right.
[3247.74 → 3248.08] But,
[3248.08 → 3248.66] but again,
[3248.72 → 3249.16] it's just,
[3249.32 → 3250.36] you know,
[3250.36 → 3253.34] the sort of idea that the
[3253.58 → 3256.82] all the biospenders tried to push is our code's perfect.
[3257.28 → 3258.22] This stuff won't happen.
[3258.32 → 3259.22] Don't worry about it.
[3259.38 → 3262.82] Now I see two things that really have pushed this along.
[3263.24 → 3263.72] One,
[3264.42 → 3265.60] maybe my bias here,
[3265.70 → 3270.44] Chrome books have really pushed the idea that actually core boot can work for
[3270.44 → 3271.24] real computers.
[3271.50 → 3271.66] Yeah.
[3271.66 → 3275.86] And I'm hearing more and more about core boot now laptops.
[3276.02 → 3276.36] And of course,
[3276.42 → 3279.68] system 76 got to really give them a nod.
[3279.78 → 3280.14] Totally.
[3280.32 → 3280.66] Fantastic.
[3281.00 → 3281.22] Yep.
[3281.46 → 3282.70] And I know they get a lot of crap,
[3282.84 → 3283.44] but purism,
[3283.72 → 3284.60] be honest,
[3284.68 → 3286.50] did also push on the idea of core boot.
[3286.60 → 3287.22] They're not as,
[3287.28 → 3287.54] you know,
[3287.58 → 3288.52] visible at the moment,
[3288.66 → 3290.04] but system 76,
[3290.22 → 3291.52] actually a few weeks ago,
[3292.20 → 3293.00] pushed commits,
[3293.00 → 3293.70] um,
[3294.20 → 3298.18] for management engine blobs for their laptops.
[3298.34 → 3298.68] That's correct.
[3298.68 → 3299.74] And just for the broader audience,
[3299.88 → 3300.78] whose system 76.
[3301.50 → 3301.94] Laptops.
[3302.16 → 3302.60] Laptops.
[3302.68 → 3303.08] We were going to,
[3303.08 → 3303.46] you know,
[3304.00 → 3304.92] Jess and I were going to,
[3304.92 → 3305.20] uh,
[3305.46 → 3307.06] get you to get a system 76 laptops.
[3307.24 → 3307.70] Get a dart.
[3307.82 → 3307.94] Yeah.
[3307.94 → 3308.82] Look at the darter pro.
[3308.96 → 3309.26] I mean,
[3309.32 → 3310.50] it's really nice.
[3310.56 → 3311.84] They have four K ones.
[3311.94 → 3313.28] The four K one is a bit bulky,
[3313.28 → 3313.84] uh,
[3313.84 → 3314.26] but like,
[3314.32 → 3314.74] I like it.
[3314.80 → 3318.20] And they are unique because they are open for open firmware.
[3318.20 → 3319.72] So a Linux laptop,
[3319.72 → 3320.24] uh,
[3320.24 → 3321.78] they actually have their own OS as well,
[3321.78 → 3323.36] but it's all open firmware.
[3323.50 → 3325.66] So they are not trying to be,
[3325.82 → 3325.90] and,
[3326.24 → 3326.36] and,
[3326.48 → 3330.74] but it's price competitive, and it is feature competitive with other laptops.
[3330.74 → 3331.90] So it shows that it's like,
[3331.92 → 3333.78] it's economically possible.
[3333.78 → 3333.98] I mean,
[3334.00 → 3336.74] they're a kindred spirit, and it will allow me to tinker with my laptop more.
[3337.42 → 3337.60] Totally.
[3337.96 → 3338.10] Well,
[3338.12 → 3339.44] and it will allow you to get at it.
[3339.52 → 3339.72] At a
[3339.82 → 3339.84] at a
[3339.84 → 3340.38] at a
[3340.38 → 3341.84] this kind of like getting,
[3342.00 → 3343.36] and I don't think they're quite at the Chromebook level.
[3343.36 → 3343.52] I mean,
[3343.54 → 3344.96] Chromebook really is amazing in terms of,
[3344.96 → 3345.74] of its ability.
[3345.92 → 3346.64] They're quite incredible.
[3346.86 → 3347.12] Yeah.
[3347.12 → 3348.42] So let me,
[3348.52 → 3349.54] I'm going to run into that.
[3349.60 → 3350.42] So system 76,
[3350.92 → 3355.52] what I like about them is they started from a point of let's do the right thing.
[3356.20 → 3356.54] Okay.
[3356.54 → 3358.58] We're going to build open systems, and they're going to run core boot.
[3358.90 → 3360.36] We're going to figure out how to make that work.
[3360.36 → 3363.04] And they follow the same path that everybody has to follow.
[3363.48 → 3365.98] You're going to get something designed by someone else, and you're going to
[3365.98 → 3367.36] kind of make it work for your needs.
[3367.36 → 3367.68] And,
[3367.68 → 3373.58] and what the folks there I talked to have said is in a lot of ways that the
[3373.58 → 3376.40] the newest ones are the ones where they really had a huge amount of,
[3376.40 → 3376.80] of,
[3376.88 → 3378.38] of impact on the design of,
[3378.42 → 3378.94] and I think it,
[3379.14 → 3380.62] they're just nice units.
[3381.24 → 3382.28] They feel nice,
[3382.32 → 3382.54] you know,
[3382.54 → 3383.10] when you hold them,
[3383.14 → 3383.68] that kind of thing.
[3383.72 → 3384.22] But further,
[3384.42 → 3386.86] I can get clone the corporate repo.
[3386.86 → 3389.38] I can build a firmware image for a system 76.
[3389.50 → 3391.64] I can burn it on that machine.
[3392.04 → 3394.68] So if I'm in a company where I don't want to believe what I,
[3395.08 → 3395.24] you know,
[3395.24 → 3396.70] what might be in the firmware,
[3396.70 → 3398.64] I can just burn it again.
[3398.64 → 3400.26] So this is fascinating to,
[3400.82 → 3405.26] I think anybody who realizes how bad the attacks you can put in firmware are.
[3406.08 → 3407.08] So system 76,
[3407.20 → 3408.40] what's really cool about them too,
[3408.44 → 3412.78] is you got a lot of configurability in terms of how much memory,
[3412.90 → 3414.12] how much NVMe,
[3414.26 → 3414.98] that kind of thing,
[3414.98 → 3416.70] and what distro you run.
[3417.62 → 3420.40] So Chrome books have absolutely,
[3420.62 → 3421.24] in my opinion,
[3421.36 → 3423.04] and I've worked with them for a long time now,
[3423.10 → 3429.70] I've completely and utterly nailed building a thing that when it turns on and puts up a screen that doesn't have a warning on it,
[3429.72 → 3431.46] I can believe it's running the right software,
[3431.58 → 3431.80] right?
[3431.96 → 3432.20] Yeah.
[3432.58 → 3433.32] They really have.
[3433.32 → 3434.58] And further,
[3434.74 → 3435.88] Chrome books have nailed the
[3436.00 → 3436.10] oh,
[3436.18 → 3436.84] by the way,
[3437.20 → 3437.94] you know,
[3437.96 → 3440.30] hold down this magic key combo, and it's yours.
[3440.82 → 3442.18] It's your laptop now.
[3442.28 → 3444.54] Now we will put up a crazy warning screen,
[3444.70 → 3447.26] but then we'll boot to whatever you want to boot to.
[3447.64 → 3448.20] The deep,
[3448.30 → 3450.18] dark secret that nobody knows about Chrome books,
[3450.24 → 3452.02] and I've been trying to give talks about this for years,
[3452.10 → 3453.60] but people still don't know it is,
[3454.16 → 3456.98] you can further take that Chromebook,
[3458.24 → 3460.16] reeky it with your personal key,
[3460.80 → 3462.92] and build an operating system image,
[3463.32 → 3465.32] which you sign with your personal key,
[3465.44 → 3470.44] and that Chromebook from then on will only boot your version of your operating system that you load.
[3470.76 → 3473.72] It won't even recognize Google's operating system as legitimate.
[3474.68 → 3475.02] This is,
[3475.02 → 3475.68] this is the
[3475.74 → 3478.20] this fantastic property of Chrome books,
[3478.26 → 3478.82] which I've been,
[3478.98 → 3483.58] I've been trying to kind of make noise about for years,
[3484.00 → 3484.12] but,
[3484.18 → 3485.12] but I think the system says,
[3485.12 → 3486.38] if there's no way back,
[3486.46 → 3487.72] that may be by the reason that people are,
[3487.82 → 3488.74] you always worry about,
[3488.92 → 3489.12] there is,
[3489.18 → 3491.04] there is no way back when you blow those,
[3491.16 → 3491.36] those,
[3491.50 → 3493.12] and you blow those Google keys out of your Chromebook,
[3493.12 → 3493.78] right?
[3493.82 → 3496.24] You're running your version of Chrome OS or whatever forever.
[3496.42 → 3496.50] But,
[3496.94 → 3500.96] but I think that I kind of feel maybe the system 76 will,
[3501.18 → 3501.44] will,
[3502.08 → 3504.92] will maybe take a little attention to that anyway,
[3504.92 → 3505.74] just because it's so,
[3505.82 → 3507.34] so incredibly configurable.
[3507.44 → 3507.56] And I,
[3507.72 → 3508.38] you know,
[3508.38 → 3509.44] maybe we'll see,
[3509.56 → 3509.92] I don't,
[3510.02 → 3511.22] I don't have any knowledge at all,
[3511.24 → 3512.42] but about this.
[3512.46 → 3513.90] So I'm just going to say hypothetically,
[3514.02 → 3514.34] but it'd be,
[3514.62 → 3514.86] you know,
[3514.86 → 3515.58] maybe down the road,
[3515.58 → 3522.24] we see system 76 picking up those additional properties of Chrome books that make them so incredibly trustworthy.
[3523.74 → 3524.06] But,
[3524.26 → 3524.84] you know,
[3525.00 → 3526.44] in my view,
[3526.52 → 3530.64] and if you kind of look like I worked with some of the early Chrome books in a day,
[3530.76 → 3532.22] some of them at least were sort of,
[3532.74 → 3534.20] here's a laptop we already sell.
[3534.62 → 3536.86] We're going to change that motherboard so it can be a Chromebook.
[3536.86 → 3538.06] But if you look at them today,
[3538.74 → 3540.92] Chrome books are just so incredibly nice.
[3541.66 → 3541.80] You know,
[3541.82 → 3542.54] they have a nice feeling,
[3543.56 → 3543.72] you know,
[3543.76 → 3543.92] okay,
[3543.94 → 3544.34] I'm biased.
[3544.46 → 3545.04] I work at Google,
[3545.04 → 3546.70] but I don't work in Chromebook land anymore.
[3546.70 → 3548.72] And I just think the hardware is just really,
[3548.88 → 3549.46] really sweet.
[3549.90 → 3549.92] No,
[3549.94 → 3551.54] I'm a huge fan of the Chrome books.
[3551.68 → 3552.08] Like I,
[3552.14 → 3552.42] I,
[3552.42 → 3554.66] I tracked that since like 2014.
[3555.02 → 3559.42] And then when I realized that it was open source and I could build Chrome OS myself,
[3559.42 → 3559.96] then I was like,
[3560.00 → 3560.20] oh,
[3560.24 → 3561.14] also it's Gen too.
[3561.14 → 3563.22] And I can make like my own distro based off of it.
[3563.26 → 3566.58] But the experience with Chrome OS is also so good.
[3566.58 → 3567.14] That's like,
[3567.14 → 3568.40] why even do that?
[3568.42 → 3568.82] Honestly,
[3568.98 → 3570.20] especially with the virtualization.
[3570.20 → 3571.30] Now people really love it.
[3571.34 → 3580.36] The only thing that the only reason I don't own a Chromebook today for my work is I miss the ability to throw in a lot of memory and NVMe.
[3580.36 → 3581.92] So in 2012,
[3581.92 → 3586.88] I had a Chromebook that had 16 gigs of RAM and 320 gig of,
[3586.88 → 3587.22] of,
[3587.22 → 3587.70] you know,
[3587.70 → 3588.78] uh,
[3588.78 → 3589.82] flash SSD.
[3590.02 → 3591.62] That's our real laptop in 2012.
[3591.80 → 3591.92] You,
[3592.34 → 3592.54] yeah,
[3592.56 → 3594.00] that was a huge thing,
[3594.04 → 3594.22] right?
[3594.40 → 3594.64] I mean,
[3594.64 → 3595.48] it's a fire breather.
[3595.48 → 3599.06] It literally took about 20 seconds to bring the memory up because it was just right.
[3599.16 → 3599.36] And,
[3599.56 → 3601.22] but I can't do that today.
[3601.26 → 3602.14] I wish I could,
[3602.34 → 3602.86] but I,
[3603.20 → 3603.70] you know,
[3604.20 → 3605.36] for lots of good reasons,
[3605.36 → 3606.72] they're not things you pull,
[3606.88 → 3608.90] you rip open and throw in your own RAM and this,
[3609.02 → 3609.66] but you don't.
[3609.72 → 3610.46] And as in my,
[3610.52 → 3611.22] my only,
[3611.30 → 3612.22] I love the Chrome books.
[3612.30 → 3613.20] The kids all have the Chrome books.
[3613.30 → 3613.58] That's that,
[3613.68 → 3614.58] those are their computers.
[3614.72 → 3614.96] Yeah.
[3615.08 → 3615.36] And the
[3615.36 → 3616.10] and the school,
[3616.18 → 3616.38] they get,
[3616.48 → 3618.86] they all get the Chrome books, and they're so good.
[3618.86 → 3619.22] I,
[3619.22 → 3619.78] I almost,
[3619.92 → 3625.00] I worry that they discourage that kind of experimentation because there are so many conditions in which it's like,
[3625.04 → 3625.16] well,
[3625.64 → 3626.52] now this is not going to boot.
[3627.12 → 3627.48] Um,
[3627.48 → 3628.84] and for good reason,
[3628.98 → 3630.24] but I,
[3630.24 → 3630.68] so my,
[3630.76 → 3631.24] I guess my,
[3631.32 → 3633.66] my only criticism is that they're so good at what they do,
[3633.66 → 3634.04] but I,
[3634.16 → 3636.90] but I do like the ability to actually go install your own thing.
[3636.90 → 3637.16] It's like,
[3637.18 → 3640.28] it does not deprive you of the ownership of your computer.
[3640.64 → 3640.94] In fact,
[3641.06 → 3641.36] um,
[3642.08 → 3647.96] we've had two sets of interns do two different operating systems for Chrome books that aren't Chrome OS's projects.
[3648.08 → 3649.34] The one is called Chrome OS,
[3649.48 → 3651.38] which is kind of the con torment,
[3651.68 → 3653.34] but Chrome OS was based on your roots.
[3653.44 → 3654.34] So all the code was gone,
[3654.42 → 3655.64] the window manager was written in go.
[3656.12 → 3657.48] And in the manner of your root,
[3657.82 → 3658.10] um,
[3658.30 → 3659.44] once you really started booting,
[3659.50 → 3661.64] everything got compiled on first use.
[3661.94 → 3664.62] So that meant the window manager source was there for you to see.
[3664.62 → 3664.80] Now,
[3664.86 → 3666.62] obviously the web browser source wasn't there,
[3666.90 → 3667.92] because it was Chrome,
[3668.04 → 3668.18] but,
[3668.26 → 3670.66] and then the most recent one is called web boot.
[3670.74 → 3674.44] And that will be a system which we've demonstrated for a few,
[3674.74 → 3675.30] well,
[3675.34 → 3678.30] really one distro Chromebook boots and says,
[3678.48 → 3679.52] what distro do you want to run?
[3679.60 → 3680.34] And you might say,
[3680.38 → 3680.68] I don't know,
[3680.74 → 3681.22] tiny core.
[3681.44 → 3683.32] And it knows how to go get tiny core,
[3683.60 → 3684.46] pull it all down,
[3684.72 → 3686.24] pull down a live image kegs that could,
[3686.34 → 3687.18] and now you're running tiny core.
[3687.36 → 3687.50] So,
[3687.62 → 3692.08] so this would be sort of the ultimate stateless device because,
[3692.18 → 3692.50] you know,
[3692.54 → 3692.72] it,
[3692.72 → 3693.44] when it boots,
[3693.54 → 3694.78] it asks you what distro to run.
[3694.78 → 3695.40] And,
[3695.40 → 3695.50] and,
[3695.50 → 3697.18] and the plan is,
[3697.28 → 3698.06] and just,
[3698.44 → 3698.68] you know,
[3698.70 → 3699.02] again,
[3699.02 → 3700.14] this is all intern project,
[3700.22 → 3700.90] all open source,
[3701.34 → 3702.18] nothing to do with Google,
[3702.28 → 3702.46] right?
[3702.50 → 3705.44] It's just that this is good thing for interns to learn how to do systems.
[3706.10 → 3708.06] You might not have a system with no disc in it,
[3708.06 → 3708.28] right?
[3709.04 → 3710.48] And why would you ever do that?
[3710.56 → 3710.74] Well,
[3710.78 → 3711.44] suppose you,
[3711.54 → 3711.80] you,
[3711.84 → 3714.14] you live in a place where you don't want a disc,
[3714.26 → 3714.44] right?
[3714.56 → 3714.70] Yeah.
[3714.76 → 3714.88] There's,
[3715.00 → 3715.12] yeah,
[3715.12 → 3715.96] there are reasons to do it.
[3715.96 → 3716.22] I mean,
[3716.26 → 3718.80] just as there are reasons to have stateless services,
[3718.80 → 3720.42] there are definitely reasons to have a stateless laptop.
[3720.42 → 3721.36] There's a lot to be said for that.
[3721.56 → 3724.18] So I think you could potentially build Joanna Wachowski's,
[3724.18 → 3724.66] um,
[3724.98 → 3727.52] Tails machine based on the Chromebook and web boot.
[3728.20 → 3729.72] It wouldn't be quite her machine,
[3729.86 → 3730.06] but,
[3730.22 → 3730.60] you know,
[3731.34 → 3734.80] we like the idea that you can sort of pick your distro boot by boot.
[3736.00 → 3736.84] There's no state,
[3736.92 → 3738.28] you turn it off and everything's gone.
[3738.54 → 3738.84] Right.
[3738.94 → 3739.18] You know?
[3739.30 → 3739.52] Yeah.
[3739.60 → 3739.76] I mean,
[3739.78 → 3739.96] I,
[3739.96 → 3740.04] I,
[3740.04 → 3741.00] you got to imagine that,
[3741.06 → 3743.40] that there are a lot of three letter agencies that would love to have,
[3743.62 → 3746.72] to know that you're entirely stateless on the laptop.
[3746.72 → 3747.16] Yeah.
[3747.16 → 3747.50] Well,
[3747.54 → 3748.18] actually the
[3748.18 → 3748.62] the one,
[3748.90 → 3754.32] one app that I sort of in partly inspired my interest in it is the case of
[3754.32 → 3754.88] the journalist,
[3754.98 → 3755.52] right.
[3755.58 → 3757.28] Who's in a hotel room or whatever,
[3757.28 → 3758.76] and they're about to get arrested and,
[3758.76 → 3759.82] you know,
[3759.92 → 3762.70] turn off the Chromebook or the web boot device and,
[3762.70 → 3763.24] uh,
[3763.24 → 3763.62] you know,
[3763.78 → 3764.52] everything's gone.
[3764.92 → 3765.08] And,
[3765.08 → 3768.22] and so there are a lot of cases where a stateless device or,
[3768.22 → 3768.68] or,
[3768.68 → 3769.16] um,
[3769.84 → 3770.24] potentially,
[3770.52 → 3770.88] uh,
[3771.66 → 3771.90] you know,
[3771.90 → 3774.46] go beyond just the government agency scenarios.
[3774.98 → 3775.38] Yeah,
[3775.38 → 3775.64] that's,
[3775.68 → 3776.04] that's great.
[3776.04 → 3776.06] All right.
[3776.10 → 3777.18] We're going to take another break.
[3777.36 → 3780.62] We will be back with more on the metal with Ron Min nick.
[3782.30 → 3785.32] On the metal is brought to you by the oxide computer company,
[3785.32 → 3787.18] where we're going to try a new feature,
[3787.56 → 3788.96] shamelessly ripped off of replies.
[3789.18 → 3789.34] Yes,
[3789.38 → 3789.54] yes,
[3789.60 → 3789.80] no,
[3789.88 → 3790.56] where our boss,
[3790.78 → 3792.36] Steve talk brings us a tweet.
[3792.50 → 3792.58] We,
[3792.72 → 3793.62] he does not understand.
[3793.82 → 3795.42] And Jess and I try to explain it to him.
[3795.46 → 3795.60] Steve,
[3795.64 → 3796.18] do you have a tweet?
[3796.76 → 3797.52] I sure do.
[3797.64 → 3798.10] Go for it.
[3798.10 → 3799.54] The tweet in question,
[3800.24 → 3804.56] UEFI reboot network stack engaged the onboard Nick in such a way that it would
[3804.56 → 3805.84] write back DMA.
[3806.04 → 3807.76] Two particular physical memory pages.
[3807.76 → 3810.28] Some time after control was passed to the bootloader,
[3810.46 → 3813.84] corruption would occur somewhere in the user parts of the Ram disc.
[3814.62 → 3816.02] No idea.
[3816.28 → 3816.88] No idea.
[3816.98 → 3817.12] Jess,
[3817.16 → 3817.84] do you understand this tweet?
[3818.50 → 3823.30] So I understand definitely the part about the UEFI reboot networking stack,
[3823.64 → 3826.42] but the part about DMA is in question marks.
[3826.42 → 3827.02] So it's like,
[3827.02 → 3829.66] I guess you're not really sure where that's going.
[3829.66 → 3830.98] You're overthinking it.
[3831.10 → 3832.04] I understand this tweet.
[3832.40 → 3834.26] Running on prem is painful.
[3834.38 → 3835.68] This is dealing with an awful,
[3835.80 → 3837.18] awful firmware bug.
[3837.34 → 3842.88] Firmware has overwritten part of the operating system in a way that is extremely painful to debug.
[3842.88 → 3844.28] So who do you go to in that case?
[3844.38 → 3845.24] Who do you go to?
[3845.34 → 3847.38] You definitely strangle one of your vendors.
[3847.74 → 3848.64] You strangle one of your vendors.
[3848.72 → 3853.48] And unfortunately your vendor is a PC vendor because all the existing computer companies
[3853.48 → 3855.80] are selling personal computers.
[3856.28 → 3858.16] What we need is a new computer company.
[3858.28 → 3859.18] So this is just saying,
[3859.30 → 3862.24] I'm an intense pain trying to run systems on premises.
[3862.46 → 3863.64] That's exactly what it's saying.
[3863.72 → 3863.90] Steve,
[3863.98 → 3866.06] what can someone do if they're in intense pain running on premises?
[3866.38 → 3866.56] Well,
[3866.60 → 3868.64] if someone is running in intense pain on premises,
[3868.64 → 3874.56] what they should do is go over to oxide. Computer to learn a little bit more about how we are going to take that pain away.
[3874.74 → 3876.44] Help is on the way.
[3876.70 → 3878.14] Join us at oxide.computer.
[3878.32 → 3879.48] You are not alone.
[3884.06 → 3884.78] All right,
[3884.84 → 3885.42] we're back.
[3885.82 → 3886.76] So Ron,
[3886.80 → 3890.14] we were just singing the high praises of the Chromebook and,
[3890.14 → 3891.62] and core boot and,
[3891.62 → 3894.48] and then system 76 and what they've done with core boot.
[3895.00 → 3896.94] Where are you seeing open firmware?
[3897.46 → 3898.02] I mean,
[3898.02 → 3900.48] obviously you're in the oxide garage,
[3900.48 → 3902.50] so we're very interested in the server space.
[3902.70 → 3904.08] Where are you seeing it in the
[3904.12 → 3904.80] in the server space?
[3904.84 → 3905.24] Are you seeing,
[3905.36 → 3905.50] I mean,
[3905.50 → 3906.84] obviously there's a lot of interest in it.
[3907.52 → 3910.26] This is a good question because your timing's perfect.
[3910.26 → 3910.82] And in fact,
[3910.86 → 3912.66] especially with the Intel announcement this morning.
[3912.66 → 3914.34] So I'm on the
[3915.08 → 3916.00] I'm on one of the
[3916.00 → 3917.08] it's a very strange name.
[3917.16 → 3919.82] I'm on the incubation committee at open compute platform.
[3920.14 → 3924.60] Which means we evaluate new standards coming in and say yes or no,
[3924.64 → 3927.24] whether they become an OCP thing.
[3927.56 → 3933.86] I was formerly the project leader at the open system firmware project,
[3933.86 → 3936.54] which became officially a project in August of OCP.
[3937.82 → 3942.32] What that project says is that I'll give the end state first.
[3942.32 → 3942.94] March,
[3943.04 → 3943.24] March,
[3943.24 → 3943.86] March,
[3943.86 → 3943.88] 2021.
[3944.76 → 3950.74] If your OCP server wants to have OCP accepted branding,
[3951.74 → 3957.12] it must be possible to purchase an OCP server running open system firmware.
[3957.42 → 3958.28] And further,
[3958.42 → 3963.26] it must be possible for the customer to replace that with their own build of open
[3963.26 → 3968.46] system firmware without asking the ODM for permission or asking the ODM to sign
[3968.46 → 3968.68] it.
[3969.20 → 3969.96] And further,
[3970.20 → 3975.94] it must be possible for you to give that build to someone else or give that
[3975.94 → 3979.32] system to someone else, and they can build and install their own.
[3980.36 → 3981.96] That is actually not possible today.
[3982.12 → 3982.92] Everybody thinks it is.
[3982.94 → 3983.22] I don't think,
[3983.26 → 3983.36] yeah,
[3983.48 → 3985.72] that's not possible by a long shot,
[3985.80 → 3985.90] right?
[3985.98 → 3986.12] Yeah.
[3986.30 → 3986.48] Now,
[3986.56 → 3986.84] now,
[3986.96 → 3988.14] none of those things is possible.
[3988.26 → 3989.84] I've been actually talking to people about this.
[3989.90 → 3992.40] There's this really weird thing coming down the pike at us.
[3992.80 → 3995.58] If I buy a 2012 Facebook server from IT Renew,
[3995.94 → 3996.94] I can do this.
[3997.60 → 3998.02] I can,
[3998.12 → 4001.86] I can build an open system firmware image that ones we build are always based on
[4001.86 → 4002.76] Linux boot and your root.
[4002.82 → 4003.32] It doesn't matter.
[4003.98 → 4004.78] I can burn it.
[4004.92 → 4005.48] It'll work.
[4006.36 → 4006.80] Unfortunately,
[4006.86 → 4009.08] this has led people to believe that this will always work.
[4009.30 → 4010.26] But for example,
[4010.64 → 4013.96] if you buy a Dell server today or an HPE server or whatever,
[4014.74 → 4017.00] and you change one bit of the firmware,
[4017.92 → 4018.78] in the case of the Dell,
[4018.90 → 4020.60] it'll say something horrible has happened.
[4020.78 → 4020.88] You've,
[4021.06 → 4021.28] you know,
[4021.28 → 4023.96] something's happened to my firmware and,
[4024.00 → 4024.58] and it,
[4024.86 → 4025.14] okay,
[4025.14 → 4026.78] it's kind of nice to have this recovery path.
[4026.92 → 4029.94] The BMC will rewrite the firmware and your changes erased.
[4030.24 → 4035.98] And what's happening is coming kind of in this used machine pipeline at
[4035.98 → 4039.96] companies like IT Renew are servers where they can't replace the firmware.
[4040.66 → 4043.98] And our goal is to make that period of time,
[4044.66 → 4044.86] you know,
[4044.86 → 4046.52] you think of a pipeline, and you think of big,
[4046.80 → 4049.74] almost like this pipeline of oil and there's some bad oil in the pipeline,
[4049.92 → 4050.10] right?
[4050.10 → 4054.76] We're trying to make the period of time when those servers can't have their
[4054.76 → 4056.58] firmware replaced as short as possible,
[4056.58 → 4061.16] but we're already kind of behind it because probably starting in the 2017 or
[4061.16 → 4063.80] 2016 years and maybe earlier,
[4063.98 → 4067.82] there are servers that have this thing called boot guard and boot guard is what
[4067.82 → 4068.64] locks you in.
[4069.02 → 4070.38] How does boot guard lock you in?
[4070.38 → 4073.60] There are one-time fuses in,
[4073.60 → 4073.90] in,
[4073.90 → 4075.74] in what's called the peripheral controller hub,
[4075.80 → 4076.40] which is a chip.
[4076.78 → 4079.66] When you blow those fuses that lock in the key.
[4079.98 → 4082.60] And the only firmware that can run on the machine is,
[4082.60 → 4084.28] is firmware signed with the key.
[4084.50 → 4084.60] Right.
[4084.60 → 4086.50] So you get a machine,
[4086.90 → 4088.44] you're not going to update the BIOS period.
[4088.76 → 4088.78] And,
[4088.78 → 4090.20] and our,
[4090.20 → 4091.14] our world,
[4091.20 → 4092.28] the world we all live in,
[4092.34 → 4092.46] the
[4092.46 → 4092.72] the
[4092.72 → 4094.40] the kind of the nerd world,
[4094.50 → 4095.12] let's just call it.
[4095.38 → 4096.80] Nobody really realizes this,
[4096.84 → 4097.04] right?
[4097.10 → 4097.26] People,
[4097.36 → 4099.04] I talk to people, and they say,
[4099.08 → 4099.48] what do you mean?
[4099.52 → 4100.94] I can't load my own firmware.
[4101.08 → 4101.20] I,
[4101.32 → 4102.56] I know how to burn a flash part.
[4102.58 → 4102.90] And I say,
[4102.98 → 4103.20] yeah,
[4103.20 → 4105.30] but you don't have the key to sign that part.
[4105.40 → 4105.62] Right.
[4105.64 → 4106.60] And you are locked in.
[4106.88 → 4108.68] And the actual CPU is not going to execute.
[4108.90 → 4109.72] CPU is not going to execute.
[4109.94 → 4110.10] Yeah.
[4110.52 → 4111.76] This is an Intel construct,
[4111.88 → 4111.98] right?
[4111.98 → 4112.12] Yeah.
[4112.16 → 4112.80] The model is,
[4112.92 → 4113.98] we call the model brick,
[4114.06 → 4114.52] not boot.
[4115.08 → 4115.44] Right.
[4115.94 → 4116.14] Right.
[4116.22 → 4116.54] And,
[4116.64 → 4118.78] and the goal with open system firmware,
[4118.92 → 4120.12] one of our goals is boot,
[4120.16 → 4120.64] not brick.
[4121.04 → 4122.58] That's kind of the Chromebook model.
[4122.58 → 4122.98] Actually,
[4123.08 → 4124.20] Chromebook will always boot.
[4124.48 → 4124.74] It won't.
[4125.06 → 4126.38] I bricked a Chromebook.
[4126.48 → 4127.64] It took a lot of work and,
[4127.84 → 4129.92] and I did things that people don't generally do.
[4130.06 → 4132.08] And it's only one of the ones I ever worked with in,
[4132.12 → 4132.64] in eight years,
[4132.72 → 4132.90] but,
[4133.20 → 4136.96] the model that comes with boot card is you're going to brick.
[4136.98 → 4138.68] If anything looks even a little bit off.
[4138.68 → 4139.02] And that,
[4139.18 → 4139.98] that's the model we,
[4140.26 → 4143.94] we've gotten acceptance from a lot of ACP vendors.
[4144.12 → 4146.68] And we've gotten the support from Intel on this actually,
[4146.68 → 4150.26] that we want to be able to ship systems with their,
[4150.38 → 4151.86] where the users can control the firmware.
[4151.86 → 4152.08] Right.
[4152.24 → 4152.52] And you can,
[4152.60 → 4156.56] you can know who's attested to the firmware, and you should be able to know,
[4156.66 → 4159.60] and you should have a chain of trust, and you should be able to know
[4159.60 → 4160.32] whether you,
[4160.48 → 4162.52] that firmware is from a trusted source or not.
[4162.52 → 4162.96] But yeah,
[4163.10 → 4164.42] the idea that you can't boot.
[4164.92 → 4166.38] And the idea of boot,
[4166.44 → 4167.12] not brick too,
[4167.12 → 4167.82] is that,
[4168.08 → 4168.30] look,
[4168.36 → 4169.58] suppose I have a machine and it,
[4169.58 → 4172.60] and it boots, and it can't attest for some reason.
[4173.64 → 4174.00] It'll,
[4174.00 → 4175.06] it'll contact the thing.
[4175.10 → 4175.70] And the thing will say,
[4175.78 → 4175.94] Ooh,
[4176.12 → 4176.48] you're,
[4176.48 → 4177.04] you're bad.
[4177.04 → 4180.82] You go talk to that other thing that will figure out what's wrong with you,
[4180.82 → 4183.94] but it won't be completely dead.
[4184.10 → 4184.46] Right.
[4184.50 → 4184.80] Which is,
[4184.86 → 4184.98] you know,
[4184.98 → 4185.74] the current model is,
[4185.80 → 4186.82] is things that die.
[4186.92 → 4187.08] Now,
[4187.60 → 4191.00] fact is there are a lot of companies that are perfectly happy with brick,
[4191.06 → 4191.50] not boot.
[4191.50 → 4195.18] So we're not saying you can't sell it at all.
[4195.40 → 4199.32] What we are saying is it has to be possible to buy a machine.
[4199.32 → 4200.80] It follows this boot,
[4200.84 → 4201.34] not brick,
[4201.52 → 4203.00] use your own firmware model.
[4203.76 → 4205.10] The fuses aren't blown.
[4205.28 → 4205.46] The few,
[4205.56 → 4207.24] we would prefer the fuses not exist.
[4207.54 → 4207.70] Right.
[4207.80 → 4209.14] One time fuses like that,
[4209.24 → 4209.92] that's a problem.
[4210.18 → 4210.54] It's a problem.
[4210.62 → 4211.70] And especially when there are,
[4211.78 → 4216.42] then it's especially gutting when there are vulnerabilities found in the
[4216.42 → 4217.42] mechanism itself.
[4217.58 → 4217.80] Yep.
[4218.32 → 4219.46] Where it turns out it doesn't even work.
[4219.62 → 4219.78] I mean,
[4219.88 → 4220.64] you can like,
[4220.78 → 4222.98] so the bad guys can find their way around it.
[4223.06 → 4223.46] It's like,
[4223.80 → 4225.12] this is just punishing.
[4225.60 → 4227.30] I've heard a lot of stories about,
[4227.34 → 4227.80] you know,
[4227.90 → 4228.96] organized crime and,
[4229.00 → 4229.24] and,
[4229.24 → 4230.30] and this kind of vulnerability.
[4230.30 → 4230.90] I've heard,
[4230.90 → 4236.94] I've been told that the way it was told to me by a faculty member from
[4236.94 → 4238.04] ETH is you,
[4238.20 → 4238.38] you,
[4238.54 → 4239.54] if you've seen Marcos,
[4239.68 → 4243.56] you might go somewhere now, and you look at this big old barn, and you'd
[4243.56 → 4243.74] think,
[4243.80 → 4243.92] Oh,
[4243.94 → 4244.20] there's,
[4244.40 → 4246.50] there's a drug manufacturing facility in the barn.
[4246.84 → 4247.42] He said,
[4247.44 → 4247.56] no,
[4247.58 → 4253.68] you go in, and you're going to find four E beam, and they do recapping and
[4253.68 → 4255.32] they can find vulnerabilities in chips.
[4255.46 → 4256.74] That's the big money thing.
[4256.92 → 4257.32] Right.
[4257.48 → 4257.66] Right.
[4257.66 → 4258.02] And that,
[4258.02 → 4258.60] that just,
[4258.70 → 4260.30] just knocked me on my heels.
[4260.44 → 4260.76] I didn't,
[4260.90 → 4261.28] I didn't even,
[4261.72 → 4263.88] he had to explain to me what he was talking about at first.
[4263.96 → 4264.20] Because I thought,
[4264.26 → 4264.50] what do you,
[4264.72 → 4265.26] what do you mean?
[4265.88 → 4267.64] But there's a lot of money in,
[4267.64 → 4271.10] in recapping and working out what's in a chip and finding these
[4271.10 → 4271.48] vulnerabilities.
[4271.66 → 4275.04] And so the two arguments I kind of make for this is first off,
[4275.14 → 4279.02] there are a lot of really smart people at a company like Intel or AMD or
[4279.02 → 4279.18] ARM,
[4279.20 → 4279.46] whatever,
[4279.64 → 4282.58] huge numbers of really smart people trying to solve these problems.
[4282.72 → 4287.06] The problem is there are way more smart people out in the world and
[4287.06 → 4288.70] they only got to succeed once and they're in.
[4288.96 → 4289.08] Yeah.
[4289.08 → 4292.22] So we're trying to get to a world where,
[4292.22 → 4292.70] you know,
[4293.60 → 4296.80] servers come with user controlled ability to control,
[4296.94 → 4298.68] to build and burn our own firmware.
[4299.48 → 4301.84] We can get much faster turnaround on vulnerabilities.
[4302.62 → 4304.84] We're all of us empowered to find vulnerabilities.
[4305.08 → 4306.82] We want the good guys looking for vulnerabilities,
[4307.02 → 4307.90] not just the bad guys.
[4307.98 → 4308.22] Right.
[4308.22 → 4309.60] And that can only happen if,
[4309.60 → 4310.64] if the firmware is open.
[4310.78 → 4310.90] Yep.
[4311.36 → 4312.00] And finally,
[4312.00 → 4313.40] we want a world where when,
[4313.50 → 4314.18] when we're done,
[4314.18 → 4317.78] when Facebook or whoever is done with a server and Facebook is doing this
[4317.78 → 4318.08] already,
[4318.08 → 4320.16] actually they can cart,
[4320.38 → 4320.88] you know,
[4320.88 → 4324.70] just put those servers on a cargo pallet and ship them to a company like
[4324.70 → 4325.28] it renews.
[4325.28 → 4329.34] And it renews refers them, and they sell them on the places that can't afford the
[4329.34 → 4330.08] new version of that.
[4330.18 → 4331.36] It's still a perfect machine.
[4331.62 → 4333.10] That's what it renews has been doing.
[4333.34 → 4337.76] So we want that to continue.
[4337.88 → 4339.14] It's called circular economy.
[4339.36 → 4341.40] It's a big thing in the world now.
[4341.40 → 4345.24] And I've been in on some of these meetings with various organizations and my,
[4345.42 → 4345.60] you know,
[4345.62 → 4345.86] my,
[4346.14 → 4349.60] I feel like Cassandra sometimes just saying,
[4349.74 → 4353.58] you've got a problem with this model coming at you.
[4354.06 → 4354.48] Yes.
[4354.50 → 4357.10] We've been able to recycle 2012 servers,
[4357.30 → 4360.30] but we're going to have a big problem about five years.
[4360.76 → 4361.84] We're going to get servers.
[4361.96 → 4363.70] We can't rewrite the firmware on.
[4363.76 → 4366.20] And we are to be honest in,
[4366.44 → 4366.52] well,
[4366.52 → 4367.72] we're in a lot of trouble at that point.
[4367.88 → 4367.98] Right.
[4367.98 → 4368.18] So,
[4368.32 → 4369.76] so we're trying to,
[4369.76 → 4372.66] there's going to be a period of time when we're going to get these boot
[4372.66 → 4374.42] card enabled things, and we can't do it,
[4374.48 → 4376.36] but we're hoping that post March,
[4376.48 → 4376.84] 2021,
[4377.18 → 4378.30] that won't be a problem.
[4378.64 → 4379.10] Now we have,
[4379.40 → 4380.98] I'm talking to companies today.
[4381.70 → 4381.88] March,
[4382.00 → 4385.02] 2020 is an aspirational target,
[4385.20 → 4388.84] which means companies will optionally provide those.
[4389.72 → 4391.36] So you'll have a list in March,
[4391.46 → 4391.84] 2020,
[4392.00 → 4394.26] there are companies that are going to come to the OCP summit.
[4394.92 → 4396.52] They're going to wave the flag and say,
[4396.68 → 4399.74] we will sell you a machine today with open system firm.
[4399.76 → 4401.20] We're not required to,
[4401.86 → 4403.02] but we're ready to do it.
[4404.22 → 4404.34] And,
[4404.42 → 4408.30] and to get back to the Intel ME firmware release of this morning,
[4408.44 → 4411.66] that is like the critical piece of all this.
[4411.96 → 4412.02] So,
[4412.02 → 4414.24] so Intel a year ago,
[4414.58 → 4415.14] you know,
[4415.20 → 4415.36] they,
[4415.50 → 4416.86] they said they're going to help us.
[4417.28 → 4420.92] They put the FSP firmware support package blobs on GitHub,
[4420.92 → 4422.76] along with their microcode.
[4423.28 → 4425.44] The license is a fantastic license,
[4425.78 → 4425.98] right?
[4426.02 → 4430.62] You can build that FSP blob into your firmware, and you can redistribute it,
[4430.70 → 4431.38] knock yourself out.
[4431.50 → 4431.62] Right.
[4431.72 → 4432.72] And so not open source,
[4432.84 → 4433.30] but freely distributable.
[4434.04 → 4434.18] Right.
[4434.18 → 4434.80] And you've got the binary.
[4435.00 → 4435.14] Right.
[4435.24 → 4435.78] Binary blob,
[4435.96 → 4437.26] but it's a big step forward.
[4437.40 → 4438.56] It's something you can redistribute.
[4438.56 → 4440.46] And the last piece in the chain,
[4441.04 → 4442.60] and notice it wasn't for every chip set.
[4442.70 → 4443.28] It doesn't matter.
[4443.38 → 4443.88] It's a start.
[4444.00 → 4444.74] It's for one chip set.
[4444.82 → 4448.20] The last piece in this chain has been the ME binary blob.
[4448.84 → 4452.88] What I'm really delighted about is they not only released that blob,
[4452.98 → 4455.58] they released the ignition variant,
[4455.78 → 4457.18] which is just half a Meg.
[4457.58 → 4457.76] Yeah.
[4457.80 → 4458.42] That is great.
[4458.60 → 4459.38] And I did not,
[4459.48 → 4460.62] I had not heard of that.
[4460.86 → 4463.82] Is ignition an internal Intel project?
[4463.90 → 4464.94] I had not heard of it until this morning.
[4464.94 → 4466.46] I've only just seen it in their,
[4466.92 → 4467.08] in,
[4467.16 → 4467.52] you know,
[4468.04 → 4468.42] Isaac,
[4469.44 → 4470.30] or it wasn't Isaac.
[4470.42 → 4471.34] It was another guy,
[4471.46 → 4474.80] but wrote it up, and they explained what it was in that release.
[4475.16 → 4476.86] And you'd have to read their thing,
[4477.00 → 4479.14] but I just read it enough to say,
[4479.22 → 4479.38] okay,
[4479.46 → 4479.74] ignition,
[4479.88 → 4480.50] it's a half Meg.
[4480.60 → 4480.84] Great.
[4481.22 → 4481.54] And,
[4481.74 → 4481.96] you know,
[4482.04 → 4483.86] if it's a half me gas opposed to three Meg,
[4483.96 → 4485.42] it's got to be doing a lot less stuff.
[4485.44 → 4485.64] Right.
[4485.64 → 4486.70] It's got to be doing a lot less stuff.
[4486.86 → 4487.08] Right.
[4487.12 → 4488.62] I'm assuming the web server's gone.
[4489.40 → 4489.54] Right.
[4489.92 → 4490.22] No,
[4490.24 → 4491.70] there's a lot of horrifying things there in,
[4491.70 → 4493.44] in the ME and in SMM too,
[4493.52 → 4493.66] right?
[4493.68 → 4494.60] In system management mode.
[4494.60 → 4494.76] I mean,
[4494.76 → 4495.18] that's the other,
[4495.28 → 4498.42] I know that's been something you've been working with a risk five folks to
[4498.42 → 4500.90] make sure they don't repeat some of the same mistakes.
[4501.28 → 4502.18] Didn't work out.
[4502.82 → 4503.90] But really,
[4504.16 → 4506.86] so it didn't work out yet.
[4506.94 → 4507.16] You know,
[4507.24 → 4510.36] I think you've got to be an optimist given how much you've been able to,
[4510.36 → 4511.40] to triumph over.
[4512.24 → 4512.60] Yeah.
[4512.70 → 4514.94] We're so let's see.
[4515.28 → 4520.44] Let me mention Intel has been proposing getting us out of the SMM box room.
[4520.44 → 4521.76] The new thing called PRM.
[4521.86 → 4523.56] We're talking again,
[4523.66 → 4524.76] the person doing that.
[4524.84 → 4525.68] I wish I could not,
[4525.80 → 4527.40] I wish I weren't blanking on his name.
[4527.46 → 4527.94] I'm sorry,
[4528.06 → 4529.42] but he's real good guy.
[4529.50 → 4533.86] And we're hoping to be done with SMM here in the next little while.
[4533.96 → 4534.38] That'd be great.
[4534.46 → 4534.60] Cool.
[4534.84 → 4535.06] Yeah.
[4535.06 → 4535.98] You can look at,
[4536.24 → 4536.56] he's given,
[4536.62 → 4536.98] I talk,
[4537.06 → 4539.12] I think at OCP about it, and it looks good.
[4539.24 → 4539.62] That's good.
[4539.62 → 4540.90] And I mean,
[4540.98 → 4542.00] just your paper on,
[4542.14 → 4542.44] I mean,
[4542.44 → 4545.50] you talked about SMM in your various ring paper.
[4545.68 → 4545.86] Yeah.
[4545.94 → 4546.30] So,
[4546.36 → 4546.58] I mean,
[4546.58 → 4547.44] what did you learn about it?
[4547.48 → 4547.70] I mean,
[4547.78 → 4549.86] for those folks who are learning about SMM,
[4549.94 → 4551.54] do you want to give them an explanation for?
[4552.44 → 4552.70] Yeah.
[4552.86 → 4554.70] Stands for system management mode.
[4555.18 → 4555.54] Ideally,
[4555.72 → 4559.00] like they wouldn't have shoved so many features in there,
[4559.00 → 4560.74] but a lot of vendors tend to do that.
[4560.78 → 4561.42] It seems like,
[4561.58 → 4563.64] so it becomes very bloated.
[4563.96 → 4564.12] Steve,
[4564.12 → 4566.24] this is like the Steve test.
[4566.40 → 4566.72] I am.
[4567.12 → 4567.38] All right,
[4567.40 → 4568.60] then we're not going to talk about it.
[4568.68 → 4569.00] All right.
[4569.72 → 4570.04] No,
[4570.12 → 4570.32] I mean,
[4570.36 → 4570.76] not that,
[4570.80 → 4571.64] not that you're the.
[4572.50 → 4572.84] Actually,
[4573.06 → 4573.94] it's fascinating.
[4573.94 → 4575.08] If you think about PCs,
[4575.42 → 4576.76] all this stuff,
[4577.08 → 4577.50] SMM,
[4577.58 → 4579.66] all this stuff is an answer to the question.
[4580.12 → 4581.76] How do I keep supporting DOS 1.0?
[4582.18 → 4582.40] Yes.
[4582.66 → 4582.82] And,
[4582.82 → 4588.14] and so if I close the lid on the laptop and I want to do a sleep thing and DOS 1.0 doesn't know anything about sleep,
[4588.24 → 4589.22] how will I implement that?
[4589.26 → 4590.14] That was the answer.
[4590.22 → 4593.88] What is your talks where SMM has mouse drivers?
[4593.88 → 4594.32] Yes.
[4594.32 → 4594.70] It's a
[4594.70 → 4595.00] yes.
[4595.00 → 4598.76] SMM has a USB mouse,
[4598.86 → 4599.60] USB keyboard.
[4600.06 → 4600.78] You would,
[4600.86 → 4603.42] you would really be amazed at what all goes in there.
[4603.54 → 4604.04] It's crazy.
[4604.54 → 4605.22] It is just terrifying.
[4605.36 → 4605.62] But again,
[4605.70 → 4607.14] that's why in,
[4607.34 → 4607.58] again,
[4607.66 → 4607.94] in the
[4608.00 → 4609.30] in the late nineties,
[4609.30 → 4610.48] I could get a laptop,
[4610.48 → 4613.62] I could run an operating system that didn't have USB support.
[4613.76 → 4615.68] I could plug in a USB mouse and it would work.
[4615.76 → 4616.06] Right.
[4616.32 → 4616.80] SMM.
[4617.16 → 4617.36] So,
[4617.92 → 4618.28] you know,
[4618.42 → 4620.84] all this stuff arguably has a good,
[4620.92 → 4621.82] has a good purpose,
[4622.08 → 4622.16] but,
[4622.34 → 4622.54] but,
[4622.70 → 4623.50] but in the long run,
[4623.52 → 4623.94] it's just,
[4624.02 → 4624.72] it's just deadly.
[4624.80 → 4625.04] Yeah.
[4625.10 → 4625.32] Right.
[4625.84 → 4627.78] Especially in a data centre who needs a mouse.
[4628.00 → 4628.20] Yes.
[4628.20 → 4628.54] Oh yeah.
[4628.90 → 4629.32] Well,
[4629.32 → 4630.78] and it's surface area.
[4631.48 → 4631.88] Honestly,
[4632.20 → 4635.44] you would not believe how many of these like recovery schemes for.
[4635.62 → 4636.24] Oh really?
[4636.66 → 4638.08] Server nodes involve a mouse.
[4638.76 → 4640.14] Actually this cupboard I have,
[4640.20 → 4641.98] which is teeny tiny $99 a board.
[4642.12 → 4643.84] I found out in the BIOS,
[4643.98 → 4646.22] there is a graphics and mouse driver.
[4646.72 → 4648.20] And one of the things the mouse driver uses,
[4648.40 → 4648.78] it allows you,
[4648.86 → 4650.60] it gives you a little keyboard, and you click buttons.
[4651.02 → 4651.78] Oh my gosh.
[4652.00 → 4653.60] What is a mouse driver doing in this thing?
[4653.80 → 4654.00] Oh,
[4654.18 → 4655.14] it's for the keyboard.
[4655.26 → 4655.32] Oh,
[4655.32 → 4655.86] that makes sense.
[4656.28 → 4658.88] And it's a different mouse driver than an SMM.
[4658.88 → 4659.94] It's a USB mouse driver.
[4660.04 → 4660.20] I mean,
[4660.32 → 4661.08] a UFI mouse driver.
[4661.48 → 4661.94] So getting back,
[4662.06 → 4662.74] getting onto RISC-V.
[4663.56 → 4663.80] Yeah.
[4663.86 → 4665.78] I wanted to mention that because I'm really glad you brought up.
[4665.88 → 4668.70] So I've been a little bit disappointed lately to see,
[4669.00 → 4670.88] I guess I understand it,
[4670.92 → 4673.90] but to see kind of the UEFI port to RISC-V.
[4674.10 → 4674.32] Yeah.
[4674.48 → 4676.30] We did the core boot port in 2014,
[4676.82 → 4677.24] 2015,
[4677.48 → 4677.84] 2016,
[4677.98 → 4678.38] 2017.
[4679.14 → 4680.56] I got out of it at that point,
[4680.64 → 4683.08] but other people have done it in 2018 and 2019.
[4683.88 → 4684.34] And I,
[4684.34 → 4684.64] I,
[4684.64 → 4686.22] I kind of,
[4686.58 → 4688.86] I've been told that the reason to do UEFI,
[4688.88 → 4690.30] UEFI is because Linux wants it.
[4690.50 → 4692.18] That's the claim that's been made to me.
[4692.42 → 4692.96] That seems,
[4693.02 → 4693.76] that seems crazy.
[4693.90 → 4694.50] That seems crazy,
[4694.62 → 4696.18] but that seems crazy.
[4696.30 → 4696.48] I mean,
[4696.48 → 4697.24] given that like,
[4697.42 → 4698.02] that seems,
[4698.80 → 4699.48] wait a minute.
[4699.48 → 4700.06] That seems,
[4700.16 → 4700.28] no,
[4700.34 → 4700.46] no.
[4700.54 → 4700.82] I like,
[4700.94 → 4701.58] that seems wrong.
[4701.68 → 4702.44] I am,
[4702.68 → 4703.20] but like,
[4703.32 → 4704.64] like it just seems like,
[4704.70 → 4705.94] it is just like perverse.
[4706.18 → 4709.40] Linux hated UEFI as much as every other non-Windows system.
[4709.40 → 4709.70] No,
[4709.70 → 4710.10] but well,
[4710.20 → 4711.42] but Linux is pretty corporate now.
[4711.42 → 4711.66] Right.
[4711.74 → 4711.92] And,
[4711.92 → 4713.36] and it's like Linux didn't want,
[4713.50 → 4713.74] I mean,
[4713.74 → 4713.90] the
[4713.90 → 4716.32] the excuse was that we need UEFI because Windows wants it.
[4716.32 → 4718.56] And now we want UEFI because Linux wants it.
[4718.56 → 4718.84] And,
[4718.92 → 4719.28] and I,
[4719.34 → 4720.24] I have a friend at arm.
[4720.32 → 4720.46] I,
[4720.54 → 4720.96] I was,
[4721.08 → 4723.02] I was pushing hard on him about why are,
[4723.24 → 4726.06] why am I only hearing about UEFI from arm nowadays?
[4726.06 → 4726.50] And he,
[4726.66 → 4727.38] he said,
[4727.42 → 4728.04] because Linux.
[4728.18 → 4728.52] And I said,
[4728.84 → 4729.10] what,
[4729.34 → 4729.54] what?
[4729.66 → 4730.04] He said,
[4730.08 → 4730.24] well,
[4730.28 → 4731.80] Linux requires UEFI.
[4731.80 → 4732.60] Or that was,
[4732.82 → 4733.34] that's their,
[4733.44 → 4734.08] their argument.
[4734.52 → 4737.54] I ought to mention that we,
[4737.68 → 4742.36] I have been looking at some arm boards that run UEFI, and we're pretty close to being able to say,
[4742.50 → 4746.42] not that we will add Linux kernel to UEFI the way we do on x86,
[4746.68 → 4750.44] but that we will completely replace UEFI with a Linux kernel and U root.
[4751.20 → 4751.64] And,
[4751.76 → 4752.92] and it's just gone.
[4753.26 → 4753.44] Right.
[4753.78 → 4754.10] And,
[4754.18 → 4755.00] and that's,
[4755.00 → 4756.70] that's kind of where we want to be.
[4756.82 → 4758.18] But now getting to risk five,
[4759.04 → 4759.28] there,
[4759.44 → 4761.22] there are some aspects of risk five that,
[4761.22 → 4764.80] I've always been not exactly thrilled with.
[4764.84 → 4769.82] One is called the open SBI because it's basically a classic BIOS interface.
[4770.12 → 4772.18] And I don't know why you would do those.
[4773.10 → 4775.36] There are a few architectural hooks in,
[4775.36 → 4783.00] in the risk five nowadays and more recent models that explicitly sort of enabled the SMM model on the risk five.
[4783.00 → 4790.08] Which is tragic because I think that risk five has done such a good job of learning from all the microprocessor mistakes from an instruction set perspective.
[4790.28 → 4790.36] Yeah.
[4790.36 → 4790.88] I mean,
[4790.90 → 4791.92] they've really done an
[4792.02 → 4794.54] a very admirable job of like,
[4794.88 → 4798.54] here's what MIPS did wrong and here's what Spark did wrong and what Power did wrong.
[4798.54 → 4799.08] And it's,
[4799.22 → 4799.40] you know,
[4799.42 → 4801.08] and not repeating those mistakes.
[4801.32 → 4801.54] Yeah.
[4801.78 → 4801.96] They,
[4802.06 → 4804.72] they really are brilliant architects on that thing.
[4804.78 → 4805.08] On that thing.
[4805.08 → 4805.46] But then,
[4805.70 → 4809.32] then to repeat these mistakes on the firmware side is just gutting.
[4809.44 → 4809.74] Yeah,
[4809.74 → 4810.32] it was bummer.
[4810.32 → 4811.76] So what we're doing,
[4811.84 → 4812.32] we've started,
[4812.64 → 4813.82] and that code's written in C.
[4814.10 → 4814.30] And,
[4814.36 → 4814.74] you know,
[4814.98 → 4815.20] I,
[4816.32 → 4818.56] every time I see new code written in C,
[4818.56 → 4819.40] I just have to say,
[4819.46 → 4820.40] why are you doing this?
[4820.50 → 4821.86] Why would you ever do this?
[4821.86 → 4827.34] And it looks like every other C piece of firmware with all the things that implies.
[4827.54 → 4830.12] So we're taking a very different tack now on RISC-V.
[4830.24 → 4830.36] We,
[4830.46 → 4833.86] I've started a project called Or boot back in March.
[4834.32 → 4834.80] We're big fans.
[4835.12 → 4835.52] Okay.
[4836.08 → 4836.30] Yeah.
[4836.30 → 4837.78] So for anyone who hasn't heard of it,
[4837.84 → 4840.14] Or boot is a downstream fork of Cor boot,
[4840.26 → 4842.24] but Or boot is Cor boot without C.
[4842.76 → 4844.84] So we downstream fork Cor boot.
[4845.34 → 4848.34] We did a search and destroy on every C code.
[4848.72 → 4850.20] The new code's all written in Rust,
[4850.34 → 4853.34] but we do use some of the Cor boot assembly code because it's good code.
[4853.34 → 4853.52] Yeah.
[4853.64 → 4853.80] Right.
[4854.00 → 4857.88] And we do use the Cor boot utilities because they're fantastic utilities.
[4857.88 → 4858.92] But where we,
[4859.14 → 4860.46] where we can,
[4860.62 → 4860.78] we,
[4860.84 → 4862.32] we discard things we,
[4862.68 → 4862.84] you know,
[4862.86 → 4865.70] from Cor boot that we feel were no longer needed.
[4865.70 → 4872.74] So that is now we have used that to load kernels on the sci-fi,
[4872.80 → 4872.98] five,
[4873.06 → 4875.08] five freedom U board,
[4875.18 → 4877.00] which is the one based on 64 bit.
[4877.36 → 4880.08] I have one over there somewhere in one of those bags.
[4880.54 → 4880.76] Well,
[4880.80 → 4881.06] here's,
[4881.12 → 4882.44] here's the slightly more exciting news.
[4882.56 → 4883.68] Now that open Titan is,
[4883.84 → 4884.10] you know,
[4884.10 → 4885.72] we're allowed to talk about open Titan.
[4885.86 → 4886.46] Very exciting.
[4888.06 → 4888.66] And yeah,
[4888.66 → 4890.34] I know it appreciated your,
[4890.48 → 4890.86] you know,
[4890.92 → 4891.98] your support of it, actually.
[4892.14 → 4892.28] Yeah.
[4892.42 → 4892.62] No,
[4892.70 → 4893.10] we were,
[4893.18 → 4894.78] it's something we were being very excited about,
[4894.78 → 4895.56] very excited to say.
[4895.86 → 4896.10] Yeah.
[4896.20 → 4896.48] So,
[4896.66 → 4900.88] so we are now compiling Or boot for the open Titan.
[4901.08 → 4901.32] Hey,
[4901.68 → 4903.40] that's good news.
[4903.46 → 4904.18] That's great news.
[4904.44 → 4904.66] Yeah.
[4904.72 → 4904.96] Wow.
[4905.34 → 4908.60] And we actually are finding bugs in rust.
[4909.04 → 4909.26] Oh,
[4909.60 → 4910.60] which we've,
[4910.60 → 4913.04] we had a number of bugs all based around atomics.
[4913.30 → 4914.04] The most interesting,
[4914.22 → 4917.78] take a look for the most recent one based around atomics on RV 32,
[4917.78 → 4917.86] too,
[4917.90 → 4921.64] because open Titan is what's called an RV 32 IMC.
[4921.64 → 4922.52] And there's no,
[4922.62 → 4923.42] it's not iMac,
[4923.52 → 4924.36] it's IMC.
[4924.48 → 4924.62] It was,
[4924.62 → 4925.06] you know,
[4925.06 → 4926.60] atomic support.
[4926.74 → 4926.78] Yeah.
[4926.78 → 4927.44] And rust,
[4927.88 → 4931.12] it turned out the compiler had a bug, and would incorrectly handle,
[4931.12 → 4932.08] uh,
[4932.08 → 4933.38] processors without atomics.
[4933.46 → 4934.10] It's a fun,
[4934.16 → 4934.80] it's a fun bug.
[4934.90 → 4935.12] That's,
[4935.16 → 4935.30] uh,
[4935.30 → 4936.00] that's a great one.
[4936.12 → 4936.30] Yeah.
[4936.30 → 4937.64] I would love to go look at that.
[4937.84 → 4938.98] It's actually a little subtle,
[4939.22 → 4939.38] but,
[4939.46 → 4939.82] um,
[4939.84 → 4941.32] I can imagine.
[4941.50 → 4941.62] Yeah.
[4941.72 → 4942.46] I can imagine.
[4942.60 → 4944.34] It's the difference between saying,
[4944.34 → 4944.92] um,
[4945.42 → 4948.02] a thing is none or is value of zero.
[4948.40 → 4948.68] Oh,
[4948.70 → 4949.00] interesting.
[4949.16 → 4950.18] So take a look at it.
[4950.18 → 4950.52] You'll love it.
[4950.52 → 4950.76] Um,
[4951.14 → 4951.42] anyway,
[4951.58 → 4958.04] so our intent with Or boot and then is that on a machine with privilege mode,
[4958.16 → 4961.68] we want to load a kernel that'll run in M mode as an experiment.
[4962.08 → 4963.60] And this goes a little bit further.
[4963.82 → 4964.34] Um,
[4964.34 → 4965.98] we're experimenting with running in M mode.
[4967.00 → 4967.80] And so the different modes.
[4968.14 → 4969.68] M is machine mode.
[4969.78 → 4970.90] It's essentially SMM.
[4971.08 → 4971.18] Right.
[4971.42 → 4977.12] But what I never viewed the ability of the operating system to modify M mode code as a bug.
[4977.12 → 4981.20] A lot of people did because I wanted the operating system to own that mode.
[4981.52 → 4981.72] Absolutely.
[4982.00 → 4982.36] Amen.
[4982.90 → 4983.34] Preach.
[4983.62 → 4983.78] Yeah.
[4983.98 → 4984.16] So,
[4984.30 → 4985.10] so there,
[4985.20 → 4985.94] there's a really,
[4986.08 → 4986.48] um,
[4986.60 → 4987.54] Jeremy Fix Harding,
[4987.62 → 4989.58] who's written the Redox operating system in Ross.
[4989.58 → 4992.24] I've talked to him about this and kind of went,
[4992.40 → 4992.84] got,
[4993.02 → 4995.24] got the sanity check from him because he's perfect.
[4995.24 → 4995.68] And,
[4995.68 → 4996.18] and said,
[4996.26 → 4996.40] look,
[4996.98 → 4998.54] we'd like to run the kernel in M mode,
[4998.62 → 4999.44] but with user mode,
[4999.54 → 4999.84] you know,
[4999.88 → 5000.02] with,
[5000.08 → 5001.06] with paging enabled.
[5001.36 → 5002.14] And he likes,
[5002.26 → 5005.20] he said he liked the idea because think about this.
[5005.28 → 5005.50] I'll,
[5005.54 → 5005.76] I'll,
[5005.76 → 5005.98] I'll,
[5005.98 → 5007.04] I'll go from my kernel,
[5007.20 → 5008.92] my process to M mode.
[5008.92 → 5010.78] I don't have to do any TLB flush.
[5010.88 → 5014.98] I don't need to lead load or page table route because there's no paging in M mode.
[5015.14 → 5015.54] Basically.
[5016.32 → 5016.60] Um,
[5016.60 → 5019.88] I can use their memory protect area registers,
[5020.00 → 5022.24] which are basically segment registers without an offset.
[5022.42 → 5022.52] No,
[5022.72 → 5022.98] it's,
[5022.98 → 5023.54] it's a bound,
[5023.60 → 5026.80] but not a base is one way to think of it to protect bits of the kernel.
[5027.32 → 5027.72] And,
[5027.84 → 5027.92] you know,
[5027.92 → 5030.36] the question is really,
[5030.42 → 5031.54] this is kind of a research question.
[5031.54 → 5038.32] Do I lose so much by not having paging enabled in the kernel that it's too far to go?
[5038.62 → 5038.74] Right.
[5039.08 → 5044.54] Or do I gain so much by not having paging turned on that it's really worth what,
[5044.60 → 5045.12] what I lose?
[5045.20 → 5046.84] This is an unknown question,
[5046.98 → 5047.12] right?
[5047.70 → 5049.44] It depends on how much your kernel is going to be doing,
[5049.56 → 5049.88] honestly.
[5050.30 → 5050.40] Yeah,
[5050.40 → 5050.74] that's true.
[5050.96 → 5051.14] I mean,
[5051.16 → 5052.24] if you've got a big kernel,
[5052.24 → 5053.06] that's going to do a lot,
[5053.14 → 5055.60] it's going to get more and more difficult to not have paging enabled.
[5055.82 → 5056.36] This would be my,
[5056.72 → 5057.08] that's,
[5057.14 → 5059.02] that's kind of our speculation.
[5059.26 → 5059.44] Yeah.
[5059.44 → 5059.56] But,
[5059.56 → 5060.20] but on a
[5060.20 → 5061.66] on these little tiny,
[5061.66 → 5062.12] you know,
[5062.14 → 5063.26] RV 64s,
[5063.40 → 5064.68] we may never care,
[5064.78 → 5064.88] right?
[5064.88 → 5065.70] For Open Titan,
[5065.90 → 5066.64] you may.
[5066.90 → 5066.96] Well,
[5066.96 → 5068.22] Open Titan won't even run Linux,
[5068.32 → 5069.00] so we're fine there.
[5069.00 → 5069.14] Yeah,
[5069.16 → 5069.34] right.
[5069.48 → 5070.86] It'll be running something else.
[5070.96 → 5071.44] But I,
[5071.46 → 5075.28] I do think that we need to step back a little about,
[5075.40 → 5075.74] you know,
[5075.80 → 5077.48] what is a kernel, and what does a kernel do?
[5077.88 → 5080.94] And does it need things the way we're doing them now?
[5081.02 → 5082.28] Or do we need to rethink this?
[5082.36 → 5086.14] Because the other fascinating thing that RISC-V opens up,
[5086.94 → 5087.42] I can build,
[5087.56 → 5087.82] and I,
[5087.82 → 5088.60] and I know someone's doing,
[5088.66 → 5089.82] I can build a machine with a thousand,
[5089.82 → 5090.64] two thousand cores.
[5090.82 → 5091.04] Right.
[5091.20 → 5091.38] Right.
[5092.22 → 5095.44] One of the reasons I can do that I'm not paying a per core license anymore.
[5095.66 → 5095.82] Yeah.
[5095.82 → 5097.22] Why didn't anyone do that with ARM?
[5097.30 → 5097.42] Well,
[5097.42 → 5098.42] you can't do it with x86.
[5098.62 → 5099.62] It's too complex and big.
[5099.72 → 5099.86] Yep.
[5100.22 → 5100.50] ARM,
[5101.14 → 5102.60] conceivably you could do it,
[5102.68 → 5103.66] but you can't pay it.
[5103.74 → 5103.94] Right.
[5104.06 → 5105.32] The licensing costs are too great.
[5105.78 → 5106.02] So,
[5107.06 → 5107.32] well,
[5107.40 → 5107.60] okay,
[5107.66 → 5108.86] if I have a thousand cores,
[5109.28 → 5111.56] should I really be time-sharing cores anymore?
[5112.56 → 5112.92] Interesting.
[5113.46 → 5113.72] Right?
[5113.90 → 5114.10] So,
[5114.22 → 5114.40] oh,
[5114.82 → 5115.30] wait a minute.
[5115.30 → 5116.52] If I'm not time-sharing cores,
[5117.62 → 5119.88] then did I need a virtual machine capability?
[5120.12 → 5120.34] Yeah.
[5120.52 → 5121.32] I'm not sharing cores.
[5121.40 → 5123.08] And virtual machine is all about sharing.
[5123.36 → 5123.76] Yeah,
[5123.80 → 5124.34] you do wonder,
[5124.50 → 5124.56] like,
[5124.60 → 5128.20] what does that pink look like today in RISC-V?
[5128.40 → 5128.62] Yeah.
[5128.62 → 5129.14] Right?
[5129.28 → 5132.18] Where you may have hundreds of thousands of cores.
[5132.70 → 5132.86] Yeah.
[5133.66 → 5134.10] Yeah,
[5134.20 → 5134.50] interesting.
[5134.82 → 5134.94] So,
[5135.04 → 5135.48] RISC-V,
[5136.18 → 5138.70] and this is a thing that people get a little mixed up on,
[5138.76 → 5140.22] RISC-V is not an open source core,
[5140.52 → 5141.10] necessarily.
[5141.80 → 5142.08] Right?
[5142.48 → 5145.24] You can make a proprietary RISC-V and not violate anything.
[5145.88 → 5148.40] It doesn't mean that firmware has to be open source.
[5148.64 → 5151.72] It just means that you don't pay a nickel or whatever
[5151.72 → 5153.82] for every core you lay down on a die.
[5154.00 → 5154.30] Right.
[5154.30 → 5161.72] And that one simple fact opens up so many interesting possibilities.
[5162.10 → 5162.46] It's just,
[5162.74 → 5163.12] you know,
[5163.18 → 5164.52] we're just seeing the beginning.
[5164.66 → 5164.88] I mean,
[5165.78 → 5168.96] a friend of mine got a $3 RISC-V board from China.
[5169.08 → 5170.68] Funny thing about the RISC-V board from China,
[5170.76 → 5171.90] it has a camera and a GPU.
[5172.06 → 5173.14] Guess what they're going to use those for?
[5173.14 → 5173.40] But,
[5173.52 → 5174.12] you know,
[5174.34 → 5176.30] the thing is,
[5176.32 → 5177.34] yeah,
[5178.26 → 5178.50] yeah,
[5178.52 → 5179.22] or don't say cheese.
[5179.40 → 5179.48] Right.
[5179.84 → 5181.06] But in any event,
[5181.24 → 5182.26] you know,
[5182.88 → 5184.20] it's really exploding.
[5184.30 → 5185.56] And from what I can tell in China,
[5185.90 → 5186.20] and,
[5186.20 → 5189.38] but also you look at the most recent sci-fi processor,
[5189.52 → 5191.68] that's pretty interesting what they've done there.
[5191.78 → 5191.98] Not,
[5192.16 → 5193.02] not the 540,
[5193.14 → 5193.86] but the next one.
[5193.92 → 5194.10] Yeah.
[5194.44 → 5194.74] And I,
[5194.80 → 5196.60] and I want to try and understand better what they've done,
[5196.68 → 5198.10] but they've had some really cool ideas.
[5198.20 → 5203.26] So I think you're going to see a lot of really innovative things coming down
[5203.26 → 5205.04] the pike around the RISC-V.
[5205.04 → 5205.28] And I've,
[5205.68 → 5206.44] it's sort of like,
[5206.44 → 5210.68] it's opened up our ability to do innovative things in hardware again.
[5210.68 → 5210.92] Well,
[5210.98 → 5211.10] yeah,
[5211.18 → 5212.34] and I totally agree.
[5212.48 → 5216.86] And especially as we increasingly get parked at that seven nanometre node,
[5216.96 → 5217.16] because I mean,
[5217.22 → 5217.58] I think what,
[5217.70 → 5218.72] I think the sci-fi guys,
[5218.80 → 5220.22] I think they're at like 28 nanometers,
[5220.32 → 5221.40] maybe even lower now.
[5221.68 → 5222.20] And it's like,
[5222.24 → 5224.28] it wasn't that long ago that that was leading edge process.
[5224.46 → 5224.54] Right.
[5225.18 → 5227.74] If I think it's reasonable to assume that we're,
[5227.84 → 5228.02] I mean,
[5228.10 → 5228.44] maybe,
[5228.52 → 5228.68] I mean,
[5228.72 → 5230.00] TSMC thinks we're going to get to five.
[5230.12 → 5231.00] I don't think we're,
[5231.06 → 5231.56] I mean,
[5231.72 → 5232.46] a silicon atom,
[5232.66 → 5232.92] I mean,
[5232.94 → 5233.20] the
[5233.20 → 5233.52] the
[5233.52 → 5238.10] the Vander wall's radius of a silicon atom is 200 nanometres or 200 picometres
[5238.10 → 5238.38] rather,
[5238.54 → 5239.50] 0.2 nanometres.
[5239.64 → 5240.14] So like,
[5240.14 → 5243.68] we're not getting too far beyond five.
[5243.90 → 5244.14] Right.
[5244.50 → 5244.76] Right.
[5245.08 → 5247.32] And then as we get more and more fabs parked at that node,
[5247.48 → 5251.38] it's going to be possible to fab a RISC-V at the same node that you're
[5251.38 → 5253.46] having an AMD microprocessor.
[5253.52 → 5253.72] Yeah.
[5254.10 → 5255.02] And the thing is,
[5255.58 → 5257.56] so I used to make this argument at Los Alamos,
[5257.70 → 5257.84] you know,
[5257.84 → 5259.90] we would run the supers at 5% efficiency.
[5260.08 → 5260.88] And I'd say,
[5260.96 → 5261.16] well,
[5261.18 → 5261.50] there's,
[5261.58 → 5263.70] there are a couple of ways to double your performance.
[5263.72 → 5267.36] One is let's find ways to be a little bit more efficient,
[5267.82 → 5268.72] 10% efficiency.
[5268.72 → 5269.08] Right.
[5269.56 → 5269.92] Or,
[5269.92 → 5272.82] or we'll go spend a hundred million on a new supercomputer or whatever.
[5272.82 → 5275.12] But I think there's a similar argument around processors,
[5275.30 → 5275.48] right?
[5275.70 → 5280.60] You can either continue to make your processor more complex and do more.
[5281.38 → 5283.76] But that's a losing game.
[5283.84 → 5284.06] Yeah.
[5284.18 → 5284.42] Right.
[5284.46 → 5285.36] As we run out of,
[5285.36 → 5285.94] you know,
[5286.00 → 5286.34] rule.
[5286.66 → 5286.84] So,
[5287.30 → 5287.46] you know,
[5287.50 → 5287.78] our,
[5287.78 → 5288.08] our,
[5288.08 → 5288.82] our node size.
[5289.00 → 5289.02] So,
[5289.14 → 5290.14] or we can say,
[5290.36 → 5290.56] Hey,
[5290.66 → 5292.64] let's do a dramatically simpler processor.
[5292.90 → 5293.12] Right.
[5293.26 → 5295.02] And then try and figure out what happens when we tile many,
[5295.08 → 5295.24] many,
[5295.24 → 5296.82] many of those on our die.
[5296.94 → 5298.84] So things are getting interesting.
[5299.10 → 5300.10] This is what AMD has done,
[5300.10 → 5300.28] right?
[5300.28 → 5304.08] Where you've got a seven nanometre part sitting on side by side with a 14
[5304.08 → 5304.64] nanometre part.
[5304.76 → 5305.64] that's really neat stuff.
[5305.76 → 5305.98] Yeah.
[5305.98 → 5307.70] The kind of the 2.5 D stuff.
[5308.38 → 5310.52] And it opens up a lot of possibility there.
[5310.62 → 5310.76] I mean,
[5310.78 → 5311.46] it's definitely,
[5311.90 → 5313.00] it's definitely interesting.
[5313.10 → 5313.80] And this is where I think the
[5313.80 → 5314.04] the
[5314.04 → 5317.04] the end of Moore's law is actually going to be exciting.
[5317.54 → 5317.90] Well,
[5318.58 → 5320.60] it'll bring us back to an age of limits.
[5320.60 → 5320.90] And,
[5320.98 → 5321.18] and,
[5321.18 → 5324.62] and arguably that's when the innovation starts,
[5324.62 → 5324.94] right?
[5324.94 → 5327.92] If you can just throw more memory at it in a year and AF,
[5328.02 → 5328.90] you don't have to be smart.
[5329.64 → 5331.04] But back in the early Linux days,
[5331.12 → 5331.30] you know,
[5331.30 → 5332.38] you had to be smart and,
[5332.48 → 5333.08] and a lot of,
[5333.18 → 5337.12] a lot of people came up with a lot of really clever things.
[5337.18 → 5337.54] And,
[5337.62 → 5340.76] and I think forcing limits on back on us,
[5340.76 → 5342.30] I think will be a good thing.
[5342.40 → 5342.90] I think it'll be healthy.
[5343.10 → 5344.58] I think it'll be healthy for the
[5344.58 → 5344.84] these,
[5344.94 → 5345.10] the
[5345.10 → 5346.28] the software ecosystem we've got,
[5346.36 → 5347.46] the firmware ecosystem we've got.
[5347.58 → 5351.28] I actually had a friend at Intel told me a funny story of really apropos.
[5352.30 → 5354.58] He had a graphics stack on the processor on,
[5354.66 → 5354.88] on a
[5354.96 → 5356.46] on an attached graphics board.
[5357.12 → 5358.10] And the one stack,
[5358.16 → 5359.20] I don't remember which direction it was.
[5359.20 → 5362.90] One stack had seven layers of API layering and one stack had six.
[5363.58 → 5364.12] Guess what?
[5364.14 → 5367.20] The decision was made to make them kind of meet.
[5367.40 → 5368.08] Oh God.
[5368.44 → 5369.16] You add another layer.
[5369.16 → 5369.74] Of course.
[5369.98 → 5370.24] Of course.
[5370.82 → 5371.00] Right.
[5371.08 → 5371.40] He said,
[5371.46 → 5372.62] nobody wanted to talk about,
[5372.62 → 5373.14] like,
[5373.22 → 5373.36] you know,
[5373.70 → 5374.66] slicing off.
[5374.70 → 5374.98] Right.
[5375.04 → 5376.02] A layer of API.
[5376.40 → 5376.54] They,
[5376.62 → 5377.62] they just added another layer.
[5377.80 → 5378.72] That's what we all do,
[5378.78 → 5378.88] right?
[5378.90 → 5379.28] That's what we all do.
[5379.32 → 5379.64] We just,
[5379.78 → 5380.72] software's made that free.
[5380.98 → 5381.16] And,
[5381.30 → 5381.62] and,
[5381.68 → 5382.10] you know,
[5382.10 → 5383.42] getting back to the plan nine discussion,
[5383.50 → 5385.54] the thing I love about plan nine is that,
[5385.54 → 5385.94] um,
[5387.08 → 5388.12] the model of that was,
[5388.12 → 5389.48] do not put anything in the kernel.
[5389.48 → 5392.02] If you can possibly find a way not to put it in the kernel.
[5392.14 → 5392.34] Right.
[5392.44 → 5392.68] And,
[5392.74 → 5397.56] and so I did an ACP subsystem for plan nine about four years ago.
[5397.56 → 5400.12] And if you look every kernel,
[5400.20 → 5400.90] including MINIX,
[5400.96 → 5402.14] which is a micro kernel,
[5402.34 → 5406.72] they take the 50,000 or 90,000 lines of APA CA code.
[5407.18 → 5409.32] And Linux transforms it to make it less ugly.
[5409.32 → 5410.48] Because it is hideous.
[5410.50 → 5411.16] It is hideous.
[5411.26 → 5412.22] And they compile it into the kernel.
[5412.46 → 5412.70] Right.
[5412.70 → 5413.40] And I thought,
[5413.72 → 5413.90] okay,
[5414.00 → 5414.22] fine.
[5414.32 → 5415.08] Everybody does that.
[5416.00 → 5419.00] But the rule is you never put it in a kernel if you don't have to.
[5419.10 → 5425.22] And so I kind of worked out a way to make a very minimal ACP device and run the ACP consortium code in user mode.
[5425.34 → 5425.44] Right.
[5425.52 → 5425.84] Yeah.
[5425.98 → 5426.20] And,
[5426.28 → 5430.98] and so I think in a lot of cases it's really possible to do these things,
[5430.98 → 5433.58] but it's so easy just to like,
[5433.72 → 5435.26] just shove it in a kernel.
[5435.38 → 5435.48] Right.
[5435.66 → 5436.26] Load it up.
[5436.34 → 5437.72] Another hundred thousand lines of code.
[5437.80 → 5438.20] Who cares?
[5438.48 → 5438.68] Right.
[5438.84 → 5439.14] You know,
[5439.18 → 5440.18] we've got enough memory,
[5440.44 → 5440.72] whatever.
[5440.72 → 5441.70] So we,
[5441.80 → 5443.48] in some ways we've kind of gotten a little lazy.
[5443.70 → 5444.06] Yep.
[5444.30 → 5444.54] And,
[5444.60 → 5445.00] and it,
[5445.04 → 5445.32] and it,
[5445.88 → 5446.16] so for,
[5446.24 → 5447.38] for back to an area where,
[5447.64 → 5448.90] era where there's sort of limits,
[5449.04 → 5450.14] that that's kind of cool.
[5450.36 → 5451.06] I think it's kind of neat.
[5451.10 → 5451.90] I think it's going to,
[5452.02 → 5454.78] as you say that with those limits force innovation,
[5454.86 → 5455.00] I mean,
[5455.00 → 5455.96] that's where you got to be,
[5456.02 → 5456.28] you got to,
[5456.28 → 5456.94] got to be creative.
[5457.38 → 5457.42] And,
[5457.54 → 5459.22] and I think that's,
[5459.38 → 5459.48] we,
[5459.56 → 5461.56] it's going to be fun times for sure.
[5462.18 → 5462.52] Ron,
[5462.58 → 5464.10] this has been delightful.
[5464.78 → 5465.14] Thank you.
[5465.14 → 5465.36] I've had fun.
[5465.54 → 5465.64] Yeah.
[5465.74 → 5467.98] Thank you so much for joining us today.
[5468.06 → 5469.58] This has been really great.
[5469.70 → 5470.06] We knew,
[5470.06 → 5474.16] we were looking forward to having you up at the garage and I think it is overdelivered.
[5474.30 → 5475.28] So thank you very much.
[5475.64 → 5476.10] Thanks again.
[5476.18 → 5476.32] Thank you.
[5476.44 → 5476.80] Thanks Ron.
[5476.90 → 5477.06] Yeah.
[5477.46 → 5478.16] Good to see you all.
[5478.32 → 5478.48] Yeah.
[5479.62 → 5481.32] You've been listening to On The Metal,
[5481.56 → 5483.60] tales from the hardware software interface.
[5483.98 → 5484.50] For show notes,
[5484.66 → 5485.86] to learn more about our guests,
[5486.12 → 5487.32] or to sign up for our mailing list,
[5487.72 → 5490.04] visit us at onthemetal.fm.
[5490.48 → 5492.90] On The Metal is a production of Oxide Computer Company.
[5492.90 → 5496.28] It is recorded in the Oxide Garage in Oakland, California.
[5496.82 → 5497.84] To learn more about Oxide,
[5498.06 → 5499.90] visit us at oxide.computer.
[5500.36 → 5501.50] On The Metal is hosted by me,
[5501.62 → 5502.24] Brian Cantwell,
[5502.36 → 5503.40] along with Jess Fri sell.
[5503.62 → 5505.34] And we are frequently joined by our boss,
[5505.58 → 5506.06] Steve Tuck.
[5506.30 → 5508.58] Our original and awesome theme music is by J.J.
[5508.64 → 5510.20] Wrestler at Pollen Music Group.
[5510.48 → 5511.56] You can learn more about J.J.
[5511.64 → 5514.16] and Pollen at pollenmusicgroup.com.
[5514.16 → 5516.66] We are edited and produced by Chris Hill
[5516.66 → 5518.34] and his crew at Humble Pod.
[5518.66 → 5520.70] From Jess, from Steve, from me,
[5520.78 → 5522.90] and from all of us at Oxide Computer Company,
[5523.18 → 5524.54] thanks for listening to On The Metal.
[5544.16 → 5574.14] On The Metal is a production of Oxide Computer Company.
