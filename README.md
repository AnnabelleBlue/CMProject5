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
    Algorithms Controller - Beatmachine - page 3
    Parameters Controller - Keys - pages 2,3
    Drums Controller - Beatmachine - page 2

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