Forked from https://github.com/dcroote/stanford-thesis-example

Two style files are provided:
- `suthesis-2e-dcroote.sty` is the one provided with this template (Modified from Derek Croote 2019 from the Emma Pease 2014 version).
- `suthesis-2e.sty` is the "official" template by [Stanford](https://library.stanford.edu/research/bibliography-management/latex-bibtex-and-overleaf) (Emma Pease 2016)


## subfiles

One of the main changes in this fork is structuring the chapters using the `subfiles` package instead of using the more common `\input` or `\include`. This package provides the functionality of allowing compilation of individual chapters, which can significantly speed up compilation times for a long thesis.

In order to use `subfiles`, some particular choices in the folder structure are needed. For example, It is more convenient to place all `.tex` sources (including the `main.tex` file as well as individual chapters) in the same folder, so that relative paths to resources (e.g. figures and bibliography files) are constant from all source files, allowing any of them to be compiled as the main file without modification.

Similarly, it would be convenient to move the style files to their own subdirectory, e.g. `sty/suthesis-2e.sty`. However, this requires importing the package in the `.tex` files as `\usepackage{../sty/suthesis-2e}` instead of `\usepackage{suthesis-2e}`, which works but produces the LaTeX warning "You have requested package `../style/suthesis-2e', but the package provides `suthesis-2e'".
There are many workarounds for this but they are inconvenient enough 

Resources:
- [https://www.overleaf.com/learn/latex/Multi-file_LaTeX_projects](https://www.overleaf.com/learn/latex/Multi-file_LaTeX_projects)
- [https://en.wikibooks.org/wiki/LaTeX/Modular_Documents#Separate_compilation_of_child_documents](https://en.wikibooks.org/wiki/LaTeX/Modular_Documents#Separate_compilation_of_child_documents)

## biblatex

This fork also moves from BibTeX to the `biblatex` package, which is a more modern and better option.
It additionally integrates more easily with `subfiles`.

Resources:
- [https://www.overleaf.com/learn/latex/Articles/Getting_started_with_BibLaTeX](https://www.overleaf.com/learn/latex/Articles/Getting_started_with_BibLaTeX)
- [https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)
- [https://en.wikibooks.org/wiki/LaTeX/Bibliographies_with_biblatex_and_biber](https://en.wikibooks.org/wiki/LaTeX/Bibliographies_with_biblatex_and_biber)
- [https://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib](https://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib)

# Stanford LaTeX Thesis Example

[![Build status](https://github.com/dcroote/stanford-thesis-example/workflows/CI/badge.svg?branch=master)](https://github.com/dcroote/stanford-thesis-example/actions?query=workflow%3ACI+branch%3Amaster)

## Preview
[View the latest PDF](https://github.com/dcroote/stanford-thesis-example/releases/latest/download/thesis-example.pdf) or click on the image below.

[![Thesis preview](preview.png)](https://github.com/dcroote/stanford-thesis-example/releases/latest/download/thesis-example.pdf)

## About
The hope is that this example thesis saves you time that I and countless others before me spent on the minutiae of writing a thesis in LaTeX. It combines a slightly modified version (more on this below) of the existing [Stanford thesis style](https://www.stanford.edu/dept/sul2/etdhelpupload/0/06/Suthesis-2e.sty) ([more Stanford information here](https://library.stanford.edu/research/bibliography-management/latex-bibtex-and-overleaf)) with a template for including figures, tables, inline references, equations, symbols, a bibliography, a signature page, etc...
I used this style as the basis for my (officially completed) thesis and thus believe it adheres to Stanford's policies, but I make no guarantees.

This thesis defaults to electronic submission using `\onlinetrue` in `suthesis-2e.sty`. Correspondingly, the copyright and signature pages *ii* and *iii*, respectively, are excluded as they are [added by the Library](https://registrar.stanford.edu/students/dissertation-and-thesis-submission/electronic-dissertationthesis-faq) upon submission. The last page of this example thesis is a signature page you can print, but remember to comment out `\onlinesignature` in `main.tex` before uploading your final version. **Remember to print the signature page on acid-free paper.** Likewise for the title page.

### Structure
This template adopts a modular structure where each chapter is a separate `.tex` file that is included by `main.tex`. Figures are similarly organized by publication or project. Citing references requires a bibliography in BibTeX format, which can be generated by exporting an existing collection from a reference manager such as [Mendeley](https://blog.mendeley.com/2012/03/24/how-to-series-generate-bibtex-files-for-your-collections-for-use-in-latex-part-3-of-12/), F1000, etc...

## Usage
1. Install LaTeX on your system, use a [Docker image](https://hub.docker.com/r/dxjoke/tectonic-docker), or use an online service like [Overleaf](https://www.overleaf.com). I used Overleaf because compilation is fast and simple.
2. Clone / download this repository, and if you are using an online service, upload the files.
3. Read `main.tex` and update it with your information. Add your bibliography, figures, and chapter text. There should be no need to further modify the Stanford style file `suthesis-2e.sty`.
4. Finish and submit thesis.

## Contributions
Pull requests are welcome for improvements or additions that will benefit others.

## Testing
This example thesis is compiled with [GitHub Actions](https://github.com/dcroote/stanford-thesis-example/actions), specifically the [GitHub Action for LaTex](https://github.com/marketplace/actions/github-action-for-latex) containing a full TeXLive environment.
