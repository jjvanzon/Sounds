TODO
====

<h2>Contents</h2>

- [Main Outlines](#main-outlines)
- [Side Issues](#side-issues)
- [2023-05-18 TODO](#2023-05-18-todo)
- [2023-05-14 Brainstorm Doubts](#2023-05-14-brainstorm-doubts)
- [WAV conversion options](#wav-conversion-options)
- [RAW to WAV Utility](#raw-to-wav-utility)

Main Outlines
-------------

Handing 8-bit and 16-bit in the tracker programs is not very easy.

- [x] Categorizing
- [ ] .. Sensible names
- [ ] .. Naming scheme (8-bit, 16-bit, mono, stereo)
    - [ ] 8: 8-bit
    - [ ] 16: 16-bit
    - [ ] S: stereo
    - [ ] L: left 
    - [ ] R: right
    - [ ] C: chord
    - [ ] 01, 02, 03: numbering within categoy
    - [ ] X, Y: yet to be numbered
    - [ ] A, B: variations
    - [ ] ' : suffix meaning 'almost the same sound'
    - [ ] _ prefix against ambiguity (e.g. THING2_8)
-  [ ] Formats:
    - [x] IT sample
    - [ ] .. IT instrument
    - [ ] RAW
    - [ ] WAV
    - [ ] ~ FT sample
    - [ ] ~ FT instrument
    - [ ] ~ ST sample
    - [ ] ~ ST instrument


Side Issues
-----------

- [ ] Loops
- [ ] Vibrato / effects
- [ ] Samples => instruments
- [ ] Tuning


2023-05-18 TODO
---------------

- [x] WAVEFORM: 
    - [x] Set loops
    - [x] Make instruments
- [ ] Short (16-bit SB) sounds:
    - [ ] (Ones poorly usable without modification.)
    - [x] Set loops
    - [x] Set vibrato
    - [ ] .. Make instruments
    - [ ] __WAS AT: DRUMS (going up)__
- [ ] 16-bit raw:
    - [ ] Poorly usable now (in Impulse Tracker for instance)
    - [ ] Convert to WAV
    - [ ] Set names
    - [ ] Make IT files
- [ ] Make wave tables (in IT) ?
- [ ] More loops ?
- [ ] More vibrato ?
- [ ] Tune ?
- [ ] Improve loops ?


2023-05-14 Brainstorm Doubts
----------------------------

In case of ambiguity between acoustic, synth and generated sounds of the same type of instrument: I guess the character of the sound is what matters most.


WAV conversion options
----------------------

- WAV16STJ.EXE:
    - Downside: Only does 16 bit it seems.
- Audacity:
    - Downside: Lots of clicking per file.
- Existing utilities
    - <https://www.nchsoftware.com/howto/convert/raw_to_wav_files.html#:~:text=Click%20on%20the%20green%20Add%20File%20%28s%29%20button%2C,into%20the%20program%20to%20convert%20them%20as%20well.>
    - Downside: Seems they are complicated.
- Program utility:
    - Using JJ.Synthesizer logic.
    - Downside: Programming. Lots of decisions about tiny details might overwhelm me.


RAW to WAV Utility
------------------

Options:

- Input file path
- Output file path
- Mono/stereo
- 8-bit/16-bit
- Sampling rate

Limited to those options. Perhaps input format / output formats RAW/WAV, but derive format if recognized.

- Using JJ.Synthesizer.
- Using WavHeaderFacade.CreateWavHeaderStruct
- (Ideal would be NuGet package JJ.Synthesizer.Business, create new repo for utility, but:)
- Put in JJ.Synthesizer repo to omit lots of infra setup.

Perhaps add a method to facade once I've facaded it all.

This is hard.

Maybe I park this for now.

----

Problems:

- [ ] Using JJ.Framework.WinForms .NET 4.6.1 in a .NET 7 project: Designer fails to load.
- [ ] Using JJ.Framework.WinForms .NET 4.6.1 in a .NET 4.6.1 project: Designer load crashes Visual Studio.

I guess it is upgrade or fall behind.

This takes quite some engineering and stuff man.

Will I do it?

The idea is to just upgrade to the latest .NET version.
And the rest of us just use the latest compatible version and that's it.

Upgrading probable comes with its own errors and 'engineering' them away.

-----

I used .NET 8, which DevOps does not support.

Alternatives:

- Target .NET 7 in the csproj files after all.
- Use a different DevOps build task to targeting .NET 7 specifically (trying to follow ChatGPT's tip).
