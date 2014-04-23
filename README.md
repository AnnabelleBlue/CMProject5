Contents
	Data structure files
		noteheader.srp
		soloinput.srp
		druminput.srp
		musicobj.srp

	Algorithm files
		electronic.srp

	main.srp


noteheader.srp contains the class which defines our note instances, which are used in soloinput, electronic.srp, and main.srp.

soloinput.srp contains the class which defines the data instance which the OSC handlers for the soloist will write to and the algorithms will read from.

druminput.srp is the same idea as soloinput.srp, but for the drum machine and not the soloist.

masterdata.srp contains a data structure for storing information about the volume, tempo, currently playing notes, scale, etc.

electronic.srp contains one of our algorithms for generating music. This will generate a list of notes for the scheduler to play each time we call it. It reads data about the current beat we're on, the weight setup of the current drums, and the latest pitches played by the soloinput

main.srp contains the OSC handlers and runs our main music loop