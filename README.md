# Riichi Reference Sheets

Reference sheets for [Japanese mahjong][] written in XeTeX.
These sheets are intended to be useful as a quick reference guide while playing.

These sheets are optimized for the ruleset used by the [Toronto Riichi Club][TORI],
but it should be widely applicable to most rulesets with a few minor variations.
A sheet based on the WRC ruleset is also available.

**Download the latest PDF from the [releases page][releases].**

[Japanese mahjong]: http://arcturus.su/wiki/Japanese_mahjong
[TORI]: https://www.torontoriichi.club/
[releases]: https://github.com/toronto-riichi-club/reference-sheet/releases

* * *

The information below is relevant only if you want to modify the sheets.
Simply to use them, you can get a PDF copy from the releases page as outlined above.

## Prerequisites

* [XeTeX](https://ctan.org/pkg/xetex) with CJK libs (available in TeX distributions such as [Tex Live](https://www.tug.org/texlive/))
* [Linux Libertine](http://libertine-fonts.org/) (font)
* [Hanazono Mincho](https://www.freejapanesefont.com/hanazono-mincho-%E8%8A%B1%E5%9C%92%E6%98%8E%E6%9C%9D/) (CJK font)

## Building

The easiest way to build is by using [`latexmk`](https://mg.readthedocs.io/latexmk.html):

```sh
latexmk
```

If you prefer not to use `latexmk`, you can build using `xelatex` directly:

```sh
xelatex riichi-refsheet
xelatex wrc-refsheet
```

Using either command will produce PDF files called `riichi-refsheet.pdf` and `wrc-refsheet.pdf`.

* * *

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International][CC BY-SA 4.0] License.

## Acknowledgements

This sheet is based on the reference sheet by [Alexis "alercah" Hunt][alercah], licensed under the [CC BY-SA 4.0][].

The tile images used were created by [FluffyStuff][], licensed under the [CC BY 4.0][].

[alercah]: https://csclub.uwaterloo.ca/~aechunt/ref-wrc.pdf
[FluffyStuff]: https://github.com/FluffyStuff/riichi-mahjong-tiles
[CC BY-SA 4.0]: https://creativecommons.org/licenses/by-sa/4.0/
[CC BY 4.0]: https://creativecommons.org/licenses/by/4.0/
