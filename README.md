# pandoc-secgroups

## installation

**Note**: it is assumed that [pandoc] and [pandoc-crossref] are already installed and that you know how to use them

1. Install panflute: `sudo pip3 install panflute`

2. Copy pandoc-secgroups in a folder included in PATH and make it executable: `sudo cp pandoc-secgroups /usr/local/bin/ && sudo chmod +x /usr/local/bin/pandoc-secgroups`

## usage

it has to be put *before* pandoc-crossref in pandoc filter chain

## syntax

see example.md


[pandoc]: https://github.com/jgm/pandoc
[pandoc-crossref]: https://github.com/lierdakil/pandoc-crossref/