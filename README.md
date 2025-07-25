# LaTeX CV/Résumé

## VSCODE

- Install `LaTeX Workshop`
- Open `settings.json` in vscode
- Check `biber`, `pdflatex` in settings `latex-workshop.latex.tools`

```json
"latex-workshop.latex.tools": [
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "-outdir=%OUTDIR%",
        "%DOC%"
      ],
      "env": {}
    },
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ],
      "env": {}
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": [
        "%DOCFILE%"
      ],
      "env": {}
    },
    {
      "name": "biber",
      "command": "biber",
      "args": [
          "%DOCFILE%"
      ]
    }
  ],
```

- Make recipe in settings `latex-workshop.latex.recipes`

```json
  "latex-workshop.latex.recipes": [
    {
      "name": "pdflatex ➞ biber ➞ pdflatex`×2",
      "tools": [
        "pdflatex",
        "biber",
        "pdflatex",
        "pdflatex"
      ]
    }
  ],
```

## Requirements and Compilation

- pdflatex + biber + pdflatex
- AltaCV uses [`fontawesome`](http://www.ctan.org/pkg/fontawesome) and [`academicons`](http://www.ctan.org/pkg/academicons); they're included in both TeX Live 2016 and MikTeX 2.9.
- Loading `academicons` is optional: enable it by adding the `academicons` option to `\documentclass`.
- Use the `normalphoto` option to get a normal (i.e. non-circular) photo.
- Use the `ragged2d` option to activate hyphenations while keeping text left-justified; line endings will thus be less jagged and more aesthetically pleasing.
- Can now be compiled with pdflatex, XeLaTeX and LuaLaTeX!
- However if you're using `academicons`, you _must_ use either XeLaTeX or LuaLaTeX. If the doc then compiles but the icons don't show up in the output PDF, try compiling with LuaLaTeX instead.
- The samples here use the [Lato](http://www.latofonts.com/lato-free-fonts/) font.

## Prettify (LaTeX Workshop)

```
cpan YAML::Tiny
cpan File::HomeDir
```

## Reduce file

```
-dPDFSETTINGS=/screen   (screen-view-only quality, 72 dpi images)
-dPDFSETTINGS=/ebook    (low quality, 150 dpi images)
-dPDFSETTINGS=/printer  (high quality, 300 dpi images)
-dPDFSETTINGS=/prepress (high quality, color preserving, 300 dpi imgs)
-dPDFSETTINGS=/default  (almost identical to /screen)
```

- Ebook Size
```
/opt/homebrew/bin/gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH -sOutputFile=eunchurn_park_small.pdf eunchurn_park.pdf
```

- Printer size
```
/opt/homebrew/bin/gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH -sOutputFile=eunchurn_park_small_printer.pdf eunchurn_park.pdf
```

- Prepress size

```
/opt/homebrew/bin/gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/prepress -dNOPAUSE -dQUIET -dBATCH -sOutputFile=eunchurn_park_small_prepress.pdf eunchurn_park.pdf
```

## Latex To Markdown

```
pandoc -s eunchurn_park.tex -o ./eunchurn_park.md
pandoc -s portfolio.tex -o ./portfolio.md
pandoc -s portfolio_side.tex -o ./portfolio_side.md
```