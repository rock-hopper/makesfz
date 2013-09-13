makesfz
=======

BASH script to auto-generate SFZ files

This an updated version of danboid's original script http://www.remastersys.com/forums/index.php?topic=1951.0

By default, running 'makesfz' with no arguments creates individual .sfz files for every .wav file found in the current directory. Samples are mapped across the entire keyboard with pitch_keycenter set to MIDI key C4 (middle C).

Alternatively, running 'makesfz -s' creates a single .sfz file named after the current directory. Each .wav file found is mapped to its own MIDI key, by default starting at C4.

The script also allows a key range and the "key center" to be specified, a specific MIDI channel can be set, and either wav or ogg files can be used. Keys can be either the key name (# or b allowed) or MIDI key number.

For example, to set a key range from C2 - C5:

    makesfz --lk=C2 --hk=C5

Or to create a single .sfz where the first sample starts on C3 and "one shot" is required:

    makesfz -s -k=C3 -1

For full list of available options:

    makesfz -h

Once downloaded, make the script executable (e.g. right click the file and select Properties->Permissions) then copy to /usr/bin with:

    su -c 'cp makesfz /usr/bin'

or

    sudo cp makesfz /usr/bin

___

Make SFZ
========

This is a Nautilus script to invoke 'makesfz'. It assumes that makesfz is installed in /usr/bin and that xterm is available.

Near the top of the script are variables that may be modified if makesfz is installed somewhere other than /usr/bin or if you wish to use a terminal emulator other than xterm:

    MAKESFZ_FILEPATH="makesfz"
    TERMINAL_COMMAND="xterm -hold -title MakeSFZ -font 9x15 -e"

Once downloaded, make the script executable then move it to /usr/share/nautilus-scripts if Nautilus Scripts Manager is installed or to ~/.gnome2/nautilus-scripts to make the script permanently available.
