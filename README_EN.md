# adsr
[leer en español](https://github.com/teaecetyrannis/pd-adsr/blob/main/README_EN.md)
<br><br>
object for generating adsr envelopes, inspired by the adsr~ object from max/msp, developed in [pure data](https://github.com/pure-data/pure-data)


## installation
download the adsr.zip from the [last release](https://github.com/teaecetyrannis/pd-adsr/releases), extract and add tge containing folder to pure data path, then it can be started in any patch by creating the `[granola~]` object


## operation
- the first inlet recives velocity (between 0 y 1, unless not scared of the possibility of distortion or phase inversion if using bigger or negative numbers respectively)
- the second inlet can take a series of messagess:
    - `[att $1(` attack time in ms
    - `[dec $1(` decay time in ms
    - `[sus $1(` sustain value (again between 0 y 1, otherwise distortion and phase inversion may occur)
    - `[rel $1(` release time in ms
    - `[legato $1(` turns legato on or off (non-zero and zero respectively, defaults to off)
    - `[anticlick $1(` turns on or off (nonzero and zero respectively, defaults to on) a ramp that goes to 0 in 10ms before the next attack when legato is off in order to avoid generating a click because of the immediate jump to 0
    - `[state(` writes in a message the current state of the object


## documentation
in the `[pd help]` subpatch inside adsr~.pd you will find all this same information and more


## credits
[pure data](https://github.com/pure-data/pure-data) by miller puckette y many others
