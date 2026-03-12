[0.00 --> 13.90]  Welcome to On The Metal, tales from the hardware software interface.
[14.40 --> 18.08]  I'm Brian Cantrell. With me, as always, is Jess Frizzell. Hey, Jess.
[18.28 --> 18.86]  Hey, Brian.
[19.20 --> 22.26]  And joining us is our boss, Steve Tuck. Hey, Steve.
[22.50 --> 23.16]  Lucky to be here.
[23.34 --> 24.54]  All right. Keep us in line.
[25.20 --> 28.08]  Jess, you want to tell us who's joined us in the garage today?
[28.08 --> 32.48]  Yes. Today we have Jeff Rothschild. Very fortunate to have him.
[32.72 --> 37.72]  And we have brought him into the garage, and we actually already started talking about some stuff that we have in here,
[38.16 --> 40.66]  one of which was an IBM basic manual.
[41.64 --> 45.38]  And Jeff, when you came, first of all, welcome to On The Metal. It's great to have you here.
[45.38 --> 45.50]  Oh, thank you.
[46.10 --> 48.84]  And, you know, you immediately started looking at our manuals.
[49.26 --> 54.06]  And I know that, like, a lot of them have personal resonance for me and personal resonance for you.
[54.06 --> 58.54]  And I know you saw the IBM manuals. And those were great manuals, weren't they? The boxes?
[58.70 --> 66.22]  They were. It felt very impressive to have that whole row of boxes sitting on your desk next to the IBM PC.
[66.54 --> 67.76]  It felt quite official.
[68.02 --> 73.04]  All right. So tell us when you first had those manuals, and tell us about some of those manuals that meant something to you.
[73.04 --> 78.84]  Well, I bought an IBM PC right when it came out. I just figured this was going to be an important platform,
[78.84 --> 82.04]  and I should know everything there was to know about it.
[82.08 --> 86.18]  I figured if I knew a little bit more than somebody else, there might be some advantage to that.
[86.60 --> 92.46]  First thing I did was I noticed there was a disassembler. And so I disassembled MS-DOS.
[92.68 --> 99.90]  I laid out 20 feet of paper listing on the floor of my apartment and got to work commenting it.
[99.90 --> 103.82]  Wow. That must have been... So, all right. So your apartment. So you're an adult at this point.
[104.02 --> 104.76]  Sort of, yeah.
[104.78 --> 106.66]  You're in the end, right.
[107.34 --> 108.42]  I was in my 20s.
[108.46 --> 111.30]  You're in your 20s. So perfect timing for the PC.
[112.16 --> 116.66]  And so what did you learn from MS-DOS? That must have been an incredible educational experience.
[116.74 --> 119.82]  Well, I understood how the file control blocks worked.
[119.98 --> 126.56]  I recognized that there was state associated with an open file that persisted past the close of the file.
[126.56 --> 132.68]  And oddly enough, I did find that very useful later because some applications would operate on a file,
[132.82 --> 138.66]  would officially do a close, and then continue to move the file pointer and do reads and writes
[138.66 --> 142.58]  because it didn't matter. That state was not eliminated on close.
[143.02 --> 146.92]  So the FCB-based IO was, you know, I had to understand it.
[146.96 --> 153.62]  I needed to understand stack switching, moving between the user stack and the system stack.
[153.62 --> 155.60]  So it was quite useful to have that commented code.
[156.40 --> 158.52]  Wow. And did you do that solo? Did you...
[158.52 --> 159.28]  On my own.
[159.50 --> 162.90]  Wow. And I mean, it's disassembly, obviously.
[163.18 --> 165.64]  So it does not come with even...
[165.64 --> 167.06]  Do you have symbols? Do you have identifiers?
[167.20 --> 167.96]  I mean, what did you have to go on?
[168.00 --> 169.14]  No, I just created my own.
[169.34 --> 173.64]  There was numeric identifiers in the disassembly, but then I created my own symbols.
[173.84 --> 176.34]  Once I figured out what something did, I'd create a name for it.
[176.88 --> 182.64]  Oddly enough, many years later, I did see portions of MS-DOS and had to go back and check.
[182.64 --> 186.52]  And my names weren't that different in most cases.
[187.26 --> 189.58]  Do you... You don't still have that comment?
[189.92 --> 189.94]  No, of course not.
[189.98 --> 194.34]  I mean, it would be invaluable, I think, to actually learn how it worked.
[194.48 --> 195.12]  That's so cool.
[195.68 --> 198.62]  And I also used it in order to do an IO redirector.
[198.88 --> 205.64]  One of the first products I did on MS-DOS was a file redirector for moving data to...
[205.64 --> 208.58]  Making... Moving file ops to a Unix system.
[208.58 --> 211.38]  So effectively like a primitive version of NFS.
[211.72 --> 215.08]  But there was no VFS interface in MS-DOS.
[215.18 --> 225.42]  So I created something like that in order to do a product called PC Interface that allowed a MS-DOS program to use a Unix host as its remote file system.
[225.64 --> 227.02]  What year is that?
[227.42 --> 229.00]  Oh, early 80s.
[229.18 --> 229.58]  Wow.
[230.02 --> 230.66]  That was early.
[230.66 --> 236.74]  That technology was purchased by Sun Microsystems and became the client side of PC NFS.
[236.96 --> 237.14]  Whoa.
[237.54 --> 237.98]  Wow.
[238.12 --> 241.42]  Because the protocol was close enough to what eventually Sun did as NFS.
[241.82 --> 244.26]  Do you ever wonder if that software is still running anywhere today?
[244.42 --> 245.20]  Oh, I'm sure it is.
[246.60 --> 250.96]  I'm sure in some government agency there's a machine somebody hasn't touched in 30 years.
[251.08 --> 253.50]  It's not on the internet, so nobody needs to update it.
[253.70 --> 256.50]  And, you know, I suspect it's still running somewhere.
[257.00 --> 257.86]  That is amazing.
[257.86 --> 262.64]  And is this, so this isn't in the day, this is all real mode, correct?
[262.90 --> 263.16]  Oh, yeah.
[263.44 --> 265.86]  So this is all effectively 16-bit disassembly.
[266.50 --> 267.04]  That's correct.
[267.58 --> 269.22]  Not a lot of registers to work with.
[269.32 --> 269.94]  No, no.
[270.04 --> 273.98]  And, you know, had to do this in, you know, a few number of bytes.
[274.16 --> 279.14]  Most machines at that time had only were sold with 64K bytes of RAM.
[279.64 --> 281.64]  So you couldn't waste anything.
[281.64 --> 288.76]  So I did a simple IPUDP implementation all in assembler in about 2.5K.
[289.32 --> 289.56]  Whoa.
[289.88 --> 290.10]  So.
[290.86 --> 292.94]  That thing would fly today.
[293.02 --> 293.78]  No, no TCP.
[294.22 --> 295.98]  That would have been, I couldn't have done that in that.
[296.14 --> 296.96]  TCP would have been tough.
[297.08 --> 297.68]  That would have been harder.
[297.92 --> 298.62]  With those constraints.
[298.66 --> 304.62]  Simple IPUDP and, you know, ARP and reverse ARP all in about 2.5K.
[305.78 --> 306.62]  That's amazing.
[306.62 --> 308.48]  And what kind of machine were you talking to?
[308.84 --> 310.04]  This was a.
[310.06 --> 310.50]  3B2?
[310.84 --> 311.60]  3B2, exactly.
[311.86 --> 312.22]  Yeah, there we are.
[312.22 --> 312.54]  Wow.
[312.54 --> 314.54]  It was the AT&T 3B2.
[315.30 --> 320.48]  A machine that if memory serves correctly, stacks grew up on the 3B2.
[320.88 --> 321.78]  Is that right?
[322.20 --> 324.98]  I, that's lost for time.
[325.10 --> 326.08]  I don't remember.
[326.22 --> 331.52]  The only reason I say that is because I ripped out some code that rely, that we historically
[331.52 --> 333.82]  allowed stacks to grow up or down.
[333.82 --> 338.88]  And I determined that the only reason that upward stack growth was there was for the 3B2.
[339.04 --> 339.64]  Back in the day.
[339.96 --> 340.64]  I can believe that.
[340.94 --> 342.38]  It was, it was a fun machine.
[342.54 --> 344.98]  It was very Unix and C centric.
[345.06 --> 347.56]  That detail, I, I'm luckily I've forgotten.
[347.76 --> 348.34]  That's right.
[348.74 --> 353.22]  So was that machine that like the favorite machine that you ever owned or did you have
[353.22 --> 353.74]  another one?
[354.14 --> 356.14]  Oh, machines I've owned.
[356.32 --> 359.56]  I can't say that the machines I've owned, I've ever had a favorite.
[359.56 --> 365.08]  I enjoyed working on a Xerox Sigma 7 when I was in school, which is a great computer,
[365.26 --> 369.52]  impressive for what you could do with it with, with, of course, you know, very little,
[369.52 --> 371.62]  you know, basic hardware performance.
[372.40 --> 372.54]  Wow.
[372.62 --> 373.98]  So what was the Sigma 7 based on?
[374.10 --> 379.90]  Sigma 7 was the scientific data systems was the company that developed the architecture.
[379.90 --> 381.32]  They sold that to Xerox.
[381.46 --> 383.12]  It was a 32 bit machine.
[383.64 --> 384.44]  A 32 bit machine.
[384.54 --> 386.10]  That's that is very early for 32 bits.
[386.10 --> 392.26]  It is an early 32 bit machine, early seventies development had, I think about probably a
[392.26 --> 393.48]  megabyte of memory.
[393.60 --> 399.78]  It used a, a fixed head disc, a drum, what they called a drum and could support, you know,
[399.86 --> 402.06]  40, 50 terminal users.
[402.06 --> 406.38]  So, you know, they're, they're, they're people were limited by the speed of the input device.
[406.38 --> 409.30]  So you're typing on a teletype 110.
[409.78 --> 411.96]  So nothing was very fast.
[412.08 --> 413.82]  It was the university shared resource.
[414.32 --> 414.94]  That's amazing.
[414.94 --> 417.74]  You think that that machine had a megabyte of Ram.
[418.08 --> 421.82]  And then a decade later, you're buying a machine with 64 K of Ram.
[421.82 --> 426.36]  I mean, it's just, it shows you how, I mean, how dichotomous computing was in terms of the
[426.36 --> 428.50]  computers that you would use versus the computers you could buy.
[428.72 --> 428.98]  Of course.
[429.56 --> 430.10]  It's amazing.
[430.72 --> 431.82]  It's almost interesting.
[431.94 --> 436.16]  Like then how people kind of just consume resources without even thinking about them
[436.16 --> 436.46]  today.
[436.90 --> 439.14]  Well, I, yeah, I mean, that's a, that's a commonly held attitude.
[439.14 --> 444.12]  I think that we, we view, I mean, how, especially growing up in that era, you must view us as
[444.12 --> 445.94]  being just profligate users of everything.
[446.02 --> 446.48]  Oh, of course.
[446.62 --> 447.40]  Terribly wasteful.
[448.48 --> 451.84]  But, you know, it's sort of a lost skill and maybe it should be lost.
[452.06 --> 457.32]  I mean, we used to, I remember when, you know, people would grade papers when I was in school.
[457.32 --> 461.98]  If somebody could show that you could eliminate 20 bytes, well, that was, you lost half a
[461.98 --> 462.24]  grade.
[462.24 --> 466.16]  I mean, because every byte mattered and today it, today it doesn't.
[466.58 --> 469.68]  I feel like there are still pockets where every byte matters.
[469.92 --> 470.18]  Of course.
[470.22 --> 475.38]  When you're dealing with obviously large amounts of data, then the representation of each individual
[475.38 --> 478.04]  data element, clearly every byte matters.
[478.04 --> 482.84]  But, you know, when you're, when you're writing a piece of functional code, it's more, I'd say
[482.84 --> 488.14]  readability and your ability to maintain and, and, and enhance that code is more important
[488.14 --> 492.30]  as to whether you achieve the utmost compact representation.
[492.82 --> 496.48]  And so was the Sigma seven, was that your first real big machine?
[496.68 --> 497.40]  It was.
[497.46 --> 497.64]  Yes.
[497.66 --> 500.00]  I then moved from there to the PDP 10.
[500.32 --> 505.70]  Ooh, I have a PDP 11 replica inside and then a PDP eight, but not a 10.
[505.82 --> 507.38]  Well, I use the eight as well.
[507.38 --> 509.84]  In fact, I did, I worked on the eight and paper tape.
[510.54 --> 511.06]  Oh, that's cool.
[511.20 --> 515.30]  And that, that was, that was also an interesting challenge to do your development of paper tape
[515.30 --> 518.62]  and PDP 10, you know, a 36 bit machine.
[518.62 --> 521.70]  And it was an interesting, interesting beast.
[521.82 --> 528.20]  I actually used to have fun coding the PDP 10, not using the assembler because I, for some
[528.20 --> 533.02]  reason that I can't explain, it might, it may have been, in fact, it, it may be indicative
[533.02 --> 538.44]  of, of, of, of a social defect, but I thought it was fun to learn the machine language and
[538.44 --> 539.60]  code without the assembler.
[539.74 --> 544.94]  So I just opened up an octal editor and could write some fairly, you know, simple programs.
[545.06 --> 545.60]  That's good.
[545.92 --> 546.18]  Okay.
[546.18 --> 547.34]  A useless trick.
[547.68 --> 552.64]  And, and again, you know, if somebody, if I saw someone doing that today, I would be
[552.64 --> 553.00]  worried.
[553.24 --> 556.32]  I was just going to ask, is everything done with an assembler today?
[556.84 --> 558.94]  Is it unheard of that you would not use an assembler?
[559.04 --> 563.22]  Certainly when Jeff was saying, I didn't use the assembler, I was saying, wow, you're using
[563.22 --> 566.66]  a higher level language in, but no, it's like he was actually going lower.
[566.66 --> 572.66]  So the, the, the assembler takes the actual instructions to the CPU and encodes them in
[572.66 --> 573.68]  the binary representation.
[574.72 --> 578.64]  What Jeff was manipulating was actually the binary representation, albeit.
[578.96 --> 579.80]  Well, I wrote it in octal.
[579.98 --> 580.10]  Right.
[580.26 --> 580.70]  Right.
[580.94 --> 581.30]  Yeah.
[581.84 --> 582.72]  I'm not, I'm not, I'm not pleased.
[582.94 --> 585.38]  I'm not a, I'm not a primate here.
[585.48 --> 587.58]  I mean, obviously I would work in octal, not binary.
[588.50 --> 589.10]  That's cool.
[589.48 --> 589.96]  That's it.
[590.00 --> 590.60]  That's amazing.
[591.22 --> 592.84]  And so you must have had the opcode.
[592.94 --> 594.40]  I mean, you probably still know some of those opcodes.
[594.40 --> 596.28]  No, I've, I've, I don't.
[596.28 --> 599.02]  I can, I luckily have forgotten that.
[599.12 --> 604.00]  I mean, there's a finite amount I think you can store and that register has been cleared
[604.00 --> 605.10]  and reused many times.
[605.56 --> 606.30]  Thank God.
[606.40 --> 606.60]  Right.
[607.04 --> 608.48]  It's been, it's been, so, all right.
[608.50 --> 612.56]  So you were on the PDP and how many years did you work on the PDP?
[612.68 --> 615.18]  Oh, just while I was in school for, you know, two, three years.
[615.70 --> 617.48]  And where'd you head to after school?
[617.78 --> 619.88]  Oh, I went to work at Honeywell.
[619.88 --> 624.08]  I spent a year at Honeywell's large information systems division.
[624.08 --> 628.50]  And this was the old General Electric computer company.
[628.92 --> 631.68]  Their system was a 36-bit machine as well.
[632.20 --> 637.68]  A real memory system at the point that I joined, though they were working on trying to add a
[637.68 --> 638.86]  virtual memory capability.
[639.48 --> 640.34]  Interesting machine.
[640.46 --> 644.32]  It had six-bit bytes, eight-bit bytes, and nine-bit bytes.
[644.32 --> 651.26]  So you could choose, you know, how many characters to pack into a word.
[651.38 --> 656.42]  And, of course, it meant that, you know, each piece of software had to identify its conventions
[656.42 --> 661.14]  for byte encoding, which wasn't that unusual in the day.
[661.22 --> 663.94]  We had both ASCII and EPSIDIC at use at the same time.
[664.16 --> 664.28]  Right.
[664.68 --> 666.14]  EPSIDIC is probably worth explaining.
[666.26 --> 667.96]  I know, Steve, there's no way you know EPSIDIC.
[668.18 --> 668.38]  Of course.
[668.38 --> 668.82]  I hope not.
[669.04 --> 669.96]  No, I have no idea.
[670.08 --> 670.58]  What's EPSIDIC?
[670.58 --> 677.80]  It's a character encoding that IBM was using through, I guess, the 50s and 60s.
[678.12 --> 680.94]  It is decimal encoded as binary.
[681.40 --> 681.82]  Whoa.
[682.14 --> 682.30]  Yeah.
[682.40 --> 684.40]  And it doesn't make a whole lot of sense.
[685.02 --> 691.26]  But we still have, it lives on today because the x86 still has instructions for binary encoded
[691.26 --> 691.56]  decimals.
[691.66 --> 692.06]  Kind of crazy.
[692.26 --> 692.82]  Oh, very good.
[693.34 --> 695.54]  ASCII add before multiply, my favorite x86 instruction.
[695.54 --> 701.30]  So, and then for the nine bit words, what was that, or the nine bit bytes, excuse me,
[701.34 --> 702.18]  what was that to allow?
[702.36 --> 703.42]  Was that a parody bit?
[703.54 --> 708.64]  Well, if they fit evenly into 36, so you get four characters in the word.
[708.80 --> 708.96]  Eight.
[709.34 --> 710.90]  Eight didn't go in quite as nicely.
[712.02 --> 717.98]  So, and then, but the six bit, of course, you would, it's only, it would fit in the 36 bit.
[718.18 --> 720.24]  And so what Honeywell machine is this at this point?
[720.24 --> 724.10]  This was, oh, you know, I don't remember the model numbers.
[724.32 --> 730.84]  It was, it was a Honeywell mainframe, ran the GCOS operating system, implemented in 7400
[730.84 --> 732.32]  LS logic.
[732.66 --> 733.80]  7400 LS.
[734.00 --> 734.16]  Yes.
[734.46 --> 735.42]  What does that denote?
[735.60 --> 744.54]  That's the, if you remember the Texas Instruments TTL data book, the yellow sort of, sort of yellowish
[744.54 --> 747.36]  binder that you don't have one on your shelf here.
[747.54 --> 748.40]  I don't have one on my shelf.
[748.40 --> 750.72]  No, I've got intense manual in me right now.
[750.74 --> 751.98]  That's one you need to buy.
[752.24 --> 757.86]  And it, it, these were a series of small scale and medium scale integration components.
[757.86 --> 761.78]  And most machines in the seventies were built out of this logic family.
[761.92 --> 768.46]  So you had 7400, 7400S, which was a faster implementation, Shotsky implementation, and then
[768.46 --> 769.64]  the low power Shotsky.
[770.06 --> 773.40]  I'm embarrassed to say, I didn't know Honeywell was ever in the computer business.
[773.76 --> 774.04]  Well.
[774.04 --> 779.58]  Because I think of Honeywell as, you know, thermostats and, and particularly the family
[779.58 --> 782.66]  business being in heating and air conditioning, ascribe them to that.
[782.80 --> 784.50]  But they were a computer company.
[784.70 --> 785.84]  They were definitely a computer company.
[786.00 --> 788.60]  And they were the H in the bunch.
[788.60 --> 792.12]  So at one point, the computer industry was IBM in the bunch.
[792.90 --> 795.76]  Burroughs, Univac, NCR, Control Data, and Honeywell.
[796.00 --> 796.54]  That's correct.
[796.78 --> 797.08]  Got it.
[797.10 --> 797.78]  Like FANG today.
[797.96 --> 798.86]  The FANG today.
[798.98 --> 799.20]  Yes.
[799.20 --> 799.38]  Okay.
[799.56 --> 799.96]  Yes.
[800.00 --> 800.74]  That's exactly right.
[801.50 --> 802.98]  1970s FANG is the bunch.
[803.32 --> 803.66]  That's cool.
[803.66 --> 807.84]  And of course, all of those companies are more or less out of the computer business.
[808.06 --> 811.98]  But so Honeywell, and actually Honeywell, although this would probably predate you, the
[811.98 --> 814.36]  H200, I imagine would predate you at Honeywell.
[814.88 --> 821.52]  They made an IBM 1401 clone called the H200, which was transistorized and forced IBM to really
[821.52 --> 822.12]  get off.
[822.52 --> 825.82]  IBM was, was very slow on a transistorized 1401.
[826.36 --> 828.12]  That's a machine I wasn't familiar with.
[828.12 --> 833.00]  I stayed at Honeywell a little less than a year and it was interesting.
[833.12 --> 836.86]  They'd given me a relocation bonus when I left school.
[837.24 --> 843.40]  And I, once I understood the state of the company and where the, where, where, where this
[843.40 --> 847.52]  organization was going to be going, I decided to calculate how much money could I save and
[847.52 --> 853.22]  how, how was my, my relocation bonus being amortized because each month I owed them a little
[853.22 --> 853.80]  bit less.
[853.84 --> 856.58]  And when the two lines crossed, I left.
[856.76 --> 857.00]  You left.
[857.00 --> 859.22]  So you decided pretty quickly you did not want to work at Honeywell.
[859.38 --> 865.48]  The year I was there, they were building a current mode logic version of their architecture.
[865.48 --> 873.08]  So CML at the time, ECL was, was a more broadly accepted technology, higher performance than
[873.08 --> 874.48]  7,400 LS.
[875.44 --> 878.12]  However, this was to be their first micro-coded machine.
[878.32 --> 878.58]  Oh, interesting.
[878.68 --> 881.78]  So the, the CML implementation was very expensive for them.
[881.84 --> 882.84]  They had their own foundry.
[882.90 --> 885.34]  They're building their own, their, their own chips.
[885.34 --> 894.20]  The, the, the micro-architecture was 10 times faster than the previously directly implemented
[894.20 --> 894.66]  logic.
[895.10 --> 899.10]  Unfortunately, you had about 10 micro-instructions in each target instruction loop.
[899.56 --> 903.52]  So the effect was a machine that cost an order of magnitude more.
[903.60 --> 903.90]  Interesting.
[903.90 --> 906.54]  And delivered exactly the same performance.
[906.94 --> 907.20]  Interesting.
[907.36 --> 911.58]  So you, maybe worth explaining micro-code because I feel micro-code is something that we don't
[911.58 --> 913.80]  really have an analog of that today.
[913.80 --> 916.70]  I mean, I know I'm looking at Steve, who I'm sure.
[917.00 --> 917.10]  Yeah.
[917.14 --> 918.92]  I can come up with a couple, but I'd like him to answer.
[920.02 --> 925.34]  Oh, micro-code is simply you have a, a low-level interpreter that is interpreting the target
[925.34 --> 926.56]  instruction set of the machine.
[926.56 --> 929.54]  And that was a very common implementation technique.
[929.90 --> 931.18]  And so it's probably still used underneath.
[931.34 --> 933.56]  I mean, it is used underneath, under the hood for you.
[933.64 --> 935.52]  X86 obviously has its own micro-code underneath.
[935.52 --> 935.80]  Yes, of course.
[936.00 --> 938.22]  But you can't write that micro-code today.
[938.36 --> 938.76]  That's correct.
[938.80 --> 940.02]  And you couldn't then either.
[940.20 --> 940.46]  Interesting.
[940.56 --> 946.02]  But the implementers of this system architecture were implementing the target instruction set
[946.02 --> 950.20]  in micro-instructions, about 10 instructions per target instruction.
[950.20 --> 954.06]  So it was, it all netted out to approximately the same performance.
[954.16 --> 954.76]  The same performance.
[954.96 --> 955.20]  Interesting.
[955.42 --> 957.44]  And so, and you were actually writing micro-code at that point?
[957.60 --> 957.62]  Or?
[957.74 --> 962.16]  No, I was on a architecture team that really didn't do much of anything.
[962.40 --> 962.68]  I got it.
[962.92 --> 964.56]  I was just simply calculating.
[964.82 --> 965.38]  Calculating the days.
[965.64 --> 966.98]  When my two lines would cross.
[967.10 --> 967.50]  There you go.
[967.50 --> 971.66]  You know, my, my, my savings and my debt crossed and I was, I was off to Intel.
[972.18 --> 973.76]  Oh, Intel was the next stop.
[973.86 --> 974.36]  Yes, it was.
[974.58 --> 975.08]  That's dope.
[975.54 --> 977.16]  So what did you work on at Intel?
[977.16 --> 984.32]  Intel used to be a large producer of memory and they had, you know, they produced DRAM.
[985.08 --> 986.40]  Not all the DRAM was good.
[986.94 --> 990.00]  Every, every process has some waste.
[990.58 --> 996.04]  Intel was producing a, a disk emulator for IBM mainframes called the 3805.
[996.22 --> 1003.24]  And this was, it had a very interesting memory controller that could deal with chips that were
[1003.24 --> 1005.08]  partially correct and mask that.
[1005.08 --> 1009.80]  So it was a great place to put, to, to pack in memory, possibly memory that you weren't
[1009.80 --> 1012.02]  able to sell at retail.
[1012.52 --> 1020.36]  And, and then deliver a solid state disk, something that sat on an IBM channel and provided, you
[1020.36 --> 1023.36]  know, provided better, presumably better performance.
[1023.60 --> 1026.50]  What was interesting was that it didn't.
[1026.66 --> 1030.78]  It was actually significantly slower than the fixed head disk.
[1030.78 --> 1037.70]  And I interviewed at Intel and being, you know, and they told me about this project and they
[1037.70 --> 1039.66]  said that they had, you know, a serious issue.
[1039.78 --> 1045.06]  They had a backlog of a quarter of a billion dollars for these systems and everyone they'd
[1045.06 --> 1049.88]  shipped had been returned for being slower than the physical disk that the solid state
[1049.88 --> 1050.80]  device was emulating.
[1051.04 --> 1051.50]  That's bad.
[1051.72 --> 1051.92]  Yeah.
[1052.00 --> 1052.54]  That's not good.
[1052.54 --> 1055.30]  And it didn't make any sense to me.
[1055.44 --> 1060.30]  So being, you know, somewhat cocky, you know, 22 year old, I said, oh, I could fix that.
[1060.30 --> 1063.14]  I mean, I knew it was, you know, just maybe that was sloppy code.
[1063.22 --> 1066.86]  I didn't know, but I very confidently said I could deal with that.
[1067.54 --> 1074.72]  And I, well, I went back to finish my two weeks at Honeywell and I looked in the, in, in, in a
[1074.72 --> 1079.88]  industry rag called Computer World, which is still around, but was very popular in the
[1079.88 --> 1080.48]  late seventies.
[1080.76 --> 1085.26]  And I saw an interview with the head of, of, of this group, the fellow I just interviewed
[1085.26 --> 1085.60]  with.
[1086.44 --> 1089.68]  And it, and in there he said, well, you know, yes, it's true.
[1089.76 --> 1093.86]  We have this backlog, but we have a solution in hand and we're going to be shipping it in
[1093.86 --> 1094.18]  a month.
[1094.24 --> 1095.88]  So I said, well, maybe they don't need me.
[1095.92 --> 1098.56]  I called him up and I said, yeah, I just read this.
[1098.86 --> 1099.18]  Exactly.
[1099.54 --> 1100.48]  I was the solution.
[1101.12 --> 1102.68]  I said, are you sure you need me?
[1102.68 --> 1104.44]  It sounds like you've solved this in the last week.
[1104.44 --> 1104.90]  I definitely need you.
[1105.22 --> 1105.98]  You are the solution.
[1106.46 --> 1106.86]  Wow.
[1106.98 --> 1107.90]  You've heard it, a PR crisis.
[1108.06 --> 1112.68]  And I hadn't really drank a lot before then, but for the next two weeks, I needed a little
[1112.68 --> 1114.46]  bit of help getting back, getting to sleep at night.
[1114.46 --> 1117.60]  I wasn't sure that I really could follow through on this.
[1117.60 --> 1118.60]  You renegotiated your offer.
[1119.32 --> 1120.26]  And what happened?
[1120.42 --> 1120.86]  What did you find?
[1120.96 --> 1125.88]  Well, I showed up and looked at this machine, scratched my head for a bit and stayed up all
[1125.88 --> 1130.94]  night with it for probably two or three weeks with a logic analyzer, trying to find
[1130.94 --> 1137.54]  out why this, you know, simple 8086, you know, instruction path was slower than the, than
[1137.54 --> 1140.90]  this physical disk that should be easy to beat.
[1141.14 --> 1142.84]  Turned out it was one instruction.
[1143.06 --> 1150.20]  It was a repeat move string byte that was used to reinitialize a condition code table for
[1150.20 --> 1151.38]  the channel control program.
[1151.86 --> 1154.68]  And just, it didn't catch the one instruction.
[1154.84 --> 1159.48]  That was, that was adding sufficient extra time that it made it slower than the fixed head
[1159.48 --> 1159.76]  disk.
[1159.76 --> 1161.70]  There were two factors in play there.
[1161.80 --> 1167.70]  One, their control path was slower, but the other was they didn't understand how the operating
[1167.70 --> 1169.56]  systems used a fixed head disk.
[1169.74 --> 1173.16]  They figured the, you know, they knew what the rotational latency was.
[1173.26 --> 1175.16]  They knew the switching time is close to zero.
[1175.32 --> 1180.30]  So they assumed that the average performance would be approximately half the rotational latency.
[1180.70 --> 1186.54]  But of course, IBM has had, had had many years to perfect this technology.
[1186.54 --> 1190.56]  And the OS is sorted the sector.
[1190.90 --> 1197.36]  So the control program would organize the requests so that it would be doing, you know, position
[1197.36 --> 1199.20]  one, position two, position three.
[1199.34 --> 1204.74]  So assuming let's say there were three tracks, three block positions on a single track, they
[1204.74 --> 1209.40]  would always go, let's say, modulo three and order them zero, one, two, zero, one, two.
[1209.40 --> 1214.36]  And then the other operating systems, they have one time sharing system that used a little
[1214.36 --> 1218.86]  bit different strategy, but also was able to effectively get the rotational latency to
[1218.86 --> 1219.64]  close to zero.
[1219.76 --> 1224.48]  They just, they put in some spacer records that handled the head switching time and the
[1224.48 --> 1228.98]  time for the control program so that the effective rotational latency was zero.
[1228.98 --> 1235.42]  And the folks at Intel who were great in microcontrollers and, and, and in process technology, they, that
[1235.42 --> 1236.22]  wasn't their specialty.
[1236.36 --> 1239.90]  They didn't know what operating system designers at IBM had, had cooked up.
[1239.98 --> 1242.80]  So they, they set their target too low.
[1242.84 --> 1245.28]  The product was simply released before they'd achieved it.
[1245.54 --> 1249.72]  What was a useful performance metric for their, for their customer.
[1249.88 --> 1250.14]  Wow.
[1250.28 --> 1250.56]  Wow.
[1250.92 --> 1252.04]  That is insane.
[1252.06 --> 1254.04]  They didn't do a quarter billion dollars.
[1254.16 --> 1255.94]  There's so much in there.
[1256.00 --> 1256.80]  That's mind blowing.
[1256.80 --> 1259.28]  I'm going to have to go back and unpack that a little bit.
[1259.38 --> 1266.50]  So first of all, it's a solid state disc at a, this is, I mean, we now call an SSD, but
[1266.50 --> 1269.66]  this is long before solid state discs were.
[1269.68 --> 1270.72]  This is 1979.
[1271.64 --> 1274.50]  And so was it, but it was still volatile, I assume.
[1274.78 --> 1275.08]  Yes.
[1275.24 --> 1276.76]  It had a motor generator.
[1276.76 --> 1283.74]  So the wall power was plugging a, a rotating generator that, or a motor that was running a
[1283.74 --> 1287.22]  generator and provided generated power to the memory.
[1287.36 --> 1292.82]  So that was to avoid potential corruption from, from, from glitches in wall power.
[1293.44 --> 1294.16]  That's cool.
[1294.78 --> 1296.00]  So this thing was loud.
[1296.38 --> 1296.80]  Oh yeah.
[1296.92 --> 1298.14]  It was just data center equipment.
[1298.56 --> 1299.40]  You weren't supposed to care.
[1299.40 --> 1305.48]  And then on an actual power failure, what would it, would it, did it have any way of getting
[1305.48 --> 1307.08]  that out to, to non-volatile storage?
[1307.40 --> 1311.02]  Oh, well, the assumption was the environment it would be had, uh, had battery backup.
[1311.20 --> 1314.28]  But this, uh, this would carry it through, uh, those transitions.
[1314.82 --> 1315.18]  Wow.
[1315.36 --> 1315.70]  Interesting.
[1315.82 --> 1317.22]  What was the capacity of this thing?
[1317.40 --> 1318.76]  That I can't tell you.
[1318.82 --> 1322.12]  This is again, that red, that register was filled and reused many years ago.
[1322.14 --> 1322.74]  No problem though.
[1322.74 --> 1323.24]  It's so missing.
[1323.32 --> 1325.80]  And then I latched onto the same thing you latched onto, Steve, about the backlog.
[1326.44 --> 1328.30]  Quarter of a billion dollars of backlog.
[1328.30 --> 1331.56]  One instruction set led to a quarter billion dollars of backlog.
[1331.70 --> 1333.70]  Well, they eventually delivered against that backlog.
[1334.04 --> 1339.04]  So, you know, they were held up for a number of months while trying to understand this performance
[1339.04 --> 1339.44]  issue.
[1339.54 --> 1340.54]  And again, it was two-sided.
[1340.66 --> 1345.42]  One is they'd, they had set the release criteria, uh, too high.
[1345.66 --> 1350.32]  So they were thinking, you know, three, four milliseconds, uh, was going to be fine when
[1350.32 --> 1355.96]  in fact they needed to be, you know, a fraction of a millisecond due to the, uh, the strategies
[1355.96 --> 1358.84]  that the OS was using in, in, in scheduling IO.
[1359.12 --> 1364.86]  And then, uh, they were also too slow simply due to repeat, move, string, byte.
[1365.02 --> 1365.14]  Right.
[1365.28 --> 1369.90]  And so, and so Steve, for context, it may help to know that this is an instruction, a single
[1369.90 --> 1371.48]  instruction that can do a lot of work.
[1371.48 --> 1376.70]  In this case, 256 bytes at a time where it could have been 128 words.
[1376.70 --> 1379.60]  This was a 16 bit machine that would have already sped it up.
[1379.60 --> 1385.76]  But the truth was only a half a dozen entries in the, uh, in that table would typically need
[1385.76 --> 1388.90]  to be reset following a single IO request.
[1388.90 --> 1394.78]  So the way the table was used was given the instructions that were in the channel program,
[1395.46 --> 1400.06]  the, there were only certain instructions that were legal for the next instruction.
[1400.06 --> 1403.20]  And then following that instruction, there were other instructions that were legal.
[1403.20 --> 1408.18]  So this was determining whether the opcodes that were used in the IBM channel program,
[1408.30 --> 1411.50]  uh, were legal at that point in the program.
[1411.50 --> 1416.12]  At the end of the IO request, you would have to reset that back to an initial state.
[1416.12 --> 1421.62]  Clearly you could track what changes had taken place and then reset those half a dozen
[1421.62 --> 1425.02]  invalid operations, uh, at the end of the request.
[1425.22 --> 1425.60]  That's interesting.
[1425.64 --> 1430.52]  Is there, is there an analog to something that you've seen or that we've seen recently that
[1430.52 --> 1436.92]  would, that would map to that kind of low level single instruction set that, that had
[1436.92 --> 1439.02]  so many, so far reaching implications.
[1439.16 --> 1440.52]  Single instruction, just to be clear.
[1440.60 --> 1441.14]  Single instruction.
[1441.24 --> 1441.36]  Yeah.
[1441.42 --> 1445.90]  Not even instruction set, but it's a single instruction that was, uh, I mean, a single
[1445.90 --> 1448.00]  instruction can still do a lot of damage today.
[1448.00 --> 1448.42]  I think.
[1448.42 --> 1450.78]  It can, but this was somewhat unique.
[1450.96 --> 1452.74]  We were dealing with slower memory systems.
[1453.00 --> 1458.46]  So anything that moved, uh, 256 bytes of memory had a pretty significant delay for someone
[1458.46 --> 1462.78]  reading a simpler code, you know, an instruction looks like every other instruction.
[1462.90 --> 1464.74]  Uh, they, they seem fairly equivalent.
[1464.96 --> 1471.20]  You don't recognize that there is a two order of magnitude potential disparity between one instruction
[1471.20 --> 1472.96]  and the next one that followed it in the listing.
[1472.96 --> 1475.70]  And I think that's what, through the team that was working on it.
[1475.70 --> 1477.36]  So you had a pretty successful first two weeks of work.
[1477.86 --> 1479.38]  Oh, it was a lot of fun.
[1479.56 --> 1483.80]  I have to admit, uh, the, the, I was like two or three in the morning and I'm staring at
[1483.80 --> 1485.98]  a logic analyzer and I'm tracking it down.
[1485.98 --> 1490.12]  And suddenly I get to that page in the listing and there's a repeat string byte.
[1490.12 --> 1491.08]  And I smiled.
[1491.16 --> 1491.90]  Oh, that must've been glorious.
[1491.90 --> 1492.18]  Smiled.
[1492.34 --> 1492.82]  Smiled.
[1492.98 --> 1493.12]  Yeah.
[1493.12 --> 1493.48]  Yeah.
[1493.72 --> 1494.14]  Exactly.
[1494.56 --> 1497.06]  I was pretty excited.
[1497.24 --> 1500.62]  It took about 15 minutes to code up, uh, you know, the alternate implementation.
[1500.62 --> 1505.54]  And, uh, you know, I, I got to sleep that night without, without a little bit of cognac.
[1505.88 --> 1507.62]  That is amazing.
[1507.90 --> 1512.94]  Um, and the, I can, if you did not admit a howl, I'm impressed with your self-control.
[1513.24 --> 1516.50]  Um, I, I've been known to howl over much smaller funds.
[1516.76 --> 1518.92]  So two bits of, of interesting context there.
[1519.18 --> 1523.14]  One, so channel programs are something, I mean, Jess, do you know, you probably don't
[1523.14 --> 1524.02]  know what a channel program is.
[1524.08 --> 1524.18]  Yeah.
[1524.20 --> 1526.52]  So this is the way, I mean, you want to explain what a channel program is, Jeff?
[1526.52 --> 1534.10]  Well, uh, the IO is performed by a second computer that, uh, had an interface to the mainframe
[1534.10 --> 1538.48]  and executed simple programs for, for doing IO.
[1538.72 --> 1543.56]  And they could deal with tape operations and could, you know, knew the intricacies of tape,
[1543.56 --> 1549.02]  but you didn't program the IO controllers directly from the main instruction set.
[1549.14 --> 1553.36]  You'd create a program and deliver that to the, uh, to the channel controller.
[1553.36 --> 1555.74]  And this is something that's coming back a little bit.
[1555.84 --> 1560.60]  I mean, not channel programs per se, but the idea of having compute spread away and kind
[1560.60 --> 1562.34]  of pushing compute elsewhere to actually.
[1562.54 --> 1567.26]  So when you look at like all the offload that we do right on, on the, on the NICs, for example,
[1567.44 --> 1572.04]  smart NICs are kind of a modern channel program, albeit in a different form.
[1572.40 --> 1575.40]  Uh, the other thing that's interesting is the, is the CISC versus RISC.
[1575.46 --> 1578.70]  So if you've the complete instruction set versus a reduced instruction set.
[1578.70 --> 1584.40]  And so what, what Jeff found was a single instruction doing a lot of work and this is predated risk.
[1584.40 --> 1587.50]  Obviously risk is, it wouldn't happen for another couple of years, right?
[1587.96 --> 1588.46]  That's true.
[1588.56 --> 1594.46]  But what we did at that point, because removing that instruction, uh, certainly moved the product
[1594.46 --> 1596.36]  forward and they were able to start making deliveries.
[1596.54 --> 1600.86]  It still could have been faster and, and wasn't meeting full potential of the architecture.
[1600.86 --> 1607.66]  So we re-implemented the control program using the AMD 2900 series, uh, logic family.
[1607.82 --> 1613.46]  So we created a bit slice processor and we're able to achieve much better performance than we could
[1613.46 --> 1614.16]  with an 8086.
[1614.42 --> 1616.44]  And the AMD 29K isn't really risk.
[1616.94 --> 1617.68]  I mean, that is a risk.
[1617.82 --> 1617.98]  Yes.
[1618.10 --> 1620.44]  Well, this was the 2900 series.
[1620.64 --> 1621.24]  Not the 29K.
[1621.32 --> 1621.52]  Yes.
[1621.52 --> 1626.14]  And so this was a bit slice model where you could really define, you had a, you had a
[1626.14 --> 1630.46]  opcode controller, but then you had, you could choose the register sets separately and you
[1630.46 --> 1634.68]  could almost design your own instruction set out of the 2900 series.
[1634.78 --> 1636.36]  That was an amazing architecture.
[1636.46 --> 1640.78]  I would like to point out there's an AMD 29K manual about eight inches behind you.
[1641.50 --> 1641.82]  Exactly.
[1642.14 --> 1645.16]  Well, listen, I'm just very, this is the, well, maybe I hope I'm not, I'm remembering
[1645.16 --> 1647.68]  it correctly when it was 2900 versus 29K.
[1647.80 --> 1649.24]  No, I never programmed it.
[1649.26 --> 1651.54]  It just, it maybe, maybe it's the same logic family.
[1651.76 --> 1656.42]  So, but I always, I mean, my read on it was, it was always viewed as this real great
[1656.42 --> 1658.54]  step forward in CPU design that never really caught on.
[1658.64 --> 1659.56]  Is that a fair read?
[1659.56 --> 1664.38]  Well, there were actually quite a few target machines that were implemented in, in the
[1664.38 --> 1665.40]  AMD family.
[1665.54 --> 1669.86]  So they use the bit slice processor for the micro instructions and you, and then implement
[1669.86 --> 1672.46]  the target instruction with that logic family.
[1672.62 --> 1674.10]  It was an interesting architecture.
[1674.52 --> 1679.84]  My role in the project, I wrote the assembler that the others on the team used in order to
[1679.84 --> 1684.16]  write instructions for this 2900 family instruction set.
[1684.16 --> 1690.74]  And that was a, a fun process, you know, the, because I could, I knew who my target audience
[1690.74 --> 1691.66]  of developers were.
[1691.78 --> 1694.90]  So I would put, but I wouldn't call them Easter eggs.
[1695.04 --> 1701.20]  I, I, I, I would put targeted error messages in that scolded the developers based on my knowledge
[1701.20 --> 1702.00]  of their habits.
[1702.00 --> 1707.74]  Can you get, do you remember any examples of, of, of, of a particular developer that was
[1707.74 --> 1708.44]  scolded in this way?
[1708.56 --> 1709.72]  Oh, one fellow.
[1710.00 --> 1714.30]  I don't remember what his habit was, but I, I, I knew he would, he would eventually do it.
[1714.70 --> 1720.66]  And I just addressed him by name and, you know, said, you know, to, to air is human, but you're
[1720.66 --> 1721.20]  a programmer.
[1721.20 --> 1722.40]  Something, something's about that.
[1722.84 --> 1723.26]  That's good.
[1723.42 --> 1724.08]  That is great.
[1724.50 --> 1728.78]  It, it, it, people were working on, on what's called an Intel development system.
[1728.90 --> 1730.42]  These were single user workstations.
[1730.54 --> 1733.04]  So you don't have, your machine is not network connected.
[1733.26 --> 1737.56]  So to have the tool that you've been using for a month or two suddenly address you by
[1737.56 --> 1741.56]  name, that is a particularly unnerving experience.
[1741.92 --> 1742.02]  Yes.
[1742.26 --> 1742.68]  Oh yeah.
[1742.70 --> 1746.26]  You know, in a network connected computer, your first thought is, is I've been hacked.
[1746.50 --> 1746.76]  Right.
[1746.76 --> 1751.14]  And, but you know, this is, this is a workstation sitting on your desk connected to nothing.
[1751.20 --> 1752.06]  That is beautiful.
[1752.48 --> 1753.18]  That is amazing.
[1753.22 --> 1754.46]  That has given me ideas.
[1754.58 --> 1755.20]  I was going to say.
[1755.80 --> 1757.22]  That is, that is amazing.
[1757.34 --> 1757.48]  I know.
[1757.50 --> 1760.98]  I love the, the custom error messages, but you've got to, you know, you got to think way
[1760.98 --> 1761.52]  in advance.
[1762.08 --> 1763.24]  That's, that's very impressive.
[1763.40 --> 1766.12]  You knew the, the error messages that repeat the errors that people were going to hit.
[1766.74 --> 1768.88]  We're going to take a quick break.
[1769.20 --> 1772.92]  And then we will be back with, with more Jeff Rothschild.
[1775.08 --> 1778.36]  On the Metal is brought to you by the Oxide Computer Company.
[1778.56 --> 1780.10]  Wait, did you say computer company, Jess?
[1780.20 --> 1780.86]  Yes, indeed.
[1780.86 --> 1781.70]  But wait a minute.
[1781.80 --> 1782.80]  Everyone runs on the public cloud.
[1782.92 --> 1785.16]  Jeff Bezos owns and operates every computer on the planet.
[1785.30 --> 1787.18]  Why would anyone start a computer company?
[1787.40 --> 1788.42]  That is so not true.
[1788.60 --> 1793.96]  I have spent a bunch of time talking to folks who are still running on premises and actually
[1793.96 --> 1799.18]  like the consensus among all of them is just a feeling of neglect because everyone thinks
[1799.18 --> 1801.48]  that like everything is moving to the public cloud, but it's not.
[1801.60 --> 1804.60]  If you're still running on premises, it's because you haven't heard of the cloud, right?
[1804.60 --> 1810.66]  No, there are really good reasons for running on premises still for security, for latency,
[1810.92 --> 1812.74]  strategic reasons for your business.
[1813.22 --> 1813.34]  Wow.
[1813.42 --> 1816.88]  The people running on premises must feel like everyone has ignored them.
[1817.16 --> 1818.04]  They do indeed.
[1818.04 --> 1823.16]  So if this is you, please head on over to our website, Oxide.computer.
[1823.30 --> 1827.04]  Sign up for our mailing list and we would love to get in touch and hear your stories.
[1827.16 --> 1831.58]  We acknowledge that you exist and you've got some really hard technical problems that we're
[1831.58 --> 1831.88]  solving.
[1832.06 --> 1833.60]  Oxide.computer, come join us.
[1833.60 --> 1835.48]  All right.
[1835.58 --> 1836.24]  Welcome back.
[1836.36 --> 1843.22]  We are all sitting slack-jawed listening to some terrific stories of the hardware software
[1843.22 --> 1844.60]  interface from Jeff Rothschild.
[1844.96 --> 1849.88]  So Jeff, you're talking about customizing error messages in the assembler that you put.
[1850.18 --> 1854.78]  Well, the fun thing with the assembler was that we were trying to squeeze every cycle out
[1854.78 --> 1855.68]  of the machine.
[1856.14 --> 1861.54]  So the only piece of novel technology that I had in there was that I could look forward
[1861.54 --> 1865.66]  in the assembly program and see, for example, when a condition code would get used.
[1866.02 --> 1868.96]  And I might see that it was used in the next instruction.
[1869.44 --> 1874.50]  So I would increase the time for the current instruction to allow that condition code to
[1874.50 --> 1878.70]  settle through the ALU and then be settled in the condition code.
[1878.80 --> 1885.22]  Where if the result of an arithmetic operation was two or three instructions later, then I could
[1885.22 --> 1887.90]  start the next instruction without any additional delay.
[1888.28 --> 1889.90]  So it was sort of pipeline optimized.
[1889.90 --> 1890.32]  Yeah, right.
[1890.60 --> 1891.32]  Yeah, it really was.
[1891.32 --> 1892.44]  That's amazing.
[1892.74 --> 1893.70]  And so that was fun to do.
[1893.82 --> 1896.70]  So what would happen if your assembler didn't make that optimization?
[1897.18 --> 1897.74]  What would happen?
[1897.92 --> 1900.08]  Well, you would have had to have default.
[1900.34 --> 1906.48]  Well, if you set everything too short, then you would have a test and the test may give
[1906.48 --> 1912.02]  the result the wrong result because the condition code hadn't propagated through the ALU.
[1912.38 --> 1912.66]  Wow.
[1912.78 --> 1914.54]  So the assembler is actually load-bearing here.
[1914.62 --> 1916.60]  The assembler is responsible for correctness.
[1916.70 --> 1917.08]  That's correct.
[1917.08 --> 1924.20]  The assembler, and of course, in modern processors, this type of instruction scheduling and variable
[1924.20 --> 1927.18]  delays are all done by the micro instruction set.
[1927.34 --> 1929.38]  But this was done in the assembler.
[1929.92 --> 1930.26]  Wow.
[1930.64 --> 1932.24]  That is scary.
[1932.46 --> 1939.42]  I mean, do you think your assembler had any bugs in it that were found the hard way?
[1939.42 --> 1941.98]  I've never written anything that didn't have bugs in it.
[1942.04 --> 1942.96]  So the odds are yes.
[1944.52 --> 1947.02]  But just, I mean, debunking that must have been a challenge.
[1947.50 --> 1952.34]  Well, clearly you could start by putting in very conservative values and then you'd always
[1952.34 --> 1953.22]  have a test version.
[1953.22 --> 1959.78]  So you could make the worst case assumption and then determine whether your optimizations
[1959.78 --> 1960.78]  had introduced a problem.
[1961.20 --> 1962.98]  And so where are you at Intel at this time?
[1963.08 --> 1963.68]  This is at Intel.
[1963.80 --> 1964.66]  Working on AMD.
[1965.02 --> 1965.98]  Working using an AMD.
[1966.32 --> 1967.66]  I just wanted to like check myself.
[1967.76 --> 1969.04]  I don't know if anyone else had the same like.
[1969.04 --> 1972.54]  I didn't even like put the two and two together until I was like, wow, that's weird.
[1972.54 --> 1977.90]  In fact, our whole team had to go to AMD headquarters, which was just down the street and, you know,
[1977.90 --> 1980.90]  take a training course on the AMD that slice architecture.
[1981.66 --> 1986.22]  And in the AMD training, they asked everyone to say who they worked for.
[1986.58 --> 1990.22]  And of course, it was all various countries building control, companies building control
[1990.22 --> 1990.74]  processors.
[1990.74 --> 1995.62]  And they got to the Intel group and it was one person from Intel, second person from Intel,
[1995.80 --> 1996.48]  third from Intel.
[1996.90 --> 2002.08]  I think the last member of the group said, you know, so-and-so from Intel, corporate espionage.
[2002.54 --> 2004.80]  Put it right out there.
[2005.00 --> 2005.50]  That's good.
[2005.62 --> 2008.74]  Are Intel and AMD even considered to be competitors at this time?
[2008.86 --> 2009.30]  Of course they are.
[2009.30 --> 2009.62]  Oh, they are.
[2009.72 --> 2009.82]  Okay.
[2009.98 --> 2014.40]  I mean, that's the, you know, they are the only competitors in that space.
[2014.48 --> 2016.18]  But at that time, they're competitors.
[2016.50 --> 2024.84]  They didn't compete for the, for, AMD did not have an x86 processor in 1981.
[2025.22 --> 2025.48]  Right.
[2025.60 --> 2025.98]  Or 1980.
[2026.26 --> 2029.76]  And does Intel even think of themselves as a microprocessor company in 1981?
[2030.52 --> 2030.92]  Oh, of course.
[2030.92 --> 2031.32]  Oh, it did.
[2031.42 --> 2031.52]  Okay.
[2031.68 --> 2032.00]  Oh, yeah.
[2032.00 --> 2039.08]  Intel had had, you know, their 8080 and then the 8086 and 8088.
[2039.76 --> 2041.66]  But this is still pre-PC.
[2042.20 --> 2043.36]  This is post-PC.
[2043.46 --> 2043.78]  Post-PC.
[2044.16 --> 2044.32]  Okay.
[2044.46 --> 2048.92]  About the time that the PC had come out, which was an 8088-based machine initially.
[2049.24 --> 2051.14]  And that, I assume, changed everything inside of Intel.
[2051.22 --> 2051.64]  I would assume.
[2051.74 --> 2052.02]  Maybe not.
[2052.02 --> 2053.22]  Yeah, they became a PC company.
[2053.36 --> 2053.58]  Right.
[2053.82 --> 2055.94]  So were you working at Intel when you bought the PC?
[2056.20 --> 2057.42]  I had left Intel.
[2057.78 --> 2058.06]  Okay.
[2058.06 --> 2059.36]  So I had gone off on my own.
[2060.36 --> 2060.52]  Well.
[2060.52 --> 2061.22]  But it was interesting.
[2061.34 --> 2065.58]  Intel had the potential to have been a PC company.
[2065.58 --> 2069.82]  The workstations that I made reference to a few moments ago were PCs.
[2070.76 --> 2075.92]  An Intel development station ran a MS-DOS-like operating system.
[2075.92 --> 2078.64]  All of these were influenced by RT11.
[2079.20 --> 2086.50]  And so if you were a user of a DEC RT11, you would recognize many aspects of the OS interface
[2086.50 --> 2089.20]  and the software development process on the machine.
[2089.88 --> 2093.08]  Intel was selling these at $10,000 or $15,000 a seat.
[2093.08 --> 2097.88]  They weren't interested in, you know, undercutting their existing market.
[2098.06 --> 2100.80]  I think if they'd understood the potential for personal computing,
[2101.00 --> 2103.78]  they could have rebranded that machine and dropped it on the market.
[2103.90 --> 2106.46]  It was not that fundamentally different than an IBM PC.
[2106.64 --> 2107.12]  It was blue.
[2107.56 --> 2108.98]  Other than that, it was the same thing.
[2109.12 --> 2109.42]  Interesting.
[2109.90 --> 2111.22]  And it was running.
[2111.48 --> 2112.64]  So what was the operating system that was running?
[2112.66 --> 2113.40]  Was it Intel author?
[2113.44 --> 2117.44]  It was an Intel operating system, but very similar to what you would have found on a,
[2117.56 --> 2118.70]  like an RT11 system.
[2118.82 --> 2119.04]  Right.
[2119.52 --> 2121.26]  Was the slash pointing the right direction?
[2121.82 --> 2122.94]  That I can't tell you.
[2122.94 --> 2125.84]  I was still trying to figure out where humanity went so wrong.
[2125.98 --> 2128.24]  And the forward slash somehow fell over.
[2128.46 --> 2129.50]  I guess it was CPM.
[2129.64 --> 2130.22]  What did it used to be?
[2130.86 --> 2133.06]  It was on Windows and DOS.
[2133.32 --> 2136.36]  It's a backslash, not a forward slash to delineate path names.
[2136.80 --> 2138.98]  And on Unix, famously, it was a forward slash.
[2139.00 --> 2144.44]  And that was, of course, a challenge in building this DOS to Unix file server,
[2144.76 --> 2148.36]  was dealing with the equivalence of forward and backward slashes.
[2148.36 --> 2154.74]  And then had to deal with a number of differences in semantics between the Windows,
[2155.70 --> 2159.22]  or I should say the DOS environment and the Unix environment.
[2159.22 --> 2164.70]  I made a mention to the file control block on DOS that programs would do IO after they
[2164.70 --> 2165.42]  close the file.
[2165.52 --> 2166.68]  Well, that doesn't work on Unix.
[2166.68 --> 2174.32]  So if you have a simple, if your server program, which is serving IOs on the Unix side,
[2174.74 --> 2178.74]  does a file close, all the context for that close is gone.
[2178.92 --> 2184.20]  But I had to implement a cache of previously opened files.
[2184.20 --> 2184.92]  To accommodate this.
[2184.92 --> 2188.32]  In order so that when somebody, when a read came in on the old file descriptor,
[2188.40 --> 2192.34]  I would have, you know, I'd be able to uniquely identify it was for that file descriptor
[2192.34 --> 2194.08]  and then reopen the file.
[2194.62 --> 2197.44]  And would this be considered a bug in the, I mean,
[2197.52 --> 2200.48]  was the interface that you were allowed to do this deliberate?
[2200.86 --> 2202.52]  I suspect it was deliberate.
[2202.52 --> 2208.50]  Some of the top selling applications of the day, like dBase, made, you know, common use of this.
[2208.60 --> 2211.96]  They closed the file and there were some advantages to closing the file,
[2211.96 --> 2216.12]  I assume in cleanliness and not be able to flush buffers, but then continue to do
[2216.12 --> 2217.90]  reads and writes on the file.
[2218.26 --> 2220.80]  So what handle do they have back to operate on that file?
[2220.84 --> 2221.76]  Do they have an FD equipment?
[2222.10 --> 2222.94]  It's just like an address.
[2223.10 --> 2223.32]  Okay.
[2223.42 --> 2224.12]  File control block.
[2224.40 --> 2225.56]  But is that address reference?
[2225.88 --> 2228.72]  How is this safe at any speed is what I'm trying to grab my mind around.
[2228.74 --> 2229.86]  I don't think it was.
[2229.98 --> 2230.16]  Okay.
[2230.52 --> 2232.46]  This was a real memory system.
[2232.62 --> 2236.10]  If you wrote over the file control block, it would have random information in it.
[2236.16 --> 2237.18]  You do an IO on it.
[2237.24 --> 2239.76]  You're changing random spots on the disk.
[2240.62 --> 2241.94]  And the machine would reboot.
[2241.96 --> 2242.32]  Of course.
[2242.32 --> 2245.28]  Do you triple fault or you'd just get random corruption or anything else?
[2245.40 --> 2246.32]  And then you'd reinstall.
[2246.46 --> 2246.68]  Yes.
[2247.10 --> 2250.40]  This was not a protected memory system.
[2250.84 --> 2261.40]  One other fun bug in building the PC interface product was that it was on a DOS system.
[2261.40 --> 2270.40]  You can truncate a file by writing to...
[2271.04 --> 2272.28]  Oh, actually, I'm trying to remember this.
[2272.28 --> 2274.76]  How this worked.
[2274.84 --> 2281.66]  But you would be able to write zero bytes to an arbitrary location in the file.
[2281.76 --> 2282.56]  I think that truncates.
[2282.98 --> 2283.22]  Okay.
[2283.22 --> 2283.30]  Okay.
[2283.70 --> 2286.74]  And so being able to...
[2286.74 --> 2289.54]  And that's one reason people would write on a closed file.
[2289.76 --> 2295.60]  They would know that a portion of that file was unused space because they compacted it,
[2295.62 --> 2296.06]  for example.
[2296.26 --> 2300.96]  And then they would do a zero byte write after the last byte that was in use.
[2300.96 --> 2303.20]  And that would truncate the size of the file.
[2303.64 --> 2304.54]  And so you had to honor that?
[2304.74 --> 2305.38]  Oh, we had to.
[2305.46 --> 2312.26]  Well, the first implementation of that on Unix was to rewrite the file and just write it up to the point
[2312.26 --> 2314.36]  where the truncate occurred.
[2314.42 --> 2315.16]  And then you just don't write.
[2315.24 --> 2315.86]  You'd close it.
[2316.28 --> 2317.32]  But of course...
[2317.32 --> 2319.08]  Now, the performance is terrible.
[2319.32 --> 2324.42]  Well, it was particularly terrible if the application you were supporting is one that was going
[2324.42 --> 2330.56]  through a compaction algorithm and wanted to be back in clean state after each phase of the
[2330.56 --> 2331.30]  compaction algorithm.
[2331.42 --> 2333.96]  Well, it may be a thousand phases in compaction.
[2334.54 --> 2336.46]  So there'd be a thousand of these truncates.
[2336.58 --> 2336.88]  Oh, my gosh.
[2336.88 --> 2341.36]  And now you're copying the file over itself, basically copying to a new file and then,
[2341.36 --> 2345.22]  you know, renaming and deleting the first one and then doing it again a thousand times on the
[2345.22 --> 2345.72]  Unix side.
[2345.72 --> 2352.00]  So some very simple, fast operations on DOS were taking days on the Unix side.
[2352.16 --> 2355.98]  So we had Bell Labs implement a truncate operation.
[2356.68 --> 2357.12]  That's F-truncate.
[2357.14 --> 2357.86]  Which is still there.
[2357.94 --> 2358.86]  Yeah, F-truncate is still there.
[2358.92 --> 2362.66]  And so F-truncate was added in order to support this behavior on DOS.
[2362.68 --> 2363.28]  Oh, my God.
[2363.34 --> 2365.14]  That's the origin story of F-truncate?
[2365.28 --> 2365.70]  That's correct.
[2365.78 --> 2366.88]  What is F-truncate today?
[2367.06 --> 2370.12]  F-truncate is the Unix interface to truncate a file.
[2370.22 --> 2371.98]  But it's explicit about it.
[2371.98 --> 2376.82]  And what Jeff is pointing out is prior to the introduction of F-truncate, there was no
[2376.82 --> 2377.62]  way to truncate a file.
[2377.90 --> 2378.08]  Yeah.
[2378.20 --> 2378.26]  That's crazy.
[2378.26 --> 2379.66]  You'd have to rewrite it.
[2380.16 --> 2383.40]  I mean, you could open it O-trunk, but that might not have existed.
[2383.86 --> 2385.40]  I mean, F-truncate certainly...
[2385.40 --> 2386.64]  No, this was why it was added.
[2386.78 --> 2388.04]  It was because of...
[2388.04 --> 2388.46]  That's amazing.
[2388.46 --> 2391.30]  You know, and AT&T was sponsoring this work.
[2391.36 --> 2391.58]  Right.
[2391.70 --> 2392.08]  So...
[2392.08 --> 2392.62]  On the 3B2.
[2392.62 --> 2393.74]  On the 3B2.
[2393.96 --> 2400.40]  And so they added the truncate operation because, you know, closing a D-base file took days.
[2400.60 --> 2401.64]  And is this...
[2401.64 --> 2402.14]  Oh, let's see.
[2402.20 --> 2403.02]  Is this System 3?
[2403.14 --> 2404.40]  Or is this like 7th edition?
[2404.52 --> 2405.08]  Where are we here?
[2405.08 --> 2407.84]  That would have been 81 or 82.
[2408.16 --> 2408.40]  Okay.
[2409.70 --> 2410.46]  Right in that timeframe.
[2411.12 --> 2411.84]  Like, probably 83.
[2412.02 --> 2413.10]  I think that would have been System 3.
[2413.36 --> 2413.90]  So we're still...
[2413.90 --> 2414.34]  Sorry, Jess.
[2414.50 --> 2415.10]  Jess is still...
[2415.10 --> 2416.58]  We're still five years before Jess is born.
[2416.92 --> 2421.22]  So we're still pre-Jess, but we're definitely post-me.
[2421.56 --> 2423.46]  But not on Unix.
[2423.60 --> 2424.42]  So that is amazing.
[2424.52 --> 2425.76]  That is the origin story of F-truncate.
[2426.16 --> 2428.46]  That is actually amazing.
[2428.76 --> 2429.96]  I've used that a lot.
[2430.32 --> 2430.94]  F-truncate, yeah.
[2430.94 --> 2435.56]  I can probably only lay claim to one other Unix system call.
[2436.12 --> 2440.84]  And this was for a project I did a few years later for a company called...
[2440.84 --> 2441.88]  I think it was Power Office.
[2442.16 --> 2445.10]  They were a division of ICL, which was a British computer company.
[2445.24 --> 2446.50]  International Computers Limited.
[2446.78 --> 2447.02]  Yes.
[2447.12 --> 2448.62]  And this was a group based in Virginia.
[2449.14 --> 2451.92]  And they called me out because they had a performance problem.
[2452.48 --> 2455.04]  And they said it was a virtual memory issue.
[2455.16 --> 2456.14]  The system was swapping.
[2456.34 --> 2458.10]  It was, you know, over committing memory.
[2458.10 --> 2462.88]  So I went ahead and just, you know, put a logic analyzer on it, which is how I used to debug things.
[2463.70 --> 2467.70]  And quickly determined that, no, this was not a virtual memory issue.
[2467.78 --> 2469.74]  They were simply out of CPU instructions.
[2469.96 --> 2473.08]  But why were they out of CPU instructions was the interesting part.
[2473.42 --> 2476.66]  It was simply the cost of handling every keystroke.
[2476.78 --> 2478.32]  This was an office automation system.
[2478.54 --> 2481.80]  And when the engineers developed it, they typed at one speed.
[2482.12 --> 2487.20]  But the customers were much more talented and could type three or four times faster.
[2487.20 --> 2494.80]  So a system that was sold as a 20-user system was only supporting seven users because these seven users really could type.
[2495.26 --> 2498.88]  And they could hit the 50, you know, characters, 50 words a minute.
[2499.04 --> 2502.80]  And the, you know, the engineers developing it simply could not.
[2503.02 --> 2504.12]  I mean, we were mortals.
[2504.24 --> 2505.76]  We were not able to type at those speeds.
[2506.08 --> 2511.72]  So the challenge was, well, do you optimize the trap interface or simply handle less characters?
[2511.72 --> 2519.14]  So I remember thinking about this problem and said, okay, what you really need is better line editing.
[2519.48 --> 2523.70]  Because really what all you're doing is echoing a character back 90% of the time.
[2523.74 --> 2533.02]  And then when a special character is hit that goes into the control language of the word processor or you reach the end of line, then you needed to do something a little special.
[2533.02 --> 2540.26]  But otherwise, you could have, and since they built their own terminals, you could have an intelligent terminal that could do local edit, local echo.
[2540.76 --> 2544.76]  But the only choices we had for terminal I.O. were cooked or raw.
[2545.46 --> 2547.50]  So I proposed gourmet mode.
[2548.14 --> 2557.34]  And there were a few versions of Unix that were shipped for a number of years that had gourmet mode as a TTY line discipline.
[2557.54 --> 2559.52]  As you say, this is a different line discipline.
[2559.98 --> 2562.00]  And you would indicate that I'm using gourmet mode.
[2562.00 --> 2565.18]  And you'd specify what the escape characters were.
[2565.26 --> 2569.28]  What were the characters that would cause you to move out of echo mode and back into a raw mode?
[2569.60 --> 2573.72]  And then what the condition was for going back into this local echoing mode.
[2574.20 --> 2576.64]  But gourmet mode has been lost, yes?
[2576.76 --> 2577.80]  I mean, do we still have gourmet mode?
[2577.82 --> 2579.22]  I have no idea.
[2579.36 --> 2579.56]  All right.
[2579.56 --> 2581.34]  I suspect, I hope it's been lost.
[2582.98 --> 2586.54]  Well, it doesn't necessarily benefit anyone today.
[2586.54 --> 2586.82]  Right.
[2586.82 --> 2594.84]  These are not, your ability to handle keystrokes through the trap interface is no longer a constraint.
[2594.94 --> 2600.86]  No longer a limiter on, or CPU performance is no longer the limiter based on the number of keystrokes we can handle.
[2601.08 --> 2602.04]  That is amazing.
[2602.16 --> 2604.68]  Yeah, I'd have to, because so much of that stuff did survive.
[2604.82 --> 2610.96]  And then, of course, long outlives its original intent and then can kind of come haunt us in modern times.
[2610.96 --> 2617.82]  Yeah, I think I saw it in System 5 Unix at one point, but I don't think it's made its way into Linux or modern versions.
[2617.94 --> 2627.02]  Because, truthfully, ftruncate actually caused me a very painful bug where I actually, because there are multiple ways to truncate a file in Unix,
[2627.62 --> 2630.58]  o-trunk being a common one, ftruncate being a lot less common.
[2630.88 --> 2635.28]  And I made a modification to the kernel, and I missed the ftruncate code path.
[2635.32 --> 2639.66]  And as a result, I had this really nasty bug because I had missed ftruncate.
[2639.66 --> 2642.28]  Well, I will indirectly apologize.
[2642.30 --> 2644.58]  No, no, no apology required.
[2644.64 --> 2649.52]  It was my mistake for missing it, but it's just interesting how these abstractions are added.
[2650.24 --> 2657.14]  So with Gourmet Mode, did you interact directly with the group to implement Gourmet Mode, or how did you implement it?
[2657.14 --> 2673.42]  We worked with the kernel group within ICL, and they implemented the Gourmet Mode handling in the TTY controller, and also in their terminals.
[2673.58 --> 2673.94]  In their terminals.
[2674.12 --> 2676.30]  And so does ICL have their own Unix at this point?
[2676.62 --> 2678.42]  They had their own Unix version.
[2678.58 --> 2678.78]  Okay.
[2678.78 --> 2682.12]  They had a few pretty solid engineers who were supporting kernel development.
[2682.12 --> 2686.78]  So they're taking AT&T code and running it, or modifying it effectively.
[2686.82 --> 2687.08]  Yes.
[2687.42 --> 2687.74]  Wow.
[2688.18 --> 2689.30]  Where after ICL?
[2689.34 --> 2690.90]  Yeah, was it Veritas after that?
[2691.00 --> 2693.56]  Well, ICL was just a one-month assignment.
[2693.84 --> 2694.00]  Okay.
[2694.10 --> 2697.10]  I just parachuted in because they had a product problem.
[2697.44 --> 2699.74]  Because they had just done a press release stating that they had a big problem.
[2700.26 --> 2701.84]  And that they had a solution for it.
[2701.96 --> 2706.54]  You know, one of the folks from Intel, who I'd worked with earlier, was running that group.
[2706.54 --> 2710.04]  And he had a problem, and he said, okay, this worked once before.
[2710.22 --> 2712.04]  So I got that contract.
[2712.20 --> 2712.98]  I was just contracting.
[2713.32 --> 2713.84]  That's great.
[2714.12 --> 2715.64]  And yeah, where next?
[2716.10 --> 2720.92]  I went to, well, I worked with a group called Locus Computing Corporation.
[2721.24 --> 2723.84]  So Locus was based in Santa Monica, California.
[2723.84 --> 2729.42]  It was a group that had spun out of UCLA, run by Jerry Popak, who's a professor at UCLA.
[2730.28 --> 2736.28]  The Locus is a distributed Unix, and it's a great, you can read a lot about Locus today.
[2736.28 --> 2736.66]  Really?
[2736.86 --> 2737.22]  Wow.
[2737.50 --> 2739.98]  So the team is still around.
[2740.28 --> 2745.64]  They're not as a team today, but many of the individuals who contributed to it are still around.
[2745.70 --> 2750.28]  And they have, you know, a tremendous, it was really a groundbreaking product.
[2750.58 --> 2752.70]  So this was a fully distributed Unix.
[2752.86 --> 2757.66]  It normalized and globalized all identifiers.
[2757.90 --> 2758.90]  So process identifiers.
[2759.14 --> 2764.36]  So file handles, pipes, references to memory.
[2764.36 --> 2765.96]  Actually, it's like memory segments.
[2766.28 --> 2769.52]  Across a cluster of machines.
[2769.84 --> 2772.78]  And then you can migrate processes between machines.
[2773.26 --> 2780.80]  You were able to build, you know, a distributed software that behaved the same on multiple machines as it would on a single node.
[2780.94 --> 2781.34]  When is this?
[2781.56 --> 2784.68]  This was early 80s, so 83, 84.
[2785.08 --> 2785.28]  Wow.
[2785.54 --> 2786.40]  That is cool.
[2786.66 --> 2787.88]  And it's a great project.
[2787.88 --> 2793.64]  I think you might want to dig into this with some of the Locus team.
[2793.72 --> 2794.78]  I definitely want to dig into it.
[2794.84 --> 2795.96]  I had never heard of it.
[2796.26 --> 2799.36]  Charlie Klein is living in the Bay Area.
[2799.50 --> 2802.46]  He's one of the early architects of this product.
[2802.56 --> 2803.72]  They did a phenomenal job.
[2804.04 --> 2805.04]  They sold it to IBM.
[2805.04 --> 2805.64]  Okay.
[2805.72 --> 2812.36]  And IBM did release it, but I think it was a very limited release and was really just an investigative system.
[2812.54 --> 2817.14]  I'm trying to think of the distributed Unices, and that is extremely early.
[2817.38 --> 2817.66]  It was.
[2817.66 --> 2821.56]  I mean, this was definitely a groundbreaking system.
[2821.72 --> 2822.18]  A groundbreaking system.
[2822.28 --> 2822.86]  Yeah, it must have been.
[2822.86 --> 2827.58]  And it was fascinating, and the work I did with this PC interface was done with Locus.
[2827.98 --> 2828.20]  Wow.
[2828.24 --> 2828.54]  Wow.
[2828.54 --> 2830.22]  They had the contract with AT&T.
[2830.36 --> 2833.02]  And this is over what network substrate?
[2833.24 --> 2834.38]  And this is like so early that.
[2834.42 --> 2835.12]  This was Ethernet.
[2835.28 --> 2835.94]  It is Ethernet.
[2835.94 --> 2837.72]  Yeah, Coax Ethernet.
[2837.94 --> 2838.24]  Okay.
[2839.20 --> 2841.60]  But Ethernet itself is very young at this point, right?
[2841.60 --> 2842.32]  Very young, yes.
[2842.84 --> 2843.80]  That is just amazing.
[2843.80 --> 2850.98]  That is crazy, because that's something that like people move processes from one computer to another still today, but like that in the 80s, that's cool.
[2850.98 --> 2856.02]  I remember when a new developer would join the team, they generally had never seen Ethernet before.
[2856.68 --> 2859.80]  And so I would explain, okay, here's this coax cable.
[2859.94 --> 2865.84]  We have a tap on the cable, but you always need to keep a terminator at the end of the line, because if you don't, the Ether leaks.
[2867.18 --> 2867.48]  Ether leaks.
[2867.48 --> 2871.54]  That was the joke, that this was a pressurized cable.
[2871.80 --> 2872.02]  Yeah.
[2872.40 --> 2873.16]  Yeah, exactly.
[2874.00 --> 2876.56]  So you need to keep it capped in order to keep that in the wire.
[2876.84 --> 2877.62]  That's great.
[2877.62 --> 2881.66]  And meanwhile, you've got someone who's terrified of taking the cap off, because the Ethernet is going to leak all everywhere.
[2882.16 --> 2883.22]  Yeah, Steve, don't worry.
[2883.76 --> 2884.28]  It's fine.
[2884.58 --> 2885.10]  Yeah, it's okay.
[2885.20 --> 2885.94]  I won't take the cap off.
[2886.34 --> 2887.80]  I mean, actually, please don't take the cap off.
[2888.16 --> 2891.22]  But so that's just an amazing system.
[2891.30 --> 2894.02]  Because you think, I mean, it's like, Jess, you're describing like the migration we do today.
[2894.34 --> 2898.18]  We do, but we don't share a process namespace across multiple machines.
[2898.22 --> 2900.86]  No, that's actually like super groundbreaking.
[2901.40 --> 2901.86]  It is.
[2901.86 --> 2905.52]  So why, was it commercialized?
[2905.54 --> 2906.54]  It sounds like it was commercialized.
[2906.56 --> 2909.06]  Well, it was productized by IBM.
[2909.66 --> 2917.56]  I don't know what level of commercial acceptance it had achieved, but it certainly advanced the science forward.
[2917.64 --> 2921.66]  And a lot of people were influenced by the work that Locus and IBM did there.
[2921.78 --> 2922.56]  Yeah, I can imagine.
[2922.66 --> 2924.56]  Where did those folks end up, what did they end up doing afterwards?
[2924.74 --> 2924.92]  What did they end up doing?
[2925.20 --> 2925.88]  Various things.
[2925.96 --> 2926.08]  Yeah.
[2926.54 --> 2927.52]  Really great team.
[2927.80 --> 2929.52]  And they did some great work.
[2929.52 --> 2931.56]  And again, all of this came out of UCLA.
[2931.82 --> 2932.46]  Out of UCLA.
[2932.70 --> 2933.54]  Yeah, that's just amazing.
[2933.74 --> 2938.04]  Again, I'm just going through and thinking of, I mean, Amoeba, I don't know if you'd call it.
[2938.08 --> 2941.16]  Amoeba was not a Unix-like system, but another transparently distributed system.
[2941.24 --> 2943.88]  But Amoeba wasn't it for another almost decade, right?
[2943.88 --> 2945.68]  This was Unix.
[2945.92 --> 2947.18]  Yeah, that's actually Unix.
[2947.40 --> 2951.16]  And so it was actually derived from AT&T Unix.
[2951.24 --> 2951.34]  Yeah.
[2952.32 --> 2952.64]  Wow.
[2952.86 --> 2953.54]  That is so cool.
[2953.64 --> 2955.18]  We got to get, we should get them on the podcast.
[2955.24 --> 2956.98]  Yeah, we'll take care of that.
[2956.98 --> 2957.72]  Yeah, exactly.
[2957.72 --> 2958.78]  I would love to get that.
[2958.78 --> 2964.78]  That would be really interesting and just interesting to capture what, I'm sure they
[2964.78 --> 2966.28]  must have pioneered a bunch of abstractions.
[2966.36 --> 2966.46]  Yeah.
[2966.46 --> 2968.38]  Yeah, that is, that's wild.
[2968.92 --> 2973.80]  So you had an early view of what a distributed system could go do at a time when people were
[2973.80 --> 2974.80]  probably not really appreciating it.
[2975.14 --> 2976.40]  I think that was the issue.
[2976.48 --> 2980.74]  I don't think that it was necessarily solving a problem people had at that point.
[2980.88 --> 2986.76]  Unix had far more substantive limitations that were keeping it out of commercial computing.
[2986.76 --> 2994.06]  And in the early 80s, Unix was starting to achieve success in desktop engineering workstations
[2994.06 --> 2995.26]  and in scientific computing.
[2995.44 --> 3002.22]  But it really wasn't until 1990 that we started to see widespread commercial adoption for enterprise
[3002.22 --> 3008.82]  computing, replacing the IBM HP and DEC mid-range OSs.
[3008.82 --> 3009.82]  Right.
[3009.82 --> 3009.86]  Yeah.
[3010.18 --> 3013.98]  I mean, I'm just thinking about all the ways in which I know Unix was immature in the early
[3013.98 --> 3014.26]  80s.
[3014.32 --> 3017.04]  And to make that thing distributed, it's just, that's amazing.
[3017.46 --> 3019.94]  So where does this find you then in the 80s?
[3020.02 --> 3020.66]  I mean, what's...
[3020.66 --> 3024.76]  Well, interestingly, I moved to the Netherlands and had some fun.
[3025.10 --> 3030.98]  Well, after we licensed PC interface to Sun for NFS, I sort of could look forward a bit
[3030.98 --> 3033.30]  and saw a revenue stream for a number of years.
[3033.52 --> 3038.10]  I took a royalty on that product and said, you know, if there's a time in your life to
[3038.10 --> 3039.60]  do some traveling, this might be it.
[3039.96 --> 3043.78]  I've worked with Philips Data Systems in Holland.
[3044.20 --> 3045.92]  That's actually where I met my wife, Marika.
[3046.18 --> 3046.56]  Oh, wow.
[3046.56 --> 3048.52]  And so we've moved back together.
[3048.68 --> 3054.04]  But when returned to the US, it was to restart a company that I had helped start before I
[3054.04 --> 3054.62]  left the country.
[3055.10 --> 3057.94]  And this was a firm that was originally called Tolerant Systems.
[3058.56 --> 3061.62]  And Tolerant was to be a fault-tolerant computer company.
[3062.54 --> 3067.66]  Their tandem had made a name for itself and was achieving commercial success.
[3067.66 --> 3072.38]  And the feeling was, is that if you could do this at a lower cost, there'd be a market
[3072.38 --> 3075.78]  for a highly available lower cost computer.
[3075.78 --> 3081.30]  And the notion was to build shoebox machines that you would put multiples of them on a
[3081.30 --> 3081.68]  network.
[3081.90 --> 3083.80]  And then you did some replication between them.
[3083.84 --> 3089.08]  And you could ensure for environments that needed lower performance, but higher availability,
[3089.28 --> 3091.20]  this could be like process control systems.
[3091.20 --> 3092.64]  This could be an interesting solution.
[3093.04 --> 3096.56]  For a variety of reasons, I actually decided to move to Europe at that point.
[3096.74 --> 3102.54]  I enjoy the fact that I knew I could be supported for a few years, be irresponsible for at least
[3102.54 --> 3103.22]  once in my life.
[3103.76 --> 3108.52]  And the company evolved in a little bit different direction.
[3109.70 --> 3115.60]  It's hard for people not to compete against others who are in the similar space.
[3115.74 --> 3118.42]  And the dimension that we frequently compete on is performance.
[3118.42 --> 3121.10]  So it got bigger and it got bigger.
[3121.10 --> 3125.56]  And eventually was a multi-hundred thousand dollar per node computer system.
[3126.14 --> 3131.24]  About the time people started to discover that fault tolerant computing really wasn't a sector.
[3131.78 --> 3136.88]  People weren't buying these machines because they needed to have true nonstop capability.
[3136.88 --> 3143.06]  What they needed was better availability and data integrity than a typical Unix system could
[3143.06 --> 3143.36]  offer.
[3143.68 --> 3149.40]  When I'm moving back to the US, I was speaking with co-founders of the company, those who I'd
[3149.40 --> 3150.94]  started the company with years earlier.
[3151.58 --> 3156.84]  And they, you know, were thinking that what they really needed was a software company that
[3156.84 --> 3163.90]  could provide higher availability and a better file system and data integrity than the Unix
[3163.90 --> 3166.26]  platform was capable of delivering in 1988.
[3166.66 --> 3168.72]  And this became Veritas Software.
[3169.38 --> 3174.08]  So we first created a company called Tolerant Software that was going to be fully owned by
[3174.08 --> 3174.78]  Tolerant Systems.
[3174.78 --> 3179.12]  And about a month later, Tolerant Systems came crashing down around us.
[3179.34 --> 3182.44]  So we, you know, we took over the company effectively.
[3182.66 --> 3186.80]  And we were a five-person software company and then started to build that up.
[3186.88 --> 3191.92]  But we didn't actually use a single line of code from the Tolerant Systems product.
[3192.06 --> 3197.02]  What we needed was something that was a very heavily customized version of Unix.
[3197.18 --> 3201.36]  This, we really did need to build something that used well-defined existing interfaces.
[3201.36 --> 3207.18]  So the System 5 VFS interface for the file system, the block and character device interface
[3207.18 --> 3212.30]  for the logical volume manager, and to be able to deliver these in a format that the Unix
[3212.30 --> 3215.68]  system OEMs were capable of receiving it.
[3216.34 --> 3219.60]  And that was the genesis of Veritas Software.
[3220.34 --> 3220.60]  Wow.
[3220.92 --> 3221.60]  Of Veritas Software.
[3221.72 --> 3222.30]  Wow.
[3222.70 --> 3223.10]  That's so cool.
[3223.22 --> 3226.98]  That it came out of this other kind of failed effort.
[3227.56 --> 3228.32]  That's interesting.
[3228.58 --> 3230.12]  And was Tolerant making hardware?
[3230.12 --> 3231.06]  They were just making software.
[3231.14 --> 3232.42]  Tolerant was a hardware company.
[3232.52 --> 3232.68]  Okay.
[3232.68 --> 3236.88]  Now, when we created, we were Tolerant Software for probably about six, seven months.
[3237.06 --> 3237.30]  Okay.
[3237.48 --> 3242.28]  And we brought in a new CEO who had been on the board of Tolerant Systems.
[3242.72 --> 3244.74]  And we decided he needed a full-time job.
[3244.76 --> 3245.58]  And that was Mark Leslie.
[3246.02 --> 3246.62]  Oh, wow.
[3246.72 --> 3248.78]  Mark was a transformative CEO for us.
[3248.84 --> 3253.06]  And the first day on the job, he says, you know, guys, Tolerant has a bad name.
[3253.42 --> 3254.80]  You can't be Tolerant anymore.
[3254.80 --> 3255.50]  We're intolerant.
[3255.76 --> 3256.72]  We're going to be intolerant.
[3256.72 --> 3257.54]  We're going to be intolerant.
[3257.72 --> 3258.14]  There you go.
[3258.14 --> 3260.96]  So, we held a contest to come up with a new name.
[3261.10 --> 3264.14]  We all picked a name out of the hat.
[3264.58 --> 3267.44]  And oddly, the one Mark had suggested one.
[3267.74 --> 3269.10]  Oh, look at this.
[3269.12 --> 3270.06]  It's the name that I put in the hat.
[3270.06 --> 3270.40]  Exactly.
[3271.68 --> 3272.58]  It's a good name.
[3272.60 --> 3273.40]  It was a great name.
[3273.48 --> 3275.12]  I mean, it really is a good name.
[3275.12 --> 3277.64]  And so, we became Veritas Software.
[3277.88 --> 3281.94]  And, of course, it really did reflect on, you know, that we were trying to provide a state of truth.
[3282.98 --> 3285.38]  And we built a logical volume manager.
[3285.64 --> 3286.54]  It supported replication.
[3286.94 --> 3289.28]  And it even eventually supported software RAID 5.
[3289.62 --> 3293.94]  But more importantly, it allowed you to grow and shrink a volume dynamically.
[3293.94 --> 3302.78]  And our file system, the Veritas file system, didn't require a structural FSCK on system restart.
[3303.30 --> 3305.68]  So, you have to think back to 1989.
[3306.00 --> 3306.84]  Discs are getting bigger.
[3307.26 --> 3310.98]  So, they're no longer 5 megabyte hard drives.
[3311.06 --> 3314.66]  We're now dealing with 50 and 100 megabyte hard drives.
[3314.66 --> 3322.40]  The structural FSCK that used to take 35 minutes was sometimes taking 12 hours to complete.
[3322.90 --> 3326.40]  So, imagine you deployed a Unix system in a mission-critical environment.
[3326.62 --> 3328.78]  Let's say the paint shop at an auto factory.
[3329.30 --> 3331.40]  And that system has a glitch.
[3331.58 --> 3332.20]  It crashes.
[3332.70 --> 3333.82]  It happens sometimes.
[3334.36 --> 3337.80]  But the recovery from that crash could take you half a day.
[3338.50 --> 3340.06]  Well, clearly, it's a non-starter.
[3340.06 --> 3344.38]  You never would have deployed the Unix system in that environment because it didn't meet the availability.
[3344.66 --> 3345.66]  It's a non-starter.
[3345.66 --> 3346.66]  It's a non-starter.
[3347.06 --> 3352.96]  Or imagine you had a system which ran out of space in one of its file systems.
[3353.38 --> 3355.02]  And now you need to add additional space.
[3355.12 --> 3357.42]  Well, how would you do that in 1989?
[3357.84 --> 3358.88]  And the answer was pretty simple.
[3359.12 --> 3360.52]  You back everything up to tape.
[3361.06 --> 3363.40]  You repartition your disks.
[3363.58 --> 3366.18]  You create a new file system.
[3366.30 --> 3367.92]  And then you recover from your backup.
[3368.32 --> 3371.64]  Because the backup and restore process is error-prone.
[3371.64 --> 3379.84]  And you potentially are putting your data at risk simply to change the capacity and rebalance capacity between file systems.
[3379.98 --> 3381.66]  So, this was a non-starter.
[3381.82 --> 3385.66]  It was the reason why Unix had not achieved its potential in the commercial market.
[3386.34 --> 3396.96]  And as a company, Veritas was there to enable OEMs to be able to deliver their systems into environments that required high data integrity and high availability.
[3396.96 --> 3402.92]  So, with VXFS, we used an intent log for all metadata changes to the file system.
[3403.54 --> 3411.36]  And on system recovery, we reapplied the intents and recovered to a clean state without having to do a structural scan of the file system.
[3411.36 --> 3414.62]  So, is this the origin of what's commonly known as RAID now?
[3415.26 --> 3419.90]  This isn't RAID, but this is the first real commercial implementation of a log-structured file system.
[3419.90 --> 3422.22]  Well, it wasn't a log-structured file system.
[3422.32 --> 3425.02]  No, in fact, it was an extent-mapped file system.
[3425.20 --> 3430.48]  But the metadata, the file system control information, was logged.
[3430.88 --> 3433.92]  So, the log didn't include actual changes to file contents.
[3434.02 --> 3434.64]  It is only metadata.
[3434.68 --> 3435.70]  It was strictly metadata.
[3435.90 --> 3439.34]  But it obviated the need for the structural FSCK.
[3439.62 --> 3442.18]  You could recover in seconds as opposed to hours.
[3442.40 --> 3442.62]  Right.
[3442.62 --> 3448.62]  And I had seen large systems that took two days to recover from a power failure.
[3449.58 --> 3459.04]  There were a lot of attempts that others had made to solve these problems by, let's say, having a clean bit that they would periodically set in the file system.
[3459.10 --> 3464.26]  And then if the system crashed while the bit was still set clean, you could avoid the FSCK.
[3465.26 --> 3466.32]  The problem is that a bit—
[3466.32 --> 3466.70]  It's never set.
[3466.78 --> 3467.40]  It's never set.
[3467.46 --> 3468.02]  Right, exactly.
[3468.02 --> 3471.04]  There's always iOS outstanding.
[3471.22 --> 3473.64]  So, in fact, you were still doing your structural FSCK.
[3474.06 --> 3479.68]  So, this was VXFS, the file system, and VXVN, the logical volume manager.
[3480.18 --> 3487.00]  The logical volume manager did implement RAID, but most customers used it to be able to migrate and move storage.
[3487.00 --> 3496.78]  If you had a disk that was showing errors, you could take the used slices on that disk and simply drag them to other disks where there was free space.
[3496.78 --> 3498.44]  The storage would migrate.
[3498.66 --> 3500.44]  You would be notified when the disk was empty.
[3500.52 --> 3501.56]  You were free to replace it.
[3502.38 --> 3506.10]  Previously, those had been major disruptions on system availability.
[3506.88 --> 3515.44]  And that's actually still a challenge for us today is actually being able to remove a device that's in either a RAID site or a ZVA or what have you is a challenge.
[3516.28 --> 3519.00]  So, and this is—RAID at this time is still mainly hardware.
[3519.24 --> 3521.46]  This is all—you guys were doing software RAID effectively.
[3521.66 --> 3524.62]  Well, there really wasn't much hardware doing RAID either at that point.
[3524.62 --> 3524.96]  Oh, really?
[3525.04 --> 3525.32]  Interesting.
[3525.32 --> 3525.60]  Okay.
[3525.86 --> 3527.70]  So this is—so, because RAID is what?
[3527.78 --> 3531.20]  I mean, that's David Patterson in the mid-'80s, right?
[3531.26 --> 3531.88]  Early-'80s.
[3532.12 --> 3532.36]  Yes.
[3532.44 --> 3544.80]  And a fellow at CMU, and blanking on his name now, that's terrible, but he had—Garth—I'll think of it in a moment—but he had written a sort of a groundbreaking paper on RAID as well.
[3544.80 --> 3551.18]  But the use of the Veritas volume manager was largely storage migration.
[3551.18 --> 3553.46]  And effectively, it's virtual memory for disk.
[3553.46 --> 3557.46]  And it offers you the same basic advantage that virtual memory did on RAM.
[3557.86 --> 3565.16]  You no longer are dealing with physical extents, but they're logical extents, which then you map on to physical extents.
[3565.16 --> 3573.02]  And you're free to change the physical locations of those logical extents without impacting availability of the applications.
[3573.02 --> 3579.38]  All right, we're going to take another quick break, and we'll be right back with Jeff Rothschild.
[3579.38 --> 3594.70]  On the Metal is brought to you by the Oxide Computer Company, where we're going to try a new feature, shamelessly ripped off of Reply All's Yes, Yes, No, where our boss, Steve Tuck, brings us a tweet he does not understand, and Jess and I try to explain it to him.
[3594.72 --> 3595.44]  Steve, do you have a tweet?
[3596.06 --> 3596.80]  I sure do.
[3596.92 --> 3597.34]  Go for it.
[3597.34 --> 3598.78]  The tweet in question,
[3598.78 --> 3615.30]  No idea.
[3615.56 --> 3616.16]  No idea.
[3616.28 --> 3617.14]  Jess, do you understand this tweet?
[3617.66 --> 3622.58]  So I understand definitely the part about the UEFI preboot networking stack.
[3622.92 --> 3625.70]  But the part about DMA is in question marks.
[3625.70 --> 3629.36]  So it's like, I guess you're not really sure where that's going.
[3629.38 --> 3630.26]  You're overthinking it.
[3630.38 --> 3631.34]  I understand this tweet.
[3631.64 --> 3633.54]  Running on-prem is painful.
[3633.66 --> 3636.46]  This is dealing with an awful, awful firmware bug.
[3636.60 --> 3642.16]  Firmware has overwritten part of the operating system in a way that is extremely painful to debug.
[3642.44 --> 3643.56]  So who do you go to in that case?
[3643.64 --> 3644.52]  Who do you go to?
[3644.62 --> 3646.62]  You definitely strangle one of your vendors.
[3647.04 --> 3647.92]  You strangle one of your vendors.
[3647.92 --> 3655.10]  Unfortunately, your vendor is a PC vendor because all of the existing computer companies are selling personal computers.
[3655.10 --> 3657.48]  What we need is a new computer company.
[3657.62 --> 3661.60]  So this is just saying I'm in intense pain trying to run systems on-premises.
[3661.76 --> 3662.94]  That's exactly what it's saying.
[3663.02 --> 3665.40]  Steve, what can someone do if they're in intense pain running on-premises?
[3665.66 --> 3673.84]  Well, if someone is running in intense pain on-premises, what they should do is go over to oxide.computer to learn a little bit more about how we are going to take that pain away.
[3674.02 --> 3675.72]  Help is on the way.
[3676.00 --> 3677.44]  Join us at oxide.computer.
[3677.60 --> 3678.74]  You are not alone.
[3678.74 --> 3684.48]  All right.
[3684.60 --> 3685.04]  We are.
[3685.20 --> 3689.98]  We're back on the metal with terrific tales from the hardware-software interface.
[3690.22 --> 3693.04]  I feel like this could go on for days.
[3693.22 --> 3693.56]  This is good.
[3693.76 --> 3694.50]  I hope not.
[3694.88 --> 3697.70]  I think you're holding us just mesmerized.
[3697.70 --> 3704.00]  So, I mean, Veritas, we were talking about Veritas, total groundbreaking technology.
[3705.02 --> 3709.26]  And, I mean, really, truly years ahead of its time.
[3709.36 --> 3712.16]  It would take a long time for any of the other folks to really catch up to Veritas.
[3712.20 --> 3720.86]  It was pretty much the end of the decade before you started to see other logical volume managers and file systems that preserve structural integrity coming into the market.
[3720.86 --> 3727.54]  Yeah, and I can tell you being on the inside of one of those companies, it's Sun, where Sun loved Veritas until-
[3727.54 --> 3728.30]  And hated Veritas.
[3728.32 --> 3729.44]  And hated Veritas.
[3729.64 --> 3733.40]  And it's, you know, the frenemy relationship, not that uncommon, right?
[3733.56 --> 3734.38]  It absolutely was.
[3734.70 --> 3740.08]  And as the years went by, really wanted to like, okay, we can, we do our own.
[3740.30 --> 3744.70]  And boy, there were a bunch of attempts at it and they were, they were not good.
[3744.70 --> 3751.70]  And you saw, I think people really appreciated how much had been done and how hard it was to actually get all the stuff correct.
[3752.38 --> 3755.20]  And so, the, how long are you at Veritas?
[3755.34 --> 3755.70]  When do you?
[3755.98 --> 3760.46]  We started the software company in the end of 88, beginning of 89.
[3760.92 --> 3763.72]  I left in 90, end of 94.
[3764.16 --> 3767.54]  So, after, about a year after the IPO or back, just after the IPO.
[3767.54 --> 3773.00]  And I left largely because the internet was happening.
[3773.54 --> 3778.28]  And I was really excited about what you could do that might be a lot of fun.
[3778.62 --> 3785.14]  I will admit that I, I, I, I, there was a point where I didn't want to talk to people about device drivers anymore.
[3786.42 --> 3789.40]  I do, I used to do a bit of sales at Veritas.
[3789.40 --> 3790.86]  So, I wore many hats.
[3790.98 --> 3792.70]  I did some prototype engineering.
[3792.98 --> 3795.62]  I did some, a little engineering management.
[3795.82 --> 3796.94]  I would do product management.
[3796.94 --> 3800.18]  And I would also grab a bag and go on the road.
[3800.74 --> 3805.40]  And one day I was sitting in a meeting and I think it was my fourth meeting that day,
[3805.48 --> 3812.30]  talking about the BDEV switch, CDEV switch, and, you know, how the, you know, how IOs were scheduled or something to that effect.
[3812.38 --> 3815.00]  And I just said to myself, tomorrow I'm doing something different.
[3815.54 --> 3818.48]  I left in order to start something that would be fun.
[3818.54 --> 3822.98]  And the fun thing I thought about was online multiplayer games.
[3822.98 --> 3830.24]  And so, started a company to do online multiplayer gaming because it seemed like the most fun thing you could do with the internet.
[3830.94 --> 3831.98]  In 1994?
[3832.32 --> 3833.80]  Well, 1995 at that point.
[3833.80 --> 3834.00]  Okay.
[3834.10 --> 3834.32]  Yes.
[3834.40 --> 3834.68]  Wow.
[3834.82 --> 3835.28]  That's early.
[3835.94 --> 3836.46]  That's early.
[3836.56 --> 3837.42]  Well, it was early.
[3837.52 --> 3841.32]  And that actually, you could put that on the, as the epithet of the company.
[3841.68 --> 3842.58]  It was early.
[3842.58 --> 3844.00]  We were too early.
[3844.24 --> 3849.56]  We were doing this with, people had 1440 baud, you know, dial-up modems.
[3849.70 --> 3849.82]  Yep.
[3850.06 --> 3852.06]  The latencies were very high.
[3852.14 --> 3855.62]  And we put a lot of energy into dealing with latency.
[3855.94 --> 3866.06]  We had matchmakers that would very carefully look at the latency of individual players and group people into game sessions based on their proximity and space to each other.
[3866.06 --> 3870.18]  That is, in network space, not physical space, though there's a relationship.
[3870.92 --> 3878.62]  And we worked with some early internet service providers and co-locating equipment, which was an interesting exercise.
[3878.62 --> 3890.18]  Because the first time we approached an internet service provider about co-locating our game servers in their network, the head of operations for this company said,
[3890.48 --> 3894.60]  over my dead body, will any customer ever put a machine in my data center?
[3894.60 --> 3895.08]  Wow.
[3895.08 --> 3898.38]  And of course, in five years, that was their business.
[3898.80 --> 3898.94]  Right.
[3899.34 --> 3901.36]  But it was an interesting response.
[3901.60 --> 3907.94]  And we finally found one provider who, when we asked the question, said, you know, I don't know why you want to do this.
[3908.10 --> 3914.86]  But I've sort of taught myself that if somebody asks me for something, you know, listen, and we'll work with you.
[3914.88 --> 3916.00]  And that was PSINET.
[3916.56 --> 3921.04]  And so PSINET worked with us to create optimized traffic.
[3921.04 --> 3924.02]  So we were able to prioritize the game traffic on their network.
[3924.02 --> 3931.66]  And we located game servers throughout their network, geographically dispersed, in order to manage for latency.
[3931.84 --> 3933.36]  Because latency mattered.
[3933.82 --> 3933.92]  Right.
[3934.00 --> 3941.30]  We also did a lot of work in the client to game server link that would be irrelevant today.
[3941.44 --> 3947.04]  We were squeezing, you know, two, three bytes at a time out of the game protocol.
[3947.04 --> 3948.94]  And today that would be irrelevant.
[3949.14 --> 3954.14]  We were working with the game developers on algorithms they could employ to hide latency.
[3954.62 --> 3959.54]  So when you have, when you fire a weapon, make sure there's a big explosion and a lot of smoke.
[3959.54 --> 3963.68]  Because that gives you time to resolve state between all the clients.
[3963.68 --> 3967.74]  So that when the smoke clears, everybody sees the same player is dead.
[3968.18 --> 3977.34]  You know, when, and again, in a first person shooter game, you would be sure that if you, if you were shot one or you shot someone, one hit wasn't a kill.
[3977.34 --> 3985.38]  Because a single hit was required precision in how you adjudicate and distribute state.
[3985.50 --> 3989.72]  But if it takes multiple hits, then there's time to figure it out.
[3989.86 --> 3997.20]  And the lack of precision in the network and in your protocol was hidden by a lack of precision in the game experience itself.
[3997.26 --> 3997.96]  That's great.
[3997.96 --> 4002.28]  And so we worked with the developers on, on helping them build multiplayer gaming.
[4002.40 --> 4013.70]  We actually had one of our fellows spent a month at, in Mesquite, Texas with id Software, converting Quake from IPX, SPX to, to IP.
[4014.00 --> 4017.70]  So it was originally written for the Novell network protocol.
[4017.94 --> 4018.76]  LAN protocol.
[4018.76 --> 4023.58]  And, and so we converted that to be the internet capable game.
[4023.72 --> 4024.72]  And so you could play Quake over the internet.
[4024.72 --> 4030.88]  The first version of Quake had a, had an M player splash screen on it, giving us credit for, for that work.
[4031.30 --> 4031.66]  Wow.
[4032.46 --> 4035.78]  And, but it was, you said the company itself was, this was too early?
[4035.80 --> 4036.48]  We were too early.
[4036.64 --> 4036.78]  Yeah.
[4036.78 --> 4037.58]  We were too early.
[4037.74 --> 4043.76]  And, and so eventually it sort of divided up and, and assets were sold to different companies.
[4043.86 --> 4045.58]  It did go public, but that was 1999.
[4045.76 --> 4050.40]  And, you know, just like there was an era in baseball where everybody's record has an asterisk on it.
[4050.40 --> 4054.66]  I think, I think a lot of companies should have asterisks on their eyes.
[4054.72 --> 4055.56]  It was 1999.
[4055.66 --> 4056.38]  I've been 1999.
[4057.32 --> 4057.76]  Exactly.
[4058.14 --> 4058.34]  Yeah.
[4058.42 --> 4063.40]  The 99 IPOs, I don't think deserve the same credit as before and after.
[4063.68 --> 4064.84]  It was a very different era.
[4064.96 --> 4065.68]  That's for sure.
[4066.32 --> 4069.28]  So, and then, so what was next for you after that?
[4069.48 --> 4072.86]  I did a few projects just as a consultant to the projects.
[4072.86 --> 4084.50]  I helped with Walmart.com and a company which did a storage controller that was eventually purchased by Brocade called Rhapsody Networks.
[4086.08 --> 4088.86]  So the storage controller, so you're backing the device driver.
[4089.08 --> 4089.22]  Oh, of course.
[4090.96 --> 4091.98]  Can't stay away.
[4092.12 --> 4097.80]  I should have erased all that from my resume so people would forget, but it kept coming back to haunt me.
[4097.96 --> 4099.76]  So I couldn't get out of that industry.
[4099.76 --> 4115.44]  Great. Let's see, early 1995, or 2005, rather, I got a call from folks at Excel Partners asking if I could help out with a couple of companies they'd invested in, a few guys from Harvard who'd started a social network.
[4115.52 --> 4117.22]  And my first response is, social network?
[4117.62 --> 4118.82]  Have you ever looked at Friendster?
[4120.00 --> 4121.66]  And they said, no, no, this is different.
[4121.74 --> 4122.84]  It has nothing to do with that.
[4122.84 --> 4128.88]  And so I figured I'd hang out in their office for a few weeks and help out with recruiting.
[4128.88 --> 4131.56]  And I spent 10 years there.
[4132.06 --> 4132.54]  That's cool.
[4132.98 --> 4136.50]  And so what was your kind of first impression walking into Facebook?
[4137.60 --> 4138.38]  Small team.
[4138.66 --> 4139.78]  I love small teams.
[4139.92 --> 4147.72]  I love people doing things from the seat of the pants and, you know, not having a lot of process, not having a lot of rules.
[4147.98 --> 4149.22]  And there were no rules.
[4149.38 --> 4151.36]  I mean, this was a development team.
[4151.74 --> 4153.46]  You know, we're sitting around a small table today.
[4153.54 --> 4155.04]  Well, that was pretty much the environment.
[4155.04 --> 4159.92]  If somebody was going to edit a file, they'd say, okay, I'm in home.php.
[4159.98 --> 4162.76]  And nobody would touch it until they said they closed it.
[4163.04 --> 4165.56]  So no source code control, no auditing.
[4165.82 --> 4167.14]  But that's small teams.
[4167.28 --> 4169.58]  I mean, I've done the same thing, you know, 100 times.
[4169.62 --> 4171.64]  You start the project with one, two developers.
[4172.06 --> 4179.50]  And then you sort of have to introduce layers of process and eventually release management and testing and frameworks and the rest.
[4179.50 --> 4184.96]  But early days, you have a blank slate to start with.
[4185.02 --> 4185.76]  But it was a lot of fun.
[4185.84 --> 4190.36]  I mean, what impressed me about Facebook is I really wasn't intending to work there.
[4190.76 --> 4195.80]  I was really going to help recruit a VP of engineering and someone to run operations.
[4196.14 --> 4198.24]  And I was bringing a few people in.
[4198.42 --> 4200.56]  The chemistry just wasn't clicking.
[4200.56 --> 4204.96]  They were great folks who've really gone on to do fantastic things.
[4205.44 --> 4214.56]  But I couldn't sit in the office and watch people work and then not say, you know, let me show you a different way to do that.
[4215.10 --> 4218.86]  And so I would sort of dive in on a few of the engineering issues.
[4219.14 --> 4223.04]  And at the same time, I was looking at the inbox.
[4223.42 --> 4225.74]  I wanted to understand what are the problems this site has?
[4225.80 --> 4228.10]  What type of issues are the users running into?
[4228.10 --> 4230.58]  So I read the unread mailbox.
[4230.84 --> 4237.62]  And there were 75,000 unread messages because the person who was assigned to read that only worked weekends.
[4238.20 --> 4243.34]  She was a student and, you know, worked weekends and read some messages and responded to them.
[4243.38 --> 4246.06]  And, of course, the rate of arrival was much greater than that.
[4246.46 --> 4248.72]  You know, she would ever be able to meet.
[4249.42 --> 4251.96]  And people were writing love letters.
[4252.56 --> 4254.00]  They were writing poems.
[4254.00 --> 4258.28]  People were saying, I showed up at school and I was so afraid I wouldn't know anyone.
[4258.46 --> 4265.00]  And using your site, I've met so many people and I feel like they're all my best friends now.
[4265.10 --> 4265.62]  Isn't that amazing?
[4265.68 --> 4266.30]  That's so nice.
[4266.38 --> 4267.98]  It's a different era of social networking.
[4267.98 --> 4273.98]  And then somebody would write a note saying, well, you know, I showed up at college and I was so sad at missing my friends from high school.
[4274.00 --> 4275.28]  But I now know what they're doing.
[4275.40 --> 4277.16]  And they post things on a daily basis.
[4277.16 --> 4279.30]  And I understand what they're up to.
[4279.44 --> 4280.74]  And I feel so close.
[4280.84 --> 4282.38]  I still feel so close to them.
[4282.52 --> 4283.10]  That's so good.
[4283.22 --> 4283.96]  And I read this.
[4284.16 --> 4287.58]  And I thought about it and said, you know, Veritas is sort of a big company.
[4287.76 --> 4293.26]  I mean, 6,000 employees, like $1.5 billion in revenue, thousands of customers.
[4293.46 --> 4299.04]  But I never saw a love letter from a system administrator saying, your volume manager made me happy.
[4299.24 --> 4299.56]  Right.
[4299.72 --> 4302.38]  I used to be afraid of losing my data until I met you.
[4302.44 --> 4304.80]  I've never seen FS Check run so quickly.
[4304.80 --> 4315.88]  And I thought about it a little more and said, well, you know, companies spend hundreds of millions of dollars a year trying to convince people that their products make them happier.
[4316.30 --> 4318.44]  And here is a company that spent nothing.
[4318.92 --> 4323.84]  That simply built a product and their users are saying, I use you because it makes me happier.
[4323.92 --> 4326.02]  I thought about Coca-Cola and Pepsi.
[4326.28 --> 4327.92]  I mean, look at their ad campaigns.
[4327.92 --> 4335.04]  It's all about how their flavored water is going to, their sugar water is going to make you, your life better.
[4335.42 --> 4341.96]  And here was a product where people were saying, you know, in concrete terms, their life is better because they're more connected to their friends.
[4342.06 --> 4344.56]  And the truth is, that is what matters.
[4344.72 --> 4350.26]  I mean, you know, what really matters in your life, it's the connection you have with people.
[4350.26 --> 4352.46]  It's not the number of friends you have.
[4352.56 --> 4353.98]  It's how close you are to them.
[4354.08 --> 4360.14]  If you have a friend and you never talk to them, then they're not adding to your life, you're not adding to theirs.
[4360.22 --> 4364.30]  And what Facebook was doing was increasing that information flow between people.
[4364.68 --> 4371.72]  And that enhanced those relationships and in turn created happiness for folks.
[4371.82 --> 4373.38]  And I wanted to be part of that.
[4373.54 --> 4374.02]  That's great.
[4374.18 --> 4375.06]  Yeah, that's huge.
[4375.22 --> 4378.94]  So obviously the power in that, and that's in 2005.
[4378.94 --> 4379.96]  That's 2005.
[4380.60 --> 4384.24]  And so at that point, because I first met you in 2007.
[4385.00 --> 4391.06]  And when you were pretty well, I mean, you were pretty well entrenched in Facebook.
[4391.20 --> 4394.20]  You guys were, at that point, Facebook was really catching on.
[4394.38 --> 4400.90]  Lots of people were, it didn't feel, it felt like it was exploding in all the right ways.
[4400.98 --> 4401.36]  It was.
[4401.76 --> 4408.56]  And of course, I remember you very, meeting you very viscerally because I was talking to you when my wife was about to have our second kid.
[4408.94 --> 4412.58]  And I was going to come down and meet you, I think the day before she was due.
[4413.20 --> 4416.98]  And you gave me a warning based on your, was it second kid or third kid?
[4417.36 --> 4419.20]  Our second was born very quickly.
[4419.42 --> 4419.70]  Yes.
[4419.88 --> 4420.84]  We showed up.
[4421.54 --> 4424.84]  My wife woke me up at, I think, 6.30.
[4425.40 --> 4428.36]  And we were on the way to the hospital at 6.45.
[4428.36 --> 4429.54]  We got there at 7.
[4429.54 --> 4431.70]  And we were really ready to go home at a quarter of 8.
[4432.64 --> 4435.86]  Which, I mean, that is, you know, Steve, you've got three kids.
[4435.94 --> 4437.02]  I mean, that is, that's.
[4437.02 --> 4437.58]  That's record time.
[4437.60 --> 4439.60]  That is terrifyingly fast.
[4439.70 --> 4444.90]  So I, I was definitely like, wow, I know this is, this is on the metal, not on the pregnancy.
[4444.90 --> 4448.52]  But wow, that was, that was a scary, that woke me up.
[4448.58 --> 4450.64]  I think I, I postponed the meeting, I think.
[4450.64 --> 4453.08]  Because I think you were telling me that, you know, the due date's tomorrow.
[4453.44 --> 4454.98]  Oh, I was very blasé about it.
[4455.00 --> 4455.20]  Yeah.
[4455.30 --> 4457.24]  And you were, you know, two hours away.
[4457.26 --> 4458.54]  Oh, I had plenty of time.
[4458.70 --> 4460.66]  And you're like, well, let me, hold on, youngster.
[4461.26 --> 4462.82]  Let me slow your roll a little.
[4463.30 --> 4466.24]  Yeah, no, it definitely, but it was a lot of fun to get down there with you and the,
[4466.32 --> 4469.76]  and so then how long were you, I mean, at Facebook, you quickly got to some of the
[4469.76 --> 4473.78]  same deep technical problems that you, I mean, back in the device drivers, but you,
[4473.84 --> 4475.04]  you got back to the metal.
[4475.04 --> 4475.98]  Of course we did.
[4476.26 --> 4482.40]  In fact, one of the first really interesting problems that we dealt with was our use of memcache.
[4482.40 --> 4487.04]  And for those of you who don't know, memcache is a distributed hash table.
[4487.82 --> 4492.88]  And it has an operation called a multiget, where with a multiget, you take a collection
[4492.88 --> 4497.62]  of keys and the driver then will, understanding the hash function, will sort those keys across
[4497.62 --> 4502.50]  a collection of servers and then make a request to the servers in the pool to respond with
[4502.50 --> 4504.40]  the corresponding data values.
[4505.30 --> 4507.94]  Well, we worked really hard on the memcache code.
[4507.94 --> 4509.54]  We had to improve its scalability.
[4509.54 --> 4511.14]  We had to improve its performance.
[4512.10 --> 4514.72]  We made it multi-threaded.
[4515.46 --> 4518.40]  And in doing all of this work, we actually made it faster.
[4518.84 --> 4524.54]  So we reduced the total instruction path of memcache down to a minimum, which meant that
[4524.54 --> 4526.56]  its variability was less as well.
[4526.66 --> 4531.12]  That is, a request to request variability was less because the total time required for
[4531.12 --> 4532.50]  a request was less.
[4532.50 --> 4538.86]  What this meant was if you made a request to a memcache pool, let's say a pool of 200 machines,
[4539.74 --> 4545.00]  and you were doing a large multiget that had maybe 1,000 keys, you're probably hitting most
[4545.00 --> 4546.24]  of those 200 machines.
[4546.56 --> 4552.82]  So inside of microseconds, you would have 200 machines firing back their responses to your
[4552.82 --> 4554.90]  client, which is in fact a web server.
[4554.90 --> 4560.04]  So your client is making this request, it gets all the responses back, and they all meet
[4560.04 --> 4564.70]  for the first time at the top of rack switch on top of your web server.
[4565.14 --> 4567.54]  And of course, the next step is buffer overflow.
[4567.96 --> 4571.06]  So you drop some packets, and then you make the next request.
[4571.22 --> 4573.12]  And you're using TCP.
[4573.46 --> 4580.24]  So TCP has variable retries, and the retries keep getting longer.
[4580.24 --> 4586.06]  And soon these requests are taking milliseconds to perform because of the retry logic, because
[4586.06 --> 4590.00]  even on the second round, you started getting buffer overflow as well.
[4590.16 --> 4592.00]  So this was a very challenging problem.
[4592.10 --> 4594.22]  It took a long time to really understand.
[4594.62 --> 4600.48]  And after that, a fellow named Mark Kwiatkowski implemented just a fantastic solution.
[4600.62 --> 4604.82]  It was a sort of a UDP version of congestion control.
[4604.82 --> 4610.84]  If you made a broad request and you dropped data, then you would make fewer numbers of
[4610.84 --> 4614.02]  requests from fewer servers the next time.
[4614.56 --> 4615.48]  And it was adaptive.
[4615.98 --> 4620.84]  So if you got a response back from those servers and nothing was dropped, then it would try to
[4620.84 --> 4622.24]  go to a larger number of servers.
[4622.42 --> 4626.60]  And so it would break it into a multi-phase request, and it would adapt to the quality of
[4626.60 --> 4630.94]  the network and the size of the buffers relative to the size of network speed.
[4631.40 --> 4632.98]  And all UDP, so implementing the congestion.
[4633.00 --> 4633.88]  Everything done in UDP.
[4633.88 --> 4635.54]  It could just control itself.
[4635.70 --> 4637.42]  It's not falling into any of it.
[4637.46 --> 4639.68]  Because TCP was really designed to protect the network.
[4639.88 --> 4641.34]  And you don't want to protect the network.
[4641.48 --> 4643.68]  You want to get the best latency for the most users, right?
[4643.68 --> 4643.92]  That's correct.
[4644.32 --> 4644.68]  Interesting.
[4644.94 --> 4648.88]  And so how long did it take to fully understand what was happening there?
[4648.98 --> 4649.38]  Too long.
[4649.66 --> 4652.50]  So I'd say the better part of a year before we really tracked it down.
[4652.60 --> 4658.00]  Initially, the first suspicions were it was problems in the network, issues with switches,
[4658.68 --> 4659.96]  problems with libraries.
[4659.96 --> 4665.56]  But eventually we understood that this was simply because we were making the memcache code
[4665.56 --> 4666.42]  faster.
[4666.96 --> 4671.98]  And if you have less variability in a faster code path.
[4672.10 --> 4677.58]  If you're talking about a half a millisecond code path, then it's going to be plus or minus
[4677.58 --> 4678.70]  50 milliseconds.
[4678.70 --> 4682.52]  But if it's 50 microsecond code path, you're 50 nanoseconds.
[4682.78 --> 4682.92]  Interesting.
[4683.04 --> 4688.30]  So by making it more deterministic, you were increasing the odds of actual buffer overflow
[4688.30 --> 4689.08]  at the top of our act.
[4689.16 --> 4690.18]  That is exactly correct.
[4690.60 --> 4694.04]  And so it took us a bit to understand why the problem is getting worse over time.
[4694.18 --> 4695.20]  Because we were getting better.
[4695.42 --> 4698.20]  You'd improve the performance and the performance would degrade enormously.
[4698.38 --> 4698.60]  Yes.
[4698.60 --> 4700.36]  That must have been frustrating.
[4700.64 --> 4700.74]  Yeah.
[4700.92 --> 4701.32]  Wow.
[4701.62 --> 4701.80]  Interesting.
[4701.80 --> 4704.52]  So that was probably one of the first hard problems we had.
[4704.58 --> 4706.32]  We had other issues.
[4706.60 --> 4714.72]  I mean, we had one that, I'm talking a little out of school here, but we had one where the
[4714.72 --> 4721.86]  release code for configuration management missed installing mod PHP on a server.
[4722.54 --> 4725.44]  And so the PHP code was simply delivered.
[4725.96 --> 4727.04]  I mean, you ship it.
[4727.44 --> 4727.76]  Oh, God.
[4727.76 --> 4728.04]  Yeah.
[4728.32 --> 4729.08]  So that was pretty ugly.
[4730.86 --> 4731.78]  That happened once.
[4731.82 --> 4735.08]  And I think there's still fragments of that code floating around the net.
[4735.10 --> 4735.26]  Yeah.
[4735.38 --> 4737.66]  That's hard to scrub the internet and all that one.
[4737.66 --> 4741.48]  And so that just sort of reinforces, you know, the importance of getting configuration
[4741.48 --> 4744.42]  management right and making sure that it's verified.
[4744.74 --> 4749.30]  Well, that's funny to think that like for a misconfiguration, we accidentally ship the source
[4749.30 --> 4749.48]  code.
[4749.54 --> 4752.16]  That's like a new kind of failure mode at that time, right?
[4752.18 --> 4755.44]  That's not something we think of in a non-networked system, certainly.
[4755.44 --> 4760.00]  Well, and it sort of elevates the importance of configuration management.
[4760.00 --> 4766.76]  I mean, people sometimes think that these are, you know, sort of like the basic problems.
[4766.90 --> 4768.20]  You know, they're not the exciting problems.
[4768.28 --> 4770.78]  But in fact, if you don't get them right, you can't do anything.
[4770.78 --> 4776.00]  What was the, I mean, I have to imagine the single instruction found back at Intel was
[4776.00 --> 4776.68]  maybe up there.
[4776.76 --> 4781.18]  But was there one that was the most gratifying kind of bug you found or resolved in your career?
[4781.60 --> 4788.28]  I would say that if I had to point to, you know, the one that we spent the most time
[4788.28 --> 4789.84]  on, I'd say the problem I just mentioned.
[4790.06 --> 4790.52]  Oh, wow.
[4790.52 --> 4795.72]  Trying to understand why it is the better we made memcache that in some ways, the worse
[4795.72 --> 4796.90]  it performed.
[4797.14 --> 4801.48]  We could increase the total number of requests per second that a server could deliver, but
[4801.48 --> 4803.18]  these error rates continued to increase.
[4803.26 --> 4806.84]  And I think that took longer than it should to shake out this.
[4806.84 --> 4810.20]  Well, also, you're a long way from being able to just use a logic analyzer to figure it
[4810.20 --> 4810.40]  out.
[4810.52 --> 4812.34]  I mean, it's like, it's a big, complicated system.
[4812.48 --> 4812.60]  Yeah.
[4812.60 --> 4817.56]  And we had to understand the switches and get the right metrics out of the switches to
[4817.56 --> 4818.50]  understand what was happening.
[4819.14 --> 4820.70]  That must have been frustrating, I assume.
[4820.80 --> 4820.92]  Yeah.
[4821.02 --> 4821.94]  That was a big one.
[4822.34 --> 4823.26]  That was a big one.
[4823.86 --> 4825.30]  To actually figure out what was going.
[4825.46 --> 4829.76]  So then when was the genesis of the Open Compute Project then at Facebook?
[4829.86 --> 4830.58]  Was that a couple of years later?
[4830.58 --> 4832.28]  Oh, that was many years later.
[4832.54 --> 4832.68]  Okay.
[4832.82 --> 4834.74]  Well, many years, you know, in internet time.
[4834.86 --> 4835.44]  Right, right, right.
[4835.44 --> 4836.34]  Two years later.
[4836.54 --> 4836.76]  Right.
[4836.94 --> 4837.10]  Nice.
[4837.24 --> 4837.90]  Three years later.
[4837.90 --> 4844.54]  And the Open Compute Project, Jonathan Heiliger was one of the drivers of that project.
[4845.10 --> 4849.72]  And there, of course, we're already at a scale where it simply made sense to have hardware
[4849.72 --> 4851.00]  that was optimized to task.
[4851.96 --> 4856.52]  And of course, in the early days, you're buying things off the shelf because your scale doesn't
[4856.52 --> 4857.56]  warrant doing anything else.
[4858.80 --> 4859.14]  Interesting.
[4859.14 --> 4865.56]  So, you know, I think that in kind of the modern era, we think of the hardware as not being
[4865.56 --> 4871.38]  important anymore, but it's still the underpinning of everything.
[4871.50 --> 4872.80]  And what do you see kind of going forward?
[4872.92 --> 4876.36]  I mean, first of all, do you throw up in your mouth a little bit when you see like serverless
[4876.36 --> 4878.24]  and cloudless and all this other kind of nonsense?
[4879.54 --> 4881.22]  Serverless, I'm still grappling with.
[4881.94 --> 4882.20]  Nice.
[4882.22 --> 4883.08]  That makes two of us.
[4884.60 --> 4889.24]  I'm sure there's a rationale there and I'm sure it's just my inability to understand it.
[4889.42 --> 4890.54]  Oh, don't be so sure.
[4891.04 --> 4892.62]  You've got a kindred spirit in Jess.
[4892.78 --> 4892.94]  Yeah.
[4892.94 --> 4896.02]  So, no, I'm still trying to work that one through.
[4896.56 --> 4900.22]  Yeah, but things tend to come, you know, everything tends to repeat itself.
[4900.52 --> 4907.00]  So ideas which you, you know, saw 30, 40 years ago suddenly become new again.
[4907.34 --> 4912.78]  And, you know, today we're looking at what do we do with non-volatile RAM?
[4913.20 --> 4917.96]  You know, so Intel's Optane technology is an example.
[4918.62 --> 4920.70]  There'll be interesting applications for that.
[4920.70 --> 4923.98]  And I think back to an early system I used called Multics.
[4924.26 --> 4927.56]  This was at the GE Computing Group, which became Honeywell.
[4927.96 --> 4931.64]  They were participants in the Multics project with Bell Labs and MIT.
[4932.10 --> 4935.98]  And this was a system that supported a single level virtual store.
[4935.98 --> 4940.48]  Well, so there were no opens and closes, reads and writes.
[4940.70 --> 4943.88]  You simply attached to a memory segment and you used it.
[4943.96 --> 4947.78]  And then you detached from the memory segment and it was stable.
[4948.40 --> 4951.22]  And so you wrote IO-less software.
[4951.22 --> 4953.70]  We're actually at a point today where we can do that.
[4954.24 --> 4956.78]  And that really changes the application paradigm.
[4956.94 --> 4960.46]  The application, the state of the application could be in the app itself.
[4961.02 --> 4963.80]  You know, you're not having to think about storage management.
[4964.24 --> 4971.20]  But also you avoid sort of the semantic gap between read and write and what you're really trying to do with the storage.
[4971.20 --> 4980.28]  So blocking and unblocking and marshalling of data, you know, putting it in a serialized formats, all of these things suddenly aren't important to the app anymore.
[4980.46 --> 4990.38]  You're simply, the data lives in the application view of the data structure and never in the storage view of the data structure.
[4990.38 --> 4994.90]  And I think that offers, that's going to offer some for the right applications that can be groundbreaking.
[4995.02 --> 5000.30]  Yeah, that'll be interesting because it allows for that abstraction to obviously be shifted.
[5000.48 --> 5003.38]  You still have to think about the non-volatility of that state though, right?
[5003.40 --> 5005.64]  I mean, if you leave yourself in an inconsistent state.
[5006.02 --> 5014.54]  You have to, you obviously have to have paradigms for managing consistency and for logging and changes.
[5014.54 --> 5021.08]  So not all of the overhead of a traditional database, for example, goes away.
[5021.42 --> 5023.16]  But you're going to implement this very differently.
[5023.42 --> 5027.66]  And one of the ways I like to think about databases is saying how well do they use their memory?
[5028.12 --> 5032.38]  A database that really makes effective use of its memory is probably performant.
[5032.42 --> 5037.48]  And one which, where the working set of the application is distributed across a large number of blocks,
[5037.86 --> 5042.26]  where there's maybe other used data in the block, so you don't view it as internal fragmentation,
[5042.26 --> 5045.44]  but the other data in the block may not be part of the working set.
[5045.52 --> 5048.34]  But because of the way you needed to structure your index,
[5048.38 --> 5051.30]  it was inevitable that you had this on-disk organization.
[5051.68 --> 5058.72]  Well, that database may not be as effective as it could be because they're limited by the size of RAM.
[5058.72 --> 5062.98]  And if your RAM is allocated to data that doesn't matter,
[5063.14 --> 5068.82]  then you're not going to get all that you potentially could out of the hardware architecture.
[5068.82 --> 5074.36]  So, or out of your overall spend on infrastructure.
[5075.16 --> 5080.38]  So, thinking about, you know, new models for the database where it's all record-oriented,
[5080.54 --> 5082.46]  you never have this notion of blocking,
[5082.64 --> 5087.34]  because blocking doesn't matter in this type of a single-level virtual store.
[5087.72 --> 5089.50]  I think there's going to be a lot of opportunities there.
[5089.72 --> 5090.18]  Yeah, interesting.
[5090.36 --> 5093.38]  But, and it will be the databases themselves that implement it.
[5093.42 --> 5096.58]  So, we'll still, it's not that everyone's going to need to think about that kind of,
[5096.58 --> 5099.56]  that non-volatile consistency, but it's that we'll be able to.
[5099.96 --> 5101.26]  Or it may be new databases.
[5101.26 --> 5101.90]  Think about it.
[5101.92 --> 5104.46]  This might be enough of a paradigm shift that it says that,
[5104.46 --> 5108.18]  you know, new databases will enter the,
[5108.82 --> 5112.92]  will take advantage of this change in order to enter the market.
[5113.36 --> 5113.72]  Interesting.
[5114.46 --> 5116.98]  It may be some of the old ones are able to adapt to this model.
[5117.12 --> 5119.88]  But, you know, that's a future I don't think I can predict,
[5120.00 --> 5122.06]  but I just feel that this is disruptive.
[5122.86 --> 5123.22]  Interesting.
[5123.22 --> 5123.34]  Interesting.
[5123.56 --> 5125.36]  And certainly it feels like something that is,
[5125.50 --> 5126.22]  that we're ripe for,
[5126.32 --> 5128.60]  to terms of the non-volatility of main memory,
[5128.72 --> 5130.56]  or getting main memory speeds with non-volatility.
[5130.68 --> 5132.16]  It feels like it would shake things up quite a bit.
[5132.36 --> 5133.00]  There's the potential.
[5133.14 --> 5134.88]  This is, you know, sort of like flash disk,
[5135.06 --> 5136.66]  shook up the storage market.
[5137.20 --> 5139.40]  You know, there are these technologies that are highly disruptive,
[5139.40 --> 5142.34]  and they create the opportunities for new players in the market.
[5142.52 --> 5144.02]  So, I think this is one as well.
[5144.28 --> 5146.78]  So, given the number of trends that you've been early on,
[5147.04 --> 5149.82]  let me know when you're going to the store to buy the Optane.
[5149.82 --> 5150.68]  Maybe it's now.
[5150.82 --> 5151.58]  I just need to, I gotta,
[5151.80 --> 5154.48]  I feel like we gotta be following Jeff wherever he goes.
[5155.06 --> 5157.00]  A couple database companies falling out of that.
[5157.62 --> 5158.02]  Exactly.
[5158.18 --> 5159.52]  Well, you know, like everything else,
[5159.66 --> 5162.64]  unless you're wrong some reasonable percentage of the time,
[5162.68 --> 5163.68]  you're probably too slow.
[5164.10 --> 5168.08]  So, I don't know if that's a good investment strategy.
[5168.44 --> 5169.28]  I'm wrong too.
[5169.50 --> 5169.74]  Okay.
[5169.86 --> 5171.02]  Well, that's a relief.
[5171.32 --> 5174.10]  I'm wrong enough to have confidence that I'm not moving too slow.
[5174.10 --> 5174.58]  Okay.
[5174.86 --> 5177.50]  Well, because it feels like you've been right a bunch of times,
[5177.50 --> 5182.92]  and you certainly have been at the epicenter of some of the biggest shifts we've seen in computing,
[5183.28 --> 5186.46]  and right on the metal all those times.
[5186.82 --> 5190.16]  So, Jeff, thank you very, very much.
[5190.42 --> 5191.24]  Yeah, this was terrific.
[5191.48 --> 5192.08]  Yes, thank you.
[5192.20 --> 5193.74]  This has been amazing.
[5194.00 --> 5195.04]  This was amazing.
[5195.48 --> 5199.20]  And what I learned an important lesson is make sure you limit engineers
[5199.20 --> 5201.26]  to no more than three sales meetings a day.
[5201.26 --> 5204.14]  I think you drew the wrong lesson from that.
[5204.30 --> 5205.54]  Yeah, yeah, exactly.
[5206.44 --> 5208.12]  But, Jeff, thank you very much.
[5208.62 --> 5213.14]  And if people want to, in terms of learning more about you or your career
[5213.14 --> 5214.54]  or some of the technologies you're interested in,
[5214.60 --> 5215.78]  is there a particular place they should go to?
[5216.08 --> 5218.30]  Well, there would be if I put something like that together,
[5218.40 --> 5219.58]  but I have to admit I have not.
[5219.80 --> 5220.00]  Okay.
[5220.70 --> 5223.24]  Well, so maybe go check out Locust, it sounds like for sure.
[5223.26 --> 5229.90]  Maybe I need to make that as a resolution this year to document some of what I've done.
[5229.90 --> 5231.88]  Well, if we can help you document it, we'd love to,
[5231.98 --> 5234.40]  because I think there's just a lot in here.
[5234.60 --> 5236.16]  Well, thank you very much for your time today.
[5236.26 --> 5237.46]  Well, thank you very much for having me.
[5238.22 --> 5238.52]  All right.
[5238.68 --> 5243.74]  And thank you, dear listener, for joining us for what was a terrific episode of On the Metal.
[5244.20 --> 5245.84]  I am Brian Cantrell.
[5246.06 --> 5248.10]  And with me again, it's Jess and Steve.
[5248.50 --> 5248.80]  Adios.
[5249.00 --> 5249.36]  Thank you.
[5249.68 --> 5249.86]  Bye.
[5250.56 --> 5252.30]  You've been listening to On the Metal,
[5252.52 --> 5254.56]  tales from the hardware software interface.
[5254.88 --> 5256.82]  For show notes, to learn more about our guests,
[5256.82 --> 5261.00]  or to sign up for our mailing list, visit us at onthemetal.fm.
[5261.44 --> 5263.84]  On the Metal is a production of Oxide Computer Company
[5263.84 --> 5267.24]  and is recorded in the Oxide Garage in Oakland, California.
[5267.86 --> 5270.84]  To learn more about Oxide, visit us at oxide.computer.
[5271.32 --> 5274.34]  On the Metal is hosted by me, Brian Cantrell, along with Jess Fussell,
[5274.56 --> 5277.02]  and we are frequently joined by our boss, Steve Tuck.
[5277.26 --> 5281.16]  Our original and awesome theme music is by J.J. Wiesler at Pollen Music Group.
[5281.42 --> 5285.12]  You can learn more about J.J. and Pollen at pollenmusicgroup.com.
[5285.12 --> 5289.30]  We are edited and produced by Chris Hill and his crew at HumblePod.
[5289.62 --> 5293.86]  From Jess, from Steve, from me, and from all of us at Oxide Computer Company,
[5294.14 --> 5295.50]  thanks for listening to On the Metal.
[5315.12 --> 5328.36]  You can learn more about J.J. Wiesler at Pollen Music Group.
[5328.64 --> 5329.24]  We are done in this film art.
[5332.76 --> 5334.54]  Talk to you by Benwick DaryYAN.
[5334.62 --> 5335.16]  Bye T Heather & J. Jeff
[5335.16 --> 5337.24]  And have your needs.
[5337.34 --> 5338.58]  Bye YPS went for two more minutes,
[5338.64 --> 5340.34]  and have a Ihnen.
[5340.40 --> 5341.32]  Bye will be the first time.
[5341.34 --> 5342.16]  Have a nice day.
[5342.28 --> 5342.90]  Bye on the date.
[5342.96 --> 5343.74]  Have a nice day.
[5343.76 --> 5344.12]  Fortunately, bye.
