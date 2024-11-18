# Background

This git repo provides a template for writing bachelor or diploma thesis using Quarto. Originally adapted from a LaTeX template by [Eli Holmes](https://github.com/nmfs-opensci/quarto-thesis), I tailored it to meet JKU’s requirements. The template can also be use for phd desertation (orginal design).

## Installing the extension

You will need to do this to get all the folders with tex files. Start in the directory where you will create the directory that will contain your thesis files. Run this from a terminal in that directory.

``` bash
quarto use template jallow-code/jku-quarto-thesis
```

It will ask for an empty directory name where to put the files, give it a new directory name.

Once you do that you can cd to the new directory and render from within the directory.

``` bash
quarto render
```

You may encounter the following error message when you first render the document:

`ERROR:  compilation failed- missing packages (automatic installed disabled)       LaTeX Error: Something's wrong--perhaps a missing \item.  See the LaTeX manual or LaTeX Companion for explanation. Type  H <return>  for immediate help.  ...  l.872 \end{CSLReferences}`{=}

This have to do with your version of `Quarto` and `Tinytex` . To fix this issue you will have to update your tinytex package or the Quarto version you are using. See [here](https://yihui.org/tinytex/) to learn how to install or maintain `TinyTex`.

## Installation or updating for an existing document

You may also use this format with an existing Quarto project or document. But you will need to have all the tex folders already (see above).

``` bash
quarto install extension jallow-code/jku-quarto-thesis
```

## Basic Usage and Customization

The template have bachelor thesis as a default. Therefore, to change it to a master or Phd dissertation you will the have to edit the `_extensions/quarto-thesis/partials/before-body.tex` file. Scroll down to the title page of the file and edit the line that contain thesis type.

%----------------------------------------------------------------------------------
%	TITLE PAGE
%----------------------------------------------------------------------------------

\begin{titlepage}
\begin{center}

% Add the logo at the top center
$if(thesis.logo)$
$if(thesis.logo-height)$
\includegraphics[height=$thesis.logo-height$]{$thesis.logo$} % University/department logo
$else$
\includegraphics[width=0.1\textwidth]{$thesis.logo$} % Adjust the width to make the logo smaller
$endif$
$endif$

\vspace*{.06\textheight}
{\scshape\LARGE \univname\par}\vspace{1.5cm} % University name
\textsc{\Large BACHELOR THESIS}\\[0.5cm] % Thesis type

\HRule \\[0.4cm] % Horizontal line
{\LARGE \bfseries \ttitle\par}\vspace{0.4cm} % Thesis title, changed from \huge to \LARGE
\HRule \\[1.5cm] % Horizontal line

Additionally, you may want to exclude some sections of the frontmatter (e.g dedication, constants etc..). This can be achieved simply by commenting out that section from the `_quarto.yml`:

---
thesis:
  supervisor:
    primary: "Assoz. Univ.-Prof. Dr. Ian Teasdale"
    co: "Dipl.-Ing. Michael Kneidinger"
  degree-name: Bachelor of Science
  university: Johannes Kepler Universität Linz
  department: Institute of Polymer Chemistry
  url: "https://www.jku.at/en/institute-of-polymer-chemistry/" #Institute url
  group: Biological Chemistry # program
  faculty: Faculty of Engineering and Natural Sciences
  declaration: "Frontmatter/declaration.tex"
  quotation:
    text: "We make our progress through explanatory conjectures and criticism. And, as Popper says, by letting our ideas 'die in our place'. "
    attribution: David Deutsch
  acknowledgements: "Frontmatter/acknowledgements.tex"
  abbreviations: "Frontmatter/abbreviations.tex"
  symbols: "Frontmatter/symbols.tex"
  #dedication: "Frontmatter/dedication.tex"
  logo: images/logo.png
  logo-height: "3cm"
---

This will leave out the dedication page from the rendered documents. Checkout the pdf file in the repo to learn more about the usage of the template. You may have to write some `Latex` code to further customize this template if you have other specific requirements. [Eli Holmes](https://github.com/nmfs-opensci/quarto-thesis) also excellent video tutorials you may find useful.

## Example

![](Synthesis-of-Hydrogels-by-Inclusion-Complexation-between-Poly-organo-phosphazenes-and-$α$-cyclodextrin.pdf)
