# Markdown Language

A great feature of the Jupyter Notebooks is that they can contain formatted text,  mathematical formula, and embedded images, via the use of the Markdown language.

Markdown is a rich language: a quick introduction to it is available here: https://guides.github.com/features/mastering-markdown/

Some quick points:

## Editting and typesetting
Within the Jupyter notebook, you simply type your text and Markdown symbols into a cell, and hit “shift-return” to typeset the cell into pretty text (and math). Click on the cell again to undo the typesetting, so you can edit and fix your text. Make sure, of course, that you have marked the cell as “Markdown” and not “Code.”

## Headers
Headers are made by starting the line with one or more hash marks #.

```
## This is a level-2 header, in text form
```

## Emphasis
Add emphasis by surrounding text with asterix or underscores.

`* italics * and ** bold **` yield * italics* and ** bold **.

### Lists
Type this:
```
- Apple
- Orange
- Pear
```
to get a list like this:

* Apple
* Orange
* Pear

Use numbers instead, to get an enumerated list


#### Web links
Type this `[GitHub](http://github.com)` to get a clickable weblink like this: [GitHub](http://github.com)

#### Images
Type this `![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)` to embedd an image into your webpage:, like this:
![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


#### Mathematics
Use the dollar sign `$`to indicate the start and end of LaTeX code for your math.

Here is the code for basic integral `$\int \cos(x) dx = \sin(x)$` which results in this display. $\int \cos(x) dx = \sin(x)$

To get the formula on a stand=alone line, use double dollar signs:
`$$\int \cos(x) dx = \sin(x)$$`
$$\int \cos(x) dx = \sin(x)$$

A cheat sheet with more details is available here:
<https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>
