Quick Set Scale
===============

With this [ImageJ](http://rsb.info.nih.gov/ij/) macro you can quickly change 
the scale of an image according to pre-defined parameters, usually based on 
your equipment.

Requirements
------------

You must know the pixels/unit ratio for each magnification beforehand, 
otherwise you cannot use `Quick Set Scale`. **Do not use the default 
settings**, it was calibrated for a specific set of equipments (camera, 
compound scope, objectives, etc). Using it to set the scale of an image taken 
with a different setup **will** give you the wrong measurements.

The ratio is shown whenever you run `Analyze` > `Set Scale...`. Take note of it 
for each magnification you want quick access to and you are ready to go. For example:

*Zeiss Axioplan2 with attached Nikon Coolpix at max zoom*

**Objective**       **pixel/µm**
2.5x            2.0450
10x             0.5277
20x             0.2571
40x             0.1333
100x            0.0525

If you do not know how to calibrate the scale in ImageJ there are plenty of 
tutorials out there (a [good 
example](http://skepticwonder.fieldofscience.com/2009/11/quick-imagej-tutorial-scalebar.html)).

Install
-------

1. Copy `QuickSetScale.txt` to `ImageJ/macro/toolsets/`

Configure
---------

**Quick Set Scale** comes with 2 examples. Simply remove, add, or change the 
values to fit your parameters. You can add as many setups as you may dare.

1. Edit the list of setups on this line (`newArray` items):

    Dialog.addChoice("Equipment:", newArray("Microscopio Zeiss Axioplan2", 
    "Lupa Zeiss Stemi SV11 APO"));

2. Input your magnifications and pixel/unit ratios using the template:

    // Options for Axioplan2
    if (equip=="Microscopio Zeiss Axioplan2") {
        // Write the magnifications available for your equipment
        magnifications = newArray("2.5x", "10x", "20x", "40x", "100x");
        scales = newArray("2.0450",  "0.5277", "0.2571", "0.1333", "0.05255");
        setScale("Zeiss Axioplan2", magnifications, scales);
        }

3. Ready!

Usage
-----

1. Restart the program (or launch).
2. Click on the toolset switcher on right-end of ImageJ's 
   [toolbar](http://rsb.info.nih.gov/ij/docs/tools.html) and select `Quick Set 
   Scale`.

History
-------

Originally published at 
[organelas.com](http://organelas.com/2007/12/26/quicksetscale/) (in 
Portuguese).
