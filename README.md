# edition-engraver: Editorial tweaks for Lilypond

This package adds commands for tweaking arbitrary score elements externally, in order to facilitate editorial operations.

This repository is a fork of [edition-engraver](https://github.com/openlilylib/edition-engraver), a part of [openLilyLib](https://github.com/openlilylib).

## What it is

The edition-engraver is used to apply or inject layout modifications to a score without polluting the musical source with tagged overrides. The external overrides are themself tagged with an edition-target-id, so they can be easily activated or deactivated.

## Installation

Install using [lyp](https://github.com/noteflakes/lyp)

```bash
lyp install edition-engraver
```

## Usage

```lilypond
\require "edition-engraver"

\addEdition test
\editionMod test 1 2/4 sing.with.bach.along.Voice.A \override NoteHead.color = #green
...

% Use the edition-engraver in a number of contexts.
\consistEE Score.Staff.Voice

...
```

Yes, documentation is lacking. For more information see the included [example](https://github.com/noteflakes/lyp-edition-engraver/blob/master/test/example-1.ly)

## Current state

The current implementation is developed from scratch. It is now (2016-03-08) able to do almost the same, as the edition-engraver found in `openlilylib/editorial-tools/edition-engraver`. It should be seen as an alpha-version.

## Development

The edition-engraver shall be developed for relative mods in time - e.g. apply mod 3/4 quarters beyond mark X. And it shall deal with ids to apply tweaks to designated grobs or objects.
