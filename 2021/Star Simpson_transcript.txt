[0.00 --> 17.08]  Welcome to On The Metal, Tales from the Hardware Software Interface.
[17.36 --> 20.34]  I'm Brian Cantrell. With me, as always, is Jess Frizzell. Hey, Jess.
[20.54 --> 20.96]  Hey, Brian.
[21.24 --> 23.42]  Joining us in the garage is our boss, Steve Tuck. Hey, Steve.
[23.70 --> 24.34]  Glad to be here.
[24.72 --> 26.62]  And Jess, do you want to introduce who we've got today?
[26.62 --> 33.10]  So today we have Star Simpson, who is currently working on drones, but also has made boards in the past,
[33.18 --> 40.54]  given a lot of awesome talks on making custom boards, and is just all over when it comes to the hardware software interface.
[41.32 --> 44.18]  Star, welcome to the podcast. It is great to have you here.
[44.34 --> 45.58]  Thank you so much. Glad to be here.
[45.66 --> 46.82]  So Star, I've got a bit of a confession.
[47.36 --> 52.42]  I feel this happened many times when you would have some incredibly interesting tweet.
[52.82 --> 56.54]  And I would tell Jess, like, when are we getting Star on the podcast?
[57.42 --> 61.60]  So we, I know that we've been looking for you to join us for a long time.
[61.68 --> 65.34]  We're very, very happy that you could accommodate it with your schedule. So welcome.
[65.60 --> 67.94]  Oh my goodness. Thank you. I was so flattered when you invited me.
[68.06 --> 71.34]  So you described yourself as having a checkered past.
[71.52 --> 74.12]  You've been all over the map. So where should we take it from?
[74.18 --> 76.12]  You want to start from the beginning? How did you get into this stuff?
[76.44 --> 80.60]  Oh, goodness. I mean, well, I would say that I got started in hardware.
[80.60 --> 84.42]  You know, I don't know if this is a classic story or like a precocious story.
[84.66 --> 89.00]  Like, I don't know. I was like 14, I think. Actually, maybe let me back up.
[89.20 --> 91.72]  I remember the first time someone told me about programming. Let's start there.
[91.88 --> 92.00]  Yeah.
[92.00 --> 98.12]  I was, I think, seven, eight or nine, something like that at my first school. And we would carpool.
[98.48 --> 103.04]  It was me and like two other kids. And one of the carpool parents was the school secretary.
[103.04 --> 105.76]  So she would come with us to school because she worked there also.
[105.76 --> 111.68]  And she knew that I was super stoked on computers. But my school was trying to be at the cutting edge.
[111.74 --> 117.08]  So they only bought Apple computers, which was like a huge expenditure. But like they were really trying to do the best for us kids.
[117.58 --> 122.80]  Unfortunately, in the 90s, Apple computers were like behind glass. You know, you could bang on the glass.
[122.84 --> 126.90]  You couldn't really get into them. So I would tinker with it and, you know, see what I could do.
[127.66 --> 133.38]  But, you know, I remember on the drive to school one morning, this woman, she said to me, she's like, you know, I could tell you really like computers.
[133.38 --> 139.98]  Like, I bet you'd like programming. And I was like, what's programming? And she's like, well, you know, those programs you use.
[140.02 --> 143.26]  I'm like, yeah, I know the programs. I know like super munchers. It's the best.
[143.64 --> 148.82]  She's like, programming is where you make the programs. And it was just like galaxy brain.
[149.00 --> 156.10]  Like, oh my God, someone makes the software. And after that, I remember this is actually how I got into hardware.
[156.62 --> 162.56]  I remember trying everything to understand how to do the programming because I wanted to make the programs.
[162.56 --> 172.40]  And I eventually ended up, I think, you know, forgive me, like pirating Borland Metro Works C++ Code Warrior for the Mac.
[172.54 --> 175.64]  Now, was that your next step from the carpool? I mean, that's a big step.
[176.28 --> 177.08]  Actually, yes.
[177.46 --> 179.54]  Wow. That's a precocious child.
[179.54 --> 181.16]  There was no one around me to guide me.
[181.16 --> 183.56]  I didn't know where to begin.
[183.68 --> 184.34]  Yeah, that's great.
[184.34 --> 191.18]  That's what the internet told me to do because the internet at the time was like, yeah, if you can't write like a shell interpreter, then like, are you even a programmer?
[191.34 --> 192.68]  And I was like, I don't know. I'm nine.
[194.38 --> 197.46]  So it seemed like, you know, that's everything pointed me in that direction.
[197.72 --> 200.44]  I needed to get the thing to do the thing. I got the thing.
[200.44 --> 206.68]  And unfortunately, you know, due to my ineptitude at pirating or whatever, like it just didn't come with the standard IO library.
[207.12 --> 207.48]  Okay.
[207.62 --> 212.20]  And so like it came with a hello world code example that wouldn't compile.
[212.42 --> 213.98]  Right. Because you didn't have streams, right?
[214.02 --> 215.32]  IO streams. It was missing IO streams.
[215.50 --> 216.02]  Yeah, exactly.
[216.16 --> 220.68]  And so, you know, I was just like, wow, this is like way harder than I thought it would be.
[220.68 --> 222.06]  I don't know what to do.
[222.46 --> 226.86]  And so that's kind of how I like kind of ended up bouncing off of coding initially.
[227.32 --> 233.06]  And instead, just like keeping this like burning fire under the surface of like, I want to learn more about the computers.
[233.36 --> 234.50]  I don't know what to do.
[234.88 --> 238.34]  The C++ thing is like inscrutable and kind of a nightmare.
[238.82 --> 242.68]  And so then like a few years later, right, you can imagine I still keeping my eye out.
[242.74 --> 244.52]  Like, I don't know how to do this. I really want to do it.
[244.88 --> 247.56]  I found a book on like kind of like building your own circuits.
[247.56 --> 248.92]  And I was like, there it is.
[248.92 --> 251.62]  And I took that book and I went to Radio Shack.
[251.74 --> 253.52]  Like somehow this is more accessible, right?
[253.56 --> 254.66]  RIP Radio Shack, right?
[254.80 --> 255.42]  RIP Radio Shack.
[256.08 --> 261.22]  We paid an enormous sum of money to me at the time being preteen with no cash of my own.
[261.26 --> 266.00]  I was like, I can't believe my mom's spending this much money to buy a bunch of circuit components from Radio Shack.
[266.24 --> 269.68]  And I spent like the entire summer just building every circuit example in the book.
[269.70 --> 270.12]  Oh my gosh.
[270.36 --> 275.76]  And so it was like my failure to get the code example to compile sent me directly into circuit design.
[276.26 --> 276.66]  Yeah.
[276.76 --> 278.84]  I don't know what to think about C++ coming out of this.
[278.84 --> 282.66]  Because my going in thought is that you were abused as a child by C++.
[283.04 --> 285.36]  But now that C++ actually drove you to hardware.
[285.52 --> 285.64]  I mean.
[287.68 --> 288.08]  Look.
[288.76 --> 289.54]  That's great.
[289.70 --> 293.20]  So then getting excited about hardware, obviously, over that summer, making like, I assume,
[293.36 --> 295.80]  were you making like burglar alarms?
[296.04 --> 297.04]  And they, what I'm trying to think.
[297.04 --> 297.44]  Yeah, that kind of thing.
[297.44 --> 297.74]  Yeah, right.
[297.74 --> 303.98]  You know, and the funny thing is, it gave me this strong impression that like, initially, that like code was completely inscrutable.
[303.98 --> 306.58]  But like hardware, you could always get to the bottom of the problem.
[307.54 --> 308.20]  Hardware is easy.
[308.40 --> 308.60]  Yeah.
[308.60 --> 308.80]  Yeah.
[308.88 --> 309.40]  That's, I can.
[309.68 --> 312.98]  Well, and it allowed you to probably completely understand what was in front of you.
[312.98 --> 317.02]  Because clearly you were, even at a young age, someone who really wanted to understand things.
[317.20 --> 318.56]  I really wanted to understand things.
[318.64 --> 318.74]  Yeah.
[318.84 --> 319.16]  At their root.
[319.16 --> 319.60]  Yeah.
[319.78 --> 326.66]  The book, I think it was like 21 transistor, you know, slowly worked you up to, I remember the final thing was like mind-blowingly cool to me,
[326.72 --> 328.32]  which was like a circuit that had memory.
[328.52 --> 330.58]  Like you could unplug it and like plug back in.
[330.70 --> 333.72]  And like the LED, the four LED state would be the same.
[334.36 --> 334.50]  Nice.
[334.62 --> 335.72]  You actually had persistence.
[336.04 --> 336.76]  It had persistence.
[337.22 --> 340.06]  And it had like, I think I put two copper wires on the board.
[340.06 --> 343.98]  So like it had like a touch input to like increment the LED count and stuff.
[344.18 --> 345.04]  That is great.
[345.04 --> 352.38]  So at that point, did you, I mean, you obviously felt a very deep resonance and did you have an idea of what you wanted to go do at that point?
[352.50 --> 354.76]  I had a vague, but strongly directional idea.
[355.02 --> 355.20]  Yeah.
[355.30 --> 362.46]  I didn't know exactly what, because again, I was like still roughly as informed as like the kid who was like, okay, the programming, I got to, I don't know where to begin.
[362.60 --> 362.80]  Right.
[362.82 --> 364.22]  Like I'm just reading everything I can.
[364.70 --> 364.88]  Yeah.
[364.88 --> 373.46]  I got into, you know, I was really lucky to be able to get into things like robotics or like building potato cannons with my best friend in the summer.
[373.46 --> 379.82]  You know, like various stuff, you know, of varying levels of sophistication or lack thereof.
[380.26 --> 384.90]  And it all really drove me to like, I knew I wanted to make stuff for people that was going to be useful.
[385.08 --> 385.16]  Right.
[385.22 --> 388.14]  I think that was like the shape of my hope.
[388.64 --> 388.76]  Right.
[389.02 --> 390.54]  That's that engineer's calling, right?
[390.54 --> 393.54]  To actually build something that people would actually use.
[394.18 --> 395.44]  So, so what next?
[395.52 --> 396.34]  Did you head off to school?
[396.74 --> 397.38]  I did.
[397.74 --> 398.60]  I went to MIT.
[398.60 --> 402.38]  He, I found out there were many levels of nerd.
[404.84 --> 407.06]  So that was pretty, pretty cool.
[407.28 --> 407.60]  Also.
[407.78 --> 407.94]  Right.
[407.96 --> 410.20]  Cause you kind of go in thinking like, I am the nerdiest person I know.
[410.22 --> 412.18]  And then you get to like the true nerd.
[412.18 --> 412.70]  I don't know if I thought that.
[412.80 --> 415.70]  I really, I was actually quite intimidated before things even began.
[415.70 --> 422.56]  I really, I was just like, I know there are people out there that like know about these things and I want to know those people and I want to go like explore.
[423.20 --> 424.70]  And how did you get over that intimidation?
[424.78 --> 430.60]  Because I think that that's something that, that everybody kind of feels where it's like, wow, everyone is so much better.
[430.70 --> 431.46]  I absolutely felt that.
[431.52 --> 433.96]  I think most technologists have felt that at one point in time in their career or another.
[434.44 --> 442.22]  I think that there's a way of looking at things where you can either take a comparative and competitive view of the world or you can take a collaborative view of the world.
[442.22 --> 444.22]  And maybe you could take both, but I don't know about that one.
[444.22 --> 444.40]  Right.
[444.40 --> 451.08]  It's like, I think that at some point you just say like, okay, everyone who's like wildly curious ends up knowing a whole lot about something.
[451.58 --> 451.96]  Right.
[452.00 --> 454.64]  And you know, this should be celebrated is my approach.
[454.82 --> 455.18]  Yeah.
[455.22 --> 456.10]  I just want to, right.
[456.20 --> 457.00]  Understand this now.
[457.10 --> 461.92]  And Jess, Jess, you can obviously, Jess engages what I would call competitive curiosity.
[462.16 --> 463.14]  You're very good at like.
[463.14 --> 464.90]  So yeah, well, it depends.
[466.00 --> 467.12]  No, it's cool, Jess.
[467.22 --> 467.58]  It's cool.
[468.28 --> 469.56]  It really depends.
[469.56 --> 474.66]  The competitiveness I think comes into play if like I feel attacked.
[475.28 --> 476.62]  And other situations.
[476.94 --> 477.12]  Yeah.
[477.20 --> 477.36]  Okay.
[477.64 --> 481.00]  Jess is a very competitive, very collaborative person.
[481.12 --> 482.20]  I mean, don't get me wrong.
[482.34 --> 485.12]  I really love competitive atmospheres.
[485.40 --> 489.42]  I was like a really fierce high school athlete also as a swimmer.
[490.08 --> 494.18]  Like there's a, there's totally a place for competitive spirit too.
[494.18 --> 507.48]  But I think that in so far as it makes you feel intimidated, I think that like, it's, it's okay to accept that like being really into something doesn't necessarily mean anyone else also being really into that thing is like herming you or taking away from you.
[507.64 --> 507.88]  Right.
[507.96 --> 508.70]  I think that that's it.
[508.74 --> 508.88]  Right.
[508.92 --> 511.70]  That's the like, and I think that it's only just, that's what you're great at.
[511.72 --> 513.32]  It's like, Hey, I've discovered something great.
[513.62 --> 515.76]  I'm going to share it with everybody because I think it's interesting.
[516.10 --> 520.32]  But I also think part of this podcast is finding those people who do the things, which is cool.
[520.54 --> 520.76]  Yeah.
[520.76 --> 527.14]  And then, uh, yeah, cause I love anyone who is just like really curious about a topic and goes super in depth.
[527.14 --> 530.30]  I'm like, okay, I want to like know what's going on in their brain.
[531.30 --> 541.42]  So speaking of topics in depth, so you have done a bunch with drones and I am really curious about how that started and when, because you were probably, you were kind of on the forefront.
[541.74 --> 542.42]  Oh my gosh.
[542.62 --> 542.84]  Yeah.
[542.86 --> 543.48]  It's a good question.
[543.48 --> 551.30]  And I think, um, I don't know what exactly hit me, but I would, I'd probably mark 2009 as me having developed an obsession with, uh, autonomous aircraft.
[551.42 --> 551.78]  Right.
[551.84 --> 553.66]  And started to think about it a lot then.
[553.66 --> 558.46]  So, you know, I usually give people a few minutes head start to run before we bring this topic up because.
[558.56 --> 559.28]  Oh, nice.
[559.60 --> 560.54]  Oh, I'm excited.
[561.22 --> 561.88]  That's great.
[561.96 --> 562.40]  I don't want that.
[562.46 --> 563.64]  Yeah, exactly.
[563.64 --> 565.32]  Uh, wow.
[565.38 --> 565.52]  Okay.
[565.52 --> 569.24]  So 2009, I'm trying to think of the history of autonomous aircraft.
[569.56 --> 572.74]  That's early from a kind of a, an accessibility perspective, right?
[572.76 --> 573.56]  I mean, in terms of like.
[573.72 --> 574.14]  Yes and no.
[574.20 --> 576.66]  For, for how we currently think about what we say drones.
[576.66 --> 577.40]  Uh, yes.
[577.70 --> 580.38]  But from the history of autonomous aircraft, no.
[580.46 --> 585.62]  I mean, most people don't realize Marilyn Monroe actually worked in a drone factory during the war.
[585.62 --> 586.08]  Oh, interesting.
[586.08 --> 591.74]  Um, because this was just sort of like radio controlled target drones that the military were using at the time for like target practice or whatever.
[591.80 --> 594.24]  She actually had a wartime job, which is like assembling these things.
[594.34 --> 594.74]  Interesting.
[595.00 --> 595.66]  Well, that's nuts.
[595.74 --> 603.22]  I feel, and Steve, I don't know about you or just, I feel like my first association with it is like, is the military using them post 9-11 in Afghanistan.
[603.22 --> 604.28]  Oh, absolutely.
[604.54 --> 611.68]  And that was a huge part of my inspiration because at the time, all of the headlines that included that word drone were pretty terrifying.
[611.92 --> 612.14]  Right.
[612.26 --> 612.92]  Fairly negative.
[612.92 --> 621.06]  And I don't know why, but my approach at the time being, you know, college students sort of being curious, where do ideas come from?
[621.30 --> 622.52]  How does technology work?
[622.82 --> 627.76]  Was to say, you know, that can't be the end of the story for this technology.
[627.98 --> 630.46]  Like, what would I do if I had a drone?
[630.56 --> 631.76]  I would do something different with it.
[631.80 --> 632.30]  What would I do?
[632.36 --> 634.20]  Or if I had autonomous aircraft, what would I do?
[634.56 --> 637.62]  That is so fundamentally optimistic, I think.
[637.90 --> 641.66]  Which I think, this is a hallmark of technology that I think is, is optimism.
[641.66 --> 645.12]  And I think as a society, we can be very pessimistic about technology.
[645.84 --> 645.96]  Fair.
[646.22 --> 650.20]  And I think it's good on you to realize that like, actually, we can do something different.
[650.32 --> 653.64]  We don't need to, this has got applications that are not merely in the military.
[654.12 --> 655.14]  Or it might.
[655.24 --> 657.28]  And if it were to, what would those be?
[657.42 --> 657.62]  Right.
[657.80 --> 658.84]  That started me thinking.
[659.10 --> 660.26]  So then where to from there?
[660.72 --> 663.52]  Well, I mean, as mentioned, I was a college student.
[663.70 --> 666.84]  College students are always hungry, if nothing else.
[666.84 --> 670.62]  So the answer to my question was, I'd use it to bring food to myself.
[671.72 --> 672.12]  Nice.
[673.10 --> 674.84]  That's kind of like a thing, I feel like.
[674.96 --> 675.38]  Oh, yeah.
[675.60 --> 676.78]  Way before your time.
[676.94 --> 677.14]  Yeah.
[677.26 --> 678.58]  You are way before your time.
[678.82 --> 683.28]  And I feel like you're after like, all three of us are definitely, eating plays a central
[683.28 --> 684.44]  role in all three of our lives.
[685.30 --> 685.62]  Totally.
[685.80 --> 686.00]  Totally.
[686.14 --> 688.06]  I can't think of a person for whom that's not true.
[688.24 --> 688.42]  Right.
[688.82 --> 689.06]  Okay.
[689.08 --> 690.68]  So you're like, I am going to use this.
[690.88 --> 691.80]  Autonomous food delivery.
[692.12 --> 694.36]  Well, that's a huge part of it.
[694.46 --> 699.92]  For me, I think the goal was to try and bring people into kind of what I saw might be possible.
[700.42 --> 703.90]  You know, I'd also say that like, if you could have food brought to you right now, right?
[703.92 --> 706.96]  This was like a very relatable example that everyone could get on board with.
[707.22 --> 710.38]  You know, I basically just started keeping notebooks of ideas of like, here's what I would
[710.38 --> 711.76]  do if I had this autonomous aircraft.
[711.76 --> 716.40]  The one that I think I became known for, which is called the taco copter on the theory that
[716.40 --> 720.84]  you could have a quadro to bring you a taco to your location on demand.
[720.84 --> 722.84]  And that's the one that really had traction.
[723.28 --> 723.36]  Right.
[723.42 --> 726.16]  But even at the time, I would like to stay for the record.
[726.30 --> 732.00]  I was thinking about what would be valuable price per pound of tacos is fairly low.
[732.28 --> 732.46]  Right.
[732.90 --> 733.08]  Right.
[733.10 --> 734.58]  But like, it caught people's attention.
[734.90 --> 736.64]  Like, look, you are more than just the taco copter.
[736.78 --> 739.14]  I think the taco copter is the biggest.
[739.14 --> 739.62]  But that's genius.
[739.86 --> 740.44]  It is genius.
[740.44 --> 743.44]  I'm not wearing a hoodie right now, but now I wish I was so that I could pull the hood
[743.44 --> 744.00]  over my face.
[744.88 --> 747.80]  And where are quadcopters when you are starting to think about this?
[747.98 --> 749.44]  At the very bleeding edge.
[749.44 --> 751.22]  So at the time, actually, I'm in undergrad.
[751.54 --> 757.02]  A few of my friends were aerodynamic students or like more into the like the embedded systems,
[757.16 --> 757.40]  you know.
[757.70 --> 764.36]  And I remember one of them at like great expense had had written a letter to Atmel to get them
[764.36 --> 771.22]  to like give us three accelerometers that were like, you know, $100 each and hand built a
[771.22 --> 771.74]  quad rotor.
[771.74 --> 773.74]  But it was like really lashed together.
[773.74 --> 775.24]  Like now you can buy kits.
[775.24 --> 779.00]  It's like there's fairly good support for like if you want to do this yourself, you know,
[779.22 --> 783.70]  starting from scratch, writing the embedded system to control the thing, you know, all
[783.70 --> 784.00]  of that.
[784.20 --> 785.24]  Could you educate us on that?
[785.34 --> 785.62]  Exactly.
[785.66 --> 789.60]  Because I know there's a lot of software involved in, but I don't know what any of that software
[789.60 --> 790.12]  looks like.
[790.18 --> 793.56]  So what are the kind of the key hardware components and the software to kind of stitch it together?
[793.56 --> 794.04]  Sure.
[794.18 --> 801.14]  So that drone and a lot of drones, a lot of quadcopters are four electric, electrically
[801.14 --> 805.32]  controlled motors, an accelerometer, which basically measures the direction of gravity
[805.32 --> 807.36]  or G forces as you move.
[807.64 --> 813.78]  And if you imagine like a basic hover where it's just staying in place, it seeks to balance
[813.78 --> 818.80]  the current output through the motors so that the position doesn't drift.
[819.14 --> 820.10]  Did that make any sense?
[820.20 --> 821.18]  Yeah, that definitely made sense.
[821.18 --> 825.14]  Well, so kind of the follow up question is because this is something I has been kind
[825.14 --> 827.06]  of been my intuition, but I'd love to get the definitive answer.
[827.16 --> 831.68]  It seems to me that it is not really possible to build a quadcopter without software.
[831.78 --> 832.82]  Is that a fair statement?
[833.00 --> 834.26]  I would actually flip that statement.
[834.42 --> 837.82]  And I would say that the quadcopter is really interesting because if you know how to write
[837.82 --> 841.88]  software, it's one of the first flying things you can kind of trivially control without
[841.88 --> 845.78]  having to get into aerodynamics or control or any of these like esoteric fields that have
[845.78 --> 849.14]  been developed for the last 50 years because it's a symmetric aircraft, right?
[849.14 --> 853.26]  So you can really kind of naively say like, okay, if it's like tipped that way, bring
[853.26 --> 857.14]  the power up on this motor, bring the power down on the opposite one, right?
[857.30 --> 857.78]  Oh, interesting.
[858.02 --> 862.14]  And like get it to hover or like, you know, accept some constant velocity to get to go
[862.14 --> 863.08]  in a particular direction.
[864.08 --> 867.98]  So it's a, it's a really neat platform for allowing software to fly.
[868.42 --> 868.76]  Interesting.
[869.00 --> 869.24]  That's cool.
[869.42 --> 869.54]  Yeah.
[869.54 --> 870.22]  That is really cool.
[870.32 --> 873.80]  Because like if it was a plane, you'd have to know the wing dynamics.
[874.00 --> 875.02]  What's an aileron.
[875.14 --> 875.92]  Yeah, exactly.
[876.24 --> 876.40]  Right.
[876.44 --> 878.22]  You have to do a lot more, a lot more physics.
[878.28 --> 883.30]  It sounds like whereas it's, but without a, it seems to me that kind of before the era
[883.30 --> 888.42]  of software avionics, some of the stuff was, would have been much more difficult or impossible.
[888.54 --> 888.98]  Or is that a.
[889.36 --> 889.68]  Yeah.
[889.68 --> 895.68]  I mean, the quadcopter configuration, I think would be pretty difficult for a human pilot.
[895.80 --> 902.88]  Well, I mean, there've been very few experiments, but there was one, the Pia Sec EPA 79 or 97,
[903.08 --> 909.56]  I can't remember, which was four, I think Huey helicopters in a like airframe with like
[909.56 --> 910.08]  a blimp.
[910.88 --> 912.60]  And like it rattled itself.
[912.78 --> 916.68]  And you know, you have four pilots trying to like human beings on board, trying to like
[916.68 --> 918.34]  coordinate with each other to like keep it balanced.
[918.34 --> 921.42]  It's like, it seems much better when it's just software.
[921.98 --> 922.08]  Yeah.
[922.14 --> 924.06]  See, this is where I'm like fundamentally a coward.
[924.56 --> 926.10]  I like you first in that thing.
[926.16 --> 926.96]  I'm not getting that thing.
[927.54 --> 928.34]  That sounds cool.
[928.64 --> 929.88]  See, this is the same.
[930.20 --> 930.84]  Spoiler alert.
[930.94 --> 931.98]  That was not a good aircraft.
[932.12 --> 932.30]  Yeah.
[933.06 --> 934.14]  That didn't end well.
[934.36 --> 938.02]  Jess has wanted to rent a scissor lift for the office to drive around the office.
[938.02 --> 939.58]  Kind of talk her down multiple times.
[939.88 --> 941.12]  Why are we bringing this up?
[941.18 --> 942.34]  You already said that I couldn't.
[942.90 --> 943.80]  Just saying you're courageous.
[944.16 --> 947.40]  I just, I just know that this, this urge is bubbling underneath the surface.
[947.40 --> 947.80]  Yeah, I know.
[947.80 --> 949.64]  Well, I'll try anything once basically.
[950.24 --> 951.14]  Except a scissor lift.
[951.34 --> 951.50]  Yeah.
[951.74 --> 953.04]  Well, because I'm not allowed.
[953.96 --> 958.00]  But this is basically beyond the control of humans to reasonably fly.
[958.10 --> 959.46]  I would assume humans can't react.
[959.54 --> 959.84]  I assume.
[960.04 --> 960.44]  Maybe not.
[961.08 --> 962.60]  I'm not going to say it's impossible.
[962.80 --> 962.96]  Right.
[962.96 --> 970.96]  But I think there are certain controls tasks people are better suited for and certain controls tasks that software would be better.
[971.56 --> 973.16]  So, or software in the loop, if nothing else.
[973.16 --> 974.88]  So, were you in that era?
[975.00 --> 976.34]  So, you're building the Taco Copter.
[976.46 --> 977.22]  So, how did that go?
[977.32 --> 978.60]  So, you're talking to your folks.
[978.80 --> 980.10]  It's kind of a funny story.
[980.22 --> 986.46]  I mean, the Taco Copter is one that sometimes I still get a little bit of, like, I don't know, negative feedback for.
[986.46 --> 988.66]  Because there's a lot involved.
[988.86 --> 989.80]  Let me put it this way.
[989.80 --> 995.92]  So, as I do, I got really interested in this world to the point of complete obsession.
[996.30 --> 999.20]  And this is, like, I'm fresh off the back of my teenage Star Wars obsession.
[999.38 --> 1002.34]  So, I didn't know how to not talk about something that I was obsessed with.
[1002.98 --> 1007.14]  And it got to the point that, like, I got invited to, like, a party, I think.
[1007.44 --> 1009.28]  I was in San Francisco for some reason.
[1009.74 --> 1018.18]  And I just wouldn't stop talking about drones and how they were going to be a super important part of the future at this party until, like, the host was like,
[1018.18 --> 1020.62]  Yeah, so everyone's good.
[1021.04 --> 1022.62]  No one wants to hear any more about drones.
[1023.24 --> 1024.08]  But why not?
[1024.20 --> 1027.02]  I would be like, okay, listen, this is a messed up party.
[1027.32 --> 1027.80]  Yeah, I agree.
[1028.08 --> 1030.52]  Because, like, any other party, I'd be like, okay, that, I want to talk to that person.
[1030.52 --> 1033.48]  Yeah, people are reporting to the host to, like, take the drone talk down.
[1033.48 --> 1034.86]  Yeah, people are, like, escalating to the host.
[1034.86 --> 1036.72]  So, this is actually an important part of the story.
[1036.72 --> 1040.26]  So, then the host of the party gave me, he kind of had taken me aside.
[1040.34 --> 1045.20]  And he was like, so, like, you know, just a thought, like, why don't you, like, make a website, you know, for your concept?
[1045.84 --> 1047.04]  And I was like, oh, brilliant.
[1048.00 --> 1049.02]  That's a great idea.
[1049.58 --> 1052.86]  So, I made a website for the TacoCopter.
[1053.44 --> 1055.62]  And that was all that happened.
[1056.04 --> 1058.48]  Basically, it was, like, a text-only website.
[1058.82 --> 1064.80]  I really thought that the idea to make a website was brilliant for a specific reason, which is, like, a college student, I didn't have a ton of cash.
[1064.80 --> 1066.34]  But I had to pay for the domain.
[1066.70 --> 1068.94]  And I knew the domain was going to expire every year.
[1069.14 --> 1074.30]  And I was really worried that I was going to, like, forget about the idea of using autonomous aircraft to, like, do stuff.
[1074.44 --> 1075.80]  And I didn't want to lose it.
[1075.80 --> 1082.46]  And so, I figured if every year the domain renewal would, like, be a nudge of, like, is this an idea whose time has arrived yet?
[1082.98 --> 1084.48]  Which is why I made the website.
[1084.70 --> 1084.84]  Okay.
[1084.94 --> 1092.42]  And it's really crucial to establish that this was not, like, some thing to, like, try and get the world's attention or anything, which is what ended up happening.
[1092.42 --> 1094.04]  So, the website pretty much just sat there.
[1094.40 --> 1095.04]  Nothing happened.
[1095.40 --> 1096.52]  There was nothing on it.
[1096.52 --> 1105.98]  And then, like, a year-ish later, I want to say, like, 2010, maybe 2011, something like that, I was like, I should spruce up that old, like, TacoCopter website.
[1106.10 --> 1107.26]  Just kind of, like, beautify it.
[1107.26 --> 1109.20]  And here's the fun backstory.
[1109.62 --> 1116.02]  So, probably, like, 10, 20 of my friends, something like that, like, a very close group of people had seen or heard of this website.
[1116.02 --> 1122.50]  And one of my friends who's just, like, he's constantly trying to, like, I don't know, he's kind of like a schemer.
[1122.58 --> 1122.90]  I don't know.
[1122.98 --> 1127.10]  Like, he's always, like, he's like, oh, here's how I'm getting more, like, points for my Hacker News account or whatever, right?
[1127.26 --> 1130.16]  So, he turned out, and I learned all of this in retrospect.
[1130.84 --> 1136.42]  He had made a new Hacker News account, and he wanted it to get a lot of, like, karma points or, you know, whatever.
[1136.42 --> 1145.48]  And a catering company, like, a YC-funded catering company launched, and they were like, hey, like, super, like, serious launch announcement.
[1145.62 --> 1147.88]  Like, oh, we're, like, delivering lunch now for companies.
[1148.24 --> 1154.76]  And this guy, he goes on there, and this, like, smart comment, he's just like, oh, yeah, that's cool, but whatever.
[1155.00 --> 1157.20]  It's, like, too bad the TacoCopter isn't delivering yet.
[1157.50 --> 1164.12]  And he posted the link to, like, my, like, you know, page out of my notebook, like, knowing this is not for anybody, like, website.
[1164.12 --> 1167.98]  Right, this is to remind you every year to contemplate whether this idea has come or not.
[1168.00 --> 1171.10]  Yeah, I realize this is very unusual to use the internet in this way.
[1171.48 --> 1172.08]  It's awesome.
[1172.08 --> 1172.24]  You know what?
[1172.46 --> 1174.66]  It feels very close to home.
[1174.84 --> 1175.66]  I like it.
[1175.74 --> 1176.28]  I like it.
[1176.54 --> 1178.44]  Nonetheless, so I had done it, right?
[1178.66 --> 1186.58]  And so he posted this, and then someone else saw the link and was like, oh, my gosh, this is so awesome.
[1186.74 --> 1189.42]  And this website, I promise you, it looked like a complete joke.
[1189.54 --> 1191.42]  There was, like, animations going everywhere.
[1191.42 --> 1194.18]  It was, like, cartoony and, you know, all the colors.
[1194.40 --> 1195.76]  Next thing you know, you've got four term sheets.
[1196.02 --> 1196.14]  Yeah.
[1197.14 --> 1201.40]  Well, yeah, there was even a little banner in the bottom because I also had bought LobsterCopter.
[1202.12 --> 1204.94]  That was, like, because it was in Boston at the time.
[1205.06 --> 1205.44]  And so I was like.
[1205.44 --> 1206.24]  Oh, that's good.
[1206.28 --> 1208.66]  I was like, LobsterCopter is like tacos of the east.
[1210.10 --> 1210.38]  LobsterCopter.
[1211.04 --> 1213.48]  That's an interesting collision of worlds.
[1213.62 --> 1214.06]  I like it.
[1214.16 --> 1216.98]  So then someone took the link and posted it to, like, the main Hacker News.
[1216.98 --> 1221.40]  And this was on, like, I want to say, like a weekday night, right?
[1221.46 --> 1228.16]  So, like, this clearly hilarious website was, like, people were starting to email it to each other because in 2011, you know, it was still, like, not like.
[1228.16 --> 1230.24]  So on the website, you said it's kind of a page of your notebook.
[1230.42 --> 1233.44]  So this is just, like, a sketch of what this thing would look like.
[1233.44 --> 1234.42]  A bookmark for an idea.
[1234.46 --> 1234.74]  Got it.
[1234.76 --> 1234.88]  Okay.
[1235.04 --> 1236.58]  You know, that's how I was treating it.
[1236.64 --> 1236.80]  Right.
[1237.36 --> 1239.12]  So people start to email each other this link.
[1239.40 --> 1246.74]  And it turned out, like, my best friends from high school had professionally gone into, like, super high volume, high traffic website hosting.
[1247.10 --> 1249.08]  Like, and I was like, oh, my gosh.
[1249.12 --> 1250.06]  I don't know what's happening.
[1250.18 --> 1251.92]  I didn't know where the traffic was coming from at the time.
[1251.98 --> 1257.20]  I actually just knew it had picked up an interest because I was in a weird time zone and the sign-up form was tied directly to my email.
[1257.70 --> 1260.30]  And it was also my birthday and I got 10,000 emails.
[1260.30 --> 1263.66]  Like, someone's messing with me.
[1263.82 --> 1264.76]  You know, like, something's happening.
[1264.76 --> 1267.62]  You had a sign-up on there to say, oh, I did the whole.
[1267.78 --> 1268.28]  Like, if you're interested.
[1268.28 --> 1269.24]  If you're interested, right.
[1269.92 --> 1271.16]  And 10,000 people were interested.
[1271.28 --> 1271.84]  10,000 people.
[1271.94 --> 1274.36]  And so I said to him, I was like, oh, my gosh.
[1274.38 --> 1276.70]  I don't know what's happening, but, like, this is getting a lot of traffic.
[1276.86 --> 1279.34]  And he said, and this was, like, a huge critical part of it.
[1279.34 --> 1281.36]  He's like, you know, I think this idea is really important.
[1281.46 --> 1282.32]  I really like this idea.
[1282.40 --> 1285.00]  Do you mind if I stand something up with, like, varnish or whatever?
[1285.08 --> 1287.86]  Like, it's more likely to stand up to all the traffic you seem to be about to get.
[1287.86 --> 1289.14]  And I was like, yeah, sure, go for it, whatever.
[1289.14 --> 1295.74]  And he basically put a, like, super simple, like, bootstrappy website up, which, like,
[1295.82 --> 1299.66]  for better or for worse, had all of the look of, like, basically a startup.
[1299.66 --> 1300.00]  Legit.
[1300.16 --> 1300.92]  Right now it looks legit.
[1301.14 --> 1308.08]  So instead of my, like, total cartoon sketch, like, nightmare, it looked like a standard bootstrap website.
[1308.60 --> 1308.76]  Right, right.
[1308.76 --> 1315.42]  And the other thing that happened is because I was in the weird time zone and he was just, like, you know, flying through this at, like, you know, the nighttime.
[1315.70 --> 1322.88]  The next morning when everyone checked their emails because their friend had, like, sent them this, like, joke link, they saw this, like, super serious thing.
[1323.18 --> 1329.20]  And, you know, maybe, like, PR marketing professional could have predicted that, like, how this is going to go, but I had no idea.
[1329.20 --> 1333.50]  So then the taco copter was, like, a big news story.
[1333.84 --> 1335.80]  And I ended up on the Colbert Report.
[1335.94 --> 1336.42]  Oh, my gosh.
[1336.46 --> 1336.80]  Whoa!
[1337.30 --> 1337.98]  That's nuts!
[1337.98 --> 1338.88]  That is amazing.
[1339.00 --> 1340.88]  I really didn't expect it.
[1341.00 --> 1342.50]  I was, like, I was traveling myself.
[1342.92 --> 1343.80]  It was all completely unexpected.
[1343.90 --> 1346.78]  Several YC-funded companies for food delivery faultics.
[1346.86 --> 1347.64]  They knew they couldn't compete.
[1347.86 --> 1349.60]  Started, actually, then.
[1350.14 --> 1350.68]  Yeah, right.
[1350.96 --> 1351.30]  Exactly.
[1351.72 --> 1352.34]  That's crazy.
[1352.42 --> 1355.12]  So, wait, it's all hacker news is, like, patient zero.
[1355.22 --> 1355.84]  Patient zero, yeah.
[1355.84 --> 1358.28]  My friend in his, like, throwaway account.
[1358.76 --> 1358.96]  Wow.
[1359.08 --> 1367.18]  So, how, I mean, how did you, I mean, you must have been, like, look, this was, like, a bit of a, not quite a joke, but this is a, this was some early ideation.
[1367.86 --> 1368.18]  Yeah.
[1368.18 --> 1368.30]  Yeah.
[1369.02 --> 1369.38]  Yeah.
[1369.40 --> 1373.42]  And this is why I, like, point out that, like, I, I think I'd also registered a bunch of others.
[1373.42 --> 1379.20]  Like, I'd registered docu-copter on the theory that you'd want to quickly, like, schlep around legal documents or things with actual value.
[1379.32 --> 1384.24]  Because people, people for years, like, I also had hemocopter on the, like, medical.
[1384.24 --> 1384.88]  Ooh, hemocopter.
[1384.88 --> 1385.48]  That's good.
[1385.64 --> 1387.86]  God, you just went on a bender for the.
[1387.88 --> 1389.48]  I was buying up domains, man.
[1389.84 --> 1391.54]  Doc-copter should be a TLD.
[1391.88 --> 1392.58]  Doc-copter should be.
[1392.58 --> 1393.12]  That's true.
[1393.12 --> 1393.96]  If we're ready for that.
[1395.96 --> 1396.28]  Yeah.
[1396.54 --> 1398.04]  So, that's how that all went, right?
[1398.08 --> 1402.94]  And I, like, I think there's a part of me that still feels like I need to defend, like, it wasn't really intended as a joke.
[1403.06 --> 1405.12]  It's something I really strongly believe in.
[1405.54 --> 1405.62]  Right.
[1405.62 --> 1406.22]  But it was early.
[1406.36 --> 1407.90]  It wasn't quite intended for the world.
[1408.20 --> 1408.44]  Right.
[1408.62 --> 1408.84]  Right.
[1408.88 --> 1409.00]  Right.
[1409.00 --> 1409.18]  Right.
[1409.18 --> 1409.22]  Right.
[1409.22 --> 1409.94]  It was early ideation.
[1409.94 --> 1410.98]  But that's really cool.
[1411.30 --> 1418.48]  Well, but I also feel, and I'm sure you got this, that people can be, and it's very annoying when people are so critical of early ideation, where it's like, why haven't you built this thing yet?
[1418.48 --> 1420.70]  It's like, because it's an early idea.
[1420.90 --> 1430.46]  Well, we had, we'd messed around with, like, a friend of mine has, like, he, you know, was super into building drones, so we hung grocery bags full of tacos and, like, flew them around.
[1430.92 --> 1432.38]  Oh, so this was further along.
[1432.42 --> 1433.82]  This was more than just a page in the notebook, then.
[1433.86 --> 1434.70]  You'd actually built the thing.
[1435.22 --> 1445.56]  You know, like, we had experimented with it and, like, explored it, but I think that there were a lot of things, technologically, in terms of, like, public acceptance of the idea, regulation.
[1445.56 --> 1450.06]  Like, more so than now, there were no rules governing whether you could do this or not.
[1450.12 --> 1458.74]  It just seemed like, and I was pretty, I was actually weirdly, like, very conservative about that whole, you know, thing, because I'm like, I think there's a quote I gave at the time, and I'm proud of it.
[1458.78 --> 1459.96]  I think it was, like, 22 or 23.
[1460.10 --> 1464.74]  I was like, it's not unreasonable to regulate this, because there are some risks.
[1465.02 --> 1466.94]  Oh, now you just capsized another YC company.
[1468.12 --> 1468.72]  Oh, goodness.
[1469.06 --> 1470.82]  You know, like, we looked into it.
[1470.82 --> 1474.22]  It's not that we hadn't, but then at the same time, people were like, well, how much is really there?
[1474.42 --> 1478.14]  And, you know, I didn't have, like, incorporated anything.
[1478.44 --> 1479.94]  You know, I was, like, working on some other thing.
[1480.10 --> 1491.82]  So it ended up kind of exploding and then collapsing, because people are like, you know, I think it was actually Wired ran, like, a hit piece at the end of, like, a week of, like, what is happening, like, media coverage.
[1491.96 --> 1493.84]  And then Wired was like, it's a hoax.
[1494.50 --> 1494.58]  What?
[1494.66 --> 1495.08]  And I was like.
[1495.14 --> 1495.74]  How dare they?
[1495.74 --> 1500.80]  I was like, why would you, like, who are all you people and why are you in my yard?
[1501.30 --> 1501.42]  Right.
[1503.58 --> 1504.76]  He was supposed to be here.
[1505.38 --> 1506.60]  I wasn't supposed to come to work today.
[1506.80 --> 1507.58]  Didn't invite any of you.
[1507.84 --> 1508.76]  Is that where it ended up?
[1508.82 --> 1510.08]  Is it with the Wired hit piece?
[1510.14 --> 1511.50]  Was that the coda for the Taco Copter?
[1513.30 --> 1517.62]  Roughly speaking, yeah, because I still wasn't, like, I was still working on some other project.
[1518.16 --> 1523.86]  But I think that is, like, as you mentioned, about when a bunch of kind of current drone companies launched.
[1523.86 --> 1529.42]  It was a few months after that, a bunch of bigger tech corporations announced their quadcopter-based initiatives.
[1529.70 --> 1531.32]  Well, they need a Taco Copter response, clearly.
[1531.56 --> 1534.10]  I mean, they have the host of a party to thank.
[1534.24 --> 1535.66]  It's also predictable now.
[1537.08 --> 1537.62]  That's great.
[1537.72 --> 1539.28]  So what were you building at the time?
[1539.40 --> 1540.22]  What did that inspire?
[1540.58 --> 1540.70]  Oh, gosh.
[1541.12 --> 1546.66]  I was working on something completely unrelated that, in retrospect, was, like, never going to be a really easy business to start.
[1546.66 --> 1559.54]  But I had done some work in college on a project in my own free time to make, like, electronic components on the idea that I could, like, make electricity, like, more legible or, like, easier to understand.
[1559.68 --> 1567.96]  So anyway, it was one of a couple of things I ended up going off to try and start and was working on at the time.
[1568.48 --> 1568.82]  That's great.
[1569.14 --> 1571.48]  And so what was after that?
[1571.56 --> 1572.26]  What came next?
[1572.40 --> 1574.40]  Roughly nothing relevant for a little while.
[1574.40 --> 1583.32]  I was, you know, just doing electrical engineering stuff and getting more into sort of, like, in my job, like, understanding manufacturing better for, like, a couple years.
[1583.46 --> 1589.94]  I think I was, like, doing electronic circuit design and then, like, working on getting some other things shipped later at another company.
[1590.22 --> 1596.88]  And all of it was, like, I still thought the Taco Copter or, like, autonomous aircraft potential was pretty exciting.
[1596.88 --> 1604.00]  But the regulatory environment was just too, like, weird and unsettled that I didn't want to, like, take my career in that direction at the time.
[1604.00 --> 1604.48]  Interesting.
[1604.76 --> 1605.52]  And then so what changed?
[1606.00 --> 1608.08]  Well, we have drone regulations now.
[1608.24 --> 1612.02]  So, like, really, really honestly, like, is your podcast, like, a regulations podcast?
[1613.60 --> 1618.48]  No, no, but we are nerds and we will go deep on anything.
[1618.82 --> 1620.84]  Also, like, when did the regulations pass and why?
[1620.94 --> 1622.36]  Like, what made people, like, woke?
[1622.92 --> 1629.18]  I remember very clearly there was a congressional mandate to write drone regulations that was supposed to pass, I think, in September of 2015.
[1629.18 --> 1629.82]  Oh, God.
[1629.82 --> 1630.78]  Date came and went.
[1631.10 --> 1632.60]  Something came out of it for a while.
[1632.70 --> 1641.52]  There was an exemption called Section 333, which is where you could be, like, I'm a very serious oil and gas company and we'd like to use this cutting-edge technology to, like, inspect our such and such.
[1641.58 --> 1643.74]  And you'd get these one-off approvals.
[1644.54 --> 1655.30]  A lot of people went into, like, data collection, which is, aka, taking photos with drones just for the purpose of, like, getting the exemption for, like, you know, whatever the early, like, photographing real estate companies.
[1655.30 --> 1668.14]  Then, after that, we got the rule that we have now, which is the USFAA's Part 107, which actually created a provision that allows you to fly commercially and collect money for your work, which, you know, before that was just kind of a gray area.
[1668.54 --> 1669.66]  And I think that was 2017.
[1670.02 --> 1671.30]  So, like, it's all that's coming together.
[1671.42 --> 1672.34]  So, what does that allow you to do?
[1672.44 --> 1675.46]  If you've got a drone, what can you do with it?
[1675.54 --> 1678.12]  And what kind of businesses can you build on autonomous aircraft?
[1678.12 --> 1682.76]  Yeah, you can fly no higher than 400 feet above the ground.
[1682.96 --> 1688.70]  Or, sorry, not above the ground, above the surface, which, you know, includes above, like, the top of the structure.
[1688.70 --> 1689.10]  Right, okay.
[1689.32 --> 1694.48]  You can fly within visual line of sight and you are allowed to get paid for your work.
[1694.58 --> 1697.40]  You may not fly over people who haven't given consent.
[1698.42 --> 1699.78]  Oh, because photos, right?
[1699.98 --> 1700.30]  Right.
[1700.42 --> 1701.58]  Yeah, largely the work is photos.
[1701.58 --> 1704.92]  And I'm pretty sure it's pretty explicit still.
[1705.06 --> 1708.42]  You may not move any cargo for hire, just saying.
[1708.72 --> 1709.08]  All right.
[1709.28 --> 1709.56]  Cargo.
[1709.76 --> 1714.62]  So, those being legal documents or serving people, that would not work here now.
[1714.76 --> 1714.98]  Yeah.
[1715.22 --> 1715.98]  Oh, that's a bummer.
[1716.10 --> 1718.16]  We may not classify the lobster as cargo.
[1718.62 --> 1719.14]  Yeah.
[1719.48 --> 1720.46]  It's a passenger.
[1720.70 --> 1721.08]  It's a passenger.
[1721.08 --> 1724.20]  I strongly advise against trying to skirt FAA regulations.
[1725.88 --> 1730.74]  And so, were you working with regulatory bodies to try to figure out what the right way to regulate this was?
[1730.74 --> 1733.38]  Or was it, I guess, there were other folks in the industry that were trying to figure all this out?
[1733.56 --> 1735.22]  Yeah, and it's an ongoing conversation.
[1735.54 --> 1742.28]  You know, I think it's interesting that as a, even as a young person, you were accepting the need for regulation.
[1742.76 --> 1744.84]  What's it like as a technologist to have to go deal with regulation?
[1745.00 --> 1746.88]  I think this is a very interesting question.
[1747.18 --> 1753.96]  You know, I originally, because I got into, like, the circuits thing, I think it was very clear to me that, you know, best practices are a thing to know about.
[1753.96 --> 1759.88]  And I just felt like, you know, early on when I was young, that there ought to be something that I didn't know how it worked yet.
[1759.88 --> 1768.78]  And so, you know, maybe I was a little timid at the time, but that was my outlook was informed by the, you know, professional standards of, you know, more the electrical engineering side.
[1769.32 --> 1769.42]  Right.
[1769.54 --> 1772.56]  That you've got a, that there should be a prescribed best practice.
[1772.68 --> 1774.38]  There should be a prescribed way to do things better.
[1774.90 --> 1775.10]  Yeah.
[1775.12 --> 1779.30]  I think that that was, you know, my sense, my understanding, my outlook of how the world worked.
[1779.72 --> 1780.18]  That's great.
[1780.66 --> 1781.68]  So it's very enlightened.
[1781.68 --> 1783.02]  I have to say, especially for, I mean.
[1783.28 --> 1783.56]  Jeez.
[1783.80 --> 1783.92]  Yeah.
[1784.32 --> 1786.02]  I cannot accept that adjective.
[1786.52 --> 1790.06]  I feel like you only come to, you often come to that the hard way, I think.
[1790.14 --> 1792.78]  From learning the lesson of whatever it was that needed to be.
[1792.96 --> 1797.00]  Well, if you knew me as like a little kid, you would know I learned a lot of lessons the hard way.
[1797.48 --> 1797.70]  Okay.
[1797.76 --> 1799.06]  That's, we want to hear more about those.
[1799.12 --> 1803.24]  We're going to take a quick break, but we will be right back with more Star Simpson on the metal.
[1803.24 --> 1809.28]  On the metal is brought to you by the Oxide Computer Company.
[1809.64 --> 1810.64]  Well, bad news.
[1810.80 --> 1812.50]  I just got back from a meeting with the attorneys.
[1812.68 --> 1812.98]  Oh boy.
[1813.16 --> 1815.86]  They are not going to let us say much in these ads.
[1816.32 --> 1820.50]  We can't talk about the customer experience today for on-premises infrastructure.
[1821.02 --> 1824.90]  So we can't do my idea to be like, are you being gaslit by your vendors?
[1825.04 --> 1826.22]  Because that's what they're doing.
[1826.22 --> 1832.16]  They're gaslighting people into thinking that these bugs only exist on one of their machines when it exists on like everyone's.
[1832.36 --> 1832.64]  God, no.
[1832.64 --> 1834.86]  They called that, I think, quote, a third rail.
[1835.18 --> 1836.40]  They must be following Jess on Twitter.
[1836.52 --> 1838.86]  I knew that that was a bad idea to let the lawyers follow Jess on Twitter.
[1839.82 --> 1843.38]  They also said we can't talk about public cloud customer experience.
[1843.86 --> 1844.24]  Oh, come on.
[1844.26 --> 1845.92]  We can't talk about the rapacious bandwidth pricing?
[1846.02 --> 1847.06]  I mean, it's practically criminal.
[1847.30 --> 1847.48]  No.
[1847.68 --> 1849.28]  Can't talk about the unit economics of that at all.
[1849.28 --> 1851.50]  Can we use the word criminal with respect to public cloud vendors?
[1851.96 --> 1852.62]  Definitely not.
[1852.72 --> 1853.08]  Oh boy.
[1853.20 --> 1853.92]  What can we do?
[1854.38 --> 1857.86]  Well, they did say, they gave us a statement we can use, which is-
[1857.86 --> 1858.52]  Are you going to read from it?
[1858.52 --> 1863.78]  Oxide Computer Company is building something that should help some people.
[1864.20 --> 1864.44]  Wow.
[1864.48 --> 1865.70]  That seems very direct.
[1865.86 --> 1866.28]  Come on.
[1866.38 --> 1868.18]  Can we at least send them over to oxide.computer?
[1868.30 --> 1868.70]  We can.
[1868.94 --> 1869.34]  We can.
[1869.46 --> 1872.60]  The other bit of bad news is all the lawyers were there in the meeting.
[1872.74 --> 1873.36]  Oh, wait a minute.
[1873.74 --> 1875.50]  Not just the cheap one, but the expensive one?
[1875.82 --> 1876.04]  Yeah.
[1876.12 --> 1876.62]  They were all there.
[1876.62 --> 1878.68]  So we paid a fortune to get this terrible ad.
[1878.68 --> 1879.36]  Oh my God.
[1879.54 --> 1883.06]  Please, listener, go to oxide.computer and learn what we're actually doing.
[1887.24 --> 1887.82]  All right.
[1887.84 --> 1888.34]  We're back.
[1888.64 --> 1890.36]  We're talking about lessons learned the hard way.
[1890.46 --> 1891.94]  We love lessons learned the hard way.
[1892.08 --> 1893.34]  What were some of the lessons you learned the hard way?
[1895.12 --> 1900.04]  Well, no parent gets a guide to parenting, but if you were to be able to write one for
[1900.04 --> 1905.22]  me in retrospect, it would include, don't tell me, star, don't tell little star not
[1905.22 --> 1907.90]  to mix electricity and water and not provide any explanation.
[1907.90 --> 1909.38]  Whoa, that's scary.
[1910.54 --> 1911.02]  Precisely.
[1911.20 --> 1911.40]  Okay.
[1911.52 --> 1912.56]  So you lived.
[1913.02 --> 1913.60]  I did.
[1913.84 --> 1914.10]  I did.
[1914.28 --> 1914.52]  Thank God.
[1916.12 --> 1916.90]  Spoiler alert.
[1917.02 --> 1917.74]  Spoiler alert.
[1917.86 --> 1918.28]  You're alive.
[1918.40 --> 1919.08]  So what happened?
[1919.26 --> 1923.28]  Oh, I mean, I did a bunch of things that were extremely dumb, but like largely due to
[1923.28 --> 1927.44]  like having asked when told that I was, I asked why not?
[1927.80 --> 1930.42]  And I was just told, well, just don't do it.
[1930.60 --> 1937.18]  And so everything from, I remember collecting like an enormous quantity of dead AA or C batteries
[1937.18 --> 1937.58]  actually.
[1937.82 --> 1941.56]  I think I remember like harvesting them out of the stereo after I ran out.
[1942.16 --> 1947.50]  And when I had enough to, so you have to picture this in your mind, picture like this
[1947.50 --> 1950.40]  like barrel battery, like the alkaline battery format, right?
[1950.60 --> 1952.32]  It's, it's a cylinder, right?
[1952.32 --> 1958.62]  And so if you want to make a circuit of batteries so that like, you're going to connect two batteries
[1958.62 --> 1961.94]  contacts to each other and another one and another one, and you're just going to add
[1961.94 --> 1966.14]  a little bit of angle until it makes a big loop because I know about the idea of circuits.
[1966.26 --> 1967.60]  That's a lot of batteries.
[1967.96 --> 1968.96]  That's a huge amount of batteries.
[1968.96 --> 1970.32]  Especially the C ones are very chunky.
[1970.40 --> 1970.56]  Yeah.
[1970.60 --> 1971.26]  They're very chunky.
[1971.44 --> 1971.64]  Yeah.
[1971.82 --> 1974.84]  So I collected enough that I could make a circle out of batteries.
[1975.48 --> 1978.24]  You know, it's like a, like a magic rune or something.
[1978.24 --> 1980.90]  Like I was like, I don't know, but the circle seems like an important shape.
[1981.16 --> 1982.00]  It's like a power wheel.
[1982.30 --> 1982.58]  Exactly.
[1982.82 --> 1983.90]  I was like, I've got to see what happens.
[1984.06 --> 1987.18]  And I collected all these batteries and I was like laying them out on the carpet and
[1987.18 --> 1991.40]  like making a little like divot in the carpet fabric to like get the battery not to roll
[1991.40 --> 1991.98]  and like all this.
[1992.14 --> 1996.24]  And like, I was like just a few battery lengths short of being able to complete it.
[1996.32 --> 1996.54]  Right.
[1996.64 --> 1999.12]  And I was like, oh, I'm so close.
[1999.66 --> 2001.74]  I'm going to get a conductive materials.
[2001.84 --> 2005.58]  I'm kind of like a, like a paper clip and I unbent a paper clip and I was like, I'm almost
[2005.58 --> 2006.96]  going to connect it.
[2007.04 --> 2011.10]  And as soon as I'd connected that like unbent paper clip wire across it, it like glowed
[2011.10 --> 2012.24]  orange and white hot.
[2012.32 --> 2012.56]  Right.
[2012.56 --> 2014.24]  And I'm holding it between my little fingers.
[2014.46 --> 2014.76]  Oh my God.
[2014.84 --> 2015.34]  Oh my God.
[2015.38 --> 2015.66]  Oh my God.
[2015.66 --> 2015.92]  Oh my God.
[2015.92 --> 2015.94]  Oh my God.
[2015.94 --> 2016.20]  Oh my God.
[2016.20 --> 2016.30]  Oh my God.
[2017.02 --> 2018.36]  So that happened.
[2018.98 --> 2020.04]  That is terrifying.
[2020.48 --> 2020.54]  Yeah.
[2020.60 --> 2024.18]  So I mean, I would assume if you, because you probably had like 30 C batteries.
[2024.32 --> 2024.88]  Something like that.
[2024.88 --> 2025.68]  That's got to be enough.
[2025.68 --> 2025.90]  That's right.
[2025.90 --> 2026.94]  I mean, it's definitely enough to start a fire.
[2026.94 --> 2028.32]  Nearly dead batteries.
[2028.66 --> 2028.76]  Yeah.
[2028.80 --> 2029.78]  I just, it glowed.
[2029.78 --> 2032.18]  And then I like threw the paper clip, of course.
[2032.34 --> 2035.46]  Fortunately, I think the air was able to cool it before it like hit the ground.
[2035.58 --> 2037.88]  And then my fingers had like two stripes across them.
[2038.50 --> 2039.66]  Secondary degree burns.
[2039.86 --> 2040.26]  Oh yes.
[2040.42 --> 2040.60]  Yes.
[2041.36 --> 2045.28]  Now, did you have the thought process of like, now that would be a lot more fun with much
[2045.28 --> 2045.88]  bigger batteries.
[2046.38 --> 2046.64]  Ooh.
[2047.12 --> 2051.44]  I guess my take was like, okay, now I know what happens on that one.
[2051.58 --> 2052.88]  God, that is such a great way.
[2052.92 --> 2055.46]  I feel like I don't, I never learned the lesson that easily.
[2055.56 --> 2057.40]  I've always got to be like, all right, let's make it like much bigger.
[2057.40 --> 2058.56]  It was not the only one.
[2058.90 --> 2060.16]  It was not the only time.
[2061.10 --> 2061.42]  All right.
[2061.50 --> 2061.82]  So, well, yeah.
[2062.54 --> 2063.28]  What next?
[2063.68 --> 2067.34]  I mean, I really, in retrospect, I think like scary one, dumb one that fortunately didn't
[2067.34 --> 2070.44]  turn out worse was, I also knew that lightning was electricity.
[2070.44 --> 2074.94]  And I remember my mom was like, yeah, lightning, metal and water is bad.
[2074.94 --> 2076.90]  And so like, I was like, but what happens?
[2077.00 --> 2083.02]  And so we're taking our entire recycling out to the yard and like during a thunderstorm
[2083.02 --> 2084.94]  just standing around waiting to see.
[2084.94 --> 2085.06]  Yeah.
[2085.06 --> 2085.20]  Okay.
[2085.20 --> 2085.70]  All right.
[2085.76 --> 2085.92]  Yeah.
[2085.92 --> 2086.08]  Yeah.
[2086.08 --> 2086.36]  Yeah.
[2086.36 --> 2086.68]  All right.
[2086.72 --> 2089.04]  Time to explain to start how this thing works.
[2090.04 --> 2091.54]  It needed a better explanation.
[2091.54 --> 2094.04]  You need to know why.
[2094.44 --> 2095.54]  I did need to know why.
[2095.66 --> 2096.50]  I needed to know why.
[2096.58 --> 2098.70]  I was so disappointed that nothing happened.
[2099.70 --> 2099.96]  Okay.
[2100.00 --> 2100.46]  Thank God.
[2100.62 --> 2100.82]  Wow.
[2100.90 --> 2101.06]  Yeah.
[2101.84 --> 2103.26]  I'm so sorry to my mom.
[2103.52 --> 2103.68]  Yeah.
[2103.76 --> 2103.90]  That's right.
[2104.06 --> 2104.68]  Oh, yeah.
[2104.84 --> 2105.16]  I know.
[2105.22 --> 2105.52]  We're all.
[2105.62 --> 2107.10]  And to be clear, I was like six.
[2107.30 --> 2111.08]  You know, well now I'm much more appreciative of your plush electronics.
[2111.32 --> 2111.56]  Right.
[2111.56 --> 2114.84]  This is a real problem in people's lives that I was trying to solve.
[2114.84 --> 2117.08]  And I saw that.
[2117.38 --> 2118.74]  So, uh, Canada do.
[2119.34 --> 2120.54]  That's the name of the, yep.
[2120.60 --> 2124.52]  The company we made to, uh, be a kit for learning about electronics.
[2124.80 --> 2124.98]  Yeah.
[2124.98 --> 2125.82]  It looked really interesting.
[2126.12 --> 2126.44]  Thank you.
[2126.48 --> 2131.00]  And certainly with kids that are under the age of six, I'm much more predisposed to trying
[2131.00 --> 2134.40]  to get those in their hands versus the, all the batteries starting to disappear in
[2134.40 --> 2134.72]  the house.
[2135.22 --> 2135.62]  Yeah.
[2135.62 --> 2139.76]  I had a bunch of theories about why it'd be good to make like large directly representational
[2139.76 --> 2141.68]  objects that could like let you tinker.
[2142.00 --> 2145.14]  I was also definitely scratching a very like fresh itch of my own.
[2145.26 --> 2145.40]  Yeah.
[2145.56 --> 2145.68]  Right.
[2145.78 --> 2147.46]  Well, I'm glad that didn't turn out worse.
[2147.84 --> 2148.00]  Right.
[2148.00 --> 2149.22]  What's the right way to do this?
[2149.30 --> 2150.62]  You know, um, how old are you kids?
[2151.10 --> 2152.46]  Uh, two, three and five.
[2152.60 --> 2153.24]  Oh my goodness.
[2153.64 --> 2156.24]  So the five-year-old's trying to get excited about electronics.
[2156.38 --> 2156.72]  Oh, nice.
[2156.84 --> 2159.20]  It's very pleasing ages from a Fibonacci perspective.
[2159.54 --> 2159.64]  Yeah.
[2160.20 --> 2160.56]  Yeah.
[2160.70 --> 2161.02]  That is.
[2161.14 --> 2162.02]  That's so true.
[2162.30 --> 2162.60]  It's true.
[2162.60 --> 2162.80]  Yeah.
[2162.94 --> 2165.04]  Steve Fortree does not have two one-year-olds to go with it.
[2165.04 --> 2166.56]  That's what he would need.
[2167.14 --> 2170.46]  Uh, yeah, I think that the five-year-old, I think it'd be safely trusted with electronics,
[2170.46 --> 2173.54]  but the, uh, I think, I don't know how you're Andrew.
[2173.80 --> 2177.52]  No, she had her first set started to play around with, uh, you know, taking a battery,
[2177.64 --> 2181.12]  getting a loop created, getting a wheel flying and that's awesome.
[2181.20 --> 2181.82]  Little pinwheel.
[2182.24 --> 2186.44]  Her first starter set way more useful than just like straight waste heat through a paper
[2186.44 --> 2186.76]  clip.
[2188.40 --> 2188.80]  Yeah.
[2188.80 --> 2191.48]  I might've connected a circuit with a paper clip myself back in the day.
[2191.68 --> 2193.46]  Saw the same white hot reaction.
[2193.46 --> 2197.60]  Um, I recall as playing with the paper clip, it's around the outlet that, that, that, that
[2197.60 --> 2198.40]  gets the attention.
[2198.52 --> 2199.00]  That's what I do.
[2199.14 --> 2199.68]  Yeah, exactly.
[2199.78 --> 2201.94]  That's the one that just make sure they're in the same hand.
[2202.02 --> 2203.08]  So you don't have it in two hands.
[2203.14 --> 2204.68]  That's the keep one hand in your pocket.
[2204.78 --> 2206.04]  That's my father's fun.
[2206.04 --> 2209.92]  I'm really jealous of kids who can look up what happens when you mix electricity with various
[2209.92 --> 2210.56]  things on YouTube.
[2210.56 --> 2214.20]  Now it's like, uh, if any kids are listening to this, it's, it's a whole other world.
[2214.20 --> 2216.42]  It is, but then they want to replicate it.
[2216.42 --> 2216.70]  They want it.
[2216.78 --> 2216.92]  Yeah.
[2217.58 --> 2218.34]  They want to.
[2218.48 --> 2220.88]  That didn't stop me from wanting to do this scissor lift thing.
[2220.94 --> 2223.98]  I was just going to say, because you didn't look up scissor lift accidents.
[2224.20 --> 2225.42]  I looked up tutorials.
[2225.64 --> 2225.90]  Yes.
[2226.12 --> 2226.32]  Right.
[2226.54 --> 2226.70]  Yeah.
[2226.70 --> 2229.54]  You need to Google accidents and then your disposition changes a little bit.
[2229.88 --> 2234.66]  So in terms of learning lessons as an engineer, when you were further along in terms of the,
[2234.66 --> 2239.86]  with aeronautical software, with, with, with avionics, obviously the failure modes are much
[2239.86 --> 2241.26]  more acute or can be.
[2241.56 --> 2245.18]  How do you deal with those kinds of problems and making sure that I'm sure you've had some,
[2245.22 --> 2246.04]  some horror stories.
[2246.46 --> 2247.72]  I actually don't have horror stories.
[2247.72 --> 2252.78]  I think that safety critical engineering is a like really good topic that I'm glad to live
[2252.78 --> 2256.04]  in an era where a lot of people have made a lot of discoveries and there are good lessons
[2256.04 --> 2257.14]  available to be learned.
[2257.40 --> 2260.12]  I'm also a like full scale glider pilot now.
[2260.20 --> 2264.64]  So I fly planes that don't have engines, which pretty esoteric hobby, but a really reward
[2264.66 --> 2269.04]  it's like a really beautiful, you know, to go way to go experience nature.
[2269.22 --> 2269.48]  Yeah.
[2269.50 --> 2270.06]  It must be amazing.
[2270.06 --> 2271.88]  Cause it's, it must be, it's so quiet.
[2272.30 --> 2272.58]  Yeah.
[2272.66 --> 2277.42]  But it's brought me into contact with like, you know, talking to other people in aviation
[2277.42 --> 2282.52]  and sort of, there's a lot of effort put into like understanding what goes wrong, why
[2282.52 --> 2284.86]  things go wrong and how to mitigate those things.
[2285.00 --> 2289.70]  So I've just got to ask you about 737 max then what your take is on, I mean, it's, it's
[2289.70 --> 2292.46]  such an interesting fiasco.
[2292.46 --> 2297.38]  How does one avoid in one's developing one's own software?
[2297.84 --> 2302.62]  I'd say as a software engineer, I look at the 737 max and I'm like, I feel that this
[2302.62 --> 2308.12]  is like a move fast, break things culture infecting an aircraft company, which is a very
[2308.12 --> 2308.62]  bad idea.
[2308.94 --> 2310.26]  I'm not sure about that.
[2310.34 --> 2315.18]  And I'm actually slightly reticent to comment on the max specifically because, you know,
[2315.20 --> 2317.40]  I feel that I'm maybe one among the peanut gallery.
[2317.54 --> 2318.70]  I couldn't have as much information.
[2318.70 --> 2321.06]  Oh, you're the, we're all in the peanut gallery on this, aren't we?
[2321.22 --> 2321.54]  Fair enough.
[2321.54 --> 2321.86]  Yeah.
[2321.86 --> 2324.60]  I mean, feel like that doesn't let, doesn't stop me anyway.
[2324.82 --> 2325.36]  Fair enough.
[2325.48 --> 2329.14]  I mean, I think it's obviously an enormous tragedy and.
[2329.14 --> 2333.28]  you know, I can't really feel anything besides completely heartbroken that it happened.
[2333.56 --> 2337.96]  And I think that, you know, pretty intense lessons have been learned that I continue to,
[2338.16 --> 2343.48]  you know, I hope will continue to impact, you know, the world of aviation where it's, you
[2343.48 --> 2347.50]  know, people, you know, travel are in the hands of the people doing the engineering.
[2347.66 --> 2348.24]  I know it will.
[2348.34 --> 2349.00]  It already has.
[2349.00 --> 2354.54]  Well, I think the kind of the irony is that when we first started using software in safety
[2354.54 --> 2359.16]  critical roles, there was a lot of concern that we would have software related defects
[2359.16 --> 2360.94]  that would cause loss of life.
[2361.62 --> 2364.24]  And it basically wasn't true for a long time.
[2364.32 --> 2364.48]  We did.
[2364.56 --> 2368.26]  You can't really, I mean, there was the Airbus crash at the Paris air show, but there basically
[2368.26 --> 2371.14]  was not a lot of software.
[2371.58 --> 2375.06]  Software was not at root for loss of life, loss of property.
[2375.06 --> 2382.20]  And it's, it's interesting that, I mean, and as you say, tragic, that when we really
[2382.20 --> 2387.32]  should know much better, we now have software has begun to emerge as a failure mode here.
[2387.48 --> 2389.36]  I mean, it's obviously much more complicated than software.
[2389.48 --> 2391.28]  There's a whole bunch of things that broke down there.
[2391.74 --> 2397.30]  Well, one thing I do see here is that we are at the cusp of a new era in aviation.
[2397.30 --> 2403.74]  I think where, you know, we've been increasing the level of, you know, sort of classic automation,
[2403.74 --> 2409.02]  which are like tools to reduce pilot workload, which is, you know, sort of making things
[2409.02 --> 2412.64]  slightly more automated or having slightly more software, you know, involved.
[2412.86 --> 2418.98]  But I think that, you know, so too, as we're seeing a lot of debate about how to roll out
[2418.98 --> 2425.58]  maybe self-driving vehicles elsewhere, I think that there's a, there's a level of autonomy in
[2425.58 --> 2433.74]  flying gadgets that I want to see the opportunity to field in test and field in use in a risk
[2433.74 --> 2434.66]  mitigated way.
[2434.78 --> 2435.00]  Yeah.
[2435.24 --> 2437.76]  You know, I think, I think we actually need to do more work.
[2438.12 --> 2438.52]  Absolutely.
[2438.84 --> 2441.90]  Because it's not happening right now in, in, in vehicles, certainly.
[2442.06 --> 2442.36]  I mean.
[2442.64 --> 2443.10]  Is that so?
[2443.16 --> 2443.68]  I'm not familiar.
[2443.74 --> 2446.66]  Well, I mean, I, from my perspective, I mean, the fact that you've got this thing that is,
[2446.76 --> 2449.26]  that is called an autopilot that is clearly not an autopilot.
[2449.26 --> 2452.80]  I must be in a bubble because all I hear about is like how to deal with the safety
[2452.80 --> 2453.74]  critical factors.
[2453.86 --> 2456.86]  Well, no, I mean, I think that just in terms of the Tesla autopilot, Tesla autopilot is
[2456.86 --> 2457.52]  not an autopilot.
[2457.70 --> 2459.36]  But it is actually really good.
[2459.52 --> 2460.98]  Having like written in one, it's like really good.
[2460.98 --> 2462.06]  I don't know so much about that.
[2462.24 --> 2464.44]  The problem is it's not an autopilot, right?
[2464.54 --> 2465.02]  Okay, fair, fair.
[2465.40 --> 2466.20]  It's a pilot assist.
[2466.36 --> 2466.56]  Yeah.
[2467.12 --> 2469.88]  Autopilot being something where like you can just go to sleep.
[2470.02 --> 2470.78]  It is not self-driving.
[2471.00 --> 2471.46]  Yeah, exactly.
[2471.82 --> 2472.74]  It's not self-driving.
[2472.92 --> 2475.30]  And it's like, well, if you read all of the fine print, it's not self-driving.
[2475.40 --> 2476.56]  It's like, you call it an autopilot.
[2476.56 --> 2480.50]  I'm really into bicycles, so please all of you don't sleep in your car while it's
[2480.50 --> 2480.96]  moving.
[2481.14 --> 2481.36]  Right.
[2481.64 --> 2484.72]  And don't play video games and don't read newspapers.
[2484.96 --> 2485.14]  Yep.
[2485.32 --> 2490.02]  But I mean, I think the use case that people appreciate about it is when they're in like
[2490.02 --> 2495.10]  bumper to bumper traffic and the vehicle will actually move forward and stop.
[2495.10 --> 2499.06]  Can we move to sort of like a clean sheet view of like, here's what I want.
[2499.18 --> 2499.44]  Okay.
[2499.58 --> 2504.72]  I'm into the idea of autonomy in vehicles, but I don't think I really need it to get me around
[2504.72 --> 2505.12]  town.
[2505.40 --> 2505.58]  Yep.
[2505.58 --> 2508.64]  The place I want it because I live in LA and I've come up to the Bay area.
[2508.74 --> 2509.58]  I've driven a few times.
[2509.72 --> 2513.36]  I just want like a tractor front end that I can like attach to my car.
[2513.40 --> 2515.06]  That's just going to take me up by five.
[2515.16 --> 2516.42]  It doesn't need to do anything.
[2516.50 --> 2518.62]  No turns doesn't need anything specific.
[2518.84 --> 2522.56]  I just want the long haul to be so much more sense.
[2522.56 --> 2523.00]  Yeah.
[2523.00 --> 2526.78]  I mean, there's a romantic allure to replacing humans.
[2527.24 --> 2529.34]  And so we want to replace them everywhere.
[2529.34 --> 2531.26]  But yeah, it's the long haul up I-5.
[2531.56 --> 2536.58]  And that's also where you can commercially, for commercial trucking, it's like you actually
[2536.58 --> 2538.28]  don't want someone who's sleep deprived at the wheel.
[2538.40 --> 2539.04]  You want someone.
[2539.16 --> 2540.54]  I mean, it makes a lot of sense.
[2540.72 --> 2544.14]  Plus, there's less factors like bicyclists, humans, crossing the street, whatever.
[2544.50 --> 2544.58]  Yeah.
[2544.68 --> 2545.98]  But you're back to sleeping in the cab.
[2546.16 --> 2547.42]  But there you could actually solve the problem.
[2547.54 --> 2551.54]  Like you can solve the problem on the, you know, from the grapevine to Tracy, right?
[2551.58 --> 2551.70]  Yep.
[2551.88 --> 2552.86]  You can solve that problem.
[2553.06 --> 2554.48]  Like that is actually a solve.
[2554.58 --> 2554.90]  That feels-
[2554.90 --> 2558.04]  Well, that is where autonomous trucking, a lot of the difference are right now.
[2558.06 --> 2558.30]  It is.
[2558.40 --> 2561.46]  But I feel like we are not culturally focusing on that use case enough.
[2561.80 --> 2566.18]  Hey, it came to mind as one where I think it would be a pretty direct hit in terms of like
[2566.18 --> 2567.34]  convenience in my life.
[2567.50 --> 2571.00]  And, you know, one that I'd be pretty into, you know, and I don't even care if it's like
[2571.00 --> 2572.54]  my car with its wheels on the road.
[2572.62 --> 2575.96]  I mean, put me on one of those, like, what's the, like, the truck that you're
[2575.98 --> 2579.72]  that carries all the, like a car, you know, or like maybe this ultimately devolves a little
[2579.72 --> 2581.14]  bit into being kind of like a train.
[2581.36 --> 2581.54]  A ferry.
[2581.72 --> 2587.18]  You know, like I'd get off the car and like, you know, they have these semis that get linked
[2587.18 --> 2591.62]  up into these really long assemblies in Western Australia where there are not a lot of people
[2591.62 --> 2594.76]  or road hazards that they call like truck trains, you know, like you could have like
[2594.76 --> 2597.38]  a car for the people and then the car for the cars.
[2598.28 --> 2601.62]  Well, so this is a really interesting point that you're making about, about meeting the
[2601.62 --> 2607.12]  world where it is, as opposed to demanding that one change the world around particular
[2607.12 --> 2610.34]  innovation, you know, because what you're basically saying is like, look, we're not going to,
[2610.78 --> 2613.88]  we don't need to replace humanity for all personal transportation.
[2614.06 --> 2614.96]  I don't know if we are or aren't.
[2615.02 --> 2616.64]  I can't make a strong statement about that.
[2616.82 --> 2621.02]  I just admire, like, let's just see how we can make the world actually, how we can improve
[2621.02 --> 2622.48]  it as opposed to.
[2622.76 --> 2623.02]  Yeah.
[2623.16 --> 2626.96]  I think you called me an optimist earlier, but I think I'm a bit of an optimizer, right?
[2626.96 --> 2630.08]  Like, kind of, kind of, uh, what's the word?
[2630.12 --> 2630.80]  Like kind of exhausting.
[2631.04 --> 2635.00]  I'm like, you know, this, this thing could be slightly better in this one particular way.
[2635.02 --> 2636.34]  And people are like, star, it's fine.
[2636.38 --> 2636.96]  It works.
[2637.44 --> 2638.88]  You know, move on.
[2639.16 --> 2639.48]  Okay.
[2639.56 --> 2643.02]  Can you, so sure you've got some stories of some things that you obsessively optimized
[2643.02 --> 2644.54]  when everyone else thought it was good enough.
[2645.08 --> 2646.14]  We love optimizing.
[2647.08 --> 2648.86]  Jess will definitely want to hear some if you want to.
[2649.00 --> 2652.00]  I'm going to throw this out there in the category of things that were like too much work,
[2652.02 --> 2653.78]  but that were like an awesome vision.
[2653.78 --> 2657.76]  Like I remember once I thought I was going to get really into drafting, which is a particular
[2657.76 --> 2661.84]  type of drawing that like you draw 3d objects with perspective as they are.
[2662.26 --> 2665.80]  And I, you know, in order to practice my drafting skills and in order, because I was
[2665.80 --> 2672.66]  on a kick at the time about like transparent interfaces, I sat in my kitchen and I drew drawings
[2672.66 --> 2674.56]  of the contents of every cabinet.
[2674.72 --> 2679.08]  And then I put those drawings on the front of the cabinet so that you could sort of see
[2679.08 --> 2680.40]  what was in the game.
[2680.40 --> 2687.10]  It was like a tangible label with no text, you know, no, like internationalized by default,
[2687.22 --> 2688.50]  you know, and it was really ridiculous.
[2688.62 --> 2691.58]  But like people were like, yeah, the first see-through refrigerator.
[2691.78 --> 2695.14]  It was like, you could have just used glass, but you know, and I'd press people and be like,
[2695.16 --> 2695.66]  is it better?
[2695.72 --> 2697.12]  And they're like, yeah, it's a sure.
[2697.96 --> 2698.54]  That's dope.
[2698.84 --> 2699.42]  That is great.
[2699.50 --> 2701.14]  That's a total over-optimization.
[2701.44 --> 2701.66]  Great.
[2701.86 --> 2702.04]  Yeah.
[2702.04 --> 2704.72]  I can see that you would, people walk in, you'd be like, look at this.
[2704.76 --> 2705.32]  Isn't this amazing?
[2705.38 --> 2706.78]  People are like, is everything okay?
[2706.78 --> 2708.16]  I just want to make sure that like.
[2708.80 --> 2712.36]  Now I don't have to give you a like rundown on how the kitchen works.
[2712.36 --> 2713.34]  You can see for yourself.
[2713.40 --> 2714.62]  You don't have to search through drawers.
[2715.22 --> 2715.72]  That is great.
[2715.80 --> 2720.28]  And I think taking, I mean, kind of taking a fresh approach is so important for so many
[2720.28 --> 2721.34]  of these, of these problems.
[2721.64 --> 2721.84]  Yeah.
[2721.88 --> 2726.02]  I think I maybe have learned to tone down or focus my targets a little better.
[2726.60 --> 2728.66]  I feel like toning down should not happen.
[2728.96 --> 2729.46]  I agree.
[2729.60 --> 2729.72]  Yeah.
[2729.74 --> 2730.92]  I think that you got to turn it up.
[2731.00 --> 2732.86]  You can't grow to say like, it's fine.
[2732.94 --> 2733.36]  It's okay.
[2733.36 --> 2734.46]  Like the kitchen's fine.
[2734.46 --> 2736.00]  Like go work on something.
[2736.00 --> 2740.58]  Someone who has like meticulously labeled every single cable that I own.
[2740.72 --> 2742.06]  Cables are really worth labeling.
[2742.36 --> 2743.22]  I totally agree.
[2743.40 --> 2746.12]  I mean, it's worth going above and beyond.
[2746.22 --> 2749.84]  I'm just saying like having the impulse and tying it to looking for something where you're
[2749.84 --> 2751.60]  going to get like a good reward for the average.
[2752.32 --> 2753.38]  That's my new thing.
[2753.66 --> 2753.90]  Yeah.
[2753.90 --> 2759.00]  I think that, that you should actually cultivate that, that kind of obsessiveness can be, I
[2759.00 --> 2763.84]  think, especially as one gets older, you temper that with wisdom, but that, that obsessiveness
[2763.84 --> 2764.36]  is great.
[2764.36 --> 2766.56]  That's that, that's such a, that's such an emotional power.
[2766.62 --> 2768.28]  Can you learn a lesson about obsessiveness here?
[2768.38 --> 2773.06]  Are there like positive, you know, targets that other people here have trained their obsession
[2773.06 --> 2773.44]  on?
[2773.44 --> 2776.82]  I feel like Jess is very positively obsessive.
[2777.02 --> 2777.22]  Yeah.
[2777.50 --> 2782.02]  And I like, just let it, I mean, I like, I, there is no shame when it comes to like labeling
[2782.02 --> 2782.46]  tables.
[2782.56 --> 2783.00]  No, no, no.
[2783.00 --> 2784.38]  Or organizing other shit.
[2784.46 --> 2785.72]  I mean, like, yeah.
[2786.12 --> 2790.00]  And I think it's, it's so terrific to appreciate the results of that.
[2790.08 --> 2793.98]  I'm also practical when it comes to other people not appreciating it.
[2793.98 --> 2796.32]  Like all appreciate it, but other people don't have to.
[2796.60 --> 2799.30]  I might force it upon you all at times.
[2799.32 --> 2799.78]  That's true.
[2799.96 --> 2804.48]  You know, I gotta say, I'm surprised that more people don't use more checklists in everyday
[2804.48 --> 2804.92]  life.
[2806.20 --> 2808.04]  You guys are all just stunned right now.
[2808.06 --> 2808.66]  No, no, no, no, no.
[2808.66 --> 2813.80]  No, I was just reflecting on, I use checklists for checklists, which is not very useful.
[2813.80 --> 2814.66]  Wait, how does that work?
[2814.66 --> 2817.90]  The end result of getting through the checklist of the checklist.
[2818.04 --> 2818.66]  You use checklists for checklists.
[2818.84 --> 2819.58]  But yes.
[2819.58 --> 2820.82]  Like, did we do the X checklist?
[2821.06 --> 2821.30]  Yeah.
[2821.56 --> 2823.50]  Kind of just need to like execute on the first checklist.
[2823.98 --> 2826.70]  I don't know how people survive without checklists, actually.
[2827.00 --> 2828.26]  Yeah, no, I'm a big checklist person.
[2828.46 --> 2831.84]  It's nice because it feels like you need that, like that positive reward that you're making
[2831.84 --> 2832.32]  progress.
[2832.60 --> 2832.78]  Yeah.
[2833.18 --> 2834.46]  Especially when you're working on a hard problem.
[2834.88 --> 2835.86]  So yeah, how do you use checklists?
[2835.86 --> 2839.12]  Well, I don't mean like to-do lists, but I mean, you know, like for simple stuff.
[2839.30 --> 2839.64]  Oh, fair enough.
[2839.64 --> 2839.96]  Okay.
[2840.10 --> 2842.00]  Because I was thinking of my to-do list for to-do lists.
[2842.00 --> 2846.04]  You're talking like in the aviation sense of like actually like making sure the flaps are
[2846.04 --> 2846.48]  down and.
[2846.82 --> 2847.92]  Yeah, that type of checklist.
[2848.20 --> 2848.56]  Like, you know.
[2848.56 --> 2849.04]  Yeah, yeah, yeah.
[2849.06 --> 2849.34]  Absolutely.
[2849.70 --> 2851.60]  So expand on that because I totally agree.
[2851.62 --> 2852.04]  Oh, I don't know.
[2852.04 --> 2855.88]  I mean, like I think probably the first one I really did was like packing checklist.
[2856.10 --> 2859.18]  Like if I traveled and I was like, oh, I really wish I had, you know, whatever.
[2859.30 --> 2862.12]  Then I actually kept running checklists for stuff like that.
[2862.12 --> 2863.92]  But I totally agree.
[2864.02 --> 2870.54]  And I, you know, early in my career, I felt frustrated that people would, we had a work
[2870.54 --> 2871.56]  on the operating system.
[2871.68 --> 2875.06]  People would break the operating system for preventable reasons.
[2875.06 --> 2880.42]  And it's like, why do we not have a checklist that has 45 things on it?
[2880.50 --> 2883.00]  And you've got to go check them all off before you actually integrate.
[2883.44 --> 2884.26]  So break that down for me.
[2884.30 --> 2885.64]  What do you mean break the operating system?
[2886.12 --> 2889.60]  So, I mean, with any complicated body of software, there's obviously lots of things
[2889.60 --> 2890.74]  that you have to remember, right?
[2890.76 --> 2891.90]  Lots of things you have to keep track of.
[2891.94 --> 2892.54]  Did you test this?
[2892.60 --> 2893.24]  Did you test that?
[2893.32 --> 2894.20]  Did you test this other thing?
[2894.28 --> 2899.12]  Did you, have you thought about the ramifications of this or of that or of, and a lot of that
[2899.12 --> 2901.38]  just felt like it was exhaustive.
[2901.44 --> 2902.72]  There was just too much to remember.
[2903.34 --> 2905.58]  But a lot of it was, it was knowable.
[2905.78 --> 2907.86]  We can know this list and we could enumerate it.
[2908.04 --> 2908.46]  You can, yeah.
[2908.54 --> 2910.40]  So this is like software tests now.
[2910.46 --> 2910.62]  Right.
[2910.68 --> 2913.56]  I mean, if you, if you can know it and you can enumerate it, well, one, you should automate
[2913.56 --> 2913.82]  it.
[2914.00 --> 2918.46]  But even when you've got a human in the loop and you do, when you're integrating software,
[2918.56 --> 2919.50]  you have a human in the loop.
[2919.54 --> 2922.86]  A human is deciding like, it is time to integrate the software.
[2922.98 --> 2926.22]  And yes, you want to automate that to support it, but you need to know.
[2926.22 --> 2927.88]  And that's where our checklist, I think is.
[2927.88 --> 2929.24]  That's where I've used checklists.
[2929.24 --> 2931.42]  Do you actively regard tests as checklists?
[2931.68 --> 2932.26]  It could be.
[2932.66 --> 2932.78]  Yeah.
[2932.80 --> 2933.66]  I think it depends on, yeah.
[2933.74 --> 2934.12]  Do you?
[2934.36 --> 2936.14]  We ask the questions.
[2939.24 --> 2940.70]  Does this table not turn?
[2942.60 --> 2949.56]  I mean, I think in terms of like accumulating data about easy, preventable, simple mistakes,
[2949.56 --> 2956.38]  I really, really, really love procedural, you know, things to go through to see if you've
[2956.38 --> 2960.26]  done the right thing or, you know, one thing I'm really proud of, actually, we checklist
[2960.26 --> 2964.62]  really heavily at the company, you know, everything from like before takeoff to like
[2964.62 --> 2966.50]  even just building the aircraft.
[2966.78 --> 2966.96]  Yeah.
[2967.04 --> 2970.30]  And we just got through a build and like, finally, we've learned enough about doing this
[2970.30 --> 2975.68]  that like put it together, turned it on and like no fiddling, you know, like no, like,
[2975.74 --> 2977.32]  ah, is this like left or right?
[2977.32 --> 2978.56]  Or like, does this go up or down?
[2978.58 --> 2980.46]  And like, I was just like, nope, I followed the instructions.
[2980.46 --> 2981.42]  We turned it on.
[2981.52 --> 2982.00]  It worked.
[2982.22 --> 2983.92]  I'm like, so proud.
[2984.08 --> 2984.72]  That is great.
[2984.82 --> 2985.86]  So can you talk about the technical details?
[2985.98 --> 2986.76]  So what is your current company?
[2986.84 --> 2987.84]  What are you guys currently building?
[2988.14 --> 2989.54]  And yeah, talk about the technical details of that.
[2989.60 --> 2991.04]  I think that's a very important lesson.
[2991.22 --> 2996.06]  We build autonomous aircraft with the goal of forwarding goods and equipment, cargo,
[2996.46 --> 2998.34]  strictly with nobody on board.
[2998.72 --> 2999.18]  That's cool.
[3000.06 --> 3005.70]  So this is, I mean, this is the vision you've had for a long time to coming to real fruition.
[3005.78 --> 3006.36]  It's one of them.
[3006.36 --> 3011.14]  But it's the result of like a lot more in-depth thought about kind of what's valuable in aviation.
[3011.44 --> 3014.02]  What do aircraft kind of, what jobs do they have?
[3014.02 --> 3019.58]  Like, you know, looking at the object is kind of having its own role that like people find valuable to do.
[3019.62 --> 3022.62]  And then kind of looking at the edges and saying, so what aren't we doing right now?
[3022.62 --> 3025.80]  Because we can't, because of, you know, that changes when you go autonomous.
[3026.42 --> 3026.74]  Interesting.
[3026.86 --> 3029.48]  So yeah, what are some of the things that you found in terms of some of those opportunities?
[3029.48 --> 3045.30]  So we, the best way to model what we're doing is we're supporting additional operations that users who would otherwise interact with helicopters for moving cargo payloads might want done in a more efficient way.
[3045.80 --> 3047.82]  And you're building the aircraft to do that as well.
[3047.96 --> 3048.50]  We are.
[3048.76 --> 3049.26]  That's exciting.
[3049.26 --> 3052.08]  It's really the easiest way to prove out what we're doing.
[3052.70 --> 3061.40]  And so describe, so in terms of the, as you were developing the checklists and developing the kind of the platform for that, what were some of the engineering challenges that you had?
[3061.40 --> 3073.78]  Oh, I mean, so this is actually not uncommon in like a first build of an aircraft where, you know, you have aerodynamic control surfaces that have to like go up or down depending on whether you want to turn left or right.
[3073.78 --> 3080.08]  And for whatever reason, I find it pretty, you know, difficult to put myself in like the reference frame and say like, okay, this one's going up.
[3080.24 --> 3083.00]  That means that the counter reaction is like this thing's going down.
[3083.06 --> 3084.90]  So that means like, and then like, okay.
[3084.90 --> 3091.38]  And then like this way means turning that way, you know, like that's one of the ones where you have to get that.
[3091.40 --> 3091.80]  Right.
[3092.00 --> 3100.06]  And just making a visual checklist for that saved so much effort was so much better than just trying to work it out in your head every time.
[3100.06 --> 3100.22]  Right.
[3100.22 --> 3103.64]  Which is like, I think something that a checklist is exactly perfect for.
[3103.90 --> 3104.30]  Interesting.
[3104.30 --> 3109.56]  That makes a lot of sense because a lot of those are like, or at least with planes are super non-intuitive.
[3109.56 --> 3110.98]  It's the opposite that you would think.
[3111.08 --> 3115.90]  They might not be intuitive and it's just a million times better not to say, I think I got it right.
[3116.48 --> 3117.56]  That's, that's really cool.
[3118.12 --> 3120.90]  I mean, obviously you guys, you're engaged in safety, critical engineering.
[3121.40 --> 3131.88]  Well, we are involved in doing engineering with things that fly, but because we don't fly over people, we don't fly with people on board.
[3132.06 --> 3143.82]  You know, if we were to see it come down in test, that would probably just, you know, at best rumple the landing gear, not further damage other than something we could replace pretty easily.
[3144.00 --> 3144.60]  Oh, that's cool.
[3144.60 --> 3150.84]  But just your disposition though is, is so strongly towards, seems towards building safe things that I, I mean, I just contrast.
[3151.18 --> 3151.58]  Why not?
[3151.78 --> 3154.16]  I mean, like I'm sitting here, you know, writing a bash script or whatever.
[3154.16 --> 3156.96]  It's like the level of discipline is.
[3157.18 --> 3159.80]  I don't want a test to go badly for dumb reasons.
[3159.90 --> 3160.18]  Right, right.
[3160.18 --> 3160.54]  Of course.
[3160.68 --> 3161.08]  Basically.
[3161.30 --> 3162.86]  And so how do you prevent that?
[3162.92 --> 3166.18]  How do you have a culture that prevents that, a system that prevents that?
[3166.18 --> 3169.90]  I mean, I think that the phrase that I really love is to make haste slowly.
[3170.10 --> 3179.56]  This was a quote from like a, I think a Roman military leader, you know, it was like, you want to go as quickly as you can without being hasty, I think ultimately.
[3179.56 --> 3187.00]  And when you make dumb mistakes, you don't check your work with something that's going to leave the surface of the earth.
[3187.12 --> 3194.98]  It's pretty easy to not find out what you were trying to find out or not get the thing to work correctly as you hope for simple reasons.
[3194.98 --> 3196.44]  And I get, I'm so frustrated.
[3196.54 --> 3201.98]  There's so much work that goes into building anything that like, I want to say like, oh, okay.
[3201.98 --> 3206.60]  Like, you know, this big thing was as we expected, not like, well, who knows?
[3206.60 --> 3209.24]  It's because, uh, you know, left was right and right was left.
[3209.24 --> 3211.16]  Like it's a huge waste of time.
[3211.46 --> 3211.66]  Totally.
[3212.06 --> 3213.28]  How do you work up to that?
[3213.28 --> 3216.60]  So, you know, that the big thing, when it turns on, it's going to turn on correctly.
[3216.60 --> 3219.58]  I mean, you've got to have a lot of small things that you, that you test.
[3220.08 --> 3220.24]  Yeah.
[3220.24 --> 3229.16]  I would say this doesn't necessarily come naturally to me, but we have a pretty good practice of like capturing and documenting and building up the docs to support that as we go.
[3229.16 --> 3233.18]  And it just makes life so much better, so much more efficient.
[3233.50 --> 3235.40]  It lets us move so much more quickly.
[3235.40 --> 3238.22]  To have things well documented and communicated.
[3238.72 --> 3238.82]  Yep.
[3239.04 --> 3242.48]  So that, you know, the first time we built it, I was like, okay, this is what was tricky.
[3242.64 --> 3247.22]  So next time that's like clearly written about how, like how to navigate this little like narrows.
[3247.60 --> 3248.38]  Oh, interesting.
[3248.66 --> 3248.80]  Yeah.
[3248.94 --> 3253.28]  So is this, is this in the spirit of kind of technical documentation or more kind of experiential documentation?
[3253.44 --> 3263.28]  It's both technical documentation, it's pack lists and it's checklists for, you know, actual procedure and checklists for, you know, what data we're recording, if it needs to be manually recorded.
[3263.28 --> 3271.68]  And, you know, it's basically, I strive for this culture of efficient, you know, I don't want to use the word bureaucracy, but kind of like light touched, right?
[3271.70 --> 3275.56]  Like the procedure is meant to support getting the job done and no more.
[3275.92 --> 3276.24]  Right.
[3276.36 --> 3276.52]  Yeah.
[3277.00 --> 3278.98]  I mean, you want to make haste slowly, as you say.
[3279.04 --> 3283.98]  I mean, you want to be sure that you're rigorous and you're still moving at pace.
[3284.10 --> 3285.00]  Rigorous is a great word.
[3285.00 --> 3285.28]  Yeah.
[3285.28 --> 3285.60]  Yeah.
[3285.60 --> 3286.54]  It's one of our values.
[3286.98 --> 3288.30]  Rigor and urgency come into tension.
[3288.72 --> 3289.14]  Rigor and urgency.
[3289.60 --> 3289.76]  Yeah.
[3289.82 --> 3297.56]  So we've got our, we've got 15 values at oxide and we ask people to take two of our values and ask when they have come into tension for them.
[3298.40 --> 3300.48]  And the most common is rigor and urgency.
[3301.54 --> 3302.28]  It's very engineering.
[3302.68 --> 3303.74]  Urgency is another one of our values.
[3304.06 --> 3306.84]  And that's the, I think, rigor and urgency and the tension between rigor and urgency.
[3307.12 --> 3308.80]  That's a tension that we see a lot in engineering.
[3308.80 --> 3311.28]  I mean, and how you do navigate that tension, right?
[3311.34 --> 3316.38]  Because you've got to be, I think in our belief, your belief obviously is that rigor has to win out.
[3316.58 --> 3316.68]  Yeah.
[3316.80 --> 3317.74]  You don't want to miss steps.
[3317.86 --> 3323.16]  I mean, and I think it's, it's hard, it's hard to do otherwise now that we have this practice.
[3323.94 --> 3324.34]  Right.
[3325.02 --> 3328.62]  Well, in terms of like, once you kind of set a culture of that.
[3328.72 --> 3330.48]  Of documenting and logs.
[3330.48 --> 3340.62]  If people come in, they, you know, we've got a, we got one of our founding engineers, Robert Moustaki has, is a, is a terrific note taker in meetings.
[3340.74 --> 3342.98]  No, he like makes me feel self-conscious.
[3342.98 --> 3343.36]  I know, I know.
[3343.46 --> 3344.64]  Can we just talk about that for a second?
[3344.64 --> 3346.42]  Sorry, sorry, we're going to have a therapy session real quickly.
[3346.94 --> 3349.86]  I, I mean, I get total like meeting imposter syndrome.
[3350.02 --> 3350.86]  The bar's been set high.
[3350.98 --> 3358.30]  The bar's been set super high, but it's where in every meeting you take these notes that are, then send them out to everyone.
[3358.30 --> 3363.20]  And boy, it's amazing though, to have that and to have that culture get set and that expectation.
[3363.50 --> 3365.52]  So I super appreciate that.
[3365.60 --> 3368.78]  I have the world of respect for like people who know take at that level.
[3369.20 --> 3373.92]  We make it work, but like, you know, when you don't have people who are necessarily like process naturals, how do you do it?
[3374.12 --> 3374.28]  Yeah.
[3374.34 --> 3374.94]  So how do you do it?
[3374.96 --> 3375.84]  Or how do you make it lightweight?
[3375.84 --> 3384.84]  And one thing we do that I think has been really good for us, you know, capturing and remembering the hardest thing to do for us is like you go out and we actually field test with a real prototype.
[3384.84 --> 3389.62]  And, you know, you can say like, well, I think what I saw was this, right?
[3389.64 --> 3391.88]  Like, I think this is the thing we need to adjust for next time.
[3392.42 --> 3408.46]  And you leave the field, you go to the office and you're like, okay, so like, here's what I saw and here's what, and that might shift as you go from the, you know, institute moment to like later trying to remember like what the other guy said, like looked like it needed to be adjusted.
[3408.46 --> 3416.92]  So we do post-flight debrief where like we kind of just do a huddle and talk through, you know, what did you see?
[3417.02 --> 3417.62]  How did it go?
[3417.72 --> 3418.40]  How did it feel?
[3418.82 --> 3421.50]  You know, what do you think we need to improve for next time, if anything?
[3422.20 --> 3429.48]  And I'm really fastidious because it's high leverage and easy for me to do is like we get that transcribed and captured.
[3429.80 --> 3431.32]  That is, I was just going to ask.
[3431.38 --> 3434.88]  So you have a huddle where people are speaking.
[3435.34 --> 3435.74]  Reviewing.
[3435.88 --> 3436.94]  Reviewing, but it's all oral.
[3436.94 --> 3442.68]  And optionally all oral and optionally even interrogating sort of like, okay, tell me, did this like, did it seem like?
[3443.08 --> 3443.44]  Okay.
[3443.70 --> 3445.12]  And then, so it's a conversational.
[3445.30 --> 3446.08]  It's conversational.
[3446.30 --> 3446.94]  It's verbal and.
[3447.66 --> 3448.06]  It's recorded.
[3448.30 --> 3448.94]  And it's recorded.
[3449.02 --> 3449.38]  That's cool.
[3449.58 --> 3450.50]  And then transcribed later.
[3450.50 --> 3452.90]  And then that makes it possible to refer to or search.
[3453.12 --> 3458.68]  And crucially to me, it's still light enough because you're going to talk about what happened afterward, no matter what.
[3458.72 --> 3460.80]  So it's a very natural thing for people.
[3460.96 --> 3460.98]  Yeah.
[3461.02 --> 3464.32]  So we did this, what we were raising a lot of money to start a company.
[3464.32 --> 3466.76]  And we, the three of us would do this.
[3466.76 --> 3468.44]  We would take these oral notes together.
[3469.70 --> 3470.06]  And.
[3470.58 --> 3471.72]  Not transcribe them later.
[3471.94 --> 3472.68]  That would be interesting.
[3472.92 --> 3475.20]  That would be, don't you, yeah, bite your tongue.
[3475.30 --> 3476.74]  That would be, that would be dangerous.
[3477.18 --> 3479.86]  But they were incredibly valuable.
[3480.00 --> 3480.66]  I mean, let's be real.
[3480.74 --> 3484.18]  I work with people that are on the record notes and off the record notes.
[3484.44 --> 3486.42]  You know, usually, usually it's just a little thing.
[3486.56 --> 3487.16]  You know, an extra comment.
[3487.16 --> 3489.74]  And I think what's really interesting for that is to go back and re-listen to some of that stuff.
[3489.76 --> 3492.94]  And you're just like, oh man, I'd forgotten all these details that were really important details.
[3492.94 --> 3502.50]  And I have, that was such an interesting experience for us that I have been so tempted to do that in from an engineering perspective as well.
[3502.78 --> 3503.62]  And we should just do that.
[3503.70 --> 3504.48]  That is such a good idea.
[3504.64 --> 3505.50]  We don't do it all the time.
[3505.56 --> 3506.42]  We don't do it for everything.
[3506.42 --> 3514.06]  But I strive to mitigate the thing where someone's like, I'm really sure that they said that like the, you know, this part needs to be heavier.
[3514.16 --> 3515.86]  And I'm like, no, they said it needs to be lighter.
[3516.02 --> 3517.86]  You know, and like this way we don't have to have that debate.
[3517.88 --> 3519.38]  We can refer to what was actually said.
[3519.46 --> 3520.00]  Go back to the tape.
[3520.10 --> 3520.84]  Yeah, go back to the tape.
[3520.86 --> 3521.64]  For the critical moments.
[3521.76 --> 3526.38]  And then I think also not having it be audio is actually a big deal because you can sort of like scroll or search.
[3526.52 --> 3527.00]  You know, those are huge.
[3527.00 --> 3528.22]  Yeah, having it transcribed.
[3528.78 --> 3529.88]  That's a really good idea.
[3530.04 --> 3530.42]  Especially postmortems.
[3531.54 --> 3531.90]  Postmortems.
[3531.90 --> 3542.62]  Also, just like when you've got, there's so many of these design discussions where the other thing that I find that I hate myself for doing and I've tried to actively undo in myself.
[3543.34 --> 3550.00]  But when I'm going back and re-listening to some of this stuff, I will have an observation that I want to make.
[3550.48 --> 3551.30]  But someone else is speaking.
[3552.50 --> 3554.88]  And I will, someone else will say something.
[3555.14 --> 3557.66]  And then I will make the observation that I wanted to make.
[3557.66 --> 3561.40]  And the reality is my brain was not processing both of those at the same time.
[3561.58 --> 3563.58]  Which is a long way of saying, like, I wasn't listening.
[3563.78 --> 3564.28]  You know what I mean?
[3564.32 --> 3565.60]  It's like I was not talking.
[3566.16 --> 3568.54]  But I was, there was a point that was made.
[3568.66 --> 3569.26]  You were waiting to talk.
[3569.32 --> 3570.02]  You were waiting to talk.
[3570.42 --> 3573.10]  And there's a point that was made that was a valuable point.
[3573.98 --> 3575.54]  And I will re-listen to it.
[3575.60 --> 3577.00]  And I know that I've missed the point.
[3577.28 --> 3583.62]  And you realize how much, even when you think you're being attentive, the level of attentiveness, you actually have to re-listen.
[3583.62 --> 3586.94]  I have to re-listen to the same thing three or four times.
[3587.02 --> 3589.48]  Well, maybe this way you could read instead of, you know, re-listening.
[3589.90 --> 3591.00]  It's a different channel.
[3591.42 --> 3595.40]  And I'd say, like, nine times out of ten, we don't end up, like, really deeply reviewing again.
[3595.64 --> 3595.92]  Right?
[3595.98 --> 3597.44]  But it's like, you know, it's there.
[3597.62 --> 3598.68]  How much audio is it?
[3599.20 --> 3601.28]  Oh, it's some handful of minutes.
[3601.58 --> 3601.74]  Okay.
[3601.82 --> 3604.68]  So transcribing it is just listening and typing that in.
[3604.76 --> 3606.98]  There's no, you can also use software to that.
[3607.22 --> 3607.86]  Do you use software?
[3608.48 --> 3608.78]  Yes.
[3609.06 --> 3610.80]  How accurate is that?
[3611.02 --> 3611.82]  It's accurate enough.
[3611.82 --> 3614.34]  Okay, because I see some weird things on YouTube.
[3614.46 --> 3614.76]  No, no, no.
[3614.84 --> 3621.46]  I mean, no, like, look, you know, for the purposes of what you're talking about, where it's just like, you know, I think we need to adjust, you know, this control service or what have you.
[3621.68 --> 3628.10]  Like, I would even argue that it's crucial that we use transcription to get it done because otherwise it's not high leverage.
[3628.10 --> 3628.36]  Right.
[3628.42 --> 3631.24]  Otherwise, it's like one second per second reliving.
[3631.42 --> 3631.52]  Right.
[3631.52 --> 3633.20]  Like, no one has time for that.
[3633.32 --> 3633.44]  Yeah.
[3633.44 --> 3633.60]  Yeah.
[3633.64 --> 3634.42]  That's super true.
[3634.42 --> 3638.74]  The other thing I would say is that for a company that touches a build process that we own in-house.
[3638.90 --> 3639.00]  Right.
[3639.06 --> 3641.40]  So for one thing, there's organizational learning there.
[3641.40 --> 3645.98]  And for two, I think capturing SOPs, I can't believe that this is me as an adult.
[3646.16 --> 3647.12]  Like, this is what I talk about.
[3647.30 --> 3649.58]  But capturing the SOPs is critical for scaling.
[3650.20 --> 3650.38]  Yeah.
[3650.50 --> 3651.10]  End of story.
[3651.20 --> 3651.34]  Right.
[3651.36 --> 3653.88]  If you can't hand off a process, then, like, what are you doing?
[3654.10 --> 3654.36]  Yes.
[3654.52 --> 3654.68]  Yeah.
[3654.68 --> 3655.00]  Yeah.
[3655.08 --> 3657.84]  And getting that thing written down and thought about rigorously.
[3658.32 --> 3662.26]  And I'm sorry to not be able to move on from the recording of those discussions.
[3662.48 --> 3663.10]  It's really cool.
[3663.20 --> 3664.60]  No, I don't feel it's done in the industry.
[3664.74 --> 3665.52]  I feel that the...
[3665.52 --> 3665.86]  It's fair.
[3665.94 --> 3668.96]  And I feel that if we had not done that during the race, I don't know that...
[3668.96 --> 3672.18]  I mean, I've seen how incredibly valuable it is.
[3672.18 --> 3673.42]  But have you heard of other folks doing this?
[3673.50 --> 3674.36]  Maybe this happens...
[3674.36 --> 3675.20]  We get a lot of...
[3675.20 --> 3678.82]  When we demo, we get a lot of attention because we openly use checklists.
[3679.16 --> 3679.26]  Right.
[3679.26 --> 3683.08]  And this is even within a field of people, you know, doing engineering building stuff.
[3683.18 --> 3684.80]  It's like, I think it doesn't come naturally.
[3685.54 --> 3685.66]  Yeah.
[3685.78 --> 3689.44]  That's interesting because in flight, I feel like checklists are a huge thing, right?
[3689.50 --> 3690.36]  Like, before takeoff and landing.
[3690.36 --> 3691.68]  People come from all different backgrounds.
[3691.92 --> 3693.42]  So, you know, it's like a funny thing.
[3693.50 --> 3695.44]  There's a high number of pilots on my team.
[3695.60 --> 3698.60]  And so, like, there's a huge familiarity with, like, the checklist thing is ingrained.
[3698.60 --> 3702.06]  And also, honestly, also how we speak to each other is really informed by, like, the kind
[3702.06 --> 3704.44]  of intense radio training you get, like radio work.
[3704.64 --> 3706.38]  They use Niner a lot.
[3706.70 --> 3709.50]  Actually, I do use copy and affirmative.
[3709.62 --> 3710.12]  We're not...
[3710.12 --> 3710.74]  We're not...
[3710.74 --> 3711.76]  Copy, yes.
[3712.08 --> 3713.10]  Copy, Niner.
[3713.46 --> 3715.74]  Niner is a joke, but I feel...
[3715.74 --> 3716.32]  I use affirmative.
[3716.52 --> 3717.06]  I use affirmative.
[3717.28 --> 3717.44]  Yeah.
[3718.00 --> 3718.72]  Affirmative and negative.
[3718.72 --> 3718.82]  I like Niner.
[3719.30 --> 3720.48]  Affirmative and negative are...
[3720.48 --> 3722.36]  There's a reason we use affirmative and negative and not yes and no.
[3722.36 --> 3724.82]  There are some subtleties between, like, I heard you and I'll do it that matter.
[3724.96 --> 3725.22]  Yeah.
[3725.54 --> 3728.18]  Like, neither one is a wrong answer to give, but it's, like...
[3728.18 --> 3728.64]  Yeah, copy.
[3728.64 --> 3729.20]  Just different.
[3729.46 --> 3729.72]  Copy.
[3729.80 --> 3731.64]  Yeah, so when you hear me say copy, this is...
[3731.64 --> 3732.78]  Yeah, no, it's...
[3732.78 --> 3735.76]  And then the alternative is willco, which is, like, will comply.
[3736.40 --> 3736.76]  Ooh.
[3737.18 --> 3737.38]  Yeah.
[3737.48 --> 3739.50]  I don't think we really actually say willco, though.
[3739.92 --> 3740.24]  Yeah.
[3740.34 --> 3741.16]  And you don't say Niner.
[3741.74 --> 3742.76]  It's a Tommy Boy reference.
[3742.78 --> 3746.12]  I would not say that unless I was really in context where that was appropriate.
[3746.12 --> 3747.64]  Did I ask you a Niner in there?
[3747.64 --> 3748.56]  You can't just Niner people.
[3748.72 --> 3749.90]  You can't just Niner people.
[3750.32 --> 3751.10]  I was about to!
[3751.20 --> 3752.10]  You're like, I'm totally going to do that.
[3752.10 --> 3753.20]  Jess was getting in on the Niner.
[3753.20 --> 3753.34]  Niner.
[3753.76 --> 3754.24]  Or...
[3754.24 --> 3755.56]  Then also, are...
[3755.56 --> 3757.04]  Do you...
[3757.04 --> 3758.12]  The reason is because...
[3758.12 --> 3758.50]  Like Delta people?
[3758.68 --> 3759.80]  Radios are bad, right?
[3759.86 --> 3761.98]  So, like, in general, you can't really under...
[3761.98 --> 3762.64]  You can't believe...
[3762.64 --> 3764.90]  They're not these, like, nice podcast microphones you guys have.
[3765.00 --> 3768.32]  They're, like, radios don't really record what you're saying or don't really transmit
[3768.32 --> 3769.46]  necessarily that well.
[3769.60 --> 3772.02]  The culture doesn't depend on the hardware being awesome.
[3772.26 --> 3772.40]  Right.
[3772.64 --> 3773.32]  So, it's not just...
[3773.32 --> 3778.36]  Actually, it's not just Niner, which is, like, the end sound is to differentiate it from
[3778.36 --> 3779.10]  something else, right?
[3779.16 --> 3779.26]  Right.
[3779.40 --> 3780.78]  But they also sometimes...
[3780.78 --> 3782.66]  It's a tree instead of three.
[3783.06 --> 3783.40]  Oh, yeah.
[3783.40 --> 3783.80]  Oh, interesting.
[3783.94 --> 3785.40]  Because the sound gets lost.
[3785.72 --> 3786.22]  That's crazy.
[3786.36 --> 3786.50]  Huh.
[3786.50 --> 3793.22]  On the Metal is brought to you by Oxide Computer Company.
[3793.38 --> 3797.80]  Well, I gotta tell ya, the podcast has been more successful than I originally anticipated.
[3797.92 --> 3798.58]  Hey, that's great.
[3798.92 --> 3799.18]  Yeah.
[3799.32 --> 3800.26]  There's good news.
[3800.48 --> 3802.48]  Folks are liking the content.
[3802.94 --> 3804.58]  There has been some negative feedback, though.
[3804.66 --> 3804.88]  What?
[3804.92 --> 3805.38]  From the podcast?
[3805.48 --> 3806.14]  The podcast is great.
[3806.20 --> 3807.02]  These interviews are amazing.
[3807.18 --> 3809.16]  The podcast themselves folks are liking.
[3809.16 --> 3814.48]  I've gotten a couple emails specifically calling out the repetitive ad content that's driving
[3814.48 --> 3814.96]  them crazy.
[3815.10 --> 3816.48]  We only recorded three ad rolls.
[3816.64 --> 3816.84]  I know.
[3816.90 --> 3817.80]  We got a lot of ad breaks.
[3818.10 --> 3821.72]  They were reminding me in email about the fact that there's only been three ad rolls
[3821.72 --> 3823.82]  that they've had to hear again and again and again.
[3823.88 --> 3824.26]  Oh, my God.
[3824.26 --> 3824.84]  We're so sorry.
[3824.94 --> 3825.82]  I mean, it's a great podcast.
[3825.92 --> 3827.56]  We don't want to ruin it with repetitive ad rolls.
[3827.74 --> 3827.88]  Yeah.
[3827.94 --> 3829.06]  So, I think it's something we should keep an eye on.
[3829.26 --> 3829.48]  Okay.
[3829.60 --> 3832.36]  So, in the meantime, we should just tell people to go to Oxide.computer, I guess?
[3832.52 --> 3832.68]  Yeah.
[3832.80 --> 3833.54]  That's all we need to do.
[3833.54 --> 3833.70]  All right.
[3833.74 --> 3836.30]  Sign up on the mailing list and then we'll just like, we'll shut up.
[3836.36 --> 3840.54]  And hey, if you got any feedback on the ads, like definitely send that to us, right?
[3841.08 --> 3841.40]  Sure.
[3841.58 --> 3842.16]  We're getting it.
[3842.38 --> 3842.74]  All right.
[3842.96 --> 3843.52]  Sounds good.
[3844.08 --> 3844.76]  Back to the show.
[3848.76 --> 3850.98]  I'm an avid Channel 9 listener from...
[3850.98 --> 3851.40]  Oh, my gosh.
[3851.40 --> 3851.74]  All right.
[3851.86 --> 3852.14]  I know.
[3852.14 --> 3852.64]  It's so cool.
[3852.64 --> 3853.26]  Hard eyes.
[3853.88 --> 3854.28]  Okay.
[3854.80 --> 3855.46]  Channel 9.
[3855.74 --> 3859.24]  Was the historically United allowed you to listen to air traffic control?
[3859.24 --> 3860.52]  I'm hearing Rhapsody in blue right now.
[3860.66 --> 3861.74]  Oh, my God.
[3861.80 --> 3862.18]  So am I.
[3862.24 --> 3862.70]  Oh, my God.
[3862.76 --> 3863.08]  Gershwin.
[3863.54 --> 3864.24]  Oh, my God.
[3864.46 --> 3865.14]  Oh, my God.
[3865.18 --> 3866.06]  Welcome to the Friendly Skies.
[3866.12 --> 3866.94]  Welcome to the Friendly Skies.
[3867.24 --> 3873.52]  And there was a great United ad from the 80s, I think, where, you know, I just heard
[3873.52 --> 3877.62]  from one of our top customers today and he's going to, you know, no longer going to be
[3877.62 --> 3878.14]  one of our top customers.
[3878.24 --> 3878.94]  Have you seen this ad, Steve?
[3879.16 --> 3879.32]  Yeah.
[3879.60 --> 3882.14]  And where he starts handing out, it's like, so you know what we're going to do?
[3882.56 --> 3884.34]  We are going to visit all of our customers.
[3884.34 --> 3887.14]  So, he starts calling out names and he's handing out United tickets.
[3887.14 --> 3889.44]  And then Rhapsody in blue is playing.
[3889.68 --> 3894.98]  And I know, United can abuse me basically arbitrarily and I'm still United Patriot, which is ridiculous.
[3895.18 --> 3898.72]  But because I love the romance of aviation and I love listening to Channel 9.
[3899.18 --> 3903.74]  Channel 9 was a way to tune into the air-to-air traffic while flying and listen to other pilots
[3903.74 --> 3904.96]  talking to other air traffic controllers.
[3905.04 --> 3905.40]  That's dope.
[3905.42 --> 3906.00]  Oh, which is great.
[3906.24 --> 3906.52]  And so.
[3906.64 --> 3908.14]  On the in-seat, like, stereo.
[3908.14 --> 3913.36]  Oh, and so, you know, so you have like, you know, United 423 heavy, clear for takeoff,
[3913.68 --> 3915.02]  one right, one right, do not delay.
[3915.34 --> 3916.16]  I love do not delay.
[3916.30 --> 3920.88]  Do not delay is like, because in San Francisco, that means that there is someone who is actually
[3920.88 --> 3921.38]  landing.
[3921.68 --> 3921.88]  Get it moving.
[3921.96 --> 3923.02]  Yeah, get moving.
[3923.58 --> 3927.62]  Because there is someone who is actually landing on the other runway that crosses.
[3927.86 --> 3928.26]  Fun fact.
[3928.70 --> 3932.50]  SFO has more weather-related delays than any other airport in the United States.
[3932.54 --> 3933.02]  That I believe.
[3933.20 --> 3933.60]  Absolutely.
[3933.80 --> 3935.12]  Because the runways are so close together.
[3935.12 --> 3940.32]  Because the runway separation is not enough to do parallel to runway landing in instrument
[3940.32 --> 3940.76]  conditions.
[3941.18 --> 3944.24]  Such as fog, which San Francisco might get sometimes.
[3944.48 --> 3944.72]  A little bit.
[3944.76 --> 3948.52]  Although SFO is a little bit better than the actual city.
[3948.84 --> 3953.78]  But San Francisco runways are so close together, they warn you when they are operating under visual
[3953.78 --> 3956.46]  conditions, just letting you know that there's an aircraft next to us.
[3956.74 --> 3957.28]  It's normal.
[3957.60 --> 3962.06]  Like this 737 that's next to you that looks like it's about to serve you drinks.
[3962.22 --> 3963.08]  Like that's fine.
[3963.26 --> 3963.80]  It's normal.
[3963.80 --> 3965.36]  For parallel landing.
[3966.68 --> 3967.46]  I got so excited.
[3967.78 --> 3970.32]  I just ripped the cord out of my microphone.
[3971.34 --> 3972.88]  I am enjoying it so much.
[3972.88 --> 3973.10]  I know.
[3973.34 --> 3974.76]  I get so excited.
[3974.92 --> 3976.16]  I just become...
[3976.16 --> 3978.16]  I love the enthusiasm.
[3978.42 --> 3979.58]  It's so wonderful to be along.
[3980.10 --> 3983.78]  You guys, you promised to bring the on the metal spirit.
[3984.06 --> 3984.66]  And here we are.
[3984.66 --> 3984.82]  Okay.
[3984.86 --> 3985.70]  So on the metal.
[3985.86 --> 3986.98]  So you know what a Traycon is.
[3987.08 --> 3988.12]  But have you ever...
[3988.12 --> 3989.40]  There's a game called the Traycon.
[3990.48 --> 3990.90]  A game.
[3991.08 --> 3991.36]  A game.
[3991.36 --> 3991.42]  Okay.
[3991.76 --> 3993.14]  So Traycon is air traffic control.
[3993.22 --> 3995.86]  It's what you get handed off to when you travel across the country.
[3995.92 --> 4000.64]  And there was a game called Traycon 2 which allowed you to be an air traffic controller
[4000.64 --> 4003.68]  and then you could dial up all of these scenarios.
[4003.68 --> 4011.32]  And you do air traffic control on like O'Hare approach on a stormy day.
[4011.42 --> 4011.80]  Oh goodness.
[4011.80 --> 4016.26]  With a high likelihood of pilots ignoring you.
[4017.02 --> 4018.62]  Or because you have like a private plane.
[4018.72 --> 4022.02]  You have a private plane and you could set a dial where it would like not pay attention
[4022.02 --> 4023.06]  to what you just told it to do.
[4023.70 --> 4024.98]  Because it's a private pilot.
[4024.98 --> 4028.52]  Sometimes a little bit of like it's a little stressful with these like aircraft simulation
[4028.52 --> 4029.42]  games.
[4029.76 --> 4031.34]  So-called games are like...
[4031.34 --> 4031.48]  No.
[4031.56 --> 4034.60]  I was playing this as like a 13-year-old and I was going to be like I need to like pick
[4034.60 --> 4037.54]  up like a smoking habit just to deal with the stress of playing this game.
[4037.66 --> 4039.98]  I mean it's like you see why every air traffic controller...
[4039.98 --> 4040.12]  Anyway.
[4040.34 --> 4042.88]  I'm thinking back to like the poor kid listening to this podcast.
[4043.02 --> 4044.86]  It's going to be like don't follow that advice.
[4045.28 --> 4045.46]  Yeah.
[4045.54 --> 4045.70]  Right.
[4046.32 --> 4048.12]  Well I think the game was I don't think was that...
[4048.12 --> 4048.46]  Which one?
[4048.60 --> 4050.72]  The circle of batteries or the smoking habits?
[4050.74 --> 4051.66]  There's a litany here.
[4051.66 --> 4052.10]  Yeah.
[4055.10 --> 4057.32]  Just because the stuff is super stressful though.
[4057.82 --> 4058.66]  Magic smoke.
[4058.84 --> 4059.08]  Yeah.
[4059.22 --> 4060.30]  Any type of smoke.
[4061.00 --> 4061.38]  Avoid.
[4062.62 --> 4064.14]  And do you have any Channel 9 stories?
[4064.50 --> 4065.26]  I don't know.
[4065.32 --> 4070.64]  I mean just any time we were you know able to fly in a big old airplane which was super
[4070.64 --> 4075.38]  exciting to me then I was definitely hooked up to Channel 9 when I could be.
[4075.64 --> 4078.88]  I feel like I've missed out on like a huge portion of my childhood and I'm like extremely
[4078.88 --> 4080.02]  stressed out about it right now.
[4080.02 --> 4083.30]  It you know I think it when it was so pilots could...
[4083.30 --> 4083.76]  Don't be stressed.
[4083.86 --> 4084.30]  Don't be stressed.
[4084.50 --> 4090.04]  I think it was not popular with pilots and indeed the pilots were allowed to start turning
[4090.04 --> 4094.98]  it off and on a flight that I desperately wanted to have Channel 9 on because it was
[4094.98 --> 4095.50]  a mess.
[4095.94 --> 4097.16]  The pilot had turned off Channel 9.
[4097.44 --> 4098.46]  So that people couldn't hear?
[4098.66 --> 4099.22]  Yeah you couldn't hear.
[4099.52 --> 4100.38]  Like here's the thing.
[4100.48 --> 4100.70]  Okay.
[4100.88 --> 4106.02]  I sometimes deal with an aviation adjacent insurance company and they're hold music.
[4106.02 --> 4106.82]  It's not music.
[4106.94 --> 4108.22]  It's actually the live radio.
[4108.22 --> 4109.22]  Oh God.
[4109.22 --> 4109.56]  Oh God.
[4109.56 --> 4109.88]  Oh my God.
[4109.88 --> 4111.24]  Because they know that people are into it.
[4111.64 --> 4115.92]  And so like I don't know you could just record like pleasant air traffic control calls you
[4115.92 --> 4117.60]  know and like I would take that.
[4117.66 --> 4118.22]  Oh I would absolutely.
[4118.42 --> 4124.78]  So I mean so with the confession I often my phone is not in airplane mode when we're
[4124.78 --> 4127.98]  taking off because I'm listening to KSFO on the plane.
[4127.98 --> 4129.84]  So you can listen to KSFO.
[4130.18 --> 4132.24]  You can get all these live feeds for air traffic control.
[4132.86 --> 4134.20]  And so you can listen to it as you're taking off.
[4134.38 --> 4139.22]  Just to note you can listen to KSFO in your house on the ground and not in a situation
[4139.22 --> 4141.18]  where the regulations require you to put your phone in.
[4143.06 --> 4145.58]  So does that pose a danger to the aircraft?
[4145.74 --> 4147.68]  I mean is that a well conceived regulation?
[4148.50 --> 4149.22]  Oh I'm so ready.
[4149.44 --> 4149.94]  I'm so ready.
[4149.94 --> 4150.88]  It's an unfair question.
[4150.96 --> 4151.16]  Jess?
[4151.16 --> 4154.42]  Did you want to answer that one?
[4154.72 --> 4155.54]  Oh I don't know.
[4156.56 --> 4159.12]  I can see why they do it.
[4160.08 --> 4160.88]  Why do they do it?
[4160.88 --> 4161.80]  But why is it?
[4162.96 --> 4164.94]  There's rationale behind it that makes sense.
[4165.30 --> 4169.56]  So I mean the best way to think about the FAA and honestly like FAA regulators have really
[4169.56 --> 4173.84]  important job and I think are really trying to do a good job of what they do.
[4173.84 --> 4176.14]  You look at the history of aviation.
[4176.44 --> 4180.46]  It's the case that like pilots were these like yahoos right?
[4180.46 --> 4184.84]  Like they're strapping on like a leather skull cap and little goggles and like doing
[4184.84 --> 4185.58]  rolls or whatever.
[4185.72 --> 4190.52]  You know like the FAA's job is to make it to people who don't have any interest in flying
[4190.52 --> 4193.54]  or aviation are kind of like don't have a worry.
[4193.86 --> 4194.00]  Right?
[4194.08 --> 4195.20]  The FAA does the worrying.
[4195.42 --> 4195.68]  They're there.
[4195.80 --> 4197.98]  There are outsourced aviation safety warriors.
[4198.18 --> 4198.38]  Right?
[4198.50 --> 4198.68]  Yeah.
[4198.80 --> 4202.44]  And they make sure that like aviation is unbelievably safe.
[4202.44 --> 4203.80]  It is amazingly safe.
[4203.80 --> 4204.60]  The record is incredible.
[4204.96 --> 4207.22]  Although I mean that's the NTSB though as much as the FAA.
[4207.42 --> 4207.52]  Right?
[4207.52 --> 4211.68]  Well I mean these are organizations that work in synchrony.
[4211.90 --> 4217.26]  You know NTSB, National Transportation Safety Board, they investigate any incidents and develop
[4217.26 --> 4222.34]  data about like what happened and why and how to like they create recommendations about
[4222.34 --> 4223.82]  how to mitigate those things.
[4223.94 --> 4225.38]  And FAA enacts the rules.
[4225.58 --> 4227.44]  So there's kind of a separation between the organizations.
[4227.90 --> 4228.96]  But I wouldn't say that it's...
[4228.96 --> 4229.46]  And famously attention.
[4229.90 --> 4230.14]  Right?
[4230.24 --> 4231.26]  Between the NTSB and the FAA.
[4231.70 --> 4232.02]  What do you mean?
[4232.02 --> 4235.92]  Well so the NTSB would make safety recommendations that the FAA wouldn't take because it would
[4235.92 --> 4236.72]  be too expensive to implement.
[4236.92 --> 4239.88]  The famous ones being the smoke detectors and the cargo holds.
[4240.00 --> 4240.02]  Right?
[4240.08 --> 4240.36]  Well sure.
[4240.46 --> 4244.14]  I mean I don't know that specific example but what I mean is I think that there's kind
[4244.14 --> 4246.14]  of like a bicameral aspect to it.
[4246.28 --> 4246.50]  Yeah.
[4246.74 --> 4247.40]  That's the...
[4247.40 --> 4247.80]  That's...
[4247.80 --> 4247.96]  Yeah.
[4248.72 --> 4249.96]  I love the NTSB.
[4250.12 --> 4251.40]  Like they keep each other in check?
[4251.70 --> 4252.46]  They try to.
[4252.72 --> 4258.34]  So famously the NTSB felt that smoke detectors were needed in the cargo hold of passenger aircraft.
[4258.34 --> 4262.06]  And the FAA resisted it because it would have cost like 165 million bucks.
[4262.50 --> 4267.28]  And it wasn't until the value jet crash which was due to the lack of smoke detectors that
[4267.28 --> 4268.86]  the FAA then adopted the regulation.
[4269.04 --> 4269.40]  Whoa.
[4269.88 --> 4273.24]  But I mean so there's a tension but it means like someone's got to be...
[4273.24 --> 4274.42]  Someone needs to keep the other in check.
[4274.54 --> 4275.32]  Someone needs to keep the other in check.
[4275.38 --> 4275.58]  My deal.
[4275.64 --> 4276.44]  I love the NTSB.
[4276.68 --> 4280.52]  I'm not sure that they are set up quite to like keep each other in check but I do think
[4280.52 --> 4286.56]  that they both and especially FAA have hard jobs because you're trying to navigate
[4286.56 --> 4292.96]  this like risk mitigation and create frameworks to you know allow other people to safely do
[4292.96 --> 4293.06]  things.
[4293.14 --> 4297.70]  I mean you know the fact that we have rules we do is actually pretty great where like
[4297.70 --> 4302.52]  you can you have an idea for an airplane that doesn't look like anything that's ever flown
[4302.52 --> 4304.82]  before and you think you can build it right.
[4304.90 --> 4307.94]  Like FAA rules actually allow you to build that thing to go fly it.
[4307.98 --> 4309.68]  You can't fly it over other people.
[4309.84 --> 4310.36]  Like there's...
[4310.36 --> 4310.38]  Right.
[4310.38 --> 4310.54]  Right.
[4310.64 --> 4310.74]  Right.
[4310.74 --> 4310.92]  Right.
[4310.92 --> 4311.02]  Right.
[4311.02 --> 4311.12]  Right.
[4311.12 --> 4311.14]  Right.
[4311.14 --> 4311.18]  Right.
[4311.18 --> 4311.22]  Right.
[4311.22 --> 4311.28]  Right.
[4311.28 --> 4311.56]  Right.
[4311.56 --> 4311.62]  Right.
[4311.62 --> 4311.72]  Right.
[4311.72 --> 4311.80]  Right.
[4311.80 --> 4312.12]  Right.
[4312.12 --> 4312.22]  Right.
[4312.22 --> 4312.80]  Right.
[4312.80 --> 4313.12]  Right.
[4313.12 --> 4313.20]  Right.
[4313.20 --> 4313.22]  Right.
[4313.22 --> 4314.22]  Right.
[4314.22 --> 4315.12]  Right.
[4315.12 --> 4319.56]  Like you can't take a paying passenger in your like hoopty but you can definitely fly
[4319.56 --> 4320.36]  yourself around.
[4321.64 --> 4322.22]  That's dope.
[4322.60 --> 4322.72]  Yeah.
[4322.88 --> 4326.76]  And it's very I mean on one hand there was or has been historical attention but on the
[4326.76 --> 4330.96]  other hand it's like the FAA does actually has made modifications obviously a lot of modifications
[4330.96 --> 4333.02]  that are trying to balance it's a hard problem as you say.
[4333.22 --> 4333.86]  It's like they're trying to be...
[4333.86 --> 4337.58]  I have a lot of respect for the FAA's job and you know also like I mean like the vastness
[4337.58 --> 4338.46]  of the United States.
[4339.00 --> 4339.12]  Right.
[4339.12 --> 4344.56]  Like it's a federal organization so any change in rules is enacted across you know six time
[4344.56 --> 4345.26]  zones at least.
[4345.26 --> 4345.54]  Right.
[4345.60 --> 4347.74]  Like it's a huge amount of area that their rules cover.
[4348.18 --> 4354.14]  And then also when you look at how strong the aerodynamic aviation bases in the United
[4354.14 --> 4359.24]  States that like it's kind of like import rules in California end up affecting product
[4359.24 --> 4362.98]  across the country because so much is imported through Californian ports.
[4363.08 --> 4363.20]  Right.
[4363.24 --> 4367.12]  So if you make like an emission standard for a car because so many of those cars are going
[4367.12 --> 4370.66]  to pass through California basically every automaker then just makes cars that comply
[4370.66 --> 4371.60]  with California rules.
[4371.60 --> 4375.80]  So you know so you end up having this like huge leverage it's like you're doing national
[4375.80 --> 4376.20]  rulemaking.
[4376.62 --> 4380.54]  So two FAA rules really govern like global standards.
[4380.94 --> 4384.24]  So you know it's a really serious serious responsibility.
[4384.88 --> 4388.16]  Well and I think it's interesting you phrase it as innovation forward which is really how
[4388.16 --> 4391.54]  I mean that's how we would like to have all regulators be.
[4391.88 --> 4392.08]  Yeah.
[4392.16 --> 4396.94]  And like my personal piece on this is like I think that I'd like to see a lot more regulation
[4396.94 --> 4401.88]  built so that we can do more innovating if that makes sense.
[4401.88 --> 4402.24]  Right.
[4402.26 --> 4408.30]  Like I want a checklist that will allow me to have a place I can go and fly this experiment
[4408.30 --> 4410.92]  and do these tasks with my autonomous aircraft.
[4411.40 --> 4415.06]  And I think the right thing to do for that is actually to like write more standards.
[4415.42 --> 4417.50]  And you know it does move slowly.
[4417.62 --> 4418.86]  There's a reason for that.
[4419.02 --> 4424.48]  The entrepreneur in me of course does get frustrated that like I can't do certain things.
[4424.48 --> 4430.16]  So you know all I can say is like and that is with the caveat like I have an enormous
[4430.16 --> 4431.66]  amount of respect for what the work involves.
[4431.88 --> 4437.04]  But this is an extremely important point I think that well-structured regulation fosters
[4437.04 --> 4437.54]  innovation.
[4438.08 --> 4438.30]  Can.
[4438.76 --> 4439.04]  Can.
[4439.22 --> 4439.32]  Right.
[4439.52 --> 4443.34]  You know the time scales are kind of rough because you know you have to have the organizational
[4443.34 --> 4447.16]  patience or like you know time to deal with.
[4447.84 --> 4447.96]  Yeah.
[4449.34 --> 4451.22]  Those changes coming slowly.
[4451.22 --> 4455.64]  Like as I mentioned I've been sort of watching the waves on this for you know 2009 what's
[4455.64 --> 4457.22]  like 11 years later.
[4457.34 --> 4457.50]  Right.
[4457.74 --> 4459.22]  I was like yeah some things have changed.
[4459.34 --> 4460.56]  There have been some positive developments.
[4461.00 --> 4463.66]  But you want to foster innovation.
[4464.10 --> 4467.86]  You want to not have these like leather cap wearing Yahoo's run amok.
[4468.02 --> 4471.60]  But you also like you know I think you do get into trouble when you're favoring organizations
[4471.60 --> 4473.00]  through the use of time scales.
[4473.16 --> 4474.92]  I love the leather cap wearing Yahoo.
[4475.14 --> 4475.60]  I'm sorry.
[4475.76 --> 4478.12]  I like giving someone a ride in their hoopty.
[4478.12 --> 4484.44]  I mean it's like there's a whole visual here that I it's like a barnstormer.
[4484.80 --> 4485.12]  Absolutely.
[4485.26 --> 4489.40]  I mean it's been so cool like now I'm based in Southern California and like Amelia Earhart's
[4489.40 --> 4491.48]  home field is like really close to where I am.
[4491.74 --> 4495.84]  Like I always like sort of like because you know like the shadow of the legacy that she
[4495.84 --> 4498.68]  created is like very present you know and so many others.
[4499.04 --> 4501.40]  And obviously it's a huge aerospace legacy in SoCal.
[4501.52 --> 4502.70]  Is that part of the reason you guys are down there.
[4502.76 --> 4506.38]  There's still an enormous amount of aerospace activity which is that's really why I'm there
[4506.38 --> 4510.84]  is like the people the talent the designers the builders the you know fabrication right
[4510.84 --> 4513.44]  like if you want to tap into that LA has it.
[4513.70 --> 4513.82]  Yeah.
[4514.42 --> 4514.96]  That's cool.
[4515.44 --> 4517.36]  And have you read Ben Rich's Skunk Works?
[4517.48 --> 4517.90]  Have you read this?
[4518.08 --> 4519.98]  Oh this is a really famous book.
[4520.06 --> 4520.16]  Yeah.
[4520.22 --> 4522.44]  It's a it's it's pretty galvanizing.
[4522.58 --> 4527.56]  I'm actually quite close to the former Lockheed Skunk Works plant which is now a mall.
[4527.56 --> 4528.56]  Oh.
[4528.92 --> 4534.84]  But but they kept a tribute to the Lockheed plant with like the mall has a.
[4534.88 --> 4536.46]  Wait like a Jamba Juice or something?
[4536.54 --> 4537.40]  It's like a Jamba Juice.
[4537.60 --> 4538.58]  Oh like there's like a Target.
[4538.92 --> 4539.52]  Oh my God.
[4539.54 --> 4540.20]  Yeah it's like a whole parking lot.
[4540.20 --> 4544.60]  But like but they have cutouts of the Lockheed like cutting edge plants like Constellation
[4544.60 --> 4546.92]  the Blackbird that are kind of like up on the sign.
[4547.06 --> 4547.64]  So there's that.
[4547.78 --> 4548.28]  On the sign.
[4548.38 --> 4549.06]  Okay I need to read that.
[4549.06 --> 4552.10]  Okay so you okay you've got Kelly Johnson.
[4552.36 --> 4553.24]  Kelly Johnson.
[4553.46 --> 4553.54]  Yeah.
[4553.98 --> 4558.66]  He ran the Lockheed Skunk Works which are like turned out these amazing never seen before
[4558.66 --> 4565.06]  like performant aircraft and I think he had a quote which is don't just wound your problems
[4565.06 --> 4565.84]  kill them dead.
[4565.84 --> 4567.34]  Like it was like it's really intense.
[4567.64 --> 4568.88]  Oh you would love Kelly Johnson.
[4569.14 --> 4574.22]  So he's an amazing person and goes to Lockheed basically like I want to do more interesting
[4574.22 --> 4577.62]  things and you're going to basically let me do this with the Skunk Works and.
[4577.62 --> 4583.60]  He was known for his like whip fast mental arithmetic of like some guy was like well I'm thinking
[4583.60 --> 4586.78]  of making like the tube diameter this big and he's like then the outlet temperature is
[4586.78 --> 4589.80]  going to be 600 degrees and how are you going to deal with that and the guy's like reeling
[4589.80 --> 4590.48]  in his chair.
[4592.32 --> 4593.70]  It's and the aircraft they built.
[4593.92 --> 4595.10]  I mean they built the U-2.
[4595.38 --> 4597.76]  Just one thing after another that was like mind blowing.
[4598.14 --> 4599.12]  So Fish Works is a.
[4599.20 --> 4599.88]  Okay I get it.
[4599.96 --> 4601.62]  It's a play on Skunk Works.
[4602.14 --> 4605.62]  And so this is a group I did within within Sun which is not doing anything.
[4605.62 --> 4608.46]  We did not we were not making the SRS 71.
[4608.98 --> 4611.98]  So I know you asked the questions but can you explain like Fish Works like there's a
[4611.98 --> 4612.98]  whole in joke going on.
[4613.12 --> 4618.80]  Well so Fish Works is a group that I and a co-worker of mine started to do something similar
[4618.80 --> 4620.20]  to Skunk Works but for computers.
[4620.70 --> 4625.08]  The fish was fully integrated software and hardware and the works was a it was a tip
[4625.08 --> 4625.50]  of the hat.
[4625.78 --> 4628.70]  I thought the fish was like that's a hip new shell now isn't it.
[4628.70 --> 4630.70]  I do not use that shell.
[4630.94 --> 4632.86]  I mean we're going to get into a whole thing right now.
[4632.92 --> 4633.80]  I thought it was like oh yeah.
[4634.02 --> 4634.50]  Whoop guys.
[4634.66 --> 4635.36]  Hold the car over.
[4636.02 --> 4637.66]  She sells seashells down.
[4639.28 --> 4643.38]  But Jess you will love this book and we'll put obviously put a link to it in the show
[4643.38 --> 4647.20]  notes and it's you know it's one of those things that's actually it's been one of the
[4647.20 --> 4648.46]  most influential books for me.
[4648.56 --> 4651.20]  That is right up there with Soul of a New Machine in terms of influencing the directory
[4651.20 --> 4651.66]  of my life.
[4651.68 --> 4652.96]  Oh those are totally on the same shelf.
[4653.04 --> 4654.18]  Yeah that's it's good.
[4654.18 --> 4659.10]  I think if anyone is a super like av geek or you want to get an aviation geekery another
[4659.10 --> 4663.30]  book I really enjoyed reading was called Who Owns the Sky which is a history of aviation
[4663.30 --> 4663.90]  regulation.
[4664.32 --> 4668.70]  It's a short quick book that's better than you'd guess given what the topic is.
[4668.94 --> 4675.74]  So there's another one Turbulent Skies which I want to read Who Owns the Sky is in the Sloan
[4675.74 --> 4676.64]  technology series.
[4676.80 --> 4676.98]  Nice.
[4677.40 --> 4680.76]  But the whole era of deregulation is kind of amazing.
[4680.76 --> 4686.86]  So that's referring to the time where previously airlines would go to the civil aviation civil
[4686.86 --> 4690.86]  aeronautical board and the fares were all set by the federal government so like you want
[4690.86 --> 4694.32]  to fly from here to there like this airline's allowed to do it and like this is what that
[4694.32 --> 4695.26]  flight will cost.
[4695.48 --> 4696.82]  Whoa so they couldn't compete on price.
[4696.96 --> 4697.20]  Oh no.
[4697.54 --> 4697.80]  Whoa.
[4697.92 --> 4698.38]  Or route.
[4698.62 --> 4699.36]  Or route or anything.
[4699.60 --> 4703.66]  And your margin was basically how much better than the fare you could do in operating costs
[4703.66 --> 4707.40]  and then if your like company was floundering you just go to the CAB and just like hold
[4707.40 --> 4713.18]  out your hat and deregulation was opening up routes and fares to you know this is where
[4713.18 --> 4715.90]  we got Southwest and discount airlines and everything.
[4716.08 --> 4718.90]  And People's Express and People's Express.
[4719.34 --> 4721.06]  We got all sorts of bonkers airlines.
[4721.36 --> 4723.34]  There was an explosion of airlines.
[4724.34 --> 4728.32]  Amazing amazing incredible fantastic book on this topic.
[4728.50 --> 4729.72]  It's called Hard Landing.
[4730.06 --> 4731.60]  Oh okay.
[4731.74 --> 4732.04]  Okay.
[4732.24 --> 4732.62]  That's good.
[4732.62 --> 4736.58]  And it talks about kind of like the downfall of Pan Am that came as a result.
[4736.66 --> 4736.68]  Right.
[4736.70 --> 4737.04]  Absolutely.
[4737.14 --> 4737.50]  Oh shit.
[4737.60 --> 4737.98]  Pan Am.
[4738.12 --> 4738.86]  That was a huge deal.
[4739.24 --> 4744.16]  And I remember being with my grandfather in the Pan Am Clipper Club in SFO.
[4744.30 --> 4745.18]  Now the United Club.
[4745.90 --> 4747.70]  He was a huge Pan Am flyer.
[4748.26 --> 4753.20]  Actually funny in I think 1955 my mother grew up in Saudi Arabia.
[4753.36 --> 4754.32]  He was a petroleum engineer.
[4754.80 --> 4757.98]  They offered him a lifetime membership to the Clipper Club.
[4758.28 --> 4759.44]  That's really special.
[4759.66 --> 4760.32]  For 500 bucks.
[4760.92 --> 4761.24]  Wow.
[4761.24 --> 4762.34]  Which is a lot of money.
[4762.44 --> 4763.04]  Which is a lot of money.
[4763.28 --> 4768.16]  But my grandfather had this belief that like lifetime membership always buy it.
[4769.14 --> 4769.78]  And it definitely.
[4769.78 --> 4770.64]  That's really cool.
[4770.80 --> 4771.32]  Yeah exactly.
[4771.44 --> 4771.66]  It was definitely.
[4771.88 --> 4772.68]  It was definitely.
[4772.88 --> 4776.90]  Another book I really liked was Sky Gods which is specifically about Pan Am.
[4777.26 --> 4777.80]  About Pan Am.
[4778.46 --> 4778.64]  Okay.
[4778.88 --> 4780.26]  I'm going to have to read most of that.
[4780.72 --> 4783.44]  I would rank Sky Gods as like it was interesting.
[4783.80 --> 4785.30]  But you have to really be into it.
[4785.40 --> 4788.20]  Hard Landing and Skunk Works top of my list.
[4788.20 --> 4788.44]  Okay.
[4788.44 --> 4788.56]  Okay.
[4788.56 --> 4788.74]  Okay.
[4788.74 --> 4792.52]  So as long as you're talking about deregulation I got a deregulation picture book for you.
[4793.12 --> 4795.14]  Deregulation Knockouts Volume 1.
[4795.36 --> 4796.24]  There is no Volume 2.
[4796.58 --> 4798.02]  Which is on each.
[4798.16 --> 4801.34]  It's like a book of photos of defunct airlines.
[4801.62 --> 4801.98]  What?
[4802.46 --> 4803.00]  Which if.
[4803.12 --> 4803.80]  Coffee table book.
[4804.00 --> 4804.64]  Coffee table book.
[4805.00 --> 4807.54]  For it is so delightful.
[4807.96 --> 4808.68]  Conversation starter.
[4808.94 --> 4809.74]  Conversation starter.
[4810.42 --> 4810.68]  Yes.
[4810.78 --> 4811.60]  I mean this is like.
[4812.28 --> 4814.30]  So you've got all these crazy airlines.
[4814.46 --> 4817.28]  They're probably just waiting for more to go debunked for Volume 2.
[4818.02 --> 4818.32]  Yeah.
[4818.32 --> 4820.32]  We're kind of in the post deregulation era.
[4821.60 --> 4822.96]  I got to take a look at this book.
[4823.10 --> 4823.32]  Oh.
[4823.62 --> 4823.88]  No.
[4823.98 --> 4824.90]  They're great.
[4825.08 --> 4825.30]  I mean.
[4825.30 --> 4827.28]  I think the history of aviation is really fascinating.
[4827.58 --> 4828.30]  And like there's deregulation.
[4829.04 --> 4829.50]  There's also.
[4829.72 --> 4829.88]  You know.
[4829.94 --> 4832.30]  You look at like the history of different aircraft configurations.
[4832.30 --> 4834.88]  Or like good ideas that for whatever reason.
[4835.16 --> 4835.32]  You know.
[4835.42 --> 4838.16]  There's a very obscure one called the Convert a Plane.
[4838.30 --> 4838.68]  That like.
[4838.78 --> 4839.06]  You know.
[4839.10 --> 4840.50]  I've spent more time than I should admit.
[4840.56 --> 4841.70]  Like being interested by.
[4841.84 --> 4842.30]  Which is like.
[4842.52 --> 4845.04]  An aircraft that can convert from flying like an airplane.
[4845.20 --> 4846.18]  To flying like a helicopter.
[4846.68 --> 4846.84]  So.
[4847.08 --> 4847.22]  You know.
[4848.00 --> 4848.40]  Sorry.
[4848.46 --> 4849.28]  It's flying like a gyrocopter.
[4849.40 --> 4849.58]  But.
[4849.88 --> 4850.16]  Technically.
[4850.52 --> 4850.62]  But.
[4850.86 --> 4852.22]  The Osprey did the same thing.
[4852.28 --> 4852.38]  Right.
[4852.42 --> 4854.36]  And famously was a very expensive project.
[4854.50 --> 4856.24]  That took forever to get right.
[4856.38 --> 4857.86]  Great book about the Osprey.
[4857.86 --> 4858.26]  Ooh.
[4860.56 --> 4861.60]  This is called.
[4861.60 --> 4863.02]  The Dream Machine.
[4863.64 --> 4863.98]  Okay.
[4864.16 --> 4865.84]  And there's another book called The Dream Machine.
[4865.96 --> 4867.22]  Which is about JCR Licklider.
[4867.40 --> 4868.06]  And this is not.
[4868.06 --> 4868.16]  Yeah.
[4868.16 --> 4869.14]  Not that book.
[4869.14 --> 4869.24]  Not that book.
[4869.24 --> 4869.44]  Yeah.
[4869.44 --> 4869.90]  Because I was like.
[4869.96 --> 4870.98]  I know a dream machine.
[4871.10 --> 4871.24]  Okay.
[4871.34 --> 4871.66]  Not that.
[4871.80 --> 4871.96]  Yeah.
[4871.96 --> 4872.38]  So there's.
[4872.38 --> 4873.08]  The Dream Machine about the Osprey.
[4873.08 --> 4874.30]  There's two good books with the same title.
[4874.56 --> 4876.00]  And it really talks about just like.
[4876.12 --> 4878.32]  The amount of commitment of belief.
[4878.48 --> 4880.26]  The engineers who built the tilt rotors.
[4880.50 --> 4880.76]  Yeah.
[4880.76 --> 4883.74]  And virtual planes had going into that program.
[4884.02 --> 4884.16]  Oh.
[4884.18 --> 4884.54]  That's cool.
[4884.72 --> 4885.40]  Because that.
[4885.50 --> 4886.04]  And that program.
[4886.20 --> 4886.92]  And how like.
[4886.98 --> 4887.58]  Took a long time.
[4887.58 --> 4888.04]  How expensive.
[4888.04 --> 4888.64]  Was very expensive.
[4888.96 --> 4890.26]  What people went through.
[4890.50 --> 4890.84]  And I mean.
[4890.84 --> 4892.04]  And also the loss of life.
[4892.30 --> 4892.44]  Right.
[4892.82 --> 4893.00]  That.
[4893.00 --> 4895.52]  That particular aircraft incurred.
[4895.58 --> 4895.94]  Right.
[4896.18 --> 4896.94]  On its way to.
[4897.48 --> 4897.84]  Becoming.
[4898.24 --> 4898.98]  Something we have.
[4899.08 --> 4899.26]  Yeah.
[4899.30 --> 4899.92]  It's something we have.
[4900.02 --> 4901.08]  It's unclear to me how.
[4901.50 --> 4902.78]  Permanently successful that is.
[4902.86 --> 4903.42]  Versus like.
[4903.54 --> 4903.72]  I mean.
[4904.58 --> 4904.90]  Versus.
[4905.00 --> 4906.30]  I love talking about the future.
[4906.50 --> 4907.00]  Who could say.
[4907.42 --> 4907.76]  That's right.
[4907.80 --> 4908.24]  There you go.
[4908.68 --> 4908.86]  You know.
[4909.00 --> 4910.54]  What is permanently successful.
[4910.72 --> 4911.02]  I mean.
[4911.02 --> 4911.94]  Like in the long run.
[4912.06 --> 4912.14]  Right.
[4912.14 --> 4912.32]  Like.
[4912.32 --> 4913.98]  I already hate myself having said it.
[4913.98 --> 4914.22]  Every computer is sand.
[4915.06 --> 4915.40]  Yeah.
[4915.46 --> 4915.60]  No.
[4915.64 --> 4915.94]  You're right.
[4916.24 --> 4916.76]  You're right.
[4917.02 --> 4917.76]  You know what actually.
[4917.86 --> 4918.80]  I find gutting that.
[4918.84 --> 4919.74]  Is the fact that the A380.
[4919.74 --> 4920.74]  Is being taken out of service.
[4921.14 --> 4921.72]  Isn't that depressing.
[4922.56 --> 4922.90]  Is it.
[4923.58 --> 4923.94]  Is it.
[4924.08 --> 4924.44]  You don't like.
[4924.52 --> 4925.34]  You're not an A380 fan.
[4925.98 --> 4926.70]  I don't know.
[4926.70 --> 4927.50]  If I should weigh in.
[4927.50 --> 4927.72]  Like.
[4928.28 --> 4929.60]  New stuff is coming.
[4929.76 --> 4930.94]  I don't dislike the A380.
[4931.20 --> 4931.52]  Particularly.
[4931.72 --> 4932.92]  The A380 just made a bad bet.
[4933.08 --> 4934.56]  They bet on hub and spoke.
[4935.00 --> 4935.02]  And.
[4935.20 --> 4935.90]  And huge planes.
[4935.94 --> 4936.62]  And huge planes.
[4936.62 --> 4937.36]  That didn't have extended.
[4937.52 --> 4938.38]  At any longer range.
[4938.46 --> 4938.66]  I mean.
[4938.68 --> 4939.02]  I don't know.
[4939.06 --> 4939.62]  I take this like.
[4939.66 --> 4941.04]  Kind of one step back view.
[4941.22 --> 4942.44]  About other people's.
[4942.68 --> 4943.60]  Technological developments.
[4943.60 --> 4944.14]  Because like.
[4944.62 --> 4945.54]  Things rise and fall.
[4945.62 --> 4946.56]  And I think it's super interesting.
[4947.46 --> 4947.74]  Yeah.
[4947.74 --> 4949.62]  You know what it's like the creative destruction.
[4949.92 --> 4950.28]  Of like.
[4950.36 --> 4950.62]  You know.
[4951.22 --> 4952.32]  This is an interesting idea.
[4952.36 --> 4954.70]  And it joins many other really interesting ideas.
[4955.00 --> 4955.94]  In the history of aviation.
[4955.94 --> 4957.44]  And now it's in the pantheon of history.
[4957.82 --> 4958.32]  I mean.
[4958.40 --> 4959.12]  The thing that's impressive.
[4959.12 --> 4959.80]  Is they built it.
[4959.84 --> 4960.40]  They shipped it.
[4960.46 --> 4960.74]  Like.
[4960.74 --> 4961.34]  It exists.
[4961.52 --> 4962.10]  It is impressive.
[4962.24 --> 4962.54]  It flew.
[4962.92 --> 4963.38]  It flew.
[4963.62 --> 4964.38]  And if you're old.
[4965.04 --> 4966.60]  My mother's a long haul traveler.
[4966.78 --> 4968.16]  And loves that aircraft.
[4968.30 --> 4969.00]  It's very upset.
[4969.10 --> 4969.50]  A380.
[4969.94 --> 4970.46]  A380.
[4970.80 --> 4971.02]  Yeah.
[4971.02 --> 4971.58]  Because they.
[4971.84 --> 4971.98]  You know.
[4971.98 --> 4972.18]  They had.
[4972.28 --> 4972.76]  They can hold.
[4972.98 --> 4973.14]  Like.
[4973.40 --> 4973.60]  Like.
[4973.60 --> 4974.92]  Like the reason I don't want to weigh in though.
[4974.92 --> 4975.36]  Is like.
[4975.42 --> 4975.72]  You know.
[4975.72 --> 4976.80]  There are people who.
[4977.24 --> 4978.30]  Put these hats on.
[4978.38 --> 4979.28]  I'm sure you see them.
[4979.46 --> 4979.92]  In computing.
[4980.20 --> 4980.52]  All over.
[4980.66 --> 4980.94]  Like.
[4981.14 --> 4981.76]  I'm on like.
[4982.02 --> 4982.78]  Team Airbus.
[4982.96 --> 4984.18]  I don't know what you're talking about.
[4984.34 --> 4984.50]  No.
[4984.60 --> 4985.82]  There's no tribalism in computing.
[4985.88 --> 4987.02]  What did you just say about like.
[4987.02 --> 4987.42]  Shells.
[4987.48 --> 4988.58]  I don't think she has strong feelings.
[4989.00 --> 4989.36]  Exactly.
[4989.64 --> 4989.78]  Well.
[4989.86 --> 4990.98]  I have strong feelings.
[4991.04 --> 4991.42]  For sure.
[4992.30 --> 4992.54]  Yeah.
[4993.00 --> 4993.42]  I'm like.
[4993.42 --> 4993.78]  I'm like.
[4993.78 --> 4994.60]  Pro aircraft.
[4994.84 --> 4995.12]  That's like.
[4995.40 --> 4995.48]  Yeah.
[4995.48 --> 4995.74]  Yeah.
[4995.96 --> 4996.78]  That is so.
[4996.96 --> 4997.80]  That's great.
[5001.02 --> 5002.02]  I'm like.
[5002.02 --> 5002.52]  I'm like.
[5002.52 --> 5003.96]  Because you experience the pain.
[5004.28 --> 5005.20]  Of using something else.
[5005.52 --> 5005.74]  I think.
[5006.30 --> 5006.56]  I mean.
[5006.60 --> 5006.92]  Personally.
[5007.04 --> 5007.94]  That is where it comes from.
[5008.00 --> 5008.28]  For me.
[5008.80 --> 5009.12]  Interesting.
[5009.44 --> 5010.00]  The problem for me.
[5010.04 --> 5010.24]  Is like.
[5010.30 --> 5010.96]  I want to be with people.
[5011.06 --> 5011.82]  Who share my values.
[5011.96 --> 5012.72]  And I feel like we.
[5013.18 --> 5014.10]  These things divide.
[5014.20 --> 5014.52]  Into like.
[5014.64 --> 5015.28]  Values divides.
[5015.34 --> 5015.90]  At least in computing.
[5016.38 --> 5017.28]  I think it's not wrong.
[5017.32 --> 5018.26]  To have strong values.
[5018.54 --> 5018.74]  Right.
[5019.10 --> 5019.72]  It's just too bad.
[5019.76 --> 5020.04]  That we.
[5020.12 --> 5020.42]  We do.
[5020.54 --> 5021.02]  We end up.
[5021.22 --> 5021.46]  You know.
[5021.86 --> 5022.08]  God.
[5022.14 --> 5022.32]  Well.
[5022.38 --> 5022.60]  You know.
[5022.60 --> 5023.52]  The thing that I really like.
[5023.52 --> 5024.24]  To stay away from.
[5024.34 --> 5025.32]  Is that it's so much easier.
[5025.32 --> 5026.18]  To tear down.
[5026.18 --> 5026.88]  A technology.
[5026.88 --> 5027.92]  And like.
[5028.02 --> 5028.98]  The number of.
[5029.42 --> 5030.06]  You know.
[5030.60 --> 5031.56]  Huge airliners.
[5031.68 --> 5032.76]  That most people have built.
[5033.00 --> 5033.32]  Is much.
[5033.72 --> 5034.88]  Smaller than the number of people.
[5034.96 --> 5036.12]  Who might have opinions about them.
[5036.24 --> 5036.36]  You know.
[5036.48 --> 5036.76]  Totally.
[5037.76 --> 5038.16]  Ah.
[5038.28 --> 5038.50]  You know.
[5038.56 --> 5040.18]  We live in this incredible age.
[5040.26 --> 5040.42]  You know.
[5040.46 --> 5040.74]  There's like.
[5040.84 --> 5041.16]  So much.
[5041.26 --> 5041.58]  I mean.
[5041.62 --> 5041.74]  Like.
[5041.82 --> 5043.50]  I get amazed by little things.
[5043.50 --> 5043.72]  Right.
[5043.74 --> 5044.00]  Like.
[5044.20 --> 5044.78]  Right in front of me.
[5044.80 --> 5045.72]  On the table right now.
[5045.98 --> 5046.90]  There are three.
[5047.24 --> 5047.58]  Like.
[5047.88 --> 5048.28]  Bottles.
[5048.32 --> 5048.52]  Right.
[5048.56 --> 5049.26]  I've got my.
[5049.26 --> 5049.62]  Like.
[5049.72 --> 5050.18]  Water bottle.
[5050.28 --> 5051.10]  That I always have with me.
[5051.20 --> 5051.58]  There's like.
[5051.82 --> 5052.10]  Like.
[5052.20 --> 5052.84]  A water.
[5053.42 --> 5053.74]  Bottle.
[5053.96 --> 5054.02]  Like.
[5054.12 --> 5054.90]  From a store.
[5055.08 --> 5055.48]  And then there's.
[5055.48 --> 5056.68]  Just wants a diet coke.
[5056.76 --> 5057.28]  Shame me right now.
[5057.32 --> 5058.00]  So just go ahead and do it.
[5058.14 --> 5058.42]  Just get another one.
[5058.42 --> 5059.28]  There's a can of soda.
[5059.86 --> 5060.34]  Go ahead.
[5060.46 --> 5060.78]  Say it.
[5061.08 --> 5061.42]  Say it.
[5062.94 --> 5063.44]  Go on.
[5063.52 --> 5063.62]  Just.
[5063.66 --> 5065.24]  Brian is 90% diet coke.
[5065.28 --> 5065.50]  Okay.
[5065.70 --> 5065.96]  All right.
[5066.00 --> 5066.38]  There we go.
[5066.38 --> 5066.66]  And.
[5066.66 --> 5067.26]  And like.
[5067.52 --> 5067.94]  All of these.
[5068.34 --> 5069.50]  Vessels are amazing.
[5069.66 --> 5069.92]  You could go.
[5070.02 --> 5070.10]  Like.
[5070.20 --> 5071.10]  I think I had like a little.
[5071.30 --> 5071.90]  So forgive me.
[5071.96 --> 5072.88]  For people who follow my Twitter.
[5073.04 --> 5073.36]  And like.
[5073.42 --> 5074.38]  Read this for some reason.
[5074.62 --> 5075.24]  Still remember.
[5075.38 --> 5075.76]  But like.
[5075.82 --> 5077.26]  I was just recently tweeting about like.
[5077.52 --> 5078.34]  How incredible it is.
[5078.38 --> 5078.90]  To have like.
[5078.98 --> 5079.44]  Fluid vessels.
[5079.44 --> 5080.30]  That you can like.
[5080.48 --> 5081.26]  Turn upside down.
[5081.32 --> 5081.66]  And trust.
[5081.66 --> 5082.54]  That they're not going to leak.
[5082.78 --> 5084.12]  And that the liquid inside.
[5084.20 --> 5084.80]  Is still good.
[5084.90 --> 5085.18]  And like.
[5085.50 --> 5085.78]  You know.
[5086.14 --> 5087.48]  The pioneers of aviation.
[5087.58 --> 5088.76]  They didn't have like.
[5088.78 --> 5089.54]  A sports bottle.
[5089.54 --> 5090.42]  With them in the plane.
[5090.48 --> 5091.30]  They were just sweating.
[5091.68 --> 5091.82]  Yeah.
[5091.82 --> 5092.02]  You know.
[5092.12 --> 5093.18]  And like thirsty.
[5093.54 --> 5093.84]  You know.
[5093.88 --> 5094.14]  And like.
[5094.20 --> 5095.28]  Maybe this is a small thing.
[5095.34 --> 5095.62]  But like.
[5095.62 --> 5095.80]  These.
[5095.94 --> 5097.20]  These little things we take for granted.
[5097.20 --> 5097.84]  Are so amazing.
[5097.92 --> 5099.78]  Much less the big things that we have.
[5099.78 --> 5100.26]  And like.
[5100.92 --> 5101.66]  It's just such a.
[5101.72 --> 5101.84]  Like.
[5101.90 --> 5102.20]  I don't know.
[5102.40 --> 5102.74]  I think.
[5103.08 --> 5104.36]  The world is getting better.
[5104.46 --> 5106.00]  And it's also an incredible place right now.
[5106.24 --> 5107.68]  That is so true.
[5107.88 --> 5108.54]  That is so true.
[5108.54 --> 5110.22]  My sickening optimist.
[5112.30 --> 5113.48]  Appreciating that any of this works.
[5113.64 --> 5113.76]  Well.
[5113.82 --> 5114.12]  And also.
[5114.20 --> 5114.32]  I mean.
[5114.66 --> 5115.02]  You're.
[5115.16 --> 5116.08]  You're among your people.
[5116.10 --> 5117.56]  Because we just started a computer company.
[5117.56 --> 5118.84]  Which people think is like.
[5119.00 --> 5119.86]  Outrageous and hard.
[5119.90 --> 5120.40]  But it's like.
[5120.40 --> 5122.74]  It's actually easier to do hardware now.
[5122.84 --> 5124.18]  Than it ever has been.
[5125.02 --> 5125.46]  And yet.
[5125.54 --> 5125.76]  We.
[5125.96 --> 5127.66]  I've got a stronger version to it than ever.
[5127.72 --> 5128.28]  When we shouldn't.
[5128.36 --> 5129.02]  It's like these things.
[5129.48 --> 5129.54]  I.
[5129.82 --> 5130.04]  No.
[5130.10 --> 5130.60]  I totally share the opposite.
[5130.60 --> 5131.24]  So tell me this.
[5131.30 --> 5132.90]  Because I'm curious about this topic.
[5133.00 --> 5136.22]  People are surprised that anyone deals with hardware.
[5136.46 --> 5136.70]  Yes.
[5136.82 --> 5137.00]  Yeah.
[5137.06 --> 5138.50]  That's also why we have the podcast.
[5138.54 --> 5139.54]  Is also to remind people.
[5139.54 --> 5140.86]  That like this stuff exists.
[5141.10 --> 5141.74]  Hardware exists.
[5141.84 --> 5142.16]  Yeah.
[5143.16 --> 5143.98]  It's crazy.
[5143.98 --> 5144.36]  Because.
[5144.48 --> 5145.32]  I think that.
[5145.58 --> 5147.30]  Just like the upper stacks of software.
[5147.30 --> 5147.76]  Got so.
[5147.90 --> 5148.88]  So like people heavy.
[5148.88 --> 5150.56]  Like there's so many developers.
[5150.56 --> 5151.30]  And stuff like that.
[5151.30 --> 5151.64]  That like.
[5151.90 --> 5153.18]  People tend to forget that like.
[5153.34 --> 5153.62]  There is.
[5154.10 --> 5154.56]  This underlying.
[5155.32 --> 5155.64]  Component.
[5155.78 --> 5156.14]  I don't know.
[5156.34 --> 5157.10]  And we're in.
[5157.62 --> 5158.50]  The Silicon Valley.
[5158.86 --> 5159.00]  Yeah.
[5159.34 --> 5160.98]  I think the thing that I'm most surprised by.
[5161.10 --> 5161.38]  Is that.
[5161.46 --> 5161.60]  You know.
[5161.66 --> 5162.52]  We've had for a long time.
[5162.60 --> 5163.86]  This management class of people.
[5163.98 --> 5165.38]  Who knew extremely well.
[5165.38 --> 5166.48]  How to take a budget.
[5166.48 --> 5167.38]  And convert it.
[5167.48 --> 5168.38]  Like into.
[5168.72 --> 5169.26]  Cutting edge.
[5169.36 --> 5170.50]  Never been seen before hardware.
[5170.70 --> 5172.14]  Like on a certain timeline.
[5172.64 --> 5172.96]  You know.
[5173.00 --> 5173.68]  And without like.
[5173.92 --> 5174.60]  Massive expenditure.
[5175.02 --> 5175.30]  That's.
[5175.40 --> 5177.36]  That's like a skill you can gain.
[5177.48 --> 5178.08]  Over time.
[5178.42 --> 5178.64]  Yes.
[5178.94 --> 5179.12]  Yeah.
[5179.22 --> 5179.44]  Yeah.
[5179.48 --> 5180.76]  You can solve hard problems.
[5181.20 --> 5181.80]  And that.
[5182.02 --> 5182.32]  You know.
[5182.32 --> 5182.68]  It's.
[5182.76 --> 5184.58]  It's something we understand reasonably well.
[5184.70 --> 5184.90]  Like.
[5184.94 --> 5186.66]  I think that the thing that amazes me is.
[5186.80 --> 5188.24]  And I think that it's been said elsewhere.
[5188.34 --> 5189.82]  We don't understand necessarily that well.
[5189.86 --> 5191.50]  Is the conversion of capital into software.
[5192.00 --> 5192.30]  You know.
[5192.64 --> 5192.82]  Well.
[5192.96 --> 5194.54]  And I think it requires.
[5194.54 --> 5196.08]  A great leap into the unknown.
[5196.20 --> 5196.78]  There's uncertainty.
[5197.16 --> 5197.32]  And.
[5197.44 --> 5198.62]  And failures are going to happen.
[5198.98 --> 5199.30]  And.
[5199.54 --> 5201.20]  That's very hard for people to wrap their.
[5201.40 --> 5202.40]  Their minds around.
[5202.76 --> 5203.12]  Understandably.
[5203.32 --> 5203.54]  You know.
[5203.58 --> 5203.88]  You want.
[5204.06 --> 5204.24]  As.
[5204.38 --> 5205.66]  As Jess was fond of saying.
[5205.82 --> 5207.08]  When we were raising money.
[5207.08 --> 5207.34]  It's like.
[5207.38 --> 5208.56]  People want a done deal.
[5209.00 --> 5209.30]  They do.
[5209.30 --> 5209.88]  But like.
[5209.96 --> 5211.16]  Hardware seems so much more.
[5211.34 --> 5212.10]  A done deal to me.
[5212.16 --> 5212.28]  Like.
[5212.34 --> 5213.64]  This is the thing where I'm just sort of like.
[5213.86 --> 5215.06]  It's like a physical object.
[5215.14 --> 5215.80]  Versus software.
[5216.38 --> 5217.08]  But I don't know.
[5217.14 --> 5217.48]  I think it's.
[5217.54 --> 5218.58]  I think it's just the fact that.
[5218.72 --> 5219.10]  So many.
[5219.54 --> 5220.16]  People these days.
[5220.28 --> 5220.44]  Just.
[5220.66 --> 5221.08]  Just like.
[5221.18 --> 5221.76]  Deal in.
[5222.12 --> 5222.44]  SAS.
[5222.98 --> 5223.22]  It's like.
[5223.32 --> 5224.04]  Software as a service.
[5224.14 --> 5224.56]  And they don't.
[5224.62 --> 5225.44]  They don't really.
[5225.64 --> 5225.78]  Like.
[5225.86 --> 5225.94]  There.
[5226.66 --> 5227.34]  There isn't.
[5227.42 --> 5227.82]  Which is.
[5227.90 --> 5228.34]  The thing is.
[5228.58 --> 5229.06]  And I.
[5229.06 --> 5229.32]  You know.
[5229.38 --> 5229.56]  I think.
[5229.68 --> 5231.00]  It is part of the reason we did the podcast.
[5231.32 --> 5231.78]  Is to.
[5232.32 --> 5233.18]  Communicate to folks.
[5233.50 --> 5233.64]  That.
[5233.80 --> 5234.06]  Actually.
[5234.14 --> 5235.46]  This is more accessible than ever.
[5236.10 --> 5236.34]  That.
[5236.42 --> 5236.56]  You know.
[5236.56 --> 5238.26]  You've been involved in the open hardware movement.
[5238.56 --> 5239.06]  We think that.
[5239.86 --> 5240.26]  The.
[5240.90 --> 5242.64]  Hardware is easier to make than ever.
[5243.08 --> 5245.88]  People can get going on a smaller amount of money than ever.
[5246.56 --> 5246.86]  I mean.
[5247.02 --> 5247.24]  That.
[5247.42 --> 5247.52]  Eight.
[5247.62 --> 5247.74]  You're.
[5247.78 --> 5248.90]  The eight year old you.
[5249.54 --> 5250.74]  Can learn about an FPGA.
[5251.38 --> 5251.58]  Yeah.
[5251.72 --> 5252.08]  Actually.
[5252.22 --> 5252.92]  That is really.
[5253.06 --> 5253.62]  Really neat.
[5253.62 --> 5254.20]  Really cool.
[5254.44 --> 5254.62]  I mean.
[5254.70 --> 5256.48]  The resources that are available are incredible.
[5256.76 --> 5257.02]  And like.
[5257.38 --> 5258.58]  The growth in them is incredible.
[5259.14 --> 5259.32]  I mean.
[5259.38 --> 5260.86]  And I say the tools are interesting.
[5260.86 --> 5261.74]  Because they have.
[5262.04 --> 5263.14]  Improved and got more accessible.
[5263.76 --> 5264.12]  Also.
[5264.30 --> 5265.28]  It's also a world where.
[5265.28 --> 5265.62]  Like.
[5265.86 --> 5266.82]  Change comes over time.
[5266.92 --> 5267.10]  You know.
[5267.16 --> 5267.42]  Like.
[5267.66 --> 5268.70]  Electronic design tools.
[5268.78 --> 5269.08]  I think.
[5269.42 --> 5270.74]  It's so adjacent to.
[5270.90 --> 5270.96]  Like.
[5271.02 --> 5272.14]  Software and programming tools.
[5272.14 --> 5272.70]  Which just like.
[5272.76 --> 5273.40]  Kind of grow.
[5274.00 --> 5274.32]  Explosively.
[5274.42 --> 5274.84]  But then like.
[5274.90 --> 5275.70]  I think because.
[5276.02 --> 5277.66]  Maybe programmers are really used to like.
[5277.78 --> 5278.12]  You know.
[5278.46 --> 5279.76]  Renewing your own tools.
[5279.86 --> 5281.02]  Because if you don't like how something works.
[5281.06 --> 5282.54]  You make your own version of it.
[5282.58 --> 5282.84]  That like.
[5282.86 --> 5283.86]  Works the way you want it to.
[5284.24 --> 5284.64]  And maybe.
[5284.72 --> 5284.84]  Like.
[5284.86 --> 5285.32]  I have a theory.
[5285.42 --> 5285.54]  Like.
[5285.64 --> 5286.40]  Electrical engineers.
[5286.84 --> 5287.92]  Are so adjacent.
[5288.44 --> 5288.76]  That like.
[5288.76 --> 5289.76]  There's a belief that like.
[5289.84 --> 5291.96]  This world should be able to also make its own tools.
[5292.08 --> 5293.04]  But when it comes to software.
[5293.18 --> 5293.28]  Like.
[5293.34 --> 5293.60]  I don't know.
[5293.60 --> 5295.38]  I feel like a lot of electrical engineering design tools.
[5295.38 --> 5296.52]  Are honestly a bit neglected.
[5297.00 --> 5297.46]  Oh they are.
[5297.58 --> 5298.14]  Oh they definitely are.
[5298.40 --> 5298.66]  I mean.
[5298.66 --> 5298.86]  It's.
[5298.92 --> 5299.34]  It's where.
[5299.48 --> 5301.36]  It's the last bastion of Tickle.
[5301.58 --> 5301.92]  I mean.
[5302.00 --> 5302.28]  I mean.
[5302.70 --> 5303.26]  Tickle's great.
[5303.44 --> 5303.54]  I mean.
[5303.60 --> 5303.78]  You're.
[5303.90 --> 5304.34]  That was a good.
[5304.48 --> 5305.06]  Deep reference.
[5305.20 --> 5306.22]  I had to look blankly at you.
[5306.22 --> 5307.76]  Before it all returned to my mind.
[5307.78 --> 5308.18]  You're right.
[5308.28 --> 5308.64]  Exactly.
[5309.04 --> 5310.00]  I hear I've got it.
[5310.00 --> 5310.24]  TK.
[5310.36 --> 5310.62]  Yeah.
[5310.76 --> 5310.94]  Exactly.
[5311.32 --> 5311.82]  T Kinter.
[5312.24 --> 5312.44]  Right.
[5312.50 --> 5313.02]  There you go.
[5313.16 --> 5313.42]  Yeah.
[5314.42 --> 5314.82]  Yikes.
[5315.50 --> 5315.62]  I.
[5315.78 --> 5316.00]  You know.
[5316.06 --> 5317.28]  But I remember teaching a workshop.
[5317.28 --> 5318.00]  On how to like.
[5318.08 --> 5319.76]  Learn to use an electronic design tool.
[5319.94 --> 5320.26]  In like.
[5320.26 --> 5325.10]  Yeah it's 2007 and like the UI hasn't changed for that tool to this day.
[5325.20 --> 5326.96]  Like I could just give the same spiel and it would.
[5327.58 --> 5328.64]  But I think change is coming.
[5328.88 --> 5329.86]  I think that this is.
[5330.00 --> 5333.24]  The EDA has historically been the last bastion of proprietary software.
[5333.50 --> 5334.20]  And that's changing.
[5334.60 --> 5335.94]  And we're seeing now.
[5336.02 --> 5338.00]  Certainly we are building stuff on open EDA tools.
[5338.38 --> 5340.02]  There's been a lot of growth there and that's really good.
[5340.08 --> 5340.32]  You're right.
[5340.32 --> 5341.00]  And I think it's.
[5341.10 --> 5343.04]  The great thing about open source is when.
[5343.44 --> 5344.52]  Once something is open.
[5344.62 --> 5345.46]  A domain is open.
[5345.62 --> 5346.40]  It never goes back.
[5347.82 --> 5349.16]  Open source software is not deleted.
[5349.62 --> 5349.98]  Yeah.
[5350.26 --> 5350.70]  And.
[5350.86 --> 5351.22]  It can be closed.
[5351.36 --> 5351.62]  But not.
[5351.76 --> 5352.24]  Not deleted.
[5352.42 --> 5352.60]  Well no.
[5352.64 --> 5353.30]  It can't even be closed.
[5353.40 --> 5354.26]  You can take a fork.
[5354.52 --> 5355.02]  Is what you can do.
[5355.10 --> 5356.00]  You can't actually close it.
[5356.02 --> 5356.98]  And then you can change the license.
[5357.10 --> 5357.42]  But that.
[5357.52 --> 5359.34]  That which existed is still there.
[5359.42 --> 5359.88]  It's still there.
[5359.98 --> 5360.26]  And it.
[5360.38 --> 5360.86]  And it.
[5360.86 --> 5362.22]  It will exist forever.
[5362.42 --> 5363.60]  I feel like you're talking about rivers.
[5364.68 --> 5365.16]  Well no.
[5365.20 --> 5365.48]  There's not.
[5365.60 --> 5365.78]  I.
[5365.82 --> 5367.30]  I feel that like we get.
[5367.40 --> 5367.88]  And I think you.
[5367.88 --> 5368.20]  You know.
[5368.20 --> 5369.52]  You were hitting on an important point.
[5369.52 --> 5370.28]  In terms of like.
[5370.46 --> 5372.16]  How much change is actually possible.
[5372.66 --> 5374.30]  So I think that we lose track of.
[5374.38 --> 5375.16]  Things can be so.
[5375.56 --> 5376.48]  Frustrating in the moment.
[5377.02 --> 5377.50]  And you're just.
[5377.62 --> 5378.42]  Looking at your.
[5378.42 --> 5380.28]  Your experience with autonomous aircraft.
[5380.52 --> 5380.76]  Where.
[5381.32 --> 5382.34]  The time had to be right.
[5382.78 --> 5383.04]  You know.
[5383.24 --> 5383.60]  And.
[5384.16 --> 5384.52]  And.
[5385.36 --> 5385.80]  You know.
[5385.88 --> 5387.00]  You have to be.
[5387.38 --> 5387.70]  Patient.
[5388.14 --> 5389.04]  Because the world.
[5389.30 --> 5389.70]  Will change.
[5389.76 --> 5390.38]  Once it changes.
[5390.52 --> 5392.06]  It can change more than you ever thought possible.
[5392.36 --> 5392.64]  I mean.
[5392.66 --> 5394.06]  This is why I think it's just so great.
[5394.12 --> 5395.82]  To read the history of technology.
[5396.34 --> 5396.60]  You know.
[5396.62 --> 5397.40]  I remember reading.
[5397.62 --> 5398.78]  About the history of development.
[5398.78 --> 5399.56]  Of a helicopter.
[5399.96 --> 5400.28]  And.
[5400.74 --> 5401.04]  You know.
[5401.12 --> 5402.86]  I think it was like in the 1890s.
[5402.86 --> 5404.16]  Someone wrote a newspaper editorial.
[5404.16 --> 5404.76]  Which is like.
[5405.22 --> 5407.50]  The flood of credulous capitalists.
[5407.50 --> 5410.18]  Who believe in some sort of chemical based engine.
[5410.28 --> 5410.92]  Never ceases.
[5411.58 --> 5412.50]  Petroleum engines.
[5412.96 --> 5413.72]  Chemical engines.
[5414.24 --> 5415.72]  These people will never amount to anything.
[5415.92 --> 5416.28]  And it's like.
[5416.28 --> 5416.50]  That's great.
[5416.60 --> 5417.54]  This was on the verge.
[5417.54 --> 5419.60]  Of the invention of like the gas engine.
[5419.82 --> 5420.12]  And like.
[5420.26 --> 5420.58]  Yeah.
[5420.68 --> 5422.44]  I think it did actually change the world.
[5422.80 --> 5423.02]  Yeah.
[5423.10 --> 5423.38]  You know.
[5423.48 --> 5424.44]  Like it came to be.
[5425.00 --> 5425.70]  But like.
[5425.84 --> 5426.46]  In the moment.
[5426.56 --> 5428.20]  It totally didn't look like anything was moving.
[5428.64 --> 5428.82]  Yeah.
[5429.00 --> 5429.36]  Right.
[5429.64 --> 5430.08]  Well that.
[5430.30 --> 5430.82]  And that's.
[5430.88 --> 5431.02]  I mean.
[5431.02 --> 5431.36]  It's such a.
[5431.36 --> 5432.12]  It's such a great.
[5432.12 --> 5433.50]  I think it's important as technologists.
[5433.60 --> 5434.52]  That we retain that fundamental.
[5434.52 --> 5435.74]  Because that is a fundamental optimism.
[5435.98 --> 5436.14]  That.
[5436.26 --> 5436.58]  That.
[5437.14 --> 5437.84]  Better things.
[5438.06 --> 5439.12]  Are possible.
[5439.78 --> 5441.04]  Are you running for president anytime soon?
[5441.20 --> 5441.46]  I'm good.
[5441.56 --> 5442.00]  I mean.
[5442.82 --> 5443.30]  Do you.
[5443.42 --> 5445.38]  Are you looking for the thing that will crush me?
[5445.82 --> 5446.82]  My optimism.
[5447.48 --> 5447.98]  I don't know.
[5447.98 --> 5448.44]  I don't know how.
[5448.80 --> 5450.56]  There's a lot of optimizing to be done there though.
[5450.62 --> 5450.80]  Yeah.
[5450.84 --> 5451.04]  Okay.
[5451.20 --> 5451.32]  All right.
[5451.32 --> 5451.86]  Now I feel bad.
[5452.14 --> 5452.76]  Now I feel bad.
[5452.80 --> 5453.22]  I take it all back.
[5453.28 --> 5453.70]  I take it all back.
[5453.70 --> 5453.82]  Yeah.
[5453.82 --> 5454.10]  But just.
[5454.10 --> 5455.78]  I just want to do like the small things.
[5456.26 --> 5456.58]  Yeah.
[5456.94 --> 5457.94]  Keep doing the small things.
[5457.94 --> 5465.16]  I saw one of the projects that you worked on was a like single use drone to deliver
[5465.16 --> 5467.16]  into remote parts that would then be biodegradable.
[5467.72 --> 5468.04]  Yeah.
[5468.12 --> 5469.40]  That was at my.
[5469.58 --> 5474.64]  The work I was doing before the current company was we had a few different autonomous aircraft
[5474.64 --> 5480.24]  we shipped and that was for a specific DARPA program where the idea was to have a one
[5480.24 --> 5480.92]  time use.
[5481.16 --> 5481.36]  Yes.
[5481.78 --> 5484.98]  Biodegradable aircraft for like one off cargo delivery.
[5485.34 --> 5486.04]  That's dope.
[5486.24 --> 5487.72]  Had to be a lot of harder constraints.
[5487.72 --> 5488.08]  It's right.
[5488.18 --> 5488.44]  Exactly.
[5488.64 --> 5489.32]  It disappears.
[5490.00 --> 5490.22]  Sorry.
[5490.40 --> 5492.48]  I mean, I know it's not foosh because it like.
[5492.68 --> 5492.70]  No.
[5492.70 --> 5494.30]  I mean it was described as like folded cardboard.
[5494.30 --> 5495.08]  But it's just like cool.
[5495.54 --> 5497.42]  We used cardboard as a prototyping material.
[5497.64 --> 5502.28]  The ultimate material that we explored developing working with actually with a research lab on
[5502.28 --> 5508.62]  it was a lignin which is kind of like a papery fabric-y kind of material that was had biological
[5508.62 --> 5515.48]  seams and so you'd activate the fungal spores that would then start to consume the paper
[5515.48 --> 5516.44]  fabric material.
[5516.44 --> 5517.12]  That's dope.
[5517.12 --> 5522.86]  And the awesome thing is when the two different colonies of fungus meet, they basically go
[5522.86 --> 5523.36]  to war.
[5523.70 --> 5524.50]  Oh, wow.
[5524.64 --> 5529.22]  So there's this process called hypertrophy where they're like, you can't have this like
[5529.22 --> 5529.84]  calorie.
[5530.12 --> 5531.58]  We're going to digest it faster.
[5532.18 --> 5536.42]  And so then the, you know, paper lignin would just like extremely go to tatters.
[5536.86 --> 5537.56]  Oh, that's great.
[5537.56 --> 5542.88]  But there's like a slow growth period and then the colonies meet and then it like goes very
[5542.88 --> 5543.76]  quickly after that.
[5544.00 --> 5544.48]  That's cool.
[5544.52 --> 5550.24]  I mean, this is hard enough as it is to actually have a vehicle that will take a payload somewhere
[5550.24 --> 5555.42]  and then doing it with all different materials that have to disappear in a certain time frame.
[5555.42 --> 5557.00]  I can't even imagine.
[5557.00 --> 5557.16]  Yeah.
[5557.24 --> 5560.60]  I'd say like DARPA work, the idea is you, you know, kind of do some research.
[5560.60 --> 5565.10]  It's not where I like to live, which is like, it's a little higher up in the, you know, speculative.
[5565.42 --> 5570.22]  Like I like to actually ship things, but we did achieve the mission as described in terms
[5570.22 --> 5574.70]  of like exploring what was possible and producing a report about like something that they have a
[5574.70 --> 5580.66]  grading scale for like how real technology is, technology readiness levels, TRL levels, great Wikipedia page.
[5580.66 --> 5588.06]  And the idea was to get it to TRL three, which was what we accomplished at the same time on the same
[5588.06 --> 5588.34]  team.
[5588.48 --> 5593.06]  We were working on simultaneously working on a tethered autonomous helicopter.
[5593.38 --> 5596.78]  And so we were, we were making autonomous aircraft left and right.
[5596.96 --> 5597.30]  Oh my God.
[5597.56 --> 5599.28]  So much fun.
[5599.96 --> 5601.12]  Projects go on and on.
[5601.72 --> 5603.72]  Thanks for the opportunity to talk about them.
[5603.84 --> 5604.50]  Oh yeah.
[5604.70 --> 5605.52]  This has been great.
[5605.58 --> 5611.56]  It has been so much fun having you and love your, your disposition is so inspiring.
[5611.56 --> 5612.08]  I think.
[5612.34 --> 5613.82]  I'll talk, I'll take my optimism elsewhere.
[5613.96 --> 5614.32]  Yeah.
[5614.48 --> 5615.40]  No, it's great.
[5615.40 --> 5616.02]  It's great.
[5616.48 --> 5621.06]  And I think that just to the optimism and yet the responsibility about how you engineer
[5621.06 --> 5625.98]  and engineer in a way that is rigorous and yet forward looking, just very inspiring.
[5626.12 --> 5627.98]  So thank you very much for joining us today.
[5628.44 --> 5628.92]  Thank you all.
[5629.10 --> 5629.32]  Thank you.
[5629.54 --> 5629.86]  Thanks.
[5631.06 --> 5634.56]  You've been listening to On The Metal, tales from the hardware, software,
[5634.56 --> 5638.88]  interface for show notes, to learn more about our guests or to sign up for our mailing list,
[5638.88 --> 5640.88]  visit us at onthemetal.fm.
[5642.00 --> 5646.30]  On The Metal is a production of Oxide Computer Company and is recorded in the Oxide Garage
[5646.30 --> 5647.82]  in Oakland, California.
[5647.82 --> 5651.44]  To learn more about Oxide, visit us at oxide.computer.
[5651.84 --> 5655.98]  On The Metal is hosted by me, Brian Cantrell, along with Jess Fussell, and we are frequently
[5655.98 --> 5657.60]  joined by our boss, Steve Tuck.
[5657.82 --> 5661.76]  Our original and awesome theme music is by JJ Wiesler at Pollen Music Group.
[5662.00 --> 5665.70]  You can learn more about JJ and Pollen at pollenmusicgroup.com.
[5665.70 --> 5669.90]  We are edited and produced by Chris Hill and his crew at HumblePod.
[5670.26 --> 5674.46]  From Jess, from Steve, from me, and from all of us at Oxide Computer Company,
[5674.74 --> 5676.08]  thanks for listening to On The Metal.
[5676.08 --> 5706.06]  On The Metal.
[5706.08 --> 5736.06]  On The Metal.
