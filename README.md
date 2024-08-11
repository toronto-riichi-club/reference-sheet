# Riichi Reference Sheets

Reference sheets for [Japanese mahjong][] written in XeTeX.
These sheets are intended to be useful as a quick reference guide while playing.

These sheets are optimized for the [ruleset used by the Toronto Riichi Club][tori-rules],
but it should be widely applicable to most rulesets with a few minor variations.
A sheet based on the WRC ruleset is also available.

**Download the latest PDF from the [releases page][releases].**

[Japanese mahjong]: http://arcturus.su/wiki/Japanese_mahjong
[tori-rules]: https://www.torontoriichi.club/rules/
[releases]: https://github.com/toronto-riichi-club/reference-sheet/releases

* * *

The information below is relevant only if you want to modify the sheets.
Simply to use them, you can get a PDF copy from the releases page as outlined above.

## Prerequisites

* [XeTeX](https://ctan.org/pkg/xetex) with CJK libs (available in TeX distributions such as [TeX Live](https://www.tug.org/texlive/))
* [Libertinus Serif](https://github.com/alerque/libertinus) (font)
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

## Customization

Certain portions of the sheet can be customized to better fit certain rulesets.
See the preamble of the [WRC sheet][] for an example on usage.

[WRC sheet]: ./wrc-refsheet.tex

### Title

You can customize the title by defining the `\thetitle` macro _before_ including `preamble.tex`.
The default title is "Riichi Reference Sheet".

```tex
\def\thetitle{Riichi Reference Sheet}
```

### Starting points

You can customize the count beside the 1000-point sticks to match your ruleset's starting point value
by defining the `\sentencount` macro _after_ including `preamble.tex`.

The default number is `4` for 25000 points; set it to `9` to start at 30000 points.

```tex
\def\sentencount{4}
```

### Rule toggles

There are a number of toggles available to turn on and off certain rules.
These toggles are defined using [`\newif`][newif] in `includes/preamble.tex`.

| Toggle | Default | Description |
| ------ | ------- | ----------- |
| `doublewind`    | `true`  | [Double wind fu][]: A wind pair that is both the seat and round wind counts as 4 fu (as opposed to just 2 fu). |
| `kazoeyakuman`  | `true`  | [Kazoe yakuman][] (counted yakuman): Hands worth 13+ han are scored as yakuman. |
| `kiriagemangan` | `false` | [Kiriage mangan][] (rounded mangan): Hands worth 3 han 60 fu or 4 han 30 fu are rounded up to a mangan. |
| `nagashimangan` | `true`  | [Nagashi mangan][] (discards mangan): Hands with terminal/honour discards after exhaustive draw are worth a mangan. |

For example, to disable kazoe yakuman and enable kiriage mangan,
add the following to the preamble _after_ including `preamble.tex`:

```tex
\kazoeyakumanfalse
\kiriagemangantrue
```

[newif]: https://tex.stackexchange.com/a/5896
[Double wind fu]: https://riichi.wiki/Scoring_variations#Double_wind_fu
[Kazoe yakuman]: http://arcturus.su/wiki/Kazoe_yakuman
[Kiriage mangan]: http://arcturus.su/wiki/Scoring_table#Kiriage_mangan
[Nagashi mangan]: http://arcturus.su/wiki/Nagashi_mangan

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
