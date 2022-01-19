# estwrite
Stata module to store estimation results on disk

`estwrite` exports models previously fitted and stored by estimates store to a
file on disk. `estread` is used to reimport the saved estimates.

To install the `estwrite` package from the SSC Archive, type

    . ssc install estwrite, replace

in Stata. Stata version 8.2 or newer is required.

---

Installation from GitHub:

    . net install estwrite, replace from(https://raw.githubusercontent.com/benjann/estwrite/master/)

---

Main changes:

    19jan2022
    - option -reproducible- added, as suggested by Brian Quistorff (see pull
      request #3)

    17apr2020
    - installation files added to GitHub distribution

    25jun2012
    - estread did not read the correct models if syntax -estread names using ...-
      was used and the sets were in ster-format, because it just read the sets one
      by one and did not skip over unwanted sets. This is fixed.

    04sep2009
    - estwrite/estread now works in Stata 11

    09dec2008
    - fixed bug with string ID variables in -estwrite-
    - added -describe- option to -estread-
    - -estread namelist using filename- now possible

    04dec2008
    - -estread- can now import estimates without e(b) written by -estwrite, alt-
    - -break- now allowed within loops in -estwrite- and -estread-
    - now sets e(cmd) to "." if undefined
    - now works with -stcox- without covariates
    - estwrite without -using- now allowed

    29oct2008
    - new version based on __st_estimatessave_wrk() and __st_estimatesuse_wrk()
    - ster => noster => alt
    - e()'s starting with "_" are now preserved
    - noster => ster
    - store estimates as Mata file (unless < Stata 9 or -estsave-)
    - "using" in "estread using" now optional
    - label() option now undocumented (works only with estsave)

    27mar2008
    - estwrite: did not drop obs.
    - estwrite: now works if dataset has zero obs
    - estwrite: bug with titles of stored estimates fixed
    - estwrite now set varabbrev off before invoking estsave. This fixes an estsave bug.
    - renamed: eststo->estwrite; estget->estread
    - append option added

    29apr2005
    - released on SSC
