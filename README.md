# gforth-snap

Gforth as a Snap package.

## From snapstore

```
  $ snap search gforth
  Name           Version         Publisher  Notes  Summary
  gforth-mtrute  0.7.9-20190501  mtrute     -      gforth snap

  $ snap info gforth-mtrute
  name:      gforth-mtrute
  summary:   gforth snap
  publisher: mt (mtrute)
  license:   GPL-3.0+
  description: |
    This is gforth snap
  commands:
    - gforth-mtrute.gforth
  snap-id:      cXf2H05AAoRzw6TOwmRucmuqHqkPJ0YQ
  tracking:     edge
  refresh-date: today at 11:30 CEST
  channels:
    stable:    --                                
    candidate: --                                
    beta:      --                                
    edge:      0.7.9-20190501 2019-05-04 (3) 3MB -
```

## Run gforth

  Install the snap with sudo
```
  $ sudo snap install --edge gforth-mtrute  
  gforth-mtrute (edge) 0.7.9-20190501 from mt (mtrute) installed

  $ snap list
  Name                   Version         Rev   Tracking     Publisher      Notes
  core                   16-2.38.1       6818  stable       canonical*     core
  core18                 20190409        941   stable       canonical*     base
  gforth-mtrute          0.7.9-20190501  3     edge         mtrute         -
```

Tested with Ubuntu 18.04 (bionic).


  $ /snap/bin/gforth-mtrute.gforth 
  Gforth 0.7.9_20190501, Copyright (C) 1995-2018 Free Software Foundation, Inc.
  Gforth comes with ABSOLUTELY NO WARRANTY; for details type `license'
  Type `help' for basic help
  version-string   ok 2
  type 0.7.9_20190501 ok
  bye 
  $
```

This snap has the right to access the network and the files within HOME.

## Building

you'll have to be me for that ;). If you want to build you own version,
make sure to replace the string mtrute with your name.

```
  $ snapcraft status gforth-mtrute
  Track    Arch    Channel    Version         Revision
  latest   amd64   stable     -               -
                   candidate  -               -
                   beta       -               -
                   edge       0.7.9-20190501  3

```

I run snapcraft in the project directory while being logged in.

```
  $ snap whoami 
  E-Mail: m_trute@yahoo.de
  $ snapcraft 
  Using 'snapcraft.yaml': Project assets will be searched for from the 'snap' directory.
  Launching a VM.
  Launched: snapcraft-gforth-mtrute                                                      
  2019-05-02T15:46:56Z INFO Waiting for restart...
  core 16-2.38.1 from Canonical✓ installed
  snapcraft 3.4 from Canonical✓ installed
  core18 20190409 from Canonical✓ installed

  ...

  ============= INSTALL SUCCEEDED =============
  Bash users: type 'hash -r' to empty the cache
  Staging gforth 
  Priming gforth 
  Snapping 'gforth-mtrute' \                                              
  Snapped gforth-mtrute_0.7.9-20190501_amd64.snap
  $ snapcraft push --release=edge gforth-mtrute_0.7.9-20190501_amd64.snap
  Preparing to push 'gforth-mtrute_0.7.9-20190501_amd64.snap'.
  After pushing, an attempt will be made to release to 'edge'
  Pushing 'gforth-mtrute_0.7.9-20190501_amd64.snap' [=======================] 100%
  Processing...|                                                                  
  Ready to release!
  Revision 1 of 'gforth-mtrute' created.
  Track    Arch    Channel    Version         Revision
  latest   amd64   stable     -               -
                   candidate  -               -
                   beta       -               -
                   edge       0.7.9-20190501  1
  The 'edge' channel is now open.
  $
```

The revision number increases with every snapcraft upload, so expect higer
numbers. 