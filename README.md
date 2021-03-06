# CSIRO_sonification
Some sounds generated during my internship at CSIRO.  
The sounds can be generated automaitcally from codes (Python & midiutil etc.).  

## Generation
The values used to generate sounds come from sensor values of SmartHome during a person's activity.  
These values are then converted to the form which we can easily generate new sounds from.  
Using the converted values directly as notes gives the Raw sounds.  
With the converted values, we do stuffs so they sound better.

This is achieved mostly by  
 
    1. categorising the converted values
    2. extract their "contour" information, and do some manipulation. 
        "Contours" is pretty much [current converted value]-[previous converted value]  
    3. apply tonality and some additional rules to the manipulated contours  
    4. these contours are converted to notes  
        - notes converted to midi files with Python's midiutil library  
        - midi files converted to mp3 with FluidSynth on Ubuntu (with FluidR3_GM soundfont)  

I think my definition of contour is actually called intervals in music theory,
and music theory contour is just the quality of movement e.g. going up and down. See https://en.wikipedia.org/wiki/Melodic_motion.  

## NOTEs
#### Note 0
Even though, activity pattern cannot be inferred from the sounds at this stage (which would make it truly useful), it sounds pretty good!?
Try to compare the sounds of same number in "Raw sounds" and "Generated sounds"!  
Using McNemar's test with n=22, people prefer sound 3>1>0.

#### Note 1
I'm not uploading the code since I signed an agreement. May be I will after a few years, if I had to.  
Right now, this repo could serve as a showroom.  
#### Note 2
If you are reading this, thanks Son and Qing for opportunities. I hope I at least gave you guys some ideas.

## Some Ideas
Currently, we only use major tonality (C or otherwise). Using other tonality like minor etc. will give a different feelings to the sounds.
This can be used appropriately if we can extract activity information from raw values.
