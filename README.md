# gforth-snap
gforth snap

run snapcraft in the current directory

$ snapcraft 
Using 'snapcraft.yaml': Project assets will be searched for from the 'snap' directory.
Launching a VM.
Launched: snapcraft-gforth                                                      
2019-05-02T15:46:56Z INFO Waiting for restart...
core 16-2.38.1 from Canonical✓ installed
snapcraft 3.4 from Canonical✓ installed
core18 20190409 from Canonical✓ installed

...

============= INSTALL SUCCEEDED =============
Bash users: type 'hash -r' to empty the cache
Staging gforth 
Priming gforth 
The 'gforth' part needs the following libraries that are not included in the snap or base: 
usr/lib/x86_64-linux-gnu/libltdl.so.7
These dependencies can be satisfied via more stage-packages, more parts, or content sharing.
Snapping 'gforth' \                                              
Snapped gforth_0.7.9-20190501_amd64.snap


Install with

$ sudo snap install gforth_0.7.9-20190501_amd64.snap --devmode
$ snap list
Name                   Version         Rev   Aufzeichnung  Herausgeber    Hinweise
core                   16-2.38.1       6818  stable        canonical✓     core
core18                 20190409        941   stable        canonical✓     base
gforth                 0.7.9-20190501  x1    -             -              devmode

Run with

$ /snap/bin/gforth


tested with ubuntu 18.04 (bionic).
