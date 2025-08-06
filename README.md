Project KDS-1
=============

Why?
----

I'm several decades late, but here it is anyway: my own software synthesizer
project. At the time of writing, there are many synths out there which feel like
they are going 90% in the direction I want but fall short on a number of little
things. Some really great ones are simply hidden behind a paywall and not
available to hobbyists and the open source community. Some just lack one or two
features that would make them really great. Some are just blatantly bad, either
in implementation or in coding style or the UI is very unfun to use. So here's
my best shot.

What the Acronym?
-----------------

It's "Kirby's Dream Synth Mark One". The name is a hint at one of my favorite
video game characters and games and also captures the intended use for making
chiptunes (or fakechips, if you will). Coincidently "Kirby" is also part of the
name of my favorite music artist [DDRKirby(ISQ)](https://ddrkirby.com/) to whom
this work is dedicated to and who gave me the motivation for this project.

Core Concepts
-------------

A good part of this work is based on topics detailed in Tim Stilson's PhD
thesis from 2006 at Stanford "Efficiently-Variable Non-Oversampled Algorithms In
Virtual-Analog Music Synthesis - A Root-Locus Perspective". At its heart,
Bandlimited Impulse Trains via the sum of windowed sincs (BLIT-SWS) are used to
efficiently generate the base signals. The usual stack of filters, effects,
envelopes and LFOs take it from there. As such the synthesizer can't be
classified as additive or subtractive but would be placed somewhere in between.

In addition to their pure forms, this synthesizer will allow to set the triangle
and sawtooth waves into a stepped mode which allows it to emulate the
characteristics of NES sound hardware. Furthermore, triangle and sawtooth are
combined into one waveform with variable slope.

Envelopes and LFOs are designed to give the musician some great degree of
freedom as they not only can be hooked to pretty much everything, including the
pulse width and tri/saw slope, but they can also be of an arbitrary shape with
any number of sampling points and interpolation between them.

Finally, all settings can be mapped to specific ranges of notes which can
effectively turn the synth into a drumset.

How To Use
----------

KDS-1 will be distributed as VST3, AU and FL Studio plugins as well as a library
and standalone version. The separate FL Studio version is necessary to account
for slide notes which are a unique feature there.

Compiling
---------

KDS-1 is written in portable C code at its core. The standalone version depends
on [RtMidi](https://github.com/thestk/rtmidi) and
[RtAudio](https://github.com/thestk/rtaudio). The plugins require their
respective SDK. Both standalone and plugins depend on
[Ultralight](https://ultralig.ht/) until I find a better way to render the GUI.
Consequently, the GUI is written in TypeScript with Vue. Everything will
require [CMake](https://cmake.org/) and a working C compiler.

TODO List
---------

- [x] Write this readme
- [ ] Setup CMake stuff
- [ ] Setup GUI stuff
- [ ] Setup RtMidi, RtAudio and standalone version
- [ ] Write core oscillator code
- [ ] Write simple envelope and LFO code
- [ ] Write complex envelope and LFO code
- [ ] Hook everything up with FL Studio
- [ ] Plan next steps
