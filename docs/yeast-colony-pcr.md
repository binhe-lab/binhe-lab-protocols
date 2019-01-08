---
title: Yeast Colony PCR
author: Bin He
date: 2018-09-21
categories: Yeast
tags:
	- pcr
	- yeast
	- cloning
---

Overview
--------

Our lab's version of yeast colony PCR, adapted from the McClean lab's [protocol](https://openwetware.org/wiki/McClean:_Colony_PCR_(Yeast)).  Generally, we use this protocol for checking transformations (i.e., to check that the intended genomic editing has been achieved) or for PCRing up a piece of DNA from the genome for cloning.



Materials
---------

-   Any Taq DNA Polymerase or PCR master mix
-   8-strip thin wall PCR tubes
-   Sterile water (MilliQ water will do, or autoclaved MilliQ water to be sure)

Protocol
--------

Add approximately 0.6uL of cells (tiny amount) with the tip of a pipet tip (10 uL one works well) into the bottom of PCR tubes or plate.  Once you've put cells into the PCR vessel, put the end of the tip into ~100 uL sterile YPD in either a PCR tube or plate.  You will use this to inoculate an overnight culture if your colony PCR works.  Keep the PCR tube or plate with the tip in YPD at either room temperature or 30°C while you run the PCR, either is fine.

**Important** Microwave cells in the PCR tube/plate for 1 min (2x).  Put microwaved cells on ice.


Add the reaction mix (described below) to the PCR tube/plate.  It is recommended to make up a master mix if you are doing multiple colonies.  Put the PCR tubes/plate into the thermocycler and run the Colony PCR program described below.

### PCR reaction mix using Taq enzyme

We use SibEnzyme Taq polymerase (cheap, works very well)

_Note_

1. For n colonies to check, make up N=n+1 worth of master master mixes as shown below. Use the additional one as negative control. Make n+2 if doing positive control.
2. It is not possible to pipet 0.05 uL Taq. Luckily, we typically do > 10 colony pcr reactions at a time, which means we will deal with no less than 0.5 uL.

|   Vol | Reagent                | x N |
|------:|:-----------------------|-----|
| 1  uL | 10x SE Buffer          |     |
| 1  uL | dNTPs 2mM each         |     |
| 1  uL | Primer mixes, 5uM each |     |
| .05uL | Taq DNAp, 5U/uL        |     |
|   4uL | MilliQ water           |     |

### PCR reaction mix using master mixes

e.g. NEB OneTaq Quick-Load 2x master mixes (biochem store #103341)


| Vol | Reagent                | x N |
|----:|:-----------------------|-----|
| 5uL | 2x PCR master mix      |     |
| 1uL | Primer mixes, 5uM each |     |
| 4uL | MilliQ water           |     |

### Thermocycler program
After mix by pipetting up and down, run PCR with the following program:

94&deg;C for 5 min<sup>1</sup>; {94&deg;C 30s; 50&deg;C<sup>2</sup> 30s; 72&deg;C 1min/kb} x 35-40 cycles; 72&deg;C 2 min; 12&deg;C 10 min<sup>3</sup>.

_note_

1. This longer time may help break the cells. But given that we have microwaved the cells, shorter time, e.g. 1 min, may be sufficient.
2. 50&deg;C generally works. However, use a tool such as [NEB Tm calculator](https://tmcalculator.neb.com/#!/main) to calculate the annealing temperature if you are in doubt or if PCR fails.
3. Traditionally PCR programs call for 4&deg;C hold forever. However, for colony PCR or other protocols where the product is only used for gel electrophoresis, this is not necessary. Instead, we use a 12&deg;C 10 min step to cool down the reaction. The products are then stable at room temperature for at least one night.

### DNA gel electrophoresis
1. Make a 0.9% (w/v) agarose gel by adding 0.9g of agarose to 100 mL of 1x LB buffer in a 250 mL flask.
    - 0.9% LB gel is good for 100bp-2.5 kb, which is the recommended size range for colony PCR anyway.
1. Microwaving the mix for 1+1 min, watch for boil-over.
1. Using a hot hand protector (rubber), hold the flask and watch for undissoved gel traces. Once fully dissolved, run cold water on the flask wall to cool it down to touch. 
1. Pour out enough for the size of the gel into a small beaker. 
    - 40 mL is enough for a small gel. If in doubt, use a cylinder to measure water and try it out.
1. Add 2.5 uL of Ethidium Bromide per 100 mL of gel mixture.
    - Ethidium bromide is a known carcinogen. Use gloves, follow good lab practice.
	- By adding EB after dissolving the agarose, we reduce the chance of inhaling fume containing EB.
	- **Important** swirl the beaker to mix the EB into the gel mixture! This is a common mistake for beginners.
1. Assemble the gel gasket by putting the black rubber stoppers onto the two ends. Then pour the gel mixture into the assembled gasket. Thinner gels will generate less heat and run faster.
1. Remeber to put the comb in after removing bubbles from the surface.
1. Let the gel solidify for about 10 min.
1. Place your gel in the electrophoresis container and ensure that the LB solution is filled to just covering the gel. For checking colony PCR products, reclaimed 1x LB is good enough. If used buffer is getting cloudy with gel traces, feel free to dump into the white bucket underneath and use fresh ones.
    - The DNA will have a net negative charge, and so ensure that the holes in the gel face the anode (-, black) so that the DNA will flow to the cathode (+). 
1. Add DNA samples
    - Add 2 uL of NEB Quick Load DNA ladder to the first lane.
	- If you used the NEB Quick-Load master mix, it already contains a tracking dye, so directly pipet 5 uL of the PCR product into each lane. When pipetting, don't "blow out" as this will cause cross well contaminations. Just dispense the majority of the product is enough.
	- If you used the Taq enzyme system, add 2 uL of 6x QuickLoad dye to each well and mix by pipetting, then add 5 uL into each lane.
1. Put on the lid, check to make sure that the anode and cathode are placed correctly and that DNA will run toward the + end.
1. Run the gel by turning on the power supply and use ~ 200-250 V for a small gel and ~300-400 V for a large gel. 10-15 min should be enough. However, watch the dye front to know when to stop.
1. To check the gel, place your gel slabs in the UV chamber, put the hood on and then turn the UV switch to low and turn on the power. Turn both the camera and the display on, check for zoom levels. To take a picture, half press the shoot button on the point-and-shoot camera to focus, keep pusing the button to take the picture.
1. If the result looks good, discard the gel into the gray bin below the UV box. Open the camera's battery chamber to remove the SD card. Insert it into your computer (there is an adapter floating around one of the lab desktops).
1. Clean up: either dump the used buffer if already used several times, or pour it back into a bottle labeled reclaimed 1x LB buffer using a funnel. Rinse out the gel boxes and cassettes. Return everything to how you find them.

### Freeze down the positive transformants

Once you have run the colony PCR and confirmed which colonies are correct and which are not, take the 100μL of YPD that you set aside before, inoculate it into 4mls of fresh YPD in a test tube, and grow it to saturation overnight.  Use this to freeze down glycerol stocks of the strain the following morning.

Notes
-----

Please feel free to post comments, questions, or improvements to this protocol. Happy to have your input!

1.  List troubleshooting tips here.
2.  You can also link to FAQs/tips provided by other sources such as the manufacturer or other websites.
3.  Anecdotal observations that might be of use to others can also be posted here.

Please sign your name to your note by adding '''*~~~~''': to the beginning of your tip.

References
----------

[McClean lab yeast colony PCR protocol](https://openwetware.org/wiki/McClean:_Colony_PCR_(Yeast))

Contact
-------

-   **Bin He 22:01, 7 Jan 2019 (EDT)**
