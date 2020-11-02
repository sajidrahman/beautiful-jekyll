---
layout: post
title: Latex Hacks - Bag of Tricks
share-img: /img/misc.jpg
tags: [latex, tricks, hacks, howtos]
---

- Mark certain bibliography items with asterisk (for example) marks

  - Add `keywords={important}`in that particular entry in .bib file

    ```latex
    @inproceedings{bar,
      author       = {Bar},
      title        = {Bar},
      booktitle    = {Bar},
      year         = {2017},
      keywords     = {important},
    }
    ```

  - Add the following command in the preamble section

      ```latex
  \renewbibmacro*{begentry}{\ifkeyword{important}{\makebox[0pt][r]{\textasteriskcentered\addspace}}{}}
      ```

  - Voila! [source](https://tex.stackexchange.com/questions/402765/how-do-i-mark-bibliography-entries-in-the-margin?rq=1)

