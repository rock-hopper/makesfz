makesfz
=======

BASH script to auto-generate SFZ files

This an updated version of danboid's original script http://www.remastersys.com/forums/index.php?topic=1951.0
It allows a key range and the "key center" to be specified, a specific MIDI channel can be set, and either wav or ogg files can be used.
Keys can be either the key name (# or b allowed) or MIDI key number.

For example, to set a key range from C2 - C5:
makesfz --lk=C2 --hk=C5

Or to create a single .sfz where the first sample starts on C3 and "one shot" is required:
makesfz -s -k=C3 -1

For full list of available options:
makesfz -h
