# pandoc-secgroups

## Description

This is a Pandoc filter that allows user to collect number and title of certain marked headings and to display a list containing such information at some point in the same text.

Suppose you are writing a contract and wish to list all clauses that would cause the contract to be terminated. If you mark each heading with a certain code (eg "term"), you can then set a pointer (eg @term in this case) within the corresponding termination clause and have a neat, consistent and updated list of such clauses. You can have multiple such lists, and even include the same heading in more than one list.

Users of [pandoc-vex] should soon replace that filter with this one, which is more generalised, allows multiple lists and to put the pointer wherever in the text and not just below the last marked heading.

## installation

**Note**: it is assumed that [pandoc] and [pandoc-crossref] are already installed and that you know how to use them

### New lua filter (RECOMMENDED)

Simply copy `secgroups.lua` to `~/.pandoc/filters`

### Old python filter (LEGACY)

1. Install panflute: `sudo pip3 install panflute`

2. Copy pandoc-secgroups in a folder included in PATH and make it executable: `sudo cp pandoc-secgroups /usr/local/bin/ && sudo chmod +x /usr/local/bin/pandoc-secgroups`

## usage

The filter must be put *before* pandoc-crossref in pandoc filter chain.
If you use the new lua filter (recommended), put `--lua-filter=secgroups.lua` in your pandoc command.

If you still want to use the old (legacy) python filter, use `--filter=pandoc-secgroups` instead - but it is not recommended, since the new lua filter may be almost 3 times faster.

## syntax

see example.md

Please note the YAML statement

``` yaml
secGroupTags:
- vex
- cons
```
the part in curly brackets after the section reference (`{#sec:AA vex=1}`) and the `@vex` and `@cons` pointers within the text.

[pandoc-vex]: https://github.com/alpianon/pandoc-vex
[pandoc]: https://github.com/jgm/pandoc
[pandoc-crossref]: https://github.com/lierdakil/pandoc-crossref/
