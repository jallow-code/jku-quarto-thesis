# Background

This Git repository offers a Quarto template for writing bachelor’s, diploma, and dissertation theses. Originally adapted from a LaTeX template by [Eli Holmes](https://github.com/nmfs-opensci/quarto-thesis), this version has been customized to meet the specific requirements of Johannes Kepler University (JKU).

## Installing the extension

You will need to do this to get all the folders with tex files. Start in the directory where you will create the directory that will contain your thesis files. Run this from a terminal in that directory.

``` bash
quarto use template jallow-code/jku-quarto-thesis
```

It will ask for an empty directory name where to put the files, give it a new directory name.

Once you do that you can `cd` to the new directory and render from within the directory.

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

This template have bachelor thesis as a default. Therefore, to change it to a master or Phd dissertation you will the have to edit the `_extensions/quarto-thesis/partials/before-body.tex` file. Scroll down to the title page of the file and edit the line that contain thesis type.

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

This will leave out the dedication page from the rendered document. Checkout the pdf file in the repo to learn more about the usage of the template. You may have to write some `Latex` code to further customize this template if you have other specific requirements. [Eli Holmes](https://github.com/nmfs-opensci/quarto-thesis) made excellent video tutorials that you may find useful.

## Example

$$embed$$[Bachelor thesis](https://github.com/jallow-code/jku-quarto-thesis/blob/main/Synthesis-of-Hydrogels-by-Inclusion-Complexation-between-Poly-organo-phosphazenes-and-%24%CE%B1%24-cyclodextrin.pdf)$$/embed$$
