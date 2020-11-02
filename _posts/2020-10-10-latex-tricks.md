---
layout: post
title: Latex Hacks - Bag of Tricks
share-img: /img/misc.jpg
tags: [latex, tricks, hacks, howtos]
---

### Mark certain bibliography items with asterisk (for example) marks

- Add `keywords={important}`in that particular entry in .bib file

  ```tex
  @inproceedings{bar,
    author       = {Bar},
    title        = {Bar},
    booktitle    = {Bar},
    year         = {2017},
    keywords     = {important},
  }
  ```

- Add the following command in the preamble section

```tex
\renewbibmacro*{begentry}{\ifkeyword{important}{\makebox[0pt][r]{\textasteriskcentered\addspace}}{}}
```

- Voila! [source](https://tex.stackexchange.com/questions/402765/how-do-i-mark-bibliography-entries-in-the-margin?rq=1)

### Add Markdown Support in Latex

- Add `markdown`package in the preamble

  ```tex
  \usepackage[T1]{fontenc}
  \usepackage[hybrid,smartEllipses]{markdown}
  ```

- Now you can create a markdown file, add all your contents and style in makrdown and link the `.md` file in the document section of your latex file using this command `\markdownInput{objective.md}`

- With the `hybrid` parameter, you can use latex code inside your markdown. Also, you need to escape latex-special characters if you choose to use hybrid parameter.

- For compiling, you need to add `--shell-escape`parameter from command-line like this:

  ```clike
  pdflatex --shell-escape main.tex
  ```

- You can also use a makefile, if you want to generate bibliography. Here's a sample Makefile:

  ```makefile
  notarealfile.pdf:
  	pdflatex --shell-escape main.tex
  	bibtex main
  	pdflatex --shell-escape main
  	pdflatex --shell-escape main

  clean:
  	rm -f *.pdf
  	rm -f *.dvi
  	rm -f *.toc
  	rm -f *.aux
  	rm -f *.bbl
  	rm -f *.log
  	rm -f *.blg
  	rm -f *.bak
  	rm -f *.out
  	rm -f *.ps
  	rm -f *.synctex.gz
  ```

- For more, check [overleaf](https://www.overleaf.com/learn/how-to/Writing_Markdown_in_LaTeX_Documents)
