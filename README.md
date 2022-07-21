# md2pdf
Markdown to PDF templates

These are Markdown Templates with YAML headers, for ease of use to convert to LaTeX using pandoc and then to PDF using pdflatex.

## Requirements 

A LaTeX environment and [pandoc](https://pandoc.org/) need to be installed. To use proper references, fig’s and BibTeX-files, the [pandoc-crossref filter](https://github.com/lierdakil/pandoc-crossref) also needs to be installed. The Letter / Brief - Templates requires the use of the `scrlttr2.latex` file, copied from [JensErat](https://github.com/JensErat/pandoc-scrlttr2).

## Export using Typora

Go to the Export Settings and add 2 or 3 new Exporters (“PDF LaTeX / Pandoc”). Name one of them “PDF (Pandoc)”, optional an extra “PDF (Pandoc) + toc” and “PDF Letter (Pandoc)”. All of them already have the basic arguments supplied to them: 

`-f native -s -o ${outputPath}`

The PDF Engine needs the path to your pdf generator, for example pdflatex. An example in Windows using MikTeX would be `C:\tools\LaTeX\miktex\bin\x64\pdflatex.exe`.

The exporter “PDF (Pandoc)” should get the following extra arguments: `-N --highlight-style haddock`, and the  “PDF (Pandoc) + toc” should get `--toc -N --highlight-style haddock`. This way, you can select the pdf export with- or without the generation of the table of contents. For additional arguments, see below.

The “PDF Letter (Pandoc)” needs the extra Template field in the Typora settings set to the `scrlttr2.latex`.

## Export using pandoc

Pandoc can also be used manually in the Terminal. A common pandoc call would look like this: 

```powershell
pandoc --toc -N --highlight-style haddock -f native -s -o homework.pdf
```

Arguments: 

- `--toc` generate a table of content between title and beginning (*optional*)
- `-N` enumerate all headings (*optional*)
- `--highlight-style haddock` set the [code block style](https://stackoverflow.com/questions/30880200/pandoc-what-are-the-available-syntax-highlighters)  (*optional*)
- `-f` specifies the conversion *from* which format. Usually contains the format and is followed by the Pandoc extensions used
- `-s` to create a standalone LaTeX document, which then gets compiled into a pdf
- `--template scrlttr2` include the Letter-Template
- `-o` output file name

## Use of Cross-references and BibTeX Systems

The YAML at the beginning of the Markdown Document needs to be extended with two definitions for a BibTeX file as well as a CSL (Citation Style Language) definition file. Many common citation styles can be found in the [Zotero Style Repository](https://www.zotero.org/styles).

```yaml
bibliography: my.bib
csl: ieee.csl
```

The pandoc command needs to be extended by a few new flags, making it a rather lengthy thing.

- `-s` to create a standalone LaTeX document. This is now non-optional.
- `-F pandoc-crossref` to make use of the filter `pandoc-crossref`
- `--natbib` to render the bibliography with `natbib` (you can also choose `--biblatex`)
- `-t` usually contains the output format and is followed by the Pandoc extensions used. In the example, we declared `raw_tex+tex_math_dollars+citations` to allow use of `raw_tex` LaTeX in the middle of the Markdown file. `tex_math_dollars` enables us to type math formulas as in LaTeX, and `citations` enables us to use –citeprog

A full new pandoc command would look like this: 

```powershell
pandoc -s -F pandoc-crossref --natbib --toc -N -f markdown -t
latex+raw_tex+tex_math_dollars+citations 
--highlight-style haddock -o document.tex
```

### Executing LaTeX commands within the Markdown documents

I have not found a proper way to achieve this, and most of the time it can be worked around. One of the biggest issues with this is the missing `\newpage` command, either in the middle of your document, or before a new `\section`. Both do not work out that well. 

If the document is lengthy or important enough to require the use of `\newpage`, then I recommend taking the easy way out and using pandoc to convert the document into a LaTeX file and manually adding the `\newpage` command.

Another problem I found was the use of the **titling-Package** to save the variables of Author, Date and Title for use through the document, especially in the header. While this works fine by itself, using the **titlesec-Package** to redefine the style of a heading, like `\section`, will have the titlesec-Package overwrite the content of the `\thetitle`-Variable from the titling-Package. 

Example of viable use of the titlesec-package within the Markdown-YAML: 

```latex
%% redefine the style of the section header %%
\usepackage{titlesec}
\titleformat{\section}
  {\normalfont\large\bfseries}{\thesection.}{1em}{}[\titlerule]
\titleformat{\subsection}
  {\normalfont\normalsize\itshape}{\thesubsection.}{1em}{}
\titleformat{\subsubsection}
  {\normalfont\normalsize\itshape}{\thesubsubsection.}{1em}{}
```

The overwrite of `\thetitle` can be worked around by manually saving the title into a new variable, for example: 

```latex
\makeatletter
\let\mytitle\@title
\makeatother
```

And then changing the Markdown YAML containing `\chead{\thetitle}` to `\chead{\mytitle}`.

However, this also falls under the use of executing LaTeX commands, and I have yet to find a way to make this work from within the Markdown YAML. Thus, it only generates Error-Messages. 


## Copyright

The scrlttr2.latex template, forked from the [pandoc-templates] is dual-licensed, under both the GPL (v2 or higher, same as pandoc) and the BSD 3-clause license (included below).

----

Copyright (c) 2014, John MacFarlane

Copyright (c) 2014, Jens Erat

All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.
    
    * Redistributions in binary form must reproduce the above
      copyright notice, this list of conditions and the following
      disclaimer in the documentation and/or other materials provided
      with the distribution.
    
    * Neither the name of John MacFarlane nor the names of other
      contributors may be used to endorse or promote products derived
      from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.