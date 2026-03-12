[0.00 --> 15.80]  Welcome to On The Metal, tales from the hardware software interface.
[16.04 --> 19.24]  I'm Brian Cantrell. With me, as always, is Jess Brisell. Hey, Jess.
[19.36 --> 19.74]  Hey, Brian.
[20.12 --> 22.52]  Joining us in the garage as well is our boss, Steve Tuck. Hey, Steve.
[22.68 --> 23.48]  Thank you for having me.
[24.04 --> 27.32]  All right. And Jess, you want to introduce who we've got in the garage today?
[27.32 --> 32.18]  Yeah. So today we have Jonathan Blow, who created The Witness and other games.
[32.26 --> 34.64]  And I played The Witness, so I'm actually a huge fan.
[35.94 --> 37.66]  Nice. Jonathan, welcome to the garage.
[37.78 --> 41.56]  Well, thanks. I did not create The Witness single-handedly, of course.
[41.68 --> 43.84]  We had a team of people making that.
[44.18 --> 51.10]  It's actually a classic thing in the video game industry is people like to identify things with one person.
[51.24 --> 54.78]  When it's actually, you know, it's hard. It's hard making those things.
[54.78 --> 58.28]  But I'm glad you played the game and hopefully got something out of it.
[58.86 --> 64.26]  So, Jonathan, it's great to have you here because we've had a bunch of folks here on the podcast
[64.26 --> 70.24]  who have spent their life at the hardware software interface delivering compute to other people.
[70.56 --> 76.10]  But you're actually using compute to deliver an actual experience to an end user.
[76.20 --> 77.14]  You've got a different perspective.
[77.52 --> 77.70]  Yeah.
[77.70 --> 81.50]  But very much trying to use hardware.
[82.22 --> 85.86]  And, you know, when you and I first met, one of the questions I asked you was,
[86.10 --> 91.62]  out of curiosity, how much hardware capacity would you use?
[91.76 --> 93.90]  And you told me, I will use anything.
[94.08 --> 96.18]  I will use as much as you give me.
[96.44 --> 99.54]  I've got use for, which I thought was really interesting.
[99.54 --> 100.48]  Yeah, for sure.
[101.32 --> 107.36]  Video games have plenty of ideas about things that we would like to do that we don't know how to do yet.
[108.08 --> 113.76]  Unfortunately, a lot of those ideas, like the more concrete flavors of those ideas are all in the same direction.
[113.76 --> 120.58]  Like visuals, you know, what things look like, which is, I don't know, like if video games like have a body,
[120.76 --> 127.00]  like we've been working out the biceps for a long time because those make money easily or something.
[127.00 --> 129.28]  But there's all sorts of other things too.
[129.62 --> 134.80]  Like if you look at games these days, there are a lot of areas that are not like directly the pixels on the screen
[134.80 --> 141.20]  that get underrepresented in terms of technical efforts so far, like animation or something, or even audio.
[141.38 --> 149.08]  Like the way audio processing happens in a video game is usually relatively low tech compared to the graphic.
[149.20 --> 150.70]  We're starting to beef it up, right?
[150.70 --> 157.34]  But the thing that makes games so hard, right, is there are many, many, many different categories of work
[157.34 --> 159.66]  that all have to come together to make the final thing.
[159.80 --> 167.26]  And every one of those is indefinitely, fractally complex if you get really serious about doing a good job at it.
[167.96 --> 172.74]  You know, and then of course, that just means bad things in terms of your to-do list
[172.74 --> 174.60]  if you're trying to build one of these things, right?
[175.00 --> 175.28]  Right.
[175.58 --> 178.34]  Well, it's interesting you said that about like the animation, for example,
[178.34 --> 183.56]  because I remember the like Prince of Persia when I was a kid was just mind-blowing.
[183.80 --> 187.04]  Even though the graphics were simple, the animation was so amazing.
[187.46 --> 191.94]  Well, so sometimes things are easy until they're not, right?
[191.96 --> 194.58]  So the thing about Prince of Persia was it's a 2D game.
[194.66 --> 196.38]  You're viewing it from the side, right?
[197.02 --> 201.56]  And the reason it was nicely animated was because it was one of the first games
[201.56 --> 205.28]  where the author actually cared about animation a great deal and had this idea.
[205.28 --> 209.80]  Like, let's actually draw out these things and get them into the game.
[210.34 --> 216.16]  But the technical job to be done back then by modern standards was relatively simple.
[216.82 --> 220.00]  Back then it was a little bit harder because, you know, less capable computers
[220.00 --> 222.74]  so you had to work harder to like get all these pixels on the screen and stuff.
[222.88 --> 227.28]  But, you know, you're essentially, you've got a 2D sprite and you're flipping through it, right?
[227.32 --> 230.54]  And you just make sure the content of that sprite is really good.
[230.54 --> 231.70]  That's like job number one.
[231.78 --> 235.44]  And then job number two is just sort of the timing of when things happen.
[235.56 --> 237.00]  You just try to make sure that's good, right?
[237.48 --> 242.68]  So now in a current game, you know, you might have a character moving around in a 3D world.
[243.54 --> 246.80]  And so objects are 3D, so they're more complicated.
[247.22 --> 248.48]  They have a lot more degrees of freedom.
[249.04 --> 254.16]  You expect them to move like different parts of an object to move separately.
[254.34 --> 258.20]  It's a very different thing from having a sprite with some data baked in
[258.20 --> 259.60]  that you're just flipping pages on, right?
[259.60 --> 262.98]  And in general, because of this increased complexity,
[263.52 --> 267.46]  you have more of an interaction between things in their environments
[267.46 --> 270.10]  and you can't really get away with the same stuff anymore.
[270.22 --> 273.76]  So in Prince of Persia, I'm having a little bit of difficulty
[273.76 --> 276.12]  calling up exactly what the screen looks like.
[276.18 --> 280.98]  But in all games of this kind, you sort of treat the character as a box or something, right?
[281.08 --> 283.80]  And you do collision with the environment by saying like,
[283.86 --> 287.06]  okay, does this box overlap with other boxes, for example?
[287.06 --> 290.44]  Some games would do pixel accurate collision detection,
[290.64 --> 292.98]  but sometimes you don't actually want that, right?
[293.02 --> 294.90]  I'm not sure exactly which one this game did,
[295.02 --> 297.48]  but either version of that is a relatively simple problem.
[297.92 --> 301.82]  In 3D, you can't really do that for various reasons.
[301.92 --> 304.74]  But like if I'm walking around on the ground
[304.74 --> 307.62]  and there's like a tiny rock on the ground that's kind of sticking up
[307.62 --> 310.16]  and like I'm colliding with it and I can't go,
[310.16 --> 313.40]  oh, it looks to a player like there's just some kind of invisible wall.
[313.54 --> 315.20]  Like I know it feels terrible, right?
[315.20 --> 315.64]  Right, right.
[315.64 --> 320.86]  And so just the degree of work that you have to do is just a lot different.
[321.20 --> 322.78]  I'm not explaining it well enough yet,
[322.80 --> 325.36]  but it would probably take like an hour to just explain that point.
[325.36 --> 327.32]  And work from a computational work?
[328.60 --> 329.04]  Yeah.
[329.58 --> 331.52]  So, I mean, just taking something like,
[331.76 --> 335.00]  like let's detect a collision between something and its environment,
[335.00 --> 336.56]  as an example, right?
[337.08 --> 338.64]  Back in old style computers,
[339.02 --> 342.64]  there were ways of accelerating that,
[342.68 --> 344.32]  even on home computers, right?
[344.36 --> 345.28]  Like I think the Atari,
[345.40 --> 347.04]  I never had like an Atari home computer.
[347.46 --> 347.76]  You never?
[347.90 --> 348.22]  Oh, really?
[348.32 --> 348.46]  Wow.
[348.64 --> 353.10]  No, I was a Commodore 64 TRS-80 guy.
[353.22 --> 353.44]  Okay.
[353.44 --> 354.82]  When I was in high school,
[355.50 --> 357.58]  which is not, you know, compared to your previous guests,
[357.72 --> 359.58]  you know, that's recent history.
[359.80 --> 362.42]  Well, but you and I are all of the same vintage.
[362.64 --> 363.66]  So this, I mean,
[363.66 --> 366.18]  I, I, but I did have an Atari 2600.
[366.76 --> 368.14]  Oh, a 2600 I had,
[368.20 --> 370.18]  but I mean like the, the, the computers.
[370.54 --> 370.80]  The 800.
[370.98 --> 372.66]  The 800 and whatever the other one was.
[372.70 --> 372.84]  Yeah.
[373.26 --> 376.08]  So those, I believe had like,
[376.70 --> 378.72]  like collision registers you could query,
[378.86 --> 379.42]  where you would like,
[379.64 --> 380.62]  you would like draw a sprite
[380.62 --> 383.84]  and then you could ask what pixels of this sprite
[383.84 --> 385.72]  hit pixels of this other sprite or something.
[385.80 --> 385.92]  Right.
[385.92 --> 387.18]  And that was a way of,
[387.18 --> 389.64]  of speeding up this kind of a problem.
[389.64 --> 390.04]  Right.
[390.08 --> 390.28]  Okay.
[390.28 --> 392.56]  And that works fine if you're doing something simple.
[392.56 --> 392.94]  The Atari 800 had that.
[392.94 --> 394.16]  And something had that.
[394.16 --> 394.86]  Yeah, no, that's fine.
[394.92 --> 395.42]  Yeah, no, I just,
[395.74 --> 397.06]  a friend of mine had the Atari 800.
[397.24 --> 397.88]  It was kind of an,
[398.26 --> 400.34]  maybe actually the Commodore 64 had that.
[400.40 --> 400.72]  I don't know.
[400.74 --> 401.04]  Yeah, right.
[401.08 --> 401.42]  No, I was.
[401.46 --> 402.18]  But, but that was,
[402.32 --> 404.34]  that was the,
[404.66 --> 405.22]  it's just to,
[405.32 --> 407.26]  just to say that that was the scale of,
[407.48 --> 409.00]  of technical problem at that time.
[409.00 --> 409.04]  Right.
[409.04 --> 409.54]  It was either,
[409.54 --> 411.30]  it was either box versus,
[411.80 --> 414.04]  people didn't even really do box versus box that much.
[414.04 --> 415.96]  It was either box versus extents
[415.96 --> 417.34]  or like sprite versus sprite.
[417.42 --> 418.96]  I think Commodore 64 did have that.
[419.56 --> 421.22]  This is showing you how much I remember.
[421.22 --> 422.74]  Like I programmed that thing for years.
[423.32 --> 424.84]  I don't remember even what,
[424.92 --> 425.76]  what it did.
[426.14 --> 426.58]  So,
[427.04 --> 427.32]  you know,
[427.34 --> 428.14]  these days is,
[428.28 --> 428.90]  it's a very,
[429.00 --> 429.22]  very,
[429.30 --> 430.08]  very different problem.
[430.18 --> 430.82]  So first of all,
[431.24 --> 432.86]  before you're even going to collide something,
[432.86 --> 434.34]  you need to like have something.
[434.64 --> 434.90]  Right.
[434.90 --> 435.88]  So like,
[435.92 --> 436.32]  let's say,
[436.38 --> 438.76]  let's say I have a person walking around,
[438.80 --> 439.72]  like a lot of games do.
[440.22 --> 440.82]  How do you,
[440.82 --> 441.52]  how do you do that?
[441.90 --> 442.14]  Right.
[442.58 --> 442.96]  Well,
[443.24 --> 444.20]  you could imagine,
[444.36 --> 444.84]  for example,
[444.94 --> 446.74]  and the earliest 3d games do this.
[446.78 --> 450.32]  You could example that much like you do sprites by having like a flip book of images,
[450.32 --> 458.24]  you could have like some poses of a person doing a walk and you somehow represent the geometry and all these poses and you flip through it.
[458.24 --> 458.46]  Right.
[458.92 --> 459.82]  Very early game,
[460.06 --> 460.74]  3d games,
[461.54 --> 462.96]  like Quake one did this,
[463.02 --> 463.40]  for example,
[463.40 --> 464.82]  it doesn't do it anymore.
[464.82 --> 465.36]  Like modern,
[465.48 --> 465.68]  well,
[466.34 --> 466.74]  sort of,
[467.14 --> 467.56]  but anyway,
[467.72 --> 469.14]  that has a lot of drawbacks,
[469.32 --> 469.44]  right?
[469.50 --> 469.66]  Okay.
[469.66 --> 470.82]  So how do you represent the geometry?
[471.00 --> 471.10]  Well,
[471.10 --> 472.24]  you have points in space.
[472.36 --> 474.66]  So there's like a 3d coordinate for every vertex.
[474.90 --> 478.34]  And then you have what's called an index array,
[478.44 --> 479.36]  which is just like,
[479.42 --> 481.56]  let's define a bunch of triangles or,
[481.56 --> 483.08]  or back then we were all like,
[483.12 --> 485.30]  maybe you should have higher order primitives or something,
[485.30 --> 486.74]  but it's still triangles today,
[486.78 --> 487.06]  mostly.
[487.06 --> 488.20]  So you say like,
[488.26 --> 488.42]  okay,
[488.44 --> 491.70]  these three vertices have a triangle and these three and these three and these three.
[491.88 --> 492.20]  And,
[492.20 --> 495.54]  and that tells you what the geometry is.
[495.58 --> 495.88]  And then,
[495.92 --> 496.50]  you know,
[496.50 --> 497.92]  you can have some additional properties like,
[498.04 --> 498.16]  Oh,
[498.62 --> 500.70]  if you want to vary the color over the surface,
[500.70 --> 502.02]  we have this thing called a texture map.
[502.02 --> 503.08]  And then each,
[503.20 --> 506.00]  each vertex can have an additional two coordinates,
[506.00 --> 510.10]  which is like it's positions in the 2d space of this image.
[510.10 --> 510.38]  Right.
[510.40 --> 512.68]  And that allows you to sort of stretch an image over it,
[512.68 --> 515.12]  which looks too bad if you stretch it too much and stuff.
[515.12 --> 516.12]  And so,
[516.32 --> 518.04]  so you represent the geometry that way.
[518.04 --> 518.50]  And then,
[518.60 --> 518.92]  okay,
[519.10 --> 520.68]  how do we animate it?
[520.76 --> 520.98]  Well,
[521.10 --> 524.38]  playing back these sets of coordinates is a,
[524.46 --> 525.44]  it's a huge amount of data.
[525.44 --> 527.58]  And B has a lot of drawbacks.
[527.58 --> 530.72]  Like it's ill-defined between frames.
[530.72 --> 533.52]  And if you try to just straightforwardly interpolate the frames,
[533.52 --> 534.28]  you get these weird,
[534.52 --> 536.60]  stretchy claymation looking guys all the time,
[536.66 --> 537.58]  which you don't usually want.
[537.58 --> 540.30]  And so we do this thing called skeletal animation,
[540.68 --> 542.90]  which is you start defining these things called bones,
[543.00 --> 545.82]  which are essentially for people with a math background.
[545.96 --> 551.36]  They're like a linear transformation that maps one set of coordinates in 3d space to another one.
[551.36 --> 552.50]  And it varies over time.
[552.50 --> 556.78]  And so then you store the position and orientation of like the root of each bone.
[556.78 --> 559.54]  And that's something that you can interpolate over time.
[559.54 --> 564.44]  And then the coordinates attached to that will like rotate through space and stuff.
[564.52 --> 564.76]  Anyway,
[565.00 --> 567.10]  this is becoming a really long explanation,
[567.24 --> 568.98]  but that's just even to have the thing,
[569.20 --> 569.38]  right?
[569.42 --> 570.62]  The thing that used to be a sprite.
[570.88 --> 571.08]  Right.
[571.36 --> 572.30]  Now is this thing.
[572.36 --> 572.58]  Right.
[572.76 --> 575.58]  Which is like way more data and way more complicated to talk about.
[575.64 --> 577.86]  And we haven't even talked about rendering this efficiently,
[578.00 --> 578.56]  which by the way,
[578.58 --> 579.26]  is not that easy.
[579.40 --> 579.62]  Right.
[580.16 --> 581.60]  It doesn't sound like it would be hard,
[581.70 --> 581.82]  but,
[581.90 --> 582.98]  but it starts to get hard.
[582.98 --> 585.50]  And so then if you wanted to say like,
[585.68 --> 585.96]  you know,
[586.04 --> 586.24]  is,
[586.32 --> 588.32]  is my arm going to collide with this table?
[588.72 --> 588.88]  Right.
[589.30 --> 589.70]  Well,
[590.30 --> 592.44]  you need to start thinking about things like how,
[592.92 --> 595.08]  how accurate does that collision need to be?
[595.14 --> 595.80]  For example.
[596.06 --> 596.28]  Right.
[596.68 --> 597.24]  Do I,
[597.46 --> 601.10]  is it good enough if I just represent around my hand with like a,
[601.10 --> 603.06]  a relatively conservative sphere that,
[603.06 --> 604.74]  that captures all the volume.
[604.84 --> 606.58]  And then if it comes close to the table,
[606.58 --> 608.48]  if there's a tiny gap down there,
[608.52 --> 609.70]  can I see that or not?
[609.76 --> 610.10]  Right.
[610.22 --> 611.40]  In a first person game,
[611.40 --> 612.80]  you might see it if the gap is big,
[612.80 --> 614.86]  but in a third person game where the camera's way back,
[614.90 --> 616.14]  you maybe don't care about that.
[616.18 --> 616.38]  Right.
[616.90 --> 618.54]  Hand against table is a weird example.
[618.70 --> 620.46]  It's not really something we would do in a game that much,
[620.50 --> 622.14]  but like character against a wall or something.
[622.24 --> 622.38]  Right.
[622.76 --> 623.08]  But,
[623.32 --> 624.42]  you know,
[624.48 --> 624.70]  and then,
[624.70 --> 625.56]  and then you start saying,
[625.66 --> 625.82]  well,
[625.90 --> 626.10]  okay,
[626.10 --> 630.96]  so maybe I had these invisible boxes around all these bones that I was just
[630.96 --> 631.56]  talking about.
[631.56 --> 634.36]  So there's like one on my forearm and one on my wrist and one on my shoulder.
[634.98 --> 635.26]  And then,
[635.38 --> 637.58]  so a character might have 30 or 40 of these.
[637.70 --> 638.76]  They're animating all the time.
[638.76 --> 642.50]  And then I need to sort of do some geometric intersection operation
[642.50 --> 642.90]  to,
[642.96 --> 645.82]  to intersect the arm with the table.
[645.96 --> 646.36]  Right.
[646.40 --> 649.66]  Except that's not good enough because if my arm is moving fast,
[649.68 --> 650.78]  it might've gone through the table.
[650.78 --> 653.52]  Like it might've been above the table on one frame and below the table on
[653.52 --> 654.10]  another frame.
[654.28 --> 658.74]  So then you have to like do some kind of time interpolated collision
[658.74 --> 660.10]  operation or something,
[660.22 --> 662.10]  have some way to make sure that you don't skip that.
[662.10 --> 666.98]  And then the problem with all that is once you start doing math like this,
[667.10 --> 669.36]  it's hard to do that in a frame rate independent way.
[669.58 --> 669.66]  Right.
[669.72 --> 672.52]  So what if I'm running this thing on one platform and it's kind of slow and
[672.52 --> 675.70]  I'm getting like 20 frames per second and someone else is running something
[675.70 --> 677.34]  at 240 frames per second,
[677.50 --> 679.74]  which is not uncommon number.
[679.82 --> 683.54]  That's like actual gaming monitors these days are 240 FPS.
[683.54 --> 688.30]  Does the thing that I programmed feel different or the same under those two
[688.30 --> 688.80]  conditions?
[689.00 --> 689.14]  You know,
[689.18 --> 689.78]  like the way,
[689.88 --> 691.90]  the way that you might write a physics equation,
[692.06 --> 692.92]  for example,
[693.42 --> 693.72]  you know,
[693.74 --> 695.20]  like just doing like a Newtonian,
[695.30 --> 695.38]  Oh,
[695.42 --> 697.88]  this thing is moving around and it's being affected by whatever.
[697.88 --> 698.26]  Right.
[698.28 --> 701.22]  So you might update the position based on the velocity,
[701.68 --> 701.86]  right.
[701.92 --> 705.60]  Update the velocity based on the acceleration and then apply some friction.
[705.60 --> 705.90]  Like,
[706.00 --> 706.12]  Oh,
[706.14 --> 707.16]  it's in air or water.
[707.28 --> 709.96]  So we're going to multiply its velocity down.
[710.24 --> 710.98]  And then,
[711.40 --> 711.92]  you know,
[711.92 --> 714.96]  you can just imagine those are relatively straightforward steps that anyone who
[714.96 --> 718.04]  even hasn't done games could probably imagine how to do pretty easily.
[718.20 --> 721.90]  The problem is the behavior of that thing that you come up with will vary
[721.90 --> 725.20]  tremendously based on what your update rate is.
[725.38 --> 727.36]  And so then you have to start having a strategy for that.
[727.42 --> 727.54]  Like,
[727.58 --> 730.70]  do we start trying to make the math more serious and more frame rate
[730.70 --> 731.14]  independent?
[731.72 --> 734.12]  Do we use like a more serious numerical integrator?
[734.66 --> 734.88]  Right.
[735.68 --> 736.74]  Let's not go into that,
[736.88 --> 737.94]  but it's just not,
[738.14 --> 738.74]  it's not simple.
[738.86 --> 738.96]  Right.
[739.18 --> 741.90]  And all of this is like to do the thing that you can do.
[741.90 --> 743.82]  That's a thing that you used to be able to get in hardware.
[744.02 --> 744.24]  Like,
[744.44 --> 744.54]  Oh,
[744.60 --> 746.40]  this sprite overlaps this one or not.
[746.52 --> 746.66]  Right.
[748.18 --> 749.00]  And so.
[749.56 --> 749.92]  Yeah.
[750.10 --> 751.24]  So how much do you,
[751.36 --> 756.04]  are you able to kind of use von Neumann computation for that versus say,
[756.12 --> 756.58]  special purpose,
[756.62 --> 756.98]  a hardware,
[757.14 --> 758.78]  special purpose accelerators and how much of that.
[759.00 --> 761.12]  And I assume that boundary has shifted over time.
[761.12 --> 762.40]  I mean,
[762.40 --> 762.42]  I mean,
[762.58 --> 765.22]  it's complicated,
[765.34 --> 765.52]  right?
[765.76 --> 766.08]  So,
[766.50 --> 767.34]  so in principle,
[767.66 --> 769.28]  as far as I know,
[770.04 --> 770.36]  okay,
[770.36 --> 772.54]  the main kind of acceleration that we might use today,
[772.54 --> 772.98]  right?
[773.16 --> 777.52]  Is a typical consumer PC or a game console has a,
[777.58 --> 779.36]  has a pretty serious GPU,
[779.64 --> 779.86]  right?
[779.94 --> 781.10]  Graphics processor on it.
[781.58 --> 784.30]  That probably has more transistors in the CPU,
[784.54 --> 784.74]  right?
[784.86 --> 785.06]  Yes.
[785.16 --> 785.42]  But,
[785.48 --> 786.00]  but it's,
[786.08 --> 788.82]  it's set up to do a different kind of a job.
[788.96 --> 791.26]  I don't really think of it as non von Neumann,
[791.64 --> 791.94]  right?
[792.12 --> 792.74]  It's just,
[793.30 --> 796.46]  it just wants to have a lot more threads working than a typical,
[796.72 --> 797.40]  you know,
[797.46 --> 798.64]  a typical CPU,
[798.76 --> 798.96]  right?
[799.76 --> 800.16]  Normally,
[800.40 --> 801.96]  if we were going to make a game,
[802.76 --> 808.24]  we don't really conceptualize things very differently.
[808.24 --> 809.56]  If they're going to run on the GPU,
[809.78 --> 809.96]  like,
[810.50 --> 813.36]  like we always could see how we could write them for the CPU and how we
[813.36 --> 814.16]  could write them for the GPU.
[814.16 --> 814.26]  I mean,
[814.26 --> 815.72]  that might change more over time,
[815.82 --> 816.28]  you know,
[816.28 --> 816.56]  as,
[816.68 --> 819.32]  as the model continues to diverge.
[819.36 --> 819.66]  Right.
[819.78 --> 820.14]  But,
[820.20 --> 821.42]  you know,
[821.44 --> 826.72]  usually like GPU programming is more about doing annoying stuff to
[826.72 --> 830.76]  satisfy the arbitrary constraints that are set forth for you that
[830.76 --> 832.56]  involved in just talking to the GPU.
[832.74 --> 833.22]  So like,
[833.22 --> 833.60]  I've got to,
[833.60 --> 836.80]  I've got to feed it my data and that has to be efficient.
[837.00 --> 837.48]  Yeah.
[837.48 --> 840.88]  And I have to get results back somehow.
[840.88 --> 842.16]  And that has to be efficient.
[842.16 --> 842.60]  And,
[842.60 --> 842.82]  and,
[842.82 --> 843.72]  and it's just,
[843.84 --> 844.98]  there's this really weird,
[845.08 --> 845.40]  right?
[846.62 --> 848.44]  CPU talking to GPU is slow.
[848.54 --> 850.50]  GPU talking back to CPU is slow.
[850.72 --> 851.26]  So you,
[851.58 --> 852.82]  once something goes there,
[853.28 --> 854.58]  like once something goes to Vegas,
[854.68 --> 855.48]  it stays in Vegas.
[855.72 --> 855.82]  Right.
[855.94 --> 856.18]  Right.
[856.32 --> 856.44]  Right.
[856.44 --> 857.04]  Um,
[857.14 --> 861.04]  but then a lot of that is not necessarily hardware constraints.
[861.04 --> 863.14]  A lot of it is often like software constraints,
[863.14 --> 863.40]  like,
[863.46 --> 866.02]  cause the APIs didn't take that seriously enough or,
[866.02 --> 866.46]  or whatever.
[866.66 --> 867.66]  But then also,
[867.88 --> 872.26]  this is the one part of what I do that's still changing substantially
[872.26 --> 876.24]  rapidly over time is like GPUs keep improving in their capabilities.
[876.24 --> 878.34]  So it's hard to like say anything definitive.
[878.60 --> 878.86]  Right.
[878.86 --> 879.60]  You know,
[879.84 --> 882.32]  the fact that we do have special purpose compute,
[882.40 --> 882.48]  I mean,
[882.52 --> 882.74]  to me,
[882.76 --> 886.52]  it's interesting because games have driven so much.
[886.80 --> 887.36]  I mean,
[887.36 --> 891.32]  obviously it drove us as kids and I think it still drives kids in terms of
[891.32 --> 893.64]  it's their first exposure to computing.
[893.64 --> 895.44]  I think for most computer scientists,
[895.82 --> 898.50]  it's the first thing they write is a game at some level.
[898.70 --> 898.82]  Right.
[898.94 --> 899.48]  It's the,
[900.00 --> 900.22]  I don't know.
[900.22 --> 900.36]  I think,
[900.46 --> 901.46]  I think that's still true.
[901.64 --> 901.94]  I don't know.
[902.08 --> 902.44]  Jess,
[902.48 --> 903.16]  is that true for you?
[903.30 --> 903.32]  I mean,
[903.32 --> 903.62]  I assume.
[903.64 --> 904.76]  Choose your own adventure games.
[904.96 --> 906.48]  The text flow to ease.
[906.80 --> 907.20]  Right.
[907.30 --> 907.62]  Exactly.
[908.38 --> 908.76]  So,
[908.86 --> 909.00]  I mean,
[909.14 --> 909.30]  the,
[909.46 --> 911.34]  and then from the hardware perspective,
[911.34 --> 912.58]  we develop hardware to,
[912.68 --> 912.92]  I mean,
[913.02 --> 914.72]  you would not have,
[914.80 --> 914.98]  I mean,
[915.02 --> 919.18]  I think that deep learning cannot alone support the GP,
[919.26 --> 919.54]  GPU,
[919.68 --> 919.82]  right?
[919.82 --> 922.82]  The GPU needed that kind of much broader use,
[922.82 --> 924.38]  use case of,
[924.48 --> 924.96]  I would assume.
[925.40 --> 925.54]  I,
[925.70 --> 926.06]  well,
[926.22 --> 927.04]  I,
[927.04 --> 928.26]  I feel like what happened,
[928.34 --> 928.60]  and again,
[928.66 --> 928.80]  I'm,
[928.88 --> 931.62]  it's not my job to like analyze the business of these things.
[931.62 --> 931.86]  Right.
[931.88 --> 932.10]  But,
[932.54 --> 935.96]  but I feel like what happened is that games launched GPUs and are the
[935.96 --> 937.72]  reason that we had GPUs.
[938.10 --> 938.50]  And,
[938.72 --> 939.24]  and like I said,
[939.28 --> 940.96]  games always want more computation.
[940.96 --> 941.32]  Right.
[941.32 --> 941.54]  And,
[941.56 --> 945.92]  and that's why there was this race because whoever made the faster GPU
[945.92 --> 947.04]  could,
[947.14 --> 949.14]  could show demonstrably better results.
[949.22 --> 950.04]  It wasn't just a number.
[950.06 --> 950.38]  It's like,
[950.40 --> 951.04]  look at the screen.
[951.14 --> 951.88]  This is actually,
[952.10 --> 952.68]  this is better.
[952.68 --> 953.22]  This is better.
[953.34 --> 953.50]  Right.
[953.58 --> 953.76]  Yeah.
[954.04 --> 954.22]  And,
[954.34 --> 954.74]  and that,
[954.90 --> 956.32]  that happened for a number of years,
[956.32 --> 958.56]  but I feel like now the,
[958.64 --> 961.04]  the deep learning people and the Bitcoin miners,
[961.32 --> 962.38]  certainly the Bitcoin miners,
[962.52 --> 967.30]  you put those two sets of people together and they're probably a lot
[967.30 --> 968.82]  bigger than the,
[969.00 --> 969.74]  or the game,
[969.86 --> 970.48]  the game market.
[970.48 --> 971.32]  I feel like,
[971.40 --> 972.32]  but I don't know for sure.
[972.50 --> 972.66]  Yeah.
[972.70 --> 973.62]  I don't know for sure either.
[973.72 --> 974.92]  Cause I feel like when the,
[975.12 --> 979.56]  certainly I think that we saw that the cryptocurrency mining was more,
[979.66 --> 981.90]  was playing more of a role in that special purpose compute than anyone
[981.90 --> 983.76]  realized when it kind of disappeared.
[983.82 --> 984.38]  And all of a sudden it's like,
[984.44 --> 984.52]  wow,
[984.58 --> 987.30]  where did a lot of the demand disappeared when,
[987.46 --> 988.06]  and that would,
[988.18 --> 988.46]  I mean that,
[988.46 --> 992.30]  that demand so correlated to the kind of the price of various cryptocurrencies.
[992.76 --> 992.94]  I mean,
[992.94 --> 993.12]  it's,
[993.12 --> 994.32]  it's kind of,
[994.32 --> 997.18]  so it's hard to know how the stuff is being used,
[997.18 --> 997.36]  right?
[997.38 --> 997.54]  I mean,
[997.54 --> 998.58]  it's like it's sold,
[998.70 --> 1001.06]  but you don't actually know how people are necessarily using it.
[1001.56 --> 1002.82]  I'm sure Nvidia knows,
[1002.88 --> 1003.06]  right?
[1003.12 --> 1003.94]  It's like they,
[1004.04 --> 1004.28]  they,
[1004.76 --> 1005.84]  sometimes I feel it's hard,
[1005.92 --> 1006.30]  honestly,
[1006.54 --> 1008.14]  especially if things are going well,
[1008.60 --> 1010.52]  it can be hard to know how these things are being used.
[1010.52 --> 1010.72]  You know,
[1010.72 --> 1011.90]  who's buying them roughly,
[1012.18 --> 1015.70]  but you actually don't know sometimes how these things are being used.
[1015.70 --> 1017.96]  And if they're being used efficiently and if they're,
[1018.10 --> 1018.24]  I mean,
[1018.26 --> 1018.68]  I think it's,
[1019.06 --> 1019.88]  that's why it's,
[1019.88 --> 1023.24]  it's always interesting when you actually get to,
[1023.38 --> 1023.52]  I mean,
[1023.54 --> 1026.84]  you're actually trying to connect what you can do in hardware to actually,
[1026.98 --> 1031.24]  and deliverable as opposed to for its own sake.
[1031.38 --> 1031.64]  You know,
[1031.66 --> 1032.48]  it's an interesting point.
[1032.56 --> 1033.32]  So I was just thinking,
[1033.46 --> 1033.66]  you know,
[1033.66 --> 1034.14]  I just said,
[1034.38 --> 1035.34]  I'm sure Nvidia knows,
[1035.42 --> 1035.60]  right?
[1035.70 --> 1035.86]  Right.
[1035.94 --> 1039.54]  So their most recent card was the Nvidia 2080 TI.
[1039.54 --> 1044.60]  Like a classic thing about video game hardware is like,
[1044.78 --> 1048.04]  it's just ridiculous strings of numbers and letters,
[1048.16 --> 1048.36]  right?
[1048.54 --> 1049.80]  That make no sense.
[1049.88 --> 1050.82]  Unless you've been following it.
[1051.10 --> 1051.38]  So,
[1051.52 --> 1053.54]  so their whole marketing for that was like,
[1053.60 --> 1056.60]  it has this capability to do onboard ray tracing,
[1056.80 --> 1058.28]  like RTX was their thing.
[1058.32 --> 1058.48]  Right.
[1058.52 --> 1058.86]  And it's,
[1059.08 --> 1059.60]  it's honestly,
[1059.66 --> 1063.94]  it's a little too early to try and do ray traced rendering in games.
[1064.02 --> 1064.90]  We do a different thing.
[1064.98 --> 1066.04]  Usually you could,
[1066.04 --> 1070.60]  you could maybe add it a little bit into scenes and get a little bit of a bonus,
[1070.60 --> 1071.04]  but it's,
[1071.04 --> 1072.08]  it's a little early yet,
[1072.12 --> 1072.64]  but that's,
[1073.18 --> 1073.40]  you know,
[1073.40 --> 1076.44]  the way this always works is you start and it's a little early in the next
[1076.44 --> 1076.90]  generation.
[1077.16 --> 1078.62]  It's less early.
[1078.62 --> 1080.04]  And then eventually it's the thing.
[1080.18 --> 1080.28]  So,
[1080.40 --> 1082.12]  so we're sort of on the leading edge of that,
[1082.16 --> 1082.46]  I think.
[1082.46 --> 1083.76]  But the point is that they're,
[1083.80 --> 1085.80]  they're marketing behind that card.
[1086.24 --> 1087.74]  Was this ray tracing thing,
[1087.90 --> 1091.00]  which like deep learning people don't care about and Bitcoin miners don't care
[1091.00 --> 1091.16]  about.
[1091.22 --> 1092.26]  That's just a game thing.
[1092.26 --> 1093.64]  So they must still think it's important.
[1093.90 --> 1094.14]  Yes.
[1094.20 --> 1094.52]  Oh yeah.
[1094.52 --> 1094.68]  Yeah.
[1094.80 --> 1094.96]  Yeah.
[1094.96 --> 1095.40]  I think it's,
[1095.48 --> 1096.28]  I think that the,
[1096.28 --> 1102.54]  the consumer market drives more broad compute innovations than I think anyone really wants
[1102.54 --> 1103.12]  to talk about.
[1103.64 --> 1103.92]  I mean,
[1103.94 --> 1104.66]  how much of,
[1104.72 --> 1104.84]  I mean,
[1105.16 --> 1106.62]  I think it's a bit of an open question.
[1106.62 --> 1107.06]  And the,
[1107.06 --> 1109.22]  the fact that we have been driven to,
[1109.42 --> 1111.54]  to more expensive processes at,
[1111.66 --> 1113.26]  at smaller and smaller feature sizes,
[1113.26 --> 1115.30]  how much of that has been driven by cell phones?
[1115.60 --> 1116.08]  You know,
[1116.08 --> 1117.68]  how much of that has been driven by,
[1117.78 --> 1118.46]  by mobile?
[1118.56 --> 1118.72]  I mean,
[1118.72 --> 1119.34]  I think it's,
[1119.54 --> 1122.68]  so we need those broader markets honestly to drive it.
[1122.68 --> 1124.78]  And that's why I think it's particularly interesting about how,
[1124.90 --> 1125.46]  you know,
[1125.46 --> 1127.96]  as someone who sits in that broader market,
[1128.60 --> 1132.38]  how you use these underlying compute resources.
[1132.74 --> 1134.36]  So you use the cell or you,
[1134.46 --> 1135.06]  you were,
[1135.36 --> 1135.66]  yeah.
[1136.78 --> 1140.88]  That's such an interesting kind of experiment that was performed.
[1141.42 --> 1141.90]  Yeah.
[1142.04 --> 1143.06]  So the cell processor,
[1143.40 --> 1144.94]  we should probably talk about what it was.
[1144.94 --> 1145.12]  Yeah.
[1145.12 --> 1146.56]  So there was this weird time.
[1147.16 --> 1147.74]  And again,
[1147.74 --> 1148.38]  this is my,
[1148.38 --> 1152.86]  my viewpoint of it as somebody who was not involved in the CPU world very directly.
[1153.18 --> 1153.30]  Right.
[1153.56 --> 1154.02]  But just,
[1154.06 --> 1154.68]  you know,
[1154.90 --> 1156.38]  peripherally working on software and stuff.
[1156.38 --> 1159.48]  But we had this weird time where the way processors were,
[1160.40 --> 1167.38]  the way that it looked like was the best way to increase performance for general purpose processors was to give them deeper and deeper pipelines.
[1168.06 --> 1168.32]  Right.
[1168.32 --> 1168.46]  Right.
[1168.48 --> 1169.30]  Because they had to,
[1169.34 --> 1170.60]  they had to predict more.
[1170.70 --> 1171.14]  Right.
[1171.90 --> 1172.30]  And,
[1172.36 --> 1173.06]  you know,
[1173.06 --> 1174.64]  that obviously starts eating a lot of power.
[1174.64 --> 1176.38]  It's expensive and all this.
[1176.46 --> 1177.60]  So people started looking at like,
[1177.68 --> 1177.78]  what,
[1177.94 --> 1182.30]  what can we do if we take some of that die space that's being reserved for,
[1182.30 --> 1182.74]  you know,
[1183.70 --> 1185.00]  speculative execution.
[1185.36 --> 1185.50]  Right.
[1185.50 --> 1185.70]  Right.
[1185.90 --> 1186.18]  And,
[1186.24 --> 1189.86]  and just try to do something more straightforward with it.
[1189.90 --> 1191.74]  And so the cell was an attempt to say,
[1191.82 --> 1192.10]  okay,
[1192.56 --> 1192.96]  for,
[1193.06 --> 1194.96]  for what we're paying to do all this stuff,
[1195.14 --> 1198.72]  you could have a number of like much faster,
[1199.00 --> 1200.50]  much tighter cores.
[1200.86 --> 1201.32]  Simpler cores.
[1201.56 --> 1201.96]  Simpler.
[1202.14 --> 1203.38]  They'd have their own memory.
[1203.56 --> 1203.86]  Right.
[1203.90 --> 1205.50]  So they don't spend a lot of time waiting on memory,
[1205.56 --> 1208.38]  which is one of the reasons that you need speculative execution for.
[1208.60 --> 1209.34]  The memory wall.
[1209.46 --> 1209.60]  Right.
[1209.60 --> 1210.46]  And so,
[1211.02 --> 1211.30]  you know,
[1211.34 --> 1212.14]  we'll just do that.
[1212.14 --> 1215.32]  And then you'll write like little sub programs that you kind of upload to
[1215.32 --> 1215.94]  these things.
[1215.94 --> 1216.34]  Right.
[1216.64 --> 1217.22]  And run that.
[1217.38 --> 1217.40]  Well,
[1217.50 --> 1217.74]  you know,
[1217.80 --> 1218.12]  DMA,
[1218.26 --> 1218.42]  right.
[1218.44 --> 1219.04]  It's like not,
[1219.40 --> 1221.36]  not over a network.
[1221.48 --> 1221.70]  Well,
[1222.06 --> 1224.96]  a project idea did involve that,
[1225.06 --> 1225.20]  but,
[1225.26 --> 1226.02]  and,
[1226.06 --> 1226.90]  and the theory was,
[1227.00 --> 1227.98]  you know,
[1227.98 --> 1228.18]  you,
[1228.18 --> 1229.40]  you write a bunch of tight loops.
[1229.40 --> 1230.52]  They go to these things,
[1231.10 --> 1231.30]  you know,
[1231.36 --> 1231.94]  you run them,
[1232.04 --> 1233.04]  you get the results back,
[1233.08 --> 1235.88]  and then you sort of had a slower main CPU that was in order.
[1236.02 --> 1236.20]  Right.
[1236.24 --> 1237.82]  So it didn't do anything speculative.
[1238.38 --> 1241.40]  The job of which was to put these results together.
[1242.28 --> 1242.48]  Right.
[1242.54 --> 1242.70]  Right.
[1243.00 --> 1243.20]  And,
[1243.26 --> 1244.78]  and they weren't the only people that did that.
[1244.84 --> 1245.04]  So,
[1245.40 --> 1245.66]  so.
[1245.80 --> 1246.44]  And when was this?
[1246.44 --> 1248.04]  This was like early 2000s,
[1248.06 --> 1248.22]  right?
[1248.30 --> 1248.44]  When,
[1248.44 --> 1249.04]  when is cell?
[1249.74 --> 1253.48]  So the consumer console that had the cell and it was the PlayStation three.
[1253.58 --> 1253.76]  Right.
[1253.86 --> 1254.08]  Right.
[1254.12 --> 1254.58]  Which I,
[1254.58 --> 1258.02]  I don't even want to remember exactly what years.
[1258.18 --> 1258.38]  So,
[1258.48 --> 1258.90]  so the year,
[1259.00 --> 1259.20]  okay.
[1259.94 --> 1264.02]  When I was working on cell was before it was actually out.
[1264.76 --> 1265.16]  Well,
[1265.18 --> 1266.00]  the first time I was,
[1266.08 --> 1268.76]  that was in 2003.
[1268.98 --> 1269.18]  Okay.
[1269.28 --> 1269.44]  Right.
[1269.58 --> 1269.70]  Yeah.
[1269.80 --> 1270.02]  Right.
[1270.16 --> 1270.28]  Right.
[1270.28 --> 1270.36]  Right.
[1270.36 --> 1270.44]  Right.
[1270.50 --> 1270.68]  So,
[1270.68 --> 1271.74]  so we're talking like,
[1272.44 --> 1272.70]  you know,
[1272.76 --> 1279.26]  PS three generation was probably like 2004 to 2010 or something.
[1279.40 --> 1284.16]  And we are kind of now in the late stage dementia of Denard scaling.
[1284.16 --> 1286.78]  Denard scaling is beginning to break down in 2003.
[1287.56 --> 1287.66]  Right.
[1287.74 --> 1288.60]  We are still,
[1288.90 --> 1289.40]  because the,
[1289.52 --> 1290.78]  what the five gigahertz part,
[1290.88 --> 1293.16]  the power five gigahertz part is kind of in there somewhere.
[1293.30 --> 1293.42]  Right.
[1293.44 --> 1294.90]  It's basically 2005,
[1295.14 --> 1296.10]  I think is when that,
[1296.92 --> 1301.34]  you're right in that point where people realizing that just accelerating clock does not make sense.
[1301.52 --> 1301.68]  Well,
[1301.72 --> 1302.10]  we even,
[1302.22 --> 1302.50]  I think,
[1302.60 --> 1303.66]  I think a lot of people,
[1304.28 --> 1304.46]  like,
[1304.48 --> 1307.98]  I remember talking to my friends about this in like 2001 or 2000,
[1308.24 --> 1308.54]  like,
[1308.84 --> 1310.36]  like on Intel CPUs,
[1310.36 --> 1312.44]  it was starting to look like clock speeds.
[1312.44 --> 1313.08]  We're going to,
[1313.08 --> 1314.00]  we're going to level off.
[1314.00 --> 1314.24]  Yeah.
[1314.34 --> 1314.74]  Back then,
[1314.80 --> 1314.90]  but,
[1314.98 --> 1315.14]  but,
[1315.14 --> 1315.66]  but other,
[1315.74 --> 1317.50]  other CPUs were probably pushing it further,
[1317.64 --> 1318.44]  but yeah.
[1318.56 --> 1318.72]  So,
[1318.84 --> 1319.18]  and,
[1319.18 --> 1321.04]  and they weren't the only people who had this thought.
[1321.04 --> 1321.24]  So,
[1321.34 --> 1322.40]  so the Xbox 360,
[1322.54 --> 1325.46]  which was the competitor console for that generation,
[1325.46 --> 1326.62]  they didn't do that,
[1326.62 --> 1327.60]  but they said like,
[1327.64 --> 1327.80]  look,
[1327.84 --> 1329.08]  instead of one fancy,
[1329.26 --> 1330.02]  you know,
[1330.06 --> 1330.90]  out of order core,
[1330.98 --> 1333.76]  we're going to have three in order cores and you could have three cores.
[1333.94 --> 1334.10]  Right.
[1334.20 --> 1334.50]  What's,
[1334.80 --> 1335.00]  what,
[1335.16 --> 1336.70]  how could that possibly be bad?
[1336.72 --> 1336.98]  Right.
[1337.30 --> 1338.32]  And the answer is,
[1338.60 --> 1342.10]  Amdahl's law is why that's bad for both systems.
[1342.10 --> 1342.48]  Right.
[1342.48 --> 1347.22]  And so something that would happen on the cell processor is just like,
[1347.28 --> 1347.54]  okay,
[1347.54 --> 1348.32]  first of all,
[1348.86 --> 1353.42]  it's actually a non-trivial problem to try to factor a program into these little,
[1353.42 --> 1357.18]  little tiny pieces that will go onto this coprocessor and run quickly.
[1357.68 --> 1359.46]  And as an outsider looking in,
[1359.46 --> 1360.00]  I have to tell you,
[1360.02 --> 1361.34]  that was my first impression of self.
[1361.34 --> 1361.74]  And I thought,
[1361.80 --> 1362.06]  I was like,
[1362.18 --> 1362.72]  wow,
[1362.76 --> 1363.96]  this would be hard to program.
[1363.96 --> 1364.18]  Well,
[1364.18 --> 1364.36]  it,
[1364.42 --> 1365.00]  I mean,
[1365.10 --> 1367.20]  because you've got so many,
[1367.30 --> 1367.46]  I mean,
[1367.46 --> 1369.00]  you've got to keep these units busy.
[1369.20 --> 1369.22]  Now,
[1369.26 --> 1370.70]  now all this kind of,
[1370.72 --> 1373.86]  this scheduling task has been thrown back on the programmer of,
[1374.00 --> 1377.18]  I've got to have these little channel programs for lack of a better word.
[1377.18 --> 1379.80]  And I've got to shunt them out to these,
[1379.84 --> 1381.62]  these devices and I want to keep them busy.
[1382.36 --> 1383.30]  And then how do I,
[1383.46 --> 1386.18]  how do I figure out what's actually happening where,
[1386.28 --> 1386.54]  when,
[1386.62 --> 1386.78]  I mean,
[1386.80 --> 1389.62]  it felt like it would need a lot of cognitive load.
[1389.62 --> 1392.90]  But even to get to that problem is actually kind of hard.
[1393.02 --> 1393.08]  Oh,
[1393.16 --> 1394.52]  so here's the thing about video games,
[1394.58 --> 1394.76]  right?
[1395.36 --> 1396.78]  Like there's different classes of problems,
[1396.86 --> 1397.00]  right?
[1397.00 --> 1397.86]  There are problems that,
[1397.94 --> 1400.44]  that are called embarrassingly parallel where it's just like,
[1400.96 --> 1401.40]  you know,
[1401.50 --> 1401.64]  the,
[1401.70 --> 1404.46]  the data do not have much dependency on each other.
[1404.52 --> 1404.74]  Right.
[1404.84 --> 1405.04]  Right.
[1405.04 --> 1405.46]  And so,
[1405.60 --> 1408.20]  so that's the thing that you can factor out and put on the side.
[1408.26 --> 1408.40]  Right.
[1408.44 --> 1410.98]  So games don't have that much.
[1410.98 --> 1412.18]  That's embarrassingly parallel.
[1412.18 --> 1412.50]  Like,
[1412.50 --> 1417.24]  like most of what we do has very heavy data dependencies on each other.
[1417.24 --> 1417.72]  And yeah,
[1417.72 --> 1418.62]  and this has a lot of,
[1418.74 --> 1421.20]  even just outside of like what CPU you try to run on,
[1421.26 --> 1423.24]  this has a lot of implications.
[1423.24 --> 1423.62]  Like,
[1423.70 --> 1423.90]  so,
[1424.30 --> 1424.48]  so,
[1424.54 --> 1424.68]  you know,
[1424.68 --> 1427.20]  when you go to computer school and they tell you how to program that you
[1427.20 --> 1431.14]  should factor your programs in certain ways so that this doesn't talk to
[1431.14 --> 1431.46]  this,
[1431.86 --> 1433.68]  this module does not talk to this module,
[1433.68 --> 1433.92]  right?
[1433.94 --> 1434.14]  They,
[1434.30 --> 1437.02]  they don't know anything about each other that like doesn't make that much
[1437.02 --> 1440.76]  sense on a game because in some sense,
[1440.76 --> 1446.04]  games are about mixing things together and having the complexity come out on
[1446.04 --> 1447.56]  the screen in a delightful way.
[1447.72 --> 1447.90]  Right.
[1448.12 --> 1448.48]  So like,
[1448.50 --> 1449.98]  if you're generating sound effects,
[1450.46 --> 1452.18]  those sound effects need to be,
[1452.34 --> 1454.38]  should know what things look like.
[1454.38 --> 1454.56]  Yeah.
[1454.64 --> 1454.88]  Right.
[1455.18 --> 1457.14]  Like it should know what the surface looks like.
[1457.28 --> 1457.48]  Yeah.
[1457.48 --> 1459.38]  And like how many dust particles are happening.
[1459.86 --> 1460.12]  And,
[1460.18 --> 1462.78]  and so like a game is like a giant nexus of,
[1462.86 --> 1464.28]  of information coming together.
[1464.28 --> 1465.58]  And so have fun,
[1465.68 --> 1468.24]  have fun factoring that onto your co-processor.
[1468.60 --> 1468.68]  Right.
[1469.40 --> 1469.66]  Well,
[1469.70 --> 1470.34]  I kind of feel like,
[1470.34 --> 1472.84]  I kind of feel like with embarrassingly parallel problems,
[1472.84 --> 1476.66]  I think everyone kind of assumes that someone else must have them because
[1476.66 --> 1477.28]  the like,
[1477.36 --> 1477.58]  okay,
[1477.80 --> 1477.90]  well,
[1477.94 --> 1479.46]  it's like the statelessness in Kubernetes,
[1479.66 --> 1479.80]  right?
[1479.84 --> 1480.10]  Justin,
[1480.26 --> 1481.24]  where it's like,
[1481.30 --> 1481.50]  all right,
[1481.50 --> 1483.22]  I guess everyone else has got these stateless problems.
[1483.36 --> 1483.92]  My problems,
[1484.02 --> 1488.38]  I've got like this kind of gnarly state that is interwoven into everything.
[1488.38 --> 1489.24]  I have to say,
[1489.36 --> 1490.00]  I kind of,
[1490.44 --> 1490.64]  you know,
[1490.70 --> 1491.32]  someone who,
[1491.56 --> 1491.72]  you know,
[1491.80 --> 1494.48]  other than my kind of early forays into game programming as a kid,
[1494.56 --> 1494.66]  I,
[1494.72 --> 1496.00]  I've always kind of assumed that like,
[1496.06 --> 1496.16]  well,
[1496.18 --> 1496.48]  I don't know,
[1496.54 --> 1498.02]  games must be embarrassingly parallel,
[1498.22 --> 1498.38]  but.
[1499.20 --> 1499.60]  Well,
[1499.70 --> 1503.56]  so the reason GPUs are so successful is because the very tail end is
[1503.56 --> 1504.40]  embarrassingly parallel.
[1504.66 --> 1507.14]  Like by the time you're done setting everything up.
[1507.16 --> 1507.42]  Right.
[1507.48 --> 1509.34]  And like all this complicated thing,
[1509.46 --> 1511.16]  we've managed to factor it.
[1511.20 --> 1513.74]  So that the very last step where the pixels go on the screen,
[1513.84 --> 1516.06]  which involves actually quite a lot of math,
[1516.14 --> 1516.36]  right?
[1517.56 --> 1517.88]  That.
[1517.88 --> 1520.62]  Usually not all the time,
[1520.70 --> 1524.46]  but usually the math for one pixel does not depend on the math for the
[1524.46 --> 1525.08]  neighboring pixel.
[1525.34 --> 1525.48]  Right.
[1525.58 --> 1526.88]  And so then,
[1527.00 --> 1528.94]  then you can go wide at the very end,
[1528.94 --> 1529.20]  but,
[1529.32 --> 1532.48]  but everything before that is not so easy.
[1532.60 --> 1533.08]  Not so easy.
[1533.40 --> 1533.70]  Yeah.
[1533.70 --> 1533.98]  That,
[1534.04 --> 1534.84]  that is really interesting.
[1534.92 --> 1535.12]  Cause it's,
[1535.18 --> 1536.68]  and it's actually a lot harder than,
[1536.88 --> 1537.82]  cause when you've got this,
[1537.82 --> 1538.38]  this interconnect,
[1538.38 --> 1539.50]  this interconnectedness,
[1539.52 --> 1541.72]  it's very hard to accelerate in hardware.
[1541.92 --> 1542.10]  I mean,
[1542.10 --> 1542.60]  it's like,
[1542.96 --> 1543.38]  I mean,
[1543.74 --> 1544.00]  yeah.
[1544.26 --> 1544.50]  All right.
[1544.50 --> 1544.66]  So,
[1544.80 --> 1547.58]  and so cell was an attempt to,
[1547.58 --> 1548.30]  I mean,
[1548.36 --> 1548.50]  how,
[1548.64 --> 1550.72]  is that part of the reason that cell struggled is,
[1550.82 --> 1553.70]  is because there was more interconnectedness than,
[1553.82 --> 1555.24]  than kind of folks realized or.
[1555.24 --> 1556.52]  I think that was one reason,
[1556.62 --> 1557.18]  but also.
[1558.26 --> 1561.10]  And it was like Toshiba and IBM and Sony.
[1561.92 --> 1562.32]  Yes.
[1562.46 --> 1562.72]  Was that,
[1562.82 --> 1563.42]  am I remembering that?
[1564.42 --> 1565.98]  That some.
[1566.74 --> 1568.24]  I believe those are the three companies.
[1568.60 --> 1568.76]  Okay.
[1568.88 --> 1568.98]  Yeah.
[1569.04 --> 1569.22]  And,
[1569.28 --> 1571.30]  and so actually my first exposure to cell was,
[1571.42 --> 1576.38]  I was doing a project for IBM with some friends and we essentially wrote a whole game.
[1576.48 --> 1576.72]  So,
[1576.76 --> 1579.06]  so IBM wanted to put these into servers,
[1579.06 --> 1579.38]  right?
[1579.44 --> 1580.74]  Cause that's what they know how to do.
[1580.74 --> 1581.14]  Right.
[1581.54 --> 1582.14]  And they were like,
[1582.26 --> 1592.72]  what part of the reason I think that cell floundered is all this research went into building this hardware in the theory that it was going to be dominant because these co-processors were so fast,
[1592.88 --> 1594.00]  which I guess makes sense.
[1594.00 --> 1598.36]  But nobody really had mapped out all the way to software of like,
[1598.36 --> 1600.48]  what actually is this for?
[1600.60 --> 1600.72]  Right.
[1600.76 --> 1602.26]  And so they had weird stuff like,
[1602.38 --> 1602.50]  Oh,
[1602.58 --> 1605.24]  you're going to have this in your refrigerator and it's going to be awesome.
[1605.38 --> 1606.30]  And like the,
[1606.30 --> 1607.92]  the Sony people see,
[1608.14 --> 1608.26]  I,
[1608.38 --> 1610.72]  I know people at Sony,
[1610.86 --> 1613.68]  so they'll get mad if I bring up embarrassing things in the past,
[1613.68 --> 1614.96]  but they were saying things like,
[1614.96 --> 1616.00]  you know,
[1616.02 --> 1617.56]  when you buy a PlayStation three,
[1617.94 --> 1619.06]  if you're,
[1619.34 --> 1622.46]  it'll talk to your refrigerator to get more processing power,
[1622.46 --> 1623.22]  or it'll,
[1623.48 --> 1627.38]  it'll call your friend's PlayStation down the street to get more processing power.
[1627.40 --> 1627.72]  That's nuts.
[1628.02 --> 1628.42]  Yeah.
[1628.42 --> 1629.72]  They were actually saying that publicly.
[1630.00 --> 1630.30]  Right.
[1630.40 --> 1635.80]  But also whether or not that's technically feasible at the hardware level,
[1635.80 --> 1636.14]  right.
[1636.16 --> 1636.94]  Which whatever,
[1637.12 --> 1639.26]  it doesn't make sense in terms of a game,
[1639.26 --> 1640.24]  like in a game,
[1640.24 --> 1643.78]  you need to know how much processing power is available to decide what to do.
[1643.78 --> 1644.52]  I can't like,
[1644.56 --> 1645.94]  is your fridge available now?
[1646.04 --> 1646.92]  Is it not available now?
[1647.16 --> 1647.20]  Like,
[1647.28 --> 1647.76]  I don't want to,
[1647.94 --> 1648.92]  and also can you imagine like,
[1648.98 --> 1649.08]  yeah,
[1649.16 --> 1651.00]  well you beat me in that game because like my fridge,
[1651.00 --> 1654.48]  someone opened my fridge and I lost the computational power.
[1654.60 --> 1655.78]  My frame rate slowed down.
[1655.92 --> 1656.04]  Now,
[1656.04 --> 1657.10]  now to be fair to Sony,
[1657.26 --> 1658.94]  Microsoft said equally dumb stuff,
[1659.16 --> 1660.40]  the next console generation.
[1660.78 --> 1661.28]  So whatever,
[1661.64 --> 1662.50]  I'll just throw that,
[1662.62 --> 1663.12]  throw that in there.
[1663.12 --> 1663.26]  Yeah.
[1663.30 --> 1663.46]  Right.
[1663.52 --> 1666.08]  No company has got a monopoly on saying dumb stuff for sure.
[1666.24 --> 1666.44]  You know,
[1666.56 --> 1666.96]  I think,
[1666.98 --> 1670.54]  I think hardware people were in the mindset that like,
[1670.58 --> 1670.78]  look,
[1670.78 --> 1675.18]  we just know how to make this fast and software people are lazy and stupid.
[1675.42 --> 1679.66]  And we'll just get them to do the right thing when the hardware comes out and it'll be great.
[1679.82 --> 1679.90]  Right.
[1680.48 --> 1680.90]  Yeah.
[1681.00 --> 1682.64]  Now there is a little bit of truth to that.
[1682.92 --> 1685.00]  I don't want to like slag on hardware people.
[1685.16 --> 1685.34]  Right.
[1685.44 --> 1685.60]  Right.
[1685.72 --> 1688.28]  There's a certain way in which software people have been lazy.
[1688.66 --> 1688.86]  Yeah.
[1689.54 --> 1690.26]  And like,
[1690.46 --> 1694.80]  are not that interested in knowing the details of the system underneath and all these things.
[1694.80 --> 1695.30]  And in,
[1695.84 --> 1696.86]  especially today,
[1697.24 --> 1704.46]  the difference between even knowing some basic high level details about what you're running on and not is like orders of magnitude difference in performance.
[1704.68 --> 1704.78]  Right.
[1704.86 --> 1706.38]  And so this stuff really matters.
[1706.38 --> 1709.64]  And I could understand being a hardware person and being just kind of frustrating at that.
[1709.64 --> 1709.82]  Right.
[1709.82 --> 1710.02]  Yeah.
[1710.02 --> 1711.54]  But the problem is if you're going to,
[1712.14 --> 1713.22]  if that's going to be your plan,
[1714.02 --> 1715.20]  you have to actually know,
[1715.30 --> 1717.20]  you have to actually map it out from beginning to end.
[1717.46 --> 1719.60]  What does this turn into when it's actual software?
[1719.70 --> 1720.78]  And nobody ever did that.
[1720.78 --> 1721.04]  Right.
[1721.20 --> 1721.42]  Right.
[1721.42 --> 1721.96]  And so,
[1722.46 --> 1723.16]  you know,
[1723.16 --> 1723.96]  I mean,
[1723.98 --> 1724.44]  you see today,
[1724.52 --> 1726.14]  nobody uses a cell processor for anything.
[1726.28 --> 1728.56]  Nobody uses a descendant of a cell processor for anything.
[1728.68 --> 1728.90]  Right.
[1728.92 --> 1730.70]  Because it just didn't work out.
[1730.72 --> 1730.90]  Right.
[1731.10 --> 1731.44]  Yeah.
[1731.50 --> 1732.26]  The model didn't work.
[1732.38 --> 1734.26]  And I think largely for software reasons.
[1734.40 --> 1734.66]  Right.
[1734.72 --> 1734.92]  I mean,
[1734.96 --> 1735.18]  it's,
[1735.32 --> 1735.38]  it,
[1735.48 --> 1739.46]  it was just a very hard model to program to,
[1739.48 --> 1740.06]  it seems like.
[1740.54 --> 1740.76]  Yeah.
[1742.28 --> 1742.84]  And so,
[1742.98 --> 1744.74]  so you're working on this project for IBM.
[1744.94 --> 1745.10]  I mean,
[1745.12 --> 1745.40]  did you,
[1745.40 --> 1748.84]  were you able to demonstrate any kind of win?
[1748.96 --> 1749.06]  I mean,
[1749.08 --> 1749.40]  was it?
[1749.56 --> 1749.66]  No.
[1749.74 --> 1749.90]  Okay.
[1749.96 --> 1750.10]  So,
[1750.18 --> 1750.80]  so the idea,
[1751.02 --> 1751.66]  see,
[1752.42 --> 1753.14]  now I don't know.
[1753.22 --> 1754.14]  I don't know what's typically,
[1754.44 --> 1756.46]  this is a dead project from a long time ago,
[1756.48 --> 1758.68]  but some of it might be under NDA technically.
[1758.92 --> 1759.20]  Okay.
[1759.20 --> 1759.44]  You know,
[1759.52 --> 1760.14]  but okay.
[1760.24 --> 1761.22]  So the point was.
[1761.42 --> 1761.52]  All right.
[1761.54 --> 1761.62]  So,
[1761.64 --> 1764.42]  so if you're listening to this and you're getting uptight about,
[1764.42 --> 1767.08]  about Jonathan talking about the cells,
[1767.20 --> 1768.12]  just relax.
[1768.12 --> 1770.34]  Because I actually think that like,
[1770.44 --> 1772.32]  I think some of these efforts are,
[1772.42 --> 1775.36]  I think the cell is an important experiment.
[1775.76 --> 1778.08]  And I think learning from that experiment is also important.
[1778.18 --> 1778.24]  Yeah.
[1778.32 --> 1778.42]  No,
[1778.48 --> 1778.90]  it is super,
[1779.02 --> 1779.58]  super important.
[1779.74 --> 1779.92]  Right.
[1780.18 --> 1780.40]  Okay.
[1780.40 --> 1782.52]  So IBM was looking for like,
[1782.60 --> 1784.84]  what can we do with servers that use this?
[1784.88 --> 1785.04]  Right.
[1785.06 --> 1785.70]  And I was,
[1785.84 --> 1787.50]  I was kind of aimless at that time.
[1787.50 --> 1787.96]  Like I'd,
[1787.96 --> 1788.92]  I'd had my own,
[1788.98 --> 1793.12]  I started a company with somebody and that didn't work out after several painful years.
[1793.12 --> 1795.22]  And then I'd done like independent consulting for a while.
[1795.22 --> 1797.92]  And I was kind of working on my own games on the side,
[1797.92 --> 1798.26]  but like,
[1798.28 --> 1798.64]  not really,
[1798.66 --> 1799.80]  I was kind of drifting around.
[1799.80 --> 1800.66]  And like,
[1800.86 --> 1802.02]  I just moved to New York,
[1802.02 --> 1802.50]  I guess.
[1802.66 --> 1805.38]  And I got hooked up with some people at IBM through some friends.
[1805.38 --> 1806.04]  And I just,
[1806.18 --> 1808.86]  I had this meeting with a guy from IBM and I was like,
[1808.94 --> 1809.10]  sure,
[1809.12 --> 1810.52]  I'll figure out what,
[1811.02 --> 1812.02]  what you can do with a server.
[1812.02 --> 1814.40]  And I had no idea prior to that.
[1814.40 --> 1817.54]  And so I went home and slept on it and I came up with a plan,
[1818.04 --> 1818.70]  which is just actually,
[1818.84 --> 1819.22]  so all this,
[1819.28 --> 1822.80]  all this complicated physics stuff that I was mentioning earlier,
[1822.94 --> 1825.70]  let's actually take that one step further.
[1825.76 --> 1827.28]  Cause then it'll explain what this thing was.
[1827.28 --> 1827.52]  Right.
[1827.52 --> 1828.86]  So I talked about maybe,
[1828.86 --> 1829.48]  you know,
[1829.50 --> 1830.74]  your hand hitting a table or not.
[1830.74 --> 1830.98]  Right.
[1831.02 --> 1832.86]  But in a world full of stuff,
[1832.86 --> 1834.68]  it's actually more complicated than that.
[1834.68 --> 1834.86]  Right.
[1834.88 --> 1838.34]  So if you have a coffee cup on a box on the table and you bump the table,
[1838.42 --> 1838.60]  right,
[1838.62 --> 1839.26]  what happens,
[1839.36 --> 1839.56]  right?
[1839.64 --> 1839.76]  Well,
[1839.80 --> 1840.82]  the things on it jostle,
[1841.06 --> 1841.32]  right.
[1841.32 --> 1845.76]  So you have these kind of semi free objects that are holding each other up and
[1845.76 --> 1846.72]  colliding with each other.
[1846.72 --> 1850.04]  And like if a box moves and my coffee cup tilts,
[1850.16 --> 1851.76]  but it's kind of got coffee in the bottom.
[1851.88 --> 1853.02]  So it doesn't tilt too far.
[1853.08 --> 1855.36]  Like all those physics computations are,
[1855.42 --> 1856.58]  I mean,
[1856.60 --> 1856.76]  they're,
[1856.76 --> 1857.50]  they're complicated.
[1857.52 --> 1857.92]  Right.
[1858.00 --> 1858.34]  And,
[1858.38 --> 1858.60]  and,
[1858.60 --> 1859.68]  and in more than one way.
[1859.68 --> 1860.40]  So one is it's,
[1860.40 --> 1863.36]  it's challenging to program those in an ideal environment.
[1863.36 --> 1863.66]  Right.
[1864.00 --> 1866.00]  But then suppose you have a multiplayer game.
[1866.44 --> 1866.74]  All right.
[1867.36 --> 1870.14]  And let's say it matters whether your coffee spills or not,
[1870.14 --> 1872.18]  because the point of the game is don't spill the coffee.
[1872.30 --> 1872.50]  Right.
[1873.16 --> 1873.56]  Okay.
[1874.08 --> 1874.28]  Well,
[1874.32 --> 1874.42]  the,
[1874.42 --> 1878.92]  the way you would do a distributed system in the face of like internet latency
[1878.92 --> 1883.44]  and unreliable packet delivery and things like this is you would do
[1883.44 --> 1884.38]  what's called in games,
[1884.50 --> 1885.54]  client side prediction.
[1885.54 --> 1887.50]  It goes under different names and different disciplines.
[1887.52 --> 1888.38]  But it's like,
[1888.70 --> 1889.10]  okay,
[1889.62 --> 1892.52]  normally we would make most of our physics just cosmetic.
[1892.98 --> 1893.58]  So like,
[1893.64 --> 1894.74]  if I blow something up,
[1894.86 --> 1897.40]  it's got these chunks that come out and bounce on the ground and roll
[1897.40 --> 1897.78]  around,
[1898.14 --> 1899.90]  but they don't really affect gameplay.
[1899.90 --> 1904.26]  And what the server does is it sends to all the players,
[1904.36 --> 1904.42]  Oh,
[1904.46 --> 1907.46]  this thing blew up and we all generate our chunks and they bounce around.
[1907.46 --> 1910.12]  But the problem is the thing that blew up is going to be in a slightly
[1910.12 --> 1912.52]  different position for all of us because we're not synchronized.
[1912.62 --> 1912.74]  Right.
[1912.78 --> 1914.64]  It doesn't matter for this purpose.
[1914.68 --> 1917.24]  It doesn't matter that you and I are seeing slightly different things.
[1917.36 --> 1917.48]  Right.
[1917.52 --> 1919.06]  And so you get this butterfly effect,
[1919.06 --> 1919.30]  right?
[1919.30 --> 1920.06]  Where my chunk,
[1920.12 --> 1920.34]  you know,
[1920.38 --> 1923.60]  bounced off that wall and then that wall and then hit the coffee cup.
[1923.64 --> 1923.82]  Right.
[1923.86 --> 1924.74]  And your chunk didn't.
[1924.86 --> 1925.02]  Right.
[1925.34 --> 1927.46]  And so the game design was always about,
[1927.58 --> 1929.10]  we'll start using this physics stuff,
[1929.20 --> 1929.92]  but it won't matter.
[1930.08 --> 1930.40]  Right.
[1930.48 --> 1931.20]  And so I said,
[1931.24 --> 1931.32]  well,
[1931.32 --> 1933.98]  what if you make this cool game where the physics actually matters?
[1934.80 --> 1935.66]  You have two problems.
[1935.74 --> 1937.24]  One is the synchronization problem.
[1937.24 --> 1937.68]  Uh,
[1937.72 --> 1938.42]  because,
[1938.78 --> 1939.98]  because of the butterfly effect,
[1940.20 --> 1943.68]  you need to have a central authority over what's actually happening.
[1943.68 --> 1944.82]  And that would be the server.
[1944.88 --> 1945.16]  Right.
[1945.24 --> 1947.70]  And then another thing that happens in multiplayer games all the time is
[1947.70 --> 1948.54]  people want to cheat.
[1948.62 --> 1949.02]  Right.
[1949.24 --> 1953.44]  And so you kind of need to have security over like what's happening.
[1953.44 --> 1955.32]  And all of that means that if you,
[1955.32 --> 1958.62]  if you had a server that was able to do physics really fast,
[1959.18 --> 1962.98]  you would enable a kind of game that you simply cannot do with a,
[1962.98 --> 1966.04]  with a client server architecture with a weaker server,
[1966.04 --> 1966.40]  right.
[1966.40 --> 1967.26]  In the traditional way.
[1967.34 --> 1967.64]  And so,
[1967.78 --> 1970.30]  so the goal was this thing is simulating physics all the time.
[1970.32 --> 1974.90]  And so we had this cool game design where like you had like giant robots
[1974.90 --> 1975.90]  walking around,
[1975.90 --> 1976.22]  like,
[1976.26 --> 1976.96]  like multi,
[1977.16 --> 1978.32]  like five story high.
[1978.48 --> 1982.36]  And you could like shoot joints of them and like the arm would fall off or
[1982.36 --> 1982.64]  whatever.
[1982.64 --> 1983.32]  I don't know.
[1984.60 --> 1985.04]  And,
[1985.12 --> 1985.44]  uh,
[1985.90 --> 1987.24]  it was a small project.
[1987.50 --> 1988.18]  So I did,
[1988.38 --> 1991.50]  I did the sort of what we would call the game engine and the rendering.
[1991.50 --> 1992.62]  And my friend Otman,
[1992.84 --> 1995.10]  who later went to Oculus,
[1995.34 --> 1995.86]  uh,
[1995.86 --> 1996.22]  well,
[1996.22 --> 1997.36]  he went to valve and then Oculus.
[1997.50 --> 1998.52]  I don't know if he's still there,
[1998.52 --> 1999.06]  um,
[1999.06 --> 2000.60]  but he did the entire,
[2000.66 --> 2004.26]  he wrote a physics engine from scratch to do all this complicated stuff that I was
[2004.26 --> 2004.76]  talking about.
[2004.76 --> 2005.04]  Right.
[2005.04 --> 2006.14]  But not only that,
[2006.20 --> 2007.44]  but do it on the cell,
[2007.64 --> 2008.80]  but not just one cell.
[2008.80 --> 2009.02]  Right.
[2009.06 --> 2011.24]  Because the IBM plan was you have the cell,
[2011.36 --> 2014.92]  two cells in a blade or something and you start slapping the blades in there.
[2015.00 --> 2015.24]  Yeah.
[2015.60 --> 2015.84]  Right.
[2016.50 --> 2017.38]  And well,
[2017.54 --> 2019.84]  how do they talk to each other?
[2019.84 --> 2024.82]  And the answer was 10 megabyte ethernet or something.
[2025.16 --> 2025.94]  10 megabit.
[2026.02 --> 2026.60]  What was it?
[2027.00 --> 2027.92]  I don't remember.
[2028.10 --> 2028.24]  Yeah.
[2028.50 --> 2029.10]  It would be like,
[2029.10 --> 2030.50]  it would be like a hundred megabit.
[2030.56 --> 2030.92]  Maybe.
[2031.26 --> 2034.58]  I think it was infiniband or something,
[2034.58 --> 2036.18]  but it was like slow infiniband.
[2036.24 --> 2036.76]  There was like,
[2036.86 --> 2039.26]  there was like a 10 option and a hundred option.
[2039.26 --> 2039.42]  Right.
[2039.42 --> 2041.54]  And they didn't want to do the hundred because that was expensive.
[2041.86 --> 2042.76]  I suppose the infiniband.
[2042.80 --> 2042.92]  Yeah.
[2042.92 --> 2043.38]  I don't know.
[2043.52 --> 2045.36]  I wasn't paying that much attention to that.
[2045.44 --> 2045.60]  Right.
[2045.60 --> 2046.42]  But the point was,
[2046.66 --> 2050.84]  so because of what I was talking about before,
[2050.92 --> 2051.60]  about in games,
[2051.70 --> 2052.90]  everything affects everything else.
[2052.96 --> 2053.14]  Yeah.
[2053.42 --> 2055.54]  So typically what you would have to do is say,
[2055.60 --> 2055.80]  okay,
[2056.70 --> 2057.60]  we're at time T.
[2058.28 --> 2060.44]  We want to go to time T plus delta T,
[2060.90 --> 2061.10]  right?
[2061.46 --> 2064.30]  Where delta T is like one 60th of a second or something.
[2064.42 --> 2064.60]  Right.
[2064.84 --> 2068.04]  And we've got a world full of all these objects that are able to physically interact.
[2068.58 --> 2073.82]  And the job of this server is to just grind the iron and figure out all this physics.
[2073.82 --> 2074.02]  Right.
[2074.14 --> 2074.34]  Right.
[2074.78 --> 2075.58]  And get back to me.
[2076.32 --> 2080.98]  And it's more physics than will happen on one cell or even on one blade.
[2081.22 --> 2081.38]  Right.
[2081.68 --> 2086.04]  So you kind of have to distribute the computation every frame.
[2086.16 --> 2086.46]  Right.
[2086.58 --> 2090.60]  But now you're like distributing it over a kind of a slow network and,
[2090.60 --> 2093.90]  and like fanning out the computations and saying,
[2093.98 --> 2094.12]  okay,
[2094.12 --> 2096.54]  work on this and then getting the results back.
[2096.60 --> 2098.48]  And we actually worked it out of like,
[2098.88 --> 2099.12]  okay,
[2099.14 --> 2100.66]  even if there's no problems,
[2100.84 --> 2101.24]  right,
[2101.58 --> 2105.26]  even if we feed all the data optimally and managed to partition it optimally
[2105.26 --> 2105.78]  and all that,
[2106.06 --> 2106.34]  like,
[2106.58 --> 2110.70]  what is our speed limit just due to like waiting for the bits to get over the wire?
[2111.10 --> 2111.46]  Right.
[2111.52 --> 2113.12]  And waiting for the results to come back.
[2113.12 --> 2116.10]  And it was an appreciable portion of that frame time.
[2116.10 --> 2118.64]  We might not have been aiming for one 60th of a second.
[2118.72 --> 2119.28]  It might've been like,
[2119.48 --> 2120.28]  I think it was 10,
[2121.20 --> 2121.40]  but,
[2121.40 --> 2122.24]  but still like when,
[2122.32 --> 2123.86]  when you need to do an entire job,
[2123.86 --> 2125.02]  uh,
[2125.02 --> 2125.26]  you know,
[2125.26 --> 2126.14]  10 times a second,
[2126.14 --> 2127.90]  it's just a different world than,
[2128.26 --> 2129.52]  than where a lot of people live in.
[2129.52 --> 2132.10]  And where the late results are useless.
[2132.52 --> 2132.80]  Yeah.
[2132.88 --> 2133.08]  Right.
[2133.08 --> 2133.32]  It's like,
[2133.34 --> 2135.20]  if you can't get back to me within a hundred milliseconds,
[2135.38 --> 2135.58]  whatever,
[2135.72 --> 2135.90]  you know,
[2135.90 --> 2137.38]  whatever my frame is going to be like,
[2137.44 --> 2139.02]  just forget it because I,
[2139.16 --> 2141.04]  we need to move on to the next frame.
[2141.12 --> 2141.24]  Yeah.
[2141.26 --> 2141.52]  And so,
[2141.52 --> 2141.88]  so that,
[2142.00 --> 2142.80]  that particular,
[2143.74 --> 2144.02]  you know,
[2144.04 --> 2144.66]  I don't like,
[2144.66 --> 2145.02]  we wrote,
[2145.10 --> 2146.58]  we wrote our final report for IBM.
[2146.78 --> 2147.08]  Right.
[2147.20 --> 2147.44]  And,
[2147.52 --> 2148.50]  and our report was,
[2148.64 --> 2151.92]  this is not good hardware to,
[2152.02 --> 2153.50]  to do what you want to do actually.
[2153.50 --> 2154.24]  And here's how,
[2154.34 --> 2154.54]  you know,
[2154.58 --> 2155.64]  here's try to be helpful.
[2155.64 --> 2157.52]  Like here's how you can change it and whatever.
[2157.52 --> 2159.98]  But they didn't like that because,
[2159.98 --> 2160.98]  you know,
[2161.00 --> 2162.26]  if they're paying you to do a project,
[2162.26 --> 2163.34]  they want you to,
[2163.34 --> 2165.84]  to tell them how good their thing is.
[2165.84 --> 2166.16]  Right.
[2166.16 --> 2166.82]  Like that.
[2166.92 --> 2170.24]  And I've actually been in that scenario multiple times when I was like a
[2170.24 --> 2174.14]  consultant where I would tell people that something is bad and that's not
[2174.14 --> 2175.36]  what they were hiring me for.
[2175.36 --> 2175.72]  Right.
[2175.90 --> 2176.84]  And that caused tension.
[2176.84 --> 2177.48]  I'm sorry.
[2177.72 --> 2181.66]  You were hired to describe how great this was not to actually.
[2182.64 --> 2182.94]  Yeah.
[2183.12 --> 2184.76]  I think we've all been there to be honest.
[2184.76 --> 2185.56]  We've all been there.
[2185.82 --> 2185.98]  Well,
[2185.98 --> 2187.44]  and I think it all depends on like,
[2187.52 --> 2189.40]  what do you title your report to?
[2189.50 --> 2192.16]  I remember talking to another technologist who was talking about,
[2192.52 --> 2194.72]  he had an internal report that was not received.
[2194.80 --> 2195.06]  Well,
[2195.48 --> 2196.60]  entitled burn the boats.
[2196.76 --> 2197.06]  I'm like,
[2197.08 --> 2198.06]  was it actually called burn the boats?
[2198.06 --> 2198.24]  Yes.
[2198.30 --> 2199.32]  It's actually called burn the boats.
[2199.44 --> 2199.76]  It's like,
[2199.80 --> 2200.04]  all right,
[2200.04 --> 2200.26]  well,
[2200.62 --> 2201.06]  you know,
[2201.06 --> 2203.06]  it's your baby is ugly.
[2203.12 --> 2203.40]  Yeah,
[2203.44 --> 2203.96]  exactly.
[2204.14 --> 2204.38]  Like,
[2204.44 --> 2204.76]  you know,
[2204.84 --> 2205.56]  kill all management.
[2205.72 --> 2205.86]  Why?
[2206.16 --> 2207.84]  What's wrong with this report?
[2208.04 --> 2208.36]  It's like,
[2208.38 --> 2208.58]  well,
[2208.58 --> 2209.14]  I don't know.
[2209.42 --> 2209.72]  Yeah.
[2209.72 --> 2210.70]  This was not that bad,
[2210.70 --> 2211.30]  but it was like,
[2211.38 --> 2211.74]  it was like,
[2211.74 --> 2212.14]  we were like,
[2212.18 --> 2212.36]  look,
[2212.36 --> 2214.76]  you need at least 10 times faster,
[2214.96 --> 2215.70]  you know,
[2216.02 --> 2217.28]  Ethernet on this.
[2217.36 --> 2218.48]  And then even if you had that,
[2218.96 --> 2221.18]  it's still not that good of an idea because,
[2221.38 --> 2222.18]  because,
[2222.30 --> 2222.68]  you know,
[2222.76 --> 2223.52]  so you start,
[2223.84 --> 2225.46]  if you were to try to solve the problem,
[2225.46 --> 2226.10]  I just mentioned,
[2226.10 --> 2226.58]  like,
[2226.62 --> 2229.98]  we're waiting all this time just for the bits to go out and come back.
[2230.08 --> 2230.38]  Right.
[2230.72 --> 2231.04]  Well,
[2231.06 --> 2233.04]  you could start engineering that,
[2233.12 --> 2233.30]  right?
[2233.32 --> 2233.54]  Like,
[2233.56 --> 2236.28]  why don't we start compressing the data on the way out and back?
[2236.28 --> 2239.36]  And why don't we get like super smart about like what we transmit and,
[2239.70 --> 2242.28]  or why don't we hold a lot of state on the individual blades?
[2243.08 --> 2243.24]  Right.
[2243.28 --> 2243.62]  So like,
[2243.64 --> 2243.88]  maybe,
[2244.22 --> 2247.20]  maybe this one is authoritative over a portion of the world.
[2247.20 --> 2250.52]  And then if somebody crosses some invisible border,
[2250.82 --> 2251.44]  you know,
[2251.54 --> 2252.92]  we move it to another one.
[2252.98 --> 2253.52]  And then what do you,
[2253.80 --> 2255.72]  what happens if it's in the middle?
[2255.72 --> 2256.08]  Right.
[2256.70 --> 2258.10]  Once you start doing that stuff and,
[2258.10 --> 2258.34]  and we,
[2258.38 --> 2260.14]  and we could have done some of that stuff and it would have helped.
[2260.20 --> 2260.40]  Right.
[2260.78 --> 2261.88]  But so first of all,
[2261.88 --> 2263.56]  you start driving complexity through the roof,
[2263.58 --> 2264.12]  which like,
[2264.16 --> 2267.72]  in some sense was not like you were supposed to be doing it much easier.
[2267.72 --> 2270.40]  And so that's indicative that something didn't turn out how you thought.
[2270.66 --> 2270.78]  Right.
[2271.12 --> 2272.08]  It seems that,
[2272.14 --> 2272.34]  I mean,
[2272.36 --> 2273.66]  part of the,
[2273.72 --> 2275.38]  the purpose of this was to make it,
[2275.62 --> 2277.48]  I assume not just faster,
[2277.58 --> 2278.86]  but easier to write games.
[2279.00 --> 2279.48]  I mean,
[2279.92 --> 2280.78]  because one of the challenges,
[2280.78 --> 2281.50]  I mean,
[2281.50 --> 2282.24]  the history of games,
[2282.34 --> 2282.46]  it's,
[2282.52 --> 2282.86]  it's,
[2282.86 --> 2285.36]  it's weird because the history of games,
[2285.72 --> 2290.34]  has been us getting more and more complicated and doing crazier stuff in order to do better stuff.
[2290.46 --> 2290.62]  Right.
[2290.72 --> 2291.34]  But there's a,
[2291.40 --> 2292.08]  there's some point,
[2292.14 --> 2294.30]  there is a cost benefit analysis that has to happen.
[2294.30 --> 2294.64]  Right.
[2294.64 --> 2297.90]  Like how crazy are you asking me to be for what benefit?
[2297.90 --> 2298.24]  And,
[2298.24 --> 2298.78]  you know,
[2298.78 --> 2299.12]  to be,
[2299.22 --> 2299.72]  to be honest,
[2299.72 --> 2299.92]  like,
[2299.92 --> 2301.56]  it was my idea to do this kind of game,
[2301.90 --> 2310.74]  but like the idea of a physics based game that could sort of only happen with a big iron server is,
[2310.94 --> 2313.40]  it's not that great of an idea.
[2313.54 --> 2313.78]  I mean,
[2313.78 --> 2316.10]  maybe it would be if like physics was better.
[2316.10 --> 2316.36]  Like,
[2316.40 --> 2316.60]  you know,
[2316.64 --> 2318.02]  even today in 2019,
[2318.56 --> 2320.76]  like game physics are kind of floaty and weird.
[2320.76 --> 2323.48]  And maybe somehow if you got a really high quality experience,
[2323.48 --> 2324.48]  it would be a really good idea,
[2324.48 --> 2324.96]  but like,
[2325.16 --> 2327.06]  it wasn't a super good idea,
[2327.20 --> 2328.32]  I guess.
[2328.70 --> 2331.36]  And then how much are you paying to do this?
[2331.42 --> 2332.36]  Not super good idea.
[2332.90 --> 2333.08]  Right.
[2334.56 --> 2335.00]  Right.
[2335.16 --> 2335.40]  All right.
[2335.40 --> 2336.50]  We're going to take a quick break.
[2336.56 --> 2339.66]  And then we'll be back with more Jonathan Blow on the metal.
[2342.88 --> 2345.82]  On the metal is brought to you by Oxide computer company.
[2345.94 --> 2346.22]  Well,
[2346.22 --> 2350.38]  I got to tell you the podcast has been more successful than I originally anticipated.
[2350.50 --> 2350.62]  Hey,
[2350.66 --> 2351.18]  that's great.
[2351.50 --> 2351.76]  Yeah,
[2351.86 --> 2352.84]  there's good news.
[2352.96 --> 2353.78]  Folks are,
[2353.78 --> 2354.16]  uh,
[2354.16 --> 2355.18]  are liking the content.
[2355.32 --> 2357.16]  There has been some negative feedback though.
[2357.22 --> 2358.02]  What from the podcast?
[2358.06 --> 2358.72]  The podcast is great.
[2358.76 --> 2359.62]  These interviews are amazing.
[2359.76 --> 2361.76]  The podcast themselves folks are liking.
[2361.76 --> 2366.32]  I've gotten a couple of emails specifically calling out the repetitive ad content.
[2366.42 --> 2367.52]  It's driving them crazy.
[2367.66 --> 2369.04]  We only recorded three ad rolls.
[2369.22 --> 2370.40]  I know we got a lot of ad breaks.
[2370.64 --> 2375.98]  They were reminding me an email about the fact that there's only been three ad rolls that they've had to hear again and again and again.
[2375.98 --> 2376.38]  And again,
[2376.44 --> 2376.82]  Oh my God,
[2376.82 --> 2377.42]  we're so sorry.
[2377.48 --> 2377.62]  I mean,
[2377.62 --> 2378.42]  that's a great podcast.
[2378.48 --> 2380.14]  We don't want to ruin it with repetitive ad rolls.
[2380.32 --> 2380.44]  Yeah.
[2380.50 --> 2381.80]  So I think it's something we should keep an eye on.
[2381.86 --> 2382.06]  Okay.
[2382.12 --> 2383.16]  So in meantime,
[2383.22 --> 2384.60]  we should just tell people to go to Oxide.computer,
[2384.66 --> 2384.96]  I guess.
[2385.10 --> 2385.26]  Yeah,
[2385.34 --> 2385.56]  that's,
[2385.62 --> 2386.06]  that's all we need.
[2386.12 --> 2386.28]  All right.
[2386.28 --> 2387.06]  Sign up from the mailing list.
[2387.16 --> 2387.88]  And then we'll just like,
[2388.02 --> 2388.20]  we'll,
[2388.26 --> 2388.88]  we'll shut up.
[2388.90 --> 2389.16]  And Hey,
[2389.24 --> 2391.50]  if you got any feedback on the ads,
[2391.52 --> 2392.96]  like definitely send that to us,
[2392.96 --> 2393.12]  right?
[2393.64 --> 2393.96]  Sure.
[2394.10 --> 2394.76]  We're getting it.
[2394.96 --> 2395.32]  All right.
[2395.52 --> 2396.10]  Sounds good.
[2396.64 --> 2397.36]  Back to the show.
[2399.84 --> 2400.40]  All right.
[2400.44 --> 2402.16]  We're back with Jonathan Blow.
[2402.16 --> 2402.30]  Oh,
[2402.66 --> 2404.54]  I could say one thing before the question.
[2405.22 --> 2405.96]  I did later.
[2406.06 --> 2406.34]  So I did,
[2406.40 --> 2407.38]  I did two things on cell,
[2407.44 --> 2407.62]  right?
[2407.64 --> 2408.72]  So that was one of them.
[2409.20 --> 2412.46]  And then the other one was a lot easier and more simple because there are,
[2412.62 --> 2416.38]  there are some embarrassingly parallel problems in games still again,
[2416.40 --> 2417.46]  because we managed to factor it.
[2417.48 --> 2418.10]  And one of them is,
[2418.10 --> 2419.16]  is like particle systems,
[2419.16 --> 2421.00]  which is a like games.
[2421.28 --> 2422.80]  Like I mentioned explosions before.
[2422.80 --> 2424.54]  So you might have chunks of thing in an explosion,
[2424.54 --> 2428.40]  but you'll also have just like lots of little like dust particles and smoke and whatever.
[2428.40 --> 2428.68]  And,
[2428.74 --> 2435.92]  and the way those tend to happen in games is with a system that just does a bunch of little
[2435.92 --> 2438.12]  billboards that are animated over time.
[2438.12 --> 2438.52]  And like,
[2438.54 --> 2440.24]  they may have ways of interacting with the environment,
[2440.24 --> 2441.12]  but it's very constrained.
[2441.12 --> 2442.38]  So it's like a separate,
[2442.56 --> 2443.74]  it's like its own thing,
[2443.78 --> 2443.96]  right?
[2443.98 --> 2445.62]  Whenever you have something that's its own thing,
[2445.66 --> 2448.66]  you can optimize that and crank on it.
[2448.66 --> 2448.86]  Right.
[2448.92 --> 2449.42]  And so,
[2449.62 --> 2450.12]  but you know,
[2450.12 --> 2452.96]  I think you're making an interesting point earlier that when you have something that it's its own thing,
[2452.96 --> 2458.24]  it's not necessarily that core to gameplay because part of the game is that
[2458.24 --> 2460.04]  interconnectedness is what makes the game interesting.
[2460.22 --> 2460.40]  Yes.
[2460.46 --> 2460.80]  However,
[2460.98 --> 2461.28]  you know,
[2461.32 --> 2464.08]  every once in a while we discover things that are exceptions to that.
[2464.14 --> 2469.30]  So like particles are great because you just have a lot of them and they really help things look cool.
[2469.38 --> 2469.58]  Right.
[2469.66 --> 2470.74]  And we just found that.
[2471.36 --> 2471.56]  Okay.
[2471.64 --> 2474.22]  But how much of that is like,
[2474.32 --> 2474.96]  like,
[2475.08 --> 2475.22]  wow,
[2475.24 --> 2477.10]  this game is a lot more fun versus like,
[2477.14 --> 2477.26]  okay,
[2477.30 --> 2477.44]  this,
[2477.52 --> 2478.78]  this simply looks better.
[2479.58 --> 2479.98]  It's,
[2480.00 --> 2481.14]  it's more of the second one.
[2481.14 --> 2481.54]  Right.
[2481.54 --> 2481.78]  But,
[2481.78 --> 2483.84]  but actually even in the earlier days,
[2483.94 --> 2485.96]  those two were not as clearly differentiated.
[2486.08 --> 2487.32]  Like now graphics are pretty good.
[2487.54 --> 2487.70]  Right.
[2487.70 --> 2487.96]  You know,
[2488.02 --> 2488.14]  but,
[2488.20 --> 2488.84]  but back then,
[2488.90 --> 2489.12]  eh.
[2489.68 --> 2496.26]  I watched the games my kids play and they basically play the logical equivalent of Atari 2600 games.
[2496.46 --> 2496.64]  I mean,
[2496.66 --> 2497.02]  you know what I mean?
[2497.02 --> 2497.36]  It's like the,
[2497.54 --> 2500.34]  the games that are really captivate them are,
[2500.50 --> 2502.24]  the games are super simple,
[2502.24 --> 2503.94]  but have great gameplay.
[2504.10 --> 2504.42]  Yeah.
[2504.52 --> 2504.80]  You know,
[2504.82 --> 2505.80]  that aren't actually,
[2506.02 --> 2506.78]  there are no,
[2507.02 --> 2507.66]  you know,
[2507.66 --> 2507.84]  no,
[2507.84 --> 2508.34]  no particles.
[2509.16 --> 2509.56]  Yeah.
[2509.90 --> 2510.34]  I mean,
[2511.20 --> 2511.58]  I mean,
[2511.62 --> 2512.52]  my kids are like,
[2512.62 --> 2514.00]  have a low bar for their own entertainment,
[2514.24 --> 2515.60]  which is something that I've always believed.
[2516.06 --> 2516.08]  So,
[2516.08 --> 2516.64]  well,
[2516.70 --> 2517.08]  I mean,
[2517.08 --> 2518.80]  there's weird generational stuff that happened,
[2518.84 --> 2519.04]  right?
[2519.08 --> 2521.06]  So around the time of Minecraft,
[2521.26 --> 2522.76]  which may be one of the games that they play,
[2522.82 --> 2523.24]  I don't know.
[2523.60 --> 2523.96]  So,
[2523.96 --> 2526.80]  so Minecraft came out and it was this super low res,
[2526.92 --> 2527.66]  super chunky,
[2528.42 --> 2529.28]  very pixely,
[2529.52 --> 2530.90]  both 3d and 2d.
[2530.90 --> 2533.84]  And everybody looks at that,
[2533.92 --> 2535.54]  who was a professional game developer and says,
[2535.68 --> 2535.94]  Oh,
[2536.40 --> 2536.66]  you know,
[2536.74 --> 2537.78]  yucky graphics or whatever,
[2537.78 --> 2539.08]  but kids don't know that.
[2539.30 --> 2539.40]  Right.
[2539.46 --> 2542.90]  They don't know that we worked so hard to get away from the Atari 2600.
[2542.90 --> 2543.66]  They just think like,
[2543.70 --> 2543.78]  Oh,
[2543.78 --> 2545.26]  that's a retro style or something.
[2545.26 --> 2545.52]  Right.
[2545.58 --> 2545.76]  Right.
[2546.06 --> 2546.46]  And,
[2546.52 --> 2552.50]  and so it didn't have the negative association that it would have for somebody who spends all day trying to make things look nice.
[2552.50 --> 2552.72]  Right.
[2552.88 --> 2553.14]  Right.
[2553.14 --> 2553.34]  And,
[2553.34 --> 2554.60]  and so it just,
[2555.26 --> 2555.50]  it's just,
[2555.56 --> 2556.18]  it's just fun.
[2556.28 --> 2556.72]  I'm sorry.
[2556.82 --> 2556.98]  I,
[2556.98 --> 2557.26]  I,
[2557.26 --> 2557.92]  I'm sorry.
[2558.00 --> 2558.14]  You know,
[2558.14 --> 2558.64]  I'm a kid.
[2558.78 --> 2559.36]  I'm stupid.
[2559.84 --> 2560.88]  I don't know any better.
[2561.06 --> 2561.32]  I'm just,
[2561.36 --> 2561.92]  it's just fun.
[2562.14 --> 2563.66]  Minecraft is actually a reasonable game though.
[2563.68 --> 2563.98]  I don't know.
[2564.00 --> 2564.52]  I don't know what,
[2564.54 --> 2565.74]  what games you're talking about.
[2565.74 --> 2567.48]  I think this is more like the games on their phone.
[2567.58 --> 2571.82]  They play basically these very simple arcade games that are very,
[2571.96 --> 2572.14]  I mean,
[2572.14 --> 2574.06]  they're definitely very precise in terms of what they,
[2574.20 --> 2574.50]  but they're,
[2574.56 --> 2576.16]  and they're very captivating for them.
[2576.16 --> 2576.36]  You know,
[2576.38 --> 2576.76]  they're very,
[2576.82 --> 2577.10]  and they,
[2577.16 --> 2579.40]  they play levels that their friends make and stuff like,
[2579.46 --> 2579.64]  I mean,
[2579.64 --> 2579.86]  it's,
[2579.86 --> 2582.00]  it's interesting in just terms of like the,
[2582.00 --> 2582.96]  the,
[2583.12 --> 2585.32]  the relative simplicity of this stuff.
[2585.54 --> 2585.94]  And,
[2586.06 --> 2586.20]  you know,
[2586.20 --> 2586.40]  it's,
[2586.52 --> 2590.82]  it's amazing to me also how much the kids still love these basic puzzle
[2590.82 --> 2591.12]  games.
[2591.12 --> 2591.74]  They're kind of like the,
[2591.74 --> 2593.74]  the Tetris kind of,
[2593.96 --> 2594.16]  yeah,
[2594.16 --> 2594.54]  exactly.
[2594.66 --> 2594.80]  Right.
[2594.80 --> 2594.98]  I mean,
[2594.98 --> 2599.52]  it's like the logical descendants of Tetris are still really captivating,
[2599.82 --> 2600.12]  you know,
[2600.18 --> 2601.14]  even though they are.
[2601.24 --> 2601.48]  And just,
[2601.58 --> 2606.12]  I think it emphasizes also that the gameplay is really important and that
[2606.12 --> 2607.04]  it's easy,
[2607.46 --> 2609.84]  especially with an abundance of hardware to kind of,
[2609.84 --> 2611.90]  kind of like do things that are cool,
[2611.90 --> 2615.68]  but do they actually result in,
[2615.78 --> 2616.86]  in a better game?
[2616.98 --> 2617.06]  I mean,
[2617.10 --> 2617.40]  well,
[2617.44 --> 2617.94]  for some of them,
[2618.02 --> 2620.00]  I'm sure it's like the more immersive the experience,
[2620.08 --> 2624.20]  the better the game for some people and having like dust come up and a
[2624.20 --> 2626.56]  sound effect associated with that is going to make it more immersive.
[2626.84 --> 2627.22]  Yeah.
[2627.22 --> 2628.64]  There's definitely different,
[2628.64 --> 2631.16]  different ideas of what a game is,
[2631.20 --> 2631.42]  right?
[2631.70 --> 2631.96]  Like,
[2632.00 --> 2634.30]  so somebody who plays Red Dead Redemption two,
[2634.44 --> 2636.98]  which is one of these games that's trying to be very high graphical fidelity
[2636.98 --> 2639.64]  and make a mood out of that.
[2639.64 --> 2642.18]  And all this probably isn't going to be playing the games that you're talking
[2642.18 --> 2642.46]  about.
[2642.64 --> 2642.78]  Exactly.
[2642.88 --> 2643.02]  Yeah.
[2643.10 --> 2643.28]  But,
[2643.48 --> 2644.02]  but that's,
[2644.08 --> 2645.00]  that's maybe a good sign.
[2645.06 --> 2645.56]  It means that,
[2645.68 --> 2646.74]  that as an industry,
[2646.74 --> 2650.66]  we have a lot of different things that we could do to talk to different
[2650.66 --> 2650.94]  people,
[2650.94 --> 2651.26]  but we,
[2651.26 --> 2652.66]  we ran over.
[2652.66 --> 2657.74]  So I was going to go back to the butterfly effects because one question
[2657.74 --> 2661.46]  that I got in an interview for a job and also one of my friends worked on
[2661.46 --> 2661.72]  Halo.
[2661.88 --> 2666.32]  So like I hear a lot about it is like the distributed systems problem of like
[2666.32 --> 2667.24]  multiplayer games.
[2667.24 --> 2667.60]  So like,
[2667.64 --> 2669.06]  say like I shoot Brian.
[2669.30 --> 2669.44]  Hey,
[2669.56 --> 2669.84]  do wait,
[2669.88 --> 2670.68]  that's your example.
[2670.90 --> 2673.32]  Like that's commonly come back to that.
[2674.64 --> 2675.72]  Can't you shoot a duck?
[2675.88 --> 2676.82]  Why do you need to shoot Brian?
[2676.92 --> 2677.52]  Because it's Halo.
[2677.70 --> 2677.98]  All right,
[2678.02 --> 2678.22]  fine.
[2678.22 --> 2678.82]  So like,
[2678.88 --> 2679.06]  and,
[2679.06 --> 2679.32]  and,
[2679.32 --> 2682.92]  and Brian moves or at least thinks that he moves out of the way,
[2682.98 --> 2684.04]  but like on my screen,
[2684.04 --> 2685.78]  it looks like I hit him.
[2686.00 --> 2686.16]  Yeah.
[2686.46 --> 2688.64]  It's like solving that problem seems to be like,
[2688.70 --> 2691.86]  or at least from people that I've heard solving that problem in a way that
[2691.86 --> 2692.86]  people can't cheat,
[2692.86 --> 2695.40]  which is also a problem that Halo had for a long time.
[2695.52 --> 2698.50]  It seems to be not like logic based.
[2698.66 --> 2702.72]  It's more like filling in the holes or I was wondering your take,
[2702.82 --> 2703.10]  honestly.
[2704.02 --> 2706.02]  This is a complicated subject.
[2706.02 --> 2706.46]  Um,
[2707.52 --> 2709.40]  behind which there is much history.
[2710.24 --> 2710.90]  So there's,
[2711.02 --> 2711.16]  okay.
[2711.52 --> 2713.34]  The fundamental problem again,
[2713.34 --> 2713.82]  there is,
[2713.82 --> 2714.70]  is network latency,
[2714.70 --> 2715.08]  right?
[2715.36 --> 2718.96]  So even if everybody's getting perfect information all the time,
[2718.96 --> 2719.14]  which,
[2719.24 --> 2719.66]  which isn't,
[2719.74 --> 2720.62]  doesn't actually happen,
[2720.88 --> 2722.40]  but we're going to simplify and say that,
[2722.48 --> 2726.02]  that everybody's getting all the information about what happens when it's
[2726.02 --> 2726.10]  just,
[2726.14 --> 2728.80]  they're getting it with different amounts of time because I have a 10 ping to a
[2728.80 --> 2730.74]  server and my friend has 110 ping.
[2730.82 --> 2732.32]  That's like a 10th of a second difference,
[2732.42 --> 2734.98]  which sounds like a small amount of time,
[2734.98 --> 2736.84]  but it's actually quite large,
[2736.84 --> 2737.06]  you know,
[2737.06 --> 2739.78]  at the speeds that people move in games in a 10th of a second,
[2740.44 --> 2740.78]  you know,
[2740.92 --> 2743.84]  you can be like a third of the way over on the screen.
[2744.20 --> 2744.86]  If you can be,
[2744.86 --> 2745.82]  you know,
[2745.88 --> 2749.36]  completely non intersecting with where your body was before that 10th of a
[2749.36 --> 2749.60]  second.
[2749.60 --> 2749.90]  Right.
[2750.32 --> 2750.68]  And,
[2750.78 --> 2753.74]  and so these time spans matter actually a great deal.
[2754.20 --> 2755.18]  And so what do you,
[2755.28 --> 2757.24]  what do you do about that?
[2757.54 --> 2757.80]  Right.
[2758.32 --> 2758.58]  And,
[2758.62 --> 2762.70]  and the one reason why this is so complicated is because the answer to this
[2762.70 --> 2766.58]  question or what you should be reasonably think about has changed a lot over
[2766.58 --> 2766.94]  time.
[2766.94 --> 2767.16]  Right.
[2767.18 --> 2768.74]  So my first professional game,
[2768.78 --> 2769.04]  actually,
[2769.06 --> 2770.58]  I started in the late nineties,
[2770.70 --> 2771.04]  1996.
[2772.10 --> 2776.74]  And we were working really hard to do this kind of like live client server
[2776.74 --> 2779.60]  update stuff over 9,600 bod modems,
[2779.60 --> 2780.82]  which was good.
[2780.94 --> 2781.14]  I mean,
[2781.14 --> 2782.78]  those were fast modems back then,
[2782.86 --> 2782.96]  man.
[2782.96 --> 2783.96]  9,600 bod.
[2784.56 --> 2785.08]  And again,
[2785.08 --> 2787.44]  we started having difficulties.
[2787.44 --> 2792.14]  Like how much time does it just take the bites to go over the modem?
[2792.14 --> 2796.82]  That was like an appreciative percentage of the total latency actually.
[2797.48 --> 2797.62]  And you're,
[2797.70 --> 2799.84]  you were trying to do effectively a first person shooter.
[2800.30 --> 2800.46]  Yeah,
[2800.48 --> 2800.76]  it was,
[2800.82 --> 2801.48]  it was a little bit,
[2801.54 --> 2803.84]  it was like a sci-fi hover tank game.
[2804.00 --> 2805.64]  And so a lot of the weapons were indirect.
[2805.84 --> 2806.24]  It would be like,
[2806.28 --> 2807.52]  I fire a missile at this guy.
[2807.54 --> 2807.70]  Right.
[2807.70 --> 2809.60]  Which is one way of working around this problem.
[2809.72 --> 2810.04]  Right.
[2810.32 --> 2810.50]  Right.
[2810.62 --> 2811.84]  It could take longer.
[2812.02 --> 2812.54]  Cause the missile,
[2812.54 --> 2815.72]  the missile is simulated on the server and then the server decides what
[2815.72 --> 2817.54]  happens and you eliminate this.
[2817.64 --> 2817.74]  Right.
[2818.06 --> 2818.38]  But,
[2818.76 --> 2819.02]  okay.
[2819.68 --> 2820.88]  So the problem is in,
[2820.94 --> 2822.58]  in these like first person shooter games,
[2822.66 --> 2827.88]  people move pretty fast and the server can't be authoritative over certain
[2827.88 --> 2828.52]  things.
[2828.52 --> 2828.90]  Right.
[2828.94 --> 2829.70]  So for example,
[2829.70 --> 2830.98]  if I move the mouse,
[2831.24 --> 2831.60]  if,
[2831.72 --> 2832.78]  if that is,
[2832.98 --> 2837.58]  I tell the server how much I moved the mouse and then the server decides how
[2837.58 --> 2839.84]  much I turned and then it tells me how much I turned.
[2839.84 --> 2841.42]  And then I go that much.
[2841.42 --> 2843.22]  Even if the numbers,
[2843.46 --> 2846.52]  the latency numbers sound really small to you,
[2846.54 --> 2848.18]  it's going to feel really bad.
[2848.32 --> 2848.42]  Right.
[2848.48 --> 2851.32]  Cause you are now well within the domain of human perception.
[2852.16 --> 2853.50]  And not even just perception,
[2853.64 --> 2854.02]  but like,
[2854.06 --> 2854.66]  there's a way,
[2854.76 --> 2857.42]  like I forget the name of this,
[2857.50 --> 2859.86]  but there's a way that like humans use tools,
[2859.94 --> 2860.24]  right.
[2860.26 --> 2861.26]  Where like you,
[2861.26 --> 2863.16]  you consider it part of your body almost.
[2863.26 --> 2863.56]  Right.
[2863.76 --> 2864.12]  You know?
[2864.24 --> 2865.76]  So if you've got a hammer in your hand,
[2865.94 --> 2869.82]  you're not thinking that hard about the fact that you're using a hammer or
[2869.82 --> 2871.62]  you're holding a thing that's hitting a thing,
[2871.62 --> 2872.02]  you're like,
[2872.04 --> 2872.14]  Oh,
[2872.14 --> 2873.28]  I'm just whacking this thing.
[2873.38 --> 2874.38]  There's some kind of like,
[2874.44 --> 2876.00]  like mental fusion that happens.
[2876.00 --> 2876.24]  Right.
[2876.24 --> 2878.60]  And so games take advantage of that actually.
[2878.60 --> 2878.94]  Right.
[2878.96 --> 2880.72]  So if you're playing a keyboard and mouse game,
[2880.78 --> 2881.02]  I mean,
[2881.02 --> 2882.40]  destiny is usually a game pad,
[2882.50 --> 2884.52]  but mouse is a little bit harder.
[2884.62 --> 2885.32]  So I'm going to use that one.
[2885.78 --> 2886.16]  You know,
[2886.22 --> 2886.40]  you,
[2886.40 --> 2886.70]  you,
[2886.70 --> 2886.82]  you,
[2887.06 --> 2888.78]  somebody who's played these games a little bit,
[2888.82 --> 2891.34]  doesn't think about the fact that they're controlling it.
[2891.34 --> 2891.56]  Right.
[2891.56 --> 2894.10]  They're just moving their hand and it's instinctual.
[2894.10 --> 2894.48]  Right.
[2894.84 --> 2897.94]  And you kill the ability for that loop to happen.
[2898.08 --> 2899.22]  It does not take much latency.
[2899.36 --> 2899.66]  I would imagine.
[2900.02 --> 2900.30]  Not much.
[2900.38 --> 2900.52]  Well,
[2900.56 --> 2902.14]  and also variable amounts of latency.
[2902.32 --> 2902.42]  Right.
[2902.50 --> 2902.78]  Oh,
[2902.78 --> 2903.16]  interesting.
[2903.46 --> 2903.70]  Interesting.
[2903.84 --> 2905.18]  Because if like your body,
[2905.42 --> 2908.12]  your brain can surprisingly adjust to a fixed amount of latency.
[2908.24 --> 2908.84]  It's not good.
[2909.02 --> 2909.22]  Right.
[2909.24 --> 2909.92]  But you can.
[2910.16 --> 2910.34]  Right.
[2910.68 --> 2911.50]  But when it's,
[2911.50 --> 2912.06]  you know,
[2912.06 --> 2912.90]  going up and down,
[2912.98 --> 2913.36]  you're like,
[2913.40 --> 2913.84]  I don't,
[2913.92 --> 2915.02]  it feels terrible.
[2915.12 --> 2916.06]  It feels very frustrating.
[2916.18 --> 2916.26]  Right.
[2916.26 --> 2916.58]  Interesting.
[2917.08 --> 2917.48]  So,
[2918.48 --> 2918.80]  well,
[2918.80 --> 2919.16]  what do you,
[2919.24 --> 2919.76]  what do you do?
[2919.94 --> 2920.12]  Right.
[2920.18 --> 2921.80]  And so what people started doing,
[2922.08 --> 2923.62]  there were some famous,
[2923.62 --> 2927.94]  presentations at conferences in like maybe late nineties,
[2928.00 --> 2928.62]  early two thousands.
[2928.74 --> 2929.18]  I forget.
[2930.46 --> 2933.62]  Evangelizing different ways of solving this problem that I didn't personally like.
[2934.30 --> 2935.88]  So one of the things that you do,
[2936.10 --> 2936.64]  well,
[2936.74 --> 2937.04]  okay.
[2937.98 --> 2939.68]  There's at least two different problems,
[2939.78 --> 2940.02]  right?
[2940.32 --> 2942.80]  So one is this problem of variable latency.
[2942.94 --> 2946.26]  People are seeing the world state with different,
[2946.92 --> 2949.26]  how do I explain all this?
[2949.94 --> 2950.92]  There's a skew,
[2951.00 --> 2951.16]  right?
[2951.20 --> 2952.20]  In the way that they're seeing the world.
[2952.64 --> 2953.00]  Yeah.
[2953.00 --> 2953.34]  I mean,
[2953.40 --> 2953.64]  okay.
[2953.98 --> 2955.04]  There's the fact that,
[2955.04 --> 2958.88]  that where I see things is by definition,
[2958.88 --> 2960.36]  not where the server thinks they are.
[2960.36 --> 2960.72]  Right.
[2960.82 --> 2961.58]  That's one thing.
[2961.68 --> 2963.50]  And then you have a second thing.
[2963.50 --> 2964.06]  That's like,
[2964.10 --> 2967.36]  if two people take an action at about the same amount of time,
[2967.40 --> 2968.50]  about the same time,
[2968.50 --> 2971.32]  and it takes a certain amount of time to travel to the server and they're
[2971.32 --> 2972.22]  conflicting actions,
[2972.22 --> 2973.12]  like who wins.
[2973.24 --> 2973.46]  Right.
[2973.52 --> 2973.68]  Right.
[2973.68 --> 2974.64]  That's a whole other thing.
[2975.42 --> 2977.70]  Usually we punt more on that second one than the first one.
[2977.76 --> 2978.10]  But anyway,
[2978.30 --> 2978.58]  so,
[2978.68 --> 2980.04]  so if we go back to the gun example,
[2980.48 --> 2980.88]  let's say,
[2980.88 --> 2981.34]  let's say,
[2981.42 --> 2981.62]  you know,
[2981.68 --> 2981.92]  you're,
[2981.98 --> 2984.10]  you're standing there and then you duck behind a corner,
[2984.10 --> 2984.64]  right?
[2985.14 --> 2985.36]  In,
[2985.36 --> 2986.22]  in a hundred milliseconds.
[2986.22 --> 2986.82]  Uh,
[2986.82 --> 2989.16]  but I shoot you before I see you duck behind the corner.
[2989.56 --> 2989.80]  Right.
[2990.38 --> 2990.60]  We're,
[2990.76 --> 2992.44]  we can even take the corner out of it.
[2992.44 --> 2994.18]  Let's just say you're in the open space.
[2994.18 --> 2994.42]  Right.
[2994.70 --> 2995.04]  So,
[2995.12 --> 2995.48]  so what,
[2995.98 --> 2998.32]  what a lot of systems did that people started building was like,
[2998.36 --> 2998.68]  okay,
[2998.68 --> 3003.86]  we look at when the shoot message comes in and we'll sort of go back in
[3003.86 --> 3005.48]  time to like,
[3005.48 --> 3006.02]  Oh,
[3006.08 --> 3006.56]  uh,
[3006.56 --> 3009.32]  to when it was actually fired,
[3009.36 --> 3011.48]  what we think your latency was,
[3011.54 --> 3012.18]  which by the way,
[3012.18 --> 3013.54]  may not be a correct number,
[3013.54 --> 3015.12]  especially if it's fluctuating.
[3015.12 --> 3015.40]  Right.
[3015.60 --> 3020.02]  We like go back in time that much and see if it looks like you were
[3020.02 --> 3021.80]  hittable from where I am.
[3022.16 --> 3023.32]  Like not,
[3023.48 --> 3026.06]  not by exactly where I was pointing,
[3026.06 --> 3026.70]  because again,
[3026.70 --> 3027.94]  that won't totally make sense,
[3027.94 --> 3029.00]  but like in general,
[3029.00 --> 3031.80]  and then we'll count you as hit or not hit.
[3031.80 --> 3032.00]  Right.
[3032.04 --> 3035.08]  But what that looks like from your side is like,
[3035.08 --> 3038.16]  we're in this intense gunfight and you get some shots off and you duck
[3038.16 --> 3038.82]  around the corner.
[3038.82 --> 3041.68]  And maybe I hit you around the corner.
[3041.68 --> 3042.06]  Right.
[3042.10 --> 3044.18]  Because you weren't around the corner before.
[3044.38 --> 3044.58]  Right.
[3044.70 --> 3045.32]  And maybe,
[3045.58 --> 3045.96]  and again,
[3045.96 --> 3047.08]  this is where it gets complicated.
[3047.26 --> 3051.64]  Like maybe at the time when the server needs to make the decision,
[3051.84 --> 3053.46]  you weren't around the corner yet,
[3053.48 --> 3054.24]  according to it.
[3054.54 --> 3054.84]  Right.
[3054.96 --> 3056.12]  Because the server could decide,
[3056.22 --> 3056.28]  Oh,
[3056.28 --> 3057.64]  you're behind the corner now,
[3057.64 --> 3058.62]  but you weren't before,
[3058.62 --> 3060.74]  but we're going to give you the benefit of the doubt or whatever.
[3061.04 --> 3062.34]  There's all sorts of weird heuristics.
[3062.50 --> 3062.70]  Huh.
[3062.78 --> 3063.14]  Interesting.
[3063.34 --> 3066.18]  The fact that there's all sorts of weird heuristics means that by
[3066.18 --> 3066.70]  definition,
[3066.70 --> 3068.34]  not everything is going to feel good.
[3068.58 --> 3069.90]  Something's going to go wrong.
[3070.02 --> 3070.24]  Right.
[3070.36 --> 3072.18]  So it's kind of at its core,
[3072.32 --> 3074.78]  not that solvable of a problem.
[3075.08 --> 3075.30]  Right.
[3075.38 --> 3076.16]  But I mean,
[3076.24 --> 3076.68]  you know,
[3076.70 --> 3079.02]  today internet is a lot better usually.
[3079.22 --> 3079.40]  Right.
[3080.08 --> 3081.70]  And so you have some of these things like,
[3081.80 --> 3082.08]  like,
[3082.12 --> 3083.28]  you know,
[3083.28 --> 3084.72]  this thing Google is,
[3084.80 --> 3085.70]  is doing right now,
[3085.76 --> 3086.56]  the Stadia thing,
[3086.56 --> 3087.06]  which is like,
[3087.12 --> 3087.26]  look,
[3087.58 --> 3090.32]  the entire game just runs on a server and we just send you the
[3090.32 --> 3090.62]  pixels.
[3090.94 --> 3091.30]  Right.
[3091.56 --> 3092.30]  Which doesn't,
[3093.02 --> 3094.16]  it's not how I would do it.
[3094.28 --> 3094.98]  Let's put it that way.
[3094.98 --> 3095.96]  That seems,
[3096.18 --> 3098.18]  the Stadia seems to have,
[3098.38 --> 3099.94]  it seems to be rather controversial.
[3100.24 --> 3100.48]  Yeah.
[3100.72 --> 3101.82]  It seems to have,
[3102.68 --> 3105.58]  but we can just use that to highlight the fact that like,
[3106.66 --> 3109.56]  the assumptions there have to be very different.
[3109.68 --> 3110.60]  They have to be that like,
[3110.64 --> 3110.76]  oh,
[3110.76 --> 3112.78]  latency is going to be consistently very small.
[3112.94 --> 3113.22]  Right.
[3113.22 --> 3114.90]  And so like what,
[3114.90 --> 3116.78]  what I always think about is like,
[3116.80 --> 3116.98]  okay,
[3116.98 --> 3117.16]  this,
[3117.22 --> 3117.96]  this kind of like,
[3117.96 --> 3118.56]  you know,
[3118.88 --> 3123.48]  client side or client side prediction along with server side
[3123.48 --> 3125.44]  heuristics about managing these kinds of events.
[3126.52 --> 3127.14]  I always,
[3127.28 --> 3128.92]  as a player want to put a cap on that.
[3129.00 --> 3129.94]  I want to be able to say like,
[3129.98 --> 3130.14]  look,
[3130.22 --> 3132.82]  I don't want to play with anybody with a ping more than 50
[3132.82 --> 3133.28]  milliseconds.
[3133.34 --> 3133.66]  Right.
[3133.68 --> 3134.90]  So I just wish a game would like,
[3134.96 --> 3136.06]  let me do that.
[3136.14 --> 3136.26]  Oh,
[3136.36 --> 3138.32]  like put that in the matchmaking or something,
[3138.40 --> 3138.62]  you know,
[3138.62 --> 3138.92]  it's like,
[3138.98 --> 3140.84]  it's fine to have this kind of a thing,
[3140.84 --> 3142.06]  but like,
[3142.12 --> 3142.48]  let me,
[3142.60 --> 3143.96]  let me control it or something.
[3143.98 --> 3144.88]  And nobody's done that.
[3144.88 --> 3146.48]  So maybe I have to do that at some point.
[3146.58 --> 3146.94]  I don't know.
[3147.30 --> 3147.44]  Yeah.
[3147.50 --> 3148.42]  And you think about the,
[3148.58 --> 3148.72]  I mean,
[3148.72 --> 3151.86]  this is a hard problem because you are up against real
[3151.86 --> 3152.76]  physical limitations.
[3153.06 --> 3153.18]  I mean,
[3153.18 --> 3154.12]  you think about like a,
[3154.18 --> 3154.40]  you know,
[3154.42 --> 3156.00]  50 millisecond latency,
[3156.80 --> 3157.76]  which is like not,
[3157.92 --> 3158.18]  I mean,
[3158.26 --> 3159.08]  there are,
[3159.32 --> 3161.38]  we can put physical constraints about how close that
[3161.38 --> 3162.52]  person is going to be to you.
[3163.34 --> 3163.70]  Right.
[3163.78 --> 3163.96]  I mean,
[3163.96 --> 3166.48]  it's like that person is not going to be in New York
[3166.48 --> 3167.42]  while you're in California.
[3167.42 --> 3167.54]  Yeah.
[3167.76 --> 3168.78]  And yet that's a,
[3168.80 --> 3170.02]  it's a human perceptible.
[3170.10 --> 3170.18]  I mean,
[3170.20 --> 3172.12]  that has human perception consequences.
[3172.12 --> 3174.70]  So there are real physical consequences for how these
[3174.70 --> 3175.72]  kind of,
[3175.72 --> 3175.98]  uh,
[3175.98 --> 3177.46]  and physical consequences for the game.
[3177.74 --> 3178.16]  Yeah.
[3178.62 --> 3179.38]  So it,
[3179.38 --> 3179.70]  it,
[3179.70 --> 3180.04]  how,
[3180.20 --> 3180.40]  I mean,
[3180.52 --> 3181.70]  it sounds like,
[3181.74 --> 3181.84]  I mean,
[3181.84 --> 3182.98]  like take the stadia thing.
[3182.98 --> 3183.94]  So why,
[3184.44 --> 3184.76]  um,
[3184.76 --> 3184.88]  well,
[3184.92 --> 3185.20]  first of all,
[3185.20 --> 3186.56]  actually this kind of the,
[3186.56 --> 3189.48]  this correction of the past,
[3189.48 --> 3191.56]  which our brains do do,
[3191.56 --> 3191.88]  right?
[3191.90 --> 3195.18]  Cause your brain will correct for time that it
[3195.18 --> 3195.90]  didn't perceive.
[3195.90 --> 3198.32]  So if you ever noticed that,
[3198.32 --> 3198.92]  like you're,
[3199.04 --> 3199.40]  if you,
[3199.52 --> 3202.54]  you'll notice this when your eye falls on a clock with a
[3202.54 --> 3205.72]  second hand and the second hand seems to be stopped.
[3206.56 --> 3207.48]  And then it like,
[3207.50 --> 3208.48]  it starts moving again.
[3208.58 --> 3209.92]  That's because your brain has,
[3210.04 --> 3212.40]  has corrected for the time that your eye was in motion.
[3213.16 --> 3215.02]  So our brains do the same thing too.
[3215.02 --> 3216.28]  And we don't like it actually.
[3216.42 --> 3216.60]  I mean,
[3216.64 --> 3218.04]  it can have like these,
[3218.16 --> 3219.36]  these effects that are,
[3219.74 --> 3220.52]  so do you,
[3220.52 --> 3222.38]  did you not like that approach?
[3222.38 --> 3222.82]  I mean,
[3222.94 --> 3223.04]  it's,
[3223.04 --> 3224.00]  well,
[3224.20 --> 3225.50]  you disagreed with the,
[3225.64 --> 3225.94]  here,
[3226.06 --> 3226.80]  here's the thing.
[3227.82 --> 3231.50]  Like it comes down to why do you play games to begin with?
[3231.64 --> 3231.86]  And,
[3231.92 --> 3234.28]  and different kinds of games have different audiences that have
[3234.28 --> 3236.06]  different reasons for why they play games.
[3236.32 --> 3238.40]  And there's this weird,
[3239.06 --> 3243.88]  what I would say conflict in the game design community where
[3243.88 --> 3246.68]  there are incentives to pull different directions.
[3246.68 --> 3246.96]  Right.
[3246.96 --> 3247.20]  Okay.
[3247.26 --> 3247.50]  So,
[3248.16 --> 3249.08]  so a shooter game,
[3249.08 --> 3249.60]  right.
[3250.72 --> 3256.44]  Is in theory about being better or worse at being able to do the
[3256.44 --> 3257.12]  shooty stuff.
[3257.36 --> 3257.76]  Right.
[3257.90 --> 3258.66]  And to like,
[3258.74 --> 3260.48]  when it's a competitive kind of thing,
[3260.48 --> 3261.44]  it's like,
[3261.44 --> 3261.80]  I,
[3262.04 --> 3262.58]  if I win,
[3262.62 --> 3264.04]  I'm probably better than you.
[3264.04 --> 3264.44]  Uh,
[3264.68 --> 3267.04]  mostly like in the same way that if sports teams win,
[3267.16 --> 3267.50]  whatever,
[3267.68 --> 3268.50]  one of them's better.
[3268.50 --> 3268.82]  Right.
[3269.12 --> 3270.34]  And so it's getting,
[3270.50 --> 3274.46]  playing that game is ostensibly to the people who are interested in
[3274.46 --> 3277.40]  it about building your skills at the game and,
[3277.40 --> 3277.68]  and,
[3277.68 --> 3279.74]  and working on it in some sense and getting better.
[3279.74 --> 3279.96]  And,
[3280.08 --> 3280.52]  and,
[3280.78 --> 3281.06]  you know,
[3281.06 --> 3283.44]  there are some shooter games that are way more serious.
[3283.44 --> 3283.84]  So,
[3283.96 --> 3284.52]  so for example,
[3284.52 --> 3286.28]  there's a game called counter strike on the PC.
[3286.36 --> 3287.60]  I guess they did console versions,
[3287.84 --> 3290.36]  but it's mostly PC game where it's like,
[3290.36 --> 3291.58]  it gets really serious.
[3291.58 --> 3291.98]  Right.
[3292.00 --> 3294.82]  There are like world tournaments of like,
[3295.10 --> 3295.74]  you know,
[3296.16 --> 3299.24]  video game sports teams playing each other at this game all the time.
[3299.56 --> 3300.50]  And it's like,
[3300.56 --> 3303.16]  it's a very fast and vicious game.
[3303.16 --> 3303.54]  Right.
[3303.54 --> 3304.60]  And the skill level is very,
[3304.66 --> 3304.80]  very,
[3304.86 --> 3305.28]  very high.
[3305.28 --> 3305.52]  Right.
[3305.62 --> 3306.52]  So like what,
[3306.90 --> 3311.30]  what a lot of people want to play this kind of shooter game for is for a
[3311.30 --> 3313.18]  more casual version of that.
[3313.18 --> 3313.56]  Right.
[3313.80 --> 3316.84]  But if you're a company and you want to sell a thing to the most people,
[3316.84 --> 3317.48]  right.
[3318.10 --> 3318.90]  You it's,
[3318.90 --> 3319.58]  it's tempting.
[3319.58 --> 3319.88]  And,
[3319.96 --> 3321.68]  and I think this is true as well.
[3321.68 --> 3324.68]  Like a certain number of people are playing it for a different reason.
[3324.82 --> 3330.58]  They want to be like the fantasy of the cool army guy who like kicks ass.
[3330.58 --> 3330.86]  Right.
[3330.86 --> 3330.90]  Right.
[3331.24 --> 3334.10]  But maybe they don't care about being good at it.
[3334.26 --> 3334.62]  Exactly.
[3334.76 --> 3335.10]  Right.
[3335.50 --> 3335.70]  And,
[3335.76 --> 3335.92]  and,
[3335.92 --> 3337.38]  and if you include those people,
[3337.56 --> 3339.04]  you get a bigger audience.
[3339.04 --> 3339.34]  Right.
[3339.46 --> 3339.68]  Right.
[3339.76 --> 3341.88]  And I'm not sure which group is actually bigger.
[3341.96 --> 3344.08]  I think most people would tell you that that latter group was bigger,
[3344.08 --> 3345.18]  but I think that's kind of wrong.
[3345.18 --> 3345.38]  Like,
[3345.40 --> 3345.78]  I think,
[3345.90 --> 3347.20]  I think people,
[3347.42 --> 3351.20]  people like being competent actually.
[3351.38 --> 3351.60]  Yes.
[3351.60 --> 3351.88]  Mostly.
[3352.00 --> 3352.28]  Right.
[3352.42 --> 3352.68]  Right.
[3352.70 --> 3353.82]  And so I think that's undervalued,
[3353.90 --> 3354.08]  but,
[3354.42 --> 3355.86]  but the point is you'll have,
[3355.86 --> 3360.10]  you'll make different design decisions depending on which game you think you're making.
[3360.38 --> 3360.60]  Right.
[3360.82 --> 3361.56]  And so,
[3361.68 --> 3363.46]  so this design decision about like,
[3364.04 --> 3367.24]  let's give people the most smooth feeling,
[3367.30 --> 3372.42]  most comfortable experience at the cost of unfairness,
[3372.46 --> 3372.82]  essentially.
[3373.10 --> 3373.38]  Right.
[3373.38 --> 3376.18]  Like maybe you got out of the way in time and you still got hit.
[3376.18 --> 3376.42]  Right.
[3376.48 --> 3376.78]  That,
[3376.90 --> 3382.06]  that turns off people who are interested in competence to a certain degree,
[3382.06 --> 3383.54]  because they get really good at the game.
[3383.64 --> 3385.24]  The more good you are at it,
[3385.38 --> 3386.24]  the more injustice.
[3386.76 --> 3386.98]  Yeah.
[3387.02 --> 3387.34]  The more,
[3387.42 --> 3387.86]  first of all,
[3387.86 --> 3388.82]  the more you see these things,
[3388.90 --> 3392.34]  like a new player might not notice that this is really happening,
[3392.34 --> 3393.38]  but after a while you're like,
[3393.42 --> 3393.60]  no,
[3393.66 --> 3393.78]  I,
[3394.10 --> 3394.28]  that,
[3394.46 --> 3395.08]  that was wrong.
[3395.08 --> 3395.48]  Right.
[3395.70 --> 3395.98]  Interesting.
[3396.70 --> 3401.38]  And then also the more you feel you're being disrespected by the game.
[3401.38 --> 3402.00]  Cause it's like,
[3402.02 --> 3402.18]  look,
[3402.18 --> 3405.92]  I'm putting in this effort and the fricking game is not even right.
[3405.92 --> 3407.42]  And it's just angering.
[3407.42 --> 3407.62]  Right.
[3407.68 --> 3408.12]  Interesting.
[3408.28 --> 3408.52]  Um,
[3408.82 --> 3409.14]  and,
[3409.24 --> 3409.72]  and so,
[3409.86 --> 3410.60]  yeah,
[3410.68 --> 3410.96]  I,
[3411.06 --> 3411.62]  I would,
[3411.62 --> 3417.02]  I would feel that the right decision to make would be more in support of
[3417.02 --> 3417.54]  competence,
[3417.54 --> 3419.10]  like whatever that means.
[3419.12 --> 3419.54]  And,
[3419.68 --> 3420.76]  and I hope we go that way,
[3420.76 --> 3422.52]  but we haven't gone that way historically.
[3422.98 --> 3423.34]  Like,
[3423.44 --> 3424.38]  so for example,
[3424.76 --> 3425.80]  I would just say like,
[3425.84 --> 3426.04]  look,
[3426.80 --> 3427.04]  you know,
[3427.04 --> 3427.48]  like I said,
[3427.50 --> 3428.46]  we can have different,
[3428.46 --> 3429.90]  different matchmaking,
[3429.90 --> 3430.78]  uh,
[3430.86 --> 3432.50]  tranches or whatever,
[3432.58 --> 3434.44]  according to connection quality.
[3434.94 --> 3435.30]  And,
[3435.42 --> 3435.98]  you know,
[3435.98 --> 3436.64]  if you have a,
[3436.66 --> 3438.98]  a not that good connection and you want to be good at the game,
[3438.98 --> 3440.36]  like how serious do you take this?
[3440.36 --> 3444.80]  Do you take it seriously enough to make sure that your Comcast connection isn't terrible or whatever?
[3444.96 --> 3445.70]  Or don't you,
[3445.82 --> 3446.28]  if you don't,
[3446.34 --> 3446.84]  that's fine,
[3446.84 --> 3448.98]  but you just can't play in the top thing.
[3448.98 --> 3449.22]  Right.
[3449.36 --> 3449.66]  And,
[3449.72 --> 3451.76]  and I would prefer that as opposed to like,
[3452.10 --> 3458.58]  just pretending like you're having a fair and reasonable match when you can shoot somebody half a second ago.
[3458.58 --> 3459.12]  Like that,
[3459.44 --> 3461.06]  that doesn't make sense,
[3461.28 --> 3461.74]  you know?
[3461.82 --> 3462.06]  Totally.
[3462.90 --> 3463.22]  Interesting.
[3463.32 --> 3463.78]  So when,
[3463.92 --> 3466.46]  I think getting to why,
[3466.80 --> 3468.24]  like why games,
[3469.24 --> 3470.22]  because there are,
[3470.34 --> 3471.46]  there is so much,
[3471.52 --> 3471.70]  I mean,
[3471.76 --> 3472.98]  there is such a,
[3472.98 --> 3473.82]  a wide,
[3474.00 --> 3474.36]  I think,
[3474.54 --> 3474.66]  well,
[3474.68 --> 3474.84]  there's,
[3474.88 --> 3476.02]  there are a lot of different games out there,
[3476.04 --> 3476.60]  but I feel that,
[3476.72 --> 3482.24]  that the ones that are popular with the broadest possible folks are not necessarily the ones where the industry focuses.
[3482.42 --> 3484.12]  Is that a fair assessment?
[3484.12 --> 3484.52]  I mean,
[3484.54 --> 3488.44]  it feels like that the industry focuses on a narrow tranche,
[3488.54 --> 3489.88]  maybe for economic reasons,
[3489.98 --> 3490.14]  maybe.
[3491.14 --> 3491.38]  I mean,
[3491.42 --> 3493.04]  God knows my kids have never paid for a game.
[3493.70 --> 3493.96]  You know,
[3494.06 --> 3497.10]  there's almost not really one video game industry now.
[3497.22 --> 3497.44]  Right.
[3497.56 --> 3497.76]  Interesting.
[3498.08 --> 3499.88]  There's the traditional one,
[3499.94 --> 3501.14]  which is the one that I live in.
[3501.30 --> 3501.54]  Right.
[3501.58 --> 3503.16]  And all this stuff I was talking about,
[3503.16 --> 3505.22]  about physics and whatever is all from that one.
[3505.24 --> 3505.46]  Right.
[3505.78 --> 3507.80]  And then there's like the iOS game industry.
[3508.02 --> 3508.26]  Right.
[3508.70 --> 3510.42]  Which is like,
[3510.48 --> 3513.16]  hopefully your kids are not playing the most exploitative games,
[3513.16 --> 3515.54]  but like a lot of these are like,
[3515.58 --> 3521.88]  I think of them as just like pretending to be games in order to have a microtransaction button or something.
[3521.92 --> 3522.14]  Right.
[3522.38 --> 3523.46]  Or to show ads.
[3524.18 --> 3524.38]  And,
[3524.44 --> 3526.78]  and those are very different things because they're all about,
[3526.82 --> 3527.18]  you know,
[3527.24 --> 3529.56]  exploiting people's psychology in,
[3529.88 --> 3530.04]  you know,
[3530.06 --> 3531.52]  I would say unethical ways.
[3531.66 --> 3531.80]  Yeah.
[3531.88 --> 3532.12]  Interesting.
[3532.52 --> 3532.62]  Yeah.
[3532.62 --> 3532.96]  And,
[3533.06 --> 3538.10]  and really they're not usually very interesting as games because they're just kind of,
[3538.10 --> 3538.96]  you know,
[3538.96 --> 3544.88]  they're only trying to be a game in as much as is necessary to get people to spend time in front of it.
[3545.02 --> 3545.24]  Yeah.
[3545.32 --> 3547.94]  And to engage the worst compulsions that they have.
[3547.98 --> 3548.40]  And so I,
[3548.50 --> 3550.86]  I actually have very little respect for that whole industry.
[3550.86 --> 3551.14]  Now,
[3551.18 --> 3553.48]  I don't know if this includes the kind of games you're talking about.
[3553.48 --> 3553.54]  Yeah.
[3553.54 --> 3553.72]  I know.
[3553.92 --> 3555.52]  Are you talking about like the,
[3555.52 --> 3558.04]  the modern iterations of the classic SimCity?
[3558.36 --> 3558.58]  Yeah.
[3558.68 --> 3558.86]  Yeah.
[3558.86 --> 3559.46]  Like Farmville.
[3559.58 --> 3559.86]  Yeah.
[3560.02 --> 3561.36]  Like SimCity was great.
[3561.38 --> 3561.82]  And it was,
[3561.98 --> 3563.26]  I think productive and healthy.
[3563.26 --> 3563.56]  And,
[3563.56 --> 3564.92]  but some of the newer,
[3565.48 --> 3568.88]  maybe dumbed down versions of it do sit like people sit in front of a screen,
[3568.96 --> 3569.76]  just clicking all day.
[3569.90 --> 3570.14]  Yeah.
[3570.16 --> 3570.42]  I mean,
[3570.42 --> 3571.10]  it's a weird thing,
[3571.12 --> 3571.28]  right?
[3571.30 --> 3576.76]  So SimCity and Farmville from a 30,000 foot view don't look that different.
[3576.76 --> 3577.20]  It's like,
[3577.20 --> 3580.78]  you're kind of controlling this spatially laid out structure and building it up.
[3580.78 --> 3581.18]  Right.
[3581.54 --> 3588.36]  But like SimCity is a creative activity that involves thoughtfulness and problem solving and skill.
[3588.48 --> 3592.76]  And Farmville is just about getting you to sit in front of the screen for as long as possible.
[3592.76 --> 3593.12]  Right.
[3593.74 --> 3593.88]  They're,
[3593.88 --> 3595.62]  they're two different things at a,
[3595.72 --> 3596.80]  at a basic level.
[3596.96 --> 3598.66]  And I don't like that.
[3598.66 --> 3598.86]  And,
[3598.92 --> 3599.22]  and again,
[3599.22 --> 3601.16]  this makes people in my industry mad,
[3601.30 --> 3601.80]  you know,
[3601.80 --> 3602.28]  when I just,
[3602.62 --> 3603.94]  when I just say it that bluntly,
[3603.94 --> 3604.52]  because it's like,
[3604.56 --> 3604.78]  look,
[3605.18 --> 3607.26]  I mean,
[3607.26 --> 3608.68]  I say it different ways at different times,
[3608.68 --> 3608.92]  but,
[3609.04 --> 3609.64]  but like,
[3610.32 --> 3612.38]  if you don't respect the player,
[3612.44 --> 3613.88]  if you're not trying to actually give them something,
[3613.88 --> 3620.26]  if you're purely entering this from a perspective of trying to take something from people and give them as little as possible.
[3620.26 --> 3620.68]  I mean,
[3621.30 --> 3622.02]  on the one sense,
[3622.02 --> 3623.26]  that's the optimization of,
[3623.26 --> 3624.04]  of capitalism,
[3624.04 --> 3625.40]  but in the other sense,
[3625.42 --> 3627.46]  that's very socially negative.
[3627.46 --> 3629.28]  And we recognize that as a society.
[3629.28 --> 3629.56]  Right.
[3629.56 --> 3630.32]  And in fact,
[3630.70 --> 3631.76]  in other industries,
[3631.76 --> 3632.76]  we,
[3633.00 --> 3634.22]  we ban things,
[3634.22 --> 3634.84]  uh,
[3634.84 --> 3637.34]  sometimes with quite harsh legal penalties when,
[3637.76 --> 3639.60]  when they are seen as socially negative enough.
[3639.60 --> 3639.86]  Right.
[3639.96 --> 3640.40]  And so,
[3640.80 --> 3641.14]  you know,
[3641.14 --> 3641.48]  I'm not,
[3641.56 --> 3643.80]  I'm not calling for banning those games right here,
[3643.80 --> 3644.26]  but like,
[3644.26 --> 3645.48]  I certainly don't,
[3645.48 --> 3647.76]  I don't respect the people who work on them.
[3647.88 --> 3648.00]  Right.
[3648.00 --> 3648.52]  Put it that way.
[3648.60 --> 3650.30]  That that's how I feel about it.
[3650.36 --> 3651.54]  I also feel that,
[3651.64 --> 3654.72]  has their time come and gone to a certain degree?
[3654.80 --> 3657.72]  I feel like that there was a kind of a Farmville moment.
[3657.72 --> 3658.68]  I mean,
[3658.74 --> 3659.16]  or period.
[3659.34 --> 3659.94]  It feels like that,
[3660.00 --> 3660.58]  that,
[3660.58 --> 3664.78]  that people are more aware of the,
[3664.78 --> 3665.94]  the kind of the exploited nature.
[3666.28 --> 3666.84]  I think they're,
[3666.92 --> 3667.30]  they're just,
[3667.36 --> 3668.86]  it feels like they're just prevalent.
[3669.06 --> 3670.62]  They're just different iterations of them,
[3670.68 --> 3674.54]  whether they are like a particular media star that has their own game now,
[3674.54 --> 3677.80]  where you can go through a house and you can buy things.
[3677.80 --> 3680.60]  If you build up enough points or pay for enough points and.
[3681.16 --> 3681.40]  Yeah.
[3681.46 --> 3683.74]  Like kind of like with.com booms and busts,
[3683.74 --> 3683.90]  right.
[3683.92 --> 3685.22]  Or technology booms and busts.
[3685.24 --> 3685.36]  Right.
[3686.00 --> 3687.26]  There's been several waves of this.
[3687.30 --> 3689.44]  So there was like casual games on the PC.
[3689.66 --> 3689.98]  Right.
[3690.00 --> 3691.20]  And then Facebook happened.
[3691.24 --> 3694.06]  And then somehow there was like all these games on Facebook.
[3694.20 --> 3694.56]  Right.
[3694.56 --> 3696.26]  Which is where Farmville came from.
[3696.26 --> 3696.36]  Right.
[3696.66 --> 3697.24]  And then,
[3697.24 --> 3697.70]  and then,
[3697.96 --> 3698.28]  you know,
[3698.34 --> 3699.64]  the smartphones happened.
[3699.86 --> 3702.64]  And so then you had the first wave of this stuff on the smartphones.
[3702.82 --> 3702.88]  And,
[3703.22 --> 3706.28]  and maybe now we're in the second or even third wave of like,
[3706.58 --> 3707.60]  you know,
[3707.60 --> 3710.80]  a set sets of games that are all sort of doing the same thing.
[3710.80 --> 3713.70]  That's like different from what prior generations of them did.
[3714.04 --> 3714.88]  So they do,
[3715.04 --> 3716.48]  they do come and go like waves,
[3716.50 --> 3718.30]  but like new waves keep showing up.
[3718.64 --> 3718.84]  Right.
[3719.52 --> 3720.90]  The ocean doesn't run out of waves.
[3721.38 --> 3721.76]  Right.
[3722.68 --> 3723.20]  Do you,
[3723.20 --> 3724.88]  do you have a favorite game that you've played?
[3724.88 --> 3729.64]  Like a game that kind of helped inform or drive your career in the game space?
[3729.84 --> 3729.88]  I,
[3730.08 --> 3732.06]  there are a number of them and they're all,
[3732.28 --> 3733.44]  it's an eclectic group.
[3733.56 --> 3733.70]  So,
[3734.00 --> 3736.28]  so when I was a kid on my Commodore 64,
[3736.28 --> 3737.22]  I liked the,
[3737.22 --> 3738.06]  the text adventures,
[3738.26 --> 3739.76]  like the infocom text adventures.
[3739.76 --> 3743.10]  And my favorite one was a game called Trinity by Brian Moriarty,
[3743.24 --> 3746.40]  which was probably the most like literature,
[3746.40 --> 3746.98]  I would say,
[3747.10 --> 3748.90]  or the most that hit me in the right spot.
[3749.02 --> 3758.16]  It was sort of a science fiction premise where like world war three happens and you sort of manage to escape in this weird extra dimensional way.
[3758.16 --> 3767.82]  And then you're trying to prevent it from happening by going to all these historic times when like moments in the development of the atomic bomb were happening.
[3767.82 --> 3768.02]  Oh,
[3768.02 --> 3768.32]  interesting.
[3768.70 --> 3768.86]  Right.
[3768.96 --> 3769.46]  And so the,
[3769.46 --> 3770.12]  the end game,
[3770.14 --> 3771.08]  this is a little bit of a spoiler,
[3771.26 --> 3772.36]  but the end game happens.
[3772.52 --> 3773.54]  This was an infocom game?
[3773.66 --> 3773.92]  Yes.
[3773.98 --> 3774.14]  Oh,
[3774.16 --> 3774.46]  nice.
[3774.46 --> 3777.78]  The end game happens like at the Trinity test site,
[3778.34 --> 3778.62]  you know,
[3778.64 --> 3780.92]  it's like historically recreated and stuff.
[3781.42 --> 3781.44]  So,
[3781.44 --> 3781.84]  um,
[3782.96 --> 3783.22]  yeah,
[3783.34 --> 3783.44]  you,
[3783.52 --> 3783.64]  the,
[3783.64 --> 3785.36]  the infocom games are available.
[3785.56 --> 3785.66]  I mean,
[3785.66 --> 3785.88]  I know,
[3785.92 --> 3787.18]  like I'm going to find it after this.
[3787.28 --> 3787.60]  I was like,
[3787.60 --> 3788.50]  I made a mental note.
[3788.50 --> 3789.18]  I'm like going to go.
[3789.40 --> 3790.10]  That sounds fun.
[3790.26 --> 3790.40]  Yeah.
[3790.42 --> 3791.08]  There's these sets.
[3791.20 --> 3793.06]  I think they're still called the lost treasures of infocom.
[3793.62 --> 3799.52]  I think you could buy it off Amazon or something and they'll send you a box like with all the maps and like cool.
[3799.52 --> 3801.76]  Like those games always had little physical objects.
[3801.94 --> 3802.04]  Yeah.
[3802.14 --> 3803.22]  The ephemera were so great.
[3803.36 --> 3805.24]  I think you also could get it on iOS.
[3805.54 --> 3807.52]  I wouldn't recommend that because typing on a,
[3807.52 --> 3809.46]  on a touchscreen is terrible.
[3809.60 --> 3809.86]  But,
[3809.92 --> 3810.16]  um,
[3810.16 --> 3814.20]  I think in those cases they have like screenshots of it or I don't know of the,
[3814.26 --> 3814.92]  of the little bobbles.
[3815.82 --> 3816.22]  Anyway,
[3816.22 --> 3816.60]  so that,
[3816.68 --> 3818.48]  that is very different from what I do today,
[3818.48 --> 3821.92]  but it affected me in a relatively deep way in terms of the way that I think about games.
[3821.98 --> 3825.14]  Like sometimes the way a creator does things like you,
[3825.34 --> 3828.62]  you feel that and you keep that as opposed to the surface.
[3829.52 --> 3831.40]  Like manifestations of whatever it is,
[3831.46 --> 3832.26]  the thing that they made.
[3832.54 --> 3832.96]  And did you,
[3833.04 --> 3833.46]  cause you know,
[3833.50 --> 3839.06]  I was much older when I realized how they actually implemented that stuff in terms of like they had their own virtual machine.
[3839.26 --> 3840.90]  Infocom was a super interesting company.
[3841.04 --> 3841.80]  It was a little wacky.
[3841.94 --> 3842.14]  Yeah.
[3842.62 --> 3843.02]  Um,
[3844.28 --> 3844.86]  it's weird.
[3844.86 --> 3846.48]  Like I think of them as such a major,
[3846.60 --> 3848.74]  major part of my childhood and stuff,
[3848.86 --> 3851.26]  but that company wasn't even around for very long.
[3851.34 --> 3852.04]  It was like,
[3852.64 --> 3854.14]  I want to say like four years.
[3854.26 --> 3855.30]  It might not have even been that long.
[3855.32 --> 3855.82]  Oh my God.
[3855.90 --> 3856.16]  That was,
[3856.46 --> 3856.62]  yeah,
[3856.64 --> 3857.80]  it just felt like a lot longer.
[3858.02 --> 3859.18]  Things happened fast back then.
[3859.18 --> 3859.46]  Yeah.
[3859.52 --> 3859.74]  It got,
[3859.82 --> 3860.96]  it felt so seminal.
[3861.12 --> 3861.56]  I don't know.
[3862.34 --> 3863.90]  Maybe that four years is incorrect.
[3864.06 --> 3864.22]  Don't,
[3864.26 --> 3864.40]  you know,
[3864.44 --> 3865.32]  fact check me later,
[3865.58 --> 3867.14]  but yeah.
[3867.24 --> 3867.50]  Um,
[3867.50 --> 3868.36]  in college,
[3868.36 --> 3868.82]  uh,
[3868.82 --> 3871.12]  when I should have been studying computer science,
[3871.12 --> 3871.52]  uh,
[3871.52 --> 3873.00]  I played a number of video games,
[3873.00 --> 3874.30]  I played some muds,
[3874.30 --> 3876.46]  which were the multiplayer text adventures back then.
[3876.46 --> 3876.78]  And,
[3876.90 --> 3877.10]  uh,
[3877.10 --> 3878.00]  but my favorite game,
[3878.00 --> 3878.74]  uh,
[3878.74 --> 3879.84]  was a game called net track,
[3879.88 --> 3881.34]  which was actually made by students there,
[3881.34 --> 3882.46]  which was a client server.
[3882.46 --> 3886.98]  I would describe it as like playing football with star Trek ships.
[3887.46 --> 3887.86]  Like,
[3887.94 --> 3894.42]  so you had like different classes of ships and you were trying to fly around and it like updated very blinkily at 10 frames per second on,
[3894.42 --> 3896.02]  on sun 360 workstations.
[3896.02 --> 3896.58]  There you go.
[3896.58 --> 3897.22]  The main things.
[3897.36 --> 3897.56]  Yeah.
[3898.24 --> 3898.68]  Or,
[3898.68 --> 3900.22]  or Apollo workstations.
[3900.42 --> 3900.52]  Right.
[3900.52 --> 3901.42]  I don't know if you know those.
[3901.46 --> 3901.96]  I do know,
[3902.02 --> 3903.84]  definitely know Apollo because the,
[3903.84 --> 3904.30]  uh,
[3904.30 --> 3904.70]  no,
[3904.80 --> 3904.96]  the,
[3905.02 --> 3909.36]  the Apollo lab had just been replaced by the sun lab when I showed up at university.
[3909.58 --> 3910.42]  So yeah,
[3910.42 --> 3912.12]  they had just gotten rid of the Apollos,
[3912.22 --> 3912.36]  which,
[3912.48 --> 3912.98]  uh,
[3912.98 --> 3913.42]  yeah.
[3914.86 --> 3918.28]  And so that's your first real exposure to networked games too,
[3918.28 --> 3919.62]  because we did not have,
[3919.70 --> 3920.90]  when you and I were growing up,
[3920.92 --> 3921.10]  I mean,
[3921.10 --> 3923.50]  the BBSs were not on a 2400 bod modem.
[3923.60 --> 3924.38]  It was not,
[3924.48 --> 3925.26]  I don't know.
[3925.26 --> 3926.78]  I didn't have plenty kind of networked game.
[3926.78 --> 3929.24]  There was weird stuff that was a little bit game ish,
[3929.30 --> 3930.52]  but it was very asynchronous.
[3930.52 --> 3933.28]  Like I'll do a move and then log out.
[3933.36 --> 3933.46]  Right.
[3933.46 --> 3935.00]  And you'll do a move tomorrow.
[3935.14 --> 3935.28]  Right.
[3935.34 --> 3935.74]  It's like chess.
[3935.92 --> 3937.56]  And I never really played those.
[3937.66 --> 3938.42]  They weren't very engaging.
[3939.06 --> 3941.46]  So you discover networked games at school.
[3941.76 --> 3941.94]  Yeah.
[3942.52 --> 3942.94]  And then,
[3943.00 --> 3943.20]  uh,
[3943.20 --> 3944.52]  my first company after school,
[3944.66 --> 3944.92]  I mean,
[3944.94 --> 3945.10]  I,
[3945.10 --> 3945.98]  I worked a real,
[3946.16 --> 3946.44]  okay.
[3946.46 --> 3948.32]  So after school,
[3948.32 --> 3951.62]  I did like a really boring enterprise software company for six months.
[3951.96 --> 3952.28]  Um,
[3952.28 --> 3954.40]  no offense to the people I know from that time,
[3954.40 --> 3954.80]  but like,
[3954.80 --> 3955.92]  it wasn't a thing.
[3956.06 --> 3956.80]  And then I,
[3956.80 --> 3957.68]  I went to,
[3957.82 --> 3958.10]  uh,
[3958.68 --> 3960.20]  I got a contract at SGI,
[3960.48 --> 3961.82]  which was still a thing back then.
[3961.92 --> 3962.18]  You bet.
[3962.18 --> 3963.04]  And I ported,
[3963.04 --> 3963.40]  uh,
[3963.40 --> 3967.50]  this relatively famous game doom to like this set top box system that they had.
[3967.72 --> 3967.76]  Right.
[3967.76 --> 3969.62]  And that was my first professional.
[3969.82 --> 3971.22]  Is this for the Orlando thing?
[3971.30 --> 3971.62]  Yes.
[3971.90 --> 3972.26]  Wow.
[3972.82 --> 3973.36]  There we go.
[3973.48 --> 3976.36]  That's that set top box is amazing.
[3976.36 --> 3978.36]  I don't know if I would say amazing.
[3978.68 --> 3979.30]  It's amazing.
[3979.68 --> 3980.54]  It's amazing.
[3981.24 --> 3981.60]  Oh,
[3981.66 --> 3982.42]  it's amazing.
[3982.74 --> 3984.10]  How do you know about this?
[3984.16 --> 3984.28]  Well,
[3984.32 --> 3987.86]  I felt like this was something that was well known at the time.
[3988.22 --> 3989.46]  Cause it was hardly deployed.
[3989.58 --> 3992.16]  It was deployed a little bit in Florida and a little bit in Japan,
[3992.16 --> 3993.10]  as far as I know.
[3993.16 --> 3994.18]  And if I recall,
[3994.26 --> 3994.52]  it was,
[3994.62 --> 4000.40]  it was classic SGI in that it was technically very interesting at a price point.
[4000.40 --> 4001.50]  That was insane.
[4001.50 --> 4002.24]  Was it the,
[4002.50 --> 4003.38]  I don't remember.
[4003.52 --> 4006.20]  I think that the box is going to be like $10,000 a box.
[4006.56 --> 4007.28]  And it's like,
[4007.44 --> 4007.66]  well,
[4008.18 --> 4009.56]  like no one's going to buy those.
[4009.68 --> 4009.98]  I mean,
[4010.02 --> 4010.86]  that's the,
[4011.20 --> 4012.08]  cause they actually deployed them.
[4012.08 --> 4013.18]  It wasn't Orlando,
[4013.48 --> 4013.62]  right?
[4013.68 --> 4014.00]  That they,
[4014.20 --> 4014.84]  I believe so.
[4014.92 --> 4015.06]  Yeah.
[4015.08 --> 4015.20]  No,
[4015.22 --> 4016.34]  I think I felt like it was,
[4016.58 --> 4022.28]  it was a famous folly by the time I arrived at Silicon Valley in 1996.
[4022.70 --> 4022.94]  Well,
[4023.02 --> 4023.28]  you know,
[4023.32 --> 4023.70]  and,
[4023.70 --> 4025.60]  and so toward the end of this project,
[4025.60 --> 4026.26]  uh,
[4026.26 --> 4028.86]  like one or two months before my contract was over,
[4028.86 --> 4032.80]  all the relatively senior people all left to go to Netscape.
[4032.80 --> 4035.16]  Cause Netscape was like poaching from everywhere.
[4035.38 --> 4036.52]  And so that really put,
[4036.94 --> 4037.28]  it was like,
[4037.34 --> 4037.80]  Oh my God,
[4037.82 --> 4040.70]  we were having a hard time on this project and now everybody just left.
[4040.88 --> 4040.98]  Yeah.
[4040.98 --> 4041.18]  Yeah.
[4041.48 --> 4041.72]  Um,
[4041.74 --> 4041.96]  but,
[4042.02 --> 4044.56]  but so same problem seemed to keep coming up.
[4044.56 --> 4044.74]  Right.
[4044.76 --> 4045.52]  So like doom,
[4045.52 --> 4046.00]  uh,
[4046.00 --> 4046.94]  it was made to run on,
[4047.00 --> 4047.64]  on PCs,
[4047.84 --> 4048.04]  right.
[4048.04 --> 4051.66]  With local disc and these set top boxes didn't have local disc.
[4051.74 --> 4055.14]  They talked over ethernet to a central server to get files.
[4055.26 --> 4055.64]  Right.
[4056.20 --> 4059.46]  And that's fine if you want to read big files,
[4059.46 --> 4060.38]  but like doom,
[4060.88 --> 4061.64]  you know,
[4061.64 --> 4061.98]  it's got,
[4062.06 --> 4064.68]  it's got a thing called it,
[4064.74 --> 4066.04]  it was called a wad file for doom,
[4066.12 --> 4068.64]  but it's basically like a zip file or a package where you put,
[4068.82 --> 4070.96]  you put a bunch of little pieces of data into,
[4070.98 --> 4071.54]  one file.
[4071.62 --> 4072.18]  And it would,
[4072.40 --> 4073.10]  for a given level,
[4073.10 --> 4074.46]  it would look up an index of like,
[4074.50 --> 4074.68]  okay,
[4074.68 --> 4075.66]  which graphics do I need?
[4075.66 --> 4076.52]  And which sounds do I need?
[4076.54 --> 4076.82]  And it would,
[4077.04 --> 4079.04]  it would seek back and forth around this file.
[4079.18 --> 4081.92]  And of course the API for this,
[4082.04 --> 4083.46]  for this set top box system,
[4083.46 --> 4086.32]  like didn't have an efficient way to do that.
[4086.32 --> 4087.64]  It was like,
[4087.64 --> 4089.14]  if you did a lot of small reads,
[4089.52 --> 4092.42]  each one was a round trip to the server and back.
[4092.60 --> 4092.86]  And like,
[4092.92 --> 4093.18]  who knows?
[4093.18 --> 4094.90]  So I actually shipped,
[4095.52 --> 4095.76]  I mean,
[4095.80 --> 4097.00]  to the extent that this thing shipped,
[4097.54 --> 4102.00]  I wrote a server that like,
[4102.58 --> 4102.88]  you know,
[4102.96 --> 4103.24]  you would,
[4103.28 --> 4106.36]  you would like coalesce all your reads and send it to that thing.
[4106.36 --> 4109.84]  And it would like do all the reads and package them and send it back to you,
[4109.84 --> 4110.78]  which like,
[4110.84 --> 4111.58]  I'm really,
[4112.08 --> 4112.74]  I mean,
[4112.78 --> 4113.62]  my ideas of,
[4113.68 --> 4119.52]  of what was okay to ship in terms of software quality back then are very different from what they are today.
[4119.52 --> 4119.84]  And just,
[4119.94 --> 4120.14]  you know,
[4120.14 --> 4121.80]  my level of experience is very different and stuff.
[4121.84 --> 4124.92]  So I'm kind of scared of whatever it is that I wrote to do that.
[4125.06 --> 4125.26]  Right.
[4125.40 --> 4126.34]  But I mean,
[4126.34 --> 4127.12]  that was officially,
[4127.62 --> 4128.00]  it was a,
[4128.00 --> 4131.82]  it was a really weird thing because at first I was talking to other people in the group and I was like,
[4131.82 --> 4131.98]  look,
[4132.06 --> 4132.98]  we need to do that.
[4133.02 --> 4133.70]  It's just too slow.
[4133.70 --> 4136.34]  There's nothing I can do on the client side to make this faster.
[4136.80 --> 4136.92]  Right.
[4137.08 --> 4138.56]  With the API that you've given me.
[4138.60 --> 4139.06]  And they were like,
[4139.12 --> 4139.74]  it was staunch.
[4139.86 --> 4140.08]  No.
[4140.24 --> 4141.16]  And then eventually it was like,
[4141.20 --> 4141.32]  oh,
[4141.34 --> 4141.60]  fine.
[4142.48 --> 4143.40]  Give us your server.
[4143.50 --> 4144.14]  We'll install it.
[4144.20 --> 4144.60]  So like,
[4144.68 --> 4144.86]  yeah,
[4144.96 --> 4145.82]  I don't know.
[4145.94 --> 4146.42]  It was weird.
[4146.42 --> 4149.46]  And what was the graphics acceleration on hardware on that?
[4149.52 --> 4151.78]  Because I do feel that the,
[4152.16 --> 4152.48]  um,
[4152.76 --> 4157.80]  you can trace the NVIDIA origin story potentially through this project.
[4158.48 --> 4160.98]  So the NVIDIA folks all came from SGI,
[4161.10 --> 4161.20]  right?
[4161.22 --> 4161.62]  It was all the,
[4161.62 --> 4162.94]  the Odyssey folks at,
[4162.98 --> 4165.38]  at SGI that quit.
[4165.90 --> 4165.94]  Yeah.
[4165.94 --> 4167.22]  I'm not sure about that.
[4167.52 --> 4167.88]  Uh,
[4168.86 --> 4169.78]  it may have had a,
[4170.04 --> 4173.10]  I assume it had a graphics accelerator in it because it was SGI.
[4173.10 --> 4173.24]  I,
[4173.24 --> 4174.46]  I remember it could do,
[4174.92 --> 4176.90]  it could do like alpha blending and stuff.
[4176.90 --> 4177.84]  So there was definitely,
[4178.20 --> 4182.22]  there was definitely a thing where there was something at least doing fast
[4182.22 --> 4183.32]  compositing and,
[4183.40 --> 4184.02]  and probably,
[4184.34 --> 4185.88]  probably some other graphics pipeline stuff.
[4186.06 --> 4186.20]  Um,
[4186.52 --> 4189.72]  the thing is my port of doom didn't use any of that stuff because,
[4189.72 --> 4193.50]  because doom was made for the systems that do not have that.
[4193.50 --> 4193.70]  Yeah.
[4193.78 --> 4193.90]  Yeah.
[4194.08 --> 4194.98]  Pixel at a time.
[4195.08 --> 4195.30]  Right.
[4195.50 --> 4195.78]  Yeah.
[4196.02 --> 4196.84]  And so,
[4196.94 --> 4197.94]  you know,
[4197.94 --> 4199.16]  I was just making that work.
[4199.20 --> 4199.38]  Right.
[4199.48 --> 4199.66]  Right.
[4199.66 --> 4199.74]  Right.
[4200.44 --> 4200.76]  You know,
[4200.80 --> 4201.44]  it was just like,
[4201.46 --> 4201.66]  you know,
[4201.66 --> 4202.10]  fill out,
[4202.46 --> 4205.42]  fill out the image and then call the thing that,
[4205.42 --> 4207.06]  that presents that image.
[4207.06 --> 4207.94]  So it's not,
[4208.00 --> 4208.20]  not,
[4208.30 --> 4210.00]  not actually particularly low level.
[4210.18 --> 4210.46]  Right.
[4211.06 --> 4211.40]  Interesting.
[4211.56 --> 4211.66]  So,
[4211.72 --> 4212.28]  and actually,
[4212.36 --> 4212.54]  you know,
[4212.56 --> 4214.20]  I ported doom to Kunix,
[4214.26 --> 4217.10]  which was a real time operating system about the same time.
[4217.14 --> 4217.34]  Okay.
[4217.40 --> 4217.54]  So,
[4217.64 --> 4218.96]  you know what I'm talking about?
[4218.98 --> 4219.00]  Oh,
[4219.00 --> 4219.22]  definitely.
[4219.30 --> 4219.44]  Yeah.
[4219.48 --> 4219.62]  No,
[4219.64 --> 4220.28]  it was the,
[4220.36 --> 4220.48]  I,
[4220.58 --> 4222.52]  the WOD file definitely brings back memories.
[4222.70 --> 4222.82]  Yeah.
[4222.82 --> 4224.50]  It wasn't that hard of a thing to port.
[4224.52 --> 4225.46]  It was not actually.
[4225.58 --> 4225.68]  No,
[4225.74 --> 4226.38]  it was actually pretty,
[4226.64 --> 4227.18]  which was great.
[4227.26 --> 4227.90]  It was pretty cool.
[4228.58 --> 4228.88]  Yeah.
[4229.46 --> 4229.84]  And I,
[4229.96 --> 4230.10]  you know,
[4230.12 --> 4231.58]  I was running with the 286 is actually quite a bit.
[4231.66 --> 4232.58]  It was actually Wolfenstein.
[4232.68 --> 4233.02]  That was like,
[4233.06 --> 4235.14]  that was Wolfenstein was the one that was a,
[4235.26 --> 4237.02]  and I'm sure you had the same again,
[4237.02 --> 4238.42]  because we're roughly the same vintage.
[4238.80 --> 4239.26]  I mean,
[4239.26 --> 4242.12]  that was just a eye popping to have.
[4242.18 --> 4242.52]  Oh yeah.
[4242.88 --> 4243.22]  I mean,
[4243.40 --> 4244.58]  all of a sudden,
[4245.06 --> 4245.26]  you,
[4245.32 --> 4245.44]  I mean,
[4245.44 --> 4246.38]  you were running on a,
[4246.44 --> 4246.62]  you know,
[4246.64 --> 4249.12]  a 286 or a 3d6 SX or whatever it was.
[4249.12 --> 4252.40]  And all of a sudden you had what felt like a 3d game.
[4253.24 --> 4254.42]  It's mostly 3d.
[4254.42 --> 4254.98]  Mostly 3d,
[4254.98 --> 4255.20]  right?
[4255.20 --> 4255.44]  Kind of.
[4255.70 --> 4256.04]  I mean,
[4256.10 --> 4257.12]  it came in steps,
[4257.18 --> 4257.32]  right?
[4257.38 --> 4258.14]  So Wolfenstein,
[4258.40 --> 4259.22]  you know,
[4259.22 --> 4259.74]  is doing this,
[4259.86 --> 4261.12]  what we call 2.5d.
[4261.24 --> 4261.40]  Right.
[4261.40 --> 4261.48]  Right.
[4261.58 --> 4265.86]  There's essentially a 2d map of the world and then walls have heights or whatever,
[4265.86 --> 4266.90]  and you sort of fake it.
[4266.98 --> 4267.30]  Right.
[4267.40 --> 4268.56]  And in Wolfenstein,
[4268.66 --> 4270.36]  all the walls were sort of on,
[4270.44 --> 4270.62]  you know,
[4270.64 --> 4271.66]  essentially on graph paper,
[4271.72 --> 4271.88]  right?
[4271.88 --> 4273.14]  They're all orthogonal to each other.
[4273.14 --> 4273.34]  And,
[4273.42 --> 4276.62]  and that means certain things are mathematically nice.
[4276.72 --> 4278.98]  So you don't have to think that hard if you're trying to figure out how to render it.
[4279.06 --> 4279.16]  Right.
[4279.16 --> 4279.34]  Right.
[4279.34 --> 4280.14]  But even,
[4280.30 --> 4280.68]  I mean,
[4280.68 --> 4281.18]  it's weird.
[4281.68 --> 4286.92]  Like earlier games had much lower performance pseudo 3d stuff.
[4286.92 --> 4288.74]  So like if you play the Ultima games or something,
[4288.88 --> 4289.54]  I don't know if you ever saw it,
[4289.70 --> 4300.36]  you'd be like in the dungeon and you hit like forward and it sort of redraws this dungeon thing that is just some white walls with a couple squares on it or whatever.
[4300.36 --> 4300.66]  Right.
[4300.72 --> 4304.50]  And so you definitely could connect it to things that were earlier,
[4304.68 --> 4304.88]  but,
[4304.94 --> 4305.92]  but at the same time,
[4305.92 --> 4306.90]  it was sort of a,
[4306.90 --> 4309.96]  a qualitative jump in what was being done.
[4309.96 --> 4310.24]  Right.
[4310.26 --> 4313.44]  And then doom was even more doom was like not gridded.
[4313.80 --> 4314.12]  You know,
[4314.12 --> 4315.12]  it was like free form.
[4315.74 --> 4315.94]  Right.
[4316.60 --> 4318.08]  We're going to take another quick break.
[4318.14 --> 4321.16]  I want to come back and I want to talk some more doom here.
[4321.78 --> 4324.44]  Back with more Jonathan Blow on the metal.
[4324.44 --> 4330.70]  On the metal is brought to you by the oxide computer company.
[4331.02 --> 4331.38]  Well,
[4331.52 --> 4333.32]  I thought we had a bit of time to deal with this,
[4333.46 --> 4336.32]  but it sounds like the listeners are pretty restless.
[4336.58 --> 4336.72]  Oh,
[4336.84 --> 4337.58]  is this about the ads?
[4337.92 --> 4338.18]  Yes.
[4338.32 --> 4338.74]  Oh no.
[4338.88 --> 4339.68]  The inbox is full.
[4339.92 --> 4340.24]  Oh boy.
[4340.34 --> 4347.72]  They also have begun recording their own ads and sending them to us requesting mercy from the repetitive ads that we've been subjecting them to.
[4347.74 --> 4348.04]  Wait a minute.
[4348.10 --> 4351.04]  They're in such pain over the ads that they're sending us ads for oxide.
[4351.36 --> 4351.60]  Yeah.
[4351.80 --> 4352.42]  I picked one out.
[4352.62 --> 4353.06]  Have a listen.
[4353.06 --> 4354.60]  This is from listener Paul Gwaz.
[4355.10 --> 4355.84]  I'm getting really,
[4355.98 --> 4356.38]  really,
[4356.46 --> 4365.92]  really tired of listening to the same oxide.computer ads every week talking about how the oxide computer company is going to make your on-premises infrastructure faster,
[4366.28 --> 4366.86]  more efficient,
[4367.10 --> 4367.78]  more secure,
[4368.00 --> 4369.96]  and just all around less painful.
[4370.50 --> 4371.26]  So much so,
[4371.34 --> 4371.68]  in fact,
[4371.80 --> 4373.24]  that I wrote and recorded this ad.
[4373.52 --> 4377.56]  Head on over to oxide.computer to learn more and join their mailing list.
[4378.00 --> 4379.50]  I think we should just do what Paul said.
[4379.88 --> 4380.14]  Yeah.
[4380.40 --> 4381.50]  Let's just follow his instructions.
[4381.50 --> 4382.62]  Let's get back to the show.
[4383.06 --> 4385.90]  All right.
[4385.94 --> 4386.54]  We're back.
[4386.88 --> 4387.04]  So,
[4387.24 --> 4387.46]  Jonathan,
[4387.56 --> 4391.88]  you just ported Doom to SGI's doomed set-top box.
[4392.10 --> 4392.36]  Yeah.
[4392.62 --> 4393.50]  I actually,
[4393.68 --> 4396.10]  I assume it never went anywhere,
[4396.10 --> 4397.12]  but I don't actually know.
[4397.28 --> 4399.56]  I think the price point was debilitating.
[4399.74 --> 4400.20]  I think it was,
[4400.30 --> 4400.44]  again,
[4400.48 --> 4401.72]  it was viewed as a folly,
[4401.88 --> 4402.28]  I think.
[4402.54 --> 4403.10]  It just,
[4403.62 --> 4409.52]  and it was a Silicon Valley company trying to enter consumer electronics in a way that backfired.
[4409.52 --> 4410.16]  Yeah.
[4410.22 --> 4410.52]  It was kind of,
[4410.58 --> 4410.96]  I was perceived,
[4411.06 --> 4412.44]  but I do think that some of that,
[4413.22 --> 4415.98]  although SGI was kind of coming apart at the seams at that point.
[4416.48 --> 4418.60]  They had a CFO with a Coke problem,
[4418.66 --> 4419.28]  among other things.
[4419.54 --> 4419.68]  Oh,
[4419.84 --> 4420.02]  yeah.
[4420.20 --> 4420.44]  Okay.
[4420.84 --> 4421.16]  That was,
[4421.24 --> 4421.94]  it doesn't sound good.
[4422.14 --> 4422.40]  No,
[4422.46 --> 4423.02]  it was bad.
[4423.40 --> 4423.66]  SGI.
[4423.66 --> 4424.76]  Don't do that in your company.
[4424.94 --> 4425.34]  No,
[4425.66 --> 4425.84]  no,
[4425.84 --> 4426.06]  no,
[4426.20 --> 4426.44]  no,
[4426.44 --> 4427.46]  we will not be doing that.
[4427.66 --> 4428.84]  We will not be doing that.
[4428.96 --> 4429.78]  SGI had,
[4429.94 --> 4430.24]  I mean,
[4430.26 --> 4431.76]  there was a hugely innovative company,
[4431.90 --> 4433.34]  but it was nuts.
[4434.58 --> 4434.86]  Yeah.
[4434.88 --> 4436.72]  I don't know what happened because you sort of,
[4437.52 --> 4441.32]  like the world became so much about graphics and like they missed that.
[4441.66 --> 4444.76]  It's like they were in the earlier age of graphics.
[4445.04 --> 4446.50]  And then they kind of missed a transition.
[4447.16 --> 4447.52]  Yeah.
[4447.74 --> 4448.02]  Well,
[4448.08 --> 4448.28]  they,
[4448.42 --> 4450.22]  they didn't know what they wanted to be,
[4450.30 --> 4453.26]  whether they wanted to be an enterprise computing company or a graphics company.
[4453.26 --> 4453.70]  And remember,
[4453.74 --> 4454.38]  because they changed their name.
[4454.38 --> 4456.24]  They were Silicon graphics and they changed their name to SGI.
[4456.40 --> 4456.60]  Right.
[4456.64 --> 4456.80]  Right.
[4456.84 --> 4457.12]  Yes.
[4457.30 --> 4460.14]  It was one of these like corporate moves.
[4460.26 --> 4460.82]  You're just like,
[4460.92 --> 4462.14]  I have head in hands.
[4462.30 --> 4465.44]  This is like when sun changed the ticker symbol from sun W to Java.
[4465.64 --> 4466.28]  You're just like,
[4466.38 --> 4467.98]  Oh God.
[4468.36 --> 4468.76]  No.
[4469.50 --> 4469.90]  Exactly.
[4470.28 --> 4472.72]  Thank you for just embarrassing every employee.
[4472.94 --> 4473.12]  You know,
[4473.14 --> 4475.18]  every employee just has their head in their hands.
[4475.36 --> 4476.80]  Oh my God.
[4477.44 --> 4477.64]  And I,
[4477.72 --> 4479.62]  but I think that as I recall,
[4479.62 --> 4480.72]  it was a bunch of the,
[4480.72 --> 4481.20]  the,
[4481.20 --> 4483.80]  the NVIDIA folks were all X SGI.
[4483.80 --> 4484.14]  I mean,
[4484.18 --> 4486.02]  I didn't want to go check that,
[4486.16 --> 4486.36]  but,
[4486.36 --> 4486.80]  um,
[4487.44 --> 4488.74]  so what did you do after,
[4488.74 --> 4489.82]  after SGI?
[4490.82 --> 4491.02]  Uh,
[4491.02 --> 4491.26]  well,
[4491.30 --> 4492.96]  I started a company with a friend,
[4492.96 --> 4493.66]  um,
[4494.12 --> 4494.90]  here actually,
[4494.90 --> 4496.72]  our first office was in Oakland.
[4496.86 --> 4497.36]  There you go.
[4498.00 --> 4498.28]  Down,
[4498.46 --> 4498.90]  downtown.
[4499.04 --> 4499.66]  There's a small,
[4499.74 --> 4500.62]  like at 12th street.
[4500.74 --> 4501.88]  We had a little thing there.
[4501.96 --> 4503.92]  And this is in the early 2000s.
[4504.08 --> 4504.76]  Post.com.
[4504.76 --> 4504.88]  No,
[4504.90 --> 4505.26]  this was,
[4505.40 --> 4507.16]  this was 96.
[4507.94 --> 4508.12]  Oh,
[4508.18 --> 4508.34]  wow.
[4508.40 --> 4508.58]  Okay.
[4508.76 --> 4508.94]  Yeah.
[4508.94 --> 4510.12]  This was pre.com bust.
[4510.38 --> 4510.54]  And then,
[4510.54 --> 4511.24]  and then,
[4511.28 --> 4513.02]  so this company lasted till like 2000,
[4513.12 --> 4513.66]  2001.
[4513.98 --> 4514.18]  Okay.
[4514.18 --> 4517.38]  So we sort of saw the whole.com thing happening.
[4517.60 --> 4517.78]  Right.
[4517.82 --> 4518.98]  And I was just like,
[4519.70 --> 4521.16]  I'm not doing that.
[4521.16 --> 4521.42]  Right.
[4521.48 --> 4521.76]  You know,
[4521.88 --> 4522.44]  I'm doing,
[4522.62 --> 4523.26]  doing my thing.
[4523.26 --> 4524.36]  And it was really,
[4524.50 --> 4524.86]  uh,
[4525.08 --> 4525.82]  it was really difficult.
[4525.96 --> 4526.20]  So this,
[4526.32 --> 4527.40]  this turned out to be,
[4527.46 --> 4528.14]  well,
[4528.18 --> 4528.48]  first of all,
[4528.48 --> 4530.48]  we didn't really know anything about video games.
[4530.48 --> 4530.92]  Right.
[4530.96 --> 4533.52]  We had no like experience except I,
[4533.64 --> 4533.82]  you know,
[4533.82 --> 4534.70]  I'd program games.
[4534.80 --> 4535.86]  I played them and stuff,
[4535.86 --> 4537.26]  but it would have,
[4537.30 --> 4540.40]  it would have helped to have somebody who had done things in the industry before,
[4540.40 --> 4541.12]  as opposed to us,
[4541.12 --> 4541.76]  which were just like,
[4541.80 --> 4541.88]  Hey,
[4541.88 --> 4542.74]  let's start a game company.
[4542.80 --> 4543.08]  Okay.
[4543.08 --> 4544.14]  How hard could it be?
[4544.26 --> 4544.50]  Right.
[4545.24 --> 4546.16]  But also it was,
[4546.40 --> 4551.24]  I'm convinced the hardest time in history to start a video game company,
[4551.24 --> 4556.60]  like almost to the month because previously games had been 2d.
[4556.88 --> 4557.32]  Right.
[4557.74 --> 4559.00]  And now with,
[4559.22 --> 4559.44]  uh,
[4559.44 --> 4559.70]  so,
[4559.78 --> 4560.36]  so 1996,
[4560.64 --> 4562.24]  beginning of 96 was when Quake,
[4562.46 --> 4562.68]  Quake,
[4562.68 --> 4564.72]  Quake test came out.
[4565.48 --> 4567.32]  Like when we were starting our company,
[4567.44 --> 4567.64]  right.
[4567.70 --> 4567.90]  Right.
[4567.90 --> 4570.06]  Which was like basically fully running Quake,
[4570.14 --> 4571.44]  but without all the levels and stuff,
[4571.50 --> 4574.14]  they were just doing like a multiplayer beta to make sure all that worked.
[4574.96 --> 4577.42]  And so Quake was the first real,
[4577.88 --> 4581.58]  like it wasn't actually the first like fully 3d game,
[4581.64 --> 4585.40]  but it was the first that like ran at high frame rates where like actiony things
[4585.40 --> 4585.84]  happened.
[4586.38 --> 4588.96]  And that just kind of changed the whole game industry.
[4589.18 --> 4590.46]  And so everybody had to do that.
[4591.24 --> 4591.68]  Right.
[4591.68 --> 4592.24]  Right.
[4592.32 --> 4593.12]  Right.
[4593.12 --> 4593.44]  Right.
[4593.44 --> 4593.90]  Right.
[4593.90 --> 4594.40]  Right.
[4594.40 --> 4594.90]  Right.
[4594.90 --> 4595.46]  Right.
[4595.46 --> 4595.62]  Right.
[4595.62 --> 4595.86]  That's right.
[4595.86 --> 4595.98]  So first of all,
[4596.26 --> 4597.04]  like we were saying,
[4597.10 --> 4598.12]  no graphics accelerators.
[4598.12 --> 4600.54]  So you had to draw every pixel on the screen.
[4600.72 --> 4602.44]  You had to do that really fast.
[4603.08 --> 4604.28]  And it just,
[4604.64 --> 4606.98]  a significant amount of math was required,
[4607.24 --> 4607.52]  right?
[4607.66 --> 4608.16]  All this,
[4608.26 --> 4610.94]  like the whole geometry situation was not quite as,
[4610.98 --> 4612.54]  as complicated as what I said at the beginning,
[4612.60 --> 4613.26]  but it almost,
[4613.58 --> 4613.88]  you know,
[4613.96 --> 4617.84]  getting there and just computers were still kind of slow.
[4617.84 --> 4620.04]  And so you really had to sweat.
[4620.22 --> 4620.58]  So like,
[4620.62 --> 4620.88]  you know,
[4620.98 --> 4621.22]  I did,
[4621.56 --> 4623.82]  so we were working on four 86s in,
[4623.90 --> 4624.32]  in the beginning,
[4624.42 --> 4624.68]  maybe,
[4625.18 --> 4625.78]  maybe three,
[4625.86 --> 4628.06]  like we were working on four 86s and we were hoping to ship
[4628.06 --> 4629.36]  for three 86s also.
[4629.72 --> 4629.78]  Right.
[4630.74 --> 4632.66]  And so fortunately for us,
[4632.72 --> 4632.84]  I mean,
[4632.86 --> 4633.22]  you think of this,
[4633.30 --> 4635.64]  this is a 66 megahertz clock rate.
[4636.00 --> 4636.64]  I mean,
[4636.78 --> 4637.28]  on a 46.
[4637.82 --> 4638.22]  Sometimes.
[4638.40 --> 4638.52]  Right.
[4638.52 --> 4639.10]  It was that high.
[4639.50 --> 4639.86]  Exactly.
[4640.42 --> 4640.78]  Lower.
[4640.94 --> 4641.06]  I mean,
[4641.14 --> 4643.36]  you think about like the amount,
[4643.44 --> 4643.60]  I mean,
[4643.60 --> 4647.36]  that is running on like a risk five today.
[4648.38 --> 4648.78]  Yeah.
[4649.30 --> 4649.50]  Right.
[4649.60 --> 4649.86]  I mean,
[4649.86 --> 4650.90]  it's like in terms of the,
[4651.00 --> 4651.98]  what you were doing,
[4652.10 --> 4653.44]  how little the horsepower is.
[4653.48 --> 4654.66]  I don't know how to compare it,
[4654.76 --> 4655.04]  honestly,
[4655.18 --> 4655.96]  to anything today,
[4656.08 --> 4657.12]  but you know,
[4657.12 --> 4657.78]  and,
[4657.96 --> 4658.18]  but we,
[4658.32 --> 4660.84]  but also the thing that you do in games is you're trying to be
[4660.84 --> 4661.18]  ambitious.
[4661.18 --> 4663.38]  You're not trying to do the same thing that people already did.
[4663.40 --> 4664.30]  You're trying to push ahead.
[4664.30 --> 4667.14]  So we were trying to do like an open world where you could like
[4667.14 --> 4670.06]  drive your little hovering tank around all these mountains
[4670.06 --> 4670.60]  and stuff.
[4670.76 --> 4670.78]  And,
[4670.82 --> 4674.14]  and part of the secret of quake was it was like indoors and very
[4674.14 --> 4674.30]  constrained,
[4674.96 --> 4675.72]  like visibly.
[4675.72 --> 4678.96]  So you didn't spend a lot of CPU to figure out what to render.
[4679.36 --> 4679.76]  Right.
[4679.80 --> 4680.32]  So there was,
[4680.48 --> 4682.28]  there was that there was a great deal to learn,
[4682.40 --> 4682.98]  but okay.
[4682.98 --> 4687.68]  So here's the great thing about this time historically is that the
[4687.68 --> 4688.60]  guys who worked on quake,
[4688.70 --> 4690.02]  which was John Carmack,
[4690.26 --> 4694.36]  who I guess he was CTO at Oculus recently and now just quit to go do
[4694.36 --> 4695.54]  AI on his own.
[4695.76 --> 4696.98]  And Mike Abrash,
[4697.12 --> 4701.20]  who's a relatively well-regarded famous person as well,
[4701.28 --> 4705.10]  we're working really hard for a year and a half to figure out how to
[4705.10 --> 4706.98]  make this game possible.
[4706.98 --> 4707.30]  Right.
[4707.32 --> 4709.76]  Or I guess the whole development was like a year and nine months or
[4709.76 --> 4710.04]  something.
[4710.04 --> 4711.28]  Again,
[4711.44 --> 4712.10]  fact check those,
[4712.46 --> 4713.18]  but like that,
[4713.70 --> 4715.90]  they then went to these,
[4715.94 --> 4716.58]  these conferences,
[4716.82 --> 4716.98]  right.
[4717.02 --> 4717.40]  For example,
[4717.44 --> 4719.76]  the game developers conference in San Francisco and said,
[4719.86 --> 4721.72]  here's exactly how we did this.
[4721.80 --> 4724.82]  Everybody else in the industry who are ostensibly competing with,
[4724.94 --> 4727.98]  here is what we did to like get the geometry on the screen.
[4728.12 --> 4730.14]  And the most magical thing was the,
[4730.14 --> 4732.32]  the texture mapping loop that would go from pixel to pixel.
[4732.32 --> 4732.98]  And they said,
[4733.12 --> 4735.26]  here's our assembly lane.
[4735.26 --> 4737.10]  Like anybody obviously could disassemble it,
[4737.20 --> 4738.02]  but like it was,
[4738.02 --> 4741.80]  it was really weird because the inner loop that wrote each pixel,
[4742.56 --> 4746.90]  like Abrash figured out weird side effects of some of the X86 instructions
[4746.90 --> 4747.46]  that like,
[4747.50 --> 4749.72]  weren't exactly the intended purpose,
[4749.72 --> 4751.06]  but when you strung them together,
[4751.06 --> 4754.08]  you could get some work that you wanted to happen to happen.
[4754.48 --> 4754.88]  Huh.
[4754.94 --> 4756.48]  And yeah.
[4756.60 --> 4756.92]  So,
[4757.42 --> 4758.36]  so,
[4758.54 --> 4759.04]  you know,
[4759.04 --> 4761.10]  I spent a lot of time trying to do variants of that.
[4761.10 --> 4761.26]  So,
[4761.48 --> 4762.96]  so they had this six cycle thing,
[4763.04 --> 4765.08]  but of course you want to like add features and stuff.
[4765.08 --> 4766.92]  So you try to add cycles to your texture mapper,
[4767.02 --> 4767.76]  but not too many.
[4767.76 --> 4768.38]  And so,
[4768.38 --> 4769.02]  and,
[4769.10 --> 4771.60]  and because you didn't have that many addressable registers back then,
[4771.68 --> 4772.16]  you know,
[4772.16 --> 4773.98]  I'm sitting there programming an assembly and like,
[4774.02 --> 4774.24]  okay,
[4774.24 --> 4776.72]  we're going to use the base pointer as like a general register.
[4776.72 --> 4777.36]  Cause we don't,
[4777.44 --> 4777.76]  there you go,
[4777.80 --> 4778.08]  you know,
[4778.12 --> 4779.64]  and then that makes it really fun to debug.
[4779.74 --> 4779.86]  Right.
[4779.86 --> 4780.02]  Right.
[4780.06 --> 4780.36]  Exactly.
[4780.42 --> 4782.16]  The classic reuse of the frame pointer.
[4782.32 --> 4782.84]  Oh my God,
[4782.84 --> 4784.16]  that's a special place in health.
[4784.24 --> 4785.66]  People would reuse the frame pointer.
[4786.04 --> 4787.00]  But you had to,
[4787.06 --> 4787.66]  cause you couldn't,
[4787.74 --> 4790.00]  I am looking forward to the room in hell.
[4790.06 --> 4790.28]  It's like,
[4790.32 --> 4790.52]  wait a minute,
[4790.56 --> 4791.24]  what are you doing here?
[4791.30 --> 4792.30]  Then you finally realize like,
[4792.30 --> 4792.68]  wait a minute,
[4792.78 --> 4794.36]  we all reuse the frame pointer.
[4794.50 --> 4795.26]  That's why we're all,
[4795.38 --> 4795.58]  yeah,
[4795.66 --> 4796.04]  I know.
[4796.16 --> 4796.32]  No,
[4796.36 --> 4796.54]  it is.
[4796.58 --> 4797.00]  You had to,
[4797.08 --> 4797.76]  you do have to,
[4797.82 --> 4798.16]  but God,
[4798.20 --> 4799.42]  it makes a brutal little bug.
[4799.72 --> 4799.92]  Yeah.
[4800.16 --> 4800.50]  And,
[4800.50 --> 4802.68]  and so that's what I was doing for a few years and just,
[4802.78 --> 4804.54]  we didn't have business savvy.
[4804.54 --> 4806.04]  And also it was a weird time.
[4806.04 --> 4807.24]  So like the,
[4807.24 --> 4811.68]  we ended up signing our game with these companies that were going to try to be like,
[4812.16 --> 4812.36]  you know,
[4812.38 --> 4813.64]  like cable TV channels,
[4813.80 --> 4815.64]  but like for the emerging internet.
[4815.90 --> 4819.86]  And the idea was they would provide low latency connections over your modem.
[4819.86 --> 4824.20]  And so we signed with this company called total entertainment network that was based in San
[4824.20 --> 4824.50]  Francisco.
[4824.50 --> 4824.86]  And,
[4825.00 --> 4825.10]  you know,
[4825.10 --> 4830.62]  we made some money off that contract and that kept us alive at subsistence level for some amount of time.
[4831.04 --> 4834.04]  But eventually that whole market just like didn't happen.
[4834.04 --> 4837.86]  It didn't end up that people were paying subscription fees for good modem gaming.
[4838.10 --> 4838.20]  Right.
[4838.28 --> 4842.78]  Because like what happened instead is just the more open internet happened.
[4843.04 --> 4843.28]  And,
[4843.40 --> 4843.76]  you know,
[4843.80 --> 4843.96]  so,
[4844.06 --> 4846.16]  so if we had done something where it was like,
[4846.16 --> 4849.58]  we're selling our game directly over the internet,
[4849.58 --> 4851.32]  we might've actually succeeded.
[4851.32 --> 4852.46]  Even though that was crazy.
[4852.46 --> 4857.04]  Like the idea of processing a credit card on the internet in 1996 was like not really.
[4857.22 --> 4857.58]  Right.
[4857.80 --> 4858.74]  Hardly anybody did that.
[4858.76 --> 4861.68]  And I see what you're saying about it being a tough time because it's like post internet,
[4861.80 --> 4863.24]  but pre internet at the same time.
[4863.32 --> 4863.68]  Yes.
[4863.82 --> 4864.26]  It's like,
[4864.28 --> 4866.98]  everyone knows the internet is here and no one has it yet.
[4867.60 --> 4867.96]  Yeah.
[4868.18 --> 4868.32]  Right.
[4868.34 --> 4869.16]  It was all dial up.
[4869.30 --> 4870.22]  It was super slow.
[4870.46 --> 4870.98]  It was,
[4871.14 --> 4871.44]  you know,
[4871.48 --> 4872.02]  this is the,
[4872.42 --> 4872.86]  this is what,
[4872.94 --> 4874.06]  you remember boo.com?
[4874.06 --> 4874.50]  Um,
[4874.90 --> 4875.98]  they were ringing a bell,
[4876.12 --> 4877.20]  but they were a retailer.
[4877.46 --> 4877.82]  They were,
[4878.02 --> 4879.26]  they were going to be us,
[4879.26 --> 4886.62]  a streetwear retailer that had a super complicated flash retail site when everyone only had,
[4886.64 --> 4886.90]  you know,
[4886.94 --> 4888.12]  57 K at best.
[4888.58 --> 4889.54]  And it was just like,
[4889.56 --> 4891.18]  you had to wait for 15 minutes for the site to load.
[4891.24 --> 4891.64]  It's like,
[4891.66 --> 4891.86]  well,
[4892.22 --> 4892.72]  goodbye.
[4893.12 --> 4893.78]  And a retailer,
[4893.92 --> 4894.46]  same kind of thing.
[4894.46 --> 4894.70]  It's like,
[4894.70 --> 4897.14]  you're at exactly the kind of wrong time.
[4898.16 --> 4898.74]  But so,
[4898.88 --> 4899.62]  you know,
[4899.68 --> 4903.18]  I worked hard for years and it was very sad.
[4903.18 --> 4904.70]  But,
[4904.76 --> 4905.04]  um,
[4905.56 --> 4906.28]  it was really,
[4906.28 --> 4906.70]  it's,
[4906.70 --> 4908.54]  it's a large part of where I learned how to program.
[4908.54 --> 4908.82]  Right.
[4908.84 --> 4909.06]  I mean,
[4909.06 --> 4909.92]  I went to college at birth.
[4910.02 --> 4910.20]  So,
[4910.24 --> 4912.00]  so I programmed a lot at home,
[4912.10 --> 4912.56]  you know,
[4912.56 --> 4914.50]  in high school and grade school on like,
[4914.54 --> 4914.80]  you know,
[4914.80 --> 4915.40]  home computers.
[4915.72 --> 4916.96]  So I kind of got that,
[4917.00 --> 4919.82]  but then I went to computer science school and it was like,
[4919.86 --> 4920.20]  Oh,
[4920.28 --> 4922.96]  so there's like actual formalisms behind some of these things,
[4922.96 --> 4925.00]  which I think was an important thing to learn.
[4925.00 --> 4925.20]  Yeah.
[4925.26 --> 4925.50]  Right.
[4925.78 --> 4926.06]  I actually,
[4926.10 --> 4927.56]  I actually dropped out of that eventually,
[4927.56 --> 4929.28]  like not soon enough.
[4929.28 --> 4931.14]  Like I had like one semester left,
[4931.16 --> 4932.14]  which is the stupidest thing.
[4932.14 --> 4935.42]  It's like just stick around and do the last semester and get your degree.
[4935.48 --> 4936.28]  But I couldn't do it.
[4936.80 --> 4937.44]  I was not.
[4937.56 --> 4937.92]  Yeah.
[4938.30 --> 4938.90]  But anyway,
[4939.54 --> 4939.82]  you know,
[4939.84 --> 4941.14]  I'm sure they'll let you finish it up though.
[4941.18 --> 4942.56]  You could probably give the commencement address.
[4942.56 --> 4942.82]  Yeah.
[4942.86 --> 4943.34]  I really,
[4943.62 --> 4943.76]  I,
[4944.04 --> 4944.44]  yeah,
[4944.52 --> 4945.86]  I don't like school.
[4946.94 --> 4947.30]  Yeah.
[4947.42 --> 4948.70]  And so I learned certain things there.
[4948.70 --> 4948.96]  Right.
[4949.04 --> 4949.40]  But,
[4949.48 --> 4950.42]  but there's still not,
[4950.42 --> 4950.94]  uh,
[4951.38 --> 4953.62]  like what you learn in school is not that practical.
[4954.18 --> 4954.88]  Like it's,
[4955.00 --> 4955.66]  there's a mixture.
[4955.92 --> 4956.24]  There's,
[4956.30 --> 4957.04]  there's ideas.
[4957.04 --> 4960.68]  There's a lot of ideas about how you should program and how computers should work and all
[4960.68 --> 4960.90]  this.
[4960.94 --> 4961.72]  And some of them are right.
[4961.74 --> 4963.52]  And some of them are actually pretty wrong.
[4963.82 --> 4964.04]  Yeah.
[4964.12 --> 4967.18]  And you have to kind of go learn which ones are right and which ones are wrong.
[4967.34 --> 4967.78]  Yeah.
[4968.18 --> 4969.36]  And that's where I did that.
[4969.52 --> 4969.80]  It's like,
[4969.80 --> 4972.98]  you have to have a very lab intensive computer science curriculum for this,
[4973.10 --> 4974.14]  just this exact reason.
[4974.38 --> 4975.06]  Even then though,
[4975.06 --> 4975.34]  like,
[4975.40 --> 4976.22]  like that helps.
[4976.22 --> 4976.50]  Right.
[4976.50 --> 4979.74]  But a lab project in school that you would do in one semester,
[4979.74 --> 4981.12]  like that's not the same as like,
[4981.12 --> 4984.50]  I'm building a game from scratch with my bare hands for four years.
[4984.58 --> 4984.84]  Yeah.
[4985.04 --> 4985.36]  Yeah.
[4985.36 --> 4986.30]  Like that's just different.
[4986.54 --> 4986.70]  Yeah.
[4986.76 --> 4987.90]  And I,
[4987.94 --> 4988.12]  I,
[4988.24 --> 4988.48]  so,
[4988.62 --> 4990.00]  so we started a company at,
[4990.38 --> 4991.58]  at the hardest possible time,
[4991.58 --> 4993.60]  but I also feel like I'm,
[4993.70 --> 4996.54]  I'm like a programmer who was raised during wartime.
[4996.74 --> 4999.08]  And I look around today and I'm like,
[4999.08 --> 5000.80]  people can't really program today.
[5000.80 --> 5001.10]  Like,
[5001.14 --> 5001.56]  it's just,
[5001.86 --> 5005.14]  it's because they weren't forced to in a sense.
[5005.30 --> 5005.36]  Like,
[5005.44 --> 5005.76]  I mean,
[5005.76 --> 5007.82]  that's a little bit of a facetious way to say it.
[5007.82 --> 5011.68]  Like people can definitely program in the sense that they type in
[5011.68 --> 5017.16]  relatively uncareful things into a computer and then approximately the
[5017.16 --> 5018.92]  right thing happens in return.
[5019.08 --> 5019.80]  But it's like,
[5019.86 --> 5020.64]  it's not the same.
[5020.88 --> 5021.72]  I think you're right.
[5021.76 --> 5021.82]  Well,
[5021.82 --> 5022.16]  I think that,
[5022.24 --> 5022.52]  that in,
[5022.62 --> 5022.98]  in particular,
[5023.20 --> 5024.02]  that we,
[5024.36 --> 5028.82]  the era of resource constraint seemed to have ended.
[5029.16 --> 5029.60]  Well,
[5029.66 --> 5030.38]  here,
[5030.46 --> 5034.66]  here's a magical thing about games is that we still had resource
[5034.66 --> 5035.18]  constraint.
[5035.18 --> 5036.34]  We still do today.
[5036.34 --> 5036.60]  Right.
[5036.70 --> 5036.86]  Right.
[5037.10 --> 5037.46]  Because,
[5037.58 --> 5039.32]  because we're in competition with each other.
[5039.40 --> 5039.74]  Right.
[5039.78 --> 5043.90]  And because a lot of the platforms that we ship on are actually like fixed
[5043.90 --> 5044.58]  platforms.
[5044.58 --> 5045.62]  Like here's the CPU,
[5045.76 --> 5046.20]  here's the GPU,
[5046.30 --> 5046.82]  here's the memory.
[5046.98 --> 5048.30]  You know what all these things are.
[5048.38 --> 5049.80]  You know what the speed of all of them are,
[5049.86 --> 5050.16]  you know,
[5050.16 --> 5051.00]  like a game console.
[5051.14 --> 5054.76]  And the people who make the game console have an interest in you being able to
[5054.76 --> 5055.22]  program it.
[5055.22 --> 5055.50]  Well,
[5055.82 --> 5055.96]  right.
[5055.96 --> 5059.70]  And so you don't have these super thick abstracted APIs that you don't know
[5059.70 --> 5060.36]  what's going on.
[5060.40 --> 5060.74]  It's like,
[5060.78 --> 5060.98]  Oh,
[5061.10 --> 5061.72]  you actually,
[5061.94 --> 5063.72]  you actually know when you call this function,
[5063.92 --> 5068.40]  what the graphics processor is actually doing in response to that.
[5068.40 --> 5068.68]  If you,
[5068.74 --> 5070.92]  if you actually care enough to dig into that.
[5070.92 --> 5071.14]  Right.
[5071.14 --> 5075.00]  And so when I say a lot of people don't know how to program today,
[5075.04 --> 5079.06]  I kind of accept certain parts of video games from that.
[5079.12 --> 5080.70]  Now it's a big industry and there's a,
[5080.74 --> 5082.52]  there's a spectrum of what people do.
[5082.52 --> 5082.92]  But like.
[5082.92 --> 5083.84]  In terms of like the,
[5083.90 --> 5085.82]  the resource utilization is,
[5086.04 --> 5086.16]  can,
[5086.38 --> 5087.82]  has immediate commercial value.
[5087.82 --> 5091.86]  So you do understand what the metal that's underneath you a lot better.
[5092.16 --> 5092.44]  Yeah.
[5092.44 --> 5092.76]  Yeah.
[5093.26 --> 5094.00]  And again,
[5094.00 --> 5096.08]  I'm in a weird space there because,
[5096.08 --> 5096.84]  you know,
[5096.86 --> 5097.50]  my whole shtick.
[5097.60 --> 5100.58]  So there's large video game companies with hundreds or thousands of people,
[5100.58 --> 5101.10]  which is again,
[5101.10 --> 5104.98]  like that's still a pipsqueak tiny thing compared to web companies,
[5104.98 --> 5107.14]  but like a giant,
[5107.26 --> 5107.70]  massive,
[5107.92 --> 5111.46]  hugely successful video game that makes billions of dollars like red dead
[5111.46 --> 5112.60]  redemption two or something.
[5113.36 --> 5114.06]  I mean,
[5114.14 --> 5117.12]  probably I don't actually know the numbers on that game,
[5117.12 --> 5120.14]  but it would be typical for something like that to peak at a thousand
[5120.14 --> 5120.56]  people.
[5120.56 --> 5125.36]  And that's just like toward the end when a lot of people jump on to try to
[5125.36 --> 5125.96]  finish it up.
[5125.96 --> 5126.28]  Okay.
[5126.28 --> 5126.56]  But,
[5126.64 --> 5128.42]  but like probably hundreds for,
[5128.56 --> 5129.58]  for most of development,
[5129.58 --> 5129.90]  right.
[5129.90 --> 5131.68]  Which it's a lot of people,
[5131.68 --> 5132.44]  it's a lot of people,
[5132.44 --> 5135.42]  but it's also not a lot of people compared to some companies.
[5135.42 --> 5135.76]  Right.
[5135.76 --> 5136.32]  And so it's,
[5136.40 --> 5136.98]  it's weird,
[5137.08 --> 5137.36]  right.
[5137.48 --> 5137.96]  It's a,
[5138.06 --> 5142.52]  it's a lot of people to try to coordinate when you're trying to be very
[5142.52 --> 5144.58]  precise about what you're doing.
[5144.58 --> 5145.62]  And when they're all like,
[5145.68 --> 5149.08]  they're all somehow like hammering on the same spot.
[5149.08 --> 5149.42]  Right.
[5149.54 --> 5149.90]  Because,
[5150.14 --> 5150.44]  right.
[5151.02 --> 5151.30]  Yeah.
[5151.82 --> 5152.34]  I don't know.
[5152.36 --> 5152.70]  But those are,
[5152.70 --> 5153.88]  those are the biggest game projects.
[5153.88 --> 5154.26]  Right.
[5154.26 --> 5156.08]  But so my history is much,
[5156.16 --> 5156.32]  much,
[5156.36 --> 5156.88]  much smaller.
[5156.88 --> 5157.20]  So,
[5157.32 --> 5159.66]  so the game before the witness that I did called braid,
[5159.66 --> 5161.18]  like I did most of it.
[5161.26 --> 5161.94]  And then,
[5161.94 --> 5162.40]  um,
[5162.66 --> 5163.08]  there's a guy,
[5163.24 --> 5165.54]  David Hellman who drew the majority of the visuals.
[5165.54 --> 5167.30]  And then we had a few other people help out,
[5167.30 --> 5168.16]  but you know,
[5168.16 --> 5168.32]  that,
[5168.32 --> 5171.80]  that shipped on the Xbox 360 in 2008.
[5171.80 --> 5175.36]  And it was competitive with other games that you could play.
[5175.42 --> 5175.96]  Like it wasn't,
[5176.02 --> 5178.68]  it wasn't competitive in the sense of like high budget.
[5178.78 --> 5179.14]  Right.
[5179.22 --> 5179.78]  Production values,
[5179.84 --> 5181.86]  but in terms of being an interesting game that you could play that like
[5181.86 --> 5183.40]  looked nice and yeah.
[5183.40 --> 5183.64]  And,
[5183.70 --> 5185.08]  and it was successful on the platform.
[5185.08 --> 5185.66]  And like,
[5185.72 --> 5186.96]  so that's kind of been my,
[5187.08 --> 5190.34]  my thing since then is like doing a lot with a little.
[5190.58 --> 5190.98]  Right.
[5190.98 --> 5191.84]  In terms of,
[5191.96 --> 5192.82]  in terms of resources.
[5192.82 --> 5194.16]  And that's hard sometimes it's,
[5194.16 --> 5195.32]  you know,
[5195.36 --> 5195.70]  but,
[5195.82 --> 5199.92]  but the weird thing about doing a lot with a little is because the things
[5199.92 --> 5201.02]  we're trying to do are ambitious.
[5201.54 --> 5206.84]  We are definitely very much in touch with reality of like what goes fast
[5206.84 --> 5207.70]  on computers.
[5207.92 --> 5208.20]  Right.
[5209.14 --> 5212.64]  And most of the work that we do is about making things go fast.
[5212.80 --> 5213.20]  Right.
[5213.58 --> 5213.98]  Ultimately,
[5214.20 --> 5214.72]  like even,
[5215.10 --> 5215.46]  you know,
[5215.56 --> 5216.90]  so if we want to get some,
[5216.96 --> 5218.56]  some graphics on the screen,
[5218.96 --> 5221.50]  there's ways to do that that are very abstracted.
[5221.50 --> 5222.26]  And there's ways to do that,
[5222.30 --> 5223.12]  that are very fast.
[5223.12 --> 5224.74]  And those are not the same way.
[5224.80 --> 5225.08]  In fact,
[5225.08 --> 5226.34]  they're very different from each other.
[5226.34 --> 5226.58]  Right.
[5226.78 --> 5227.46]  And so,
[5227.84 --> 5228.54]  so we do the,
[5228.54 --> 5228.76]  the,
[5228.76 --> 5229.36]  the fast way,
[5229.36 --> 5230.04]  or we try to,
[5230.34 --> 5231.46]  and as much as that's possible,
[5231.46 --> 5233.34]  sometimes it's too ill defined.
[5233.34 --> 5234.26]  So if you're going to ship on a,
[5234.28 --> 5236.32]  like a lot of different PCs with different GPUs,
[5236.34 --> 5238.80]  it gets harder to know what,
[5238.86 --> 5239.40]  what to do.
[5239.40 --> 5239.66]  Right.
[5240.20 --> 5240.56]  But,
[5240.72 --> 5241.54]  you know,
[5241.58 --> 5241.76]  our,
[5241.76 --> 5242.94]  our deal is just,
[5243.04 --> 5244.02]  we,
[5244.10 --> 5246.04]  we work pretty hard and we,
[5246.22 --> 5247.52]  we try to be productive.
[5247.52 --> 5249.54]  And the way that I found to be productive,
[5249.54 --> 5251.10]  and this is a little bit paradoxical,
[5251.18 --> 5253.14]  especially for being on this podcast is like,
[5253.22 --> 5256.06]  you can't be that far from the CPU,
[5256.06 --> 5259.24]  but if you think every,
[5259.24 --> 5263.44]  every little CPU thing is super interesting and rat hole on,
[5263.56 --> 5265.96]  on doing the optimal job on that thing,
[5266.02 --> 5267.84]  you will never ship a large piece of software.
[5267.84 --> 5268.18]  Right.
[5268.20 --> 5268.70]  And I've seen,
[5268.82 --> 5270.00]  I've seen a lot of people do that.
[5270.00 --> 5270.26]  And,
[5270.38 --> 5274.20]  and so I've sort of been in this weird middle place where it's like,
[5274.20 --> 5275.32]  you know,
[5275.32 --> 5276.84]  like for,
[5276.94 --> 5278.02]  for braid on the,
[5278.08 --> 5279.12]  on the Xbox 360,
[5279.12 --> 5279.72]  it was like,
[5279.74 --> 5279.88]  Oh,
[5279.98 --> 5281.22]  particle system slow.
[5281.22 --> 5285.10]  I should use some SIMD intrinsics to speed that up.
[5285.16 --> 5288.82]  So I spend like a month or two learning that and putting it in.
[5288.86 --> 5289.42]  And then I'm like,
[5289.44 --> 5289.74]  all right,
[5289.74 --> 5290.58]  it's fast enough.
[5290.64 --> 5291.50]  I got to move on.
[5291.50 --> 5291.70]  Right.
[5291.90 --> 5293.82]  Because there's just so much to do.
[5293.82 --> 5294.10]  So much to do.
[5294.36 --> 5294.54]  Right.
[5295.82 --> 5296.50]  It does.
[5296.82 --> 5296.98]  Well,
[5297.04 --> 5297.90]  but that's interesting.
[5297.90 --> 5298.92]  And actually in retrospect,
[5298.92 --> 5303.22]  I'm sure I could have done a much better job on that particle system with my
[5303.22 --> 5305.22]  current experience had I time traveled back,
[5305.36 --> 5305.76]  but like,
[5305.84 --> 5306.12]  you know,
[5306.68 --> 5310.00]  so there's also this thing where computers today are just too complicated.
[5310.78 --> 5311.22]  You can't,
[5311.42 --> 5311.62]  you can,
[5311.72 --> 5311.92]  you know,
[5312.00 --> 5313.64]  a modern Intel,
[5313.78 --> 5314.02]  you know,
[5314.08 --> 5315.18]  I seven dash,
[5315.52 --> 5317.62]  whatever random string of digits you have.
[5317.80 --> 5321.66]  If you're going to try to actually understand what that's doing in
[5321.66 --> 5322.62]  response to your software,
[5322.62 --> 5323.52]  it's very difficult.
[5323.52 --> 5325.56]  Even using all the tools that Intel gives you,
[5325.92 --> 5326.88]  it's very unlike,
[5327.04 --> 5327.48]  for example,
[5327.60 --> 5328.44]  in the quake days,
[5328.44 --> 5329.32]  where it was like,
[5329.36 --> 5329.64]  okay,
[5330.22 --> 5332.38]  a lot of the CPUs is going to run on our Pentiums.
[5332.70 --> 5334.68]  It's got this like dual pumped thing.
[5334.78 --> 5335.06]  Right.
[5335.08 --> 5335.80]  So we could like,
[5335.86 --> 5337.22]  I forget what the terminology was,
[5337.32 --> 5337.62]  but like,
[5337.62 --> 5338.36]  the R and V pipe,
[5338.44 --> 5338.56]  right?
[5338.56 --> 5339.00]  It had like,
[5339.04 --> 5341.14]  I think of it as A and B,
[5341.34 --> 5342.02]  but whatever.
[5342.18 --> 5342.22]  Yeah,
[5342.22 --> 5342.32]  yeah,
[5342.32 --> 5342.50]  right.
[5342.72 --> 5346.52]  But the point is you'd issue some things for pipe A and then B and you'd
[5346.52 --> 5347.94]  move your instructions around,
[5348.22 --> 5349.28]  you know,
[5349.32 --> 5350.94]  just to try to keep those balanced.
[5350.94 --> 5351.24]  Right.
[5351.36 --> 5351.46]  And,
[5351.78 --> 5351.86]  but,
[5351.90 --> 5352.56]  but that was,
[5352.96 --> 5355.92]  that was a thing where you understood what was going on.
[5355.92 --> 5356.52]  And now it's,
[5356.62 --> 5357.92]  that's simply not even possible.
[5358.44 --> 5359.74]  Really mostly like,
[5359.82 --> 5359.96]  like,
[5360.08 --> 5365.42]  so the number one thing to understand in games and we're reaching the point
[5365.42 --> 5368.38]  because things are so complicated that not that many game programs understand
[5368.38 --> 5368.52]  it.
[5368.54 --> 5369.86]  But the number one thing is,
[5370.26 --> 5370.50]  you know,
[5370.50 --> 5371.68]  don't miss your data cache.
[5371.78 --> 5372.26]  Right.
[5372.36 --> 5372.54]  Right.
[5372.54 --> 5373.50]  Because you pay,
[5373.84 --> 5374.04]  again,
[5374.08 --> 5374.60]  it depends,
[5374.76 --> 5376.94]  but you pay hundreds of cycles for doing that.
[5377.02 --> 5377.24]  Yeah.
[5377.24 --> 5381.40]  And like the absolute worst case is like dependent pointer reads where like,
[5381.46 --> 5381.68]  okay,
[5381.68 --> 5385.00]  I'm looking through this pointer to get this other pointer that like what,
[5385.26 --> 5388.28]  and it doesn't matter how much speculative execution you have at that point.
[5388.32 --> 5388.52]  Right.
[5388.90 --> 5391.52]  Probably most of those cycles are not going to get filled.
[5391.58 --> 5391.76]  Right.
[5391.84 --> 5392.84]  And so the problem is,
[5392.84 --> 5393.64]  it's still the memory wall.
[5393.80 --> 5393.94]  Yeah.
[5394.08 --> 5394.30]  Yeah.
[5394.30 --> 5394.90]  And,
[5394.90 --> 5395.08]  and,
[5395.08 --> 5402.52]  and the thing is most ideas of how to program both the ones from academia and
[5402.52 --> 5403.72]  also the industry ones,
[5403.72 --> 5405.30]  which are kind of a different thing,
[5405.30 --> 5406.40]  but like industry best,
[5406.40 --> 5407.14]  best practices,
[5407.28 --> 5411.34]  ways to program all don't really contend with this reality yet.
[5411.34 --> 5411.88]  And so we,
[5411.94 --> 5412.74]  in the games industry,
[5412.74 --> 5414.14]  we have various things.
[5414.26 --> 5415.92]  So like data oriented design.
[5416.02 --> 5417.02]  I don't know if you've heard of that.
[5417.18 --> 5417.34]  No,
[5417.50 --> 5417.78]  it's,
[5417.78 --> 5418.10]  it's a,
[5418.14 --> 5418.74]  it's a thing.
[5419.24 --> 5421.08]  It was started by some people who are not me,
[5421.16 --> 5421.34]  but,
[5421.50 --> 5422.62]  but I think it's a good idea.
[5422.72 --> 5423.82]  And it's basically like,
[5423.82 --> 5423.98]  look,
[5424.00 --> 5425.50]  if you want your program to run well,
[5426.62 --> 5429.98]  you need to look at what the data transformations are and design for that,
[5430.08 --> 5433.56]  because that's by far the limiting factor on the processing you'll be able to do.
[5434.40 --> 5435.60]  And by the way,
[5435.76 --> 5436.72]  when you do that,
[5436.76 --> 5439.14]  that doesn't look anything like object oriented programming,
[5439.20 --> 5439.70]  for example,
[5439.70 --> 5441.58]  because object oriented is a,
[5441.58 --> 5443.94]  is a totally different factoring that'll cause you to be very slow,
[5443.94 --> 5446.68]  but it also doesn't look like a lot of things that you learn in,
[5446.68 --> 5447.02]  you know,
[5447.02 --> 5447.64]  computer school.
[5447.82 --> 5448.66]  So like,
[5448.66 --> 5449.00]  like in,
[5449.00 --> 5449.22]  in,
[5449.22 --> 5450.66]  in computer science class,
[5450.84 --> 5455.62]  they love telling you to allocate nodes all the time and have pointers between nodes.
[5455.62 --> 5456.96]  That's like half of what you learn.
[5457.04 --> 5457.26]  Right.
[5457.34 --> 5457.84]  But it's like,
[5457.90 --> 5459.70]  suddenly we're in a world where that is very,
[5459.78 --> 5460.50]  very slow.
[5460.86 --> 5461.22]  Right.
[5461.90 --> 5462.26]  But,
[5462.34 --> 5464.66]  but then maybe a lot of programmers don't need to care.
[5465.42 --> 5466.82]  So I have to ask you,
[5466.92 --> 5469.30]  I feel like this is a very on-brand question for me to ask you.
[5469.30 --> 5470.52]  So have you looked at Rust at all?
[5470.56 --> 5470.92]  Cause I think.
[5471.14 --> 5472.38]  I have a little bit.
[5472.44 --> 5473.52]  I actually famously,
[5473.52 --> 5476.30]  I have a rant on YouTube for an hour.
[5476.48 --> 5476.68]  Oh,
[5476.70 --> 5477.06]  nice.
[5477.36 --> 5477.50]  Oh,
[5477.62 --> 5478.60]  I'll have to go watch it.
[5478.82 --> 5478.96]  Okay.
[5479.06 --> 5479.22]  So,
[5479.28 --> 5481.26]  so I don't know if you know this right about me.
[5481.36 --> 5481.88]  So I'm,
[5481.90 --> 5484.94]  I'm also making a programming language now to replace C++.
[5485.52 --> 5485.76]  Ooh.
[5485.76 --> 5486.12]  Because,
[5486.30 --> 5486.84]  cause like I said,
[5486.88 --> 5488.28]  my shtick is doing a lot with a little.
[5488.54 --> 5488.58]  So,
[5488.58 --> 5489.80]  so like now,
[5489.90 --> 5490.20]  so,
[5490.20 --> 5493.28]  so building a game engine,
[5493.58 --> 5494.16]  which is,
[5494.28 --> 5494.60]  you know,
[5494.64 --> 5502.28]  the thing that sort of runs the gameplay code and all that is usually people wouldn't even do that these days.
[5502.28 --> 5503.94]  Cause they would like use licensed engines.
[5504.10 --> 5504.42]  Yeah.
[5504.42 --> 5504.60]  Um,
[5504.98 --> 5505.22]  for,
[5505.34 --> 5506.42]  for both Braid and The Witness,
[5506.56 --> 5507.64]  we built our own things.
[5507.64 --> 5507.84]  And,
[5507.96 --> 5508.98]  but while I was building The Witness,
[5509.12 --> 5509.48]  I was like,
[5509.52 --> 5509.66]  yeah,
[5509.70 --> 5510.10]  C++,
[5511.34 --> 5513.00]  it's not really a good language to do this.
[5513.04 --> 5513.48]  Like when,
[5513.58 --> 5515.20]  when you're like five years into a project,
[5515.34 --> 5516.40]  Witness took six and a half years.
[5516.46 --> 5517.34]  When you're like five years,
[5517.42 --> 5518.40]  five and a half years in,
[5518.86 --> 5519.50]  and you're just like,
[5519.56 --> 5520.00]  oh my God,
[5520.00 --> 5520.96]  this is such a slog.
[5521.06 --> 5522.24]  When are we going to be done with this?
[5522.34 --> 5522.54]  Right.
[5522.58 --> 5525.56]  Which even if you're working on the most exciting thing you ever worked on,
[5525.56 --> 5527.54]  if you're doing it intensely for that long,
[5527.62 --> 5528.14]  it's hard.
[5528.14 --> 5528.88]  That's a long time.
[5528.96 --> 5529.34]  And then,
[5529.44 --> 5534.26]  and then to go in and feel like a lot of my time was being wasted by this stupid programming language.
[5534.38 --> 5535.12]  By the language itself.
[5535.24 --> 5535.32]  Yeah.
[5535.50 --> 5535.72]  Yeah.
[5536.00 --> 5536.20]  Which,
[5536.20 --> 5539.82]  which by the way is really the only option for us in that industry.
[5539.82 --> 5541.96]  Like there's good reasons why we use C++,
[5542.34 --> 5545.20]  but also it's a terrible,
[5545.34 --> 5546.96]  terrible language at this point.
[5547.16 --> 5548.64]  It used to be not so bad,
[5548.72 --> 5553.82]  but then the direction that they're taking C++ is less and less reality based.
[5553.92 --> 5554.50]  I would say.
[5554.50 --> 5554.52]  Okay.
[5554.64 --> 5555.10]  This is interesting.
[5555.32 --> 5557.56]  My view is that C++ was terrible.
[5557.96 --> 5558.08]  Yeah.
[5558.14 --> 5559.66]  And that people who,
[5559.78 --> 5560.06]  I mean,
[5560.14 --> 5560.92]  I've long,
[5561.00 --> 5566.16]  I decided C++ and I broke up in college and I just decided we could never be together.
[5566.44 --> 5566.60]  Yeah.
[5566.88 --> 5567.84]  And people said,
[5567.88 --> 5568.04]  Oh,
[5568.06 --> 5568.76]  it's gotten better.
[5568.76 --> 5570.78]  And C++ 11 and C++ 17.
[5571.10 --> 5571.48]  And I'm like,
[5571.80 --> 5573.08]  that maybe that's great for you.
[5573.20 --> 5577.20]  I can't go back to C++ because of the way that relationship broke up with me,
[5577.26 --> 5580.04]  which is C++ dragging all my stuff into the street and lighting it on fire.
[5580.24 --> 5580.44]  Yeah.
[5580.44 --> 5580.62]  It's like,
[5580.64 --> 5582.08]  we're definitely not getting back together.
[5582.08 --> 5585.30]  I would say that C++ 11 added some good stuff.
[5585.38 --> 5585.60]  Okay.
[5585.80 --> 5586.06]  You know,
[5586.12 --> 5586.86]  but after that.
[5587.26 --> 5587.80]  It overshot.
[5587.94 --> 5588.48]  It overshot.
[5588.60 --> 5592.70]  And then the problem that C++ has is there's a lot of design mistakes in the past.
[5592.70 --> 5592.98]  Yeah.
[5592.98 --> 5594.68]  That they have to carry forward.
[5594.68 --> 5599.94]  And so everything new that gets added is hobbled by having to deal with all these other things.
[5600.10 --> 5600.20]  Right.
[5600.36 --> 5600.58]  And so.
[5601.02 --> 5601.28]  I mean,
[5601.32 --> 5602.34]  that's its origin story,
[5602.52 --> 5602.66]  right?
[5602.82 --> 5603.50]  It is.
[5603.50 --> 5603.82]  Exactly.
[5604.08 --> 5604.36]  C++.
[5604.36 --> 5604.54]  Plus,
[5604.62 --> 5604.74]  I mean,
[5604.84 --> 5605.68]  the end,
[5605.86 --> 5608.40]  just the necessary compatibility with C.
[5608.78 --> 5610.66]  And it's like the comma operator.
[5610.76 --> 5612.12]  You can overload the comma operator.
[5612.28 --> 5612.86]  What does that mean?
[5612.96 --> 5613.56]  Nobody knows.
[5614.48 --> 5614.88]  Certainly,
[5615.06 --> 5615.82]  if you do it,
[5615.98 --> 5616.96]  nobody's going to understand.
[5617.02 --> 5618.14]  Nobody's going to understand it.
[5618.18 --> 5619.30]  It's got it right to left evaluate.
[5619.40 --> 5619.62]  It's like,
[5619.66 --> 5620.00]  you know,
[5620.04 --> 5623.08]  no good is going to happen from overloading the comma operator.
[5623.42 --> 5623.66]  Yeah.
[5623.88 --> 5624.56]  So anyway,
[5624.56 --> 5626.48]  so that's the backdrop of all this.
[5626.74 --> 5626.76]  Right.
[5626.84 --> 5633.48]  And so I started making the language that I'm working on in like 2014 toward the end,
[5633.48 --> 5636.06]  but it wasn't a serious full-time thing until 2016.
[5636.38 --> 5636.42]  Right.
[5636.54 --> 5637.24]  But so now,
[5637.36 --> 5640.72]  now we're building a game in a game engine.
[5640.72 --> 5644.24]  That's a new engine because it's in the new language that is in development.
[5644.24 --> 5646.56]  And we're doing that full stack of things at once.
[5646.70 --> 5646.72]  Right.
[5646.72 --> 5648.00]  And this is Jai,
[5648.10 --> 5648.44]  J-A-I?
[5648.66 --> 5648.82]  Yeah,
[5648.90 --> 5649.02]  yeah,
[5649.02 --> 5649.18]  yeah.
[5649.26 --> 5649.40]  Okay.
[5649.60 --> 5650.00]  And so.
[5650.42 --> 5651.30]  Do you pronounce it Jai?
[5651.40 --> 5651.70]  I'm sorry.
[5651.76 --> 5652.22]  I don't,
[5652.32 --> 5653.18]  I tend not to pronounce it.
[5653.22 --> 5655.00]  It's a code name because one of my.
[5655.02 --> 5655.50]  You don't pronounce it.
[5655.60 --> 5656.24]  Like you're the guy.
[5656.34 --> 5657.28]  You have to tell people how this.
[5657.48 --> 5659.14]  So one of my pet peeves.
[5659.28 --> 5660.80]  It's like you can't tell people to not pronounce it.
[5660.96 --> 5662.46]  One of my pet peeves for decades.
[5662.46 --> 5667.28]  And it got worse once open source became this weird social thing.
[5667.44 --> 5667.66]  Okay.
[5668.30 --> 5672.08]  Is like you go on Hacker News or even before that you read some,
[5672.08 --> 5674.26]  some Usenet posting or some paper.
[5674.26 --> 5674.90]  And it's like,
[5674.94 --> 5677.04]  everybody introduces their like project to you.
[5677.04 --> 5677.66]  And it's like,
[5677.66 --> 5679.74]  whatever weird name,
[5679.92 --> 5681.60]  like diamond dust colon.
[5681.90 --> 5683.38]  And then they tell you what the thing does.
[5683.52 --> 5683.68]  Yeah.
[5683.80 --> 5684.04]  And,
[5684.12 --> 5684.32]  and,
[5684.44 --> 5686.32]  and then you go check it out and it kind of sucks.
[5686.38 --> 5688.02]  And it hasn't had that much work put into it.
[5688.04 --> 5689.98]  And it's maybe not that good of an idea in the first place.
[5689.98 --> 5690.20]  Right.
[5690.48 --> 5691.42]  Most of the time.
[5691.42 --> 5692.10]  And,
[5692.20 --> 5694.18]  and it's like people put all the,
[5695.14 --> 5703.36]  people put all their effort into the cool name and the idea that they're doing a project and then putting it out in the world and getting people to sign up for their project.
[5703.36 --> 5705.18]  That hasn't really had that much work put into it.
[5705.28 --> 5705.44]  Yeah.
[5705.50 --> 5705.92]  So I,
[5705.94 --> 5708.40]  I am doing things in the opposite way.
[5708.40 --> 5708.84]  There you go.
[5708.94 --> 5709.04]  Okay.
[5709.04 --> 5709.88]  So this language,
[5709.88 --> 5711.76]  a name that is deliberately not pronounceable.
[5711.94 --> 5712.14]  Well,
[5712.22 --> 5713.32]  it's not that it's not pronounceable.
[5713.32 --> 5713.94]  It's just that I don't,
[5714.00 --> 5715.48]  I don't use it because it's maybe not the real name.
[5715.58 --> 5715.78]  Okay.
[5715.82 --> 5716.18]  Got it.
[5716.26 --> 5716.52]  Fair enough.
[5716.52 --> 5716.78]  You know,
[5717.08 --> 5717.40]  and,
[5717.58 --> 5717.96]  um,
[5718.48 --> 5719.96]  we haven't released this language to anybody,
[5720.06 --> 5722.30]  even though it's been in work for five years.
[5722.42 --> 5722.58]  Okay.
[5722.58 --> 5722.82]  Uh,
[5722.82 --> 5724.58]  it's been runnable for the whole time.
[5724.58 --> 5727.40]  It's been expanding in feature set and reliability and all this,
[5727.48 --> 5727.60]  but,
[5727.68 --> 5728.36]  but like,
[5728.66 --> 5729.20]  so,
[5729.32 --> 5731.12]  so one of my beefs about open source again,
[5731.12 --> 5732.72]  I also like about that is like,
[5732.80 --> 5734.90]  I feel there is too much emphasis,
[5735.24 --> 5737.64]  especially in open source on winning.
[5738.32 --> 5738.96]  And it's like,
[5738.98 --> 5740.42]  my language needs to win.
[5740.98 --> 5741.38]  Yeah.
[5741.50 --> 5741.78]  My,
[5741.88 --> 5745.06]  my database needs to win and my software needs to win.
[5745.08 --> 5745.42]  And it's like,
[5745.56 --> 5746.56]  actually your software,
[5746.88 --> 5748.36]  if it's useful for you,
[5748.44 --> 5749.24]  it can just,
[5749.32 --> 5751.70]  I love the fact that you get this language that is usable,
[5751.70 --> 5752.58]  that you're using,
[5752.70 --> 5753.96]  that you haven't yet released.
[5754.06 --> 5754.16]  Yeah.
[5754.22 --> 5754.36]  So,
[5754.42 --> 5755.22]  so I went to Berkeley,
[5755.30 --> 5755.50]  right?
[5755.62 --> 5759.56]  And there was this idea of the Berkeley approach versus the MIT approach back
[5759.56 --> 5759.82]  then,
[5759.82 --> 5761.48]  and that the Berkeley approach always wins,
[5761.56 --> 5761.68]  right?
[5761.72 --> 5767.44]  The MIT approach was you craft some beautiful jewel in your backyard or in your
[5767.44 --> 5769.84]  garage or something for many years and you make it perfect.
[5770.12 --> 5771.28]  And then you release it.
[5771.32 --> 5772.82]  And the Berkeley approach was like,
[5772.86 --> 5772.98]  Oh,
[5772.98 --> 5775.64]  you just kind of do something and you let people use it sort of like the
[5775.64 --> 5778.86]  minimum viable product that like web people do now.
[5778.98 --> 5779.10]  Right.
[5779.10 --> 5782.00]  And so that was considered to be like the right way to do things,
[5782.16 --> 5782.26]  but,
[5782.34 --> 5783.66]  but situations change.
[5783.66 --> 5787.44]  And I think we're now in a situation where everybody in the world is flooded
[5787.44 --> 5791.14]  by low quality software and everybody wishes that they had higher
[5791.14 --> 5791.96]  quality software,
[5792.18 --> 5792.94]  at least,
[5793.02 --> 5794.14]  at least people who make software,
[5794.24 --> 5794.56]  I think.
[5794.70 --> 5794.88]  Right.
[5794.98 --> 5795.90]  And so the,
[5795.94 --> 5797.14]  the amount of time that I,
[5797.14 --> 5797.82]  like,
[5797.88 --> 5798.08]  so,
[5798.14 --> 5801.54]  so we're making a game games have a lot of things they want to do.
[5801.54 --> 5806.40]  A lot of those things are potentially stuff that a library could do of
[5806.40 --> 5807.00]  some kind.
[5807.28 --> 5807.42]  Right.
[5807.82 --> 5808.06]  And,
[5808.12 --> 5809.04]  and so let's go out,
[5809.32 --> 5809.90]  whether it's,
[5809.98 --> 5810.24]  you know,
[5810.24 --> 5813.58]  maybe to do some constructive solid geometry or like,
[5813.60 --> 5813.82]  you know,
[5813.84 --> 5815.54]  text layout or something.
[5815.54 --> 5815.80]  Right.
[5815.80 --> 5817.58]  There's a lot of different little sub jobs.
[5817.76 --> 5817.96]  Right.
[5818.38 --> 5819.52]  And so if I go on the internet,
[5819.52 --> 5820.20]  like what,
[5820.32 --> 5823.24]  what is the state of the art of what people out there are doing for this
[5823.24 --> 5823.74]  task?
[5823.74 --> 5824.10]  Right.
[5824.10 --> 5828.04]  Very often I will find a number of things that claim to do the job.
[5828.62 --> 5832.68]  Some of them actually do it to an okay level and some don't.
[5833.10 --> 5834.18]  And a lot of them are,
[5835.00 --> 5838.80]  don't really work for like high stress situations.
[5839.12 --> 5842.46]  And a lot of them don't even like fricking compile anywhere.
[5842.46 --> 5842.90]  Right.
[5842.90 --> 5847.54]  And like just the amount of swimming through a sewer that I have to do to
[5847.54 --> 5851.76]  even figure out what is the thing that I should seriously consider to maybe
[5851.76 --> 5853.62]  do this job versus writing it myself.
[5853.80 --> 5854.04]  Right.
[5854.20 --> 5857.88]  That is a huge investment time and energy investment.
[5857.98 --> 5858.18]  Right.
[5858.58 --> 5861.28]  And then maybe I start using something and then I find out later that it
[5861.28 --> 5863.64]  doesn't do a very robust job of solving the problem,
[5863.64 --> 5865.42]  but it took me a month to figure that out.
[5865.42 --> 5865.60]  Right.
[5865.60 --> 5865.72]  Right.
[5866.00 --> 5867.00]  Because things were,
[5867.86 --> 5870.42]  that's how much investment I had to put in to get to the point where the
[5870.42 --> 5871.30]  problem was hard.
[5871.50 --> 5872.34]  And it's like,
[5872.44 --> 5873.60]  I,
[5873.66 --> 5877.04]  I've developed a very strong distaste for that.
[5877.12 --> 5881.78]  Like I feel like if you put some source code out into the world and claim
[5881.78 --> 5886.20]  that people should check this cool thing out and it's like not actually doing a
[5886.20 --> 5887.08]  good job at what it does,
[5887.14 --> 5890.66]  you're kind of creating an ecological disaster because of the scaling factor.
[5890.78 --> 5890.92]  Right.
[5890.98 --> 5892.50]  How many people are going to download,
[5892.50 --> 5895.96]  how many people are going to invest time in your thing before they figure out
[5895.96 --> 5896.96]  it's not actually good.
[5897.10 --> 5899.12]  So the NPM ecosystem is the,
[5899.32 --> 5901.74]  is going to be the canonical example of this problem for you.
[5901.84 --> 5902.14]  I imagine.
[5902.22 --> 5902.34]  Sure.
[5902.40 --> 5904.44]  I have very little experience in that territory,
[5904.58 --> 5905.90]  but it sounds,
[5906.26 --> 5906.48]  you know,
[5906.52 --> 5908.04]  I know about left pad and all that stuff.
[5908.04 --> 5908.28]  Oh yeah.
[5908.42 --> 5908.58]  No,
[5908.64 --> 5909.30]  just from a note,
[5909.38 --> 5912.18]  like from a psychological safety perspective,
[5912.18 --> 5916.54]  you should avoid the NPM ecosystem because it is the absolute very worst.
[5916.62 --> 5916.74]  I mean,
[5916.84 --> 5918.14]  don't you feel Jess that like the,
[5918.42 --> 5918.72]  I mean,
[5919.06 --> 5921.86]  there's a spectrum and I do think that like,
[5921.86 --> 5924.86]  and I think the go ecosystem is probably like meh.
[5925.56 --> 5926.36]  It's kind of in the middle.
[5927.24 --> 5928.82]  Of like good software.
[5928.82 --> 5929.16]  Of like,
[5929.16 --> 5929.52]  of like,
[5929.66 --> 5930.54]  like if I,
[5930.70 --> 5933.40]  if there are in the note ecosystem,
[5933.40 --> 5936.58]  there are 15 things that do this task.
[5936.70 --> 5937.26]  None of them will.
[5937.64 --> 5937.88]  Okay.
[5937.98 --> 5938.18]  Okay.
[5938.26 --> 5938.94]  That's in,
[5939.02 --> 5939.82]  in the go ecosystem.
[5939.82 --> 5941.48]  There are six things that do this task.
[5941.60 --> 5942.46]  Some of them.
[5942.68 --> 5943.04]  Okay.
[5943.88 --> 5945.66]  Some of them forkable to make good.
[5945.74 --> 5946.18]  Some of them.
[5946.34 --> 5949.74]  But I think that's just a testament of the fact that JavaScript is around longer.
[5949.74 --> 5950.24]  I totally,
[5950.32 --> 5950.68]  I agree.
[5950.68 --> 5951.28]  I agree that,
[5951.44 --> 5952.10]  that the,
[5952.34 --> 5952.50]  and,
[5952.88 --> 5954.10]  and I mean,
[5954.16 --> 5956.72]  JavaScript's core value is growth is metastasis.
[5956.96 --> 5958.02]  And as a result,
[5958.14 --> 5961.08]  they want to make everyone be able to write a program,
[5961.08 --> 5963.44]  which I think is laudable at some level,
[5963.44 --> 5964.44]  but it means that a lot of,
[5964.56 --> 5965.88]  there's a lot of garbage out there.
[5966.32 --> 5966.70]  It is.
[5966.84 --> 5967.48]  I have to,
[5967.52 --> 5968.48]  is one of the things that,
[5968.58 --> 5968.72]  again,
[5968.72 --> 5970.06]  I know I'm being very on brand here,
[5970.06 --> 5974.92]  but it's one of the things I like about Rust is that it's so much harder to get something to work.
[5975.22 --> 5975.38]  And it,
[5975.86 --> 5976.08]  no,
[5976.10 --> 5977.24]  but it's just like the cognitive load.
[5977.24 --> 5977.40]  I mean,
[5977.46 --> 5977.56]  it,
[5977.56 --> 5978.00]  it,
[5978.00 --> 5980.46]  it forces you to have this true,
[5980.56 --> 5982.36]  the true cognitive load of your software.
[5982.62 --> 5984.50]  You have to absorb when you're developing it,
[5984.50 --> 5986.16]  as opposed to being able to just kind of poop it out.
[5986.26 --> 5986.36]  Well,
[5986.48 --> 5987.18]  so I agree.
[5987.26 --> 5988.20]  I agree that that's good.
[5988.20 --> 5988.72]  Like I,
[5989.04 --> 5992.64]  the thing that I don't like so much about Rust and several other languages,
[5992.64 --> 5992.86]  like,
[5992.92 --> 5993.10]  okay,
[5993.14 --> 5995.38]  the mission statement of Rust,
[5995.66 --> 5996.36]  broadly speaking,
[5996.36 --> 5998.46]  I think is very good,
[5998.46 --> 5998.98]  right?
[5999.22 --> 6001.34]  Like fast,
[6001.46 --> 6002.24]  fast and safe.
[6003.02 --> 6003.42]  Yes.
[6003.46 --> 6003.70]  We're,
[6003.70 --> 6004.16]  we're going to,
[6004.22 --> 6004.88]  we're going to improve.
[6004.88 --> 6007.66]  Let me make it even more general and who knows,
[6007.78 --> 6009.40]  Rust people might not agree with this restatement,
[6009.52 --> 6009.94]  but like the,
[6009.94 --> 6014.56]  the broad thing that we need to work on is we need to make software work better.
[6014.76 --> 6015.16]  Generally,
[6015.16 --> 6018.12]  we need to make it more so that when you write a program,
[6018.32 --> 6020.06]  you know that it's correct,
[6020.06 --> 6020.58]  right?
[6020.68 --> 6022.08]  To a greater degree than today.
[6022.22 --> 6022.44]  Yeah.
[6022.48 --> 6022.64]  Right.
[6022.64 --> 6031.72]  And it would be helpful to do that in ways that are not the ones that have been well trodden because we,
[6031.84 --> 6033.80]  we kind of have seen those ways before.
[6033.92 --> 6034.56]  So for example,
[6034.70 --> 6035.00]  you know,
[6035.50 --> 6036.60]  a garbage collect,
[6036.66 --> 6038.20]  like a list variant or something,
[6038.32 --> 6038.46]  right?
[6038.46 --> 6038.62]  Right.
[6039.02 --> 6039.48]  Is actually,
[6039.54 --> 6040.66]  it's safe in certain ways,
[6040.72 --> 6043.24]  but it's actually very unsafe in other ways because like lisps,
[6043.34 --> 6043.84]  for example,
[6043.84 --> 6047.76]  were not traditionally statically type checked and who,
[6047.84 --> 6050.52]  who realized that that's actually important.
[6050.52 --> 6050.82]  Right.
[6050.82 --> 6051.78]  And so,
[6052.10 --> 6052.30]  you know,
[6052.36 --> 6052.56]  Rust,
[6052.68 --> 6053.54]  I think has a good,
[6053.60 --> 6055.14]  has a good set of ingredients there.
[6055.26 --> 6059.98]  The problem that I have with it is when I'm working on really hard stuff,
[6060.52 --> 6062.54]  I don't exactly know what I'm doing for a long time.
[6062.60 --> 6062.86]  Right.
[6063.34 --> 6065.04]  And so if the,
[6065.04 --> 6067.34]  if the cost of experimentation is driven too high,
[6067.42 --> 6070.20]  it actually impairs my ability to get work done.
[6070.38 --> 6070.56]  Right.
[6070.82 --> 6071.02]  Yeah.
[6071.04 --> 6071.92]  I think that that's fair.
[6072.16 --> 6072.48]  And so,
[6072.52 --> 6072.96]  and so my,
[6073.02 --> 6076.30]  my approach that we're doing in the language I'm working on is,
[6076.36 --> 6077.32]  is different.
[6077.32 --> 6077.94]  It's like,
[6077.94 --> 6081.40]  you have very,
[6081.46 --> 6081.64]  very,
[6081.72 --> 6089.06]  very extensive metaprogramming facilities and you can use those to build your own correctness checking,
[6089.26 --> 6089.52]  right?
[6089.56 --> 6094.46]  For your program that you traditionally would have needed to make like a compiler extension to do,
[6094.68 --> 6095.34]  which is like,
[6095.68 --> 6098.04]  that's pretty far away from what people do day to day.
[6098.10 --> 6100.50]  And they just don't end up doing it even if they could have.
[6100.56 --> 6100.74]  Right.
[6100.74 --> 6101.26]  And so,
[6101.62 --> 6107.42]  so what happens is your metaprogram gets information that normally would only be internal to the compiler.
[6107.62 --> 6107.80]  Like,
[6107.88 --> 6108.76]  like here's,
[6109.32 --> 6112.70]  you get like a message loop while you're compiling and it's like,
[6112.76 --> 6112.90]  oh,
[6113.22 --> 6113.52]  this,
[6113.66 --> 6115.92]  this declaration just compiled.
[6116.36 --> 6117.22]  It's a procedure.
[6117.48 --> 6118.50]  You get the full time,
[6118.56 --> 6119.76]  like here's the types of the arguments.
[6119.88 --> 6121.18]  Here's the types of the return value.
[6121.64 --> 6122.14]  Here's the,
[6122.24 --> 6122.50]  you know,
[6122.62 --> 6124.66]  this identifier maps to this other thing.
[6124.78 --> 6127.14]  And so you could start having house rules that,
[6127.46 --> 6127.84]  that,
[6128.02 --> 6128.14]  okay.
[6128.14 --> 6129.04]  So it's an example.
[6129.20 --> 6130.14]  So I have kind of the,
[6130.20 --> 6131.84]  the compile time.
[6131.96 --> 6133.44]  I have compiled time logic.
[6135.02 --> 6138.08]  That can enforce different kinds of constraints.
[6138.22 --> 6138.34]  Yes.
[6138.36 --> 6139.86]  And you can decide what that is later.
[6140.10 --> 6141.52]  So a video game example,
[6141.52 --> 6142.26]  because you know,
[6142.28 --> 6144.46]  this is motivated by the,
[6144.46 --> 6145.76]  the reality that I come from.
[6145.76 --> 6145.92]  Right.
[6145.94 --> 6146.14]  Yeah.
[6146.14 --> 6149.38]  So we have these game engines and an object in a game world.
[6149.52 --> 6150.62]  We don't use the word object.
[6150.62 --> 6152.16]  Cause that got commandeered by object.
[6152.28 --> 6152.56]  Right.
[6153.04 --> 6154.22]  Commandeered and slaughtered.
[6154.32 --> 6155.54]  So we call them entities,
[6155.78 --> 6155.88]  right.
[6156.26 --> 6156.38]  Right.
[6156.38 --> 6157.26]  Even though somebody else.
[6157.40 --> 6157.50]  Right.
[6157.50 --> 6158.00]  So like my,
[6158.00 --> 6159.48]  my coffee cup is like an entity,
[6159.60 --> 6159.90]  right.
[6160.06 --> 6162.90]  And so entities have data associated with them and so forth.
[6162.90 --> 6164.68]  And you might have different kinds of entities,
[6164.68 --> 6165.48]  like a person.
[6165.90 --> 6169.40]  You probably want a lot of different things to happen for a person than like,
[6169.40 --> 6170.10]  you know,
[6170.10 --> 6170.84]  a soccer ball,
[6170.92 --> 6171.14]  right.
[6171.16 --> 6172.38]  Those are very different.
[6172.80 --> 6173.20]  And,
[6173.20 --> 6173.26]  and,
[6173.34 --> 6173.86]  and so,
[6174.60 --> 6174.94]  you know,
[6174.94 --> 6178.96]  we tend to make those different types of entities and somehow they end up
[6178.96 --> 6180.78]  having different behavior and so forth.
[6180.78 --> 6181.02]  But,
[6181.36 --> 6181.92]  you know,
[6181.96 --> 6183.82]  the way people have different ways of representing this,
[6183.92 --> 6184.14]  of course,
[6184.14 --> 6185.84]  but the way that I tend to do it is like a very,
[6186.06 --> 6188.26]  very shallow inheritance thing where there's like,
[6188.52 --> 6191.54]  there's a base that's like entity and it's got all the things that are common to
[6191.54 --> 6191.88]  everybody.
[6192.20 --> 6195.22]  And then like one level subclassing maybe.
[6195.46 --> 6195.60]  Right.
[6195.94 --> 6196.18]  Other,
[6196.18 --> 6197.38]  other people do that a different way,
[6197.38 --> 6197.66]  but,
[6197.80 --> 6198.10]  um,
[6198.10 --> 6201.22]  I think the way I do it is probably among the most common,
[6201.34 --> 6201.56]  right.
[6202.48 --> 6205.72]  And are you inheriting the interface or implementation or both?
[6205.78 --> 6205.92]  Well,
[6206.70 --> 6210.60]  it's not really about interface and implementation is the thing.
[6210.70 --> 6211.22]  It's just like,
[6211.26 --> 6211.40]  look,
[6211.44 --> 6212.58]  there's the data and do it,
[6212.74 --> 6213.58]  do what you want with it.
[6213.58 --> 6216.14]  Like there's not getters and setters and whatever.
[6216.30 --> 6216.54]  Right.
[6216.54 --> 6216.82]  Usually.
[6217.16 --> 6217.40]  Right.
[6217.44 --> 6217.66]  Okay.
[6218.28 --> 6218.50]  I,
[6218.62 --> 6221.40]  I don't find those to actually solve any problems.
[6221.58 --> 6221.82]  Amen.
[6222.36 --> 6223.78]  So usually,
[6223.78 --> 6224.38]  uh,
[6224.38 --> 6225.34]  an entity will have an ID,
[6225.44 --> 6227.06]  like it's got some handle that used to look it up.
[6227.06 --> 6228.98]  It's probably an integer or functionally an integer.
[6229.12 --> 6231.22]  Maybe it's a couple of fields packed into a thing.
[6231.22 --> 6231.56]  Right.
[6232.06 --> 6232.54]  And so,
[6232.94 --> 6234.76]  because there's a coordination problem,
[6234.76 --> 6238.24]  you have a lot of things moving around in a game and like something gets
[6238.24 --> 6238.68]  destroyed,
[6238.80 --> 6239.02]  right.
[6239.08 --> 6242.80]  You blow it up or it gets paged out to another area of the world that you're
[6242.80 --> 6244.66]  not simulating anymore or something.
[6244.66 --> 6247.00]  And you have to work within a limited amount of memory.
[6247.40 --> 6249.10]  So you have to destroy these things,
[6249.22 --> 6252.14]  but the nature of a game is all these things want to coordinate with each other
[6252.14 --> 6252.66]  all the time.
[6252.66 --> 6252.86]  Right.
[6252.86 --> 6255.30]  And so if you just naively delete something,
[6255.30 --> 6259.32]  then some other entity that's trying to follow that thing is now following an
[6259.32 --> 6260.32]  initialized memory or something.
[6260.32 --> 6260.58]  Right.
[6260.58 --> 6260.62]  Right.
[6260.62 --> 6260.72]  Right.
[6260.72 --> 6261.42]  And so what do you do?
[6261.70 --> 6262.10]  Well,
[6262.98 --> 6263.40]  you know,
[6263.50 --> 6266.08]  often you'll refer to things with a handle.
[6266.40 --> 6266.46]  Yeah.
[6266.50 --> 6267.96]  Modern C++ people,
[6268.12 --> 6269.10]  I'm putting air quotes,
[6269.34 --> 6269.90]  uh,
[6269.90 --> 6270.56]  as I say that,
[6270.60 --> 6271.72]  because I think it's a silly phrase,
[6271.72 --> 6271.94]  but,
[6272.04 --> 6273.44]  but those people would say like,
[6273.48 --> 6275.48]  you should use some weird kind of smart pointer for that.
[6275.58 --> 6275.98]  Oh God.
[6275.98 --> 6279.72]  But that's not actually what you want to do because you want to have like very
[6279.72 --> 6283.40]  clear and authoritative control over what is the memory for this thing?
[6283.40 --> 6284.28]  When is it live?
[6284.36 --> 6285.32]  When is it not live?
[6285.64 --> 6287.86]  Exactly what happens at exactly that moment.
[6287.86 --> 6288.10]  Right.
[6288.16 --> 6292.96]  Which smart pointers are more about like kind of hiding things and magically
[6292.96 --> 6295.32]  stuff happens later when I don't exactly know.
[6295.32 --> 6295.56]  Right.
[6295.62 --> 6296.64]  It's the wrong thing.
[6296.86 --> 6297.38]  So anyway,
[6298.00 --> 6298.22]  see,
[6298.34 --> 6302.30]  so you have some integer ID that you use and you say,
[6302.36 --> 6302.60]  Hey,
[6303.02 --> 6307.26]  give me the pointer to the entity that corresponds to this ID that I like,
[6307.32 --> 6308.30]  say I'm following this entity.
[6308.30 --> 6311.26]  So I get back that pointer or it says,
[6311.38 --> 6311.44]  Oh,
[6311.46 --> 6312.22]  it doesn't exist.
[6312.22 --> 6314.98]  And because there's a specific time at which this happens,
[6315.18 --> 6319.58]  you're going to handle the non-existing case because it's obvious.
[6319.58 --> 6319.84]  Right.
[6319.94 --> 6320.10]  Right.
[6320.26 --> 6320.96]  And then it's like,
[6320.98 --> 6321.16]  okay,
[6321.16 --> 6322.48]  I'm going to start looking at all this data,
[6322.56 --> 6323.78]  which might be quite a lot of data.
[6324.28 --> 6324.80]  You know,
[6324.84 --> 6325.78]  I might need to use a lot.
[6325.86 --> 6327.64]  So I take the pointer for a while and do stuff with it.
[6327.78 --> 6329.68]  Now we have a safety problem,
[6329.68 --> 6330.14]  right?
[6330.18 --> 6330.78]  Because like,
[6330.82 --> 6331.12]  okay.
[6332.10 --> 6332.80]  When are you done with this?
[6332.94 --> 6333.14]  Yeah.
[6334.06 --> 6334.30]  Right.
[6334.30 --> 6335.90]  And so in games,
[6335.94 --> 6338.96]  the way that's traditionally handled is there's a very natural barrier,
[6339.10 --> 6340.18]  which is the end of the frame.
[6340.18 --> 6340.42]  Right.
[6340.44 --> 6344.54]  So we do a bunch of stuff over and over 60 times per second or 200 times per
[6344.54 --> 6344.66]  second,
[6344.72 --> 6344.88]  whatever.
[6345.10 --> 6345.28]  Right.
[6345.74 --> 6347.12]  And at the end of that frame,
[6347.12 --> 6351.50]  we pretty much know that it's all garbage now.
[6351.74 --> 6352.10]  Well,
[6352.16 --> 6352.50]  we're not,
[6352.60 --> 6353.90]  we're not really hanging on to anything.
[6353.90 --> 6354.04]  Right.
[6354.14 --> 6354.26]  Right.
[6354.26 --> 6354.50]  Exactly.
[6354.64 --> 6356.26]  So it's a very clean cut.
[6356.36 --> 6356.48]  Yeah.
[6356.48 --> 6356.60]  Right.
[6356.60 --> 6356.88]  Right.
[6357.68 --> 6358.08]  So,
[6358.54 --> 6358.88]  well,
[6359.26 --> 6361.10]  it's a very reasonable thing to say,
[6361.10 --> 6365.98]  it's fine to do that stuff as long as you don't hold an entity pointer across a
[6365.98 --> 6366.54]  frame boundary.
[6366.78 --> 6367.02]  Right.
[6367.30 --> 6367.50]  Yeah.
[6367.82 --> 6372.32]  Now that's not a very generalizable rule because what's an entity pointer versus
[6372.32 --> 6373.30]  a pointer to something else?
[6373.34 --> 6374.56]  Your compiler doesn't know that.
[6374.68 --> 6374.84]  Right.
[6374.96 --> 6376.10]  But you know that.
[6376.34 --> 6376.60]  Right.
[6376.64 --> 6380.20]  And so when the new guy shows up or the summer intern shows up and writes some
[6380.20 --> 6383.42]  code where he puts that entity pointer into a data structure that like.
[6383.50 --> 6385.04]  That actually is surviving across a frame.
[6385.04 --> 6386.50]  Like some hash table that's sitting around.
[6386.66 --> 6386.78]  Right.
[6387.18 --> 6388.46]  That's going to be a problem.
[6388.64 --> 6388.84]  Right.
[6388.84 --> 6390.46]  And that's a very practical,
[6391.04 --> 6392.12]  real kind of problem.
[6392.20 --> 6392.28]  Yeah.
[6392.30 --> 6393.64]  It's not an academic made up problem.
[6394.28 --> 6395.04]  So how do you enforce that?
[6395.04 --> 6395.54]  You actually can solve that.
[6395.60 --> 6396.80]  Your metaprogram can say like,
[6396.90 --> 6397.10]  well,
[6397.68 --> 6398.02]  you,
[6398.10 --> 6401.84]  you put an entity pointer in this data structure and that data structure is not
[6401.84 --> 6403.50]  in this white list that I have over here.
[6403.62 --> 6405.06]  And so error,
[6405.34 --> 6406.00]  you don't compile.
[6406.18 --> 6406.28]  Right.
[6406.36 --> 6406.52]  Right.
[6406.62 --> 6409.06]  And so you can start solving the very,
[6409.18 --> 6412.90]  the very specific problems that you have without introducing general friction.
[6413.36 --> 6413.46]  Now,
[6413.58 --> 6413.94]  is that,
[6414.00 --> 6415.38]  is that better than the rest approach?
[6415.42 --> 6415.92]  I don't know.
[6415.92 --> 6416.74]  I think it will be,
[6416.74 --> 6419.34]  but I certainly offer you no proof of that statement.
[6419.54 --> 6423.66]  I think it's interesting because it's grimier a little bit in that it is like less academically
[6423.66 --> 6424.16]  pleasing.
[6424.58 --> 6424.90]  Yes.
[6425.04 --> 6425.46]  Because it's like,
[6425.54 --> 6425.66]  oh,
[6425.72 --> 6428.24]  but I should have a type system that should,
[6428.44 --> 6430.84]  it should be the type system that should enforce that.
[6431.32 --> 6434.00]  And as opposed to this kind of programmed logic,
[6434.32 --> 6435.68]  because effectively you have a,
[6435.68 --> 6437.86]  a dynamically programmable type system.
[6438.86 --> 6439.22]  Yeah.
[6439.26 --> 6439.46]  Well,
[6439.46 --> 6440.08]  it's not really,
[6440.16 --> 6440.54]  I mean this,
[6440.64 --> 6442.92]  I don't think of this checking as being part of the type system.
[6442.92 --> 6443.18]  Right.
[6443.28 --> 6446.10]  Because the type system is like,
[6446.10 --> 6452.70]  it's like what you would get if you went back to like somewhere between C and C++ and then made
[6452.70 --> 6454.84]  all the decisions the right way instead of the wrong way.
[6454.84 --> 6454.96]  Yeah.
[6454.96 --> 6455.12]  Interesting.
[6455.12 --> 6456.92]  About like what automatically casts to what.
[6457.04 --> 6457.24]  Yeah.
[6458.24 --> 6458.64]  And,
[6458.64 --> 6461.10]  and you're allowing it yourself to like,
[6461.16 --> 6464.74]  you're saying I'm going to have programmable logic about what can be casted to what.
[6465.08 --> 6466.02]  Not in a smart pointer,
[6466.14 --> 6467.32]  but presumably at compile time,
[6467.40 --> 6467.46]  right?
[6467.46 --> 6467.72]  Well,
[6467.92 --> 6469.28]  not even really.
[6469.52 --> 6470.58]  Does your logic execute at,
[6470.68 --> 6472.50]  does that intern that made the mistake,
[6472.50 --> 6473.84]  did they know that at compile time?
[6473.94 --> 6474.08]  Oh yeah.
[6474.38 --> 6474.68]  Interesting.
[6474.94 --> 6475.06]  Yeah.
[6475.06 --> 6475.34]  Yeah.
[6475.50 --> 6475.96]  That's cool.
[6476.10 --> 6476.48]  I like it.
[6476.66 --> 6476.88]  But it,
[6476.90 --> 6478.28]  but it's not through the type system.
[6478.36 --> 6478.52]  Sure.
[6478.62 --> 6478.74]  Right.
[6478.82 --> 6479.12]  Exactly.
[6479.30 --> 6482.64]  It's like the type system is made available to your arbitrary code,
[6482.74 --> 6483.50]  which then does this thing.
[6483.80 --> 6484.02]  But anyway,
[6484.16 --> 6484.38]  so,
[6484.50 --> 6484.76]  um,
[6484.82 --> 6485.66]  that's very practical.
[6485.66 --> 6486.08]  I think,
[6486.10 --> 6486.58]  I think it's neat.
[6486.82 --> 6487.06]  Yeah.
[6487.38 --> 6488.66]  Are you going to,
[6488.78 --> 6490.10]  is the intent to get that,
[6490.44 --> 6492.02]  to get this broadly out there after?
[6492.54 --> 6492.82]  Well,
[6493.02 --> 6495.98]  closed beta begins by the end of 2019.
[6496.32 --> 6496.60]  Okay.
[6496.80 --> 6497.04]  Oh,
[6497.26 --> 6498.34]  that's very exciting.
[6498.72 --> 6499.94]  That's coming right up.
[6500.06 --> 6501.20]  I don't know when this will air.
[6501.32 --> 6502.56]  So maybe it will already have happened.
[6502.88 --> 6504.04]  So it would be open source.
[6504.04 --> 6505.56]  We'll be not initially.
[6505.72 --> 6505.88]  No,
[6505.96 --> 6506.12]  sure.
[6506.26 --> 6506.32]  Oh,
[6506.32 --> 6507.88]  but I think in the longterm,
[6507.88 --> 6509.84]  if you want people to use a programming language,
[6509.84 --> 6510.94]  they have to be able to have source.
[6510.94 --> 6513.46]  So the one thing it does remind me of a little bit is D,
[6514.04 --> 6515.82]  not mechanically from D,
[6515.92 --> 6516.06]  not,
[6516.10 --> 6517.68]  not from in terms of what D actually did.
[6517.68 --> 6517.92]  I mean,
[6517.96 --> 6520.86]  D makes a lot of really decisions that are different.
[6521.34 --> 6521.70]  No,
[6521.76 --> 6521.86]  but,
[6521.86 --> 6522.84]  but I think that the,
[6522.84 --> 6529.04]  the meta decision that Walter Bright made was to have that be kind of the last proprietary compiler.
[6529.64 --> 6530.82]  And I think D,
[6531.32 --> 6534.40]  if D had been opened five or six years earlier,
[6534.88 --> 6535.22]  it would,
[6535.32 --> 6536.14]  it might've taken off.
[6536.24 --> 6538.04]  I think it would have had a broader relevance.
[6538.04 --> 6538.28]  Again,
[6538.64 --> 6539.36]  not that I,
[6539.36 --> 6539.86]  I,
[6539.86 --> 6540.76]  I just to,
[6540.88 --> 6543.48]  I hate the idea that we all need to pick winners.
[6543.48 --> 6544.18]  I think it's ridiculous.
[6544.30 --> 6544.92]  I think that it's,
[6545.02 --> 6545.26]  it,
[6545.44 --> 6545.78]  you know,
[6545.78 --> 6548.36]  if it's a solution for someone's problem,
[6548.44 --> 6548.80]  it's a good,
[6548.94 --> 6549.18]  you know,
[6549.20 --> 6549.70]  that's great.
[6550.06 --> 6551.20]  But I think it sounds interesting.
[6551.60 --> 6551.70]  Yeah.
[6551.70 --> 6551.92]  You know,
[6551.96 --> 6552.12]  okay.
[6552.12 --> 6552.32]  So,
[6552.38 --> 6553.66]  so going back to Rust for a second,
[6553.82 --> 6555.34]  one of the things that I like about it,
[6555.36 --> 6555.86]  like I said,
[6555.90 --> 6556.34]  is like,
[6556.36 --> 6556.62]  okay,
[6556.62 --> 6562.00]  we're going to approach this problem of memory safety through compile time management as opposed to runtime management.
[6562.08 --> 6562.32]  That's right.
[6562.40 --> 6562.54]  Right.
[6562.82 --> 6563.22]  I mean,
[6563.30 --> 6564.08]  that's the,
[6564.56 --> 6569.14]  but it does force you to really accept some limitations.
[6569.36 --> 6569.54]  Yes.
[6569.60 --> 6569.96]  It's not,
[6570.06 --> 6570.24]  it's,
[6570.38 --> 6572.22]  that's a non-trivial statement to make that,
[6572.30 --> 6573.34]  that has a lot of implications.
[6573.34 --> 6573.70]  Right.
[6573.98 --> 6577.14]  But at least it's starting to rethink some stuff.
[6577.32 --> 6577.38]  And,
[6577.44 --> 6578.74]  and so going back to.
[6579.18 --> 6581.20]  But I think you have a good point because I think that one of the,
[6581.20 --> 6581.32]  the,
[6581.32 --> 6587.40]  the kind of system that Rust struggles with is where you've got a lot of inner connections and interdependencies.
[6587.52 --> 6590.34]  So to the point where it's advised,
[6590.42 --> 6590.76]  and I think,
[6590.84 --> 6597.32]  I think rightly so that like you want to get away from these complicated object graphs where everyone's got a kind of pointer to everybody else.
[6597.48 --> 6597.66]  Yeah.
[6597.66 --> 6598.68]  Because Rust,
[6599.00 --> 6602.88]  those are going to be multiply owned data structures and Rust is going to bridle at that.
[6602.88 --> 6603.80]  You can get it to work,
[6603.92 --> 6604.44]  but it's ugly.
[6604.88 --> 6605.02]  Well,
[6605.10 --> 6605.32]  and then,
[6605.36 --> 6607.50]  and then a lot of what people do sometimes,
[6607.50 --> 6611.56]  it seems like they don't realize that they're skirting around the system,
[6611.68 --> 6611.94]  but they,
[6612.06 --> 6612.80]  they really are.
[6612.94 --> 6613.02]  So,
[6613.28 --> 6613.78]  so for example,
[6613.78 --> 6614.18]  I mentioned,
[6614.18 --> 6615.42]  I have a rant on YouTube.
[6615.52 --> 6616.78]  It's not an angry rant,
[6616.88 --> 6617.46]  but it's like,
[6617.60 --> 6618.60]  I saw,
[6618.60 --> 6620.08]  this is what I see about my rant too.
[6620.20 --> 6620.44]  I think,
[6620.50 --> 6621.28]  thank you for saying that.
[6621.32 --> 6621.54]  It's like,
[6621.62 --> 6623.82]  it's a rant with like a glint in the eye.
[6623.92 --> 6625.86]  It's more of a rant in the sense of unprepared,
[6626.24 --> 6626.38]  right?
[6626.38 --> 6627.96]  I spoke for an hour unprepared,
[6628.44 --> 6628.56]  but,
[6628.62 --> 6630.42]  so basically another,
[6630.54 --> 6633.68]  another company in the games industry was experimenting using Rust.
[6633.78 --> 6634.84]  There are a few people doing that,
[6634.92 --> 6635.08]  right?
[6635.08 --> 6635.28]  And,
[6635.28 --> 6636.98]  and we'll see how it goes,
[6637.06 --> 6637.66]  but you know,
[6637.72 --> 6639.52]  for now it's the early stages of an experiment.
[6640.02 --> 6644.06]  And one of the engineers from one of these companies did a presentation at RustCon,
[6644.26 --> 6644.66]  I guess,
[6644.86 --> 6645.74]  is that what it's called?
[6645.90 --> 6646.62]  Where she said,
[6646.68 --> 6646.86]  Hey,
[6647.12 --> 6648.32]  here's what I like about Rust.
[6648.36 --> 6652.86]  Cause it led me toward this design of a way of doing this entity system.
[6652.96 --> 6653.06]  Yeah.
[6653.12 --> 6653.28]  So,
[6653.38 --> 6655.48]  so that entity problem that I was talking about before,
[6655.60 --> 6655.82]  right?
[6655.90 --> 6657.54]  This is a talk at RustCon for 2018,
[6657.66 --> 6657.94]  I think.
[6658.08 --> 6658.52]  Something like that.
[6658.56 --> 6658.76]  Yeah.
[6659.18 --> 6659.76]  Pretty recent.
[6659.90 --> 6660.02]  Yeah.
[6660.02 --> 6660.90]  It was good talking.
[6661.16 --> 6661.54]  And so,
[6661.98 --> 6662.28]  you know,
[6662.36 --> 6662.52]  the,
[6663.18 --> 6664.82]  what I said before about,
[6665.08 --> 6665.28]  you know,
[6665.32 --> 6668.58]  what happens if one entity is following another one and one of them goes away and you have
[6668.58 --> 6669.42]  uninitialized memory,
[6669.52 --> 6669.66]  right?
[6670.24 --> 6670.64]  Well,
[6670.80 --> 6675.74]  that's exactly the kind of memory safety problem that Rust is supposed to help you figure
[6675.74 --> 6676.44]  out is there,
[6676.52 --> 6676.80]  right?
[6677.16 --> 6677.32]  And,
[6677.42 --> 6678.84]  but this particular system,
[6679.34 --> 6681.36]  I don't want to go in super much into the details,
[6681.46 --> 6681.82]  but the,
[6681.82 --> 6682.54]  the point of it,
[6682.74 --> 6684.12]  there's this thing called entity component system,
[6684.20 --> 6685.44]  which is a different structure of,
[6685.48 --> 6686.14]  of doing this.
[6686.14 --> 6688.42]  And mostly it involves what,
[6688.42 --> 6691.76]  what that phrase means these days is sort of,
[6691.80 --> 6691.98]  it's,
[6691.98 --> 6693.82]  it's laid out in a data oriented way.
[6693.82 --> 6695.54]  So if you're going to get the memory for a new entity,
[6695.74 --> 6700.16]  it's like maybe in some preallocated arena with all the things of the same size.
[6700.28 --> 6701.90]  So if you were to allocate and deallocate,
[6702.10 --> 6705.14]  you could like grab something out of that spot and put it back.
[6705.18 --> 6707.38]  And there's like no fragmentation or anything like that.
[6707.38 --> 6707.62]  Right.
[6707.72 --> 6707.92]  Right.
[6708.14 --> 6708.72]  And so,
[6708.82 --> 6711.64]  but this entity component system that was being,
[6711.78 --> 6715.78]  the virtues of which were being extolled in this talk was essentially a custom memory
[6715.78 --> 6718.90]  allocator just where everything was the same size.
[6718.90 --> 6719.46]  So,
[6719.46 --> 6720.86]  so they were the same type.
[6721.00 --> 6723.96]  So that the type system wasn't getting angry.
[6723.96 --> 6724.36]  Right.
[6724.82 --> 6725.44]  But like,
[6725.76 --> 6726.68]  it still has,
[6727.24 --> 6727.52]  you know,
[6727.56 --> 6730.30]  you still could have a use after free bug that,
[6730.46 --> 6734.30]  that the compiler wouldn't catch because the compiler just doesn't know this is a memory
[6734.30 --> 6734.78]  allocator.
[6734.78 --> 6734.98]  Right.
[6735.18 --> 6737.34]  And so I keep seeing things like that where I'm like,
[6737.40 --> 6738.98]  I'm not sure,
[6739.36 --> 6739.62]  like,
[6739.62 --> 6744.56]  I'm not sure that the amount that's being paid is worth what is actually being gotten.
[6744.92 --> 6745.04]  Right.
[6745.28 --> 6745.72]  However,
[6746.44 --> 6749.42]  I greatly respect the fact that Rust is going in this direction.
[6749.42 --> 6754.46]  And I wish a lot more people would like where we kind of need to have some new ideas about
[6754.46 --> 6756.28]  how to program well,
[6756.30 --> 6760.56]  because we've been following the old ones for a while and we've kind of seen where they go.
[6761.16 --> 6762.48]  And it's not that great.
[6762.64 --> 6763.24]  It's not that great.
[6763.40 --> 6763.58]  Yeah.
[6763.72 --> 6765.46]  And I think that this also,
[6765.68 --> 6765.78]  we,
[6765.98 --> 6767.24]  and I think we may well see,
[6767.24 --> 6773.20]  and I should think we should see some bifurcation in languages around purpose and around where,
[6773.28 --> 6774.14]  because I do think that,
[6774.14 --> 6775.56]  that Rust struggles,
[6775.64 --> 6776.78]  because I thought a lot about like,
[6776.82 --> 6779.06]  what does it mean to like rewrite the operating system in Rust?
[6780.08 --> 6781.70]  And there are a lot of things where it's like,
[6781.82 --> 6787.38]  it will be grisly and it will have limited utility and limited payoff because there are so many
[6787.38 --> 6788.54]  multiply owned data structures.
[6789.04 --> 6789.44]  When,
[6789.50 --> 6791.60]  when data structures have true multiple ownership,
[6791.92 --> 6794.22]  it means that in Rust,
[6794.22 --> 6797.54]  you're going to have to pull tricks to get that to work.
[6798.48 --> 6801.78]  But there are lots of data structures where you have multiple ownership,
[6801.90 --> 6803.50]  where you don't actually need to have multiple ownership.
[6803.58 --> 6808.32]  And if you rethink your problem and recast it in a way where you've got that ownership kind of going one direction,
[6808.62 --> 6810.02]  and where things are singly owned,
[6810.46 --> 6811.12]  then Rust says,
[6811.20 --> 6811.28]  hey,
[6811.32 --> 6813.56]  if you can recast your problem this way,
[6813.72 --> 6814.52]  in return,
[6814.68 --> 6816.74]  I'm going to give you a high performing artifact that you can really,
[6816.84 --> 6817.38]  that is safe.
[6817.64 --> 6817.76]  Yeah.
[6817.80 --> 6818.72]  And I think that's valuable.
[6819.18 --> 6819.58]  However,
[6819.92 --> 6820.70]  I think also,
[6821.24 --> 6821.44]  you know,
[6821.52 --> 6825.00]  there's always people who are very overzealous about any particular idea.
[6825.18 --> 6825.30]  Right.
[6825.46 --> 6825.64]  Right.
[6825.64 --> 6829.88]  And I think the people who are overzealous say that that's a hundred percent of it.
[6830.06 --> 6834.02]  Like you always can make your program better by getting rid of the multiple ownership.
[6834.16 --> 6835.44]  And that's not true in my experience.
[6835.46 --> 6836.56]  I think that's fair.
[6836.68 --> 6836.78]  Yeah.
[6836.88 --> 6837.00]  Yeah.
[6837.04 --> 6837.30]  You know,
[6837.30 --> 6837.70]  that's fair.
[6837.82 --> 6838.22]  And like,
[6838.32 --> 6840.68]  sometimes like your problem is your problem,
[6840.68 --> 6840.94]  right?
[6840.96 --> 6842.18]  Like engineering is,
[6842.42 --> 6844.20]  means that you're confronting reality.
[6844.58 --> 6844.84]  Yeah.
[6844.92 --> 6846.10]  And reality is what it is.
[6846.10 --> 6847.68]  And you don't get to decide what it is.
[6847.68 --> 6848.42]  As an engineer,
[6848.60 --> 6850.06]  you're dealing with reality.
[6850.16 --> 6850.36]  Yeah.
[6850.52 --> 6851.68]  As best you can.
[6851.94 --> 6852.14]  Right.
[6852.70 --> 6853.10]  So.
[6854.12 --> 6856.64]  If your problem has that tight interconnectedness.
[6856.90 --> 6857.04]  Yeah.
[6857.14 --> 6857.60]  I think it's.
[6857.76 --> 6859.16]  Going to a simpler example,
[6859.16 --> 6859.68]  right.
[6859.96 --> 6860.18]  That,
[6860.22 --> 6863.76]  that takes the rust part out of the equation for any rust enthusiasts for listening.
[6863.88 --> 6864.06]  Right.
[6864.46 --> 6865.74]  One thing people will say is like,
[6865.76 --> 6865.86]  Oh,
[6865.86 --> 6869.48]  your program shouldn't have global state at all because global state invites bugs,
[6869.60 --> 6870.16]  you know,
[6870.54 --> 6870.76]  right.
[6870.76 --> 6872.22]  In all the ways that we've been told.
[6872.64 --> 6873.06]  Okay.
[6873.06 --> 6874.00]  That's a true statement.
[6874.00 --> 6875.24]  Like all things being equal,
[6875.24 --> 6877.66]  if you have global state that you don't need,
[6878.46 --> 6879.42]  it's probably bad.
[6879.72 --> 6880.70]  You should probably get rid of it.
[6880.80 --> 6881.24]  And I,
[6881.28 --> 6881.96]  I agree with that.
[6881.96 --> 6882.18]  Right.
[6882.22 --> 6884.38]  But actually games have tons of global state.
[6884.48 --> 6884.72]  Yeah.
[6884.72 --> 6885.16]  Because like,
[6885.24 --> 6887.42]  actually a lot of the problems that we need to solve,
[6887.92 --> 6891.88]  the actual problem is a global state manipulation problem.
[6891.94 --> 6892.22]  Okay.
[6892.24 --> 6892.48]  Right.
[6892.58 --> 6895.08]  And so pretending that it's not by saying like,
[6895.14 --> 6895.28]  look,
[6895.32 --> 6900.54]  I have a functional language and I'm going through seven layers of things so that I can avert my eyes
[6900.54 --> 6904.90]  sufficiently from the fact that I'm actually just manipulating globals at the end of the day.
[6904.98 --> 6905.12]  Right.
[6905.12 --> 6905.30]  Right.
[6905.44 --> 6906.80]  That's just an obfuscation.
[6906.92 --> 6908.26]  It doesn't actually solve any problems.
[6908.26 --> 6908.52]  That's right.
[6908.52 --> 6909.84]  It certainly doesn't make you fast.
[6909.94 --> 6910.02]  Right.
[6910.02 --> 6910.14]  It's like,
[6910.14 --> 6911.00]  it's a global washing.
[6911.32 --> 6911.40]  You,
[6911.40 --> 6911.66]  you,
[6911.66 --> 6911.86]  you,
[6911.86 --> 6911.96]  you,
[6911.96 --> 6912.00]  you,
[6912.00 --> 6912.26]  you,
[6912.26 --> 6912.66]  you,
[6912.66 --> 6913.92]  that's a good term.
[6914.32 --> 6914.68]  Yeah.
[6914.78 --> 6915.02]  I mean,
[6915.02 --> 6915.78]  even like,
[6916.40 --> 6916.76]  I don't know,
[6917.20 --> 6917.48]  we won't,
[6917.54 --> 6920.34]  we won't start talking about singletons and how they're totally not globals.
[6920.86 --> 6921.22]  Um,
[6921.28 --> 6921.50]  right.
[6921.54 --> 6921.84]  Exactly.
[6921.96 --> 6922.36]  But no,
[6922.42 --> 6926.12]  I think it's a very good point that your problem is what your problem is.
[6926.48 --> 6926.84]  Yes.
[6926.84 --> 6930.16]  And the task should be to find something that is,
[6930.28 --> 6932.16]  that is tightly tailored to that.
[6932.38 --> 6932.54]  Yeah.
[6932.58 --> 6932.96]  And so,
[6933.08 --> 6935.54]  so when I get into arguments with people about this,
[6935.58 --> 6936.38]  I try not to,
[6936.44 --> 6942.84]  because it's just hard because like I've seen problems that are multiple ownership problems.
[6943.50 --> 6943.94]  Fundamentally,
[6943.96 --> 6945.20]  they just are right.
[6945.56 --> 6945.76]  And,
[6945.84 --> 6951.38]  and so you can't tell me to refactor that until it's like saying just refactor your program.
[6951.46 --> 6953.12]  So it runs on the cell processor fast.
[6953.30 --> 6954.00]  What's your problem?
[6954.16 --> 6954.50]  Right.
[6954.64 --> 6955.06]  And it's like,
[6955.12 --> 6955.28]  well,
[6955.50 --> 6956.10]  wait a minute.
[6956.10 --> 6956.32]  Yeah.
[6956.74 --> 6957.40]  It's a good,
[6957.60 --> 6957.70]  well,
[6957.72 --> 6957.80]  no,
[6957.84 --> 6958.06]  and I,
[6958.16 --> 6960.16]  I really feel this way around doubly linked lists.
[6960.30 --> 6962.46]  Doubly linked lists are a multiply owned data structure.
[6962.78 --> 6963.76]  And I think that,
[6963.76 --> 6970.48]  that Rust advocates do themselves a disservice when they say you shouldn't need a doubly linked list.
[6971.26 --> 6971.82]  It's like,
[6971.94 --> 6972.06]  Hey,
[6972.16 --> 6972.56]  screw you.
[6972.62 --> 6973.96]  I need a doubly linked list for this problem.
[6974.04 --> 6974.60]  Or I,
[6974.60 --> 6974.74]  I,
[6974.88 --> 6975.22]  the,
[6975.54 --> 6976.28]  for this problem,
[6976.34 --> 6977.60]  my problem is what my problem is.
[6977.96 --> 6978.32]  Now,
[6978.42 --> 6979.22]  I think what it,
[6979.42 --> 6983.38]  and I think that I would say that most people in the Rust community are much more balanced about this.
[6983.38 --> 6983.64]  I'm saying,
[6983.76 --> 6983.86]  Hey,
[6984.50 --> 6986.00]  you can do that if you need to,
[6986.00 --> 6988.40]  but if you can possibly recast your problem,
[6988.40 --> 6988.84]  if you can,
[6988.92 --> 6991.12]  if you can let go of that particular way,
[6991.16 --> 6992.32]  you've implemented it for a second,
[6992.32 --> 6995.42]  if you can recast your problem in this other way,
[6995.42 --> 6996.98]  you can get this great dividend.
[6996.98 --> 6998.42]  But I think there are problems that are,
[6998.52 --> 7000.58]  that are not going to be able to be recasted that way.
[7000.66 --> 7000.90]  I mean,
[7000.92 --> 7001.50]  and that's just,
[7001.60 --> 7001.78]  yeah,
[7002.06 --> 7002.78]  but that's okay.
[7002.78 --> 7003.10]  I mean,
[7003.10 --> 7003.36]  you know,
[7003.42 --> 7003.60]  we're,
[7003.66 --> 7004.58]  we're figuring it out.
[7004.70 --> 7004.88]  Like,
[7004.92 --> 7008.18]  does anybody think that programming,
[7008.96 --> 7012.00]  assuming the human race exists,
[7012.08 --> 7012.38]  you know,
[7012.38 --> 7013.60]  in 300 years or something,
[7013.94 --> 7014.16]  does,
[7014.24 --> 7017.18]  does programming 300 years from now look like programming today?
[7017.18 --> 7018.36]  I don't think it does.
[7018.50 --> 7018.64]  Ooh,
[7018.64 --> 7019.64]  that's a great question.
[7019.64 --> 7020.00]  So like,
[7020.12 --> 7021.50]  I don't know what it looks like.
[7022.00 --> 7023.70]  I have some ideas about what it looks like.
[7023.74 --> 7025.24]  So you were talking before about like,
[7025.28 --> 7025.56]  you know,
[7026.32 --> 7028.28]  everybody can program kind of things,
[7028.40 --> 7028.56]  you know,
[7028.56 --> 7029.42]  like president Obama,
[7029.56 --> 7030.60]  everybody should learn to code.
[7030.76 --> 7031.12]  Like,
[7031.36 --> 7032.20]  I think that's,
[7032.86 --> 7033.74]  on the one hand,
[7033.78 --> 7035.94]  I think people are right when they say that that's a computer skill,
[7036.04 --> 7036.76]  but on the other hand,
[7037.18 --> 7037.86]  that's different.
[7038.04 --> 7038.90]  We don't say like,
[7038.96 --> 7041.56]  everybody should build a bridge that traffic drives across.
[7041.56 --> 7041.84]  Right.
[7041.98 --> 7042.12]  Right.
[7042.38 --> 7042.96]  Those are,
[7043.14 --> 7044.92]  we also don't say that everyone should write literature.
[7045.10 --> 7046.52]  I think everyone should be able to read and write,
[7046.52 --> 7049.66]  but everybody could write their poetry in high school or whatever.
[7049.84 --> 7050.84]  Like that's not bad,
[7051.12 --> 7051.30]  but,
[7051.42 --> 7056.40]  but we don't say that everybody deserves to have their novel read by the
[7056.40 --> 7056.78]  nation.
[7056.96 --> 7057.36]  Right.
[7057.36 --> 7057.58]  Right.
[7058.04 --> 7059.56]  And so those things,
[7059.68 --> 7063.18]  there's just some clarity there that we have not reached when it comes to
[7063.18 --> 7063.48]  software.
[7063.48 --> 7064.02]  I think you're right.
[7064.12 --> 7064.62]  I think you're right.
[7064.68 --> 7067.10]  And I think it's good for people to have technical skills to know how to
[7067.10 --> 7067.42]  program.
[7067.58 --> 7067.96]  I think,
[7068.02 --> 7072.08]  what does it look like when people who are not like bridge builders,
[7072.42 --> 7073.38]  when they program,
[7073.48 --> 7075.50]  I think it looks different from when bridge builders program.
[7075.64 --> 7076.14]  I think maybe,
[7076.14 --> 7076.90]  so in,
[7076.94 --> 7077.42]  in games,
[7077.42 --> 7080.18]  we have these systems that are visual programming kind of things like
[7080.18 --> 7082.24]  blueprints and unreal or things like,
[7082.48 --> 7082.88]  it's like,
[7082.90 --> 7083.22]  you know,
[7083.34 --> 7086.60]  connect boxes with some lines to do a thing that kind of looks like a
[7086.60 --> 7086.86]  circuit,
[7086.86 --> 7088.24]  but you get around like,
[7088.68 --> 7088.88]  you know,
[7088.92 --> 7091.42]  infinite loop problems and flow control problems.
[7091.42 --> 7093.52]  And you kind of don't have pointers or anything.
[7093.52 --> 7093.88]  Right.
[7094.20 --> 7094.78]  Very simple,
[7095.20 --> 7096.32]  still a limited model,
[7096.46 --> 7096.96]  but I think,
[7097.04 --> 7098.20]  you know,
[7098.22 --> 7102.04]  the future for like non low level programmers starts to look like that
[7102.04 --> 7102.34]  eventually.
[7102.34 --> 7102.80]  It doesn't,
[7102.90 --> 7104.20]  it doesn't look like a,
[7104.20 --> 7105.48]  like JavaScript,
[7105.80 --> 7106.32]  for example.
[7106.44 --> 7106.54]  Right.
[7106.70 --> 7109.58]  I think that computational literacy actually is important as a universal
[7109.58 --> 7110.10]  attribute,
[7110.10 --> 7114.90]  but that doesn't mean that everyone is going to be at arbitrary depth.
[7114.90 --> 7115.34]  And it,
[7115.34 --> 7116.54]  and it certainly does not,
[7116.60 --> 7119.12]  it doesn't mean should everyone be writing rust?
[7119.36 --> 7119.78]  No,
[7119.86 --> 7121.06]  probably not actually.
[7121.66 --> 7122.62]  Certainly not everybody,
[7122.62 --> 7125.26]  but should everybody who's building bridges be writing rust?
[7125.38 --> 7125.46]  Well,
[7125.52 --> 7126.32]  rust people would argue.
[7126.40 --> 7126.64]  Yes.
[7126.64 --> 7127.20]  And I would say,
[7127.34 --> 7127.82]  I think,
[7127.86 --> 7128.00]  yeah,
[7128.06 --> 7129.72]  I would say I don't a hundred percent agree,
[7130.28 --> 7132.02]  but we shouldn't be writing C plus plus.
[7132.18 --> 7132.60]  That amen.
[7132.90 --> 7133.14]  Okay.
[7133.40 --> 7133.60]  Yeah.
[7133.60 --> 7134.12]  There we go.
[7134.58 --> 7134.74]  Yeah.
[7134.94 --> 7137.56]  When the 300 years thing is kind of interesting because I actually,
[7137.56 --> 7143.88]  and I still believe that we are in a golden age of software still.
[7144.94 --> 7146.84]  And I think that we are,
[7146.96 --> 7148.42]  we are laying down track.
[7148.56 --> 7149.32]  That will be,
[7149.44 --> 7152.22]  especially as we take some of these big and important iterations.
[7152.22 --> 7153.74]  I do think rust is an important iteration.
[7153.74 --> 7155.92]  I think that Jai,
[7156.08 --> 7156.60]  J-A-I,
[7156.80 --> 7157.56]  whatever it will be,
[7157.68 --> 7160.02]  whatever we renamed diamond dust.
[7160.18 --> 7160.82]  Diamond dust.
[7161.60 --> 7162.04]  Will,
[7162.54 --> 7164.02]  it is potentially an important iteration.
[7164.12 --> 7165.90]  I think that we are going to take some of these big,
[7165.96 --> 7166.72]  important iterations.
[7167.10 --> 7167.70]  And I,
[7167.74 --> 7169.80]  I do think that we're going to be building things that,
[7169.84 --> 7169.98]  you know,
[7169.98 --> 7174.68]  the Romans laid down a lot in terms of civil engineering and the,
[7174.82 --> 7175.20]  you know,
[7175.28 --> 7175.52]  the,
[7175.52 --> 7180.04]  the Greeks laid down a lot in terms of philosophy and,
[7180.04 --> 7180.60]  and,
[7180.60 --> 7181.74]  and how things are constructed.
[7181.74 --> 7185.74]  And I think we're laying down a lot in terms of how future software is
[7185.74 --> 7186.14]  constructed.
[7186.98 --> 7187.38]  Maybe.
[7188.00 --> 7188.68]  I mean,
[7188.78 --> 7189.04]  yeah,
[7189.10 --> 7189.78]  yes and no.
[7189.84 --> 7190.04]  Right.
[7190.12 --> 7190.30]  So,
[7190.46 --> 7191.76]  so one of the things that I can,
[7191.84 --> 7193.80]  I can shill here,
[7193.92 --> 7195.60]  I have a different video on YouTube.
[7195.92 --> 7199.74]  It's a lecture I gave in Moscow this year in March called preventing the
[7199.74 --> 7200.80]  collapse of civilization.
[7201.14 --> 7201.36]  Okay.
[7202.14 --> 7202.86]  Where I,
[7202.86 --> 7205.92]  I do agree with the fact that we're producing a great deal of software,
[7205.92 --> 7211.12]  but I sort of note that these days we don't really expect it to kind of
[7211.12 --> 7212.32]  work that well,
[7212.50 --> 7212.74]  you know,
[7212.74 --> 7212.94]  like,
[7213.16 --> 7216.08]  like computers always computer bugs have always been a thing.
[7216.08 --> 7216.44]  Right.
[7216.52 --> 7217.60]  But like these days,
[7217.60 --> 7220.16]  our expectations seem to be lower and lower.
[7220.56 --> 7220.88]  And so,
[7220.98 --> 7222.00]  and that's where I,
[7222.12 --> 7222.40]  so I,
[7222.40 --> 7225.38]  I do take issue with that in that I think our expectations should be higher
[7225.38 --> 7228.90]  and higher in that we should be writing software for permanence.
[7229.36 --> 7229.76]  Yes.
[7229.76 --> 7230.60]  And I agree with that.
[7230.60 --> 7230.80]  And,
[7230.86 --> 7232.84]  and the problem is we're not really,
[7232.84 --> 7233.46]  and right.
[7233.58 --> 7235.36]  And there's all sorts of weird stuff going on.
[7235.36 --> 7235.48]  So,
[7235.54 --> 7236.20]  so you mentioned,
[7236.32 --> 7236.60]  you know,
[7236.60 --> 7238.02]  like NPM kind of things.
[7238.02 --> 7238.20]  Right.
[7238.20 --> 7241.74]  So my understanding of the way NPM works is when you build something,
[7241.84 --> 7242.80]  you've had such a charmed life.
[7242.86 --> 7243.02]  Yeah.
[7243.32 --> 7243.52]  No,
[7243.56 --> 7244.56]  I've stayed away from that stuff.
[7244.58 --> 7245.68]  You really have stayed away.
[7246.20 --> 7246.66]  I mean,
[7246.72 --> 7247.10]  so,
[7247.16 --> 7247.84]  so when you,
[7247.92 --> 7248.58]  when you build stuff,
[7248.64 --> 7251.40]  the tradition is you just sort of pull down the newest version of any
[7251.40 --> 7252.34]  dependency that you have.
[7252.36 --> 7254.50]  And of course you have like 37,000 dependencies.
[7254.50 --> 7254.96]  Right.
[7255.02 --> 7255.22]  Yeah.
[7255.22 --> 7259.06]  And so everything that I've learned from making video games,
[7259.06 --> 7261.58]  which are very complicated and have to work well,
[7261.58 --> 7262.00]  right.
[7262.40 --> 7265.70]  Is that the way you ship software that works robustly is a,
[7266.44 --> 7266.66]  well,
[7266.74 --> 7266.90]  okay.
[7266.90 --> 7267.14]  So,
[7267.24 --> 7268.18]  so all these obvious things,
[7268.18 --> 7268.34]  like,
[7268.40 --> 7269.28]  of course you test it.
[7269.28 --> 7269.56]  Right.
[7269.58 --> 7270.26]  But what does that mean?
[7270.26 --> 7272.34]  It means you test exactly the thing that you shipped.
[7272.52 --> 7274.56]  It means if you update some sub module,
[7275.12 --> 7278.08]  you don't do that without like fully testing it.
[7278.12 --> 7279.34]  And that's not like automated tests.
[7279.34 --> 7281.36]  That's like playing it for weeks and weeks.
[7281.36 --> 7281.58]  Right.
[7281.64 --> 7281.76]  Yeah.
[7281.76 --> 7281.96]  Right.
[7282.30 --> 7283.04]  But also it means,
[7283.12 --> 7283.36]  you know,
[7283.38 --> 7285.06]  what's in there and you know how it works,
[7285.06 --> 7287.44]  which means you probably don't have 37,000 dependencies.
[7288.42 --> 7292.08]  And it means that once things are established to work,
[7292.14 --> 7293.12]  you kind of harden it.
[7293.18 --> 7293.64]  You say like,
[7293.68 --> 7295.34]  this is the product.
[7295.34 --> 7299.48]  Like we're not going to go have a summer intern swap out parts of this
[7299.48 --> 7301.76]  product when nobody's looking in six months.
[7302.02 --> 7302.12]  Right.
[7302.22 --> 7303.44]  Because like we,
[7303.62 --> 7304.38]  the thing,
[7304.46 --> 7306.70]  the thing that we have vetted is done is,
[7306.84 --> 7308.32]  is yeah,
[7308.40 --> 7308.62]  it's,
[7308.84 --> 7309.54]  this is the thing.
[7309.54 --> 7309.82]  Right.
[7310.14 --> 7312.36]  And that's very counter to like what,
[7312.52 --> 7313.48]  what the web people are,
[7313.50 --> 7314.52]  are doing these days.
[7314.52 --> 7316.46]  And I,
[7316.66 --> 7318.20]  I kind of,
[7318.54 --> 7318.80]  you know,
[7318.80 --> 7319.32]  it's interesting because,
[7319.38 --> 7319.54]  all right.
[7319.58 --> 7319.76]  So no,
[7319.82 --> 7321.10]  I see what you're saying because I,
[7321.28 --> 7324.40]  one of my criticisms of games such as it is,
[7324.44 --> 7327.08]  has been that it's a lot of software that's thrown out,
[7327.08 --> 7332.88]  but because there is this emphasis on completing the artifact and not
[7332.88 --> 7334.16]  constantly evolving it,
[7334.86 --> 7337.02]  there is a higher bar for the correctness.
[7337.02 --> 7337.82]  We,
[7337.82 --> 7339.56]  we throw out a lot less than we used to.
[7339.66 --> 7339.78]  So,
[7339.86 --> 7341.38]  so back in the doom quake days,
[7341.58 --> 7341.78]  yeah,
[7341.78 --> 7345.74]  we would throw everything out every time because what we had to do was so
[7345.74 --> 7346.08]  different.
[7346.28 --> 7346.64]  Nowadays,
[7346.64 --> 7348.48]  that doesn't really happen anymore.
[7349.04 --> 7349.80]  But the thing,
[7349.88 --> 7351.84]  the thing that weirds me out and the more and more,
[7352.00 --> 7355.50]  so the thing I've been doing for the past year or two is like looking around
[7355.50 --> 7356.06]  and saying like,
[7356.12 --> 7356.28]  wait,
[7356.36 --> 7358.96]  where are we with respect to all this software stuff?
[7358.96 --> 7359.36]  And like,
[7359.42 --> 7360.90]  what happened exactly?
[7361.28 --> 7361.40]  Yeah.
[7361.96 --> 7363.12]  So for example,
[7363.98 --> 7364.88]  if you go back to the,
[7364.88 --> 7368.12]  the 1970s invention of Unix or something like that,
[7368.12 --> 7368.36]  right?
[7368.36 --> 7368.66]  What,
[7368.78 --> 7371.32]  what is that operating system?
[7371.40 --> 7372.54]  What does operating system mean?
[7372.66 --> 7372.82]  Well,
[7372.84 --> 7376.80]  it's the thing that just like helps you run programs on this computer,
[7376.80 --> 7377.38]  right?
[7377.90 --> 7382.70]  That was relatively laborious to like startup programs and get them going.
[7382.86 --> 7382.98]  Right.
[7383.02 --> 7383.46]  And so,
[7383.78 --> 7385.68]  so now we have a system that helps us do this.
[7385.70 --> 7385.92]  Right.
[7386.78 --> 7388.28]  So we're 50 years later.
[7388.72 --> 7389.74]  It's a long time.
[7389.96 --> 7390.16]  Yeah.
[7390.16 --> 7392.32]  And we have operating systems still.
[7393.50 --> 7397.04]  And I don't seem to be able to consistently run software on them.
[7397.74 --> 7397.78]  Like,
[7398.46 --> 7398.84]  you know,
[7398.92 --> 7399.28]  whether,
[7399.30 --> 7400.10]  whether it's,
[7400.10 --> 7400.54]  you know,
[7400.64 --> 7401.26]  Linux or,
[7401.26 --> 7402.84]  or Windows or something like that,
[7403.14 --> 7407.16]  distributing a program on Windows that I will know will work.
[7407.38 --> 7411.56]  Work on someone else's Windows computer is really non-trivial.
[7411.70 --> 7412.54]  Like just what,
[7412.60 --> 7414.10]  I don't care what the program even does.
[7414.16 --> 7416.48]  Like once you start getting into things like how it interfaces,
[7416.66 --> 7417.50]  but just like,
[7418.04 --> 7421.60]  do I know that it's going to start up correctly or it's going to pop up
[7421.60 --> 7424.62]  some missing DLL error box?
[7424.76 --> 7425.40]  Like I don't,
[7425.58 --> 7427.24]  it's hard to know that actually.
[7427.68 --> 7427.96]  And the,
[7427.96 --> 7431.24]  the only real way you can know that is by abandoning a lot of the stuff
[7431.24 --> 7434.70]  Microsoft is trying to get programmers to do and having very little in
[7434.70 --> 7435.18]  the way of,
[7435.18 --> 7436.40]  of dependencies and,
[7436.40 --> 7439.04]  and really like focusing down on that.
[7439.08 --> 7439.48]  But like,
[7439.68 --> 7441.30]  nobody steps back and says like,
[7441.36 --> 7441.74]  but wait,
[7441.90 --> 7442.30]  wasn't,
[7443.18 --> 7443.52]  I mean,
[7443.58 --> 7443.80]  what,
[7444.04 --> 7446.58]  why is it so hard to run a program?
[7446.88 --> 7447.04]  You know,
[7447.04 --> 7447.56]  on Linux.
[7447.72 --> 7449.64]  So Linux has a different aesthetic,
[7449.64 --> 7450.22]  right?
[7450.58 --> 7451.98]  People sort of expect that,
[7452.08 --> 7455.08]  that you don't distribute precompiled binaries there.
[7455.44 --> 7455.50]  Right.
[7456.34 --> 7457.00]  But like,
[7457.04 --> 7459.02]  one of the reasons is just that it's so hard to,
[7459.10 --> 7461.48]  to do that and have it actually work for,
[7461.56 --> 7462.08]  for everybody.
[7462.08 --> 7462.42]  Right.
[7462.42 --> 7462.86]  For,
[7463.06 --> 7478.88]  for,
[7478.88 --> 7479.20]  on,
[7479.20 --> 7480.84]  on eight percentage of systems,
[7480.84 --> 7481.96]  this thing just doesn't run.
[7482.06 --> 7483.12]  That's a huge disaster.
[7483.36 --> 7483.60]  Right.
[7483.60 --> 7485.04]  Because that you'll get killed by,
[7485.12 --> 7486.06]  by support calls.
[7486.06 --> 7486.32]  Right.
[7486.42 --> 7486.96]  But anyway,
[7487.12 --> 7487.42]  so,
[7487.94 --> 7488.50]  so this is,
[7488.56 --> 7489.30]  I think you,
[7489.38 --> 7490.24]  you worked at Docker,
[7490.42 --> 7490.68]  right?
[7490.80 --> 7491.04]  Yeah.
[7491.18 --> 7491.50]  And so,
[7491.50 --> 7493.56]  so containers are one of my pet peeves.
[7493.76 --> 7494.70]  Because we've somehow,
[7494.90 --> 7495.32]  it's great.
[7495.48 --> 7495.82]  We've somehow,
[7495.82 --> 7496.14]  like,
[7496.14 --> 7498.16]  like if you go back to like the seventies or eighties,
[7498.22 --> 7499.78]  like you had a couple of computers,
[7499.92 --> 7501.02]  they were the same kind.
[7501.80 --> 7503.64]  You just copy the executable and run it.
[7503.76 --> 7503.94]  Yeah.
[7503.96 --> 7505.44]  Like I remember doing that in college.
[7505.44 --> 7505.84]  Right.
[7506.24 --> 7506.52]  So,
[7506.98 --> 7509.72]  and then somehow we've made this several layers harder by like,
[7509.74 --> 7510.04]  okay,
[7510.40 --> 7512.46]  so you're actually linked against dynamic libraries,
[7512.46 --> 7514.34]  which it seemed like a good idea at first,
[7514.34 --> 7517.10]  but now this other system has different dynamic libraries.
[7517.30 --> 7517.68]  Right.
[7517.74 --> 7518.84]  And so it may not run,
[7518.92 --> 7522.36]  even though they're named the same and you don't bring them with you.
[7522.42 --> 7523.38]  So like that's,
[7523.38 --> 7525.20]  I think containers are a reaction to that,
[7525.24 --> 7525.34]  right?
[7525.34 --> 7525.46]  Well,
[7525.46 --> 7527.94]  containers are trying to get you back to that model you had.
[7528.24 --> 7530.04]  And I have no problem with that.
[7530.06 --> 7532.68]  As long as somebody says,
[7532.84 --> 7534.40]  wait,
[7534.46 --> 7537.36]  this is just covering up for a problem that we solved.
[7537.36 --> 7541.04]  And so maybe eventually we should go back and like collapse these layers and
[7541.04 --> 7542.18]  resolve the problem.
[7542.18 --> 7544.16]  But if you go on like Hacker News or something,
[7544.32 --> 7544.50]  right?
[7544.90 --> 7546.58]  Or the 24 year olds hang out.
[7546.72 --> 7546.94]  Yes.
[7547.04 --> 7551.64]  They think this is advanced software technology that you have a container and
[7551.64 --> 7555.18]  that this provides a new layer that like gives you new capabilities.
[7555.34 --> 7556.10]  And I'm like,
[7556.14 --> 7556.26]  no,
[7556.48 --> 7556.74]  dude,
[7556.82 --> 7559.66]  I could copy a program over the network and run it in,
[7559.74 --> 7560.10]  you know,
[7560.14 --> 7561.50]  the seventies just fine.
[7561.62 --> 7563.20]  We lost that capability.
[7563.40 --> 7563.90]  And actually one,
[7564.00 --> 7565.06]  so one of the points that I,
[7565.22 --> 7565.98]  that I put in,
[7566.06 --> 7567.88]  in this Russia talk was,
[7567.88 --> 7569.90]  I mean,
[7569.90 --> 7571.08]  it's even weirder than that.
[7571.08 --> 7571.34]  Right.
[7571.34 --> 7572.48]  And especially in games,
[7572.48 --> 7573.16]  but,
[7573.22 --> 7574.04]  but broadly speaking.
[7574.22 --> 7582.28]  So if you have a windows PC and a Linux PC and a Mac laptop and a
[7582.28 --> 7583.06]  PlayStation four,
[7583.40 --> 7585.90]  those all have compatible CPUs in them,
[7585.90 --> 7586.24]  right?
[7586.24 --> 7590.66]  If you have a machine language program that you just magically teleport into the
[7590.66 --> 7591.58]  memory of those things.
[7591.58 --> 7594.00]  And if it doesn't go out to the operating system to do anything,
[7594.00 --> 7595.16]  it's just computing a result.
[7595.66 --> 7596.30]  It will,
[7596.40 --> 7600.48]  it will run on all four of those things with no problems.
[7600.56 --> 7600.76]  Yeah.
[7600.90 --> 7601.34]  Perfectly.
[7601.40 --> 7601.62]  Yeah.
[7601.94 --> 7602.42]  Perfectly.
[7602.72 --> 7604.46]  And yet we have,
[7604.92 --> 7605.12]  so,
[7605.18 --> 7609.42]  so we have this capability of perfect cross platform compatibility,
[7609.42 --> 7610.02]  right?
[7610.02 --> 7610.32]  I mean,
[7610.32 --> 7610.58]  by,
[7610.70 --> 7612.40]  by virtue of the platforms being the same,
[7612.54 --> 7612.94]  but whatever.
[7613.32 --> 7613.42]  Yeah.
[7613.48 --> 7615.42]  And we have somehow subtracted that,
[7616.24 --> 7617.56]  at the operating system level.
[7617.62 --> 7617.80]  Yeah.
[7618.12 --> 7619.04]  For what reason?
[7619.12 --> 7619.94]  Hopefully a good reason.
[7620.02 --> 7620.20]  No,
[7620.22 --> 7623.64]  it's just like the executable formats a little bit different and whatever.
[7623.90 --> 7624.12]  Right.
[7624.22 --> 7627.78]  Like reasons that aren't like all these operating systems are kind of doing the
[7627.78 --> 7628.24]  same thing.
[7628.30 --> 7631.36]  They're just doing it in incompatible ways that don't really buy you anything.
[7631.36 --> 7631.58]  Right.
[7631.98 --> 7632.48]  And then,
[7632.54 --> 7632.72]  okay.
[7632.72 --> 7636.10]  So the really horrible thing for the future is we,
[7636.18 --> 7637.02]  we are now in,
[7637.12 --> 7642.78]  in an area where these kinds of infrastructural decisions are being made by
[7642.78 --> 7649.66]  companies who don't seem to have any incentive to cooperate anymore in a
[7649.66 --> 7649.92]  sense.
[7650.44 --> 7650.84]  So,
[7650.90 --> 7652.80]  so going back to the C programming language,
[7653.24 --> 7655.12]  pretty good idea back when it was made,
[7655.16 --> 7655.42]  I guess.
[7655.48 --> 7655.64]  I mean,
[7655.64 --> 7656.40]  a lot of people would,
[7656.40 --> 7657.64]  would think it,
[7657.70 --> 7658.94]  it wasn't particularly good,
[7659.02 --> 7659.78]  but you know,
[7659.78 --> 7663.38]  anyone who's getting complained about C is ordered to spend time in the
[7663.38 --> 7664.80]  languages that immediately predated.
[7664.80 --> 7666.64]  There are reasons why C was successful.
[7666.64 --> 7667.46]  Let's put it that way.
[7667.46 --> 7667.60]  Yeah.
[7667.60 --> 7667.90]  I mean,
[7667.94 --> 7670.02]  C is way better than what comes before it.
[7670.02 --> 7671.46]  Although I wish that they had done,
[7671.76 --> 7674.28]  that they had actually type checked parameters.
[7674.42 --> 7674.82]  That would be nice.
[7674.82 --> 7675.34]  Can RC.
[7675.54 --> 7676.22]  That would have been great.
[7676.40 --> 7676.76]  Great.
[7676.90 --> 7677.04]  Yes.
[7677.46 --> 7677.68]  Yes.
[7678.44 --> 7678.88]  Yes.
[7679.04 --> 7679.40]  The,
[7679.40 --> 7680.28]  the open paren,
[7680.38 --> 7682.12]  close paren thing was not good.
[7682.38 --> 7683.24]  It really wasn't.
[7683.98 --> 7684.82]  It was bad.
[7684.96 --> 7685.00]  Yeah.
[7685.00 --> 7686.74]  That was my first C experience was like,
[7686.78 --> 7687.66]  why is this crashing?
[7687.90 --> 7688.16]  It's like,
[7688.18 --> 7688.32]  Oh,
[7688.32 --> 7689.98]  because a signature is optional.
[7690.22 --> 7690.70]  It's like,
[7690.74 --> 7690.90]  yeah,
[7690.90 --> 7691.22]  right.
[7692.02 --> 7692.42]  Anyway,
[7693.00 --> 7693.24]  but,
[7693.24 --> 7694.58]  but back then it was like,
[7694.62 --> 7694.74]  look,
[7694.80 --> 7695.38]  we have this,
[7695.52 --> 7696.72]  this language.
[7696.72 --> 7699.94]  We can compile for multiple CPUs.
[7699.98 --> 7701.24]  The CPUs might be quite different,
[7701.62 --> 7701.82]  right?
[7701.92 --> 7702.10]  Yeah.
[7702.34 --> 7704.88]  We might have to make some allowances in the,
[7704.94 --> 7705.44]  in the code.
[7705.54 --> 7708.76]  So we do some if defs around small portions of the code where like,
[7709.38 --> 7713.14]  I don't know if we're running on something that doesn't have a certain size integer or something,
[7713.26 --> 7713.58]  do this,
[7713.66 --> 7714.32]  otherwise do this,
[7714.40 --> 7714.56]  right.
[7714.62 --> 7714.96]  Whatever.
[7715.18 --> 7716.50]  We're all very familiar with that.
[7716.64 --> 7716.74]  Right.
[7716.94 --> 7718.04]  That is a good model,
[7718.72 --> 7718.96]  right?
[7718.96 --> 7719.34]  That is,
[7719.46 --> 7720.60]  that got us a long way.
[7721.40 --> 7725.50]  Eventually that got replaced with this interpreter languages model,
[7725.50 --> 7726.10]  which I have,
[7726.18 --> 7729.20]  I could rant for hours about why that's weird and,
[7729.32 --> 7730.72]  and not what we think it is,
[7730.76 --> 7731.12]  but I,
[7731.18 --> 7732.82]  I feel like we're going kind of long.
[7732.82 --> 7733.08]  Like,
[7733.10 --> 7734.38]  I don't know how long this is supposed to be.
[7736.28 --> 7736.98]  But anyway,
[7737.22 --> 7739.16]  so the problem is now,
[7739.54 --> 7739.80]  okay.
[7740.10 --> 7740.50]  So,
[7740.60 --> 7742.82]  so we've had this new hardware introduced like GPUs,
[7742.88 --> 7743.10]  right?
[7743.56 --> 7745.78]  GPUs are very fast at doing the thing that they do.
[7745.88 --> 7749.88]  And then your job to render graphics is to talk to the GPU or to mine Bitcoin or,
[7749.94 --> 7751.34]  or whatever you're trying to do.
[7751.34 --> 7751.66]  Right.
[7751.66 --> 7754.02]  And so how,
[7754.22 --> 7756.08]  how do you communicate across that barrier?
[7756.76 --> 7757.20]  Well,
[7757.38 --> 7758.96]  it going way back,
[7759.00 --> 7760.94]  it was just a data communications.
[7761.10 --> 7764.46]  You would like upload your image data for your texture maps to the GPU.
[7764.66 --> 7770.32]  And then you just send commands through a command buffer where the commands were just like some byte code that says like draw,
[7770.44 --> 7771.62]  draw this triangle or something.
[7771.66 --> 7773.32]  It was pretty primitive back then.
[7773.32 --> 7773.60]  Right.
[7774.10 --> 7775.94]  It's gotten more and more complex where now,
[7776.00 --> 7776.22]  you know,
[7776.22 --> 7780.08]  it certainly rivals as a CPU or exceeds a CPU in complexity.
[7780.08 --> 7782.58]  And so we have programming languages for that.
[7783.04 --> 7783.14]  Right.
[7783.52 --> 7783.86]  Now these,
[7784.12 --> 7784.20]  so,
[7784.28 --> 7785.68]  so we call these like shaders,
[7785.86 --> 7786.08]  right?
[7786.16 --> 7788.10]  Which that name just means,
[7788.40 --> 7789.06]  you know,
[7789.28 --> 7791.56]  it's how you would compute the light on a surface originally,
[7791.56 --> 7794.48]  but it doesn't make sense because now we have like compute shaders,
[7794.64 --> 7799.68]  which just means it's the program that runs on the GPU that runs an arbitrary function.
[7799.78 --> 7800.10]  Right.
[7800.18 --> 7800.50]  Whatever.
[7800.86 --> 7801.12]  Okay.
[7801.12 --> 7813.68]  But all of these languages are being done by either GPU vendors or people who are trying to standardize their graphics API or people who are doing both.
[7813.82 --> 7813.94]  Right.
[7813.98 --> 7814.98]  So operating system people,
[7815.08 --> 7815.64]  GPU people.
[7815.84 --> 7816.12]  Okay.
[7816.12 --> 7818.22]  So we have the opposite of C now.
[7818.68 --> 7818.82]  Okay.
[7818.82 --> 7824.78]  What we have is I can have a system with an Intel CPU and NVIDIA GPU,
[7825.48 --> 7825.64]  right?
[7826.04 --> 7826.48]  Hard drive,
[7826.56 --> 7826.78]  whatever.
[7827.32 --> 7828.60]  If it's running Linux,
[7828.96 --> 7833.42]  I have to use one shading language because I'm using,
[7833.58 --> 7835.58]  let's say OpenGL or Vulkan,
[7835.76 --> 7836.02]  right?
[7836.02 --> 7836.68]  To do the rendering.
[7836.94 --> 7837.84]  If I'm on Windows,
[7837.94 --> 7839.38]  I'm using DirectX to do the rendering.
[7839.50 --> 7841.54]  So I have to use a different programming language.
[7841.66 --> 7841.96]  Right.
[7842.82 --> 7845.06]  I can't compile the same language to a different target.
[7845.18 --> 7847.04]  It is a different programming language that,
[7847.14 --> 7847.58]  by the way,
[7847.70 --> 7850.28]  in much of the way operating systems are different for arbitrary reasons,
[7850.34 --> 7851.52]  but they're all doing the same thing.
[7851.58 --> 7854.62]  All these shading languages are different for arbitrary reasons.
[7855.28 --> 7855.52]  Yeah.
[7855.94 --> 7860.00]  And so now we do all this like transpiling from one shading language to another,
[7860.10 --> 7860.94]  like in the background.
[7861.06 --> 7864.52]  And if it's hard to have like a serious program when you're doing it,
[7864.52 --> 7866.22]  you can't program in the same way anymore.
[7866.22 --> 7866.50]  Right.
[7866.84 --> 7867.58]  And like nobody.
[7867.86 --> 7869.96]  That's getting further away from the ultimate,
[7870.12 --> 7870.98]  from the hardware.
[7870.98 --> 7873.26]  There's no adult supervision.
[7873.54 --> 7874.98]  Like nobody's looking around and saying like,
[7875.06 --> 7875.20]  wait,
[7875.30 --> 7875.54]  what?
[7875.74 --> 7877.22]  Like these programs are actually simpler.
[7877.42 --> 7877.50]  Like,
[7877.58 --> 7882.02]  so C programs were like manipulating data structures and going into the
[7882.02 --> 7883.08]  operating system and all that.
[7883.16 --> 7884.76]  Like shader programs are actually simpler.
[7884.90 --> 7886.12]  They're just mostly doing math.
[7886.46 --> 7886.72]  Competition.
[7886.88 --> 7887.98]  And outputting numbers.
[7888.74 --> 7888.98]  Right.
[7889.06 --> 7889.20]  Right.
[7889.20 --> 7891.20]  That's a strict subset of what we used to do.
[7891.56 --> 7891.88]  I mean,
[7892.16 --> 7895.50]  you start doing weird data structure stuff these days because GPUs are more
[7895.50 --> 7895.84]  powerful,
[7895.84 --> 7898.26]  but like when you do that,
[7898.32 --> 7898.74]  it's in a,
[7898.74 --> 7902.20]  it's in a more streamlined way that is,
[7902.28 --> 7903.06]  is just simpler.
[7903.16 --> 7905.66]  It doesn't require the kind of iron behind it because you're,
[7905.80 --> 7907.72]  you're programming to the GPU as expect,
[7907.84 --> 7909.80]  as opposed to expecting the GPU to come to you.
[7909.80 --> 7909.98]  Right.
[7910.06 --> 7910.20]  Right.
[7910.84 --> 7913.66]  So nobody's looking around and saying like,
[7913.74 --> 7914.06]  what?
[7914.38 --> 7914.68]  Right.
[7914.98 --> 7915.86]  Why is this happening?
[7915.98 --> 7918.18]  And certainly nobody is trying to prevent it from happening.
[7918.32 --> 7918.50]  Right.
[7918.90 --> 7919.12]  Like,
[7919.20 --> 7924.64]  imagine if like you just like a sun workstation use a different
[7924.64 --> 7926.64]  programming language from an Apollo workstation,
[7926.64 --> 7928.50]  which used a different programming language from SGI.
[7928.80 --> 7928.94]  Right.
[7928.94 --> 7929.48]  Like what,
[7929.62 --> 7930.50]  what would have happened?
[7931.08 --> 7931.82]  I don't know,
[7931.88 --> 7932.76]  but it would have been a mess.
[7932.92 --> 7933.04]  Yeah.
[7933.10 --> 7933.50]  But so I,
[7933.60 --> 7936.66]  but I think that that also leads to that,
[7936.66 --> 7940.34]  that tension is what leads to these revolutions.
[7940.76 --> 7941.16]  Right.
[7941.20 --> 7942.60]  It's like where now we're right.
[7942.60 --> 7942.82]  I mean,
[7942.88 --> 7945.22]  because what came before C was a mess.
[7945.28 --> 7948.04]  It was people doing exactly that where the different language that I
[7948.04 --> 7950.82]  have on these different machines was the assembler.
[7951.42 --> 7954.02]  And the assemblers were different for all of these machines.
[7954.02 --> 7956.04]  And C was what came in and,
[7956.38 --> 7957.24]  and so,
[7957.36 --> 7957.48]  I mean,
[7957.48 --> 7958.70]  we could say like before,
[7958.84 --> 7960.16]  before Fortran or something,
[7960.28 --> 7961.08]  that was a situation,
[7961.22 --> 7961.38]  right?
[7961.46 --> 7965.50]  Or did enough people object to Fortran that they just would rather be
[7965.50 --> 7966.06]  an assembler?
[7966.30 --> 7966.44]  Well,
[7966.46 --> 7967.62]  I think for systems programmers,
[7967.84 --> 7969.56]  Fortran was not a real option.
[7969.78 --> 7969.96]  Okay.
[7970.00 --> 7970.16]  Right.
[7970.24 --> 7972.58]  And so operating systems themselves had to be written in the
[7972.58 --> 7973.52]  assembler of the machine.
[7973.66 --> 7973.94]  Right.
[7974.18 --> 7974.88]  And that is what,
[7975.22 --> 7976.30]  and C,
[7976.54 --> 7976.84]  that was,
[7976.90 --> 7979.94]  that was kind of C's gift is that you can now write a portable system
[7979.94 --> 7980.38]  software.
[7981.26 --> 7982.36]  And I think that the,
[7982.46 --> 7982.60]  I mean,
[7982.60 --> 7982.94]  this is,
[7983.10 --> 7985.54]  I think that part of why,
[7985.54 --> 7985.92]  I mean,
[7985.92 --> 7986.50]  I think the,
[7986.62 --> 7991.80]  there is still so much to be had in new computer programming languages is
[7991.80 --> 7992.88]  because we have not yet.
[7993.18 --> 7993.34]  I mean,
[7993.36 --> 7996.94]  I think you see this with Rust and systems programming and maybe with the
[7996.94 --> 7998.60]  future diamond dust in,
[7998.60 --> 7998.90]  it,
[7998.90 --> 7999.04]  it,
[7999.04 --> 8001.28]  it gave programming where it's like,
[8001.30 --> 8003.02]  there actually is innovation to be had.
[8003.56 --> 8004.34]  There's a lot.
[8004.46 --> 8004.86]  There's a lot.
[8004.92 --> 8005.04]  So,
[8005.08 --> 8005.58]  so I'll give you,
[8005.64 --> 8008.58]  I'll give the short version of my interpreted languages spiel because we're
[8008.58 --> 8009.88]  roughly contemporaneous.
[8010.00 --> 8010.28]  You'll,
[8010.34 --> 8011.78]  you'll know where I'm coming from on this.
[8011.82 --> 8012.00]  Right.
[8012.04 --> 8012.28]  So,
[8012.64 --> 8013.56]  so in the nineties,
[8013.56 --> 8017.50]  we were still under this impression that like Moore's law is infinite.
[8017.70 --> 8017.98]  Yes.
[8018.36 --> 8019.62]  And this is what I call it.
[8019.62 --> 8021.74]  This is the true golden age of Moore's law.
[8021.92 --> 8022.06]  Well,
[8022.12 --> 8022.32]  okay.
[8022.36 --> 8022.56]  And,
[8022.62 --> 8027.24]  and there's this history of programming languages that had held up to that
[8027.24 --> 8027.56]  point,
[8027.68 --> 8029.78]  which was back in the olden days,
[8029.78 --> 8031.32]  we programmed in machine language.
[8031.46 --> 8031.64]  Yeah.
[8031.72 --> 8033.06]  And that was just very laborious.
[8033.06 --> 8034.14]  So we made assembly language,
[8034.30 --> 8036.22]  which was a higher level text representation.
[8036.46 --> 8036.64]  Right.
[8036.80 --> 8037.30]  Compiles down.
[8037.40 --> 8040.54]  And people these days don't think there's much of a difference between those two
[8040.54 --> 8040.80]  things,
[8040.88 --> 8041.70]  but try it.
[8041.76 --> 8042.40]  It's really different.
[8042.66 --> 8042.74]  Yeah.
[8042.74 --> 8043.30]  Yeah.
[8043.42 --> 8043.60]  Right.
[8044.14 --> 8044.48]  You know,
[8044.62 --> 8045.18]  okay.
[8045.18 --> 8048.24]  So then assembly language is still very mired in details.
[8048.24 --> 8050.96]  And so then we started having higher level things like Fortran or C.
[8051.10 --> 8051.30]  Right.
[8051.34 --> 8051.78]  And then,
[8052.08 --> 8054.06]  then maybe depending on,
[8054.06 --> 8054.66]  uh,
[8054.72 --> 8055.02]  you know,
[8055.02 --> 8056.56]  what political party you belong to,
[8056.64 --> 8059.44]  maybe Lisp was the more powerful next step or,
[8059.44 --> 8061.36]  or maybe it was like modular or,
[8061.36 --> 8062.40]  or C plus plus,
[8062.50 --> 8062.68]  whatever.
[8062.76 --> 8062.90]  Right.
[8062.98 --> 8063.12]  Right.
[8063.24 --> 8064.06]  But the point is,
[8064.16 --> 8064.62]  yeah,
[8064.94 --> 8066.60]  the point is there was this,
[8066.82 --> 8072.24]  this way that we had been proceeding that was obviously true,
[8072.24 --> 8074.48]  which is that the higher level,
[8074.58 --> 8075.56]  your language where I'm,
[8075.56 --> 8075.58]  I'm,
[8075.58 --> 8076.08]  I'm again,
[8076.12 --> 8080.02]  putting that in air quotes because we still don't exactly know what that means.
[8080.02 --> 8080.28]  Right.
[8080.28 --> 8080.38]  But,
[8080.46 --> 8081.54]  but the higher level of your language,
[8081.54 --> 8083.92]  the more powerful the programmer programmer is,
[8083.92 --> 8084.40]  right.
[8084.40 --> 8088.48]  The more abstracted they are from the details of what's happening.
[8088.60 --> 8088.84]  Yes.
[8088.90 --> 8090.62]  And then the more productive they could be.
[8090.62 --> 8090.98]  Yes.
[8091.58 --> 8094.52]  And so then the problem is we,
[8094.60 --> 8096.64]  we made a conflation in the nineties.
[8096.64 --> 8097.00]  Yeah.
[8097.58 --> 8099.56]  Which is higher level,
[8099.94 --> 8103.62]  which is something about power and expressibility and far from the CPU,
[8103.84 --> 8106.08]  because those things had been correlated.
[8106.08 --> 8110.62]  And so we just started making all these languages that were far from the CPU and
[8110.62 --> 8111.56]  that seemed higher level,
[8111.56 --> 8114.50]  but in ways that are actually a little bit trivial,
[8114.50 --> 8114.94]  like,
[8115.00 --> 8115.28]  okay,
[8115.64 --> 8116.06]  so I could,
[8116.16 --> 8116.90]  I could use,
[8117.10 --> 8119.36]  I could say string plus an integer and like,
[8119.38 --> 8121.86]  it'll convert that to a string and like make,
[8122.04 --> 8123.92]  and that for the first 10 minutes,
[8123.92 --> 8124.92]  when you sit down and doing that,
[8124.96 --> 8126.02]  that seems really cool.
[8126.02 --> 8126.46]  Right.
[8126.60 --> 8126.90]  Yes.
[8126.90 --> 8127.24]  But like,
[8127.24 --> 8131.18]  does that help you solve hard problems or does it get you started faster on
[8131.18 --> 8131.86]  easy problems?
[8131.90 --> 8132.70]  It's the latter one.
[8132.70 --> 8135.92]  And it actually causes hard problems later because you have no type system.
[8135.92 --> 8136.12]  Right.
[8136.42 --> 8136.78]  Like what,
[8137.04 --> 8137.24]  what,
[8137.34 --> 8137.58]  you know,
[8137.64 --> 8138.90]  does this variable exist?
[8139.02 --> 8139.20]  No,
[8139.26 --> 8140.40]  let's make a global variable.
[8140.40 --> 8142.96]  That's the empty string because you typoed somewhere.
[8143.14 --> 8143.46]  And just,
[8143.58 --> 8143.70]  I mean,
[8143.70 --> 8144.62]  you are a math concentrator,
[8144.68 --> 8145.76]  not a computer science concentrator.
[8145.76 --> 8150.60]  So you might not have gone through this kind of youthful experimentation with
[8150.60 --> 8151.64]  operator overloading,
[8151.70 --> 8152.54]  which is what Jonathan is.
[8152.68 --> 8153.44]  And it's where you,
[8153.72 --> 8155.56]  cause the first time you discover operator overloading,
[8155.58 --> 8157.06]  it just seems like awesome.
[8157.70 --> 8161.06]  And then at some point you need to realize that like,
[8161.12 --> 8162.68]  actually this has not made it easier to solve.
[8162.70 --> 8163.26]  Hard problems.
[8163.82 --> 8164.14]  Yeah.
[8164.24 --> 8164.38]  But,
[8164.44 --> 8166.10]  but I would even go more general than that,
[8166.18 --> 8166.82]  that like we,
[8166.88 --> 8169.92]  we had all these kinds of very managed languages at that time.
[8169.92 --> 8170.32]  Right.
[8170.36 --> 8170.90]  So like,
[8170.90 --> 8171.28]  uh,
[8171.32 --> 8171.82]  you know,
[8172.40 --> 8172.64]  uh,
[8172.64 --> 8173.06]  Tickle,
[8173.32 --> 8173.68]  there's one,
[8173.82 --> 8177.34]  that's in the extreme where like everything is a string all the time and
[8177.34 --> 8179.44]  Tickle programs never would work two months later.
[8179.58 --> 8179.80]  Uh,
[8179.80 --> 8180.14]  by the way,
[8180.22 --> 8181.00]  Tickle is alive.
[8181.08 --> 8183.54]  And one of the things that Jess and I have been doing is we've been doing a
[8183.54 --> 8185.00]  lot of low level stuff with,
[8185.12 --> 8188.04]  in terms of the EDA and FPGAs and so on,
[8188.04 --> 8190.82]  where Tickle is alive and well and thriving.
[8190.94 --> 8191.30]  People use that.
[8191.38 --> 8192.04]  Oh my God.
[8192.04 --> 8192.48]  Okay.
[8192.70 --> 8192.88]  No,
[8192.94 --> 8195.52]  we get like software that generates Tickle for the,
[8195.66 --> 8195.80]  the,
[8195.90 --> 8196.04]  the,
[8196.04 --> 8198.16]  for these FPGA synthesis.
[8198.32 --> 8198.54]  It's,
[8198.58 --> 8199.00]  it's insane.
[8199.08 --> 8201.86]  I've never seen more Tickle in my life than I have.
[8201.94 --> 8202.50]  Doesn't that sound good to me?
[8202.50 --> 8202.52]  Yeah.
[8203.12 --> 8203.52]  But you know,
[8203.60 --> 8203.72]  so,
[8203.72 --> 8203.96]  so,
[8204.04 --> 8204.28]  you know,
[8204.32 --> 8205.30]  Pearl from that era.
[8205.42 --> 8205.58]  Yeah.
[8205.82 --> 8206.12]  Python.
[8206.38 --> 8206.54]  Yeah.
[8206.60 --> 8206.78]  Right.
[8206.92 --> 8208.28]  Python's still in heavy use today.
[8208.28 --> 8209.00]  Unlike those,
[8209.24 --> 8209.40]  well,
[8209.44 --> 8210.90]  I guess you're telling me Tickle's in heavy use,
[8210.98 --> 8212.72]  but like Python is still used.
[8212.98 --> 8215.08]  A later variant of Python is used by many,
[8215.16 --> 8215.96]  many programmers.
[8215.96 --> 8216.24]  Right.
[8216.24 --> 8218.68]  So the thing is like,
[8218.78 --> 8219.08]  okay,
[8219.72 --> 8221.64]  how high level is Python really?
[8222.68 --> 8224.56]  It's probably higher level than C.
[8224.68 --> 8225.72]  I would agree with that.
[8225.96 --> 8227.66]  It is high level as people think it is.
[8227.74 --> 8231.64]  Is it high enough level to pay what we are paying to run all these Python programs?
[8231.74 --> 8233.92]  I'm not sure because a part,
[8234.24 --> 8237.12]  there's sort of multiple things that happened in one time at once.
[8237.28 --> 8239.52]  One is this programming language is like,
[8239.82 --> 8240.38]  say it's,
[8240.58 --> 8243.44]  it's a lot slower because it's running interpreted and all this,
[8243.74 --> 8244.34]  all these things.
[8244.42 --> 8248.42]  But also there was like a different kind of community that started happening around that time
[8248.42 --> 8251.60]  where source code was shared much more readily and all of this.
[8251.60 --> 8252.76]  And so part of,
[8252.94 --> 8257.46]  part of what's appealing about those languages is just how fast you can get started because
[8257.46 --> 8258.56]  there's just a lot of code.
[8258.76 --> 8258.88]  Right.
[8259.00 --> 8261.16]  Similarly with JavaScript and all this stuff.
[8261.38 --> 8261.68]  And so.
[8261.80 --> 8262.34]  Batteries included.
[8262.44 --> 8264.18]  Like JavaScript is so weird.
[8264.28 --> 8267.50]  Like that was not ever supposed to be a real programming language and somehow.
[8268.10 --> 8268.50]  No.
[8268.92 --> 8270.86]  It was supposed to just be like,
[8270.92 --> 8273.26]  this is a way you do some simple if statements on a webpage.
[8273.48 --> 8273.78]  Right.
[8273.96 --> 8274.20]  Like that.
[8274.40 --> 8274.58]  Yeah.
[8274.86 --> 8275.04]  Well,
[8275.10 --> 8275.84]  in JavaScript,
[8276.20 --> 8276.46]  I mean,
[8276.52 --> 8279.00]  its birth is in its own kind of metastasis.
[8279.26 --> 8281.20]  It was not supposed to be what it is.
[8281.20 --> 8281.56]  In fact,
[8281.74 --> 8283.54]  Brendan Eich never wrote a book on it.
[8283.72 --> 8284.92]  And this is one of the,
[8285.62 --> 8286.04]  anyway,
[8286.26 --> 8286.40]  yeah.
[8287.46 --> 8287.78]  Yeah.
[8288.32 --> 8288.68]  But,
[8288.74 --> 8288.84]  but,
[8288.84 --> 8290.36]  but the point I was trying to get at is just,
[8290.52 --> 8291.72]  there's two parallel stories,
[8291.78 --> 8291.96]  really.
[8292.02 --> 8293.24]  There's that one story of like,
[8293.30 --> 8294.84]  here's the sequence of programming languages.
[8294.84 --> 8298.54]  And as the programming languages get bigger and slower and farther from the CPU,
[8299.26 --> 8299.72]  that's okay.
[8299.72 --> 8303.68]  Cause CPUs are going to get faster forever and we become much more productive.
[8304.06 --> 8304.30]  Okay.
[8304.42 --> 8305.28]  So are we,
[8305.42 --> 8306.66]  are we more productive in Python?
[8306.88 --> 8307.64]  I'm not sure.
[8307.64 --> 8308.20]  Cause like,
[8309.00 --> 8310.68]  you can keep seeing all these examples,
[8310.88 --> 8314.62]  like Dropbox published this thing in early 2019 about like,
[8314.62 --> 8314.84]  Hey,
[8314.96 --> 8318.20]  here's the story of us migrating from Python two to Python three,
[8318.30 --> 8319.02]  uh,
[8319.26 --> 8323.42]  our 1.2 million line program for our desktop client.
[8323.42 --> 8323.70]  Oh my God.
[8323.70 --> 8324.14]  And I'm like,
[8324.18 --> 8324.40]  wait,
[8324.74 --> 8324.94]  what?
[8325.90 --> 8327.20]  I have so many questions.
[8327.20 --> 8329.38]  My hand is up in the back.
[8329.48 --> 8331.44]  And I don't mean to single out Dropbox because like,
[8331.50 --> 8332.84]  if you just start looking around at this stuff,
[8332.86 --> 8333.74]  you see it everywhere.
[8333.74 --> 8335.64]  You see so much code for all these things.
[8335.64 --> 8336.00]  And I'm like,
[8336.02 --> 8336.20]  wait,
[8336.80 --> 8338.10]  if this language is so high level,
[8338.10 --> 8340.06]  why do you have so much code to do such a small thing?
[8340.22 --> 8340.28]  Yeah.
[8340.36 --> 8340.48]  Right.
[8340.48 --> 8341.96]  And so what you see when you look around,
[8342.08 --> 8343.48]  I claim,
[8343.58 --> 8343.98]  and it's,
[8344.06 --> 8344.28]  you know,
[8344.34 --> 8346.92]  I haven't done a double blind,
[8347.64 --> 8349.42]  triple reproduced study on this,
[8349.50 --> 8349.98]  but like,
[8350.80 --> 8355.18]  it looks to me like the productivity levels of Silicon Valley engineers,
[8355.18 --> 8355.94]  uh,
[8355.94 --> 8359.42]  are historically low actually in terms of what they produce.
[8359.52 --> 8359.72]  Yeah.
[8359.98 --> 8361.90]  Not necessarily in terms of lines of code,
[8362.00 --> 8363.48]  the lines of code is very large,
[8363.48 --> 8365.94]  but in terms of actual functionality produced per engineer,
[8366.10 --> 8366.80]  it's low.
[8366.92 --> 8370.40]  And so something went wrong because everyone always has to be hustling.
[8370.76 --> 8370.98]  I know.
[8371.58 --> 8371.98]  No,
[8372.08 --> 8373.24]  this is the hustling.
[8373.56 --> 8374.74]  And that's fine.
[8374.76 --> 8374.88]  Right.
[8374.88 --> 8378.02]  This is the long shadow of Uber and always be hustling where everyone,
[8378.14 --> 8381.80]  it feels like I need to be productive today and I need to be.
[8381.94 --> 8382.64]  So I need,
[8382.74 --> 8383.08]  it is,
[8383.08 --> 8388.94]  it is better for me to regurgitate code than it is for me to reflect on a hard
[8388.94 --> 8389.24]  problem.
[8389.32 --> 8390.00]  I do think that is,
[8390.08 --> 8391.66]  that is right now very deeply entrenched.
[8391.68 --> 8393.98]  But at some point when you have like an order of magnitude,
[8393.98 --> 8395.32]  more code than you should,
[8395.40 --> 8395.54]  right.
[8395.54 --> 8398.58]  Which is not the order of magnitude that computer scientists are supposed to be
[8398.58 --> 8401.02]  thinking about order of magnitude of like speed or something.
[8401.02 --> 8401.18]  Right,
[8401.18 --> 8401.34]  right,
[8401.34 --> 8401.44]  right,
[8401.44 --> 8401.62]  right.
[8401.74 --> 8403.62]  Order of magnitude of code is,
[8403.66 --> 8404.58]  is a weird concept,
[8404.58 --> 8405.20]  but like,
[8405.98 --> 8406.70]  doesn't,
[8406.78 --> 8408.70]  doesn't that have to kill your company eventually,
[8409.14 --> 8409.30]  right.
[8409.30 --> 8409.42]  Yeah.
[8409.50 --> 8409.64]  In,
[8409.64 --> 8409.78]  in,
[8409.86 --> 8410.94]  on a long enough time horizon,
[8411.08 --> 8411.26]  maybe,
[8411.38 --> 8412.84]  maybe it's just longer than people are thinking,
[8412.84 --> 8415.22]  but so regardless of that,
[8415.32 --> 8416.90]  regardless of the business case for that,
[8416.96 --> 8419.28]  which is something that people will argue with all day,
[8419.32 --> 8419.52]  right.
[8420.20 --> 8424.38]  There are supposed to be people who are the custodians of the field,
[8424.38 --> 8424.84]  right.
[8424.90 --> 8425.20]  We are,
[8425.28 --> 8426.96]  we are the people who really care about computers,
[8427.46 --> 8429.32]  trying to make sure that computers are good.
[8429.32 --> 8430.34]  And like that,
[8430.34 --> 8432.12]  the way we program is good and all this stuff.
[8432.12 --> 8432.34]  Right.
[8432.34 --> 8436.42]  And I don't feel like enough of those people are looking around and saying,
[8436.48 --> 8436.62]  wait,
[8436.64 --> 8443.10]  we're in crazy town right now because this didn't like the claimed benefits of
[8443.10 --> 8445.46]  all these things did not happen.
[8445.96 --> 8446.36]  And,
[8446.44 --> 8447.08]  and why not?
[8447.38 --> 8447.64]  I mean,
[8447.64 --> 8449.52]  maybe they happened 10% or something,
[8449.52 --> 8450.74]  but like we,
[8450.88 --> 8451.88]  and then there's,
[8451.92 --> 8452.90]  there's a whole other thing,
[8452.90 --> 8453.30]  right.
[8453.30 --> 8455.26]  Which is if you go back to something like C,
[8455.94 --> 8456.48]  like I said,
[8456.54 --> 8457.12]  my experience,
[8457.36 --> 8460.64]  my initial user experience of programming in C was horrible because initially it
[8460.64 --> 8461.24]  was KNRC.
[8461.74 --> 8461.94]  And right.
[8462.56 --> 8465.20]  Maybe it was NCC cause this was like 89,
[8465.34 --> 8465.60]  90.
[8466.00 --> 8466.50]  I'm not sure,
[8466.98 --> 8469.06]  but I was learning from the KNRC book.
[8469.10 --> 8471.94]  So you still didn't type procedure prototypes or whatever.
[8472.14 --> 8472.50]  But,
[8472.58 --> 8474.72]  but the point being there were all sorts of dumb crashes.
[8474.72 --> 8475.66]  And then even later,
[8475.78 --> 8476.84]  all sorts of dumb things.
[8476.96 --> 8480.72]  So thing that's very easy to do and see have an uninitialized variable.
[8480.72 --> 8481.22]  I just,
[8481.32 --> 8482.22]  I put it on the stack.
[8482.34 --> 8483.50]  I didn't set it.
[8483.80 --> 8484.72]  And I used it later.
[8484.78 --> 8485.10]  Right.
[8485.44 --> 8485.72]  Okay.
[8486.10 --> 8488.66]  It's like many,
[8488.80 --> 8489.08]  many,
[8489.20 --> 8493.94]  many programmer millennia were wasted debugging that kind of thing.
[8494.02 --> 8494.56]  I'm sure.
[8494.68 --> 8496.56]  Like if you were to compute the amount of time.
[8496.68 --> 8498.02]  And that's an entirely preventable.
[8498.44 --> 8498.72]  Yes.
[8498.80 --> 8499.44]  It's trivial.
[8499.54 --> 8499.78]  Actually.
[8499.90 --> 8500.18]  I mean,
[8500.18 --> 8502.24]  the computer knew what it was doing when it did it.
[8502.34 --> 8504.12]  Solving a hundred percent of that is not,
[8504.16 --> 8505.64]  is not necessarily easy,
[8505.64 --> 8506.00]  but like,
[8506.02 --> 8506.24]  look,
[8506.60 --> 8509.38]  just have a debug build where for local variables,
[8509.38 --> 8512.54]  you have an additional Boolean or something and just add some
[8512.54 --> 8513.96]  instrumentation code that checks.
[8513.96 --> 8515.94]  If you use that and set,
[8516.06 --> 8516.44]  set it,
[8516.52 --> 8516.86]  you know,
[8517.10 --> 8518.72]  so maybe you don't know if it's a sign.
[8518.72 --> 8520.08]  But this is what you do have to like about Rust.
[8520.18 --> 8521.82]  I do like about Rust is that it,
[8521.82 --> 8523.88]  it doesn't actually defer that to,
[8523.88 --> 8525.42]  to a linter.
[8525.90 --> 8526.30]  Yes.
[8526.40 --> 8526.60]  It,
[8526.60 --> 8530.08]  as actually it forces that cognitive load right back on the
[8530.08 --> 8530.42]  programmer.
[8530.54 --> 8530.70]  Well,
[8530.82 --> 8531.08]  well,
[8531.40 --> 8531.66]  so,
[8531.76 --> 8532.32]  so the thing,
[8532.46 --> 8535.42]  the thing that I like about the mood today is we're starting to
[8535.42 --> 8536.86]  realize that these things are problems.
[8536.86 --> 8538.64]  Even if you go back to like Clang or something,
[8538.64 --> 8540.48]  I think they have that kind of thing in there now.
[8540.48 --> 8540.70]  Right.
[8540.80 --> 8544.56]  But the point is we went many decades without that.
[8544.74 --> 8545.10]  Yeah.
[8545.16 --> 8546.56]  Where you're just like,
[8546.80 --> 8548.82]  maybe that's why I don't have that much hair anymore is because I
[8548.82 --> 8549.84]  was pulling my hair out,
[8549.84 --> 8550.32]  you know,
[8550.32 --> 8550.66]  in the,
[8550.72 --> 8552.96]  in the Apollo lab trying to figure out why my C program was
[8552.96 --> 8553.26]  crashing.
[8553.42 --> 8553.50]  Right.
[8553.50 --> 8553.68]  Right.
[8554.12 --> 8554.42]  Um,
[8555.28 --> 8557.12]  a lot of these languages that were designed later,
[8557.70 --> 8559.06]  including probably stuff like Java,
[8559.06 --> 8559.70]  uh,
[8559.70 --> 8561.30]  which I also don't have that much experience with,
[8561.34 --> 8562.52]  but I assume you do having,
[8562.58 --> 8563.52]  having a son history.
[8563.74 --> 8563.78]  No,
[8563.78 --> 8564.08]  no,
[8564.20 --> 8564.50]  no,
[8564.50 --> 8564.84]  no,
[8564.92 --> 8565.20]  no,
[8565.20 --> 8565.24]  no,
[8565.24 --> 8565.26]  no,
[8565.26 --> 8566.28]  my experience.
[8566.54 --> 8566.96]  No,
[8567.06 --> 8570.18]  I was always a Java malcontent and conscientious objector.
[8570.24 --> 8570.54]  Anyway,
[8570.54 --> 8570.78]  though,
[8570.84 --> 8571.30]  a lot of,
[8571.40 --> 8576.38]  a lot of this thing that happened was a reaction to stuff like C,
[8576.64 --> 8576.82]  like,
[8576.82 --> 8577.06]  look,
[8577.18 --> 8579.20]  look how terrible it is to program in these languages.
[8579.20 --> 8579.54]  Right.
[8579.54 --> 8579.78]  Right.
[8579.90 --> 8580.86]  But the vast,
[8580.98 --> 8584.86]  let's say 95% of the unpleasantness was actually completely unnecessary.
[8584.86 --> 8588.52]  If anybody who was making those compilers had,
[8588.62 --> 8590.60]  had cared about the programmer really.
[8590.76 --> 8591.12]  And I,
[8591.12 --> 8592.20]  I think you're right.
[8592.26 --> 8592.48]  And I,
[8592.62 --> 8593.58]  I think that one of the,
[8593.58 --> 8595.20]  the reasons that I,
[8595.32 --> 8596.74]  I was not a Java programmer.
[8596.74 --> 8599.74]  One of the problems I had with Java was it's,
[8600.46 --> 8601.14]  it's assert,
[8601.32 --> 8604.94]  it's assertion that the programmer was too stupid to do memory,
[8605.36 --> 8605.86]  to do,
[8605.96 --> 8608.44]  to have any kind of memory safety and to do memory management.
[8608.60 --> 8609.52]  Memory management's impossible.
[8610.24 --> 8614.14]  So we are going to completely take it out of the programmer's hands.
[8614.40 --> 8614.60]  Yeah.
[8614.86 --> 8615.56]  And what,
[8615.76 --> 8618.74]  and what people ended up who are building sophisticated systems in Java,
[8618.90 --> 8620.48]  ended up spending all their time on memory management,
[8620.62 --> 8623.78]  namely trying to outsmart the garbage collector or feed the garbage collector.
[8623.78 --> 8624.00]  It's like,
[8624.22 --> 8627.80]  do you realize that the problem you're solving is just as hard as malic and free?
[8628.04 --> 8628.16]  Well,
[8628.30 --> 8629.78]  it's actually worse because,
[8629.90 --> 8631.34]  so this happens in games all the time too,
[8631.42 --> 8633.66]  because a lot of people use C sharp or whatever.
[8634.08 --> 8635.30]  And there's like game engines,
[8635.46 --> 8637.64]  like unity that uses C sharp as its primary language.
[8637.64 --> 8639.46]  And I get into these arguments with people like,
[8639.54 --> 8639.66]  look,
[8639.70 --> 8640.32]  you shouldn't use.
[8640.68 --> 8641.02]  And they're like,
[8641.04 --> 8641.14]  no,
[8641.20 --> 8642.18]  garbage collection is fine.
[8642.24 --> 8643.34]  Just do this and that and that.
[8643.34 --> 8645.08]  And you're telling me about memory management.
[8645.08 --> 8645.26]  Yeah,
[8645.26 --> 8645.66]  exactly.
[8646.18 --> 8646.50]  But,
[8646.80 --> 8649.18]  but after you've done all those things,
[8649.18 --> 8651.68]  you still can't really prevent the garbage collector from kicking in.
[8651.78 --> 8652.66]  You never really can,
[8652.88 --> 8655.10]  especially if you use a library somewhere that you don't control.
[8655.10 --> 8655.50]  Right.
[8655.80 --> 8656.12]  And so,
[8656.26 --> 8657.42]  so you've got now a new,
[8657.50 --> 8662.02]  you've got a performance problem and you're doing most or more actually of,
[8662.10 --> 8663.06]  of the same kind of engineering.
[8663.22 --> 8663.62]  And,
[8663.68 --> 8665.06]  and people don't like,
[8665.10 --> 8665.28]  again,
[8665.28 --> 8666.94]  there's not the adult supervision to say,
[8667.00 --> 8667.16]  okay,
[8667.16 --> 8667.46]  wait,
[8667.46 --> 8668.46]  it maybe was a,
[8668.70 --> 8673.08]  it was an interesting idea to say that everything should be garbage collected and
[8673.08 --> 8674.06]  nobody should manage memory,
[8674.16 --> 8675.52]  but it hasn't worked out.
[8675.52 --> 8677.80]  Like somebody has to do the accounting of like,
[8677.90 --> 8680.50]  what did we expect back when we started this idea?
[8680.60 --> 8680.86]  Right.
[8680.86 --> 8684.30]  That the benefit would be what percentage of that benefit do we have now?
[8684.40 --> 8684.52]  Oh,
[8684.54 --> 8685.10]  it's low.
[8685.50 --> 8686.98]  Maybe that wasn't that good of an idea.
[8687.14 --> 8690.28]  We don't have anyone standing around doing that.
[8690.36 --> 8690.84]  So I actually,
[8690.98 --> 8691.14]  so I,
[8691.20 --> 8691.30]  okay.
[8691.30 --> 8692.74]  So I do think people are doing that.
[8692.80 --> 8694.64]  It's just that they're doing it kind of in clusters and clumps.
[8694.66 --> 8698.08]  And I do think that a lot of the rust enthusiasm is people saying,
[8698.18 --> 8702.82]  actually agreeing with that and welcoming a different kind of approach.
[8702.82 --> 8703.14]  Yeah.
[8703.24 --> 8703.34]  So,
[8703.38 --> 8704.20]  so the other,
[8704.38 --> 8706.86]  I don't know whether to go off on this tangent,
[8707.02 --> 8707.86]  but so,
[8708.22 --> 8710.42]  so the garbage collecting collection thing,
[8710.42 --> 8711.10]  of course,
[8711.12 --> 8713.12]  people will argue about garbage collection infinitely,
[8713.12 --> 8718.88]  but one of the reasons why I claim it's really turning out not to have been a good idea is in part,
[8718.98 --> 8719.66]  this thing about,
[8719.82 --> 8723.20]  about memory being so slow relative to CPU cycles right now.
[8723.32 --> 8724.36]  And so you,
[8724.46 --> 8724.82]  of course,
[8725.26 --> 8729.98]  the only real way you can ensure that that's good is by knowing where things are in memory.
[8729.98 --> 8730.20]  Right.
[8730.20 --> 8730.96]  People will say like,
[8730.96 --> 8731.10]  Oh,
[8731.12 --> 8735.56]  our generational collector compact things together sometimes stochastically.
[8735.72 --> 8736.12]  And it's like,
[8736.50 --> 8736.86]  actually,
[8736.94 --> 8737.12]  no,
[8737.18 --> 8739.32]  you can do much better as an actual programmer.
[8739.60 --> 8739.72]  Yeah.
[8739.72 --> 8739.92]  Um,
[8740.68 --> 8741.66]  so that matters a lot,
[8741.66 --> 8743.66]  but also our demands matter a lot.
[8743.68 --> 8744.10]  Like I said,
[8744.12 --> 8745.76]  like games run at two 40 Hertz,
[8745.76 --> 8751.22]  like how much of a GC pause can you afford to take when your frame is four milliseconds?
[8751.46 --> 8751.58]  Right.
[8752.24 --> 8752.94]  It's not that long.
[8753.20 --> 8755.74]  And a memory access is going to be a hundred nanoseconds.
[8756.04 --> 8756.60]  It's like,
[8756.60 --> 8757.76]  this adds up really,
[8757.86 --> 8758.32]  really quickly.
[8758.32 --> 8758.68]  Yeah.
[8758.80 --> 8759.12]  And so,
[8759.22 --> 8759.60]  so I'm,
[8759.60 --> 8759.84]  I'm,
[8760.00 --> 8763.48]  that's one reason why I like the fact that rust went this other direction.
[8763.56 --> 8763.70]  Yeah.
[8763.74 --> 8763.94]  It's like,
[8763.96 --> 8764.22]  okay,
[8764.40 --> 8764.56]  yeah,
[8764.56 --> 8764.96]  good.
[8765.08 --> 8765.40]  Let's,
[8765.52 --> 8766.42]  let's start doing that.
[8766.50 --> 8766.80]  Right.
[8766.90 --> 8767.22]  Now,
[8767.22 --> 8770.06]  the thing that I'm concerned about there is,
[8770.24 --> 8772.72]  so I mentioned this data oriented design thing before.
[8772.82 --> 8773.22]  And,
[8773.30 --> 8779.60]  and one of the tenants of that is that the way that you do things fast is by operating on large groups of things.
[8779.60 --> 8780.70]  You know,
[8780.76 --> 8782.14]  that's just what CPUs are good at.
[8782.24 --> 8784.56]  Like just figure out what you're going to do,
[8784.66 --> 8786.56]  do it on this set of stuff,
[8786.90 --> 8788.10]  move on to the next set of stuff.
[8788.10 --> 8788.34]  Right.
[8788.70 --> 8789.54]  And so collect,
[8789.78 --> 8790.10]  uh,
[8790.10 --> 8794.72]  conceptualizing things as individual actually will make your code slow.
[8794.72 --> 8798.14]  Even if you didn't like spend instructions,
[8798.14 --> 8798.80]  right.
[8798.92 --> 8803.56]  You're missing like the opportunity cost of having had this bundled together with a lot of things.
[8803.60 --> 8804.24]  So for example,
[8804.38 --> 8804.62]  you know,
[8804.66 --> 8805.06]  languages,
[8805.50 --> 8809.58]  some languages are predicated around memory management with like automated reference counting.
[8809.70 --> 8811.46]  That's one of the big things like Swift or whatever,
[8811.46 --> 8812.12]  or the,
[8812.12 --> 8815.46]  or the C plus plus people are all about like R A I I,
[8815.60 --> 8818.42]  which stands for like resource allocation is initialization,
[8818.66 --> 8819.16]  which is,
[8819.24 --> 8820.66]  which is partially about memory,
[8820.66 --> 8822.48]  but also partially about like object state,
[8822.58 --> 8822.82]  whatever.
[8822.82 --> 8824.80]  I'm not going to get into an argument about that,
[8824.90 --> 8826.08]  but I,
[8826.16 --> 8828.90]  I believe that that has very clearly not worked out again,
[8829.10 --> 8831.94]  maybe sounded like an interesting idea for the first year,
[8832.46 --> 8833.88]  really had a lot of problems.
[8833.88 --> 8834.14]  Right.
[8834.56 --> 8837.98]  But when you conceptualize things as individual like that,
[8837.98 --> 8840.20]  you're probably not going to have arrays of them.
[8840.34 --> 8845.68]  You're probably certainly not going to have different arrays with like cross cutting things that those guys care about,
[8845.74 --> 8847.62]  which is what you actually need to do on a CPU.
[8847.96 --> 8849.04]  So in that kind of world,
[8849.04 --> 8855.18]  like automated reference counting is not that useful unless you wrote everything behind the reference count anyway.
[8855.56 --> 8855.74]  Right.
[8855.80 --> 8855.98]  Yeah.
[8855.98 --> 8856.68]  Which is what,
[8856.74 --> 8858.18]  what people are trying not to do.
[8858.26 --> 8858.64]  And so,
[8859.12 --> 8859.54]  so what,
[8859.68 --> 8862.20]  the thing that I try to explain to programmers is like,
[8862.26 --> 8862.46]  look,
[8863.02 --> 8865.94]  this memory speed thing isn't going to change anytime soon.
[8865.98 --> 8866.24]  Yes.
[8866.36 --> 8866.98]  I mean,
[8866.98 --> 8869.34]  the other thing attacks into exactly what you're saying is like Moore's law.
[8869.48 --> 8870.12]  We're done.
[8870.80 --> 8872.10]  We're not done,
[8872.24 --> 8873.32]  but we're done ish.
[8873.42 --> 8873.82]  I mean,
[8873.90 --> 8874.16]  well,
[8874.16 --> 8876.32]  people don't remember back in my first game company,
[8876.48 --> 8878.96]  we bought new computers every six months.
[8878.96 --> 8879.20]  Right.
[8879.20 --> 8881.04]  Because our productivity would be way,
[8881.18 --> 8881.48]  you know,
[8881.98 --> 8882.70]  486,
[8882.78 --> 8883.10]  60,
[8883.22 --> 8883.66]  486,
[8883.72 --> 8883.96]  90,
[8884.04 --> 8884.38]  or whatever,
[8884.52 --> 8886.06]  maybe 66 to 90 or 50.
[8886.22 --> 8887.38]  I think I had a 50 at one point.
[8887.40 --> 8888.40]  I don't remember what the numbers were,
[8888.48 --> 8892.08]  but the point is in six months you could get that much faster.
[8892.28 --> 8892.48]  Yeah.
[8893.20 --> 8893.98]  That's not a thing to do.
[8893.98 --> 8894.12]  No,
[8894.16 --> 8894.26]  no.
[8894.26 --> 8894.64]  And it just,
[8894.70 --> 8895.52]  it changes everything.
[8895.70 --> 8896.22]  It changes everything.
[8896.22 --> 8897.04]  And I think that we,
[8897.16 --> 8904.12]  I think we're going to get back to an era where people are looking at what the actual artifact is,
[8904.14 --> 8904.64]  is generated,
[8904.76 --> 8908.90]  how that actually runs on the metal and how we can have better abstractions that'll,
[8908.90 --> 8909.80]  allow us to,
[8909.92 --> 8912.52]  to better express that in terms of the running artifact.
[8913.74 --> 8914.74]  And so,
[8914.84 --> 8915.04]  I mean,
[8915.08 --> 8915.26]  I'm,
[8915.34 --> 8915.72]  I don't know.
[8915.74 --> 8916.34]  I feel optimistic.
[8916.50 --> 8917.38]  I feel that the,
[8917.90 --> 8924.08]  I feel that we've gone through a bunch of experiments and that you now have,
[8924.08 --> 8924.44]  I think,
[8924.50 --> 8925.34]  cause you were saying that like,
[8925.44 --> 8925.70]  you know,
[8925.72 --> 8926.70]  where's the adult supervision.
[8926.96 --> 8933.82]  I think that we have enough miles on the tires on some of these things that you are now seeing groups of people who are like,
[8933.88 --> 8933.98]  no,
[8934.00 --> 8934.06]  no,
[8934.06 --> 8935.72]  we've done it that way for a long time.
[8935.72 --> 8938.80]  And now actually we've seen all the problems with this.
[8939.32 --> 8940.60]  I hope you're right.
[8940.70 --> 8941.28]  The thing is,
[8941.38 --> 8943.46]  I am relatively vocal about these things lately.
[8943.80 --> 8945.08]  And whenever I say stuff,
[8945.14 --> 8946.76]  especially somewhere like Twitter or whatever,
[8946.94 --> 8947.12]  but,
[8947.18 --> 8948.34]  but even in other venues,
[8948.34 --> 8952.48]  I get a mixture of a lot of people telling me I'm wrong.
[8952.60 --> 8952.94]  Right.
[8953.12 --> 8954.40]  About whatever.
[8954.80 --> 8954.92]  Right.
[8955.36 --> 8958.30]  Twitter is like the worst place for that.
[8958.30 --> 8958.62]  But,
[8958.62 --> 8958.74]  but,
[8958.74 --> 8958.80]  but,
[8958.80 --> 8960.42]  but also then a lot of people saying,
[8960.54 --> 8960.72]  Oh,
[8960.86 --> 8961.28]  you know,
[8961.28 --> 8963.82]  none of that really matters because like,
[8964.36 --> 8964.78]  you know,
[8964.86 --> 8965.58]  my slow,
[8966.28 --> 8969.12]  my slow react application is the future or whatever.
[8969.12 --> 8970.82]  And they might actually be right.
[8971.02 --> 8972.24]  But here's my counter on that.
[8972.24 --> 8974.22]  And then maybe this is just like fundamentally elitist,
[8974.34 --> 8974.78]  but I,
[8974.78 --> 8975.62]  I just,
[8975.72 --> 8977.80]  this is in my marrow is that the,
[8977.90 --> 8986.20]  the number of people that are writing that software that is at the actual brainstem is a smaller number than the people that were write all software.
[8986.20 --> 8988.62]  And the people that we're talking about,
[8988.68 --> 8989.30]  about the,
[8989.42 --> 8991.50]  who are writing the core of game engines,
[8991.50 --> 8996.00]  who are writing system software is it's a smaller number of programmers.
[8996.12 --> 8996.22]  Well,
[8996.26 --> 8996.44]  okay.
[8996.52 --> 8997.14]  Here's okay.
[8997.34 --> 8999.78]  So it's actually okay to ship that cognitive load to them.
[9000.00 --> 9001.34]  There's a real problem though,
[9001.66 --> 9012.16]  which is the following that the people who want to ship the slow react application a little bit do have a point in that like,
[9012.22 --> 9012.86]  what's their alternative?
[9013.00 --> 9013.12]  Okay.
[9013.12 --> 9015.50]  They make a native application that they cross compile for,
[9015.62 --> 9016.94]  for all these different platforms.
[9017.10 --> 9018.50]  We have made that very,
[9018.60 --> 9019.14]  very difficult.
[9019.30 --> 9019.46]  Yes.
[9019.52 --> 9020.22]  We have made it,
[9020.34 --> 9026.54]  we have made it an insane cluster F to do all those things for essentially no reason.
[9026.90 --> 9027.14]  Yeah.
[9027.14 --> 9030.14]  There's just a lot of implementation details that have historically accrued.
[9031.14 --> 9031.90]  And it,
[9032.18 --> 9032.24]  to,
[9032.32 --> 9036.34]  to tell somebody who can just sort of write their high level scripted thing,
[9036.48 --> 9037.10]  like,
[9037.16 --> 9037.24]  oh,
[9037.24 --> 9038.14]  you should do this native.
[9038.92 --> 9039.40]  It's like,
[9039.64 --> 9040.36]  it's a big,
[9040.54 --> 9042.98]  it's a big change for them.
[9043.12 --> 9043.36]  In,
[9043.40 --> 9044.12]  in terms of,
[9044.46 --> 9044.68]  but it's,
[9044.76 --> 9046.00]  in terms of things that aren't that important.
[9046.00 --> 9046.52]  So yeah,
[9046.60 --> 9047.40]  then right.
[9047.50 --> 9047.66]  Exactly.
[9048.44 --> 9050.30]  We need to start fixing that stuff.
[9050.42 --> 9050.58]  Yeah.
[9050.58 --> 9052.58]  And nobody seems very concerned about that.
[9053.48 --> 9053.88]  Right.
[9054.14 --> 9054.44]  Yeah.
[9054.56 --> 9055.64]  I just feel it's going to start.
[9055.72 --> 9059.28]  It's going to start at the kind of the bottom of the stack in terms of like,
[9059.44 --> 9059.82]  possibly.
[9059.98 --> 9060.18]  Right.
[9060.18 --> 9060.50]  So,
[9060.94 --> 9061.34]  you know,
[9061.46 --> 9061.68]  I'm,
[9061.76 --> 9061.96]  I mean,
[9061.98 --> 9062.58]  there's all the,
[9062.58 --> 9064.40]  the bridge builders,
[9064.64 --> 9065.00]  the bridges,
[9065.00 --> 9065.88]  as you pointed out.
[9066.40 --> 9066.68]  Well,
[9066.88 --> 9071.60]  so I think that's a little bit happening a little bit wrong to some degree.
[9071.60 --> 9071.78]  Right.
[9071.78 --> 9072.10]  So there's,
[9072.16 --> 9073.64]  there's the rewrite it in rust people,
[9073.84 --> 9074.90]  which I think,
[9074.98 --> 9075.76]  I think that's a,
[9075.76 --> 9077.24]  a thing that makes sense,
[9077.32 --> 9080.98]  especially when it's very well defined what the thing is.
[9080.98 --> 9081.38]  That's right.
[9081.48 --> 9082.20]  Here's a utility.
[9082.42 --> 9083.56]  We know exactly what it is.
[9083.56 --> 9084.26]  We know what the abstraction is.
[9084.26 --> 9086.84]  We're not going to go through some prototyping phase where we're figuring it.
[9086.88 --> 9089.48]  We just know we want it to be more secure.
[9089.72 --> 9091.00]  We want it to be safe,
[9091.34 --> 9091.74]  secure,
[9092.14 --> 9092.78]  and high performing.
[9092.98 --> 9093.80]  I think that makes.
[9093.84 --> 9094.66]  And we know what it is.
[9095.14 --> 9095.50]  Yes.
[9095.56 --> 9096.54]  That makes a lot of sense.
[9096.88 --> 9101.50]  The problem is the things that we're rewriting in rust is not the right thing.
[9101.88 --> 9102.16]  Yeah.
[9102.22 --> 9102.44]  Okay.
[9102.76 --> 9103.02]  Like,
[9103.34 --> 9104.72]  so Unix is from 1970,
[9104.94 --> 9105.16]  right?
[9105.26 --> 9106.32]  And it grew,
[9106.32 --> 9107.18]  it changed a lot,
[9107.32 --> 9107.78]  but like,
[9108.42 --> 9111.66]  we're still doing 1970 stuff 50 years later.
[9112.04 --> 9113.74]  We like should have a better idea.
[9113.74 --> 9116.44]  And some of the better ideas may be things that we discounted.
[9116.48 --> 9118.24]  So like microkernel was a thing for a while.
[9118.26 --> 9118.44]  Yeah.
[9118.72 --> 9119.44]  And then it likes,
[9119.56 --> 9121.24]  it sort of lost this performance argument.
[9121.38 --> 9123.10]  Like microkernels are going to be slower,
[9123.20 --> 9123.36]  right?
[9123.42 --> 9123.60]  Yeah.
[9123.98 --> 9124.22]  Well,
[9124.70 --> 9125.10]  I mean,
[9125.48 --> 9127.46]  after all this Spectre and Meltdown stuff,
[9127.96 --> 9128.12]  I,
[9128.48 --> 9129.00]  and the,
[9129.06 --> 9130.42]  the point that I always make is like,
[9130.46 --> 9130.60]  look,
[9130.64 --> 9134.46]  there's 173 more of these that like people just haven't found yet.
[9134.46 --> 9134.98]  That's right.
[9135.44 --> 9138.46]  I think now that we're in this age where cores are cheap,
[9138.56 --> 9143.48]  you're just going to have the model be your operating system gets a core and it just lives there.
[9143.58 --> 9143.70]  Yeah.
[9143.74 --> 9144.18]  I think you're right.
[9144.36 --> 9144.74]  And that's,
[9144.82 --> 9146.12]  that's the secure thing.
[9146.42 --> 9146.74]  Yeah.
[9146.74 --> 9147.02]  And,
[9147.12 --> 9148.16]  and why not?
[9148.20 --> 9149.98]  Cause you're not able to use that core anyway,
[9149.98 --> 9152.72]  because we don't know how to make parallel software well enough anyway.
[9152.72 --> 9153.06]  So,
[9153.60 --> 9153.72]  so,
[9153.72 --> 9155.40]  or actually did your point,
[9155.48 --> 9155.64]  the,
[9155.64 --> 9155.82]  the,
[9155.82 --> 9157.90]  the problems are just not parallel enough.
[9157.94 --> 9159.84]  We just don't have enough problems that are parallel enough.
[9159.90 --> 9160.68]  We've got a lot of problems.
[9160.78 --> 9160.98]  I mean,
[9161.02 --> 9162.50]  that's sort of what I mean by that.
[9162.50 --> 9162.86]  Um,
[9162.86 --> 9163.34]  and so,
[9163.34 --> 9166.08]  so then has anyone done that performance comparison?
[9166.32 --> 9166.60]  Like,
[9166.72 --> 9172.58]  is your microkernel really slower if your non-microkernel always lives on a different CPU?
[9172.72 --> 9173.18]  I don't know.
[9173.26 --> 9174.34]  I don't know what that looks like.
[9174.38 --> 9174.52]  Yeah.
[9174.52 --> 9174.84]  Like,
[9174.96 --> 9176.20]  but I'm all,
[9176.26 --> 9177.28]  I'm just very concerned,
[9177.64 --> 9177.82]  you know,
[9177.82 --> 9178.72]  like I'm writing a compiler,
[9178.94 --> 9179.18]  right?
[9179.58 --> 9181.20]  And what are you writing the compiler in?
[9181.44 --> 9181.62]  Well,
[9181.64 --> 9182.24]  it's in C++,
[9182.42 --> 9182.68]  unfortunately.
[9183.14 --> 9184.46]  I couldn't figure it out to be.
[9184.46 --> 9185.10]  Uh,
[9186.90 --> 9187.44]  but you know,
[9187.52 --> 9187.66]  so,
[9187.70 --> 9189.58]  so our compilation model is different,
[9189.66 --> 9189.86]  right?
[9189.94 --> 9190.22]  So,
[9190.76 --> 9190.96]  so,
[9191.06 --> 9191.18]  you know,
[9191.20 --> 9191.36]  this,
[9191.50 --> 9198.18]  the compilation model used by C and by many other languages is that you compile your program in little pieces that are .o files.
[9198.40 --> 9198.54]  Yeah.
[9198.62 --> 9200.24]  And that's important for many reasons.
[9200.24 --> 9200.80]  First of all,
[9200.82 --> 9205.32]  so that you can interoperate with other languages and stuff and you can link those .o files together.
[9205.76 --> 9206.00]  Um,
[9206.00 --> 9207.88]  it's also lets you do incremental compilation,
[9208.36 --> 9208.54]  right?
[9208.68 --> 9210.44]  It also lets you do parallel compilation,
[9210.84 --> 9211.06]  right?
[9211.16 --> 9212.84]  Because you could do all these things,
[9212.88 --> 9213.04]  right?
[9213.32 --> 9213.72]  However,
[9213.72 --> 9216.40]  it lets you do a bad job at all those things.
[9216.40 --> 9217.64]  And some of those things are not necessary.
[9217.64 --> 9218.00]  So,
[9218.12 --> 9218.32]  you know,
[9218.32 --> 9218.52]  like,
[9218.60 --> 9221.12]  like the game that we have right now that we're working on is,
[9221.18 --> 9221.34]  uh,
[9221.34 --> 9222.44]  it's about a hundred thousand lines.
[9222.44 --> 9223.20]  So not giant,
[9223.28 --> 9223.70]  not tiny.
[9223.70 --> 9224.14]  Okay.
[9224.32 --> 9225.58]  With our compiler,
[9225.58 --> 9227.74]  that's running mostly on a single core,
[9227.74 --> 9228.30]  uh,
[9228.30 --> 9230.82]  with beyond C++ level features,
[9230.92 --> 9231.06]  what,
[9231.12 --> 9233.48]  what I consider to be better C++ people might argue,
[9233.56 --> 9235.48]  but whatever we compile that,
[9235.62 --> 9236.64]  that whole game in about,
[9236.64 --> 9237.04]  uh,
[9237.04 --> 9238.32]  right now it's 0.9 seconds.
[9238.44 --> 9239.74]  Cause we got 900 milliseconds.
[9239.94 --> 9240.04]  Yeah.
[9240.08 --> 9240.68]  On one core,
[9241.04 --> 9243.70]  we compile output and output the executable.
[9243.72 --> 9249.06]  Which includes spending a hundred milliseconds on a link step because we output like one object file.
[9249.06 --> 9249.28]  You know,
[9249.34 --> 9252.90]  there's a turbo Pascal manual.
[9253.12 --> 9253.38]  Yeah.
[9253.38 --> 9254.20]  So you're right down there.
[9254.28 --> 9255.96]  I think it's glowing hot to the touch.
[9255.96 --> 9256.32]  Yeah.
[9256.64 --> 9257.60]  Remember turbo Pascal?
[9257.60 --> 9258.04]  I,
[9258.10 --> 9260.22]  I had that in high school and you know,
[9260.26 --> 9262.22]  we never wrote big things on it,
[9262.22 --> 9262.98]  but you know,
[9263.08 --> 9263.70]  it was such a,
[9263.70 --> 9265.42]  it was like running on Apple twos or something.
[9265.42 --> 9266.36]  And yeah.
[9266.56 --> 9266.88]  And,
[9266.88 --> 9267.44]  and here's,
[9267.52 --> 9267.74]  okay.
[9268.08 --> 9268.30]  So,
[9268.40 --> 9269.52]  so among the many rants,
[9269.58 --> 9270.38]  Andrew Schilesberg,
[9270.44 --> 9271.38]  wherever he is right now,
[9271.42 --> 9272.68]  just suddenly feels happy.
[9272.70 --> 9274.28]  He doesn't know why it's being a warm feeling.
[9274.38 --> 9274.60]  It's,
[9274.60 --> 9275.28]  it's insane.
[9275.28 --> 9275.34]  I mean,
[9275.40 --> 9278.22]  so one of the many things that I try to get people to realize is look,
[9278.28 --> 9280.22]  it's insane how long compilers take right now.
[9280.22 --> 9281.26]  Like if they're optimizing,
[9281.40 --> 9284.12]  you kind of have an excuse because you're doing like combinatoric things.
[9284.12 --> 9284.60]  Right.
[9284.92 --> 9286.84]  But like just to compile a program,
[9287.34 --> 9288.34]  like look at like,
[9288.42 --> 9289.84]  how big is that program as text?
[9290.10 --> 9292.16]  And like how many operators per second,
[9292.24 --> 9294.14]  how many operations per second can your CPU do?
[9294.72 --> 9296.68]  And so how long should it take?
[9296.98 --> 9299.64]  And why do we take orders of magnitude longer?
[9299.64 --> 9300.12]  And why,
[9300.20 --> 9301.94]  why does that time keep going up over time?
[9301.94 --> 9302.10]  Now,
[9302.16 --> 9302.40]  again,
[9302.86 --> 9307.00]  some languages like Rust have more of an excuse because you know,
[9307.06 --> 9310.12]  all this correctness checking actually is combinatoric also.
[9310.70 --> 9314.22]  Whether or not you should pay that every time you compile is something I disagree,
[9314.38 --> 9314.46]  but,
[9314.52 --> 9315.30]  but it's got a reason,
[9315.38 --> 9315.54]  right?
[9315.60 --> 9315.74]  Yeah.
[9315.80 --> 9315.94]  But,
[9316.00 --> 9316.38]  but again,
[9316.46 --> 9317.96]  like for most programming languages,
[9318.18 --> 9321.64]  we're compiling these things on insane supercomputers.
[9321.74 --> 9322.74]  Like these things,
[9322.74 --> 9328.54]  my phone is faster than the fastest computer in the world in college that used to do like,
[9328.54 --> 9328.92]  you know,
[9329.42 --> 9332.34]  nuclear simulation stuff.
[9332.34 --> 9332.70]  Right.
[9333.22 --> 9336.40]  And one of my peeves is programmers today don't understand this,
[9336.54 --> 9336.68]  right?
[9336.68 --> 9340.78]  They open an application on windows and it takes three seconds to open.
[9340.92 --> 9341.46]  And like,
[9341.50 --> 9342.90]  they think that that's fine.
[9343.44 --> 9344.68]  And it like doesn't do,
[9344.80 --> 9346.94]  it doesn't put anything on the screen after those three seconds.
[9346.94 --> 9347.22]  Right.
[9347.28 --> 9347.62]  And you're like,
[9347.70 --> 9352.72]  do you have any idea how much your computer can do in three seconds on even one core?
[9352.74 --> 9353.10]  Right.
[9353.34 --> 9356.24]  And so we're in this world where all these design decisions are made the wrong way.
[9356.30 --> 9356.90]  So I'm trying,
[9357.00 --> 9358.28]  I'm trying to simplify this stuff.
[9358.34 --> 9358.46]  Right.
[9358.46 --> 9359.94]  So like you run the compiler,
[9360.14 --> 9363.70]  you certainly have the option of just getting an executable out the other end.
[9363.70 --> 9366.24]  If you don't have any dependencies in other programming languages.
[9366.40 --> 9366.58]  Right.
[9367.18 --> 9368.28]  And it's real fast to do that.
[9368.52 --> 9374.18]  Trying to get that to work with different operating systems is really annoying.
[9374.30 --> 9376.10]  There's just a lot of like friction in the way.
[9376.24 --> 9376.56]  Why?
[9376.78 --> 9377.78]  What's an executable?
[9378.62 --> 9384.00]  It's just a well-defined file format where some things go in certain slots.
[9384.00 --> 9384.36]  Right.
[9384.38 --> 9385.20]  It's just data.
[9385.58 --> 9390.98]  It's like writing an executable file is not that different from writing a zip file or writing a JSON file.
[9391.14 --> 9391.26]  Yep.
[9391.26 --> 9394.96]  But it's become this magic scary thing that nobody is willing to do.
[9395.40 --> 9396.96]  And especially that we can't,
[9397.06 --> 9397.48]  you know,
[9397.98 --> 9398.30]  I don't know.
[9398.44 --> 9400.46]  I guess some people have made inroads on this.
[9400.54 --> 9400.62]  Like,
[9400.68 --> 9402.00]  doesn't the Go compiler,
[9402.62 --> 9403.90]  can't that cross compile?
[9404.32 --> 9404.50]  Yeah.
[9404.50 --> 9405.36]  And generate executables.
[9405.36 --> 9406.00]  It's actually really nice.
[9406.08 --> 9406.32]  Yeah.
[9406.54 --> 9410.74]  The other thing I like about Go is that you can create static binaries like super easily.
[9410.86 --> 9411.08]  Yes.
[9411.16 --> 9411.42]  And so,
[9411.48 --> 9412.90]  so we're going that same direction too.
[9413.00 --> 9415.80]  I think that's something Go got right that is like underappreciated.
[9416.04 --> 9417.82]  And that's what Rust does too.
[9417.98 --> 9418.06]  Right.
[9418.16 --> 9421.32]  Rust generates the binaries that have,
[9421.46 --> 9421.70]  yeah,
[9421.76 --> 9421.84]  no,
[9421.88 --> 9422.52]  I think that that is,
[9422.68 --> 9428.30]  I think dynamic linking may be another one of those like garbage collection kinds of things.
[9428.52 --> 9429.14]  dynamic linking,
[9429.28 --> 9429.90]  but even like,
[9429.96 --> 9430.82]  even static linking.
[9430.92 --> 9431.10]  Right.
[9431.42 --> 9435.32]  So you've got this thing at the back end of how you're assembling your program,
[9435.32 --> 9436.10]  which today,
[9436.86 --> 9437.06]  like,
[9437.12 --> 9438.72]  what does it mean to have a well-structured program?
[9438.90 --> 9439.80]  Like it's namespaced,
[9439.92 --> 9440.38]  interestingly.
[9440.38 --> 9440.82]  Right.
[9441.16 --> 9442.28]  It's got,
[9442.72 --> 9443.08]  I don't know,
[9443.16 --> 9444.18]  you've got overloading,
[9444.24 --> 9444.80]  we've got whatever.
[9445.00 --> 9445.20]  Right.
[9445.84 --> 9452.28]  And you go through the link step and kind of like the first person who uses a name gets it like invisibly or whatever.
[9452.46 --> 9453.06]  Like what?
[9454.14 --> 9457.12]  It's not a good thing to have in the back end of your infrastructure.
[9457.12 --> 9457.46]  Right.
[9457.58 --> 9457.90]  And,
[9457.90 --> 9460.52]  and that's just there.
[9460.86 --> 9462.18]  Like there's problems that I have.
[9462.28 --> 9462.42]  So,
[9462.72 --> 9462.88]  you know,
[9462.88 --> 9464.06]  we have hygienic macros.
[9464.30 --> 9464.50]  Right.
[9464.68 --> 9466.46]  And so in principle,
[9466.64 --> 9467.56]  if you're in the debugger,
[9467.76 --> 9469.28]  you can step into your macro.
[9469.28 --> 9469.60]  Right.
[9469.60 --> 9470.58]  And you see,
[9470.76 --> 9470.90]  okay,
[9470.96 --> 9471.18]  good.
[9471.48 --> 9471.70]  Right.
[9471.76 --> 9471.92]  You,
[9471.98 --> 9472.74]  you would like that.
[9472.80 --> 9472.98]  Right.
[9473.42 --> 9473.82]  Problem.
[9474.38 --> 9475.70]  How do you really put that in,
[9475.86 --> 9478.30]  in the existing debug format?
[9478.44 --> 9479.96]  There might be a way to do it in,
[9479.96 --> 9481.00]  in dwarf actually,
[9481.08 --> 9482.00]  because dwarf so insane.
[9482.12 --> 9482.94]  But the problem is,
[9482.94 --> 9484.30]  the problem is,
[9484.30 --> 9485.04]  if I,
[9485.04 --> 9485.06]  if I,
[9485.06 --> 9486.60]  if I set a break point in that macro,
[9486.72 --> 9486.94]  right?
[9487.00 --> 9487.36]  Like,
[9488.06 --> 9491.30]  I don't know where I came from now because it's on,
[9491.36 --> 9492.78]  it's on like the stack.
[9492.96 --> 9493.18]  Right.
[9494.34 --> 9494.58]  It's,
[9494.58 --> 9496.54]  it's in the stack frame of the outer function,
[9496.66 --> 9498.68]  but I've identified that macro expansion.
[9499.76 --> 9501.40]  It's maybe a hard problem to explain,
[9501.48 --> 9503.78]  but the point is I can identify this.
[9504.10 --> 9507.70]  I can identify it as being in the macro or as in the function that called the macro,
[9507.82 --> 9509.00]  but kind of not both.
[9509.08 --> 9509.42]  Right.
[9509.42 --> 9509.66]  You know,
[9509.82 --> 9510.06]  right.
[9510.18 --> 9510.90]  I don't know if there's,
[9510.98 --> 9512.96]  I don't know dwarf well enough to know if there's a way to do that,
[9513.02 --> 9514.26]  but these,
[9514.32 --> 9515.06]  these things are just,
[9515.16 --> 9518.04]  they're very complicated and they're very old.
[9518.56 --> 9522.28]  And if you were to design things from scratch today,
[9522.28 --> 9523.92]  they wouldn't look like what we have.
[9524.38 --> 9528.30]  And yet there aren't very many people willing to change the things that we have.
[9528.36 --> 9528.62]  Right.
[9528.80 --> 9529.36]  And again,
[9529.44 --> 9529.54]  I,
[9529.70 --> 9530.18]  you know,
[9530.22 --> 9530.50]  back,
[9530.56 --> 9531.26]  back to the point.
[9531.72 --> 9532.04]  Yeah.
[9532.04 --> 9534.14]  The point that I brought up earlier about the,
[9534.16 --> 9536.52]  the point of an operating system is to help you run programs,
[9536.62 --> 9536.84]  right?
[9537.74 --> 9539.12]  If you install Linux today,
[9539.42 --> 9540.68]  it's insane.
[9540.82 --> 9542.02]  I have no other word than insane.
[9542.10 --> 9542.20]  Well,
[9542.22 --> 9542.86]  also windows,
[9543.00 --> 9543.26]  right?
[9543.62 --> 9544.26]  It's insane.
[9544.68 --> 9547.28]  Like my windows machine wants to reboot itself every week.
[9547.36 --> 9547.76]  Right.
[9548.02 --> 9549.22]  To install updates.
[9549.38 --> 9549.54]  Yeah.
[9549.58 --> 9550.30]  What are the updates?
[9550.42 --> 9550.52]  Well,
[9550.52 --> 9553.40]  they're mostly to software that I wish wasn't on my machine anyway.
[9553.66 --> 9553.88]  Right.
[9554.16 --> 9554.72]  Candy crush.
[9554.92 --> 9557.72]  I can't get rid of candy crush on a windows machine for like the life of me.
[9557.76 --> 9559.40]  It's like this demon that keeps coming back.
[9559.40 --> 9566.24]  I had to write a script to be a scheduled job on windows to get rid of candy crush because it
[9566.24 --> 9567.00]  would come back.
[9567.10 --> 9568.82]  Like it just runs every so often.
[9568.82 --> 9569.46]  But like we've,
[9569.54 --> 9570.92]  we've ended up in this world where like,
[9570.98 --> 9571.40]  that's,
[9571.72 --> 9574.22]  that's the minimal thing that you need on your computer to run.
[9574.58 --> 9576.08]  Candy crush is a load bearing.
[9576.44 --> 9576.66]  Yeah.
[9576.96 --> 9577.16]  Yeah.
[9577.22 --> 9577.38]  No,
[9577.52 --> 9580.04]  it seems load bearing because it keeps coming back.
[9580.08 --> 9581.40]  It's like absolutely insane.
[9582.08 --> 9582.48]  Yeah.
[9582.54 --> 9582.84]  But like,
[9582.92 --> 9583.26]  how,
[9584.02 --> 9584.64]  how do you,
[9584.88 --> 9585.30]  and meanwhile,
[9585.42 --> 9585.56]  okay.
[9585.56 --> 9585.86]  so we,
[9585.86 --> 9585.88]  so we,
[9585.88 --> 9587.38]  so we have this windows that by the way,
[9587.38 --> 9591.42]  has like probably three nines of reliability built in now because it wants to,
[9591.60 --> 9597.20]  nobody even knows what nines are anymore because we've given up on that idea of things being that reliable,
[9597.20 --> 9599.86]  except maybe in corners of enterprise software.
[9600.46 --> 9602.92]  And at the end of the day,
[9602.92 --> 9610.00]  I still can't like render something full screen in windows without other windows,
[9610.00 --> 9613.36]  like running to the other monitor or like flickering back and forth.
[9613.36 --> 9620.98]  And like things are still super broken or like windows handling of high resolution displays is still super broken.
[9620.98 --> 9621.40]  And,
[9621.40 --> 9623.64]  and all this,
[9623.74 --> 9627.50]  so all this complexity hasn't helped us solve the actual problems that we have.
[9627.50 --> 9627.68]  It hasn't.
[9627.86 --> 9633.12]  So here's my hopeful note for the future is that I think that the abstractions,
[9633.18 --> 9633.32]  I mean,
[9633.32 --> 9633.94]  you look at Unix,
[9634.00 --> 9634.22]  a very,
[9634.22 --> 9635.56]  a very persistent abstraction.
[9636.46 --> 9637.68]  And I do think that there are,
[9637.74 --> 9638.80]  there are other abstractions.
[9638.88 --> 9640.58]  I think that Rust is a very important development.
[9640.96 --> 9641.78]  I think that there are,
[9641.84 --> 9642.98]  there are other important,
[9642.98 --> 9644.60]  the sequel is a very important abstraction.
[9644.74 --> 9650.60]  We develop these very important abstractions and the history for behind each of those abstractions,
[9650.70 --> 9664.04]  almost invariably is someone who has started to deeply question the complexity and takes a katana to it and slices through the complexity and delivers an underlying simplicity.
[9664.18 --> 9664.76]  So I think it's like,
[9665.06 --> 9665.70]  and then we,
[9666.24 --> 9668.20]  the nature of software is such that we can,
[9668.20 --> 9669.00]  that idea,
[9669.26 --> 9672.96]  it takes one person or a small group of people to have,
[9672.98 --> 9676.52]  the guts and the stamina and the resilience to do that.
[9676.60 --> 9681.10]  And the way that they do that is leverageable by a much broader cross section of people.
[9681.60 --> 9681.66]  Yeah.
[9681.88 --> 9682.16]  Can I,
[9682.22 --> 9682.46]  can I,
[9682.54 --> 9685.56]  I'm going to throw out another stone that'll get people mad at me.
[9685.70 --> 9685.90]  Right.
[9686.32 --> 9689.20]  But so in terms of all this complexity that needs to be collapsed,
[9689.20 --> 9689.42]  right.
[9689.42 --> 9690.84]  I think everything has its time.
[9690.84 --> 9692.26]  The thing,
[9692.90 --> 9693.10]  so,
[9693.14 --> 9693.58]  so the,
[9693.58 --> 9693.78]  the,
[9693.78 --> 9694.54]  what's next?
[9694.76 --> 9694.88]  I,
[9695.00 --> 9695.20]  I,
[9695.20 --> 9695.96]  what are you going after?
[9696.08 --> 9696.24]  I,
[9696.24 --> 9696.52]  I,
[9696.52 --> 9696.66]  I,
[9696.66 --> 9696.88]  well,
[9696.88 --> 9697.20]  like the,
[9697.20 --> 9698.18]  the Unix philosophy,
[9698.32 --> 9698.80]  for example,
[9698.86 --> 9701.58]  which has been inherited by windows to some degree,
[9701.68 --> 9702.26]  even though it's,
[9702.34 --> 9703.46]  it's a different operating system,
[9703.46 --> 9703.70]  right.
[9703.78 --> 9705.32]  The Unix philosophy of,
[9705.44 --> 9708.86]  you have all these small programs that you put together in tool like ways,
[9708.86 --> 9709.78]  I think is wrong.
[9709.78 --> 9710.54]  Um,
[9710.64 --> 9710.76]  yeah,
[9710.84 --> 9710.98]  no,
[9711.04 --> 9712.10]  it's wrong for today.
[9712.30 --> 9712.46]  Yeah.
[9712.46 --> 9714.58]  And it was also picked up by plan nine as well.
[9714.68 --> 9714.84]  Right.
[9715.32 --> 9715.80]  And so.
[9716.68 --> 9717.56]  And microservices,
[9717.68 --> 9718.46]  microservices aren't,
[9718.58 --> 9719.46]  especially the Unix philosophy.
[9719.70 --> 9719.94]  Yeah.
[9720.08 --> 9720.20]  I,
[9720.44 --> 9721.58]  so the Unix philosophy,
[9721.86 --> 9723.86]  I've got a complicated relationship with Unix philosophy.
[9724.16 --> 9724.44]  Yeah.
[9725.10 --> 9725.38]  Jess,
[9725.40 --> 9726.40]  I imagine you do too,
[9726.62 --> 9727.10]  where it's like,
[9727.18 --> 9727.78]  I love it.
[9728.54 --> 9729.86]  I love it when I'm,
[9730.06 --> 9730.20]  I,
[9730.26 --> 9731.38]  I love a pipeline.
[9731.58 --> 9733.90]  I love it when I want to do something that is ad hoc,
[9734.04 --> 9736.08]  that is not designed to be permanent.
[9737.10 --> 9737.88]  Cause it allows,
[9737.98 --> 9738.14]  I mean,
[9738.24 --> 9739.76]  and you were getting this earlier about,
[9739.78 --> 9741.94]  about rust for video games and why it,
[9742.00 --> 9744.06]  maybe it's not a fit in terms of that ability to,
[9744.06 --> 9745.04]  to prototype quickly.
[9745.48 --> 9746.12]  Unix philosophy.
[9746.26 --> 9748.00]  Great for ad hoc prototyping.
[9748.02 --> 9748.22]  Yeah.
[9748.28 --> 9748.68]  Sort of.
[9749.26 --> 9750.10]  Bash one-liners.
[9750.24 --> 9750.88]  Bash one-liners.
[9750.96 --> 9752.02]  As long as what you're doing,
[9752.02 --> 9754.78]  like is expressible as grep or something.
[9754.94 --> 9755.08]  Yeah.
[9755.08 --> 9755.60]  Yeah.
[9755.60 --> 9755.78]  Yeah.
[9755.78 --> 9755.96]  Yeah.
[9755.96 --> 9756.02]  Yeah.
[9756.18 --> 9756.32]  But,
[9756.32 --> 9757.86]  but then doing that is great.
[9758.08 --> 9759.60]  Just don't make that load bearing.
[9759.82 --> 9759.94]  Right.
[9760.02 --> 9760.18]  Well,
[9760.28 --> 9760.44]  so,
[9760.52 --> 9762.02]  so as somebody who likes rust,
[9762.12 --> 9762.34]  right.
[9762.70 --> 9763.00]  Um,
[9763.54 --> 9765.12]  you probably agree with me about certain things.
[9765.12 --> 9765.32]  Like,
[9765.36 --> 9765.50]  look,
[9765.52 --> 9769.08]  if you're going to write a substantial program.
[9769.28 --> 9769.58]  Yes.
[9769.58 --> 9769.86]  Right.
[9769.94 --> 9771.08]  That needs to work.
[9771.26 --> 9771.54]  Yes.
[9771.60 --> 9772.22]  For a long time.
[9772.52 --> 9775.28]  And it's doing sophisticated things as we often want to do today.
[9775.38 --> 9775.56]  Yeah.
[9775.62 --> 9777.32]  You want your data to be well-defined.
[9777.44 --> 9777.58]  Yeah.
[9777.62 --> 9778.14]  And structured.
[9778.34 --> 9780.66]  You want to understand when you're dereferencing data,
[9780.66 --> 9782.06]  that it's the right type.
[9782.22 --> 9782.42]  Yeah.
[9782.42 --> 9782.60]  Right.
[9782.74 --> 9782.90]  Yeah.
[9783.02 --> 9783.22]  Yeah,
[9783.22 --> 9783.52]  exactly.
[9783.66 --> 9785.48]  You want to be able to move data around quickly.
[9785.60 --> 9786.14]  You want to be able to,
[9786.26 --> 9787.16]  so all these things,
[9787.20 --> 9787.40]  right.
[9787.40 --> 9788.04]  Um,
[9788.54 --> 9791.16]  that's what it looks like when you have a,
[9791.16 --> 9796.58]  a strongly typed programming language that calls out to libraries or whatever.
[9796.58 --> 9797.00]  I don't know,
[9797.18 --> 9798.50]  crates in rust or whatever,
[9798.50 --> 9800.14]  whatever people call things these days,
[9800.14 --> 9800.96]  um,
[9801.30 --> 9802.50]  to do jobs.
[9802.50 --> 9802.80]  So,
[9802.92 --> 9803.44]  so it's,
[9803.44 --> 9809.66]  that is the thing that we have discovered about how to put together a thing that does
[9809.66 --> 9812.88]  technical work at a large scale that does a complicated job.
[9812.88 --> 9813.14]  Right.
[9813.14 --> 9815.26]  So all this Unix stuff is like,
[9815.30 --> 9816.62]  it's the sort of the same thing,
[9816.62 --> 9818.38]  except instead of libraries or crates,
[9818.40 --> 9819.54]  you just have programs.
[9819.54 --> 9824.52]  And then you have like your other program that calls out to the other programs and pipes them
[9824.52 --> 9824.86]  around,
[9824.86 --> 9830.18]  which is as far from strongly typed as you can get is like data coming in a stream on a,
[9830.18 --> 9830.82]  on a pipe.
[9831.12 --> 9831.16]  Right.
[9831.68 --> 9833.80]  Other things about Unix that seemed cool.
[9834.16 --> 9834.44]  Well,
[9834.52 --> 9836.20]  and the last point there is just to say,
[9836.30 --> 9839.78]  so we've got two levels of redundancy that are doing the same thing.
[9840.36 --> 9840.80]  Why?
[9841.00 --> 9842.50]  Like get rid of that.
[9842.70 --> 9842.90]  Right.
[9842.90 --> 9843.42]  Do the,
[9843.42 --> 9844.18]  do the one that works.
[9844.18 --> 9846.12]  And then if you want a looser version of that,
[9846.84 --> 9851.94]  maybe you can have a version of a language that just doesn't type check and use that for your
[9851.94 --> 9852.54]  crappy spell.
[9853.06 --> 9853.42]  Well,
[9853.44 --> 9853.54]  no,
[9853.54 --> 9854.66]  I think we already have that.
[9854.70 --> 9855.14]  That's Ock.
[9855.24 --> 9855.40]  I mean,
[9855.40 --> 9856.18]  this is what I love about like,
[9856.22 --> 9857.00]  go use Ock if,
[9857.06 --> 9857.76]  if you need Ock.
[9857.96 --> 9858.32]  Yeah.
[9858.68 --> 9859.40]  Something like that.
[9859.54 --> 9859.56]  But,
[9859.56 --> 9860.38]  but I love Ock.
[9860.48 --> 9860.96]  I love Ock.
[9861.06 --> 9861.24]  I just,
[9861.36 --> 9861.92]  I'm not gonna,
[9862.06 --> 9864.68]  I'm not gonna write a hundred lines in Ock.
[9864.98 --> 9865.26]  Oh God,
[9865.36 --> 9866.10]  who would do that?
[9866.20 --> 9866.36]  Right.
[9866.38 --> 9866.68]  Exactly.
[9866.80 --> 9867.04]  Just like,
[9867.06 --> 9867.42]  it's got to,
[9867.46 --> 9867.74]  it's a,
[9867.92 --> 9868.36]  there's a,
[9868.36 --> 9869.36]  there's a bit of a right to a better job.
[9872.90 --> 9872.98]  Pearl,
[9873.12 --> 9875.40]  like put all the mess in Pearl and then it just lives there.
[9875.48 --> 9875.56]  Oh God.
[9875.64 --> 9875.80]  Right.
[9876.28 --> 9876.52]  But,
[9876.52 --> 9879.02]  but Pearl became a super fun site.
[9879.24 --> 9879.52]  It became,
[9879.78 --> 9883.14]  it's like we dumped so much crap into Pearl that it became uninhabitable.
[9883.14 --> 9883.88]  It went too far.
[9884.28 --> 9885.30]  It definitely went too far.
[9885.74 --> 9885.84]  But,
[9885.88 --> 9886.46]  but so that's,
[9886.48 --> 9888.54]  that's levels of redundancy that like,
[9888.72 --> 9890.06]  where one of the levels is,
[9890.18 --> 9891.32]  is not very sound,
[9891.80 --> 9893.76]  but adds a great deal of complexity.
[9893.76 --> 9894.16]  Right.
[9894.22 --> 9894.40]  And,
[9894.44 --> 9895.76]  and so maybe we should put those together.
[9895.76 --> 9897.54]  But another thing about Unix that like,
[9898.10 --> 9899.28]  this is maybe getting more,
[9899.34 --> 9900.10]  more picky,
[9900.22 --> 9900.36]  but,
[9900.46 --> 9901.04]  but you know,
[9901.04 --> 9903.66]  one of the cool philosophical things was like,
[9904.04 --> 9904.28]  you know,
[9904.32 --> 9905.04]  file descriptors,
[9905.08 --> 9905.26]  right?
[9905.30 --> 9905.60]  Like,
[9905.72 --> 9905.94]  Hey,
[9906.74 --> 9910.92]  this thing could be a file on disc or I could be talking over the network.
[9910.92 --> 9914.70]  Isn't it so totally bad-ass that those are both the same thing.
[9914.86 --> 9916.58]  And like in a nerd kind of way,
[9916.64 --> 9916.82]  like,
[9916.90 --> 9917.00]  sure,
[9917.06 --> 9917.64]  that's great.
[9917.78 --> 9919.42]  But actually when I'm writing software,
[9919.64 --> 9924.22]  I kind of need to know whether I'm talking over the network or to a file.
[9924.22 --> 9927.00]  And I'm going to do very different things in both of those cases.
[9927.18 --> 9927.42]  Yeah.
[9927.56 --> 9927.92]  And,
[9927.92 --> 9935.58]  and so I would actually like them to be different things because I want to know what things that I could do to one that I'm not allowed to do to another and so forth.
[9936.26 --> 9936.62]  Yeah.
[9936.62 --> 9938.86]  And I am of such mixed mind because it's like,
[9938.94 --> 9944.40]  because it is a powerful abstraction when it works and when it breaks,
[9944.44 --> 9945.04]  it breaks badly.
[9945.46 --> 9945.68]  Yeah.
[9945.68 --> 9946.02]  It's just,
[9946.10 --> 9946.62]  I think,
[9946.70 --> 9949.96]  I think it was more powerful when it was conceived.
[9950.08 --> 9950.26]  Right.
[9950.26 --> 9951.24]  I think for the time,
[9951.32 --> 9951.58]  you know,
[9951.62 --> 9952.32]  1970s,
[9952.34 --> 9953.00]  early eighties,
[9953.18 --> 9955.14]  I think that was probably the right thing.
[9955.38 --> 9955.58]  Right.
[9955.58 --> 9955.98]  Um,
[9955.98 --> 9957.48]  I don't think it's the right thing today.
[9957.52 --> 9964.18]  And the problem is nobody is willing to question things at that low of a level because I think they just perceive a,
[9964.30 --> 9967.64]  it'll be way too much work to try to build a new thing from scratch.
[9967.64 --> 9969.20]  That's not like other people's things.
[9969.20 --> 9969.72]  And then B,
[9969.80 --> 9970.38]  once I do that,
[9970.44 --> 9971.20]  nobody will use it.
[9971.24 --> 9972.32]  And so my life will be wasted.
[9972.32 --> 9972.66]  Right.
[9973.08 --> 9975.12]  And the problem is we need people who are brave.
[9975.92 --> 9976.18]  Yes.
[9976.20 --> 9976.46]  We need,
[9976.50 --> 9977.34]  we need people to go,
[9977.44 --> 9981.06]  we need like the 300 Spartans or whatever to go out and like do some things.
[9981.06 --> 9982.84]  We need people crazy enough to start a computer company.
[9983.34 --> 9983.66]  Yeah.
[9983.86 --> 9984.10]  No,
[9984.16 --> 9984.56]  I think you're right.
[9984.60 --> 9985.20]  I think that we need,
[9985.24 --> 9985.80]  we need,
[9985.94 --> 9990.38]  we need people who are going to be courageous with respect to abstractions.
[9990.56 --> 9994.80]  And understand also that you can work for an abstraction that,
[9994.88 --> 9996.70]  that may have limited utility,
[9996.70 --> 9998.08]  but that utility can be important.
[9998.16 --> 10000.44]  That can be an important subsection.
[10000.44 --> 10000.90]  I mean,
[10000.90 --> 10003.20]  it doesn't need to be everything to everybody.
[10003.32 --> 10003.62]  I think that,
[10003.70 --> 10003.88]  in fact,
[10003.90 --> 10005.32]  I think that that era needs to end.
[10005.54 --> 10006.36]  I think that we,
[10006.92 --> 10007.24]  we,
[10007.36 --> 10010.52]  and we've oscillated a couple of times into this where everything was gonna be
[10010.52 --> 10011.08]  written in Java.
[10011.30 --> 10012.28]  And then we realized like,
[10012.36 --> 10012.84]  actually shit,
[10012.86 --> 10013.50]  that's a bad idea.
[10014.04 --> 10015.08]  Some things should be written in Java,
[10015.16 --> 10016.22]  but a lot of other things shouldn't be.
[10016.60 --> 10018.14]  And right now I think it's like,
[10018.16 --> 10018.48]  we,
[10018.60 --> 10023.16]  we need to accept that different domains are going to have different,
[10023.36 --> 10024.70]  they're going to be expressed in different languages.
[10024.70 --> 10025.86]  They may have different systems,
[10025.86 --> 10029.40]  but it's not an excuse for this kind of spurious incompatibility.
[10029.40 --> 10030.62]  So I would like to solve this.
[10030.78 --> 10031.02]  So,
[10031.14 --> 10031.34]  you know,
[10031.42 --> 10032.92]  I didn't like Java when it came out,
[10032.98 --> 10034.32]  I never really programmed in it,
[10034.74 --> 10035.26]  but like,
[10035.58 --> 10035.90]  again,
[10036.00 --> 10036.72]  because the,
[10036.76 --> 10040.86]  the people who want to do their react applications kind of have a point,
[10041.20 --> 10044.00]  I would like to figure out how do we actually solve that?
[10044.06 --> 10044.20]  Like,
[10044.28 --> 10047.16]  what is the most technically sound thing that we could do?
[10047.28 --> 10047.66]  Yeah.
[10047.76 --> 10051.26]  Where I could actually copy my program to another operating system.
[10051.76 --> 10054.42]  And let's say it's not magical.
[10054.44 --> 10054.80]  Like,
[10054.86 --> 10058.28]  let's say I even have to if def around operating specific things.
[10058.28 --> 10059.94]  And somehow that gets compiled into it.
[10059.94 --> 10060.18]  Right.
[10060.74 --> 10061.20]  But like,
[10061.24 --> 10062.06]  then it runs,
[10062.12 --> 10063.98]  but it's like not as managed as Java,
[10063.98 --> 10065.98]  but maybe it maps to CPU instructions,
[10066.76 --> 10066.94]  you know,
[10067.04 --> 10069.00]  like if we did something like that,
[10069.26 --> 10070.44]  it would remove,
[10070.62 --> 10071.24]  and I'm not,
[10071.28 --> 10073.20]  I'm not actually advocating this as I'm saying it.
[10073.24 --> 10073.52]  I'm just,
[10073.62 --> 10074.64]  I'm just saying like,
[10075.14 --> 10077.10]  nobody's really taking that that seriously.
[10077.10 --> 10077.56]  That like,
[10077.58 --> 10077.80]  maybe,
[10077.80 --> 10079.38]  maybe Java was not the right thing,
[10079.38 --> 10084.54]  but maybe something near proximal to Java would be tremendously better.
[10084.78 --> 10084.96]  Yeah.
[10084.96 --> 10086.88]  It would allow us to have something very low level,
[10087.14 --> 10087.32]  like,
[10087.36 --> 10088.02]  like things change.
[10088.02 --> 10088.24]  Right.
[10088.48 --> 10093.06]  So like being exactly optimal in terms of CPU instruction count is not that important.
[10093.30 --> 10093.56]  Right.
[10093.68 --> 10094.66]  So like all this,
[10094.72 --> 10097.86]  like worrying really hard about jitting something into an optimal thing,
[10097.86 --> 10100.24]  not actually going to get you that much mileage today.
[10100.24 --> 10100.64]  Right.
[10101.20 --> 10101.68]  But like,
[10101.98 --> 10102.10]  Oh,
[10102.10 --> 10105.36]  we've got some byte code that we know is pretty close to arm and pretty close to
[10105.36 --> 10105.82]  x86.
[10105.82 --> 10109.38]  And we can sort of like map it in the last stage is like,
[10109.38 --> 10110.00]  you know,
[10110.58 --> 10111.58]  that's not the worst thing.
[10111.58 --> 10112.12]  I mean,
[10112.12 --> 10114.80]  I would prefer to ship something that I compiled directly,
[10114.92 --> 10115.28]  but like,
[10115.34 --> 10120.24]  if that is what enables people to copy a program from one computer to another,
[10120.46 --> 10126.02]  without having to have an installer and downloading dependencies and then have it like not work
[10126.02 --> 10126.78]  correctly anyway,
[10126.78 --> 10127.54]  after all that,
[10127.94 --> 10129.80]  like we need to start thinking about that.
[10129.94 --> 10130.86]  We really do.
[10131.50 --> 10132.38]  And nobody is.
[10132.60 --> 10133.50]  And I don't know.
[10133.98 --> 10134.08]  Well,
[10134.20 --> 10134.26]  I,
[10134.36 --> 10135.78]  I think that I,
[10135.92 --> 10136.78]  so I do think again,
[10136.78 --> 10137.78]  I think that,
[10137.82 --> 10144.50]  that this it's these kinds of problems from which are born great and revolutionary ideas.
[10144.78 --> 10145.98]  So I'm hoping that you're,
[10146.04 --> 10148.22]  I'm that Jai,
[10148.32 --> 10148.74]  Jai,
[10148.94 --> 10149.26]  whatever.
[10149.40 --> 10151.64]  I'm hoping that that's going to close beta start soon,
[10151.66 --> 10153.28]  but I'm hoping that's going to get out there.
[10153.48 --> 10155.02]  I don't know what the timing for that will be.
[10155.06 --> 10156.36]  It's going to start small and it'll,
[10156.52 --> 10157.70]  it'll grow over time.
[10157.78 --> 10157.96]  Yeah.
[10157.96 --> 10158.42]  That's great.
[10158.50 --> 10159.60]  I think that that's terrific.
[10160.46 --> 10162.82]  This has been an amazing conversation.
[10163.22 --> 10163.56]  I don't,
[10163.66 --> 10164.18]  I mean,
[10164.18 --> 10165.92]  I feel like there's so much we didn't say,
[10165.92 --> 10166.54]  but that's fine.
[10166.54 --> 10167.30]  The,
[10167.68 --> 10170.46]  and so many more rants to be had,
[10170.66 --> 10171.20]  but no,
[10171.24 --> 10172.06]  I think this has been,
[10172.60 --> 10173.38]  it's been great.
[10173.80 --> 10174.42]  Thanks for having me.
[10174.44 --> 10174.64]  Oh,
[10174.72 --> 10175.76]  we cannot thank you enough.
[10175.86 --> 10179.96]  This has been so much fun and it's so great to,
[10180.08 --> 10180.48]  I have to say,
[10180.52 --> 10185.16]  speak to someone who is not doing computing for its own sake,
[10185.28 --> 10192.74]  but actually really focused on delivering something to an end user is really terrific and refreshing.
[10193.14 --> 10195.24]  And yet still having that,
[10195.24 --> 10196.42]  that deep system perspective.
[10196.54 --> 10198.10]  It's so in the same way that,
[10198.26 --> 10200.34]  that having to code directly to metal,
[10200.84 --> 10202.70]  there's an element of reality there.
[10202.76 --> 10202.96]  Yeah.
[10203.26 --> 10206.02]  Caring what something looks like to the end user is like a different,
[10206.08 --> 10208.04]  it's a different wall of the room of reality.
[10208.04 --> 10208.28]  Yeah.
[10208.28 --> 10211.10]  And like seeing both of those walls at once is useful.
[10211.10 --> 10211.58]  I think.
[10211.66 --> 10212.50]  It's very useful.
[10212.50 --> 10213.94]  And it's been a great conversation.
[10214.18 --> 10214.58]  Jonathan,
[10214.78 --> 10216.00]  thank you so much for joining us today.
[10216.00 --> 10216.24]  I don't.
[10216.32 --> 10216.66]  Thank you.
[10216.86 --> 10217.14]  All right.
[10217.14 --> 10223.34]  You've been listening to on the metal tales from the hardware software interface for show notes,
[10223.34 --> 10226.14]  to learn more about our guests or to sign up for our mailing list,
[10226.52 --> 10228.86]  visit us at on the metal.fm.
[10229.30 --> 10231.76]  On the metal is a production of oxide computer company.
[10231.76 --> 10234.44]  It is recorded in the oxide garage in Oakland,
[10234.58 --> 10235.12]  California.
[10235.76 --> 10236.64]  Torn more about oxide,
[10236.64 --> 10238.70]  visit us at oxide.computer.
[10239.18 --> 10240.32]  On the metal is hosted by me,
[10240.42 --> 10241.04]  Brian Cantrell,
[10241.16 --> 10242.20]  along with Jess for cell.
[10242.42 --> 10244.16]  And we are frequently joined by our boss,
[10244.38 --> 10244.88]  Steve Tuck.
[10245.12 --> 10249.06]  Our original and awesome theme music is by JJ Wiesler at pollen music group.
[10249.28 --> 10252.96]  You can learn more about JJ and pollen at pollen music group.com.
[10253.32 --> 10258.12]  We are edited and produced by Chris Hill and his crew at humble pod from Jess,
[10258.32 --> 10258.94]  from Steve,
[10259.08 --> 10261.76]  from me and from all of us at oxide computer company.
[10261.88 --> 10263.38]  Thanks for listening to on the metal.
[10266.64 --> 10296.62]  We'll see you next time.
[10296.64 --> 10326.62]  We'll see you next time.
