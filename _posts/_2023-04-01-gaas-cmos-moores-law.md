---
author: unknown
--- 
## Why isn't GaAs CMOS a thing? 

On transmission lines and Moore's Law:
 
Because GaAs isn't a thing and because there is no native oxide in most non-Silicon semiconductors so piling them up and/or making MOSFETs isn't possible (or easy anyway).

GaAs is a compound semiconductor and ALL compound semiconductors (which includes III-V and II-VI semiconductors) combined only amount to 1% of all semiconductor manufacturing, shipped volume and sales revenue for the entire semiconductor market. A major reason is "native oxide" that faciliate making passivation and in the case of MOS, MOS gate oxides. What this means is you can merely heat silicon in an oxygen rich environment and it produces silicon dioxide on its surface spontaneously. Silicon dioxide (aka sand, quartz, etc.) is a very good insulator, and very hard and tough. Other semiconductors have either gaseous oxides or have very soft and conductive oxides (e.g. GeO2).

Passivation matters because interface states between the semiconductor surface and either the environment or other materials are a problem. Most of the problems associated with transistor reliability in the 1950s and IC reliability in the 1960s was related to passivation and it's low quality. Interface states are still the primary reason for transistor failure but we've pushed the time out fairly well (though shrinking transistor sizes makes all reliability problems worse again!) The big advance was to grow native oxide and completely encapsulate the active transistors from the outside environment.

There are techniques used with GaAs and similar which typically involve depositing silicon oxide or other insulator (plastics) or air insulation. Most of these weren't possible at all until the 1980s and even then they are expensive and problematic. Thus compound semiconductors devices tend to be devices (e.g. LEDs, laser diodes or RF transistors) or they are fairly low complexity and density devices (e.g. digital ICs made by Triquint which are generally of the density of TTL MSI parts).

Silicon has an insanely strong lock on semiconductors because of it performance and versatility due to its chemical and physical characteristics.

The problem with VLSI device speeds today is NOT only partly transistor limited. If you magically had an arbitrarily fast transistor now and substituted it into a current manufacturing process, CPU clock speeds would increase and then stop at ~10-15 GHz. The reason is the interconnect parasitics between transistors become the limiting factor!

Basically you have transmission lines connecting things with R, L and C parasitics defined by the materials used interconnecting transistors on ICs. Remember that you get transmission line effects when the lumped-model breaks down which starts happening at ~±10x of the wavelength of the signal involved. Because digital deals with square waves, accurate edge-placement depends on having harmonics of the fundamental up to ~10x of the fundamental. So with a 3 GHz clock rate, you actually need to worry about frequencies at 30 GHz which has a wavelength 3E8 / 3E10 or 1 cm. Because lumped model breaks down within a factor of ten of the wavelength, you run into distributed model effects at dimensions between 1 mm and 10 cm. Ok, then, how big is your average IC die? From 5 mm to 2 cm - right in the middle of trouble and transmission line effects.

In the late 1990s, these same limits defined the maximum speed of ICs. Two things were done to speed up the transmission line effects: switching to low-k dielectrics in the inter-metal dielectric (which reduced the C value and boosted the parallel R) and then shortly after that to switch to copper metal interconnects (from aluminum used since the 1950s) which reduces the series R. The L is pretty much unchangeable because it's based on length. So you drop both the RC and RL time constants of the transmission lines and things go faster. Fast enough that devices become the limiting factor.

To fix that, more scaling would typically solve that BUT there was a problem - scaling requires shrinking XY dimensions but it also requires shrinking the gate oxide thickness. And shrinking that causing a new problem: below 30Å you get strong direct tunneling through any dielectric so thinning the oxide stopped being an option as well.

Instead there's another variable you can change (but only once thanks to the periodic table of elements): you can increase the gate dielectric constant. Which is what high-k gate stacks are about. These use exotic oxides such as HfO2 and ZrO2 along with SiO2.

One 2nd to last gasp for pure planar CMOS is FDSOI which reduces the parasitic capacitance caused by the substrate upon which the devices are built. This also has a shelf-life.

FinFET and 3D transistors - they are an 3D alternative to FDSOI. But it's looking like these are also "one trick ponies" and FDSOI might give us more longevity.

There is an opening for III-V (it's part of the current roadmap) and will be what's behind that last "oomph" between now and 2025: using deposited III-V semiconductor in the channel of an otherwise silicon MOSFET to gain a mobility kick. It won't be GaAs however. Mostly it will be an InGaSb/InAs or similar which happens to have the maxed out carrier mobility of all III-V semiconductors; basically we are shooting our entire wad on this.

So now, if you increased the speed, you'll again be locked in and hit a wall because of low-k and copper. There's nothing much better than copper as a conductor (silver which has metallurgical problems and maybe graphene but it has process issues as well). Low-k is a chemical cousin of aerogels and already pretty much un-improvable. You have high-k but that's also hits a wall. And you have FDSOI which only works for a while. And III-V channel CMOS will be the last hurray. So as long as you are using electrical connection between transistors, you are fucked again at 10-15 GHz or a little bit higher. This, BTW, is why Moore's Law ends in 2025.

The only viable option then is optical. However, optical is only a bit faster - electrical transmission lines are already operating at ~40%-70% of the speed of light and simply adding dielectric waveguides (e.g. fiber optic channels) to connect the light source and destination throws some of that advantage away by slowing the speed down.

The simple answer is: we're done with turning the crank and speeding up devices and ICs to get more performance - that's 100% over for the most part.

Instead the best solution is to change how we compute and write code so that you don't actually have to have faster connections between faster devices most of the time. This gets to the problems of how to write parallel and threaded code. If you've ever written pthread code you know how utterly unscaleable most common programming languages are for parallelizing execution. But that's what the "answer" is.

If you are an Apple fan, you probably know about Swift. Why would they abandon ObjC and adopt an immature language like this? Simple: Swift is far more "functional" than C or other derived languages (including ObjC) and functional languages have mathematically provable advantages in parallelizing code because of the lack of "side effects". Combine this is Apples OpenCL push and a pattern develops.

And there's also a ton of stuff that can still be innovated that doesn't include "speeding things up" but making electronics "smarter" rather than brute force better. Consider, for instance, all the possible technology forgone simply because Moore's Law was so insanely successful. Many of those might be quite useful if revisited from this vantage in history.

