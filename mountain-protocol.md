---
title: Rocky Mountain adventures in Genomic DNA
permalink: /mountain-protocol/
layout: default
---

**Rocky Mountain adventures in Genomic DNA sample preparation, ligation
protocol optimisation / simplification and Ultra long read generation**

So been a while since I posted on the community so a bit of catching up
to do…..:o). We have been playing quite a bit with native genomic DNA
sequencing for a project we have running on Epigenetic modifications of
Rat models of neurological disease. While we are still rapidly iterating
on tweaks etc. to some new protocols around increasing our production
efficiency of ultra-long reads (100kb+) using LSK109 ligation kit
components and PEG/NaCl mediated DNA precipitation, we are settling into
a workflow now that I think is worth sharing and has been generating
very good results for us. That said remember this is a little “wild
west” and perhaps for the more adventurous at this stage, use at your
own risk etc. etc. and perhaps help with some tweaks of your own ;o).
I’ll say now that I have been optimizing this on a very easy Rat cell
line grown in culture and realise some people don’t have this luxury,
however I think this is a very good jumping off point and allowed us to
iterate on a consistent starting material and will myself be venturing
off into tissue extractions now.

There are currently three main areas to highlight and detail changes
within a sample to sequence workflow that we think has allowed us to
push the efficiency and yields of sequence data out. Firstly DNA
extractions using Phenol/Chloroform and spooling out of HWM DNA to
generate the starting DNA sample.  Secondly input material shearing and
modifications to the LSK109 ligation protocol that have yielded high
efficiency libraries, and production of greater ultra-long reads
numbers. Lastly the use of flowcell refueling and DNAseI clearing of the
flowcell surface to remove “blocking” DNA and allow fresh library
addition after a surface “reset”.

I’m detailing all we have here is an attempt to allow people to fully
understand what is going on as much as possible and so we can all use
this information to make intelligent changes to the protocols etc. if
you are so inclined. Commercial “black box kits” and solutions while
great for defined on mass purpose and reproducibility make this process
more opaque and often overly complex and expensive. A good example of
this is the addition of just NaCl after the ligation reaction to
precipitate the adapted DNA showing how knowing what you have provides
simplification and economic sense for the end user in some situations,
but more on that later…...

**Old-School Phenol/Chloroform Genomic HMW DNA Preparation**

In order to mitigate damage/shearing of genomic DNA we have avoided kits
etc. that employ beads or a matrix that your DNA must associate with or
sieve through (blend :o)). We have not gone the whole hog at this point
and used nuclei preps, dialysis or plug extractions etc. as we have
found that material produced from a simple and rapid phenol/chloroform
prep is more than adequate and high yielding. We have done some limited
salting out experiments as a substitute for the phenol/chloroform
approach but have some remaining questions around size and stability in
the fridge for extended periods that need resolving. We will be
revisiting this.

The jumping off point for us was using methods detailed in “Molecular
Cloning: A laboratory Manual” by Sambrooke and Russell. If you are at a
large institution there will probably be copies around on people’s
shelves or in the library collecting dust. It’s time to dust those off,
they have been patiently waiting for their day in the sun again :o)).
Chapter 6 is a good place to start. This approach produces DNA that is
more than large enough for any nanopore sequencing currently.

**Protocol: Phenol/Chloroform Genomic DNA extraction from Tissue Culture
cells**

1\. Remove tissue culture media from two T25 flasks of cells ( \~ 1 x
10^7 cells / per flask, or 60-80% confluency) and lyse cells by adding
5ml of Lysis buffer per flask and gentle rocking back and forth for \~1
min.

<span class="underline">Lysis Buffer</span>

10mM Tris-Cl (pH 8.0)

25mM EDTA (pH 8.0)

100mM NaCl

0.5% (w/v) SDS

20ug/ml RNase A (added fresh)

2\. Pour the viscous sample into a 50 ml tube after gently scrapping the
surface of the two T25’s with a cell scrapper.

3\. Incubate for 1hr at 37<sup>o</sup>C.

4\. Add proteinase K (20mg/ml) to a final concentration of 100 ug/ml and
mix by gentle inversion of the tube several times.

5\. Incubate the lysate at 56<sup>o</sup>C for 3 hrs. (occasionally mix
by inversion)

6\. Allow to cool to room temperature before adding an equal volume of
buffer saturated phenol (Invitrogen 15513-047).

7\. Gently mix by inversion for a few minutes until an emulsion is
formed.

8\. Separate the two phases by centrifugation at 5000g for 30-60 mins at
room temperature.

9\. Use a wide-bore pipette to transfer the upper viscous aqueous phase
to a fresh tube being careful not to disturb any material at the
interface. (further Phenol extraction steps may be required if there is
a large quantity of material at the interface i.e. when performing
extractions from tissue samples)

10\. Add an equal volume of Chloroform and mix by gentle inversion for a
minute or so.

11\. Separate the two phases by centrifugation at 5000g for 30 mins at
room temperature.

12\. Use a wide-bore pipette to transfer the upper viscous aqueous phase
to a fresh 50ml tube being careful not to disturb the interface.

13\. Add NaCl to increase concentration by 0.3M from a 5M stock and mix
by gentle inversion.

14\. Add 2 volumes of ethanol and mix by inversion a couple of times and
then gentle swirling. You should see a stringy mass of DNA condense
together and this is hooked out using a glass capillary with a hook made
at the end.

15\. Wash the DNA condensate by dipping into a series of three 1ml tubes
containing 70% ethanol and holding there for \~20 seconds.

16\. Allow the DNA on the glass capillary to air-dry for \~1min (hold
upside down and allow any excess liquid to rundown and dab away with a
tissue avoiding the DNA).

17\. Place the DNA on the end of the glass capillary into a tube
containing 100-200ul EB (10mM Tris-Cl pH 8.0) and let sit at room
temperature for \~30 mins.

18\. Gently dislodge the DNA from the glass capillary. You should be
left with a viscous solution with no “gel” mass on the glass capillary.

19\. Place the DNA solution in the fridge and leave for a few days to
fully hydrate before use. We generally see a yield of 200-400ug of
genomic DNA. High viscosity is a good indication of HMW DNA being
present (using a pipette draw a small volume up and then pull out from
the surface of the DNA solution. If you see a continuous strand
connecting the tip and solution you are good).

Note: It can take a while for HMW DNA solutions to “homogenise” when
diluted due to viscosity and this often makes reliable quantification
hard. We will often prepare 1/5 or other appropriate dilutions a day
ahead of intended processing to help with this issue.

**Modified LSK109 ligation prep using needle shear and bead
purification**

Using HMW DNA purified as above we have been performing 29G and 26G
needle shears to produce fragmentation to around 18Kb and 34kb
respectively (reported read N50’s after basecalling). Also by going into
the library preparations with 5-10ug of DNA have been able to produce
enough material to provide up to 10 library loads from a single prep. We
have not been performing the FFPE repair during the end-prep step, and
have been diluting the sample at the cleanup points in the protocol with
EB to prevent bead clumping during 0.4-0.5x AMPureXP purifications when
DNA fragments are large and at high concentrations. Shown below are the
results from a batch of 12 runs we performed using this approach.

> ![](/assets/mountain-protocol/image1.png)

**Protocol: Modified LSK109 ligation prep with needle shear and bead
clean up**

1\. 10 ug of HMW genomic DNA made up to 250ul with EB and sheared with
either a 29G or 26G needle using 20 passes. (After shearing is a good
time to get a reliable DNA quantification using the Qubit DNA HS kit
etc.)

2a. For 26G shear add 250ul of EB (10mM Tris-Cl pH8.0) followed by 250ul
AMPureXP bead solution.

2b. For 29G shear add 125ul AMPureXP bead solution.

3\. Mix by flicking, incubate for 10 mins at room temperature followed
by pelleting on a magnet.

4\. Remove supernatant and keeping on the magnet wash 2x with 300-500ul
80% ethanol without disturbing the pellet. Briefly spin, return to
magnet and remove any residual 80% ethanol with a pipette before
allowing the bead pellet to air dry for \~2 min.

5\. Removed tube from the magnet and resuspend the bead pellet in 51ul
EB by flicking. Spin down and allow DNA to elute by incubation at
37<sup>o</sup>C for 5 mins.

6\. Place tube on magnet and remove eluted DNA sample to a fresh tube.

7\. Quantify 1ul of the DNA sample using the Qubit DNA HS kit to confirm
DNA recovery (\~6ug) and then set up the following End-Prep reaction:-

50ul DNA sample

7ul Ultra II End-Prep Buffer (NEB)

3ul Ultra II End-Prep Enzyme mix (NEB)

8\. Incubate at 20<sup>o</sup>C for 30 mins followed by 65<sup>o</sup>C
for 30 mins.

9\. Add 120ul EB buffer followed by 72ul AMPureXP bead solution.

10\. Mix by flicking, Incubate for 10 mins at room temperature followed
by pelleting on a magnet.

11\. Remove supernatant and keeping on the magnet wash 2x with 300ul 80%
ethanol without disturbing the pellet. Briefly spin, return to magnet
and remove any residual 80% ethanol with a pipette before allowing the
bead pellet to air dry for \~2 min.

12\. Remove tube from the magnet and resuspend the bead pellet in 67ul
EB by flicking. Spin down and allow DNA to elute by incubation at
37<sup>o</sup>C for 5 mins with occasional flicking.

13\. Place tube on magnet and remove eluted DNA sample to a fresh tube.

14\. Quantify 1ul DNA sample using the Qubit DNA HS kit to confirm DNA
recovery (\~4-5ug) and then set up the following Ligation reaction:-

66ul DNA sample

25ul LNB buffer

5ul AMX adapter

4ul Quick T4 DNA Ligase (NEB)

15\. Incubate at 20<sup>o</sup>C / room temperature for 60 mins.

16\. Add 100ul EB buffer followed by 80ul AMPureXP bead solution.

17\. Mix by flicking, briefly spin and incubate for 10 mins at room
temperature followed by pelleting on a magnet.

18\. Remove supernatant and keeping on the magnet wash 2x with 250ul of
LFB buffer by removing from the magnet and flicking, briefly spin, and
pelleting again on the magnet. Remove any residual LFB buffer while on
the magnet with a pipette after final pelleting.

19\. Remove tube from the magnet and resuspend the bead pellet in 21ul
ONT-EB buffer by flicking. Spin down and allow DNA to elute by
incubation at 37<sup>o</sup>C for 5 mins.

20\. Place tube on magnet, pellet beads and remove eluted DNA sample to
a fresh tube.

21\. Quantify 1ul DNA sample using the Qubit DNA HS kit to confirm DNA
recovery (\~2.5ug).

22\. Library ready for use, (200–400 ng per load).

DNaseI and flowcell clearing for increasing long read yields and
multi-sample sequencing

The use of the Nuclease flush protocol (DNaseI digestion of DNA on the
surface of the flowcell;
https://community.nanoporetech.com/protocols/nuclease-flush-protocol/v/NFL\_9076\_v109\_revB\_08Oct2018
) has become an integral part of our long reads sequencing efforts.
These can be seen in the figure above and can be seen as increases in
data yield accumulations on the curves. In the case of our native rat
genomic sequencing we see an accumulation of pore blockage over time
that is DNA fragment length dependent. Shown below are two libraries
produced from an identical sample sheared to an increasingly smaller
size and run.

![](/assets/mountain-protocol/image2.png)

Using DNaseI surface clearing we often see recovery of an additional
50-80% of total reported pores on top of what a mux scan reports before
treatment as long as the flowcell surface has not been “damaged” in some
other way. You can monitor the process live if you restart a run and
then pipette in the DNaseI clearing solution and watch the duty plots
(see below). Once complete in \~30 mins flushing back to FLB/PFB and
re-tethering will on a restart produce a pore count of what you have
left to use. The flowcell is “reset” ready for the next library addition
and run restart. That may be the same library again or something
different……

![](/assets/mountain-protocol/image3.png)

With our “blocky” rat genomic samples sheared to 18-34kb we have been
performing these resets every 16-24 hrs. For larger fragment lengths we
will likely shorten this time period so the flowcell is not sitting
there in an unproductive “blocked” state. It might be time for some
MinKNOW scripted automated yield monitoring and hardware surface
clearing hacks ;o).

**Size Selective Precipitation of DNA using PEG & Salt**

We and others have been thinking about the possibility of providing DNA
size selection / clean up / and removal of expensive reagents in the
library preparation process for a little while now. There are a number
of possible routes but we have focused more recently on Polyethylene
Glycol (PEG) and salt precipitation of DNA as it is cheap, non-toxic and
known to be compatible with the existing library preparation process.
One of the early demonstrations of combining PEG and salt to selectively
size fractionate DNA by selective precipitation was by Lis & Schleif in
1975 ( Size fractionation of double-stranded DNA by precipitation with
polyethylene glycol. NAR 2:(3) p383). We have been screening different
sizes and concentrations of PEG combined with different salt amounts to
find suitable combinations for removal of short “contaminating” DNA
fragments. This is useful for situations where you are not starting with
a DNA sample of HMW and want to target the longest DNA strands you have
or want to try and remove shorter fragments produced during a
preparation.

Shown below are some of our current best combinations but the hunt goes
on, with changes to type and concentration of PEG, and different cations
with different charge densities. The commercially available Circulomics
buffers perform a similar task, and are performing a little better at
this stage. We do not know what exactly has been used in their
solutions.

![](/assets/mountain-protocol/image4.png)

One advantage of knowing that PEG/NaCl can be used in this fashion came
with the realisation that given ligation buffers often use high PEG
concentrations to crowd the DNA fragments we could probably use straight
NaCl addition into the ligation reaction once complete to precipitate
our adapted DNA. This is shown below with testing on a Lambda+DNA ladder
sample and the ONT LNB buffer +/- 600mM NaCl (There is also the hint
there that some level of HMW DNA is even coming out of solution without
the salt addition…….). This idea together with PEG / NaCl precipitation
when coming out of the LSK109 library End-Prep reaction was taken and
used to develop the Bead-free LSK109 ligation prep for ultra-long DNA
detailed below in the next section.

![](/assets/mountain-protocol/image5.png)

If people feel so inclined I can provide further details on the current
matrix of PEG size / concentrations and salt type / concentrations we
have looked at so far and then we can perhaps speed up the search. There
are obviously other possibilities that can be explored around size
selection using charged polymers and higher charge density ion induced
precipitation. Only so many hours in the day :o)).

**Bead-Free LSK109 ligation prep for ultra-long DNA**

The use of AMPureXP beads for reaction cleanup when targeting Ultra-long
DNA reads is not optimal as inter-bead binding results in bead clumping
and potential fragmentation as individual beads move around freely in
suspension. This is why the original Ultra-read method
(https://www.protocols.io/view/ultra-long-read-sequencing-protocol-for-rad004-mrxc57n)
developed by Josh Quick and Nick Loman used dilution of the Rapid MuA
kit and high concentrations of HMW genomic DNA. Saturating the MuA
insertion reaction with HMW DNA results in less individual strand
fragmentation and produces previously unattainable read lengths. It does
not require cleanup or binding and elution on and off magnetic beads and
minimized “handling” of the DNA. This therefore mitigates the
fragmentation and DNA recovery issue with very long DNA molecules and
has allowed the production of individual reads in excess of 1 million
bases to be produced. The yield from individual flowcells using this
approach is around an order of magnitude less however as there appears
to be flowcell surface damage and rapid pore “blockage”. While 1Mb+
reads are amazing to see, they are a very small fraction of the total
and it is the read N50 that is important. Targeting 100kb+ reads in
volume goes a long way to producing substantial improvements in large
genome assemblies particularly when trying to span large repeats or low
complexity regions refractory to other sequencing technologies. We have
been experimenting with DNA size fractionation / precipitation using
PEG/NaCl as mentioned above. This provides a means to remove the
requirement for magnetic beads with their associated issues, and allows
a higher yield of ultra-long reads to be produced. We have found that
the DNA produced from the Phenol/Chloroform prep above provides DNA of a
size that requires shearing down into a range to provide a mix of length
and yield. Shown below is data from a single flowcell that I ran
multiple libraries on looking at the effects of sequential shearing to
gradually shorter lengths using a single DNA sample and where aliquots
were removed before the next smaller shear was performed. Using a P1000
pipette tip or simple needle shear and PEG / NaCl precipitations, you
are able to produce up to 21% of total sequenced data in 100kb+ reads.
Combined with DNaseI flowcell clears, high yields are looking
obtainable. It is early days for this protocol so expect changes to come
quickly as we try and dial in better size selection and an even higher
proportion of 100kb+ reads. At present we are not really seeing much
short read depletion and I think this is to do with suboptimal
conditions used for the DNA precipitation. Unknown buffer components in
the End-Prep and Ligation buffers appear to be throwing off the PEG/NaCl
parameters we have identified for size selection so there is still work
to be done to tune this and something we are working on. For the 21G and
29G examples below we did do a final PEG/NaCl precipitation of the
finished library but didn’t see consistent depletion comparing the two,
so still things to be worked out for consistency and to understanding
what is happening.

![](/assets/mountain-protocol/image6.png)

As a fall back, assuming little size selection can be implemented during
the prep for now, we looked again at the size selection step at the end
of the library preparation when eluted into EB buffer (no other salts or
other components to throw size selective precipitation off). This is
shown below comparing the Circulomics SRE buffer and 9% PEG8000 (w/v) 1M
NaCl on precipitation and recovery using an equal volume addition to a
P1000/26G needle sheared Bead-free LSK109 prep. Take this with a grain
of salt at the moment as one used an old MinION flowcell (for
Circulomics) and the others (library before selection (control), and
PEG/NaCl size selection) were run on flongles so data volume is a little
low with long frag blockage. We are seeing the SRE buffer performing
better at short fragment removal, but want to investigate what is going
on with the upper end and read N50.

![](/assets/mountain-protocol/image7.png)

**Protocol: Bead-free long fragment LSK109 library preparation**

1\. 10 ug of HMW genomic DNA in 51ul of EB was either used unsheared or
sheared (see above).

2\. Quantify 1ul of the DNA sample using the Qubit DNA HS kit to confirm
DNA recovery and then set up the following End-Prep reaction:-

50ul DNA sample

7ul Ultra II End-Prep Buffer (NEB)

3ul Ultra II End-Prep Enzyme mix (NEB)

3\. Incubate at 20<sup>o</sup>C for 30 mins followed by 65<sup>o</sup>C
for 30 mins.

4\. Add 60ul of a PEG/NaCl precipitation buffer \[9% PEG8000 (w/v), 1M
NaCl, 10mM Tris-Cl (pH8.0)\] and mixed by flicking tube. This mixture
was then incubated at room temperature for 30 mins before being
centrifuged at 13.5K rpm for 30mins at room temperature.

5\. Remove supernatant and wash 2x with 200ul of 70% ethanol by simple
addition to the inside of the tube wall and centrifuging for 5 mins
followed by removal. Be careful to avoid pelleted DNA when doing this
(you may not see DNA so keep away from appropriate area of tube).

6\. Allow DNA to air dry for a couple of mins and then add 41ul EB
buffer (10mM Tris-Cl pH8.0).

7\. Leave DNA in fridge to resuspend overnight. (depending on DNA
fragment size time can be shortened)

8\. Mix DNA by flicking and quantify 1ul using the Qubit DNA HS kit to
confirm DNA recovery and then set up the following Ligation reaction:-

33.5ul DNA sample

12.5ul LNB buffer

2ul AMX adapter

2ul Quick T4 DNA Ligase (NEB)

9\. Incubate at 20<sup>o</sup>C / room temperature for 60 mins

10\. Add 4.4ul 5M NaCl, mix by flicking and incubate for 30 mins at room
temperature to precipitate the DNA.

11\. Centrifuged at 13.5K rpm for 30mins at room temperature.

12\. Remove supernatant and wash 2x with 200ul of a 2 fold dilution of
the previously used PEG/NaCl precipitation buffer above. Do not disturb
the pellet and centrifuge for 5 mins between each addition before
removing wash solution.

13\. Add 26ul EB buffer (10mM Tris-Cl pH8.0).

14\. Leave adapted DNA in fridge to resuspend overnight. (depending on
DNA fragment size time can be shortened)

15 Mix DNA by flicking and quantify 1ul using the Qubit DNA HS kit to
confirm DNA recovery.

16\. \[Possible round of size selection with Circulomics / PEG-NaCl
buffer (see figure above).\]

17\. Library ready to load (400ng-1.3ug depending on size and recovery).

**Final thoughts….**

One of my interests around nanopore sequencing and moving sequencing
back to small labs and beyond with the MinION device is also mitigating
the sample preparation costs while not sacrificing performance. Using
cheap needles, Polyethylene Glycol, salt and old school molecular
biology techniques we are seeing uncompromising performance for both
yield and read lengths that I think even the “big” guys will use :o)). I
will reproduce this post and methods at www.longreadclub.org soon so
they will be easier to find and develop going forward, and we will try
and provide protocols on www.protocols.io as well.

Things on the to do list include:

  - Further optimisation of PEG/salt parameters for size selection /
    short read elimination at different stages of library preparation.

  - Refinement of shearing to provide increased 100kb+ reads from HMW
    DNA

  - Look at replacing Phenol/Chloroform with salting out in initial HMW
    Genomic DNA preparation.

Who knew that PEG and salt would be a route to cheap ultra-long reads,
we all just need to keep tweaking away in an open fashion and who knows
where we can get. Anyway that’s enough from me for now, happy Nanopore
adventuring\!

John Tyson (Snutch Lab, UBC, Vancouver, BC, Canada)

