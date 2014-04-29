Contents
	Data structure files
		algoobj.srp
        noteheader.srp
		soloinput.srp
		drum_input.srp
		musicobj.srp

	Algorithm files
		electronic.srp

    OSC files
        handlers.srp
	
    main.srp

OSC Controls
    Soloist - LiveControl Ipad - Keys
        Just a regular scale with the bottom C set as
        middle C (pitch = 60) and the top C set as an octave up
    Algorithms Controller - Beatmachine - page 3
        Rotary1 - Controls the velocity of the algorithm bass
        Rotary2 - Controls the velocity of the algorithm treble
        Toggle1,2,3 - Controls which aspects of the algorithm feed 
            into the final note played
    Parameters Controller - Keys - pages 2,3
        Page 2 - 
            Pick a key by pressing the corresponding button on the keyboard
        Page 3 - 
            Slider1 - Controls the tempo of the underlying system
            Slider2 - Controls the velocity of the soloist
            Slider3 - Controls the velocity of the drum beat
            Toggle1,2,3 - Controls the underlying instrument based on a binary
                index into an array containing instrument choices
            Push1,2,3,4 - Red push turns the key to minor, green push turns the 
                key to major
            
    Drums Controller - Beatmachine - page 2
        Uses the XY controller - each toggle represents exactly 1 beat
        The top line controls the first 16 beats of the hi hat drum
        The second line controls the second 16 beats of the hi hat drum
        The next two lines control the snare drum
        The bottom two lines control the bass drum

noteheader.srp 
    contains the class which defines our note instances, which are used in soloinput, electronic.srp, and main.srp.

soloinput.srp 
    contains the class which defines the data instance which the OSC handlers for the soloist will write to and the algorithms will read from.

drum_input.srp 
    the same idea as soloinput.srp, but for the drum machine and not the soloist.

algoobj.srp
    contains a data structure for storing information about the algorithm such as volume, tempo and which algorithms are playing
   
musicobj.srp 
    contains a data structure for storing information about the volume, tempo, currently playing notes, scale, etc.

electronic.srp 
    contains one of our algorithms for generating music. This will generate a list of notes for the scheduler to play each time we call it. It reads data about the current beat we're on, the weight setup of the current drums, and the latest pitches played by the soloinput

handlers.srp
    contains all the OSC handlers that redirects all inputs to their appropriate data structures and functions
    
main.srp 
    contains the OSC handlers and runs our main music loop