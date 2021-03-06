# Eisvogel

[![Download the preview PDF](https://img.shields.io/badge/download-example_PDF-green.svg)](example/example.pdf)

A clean **pandoc LaTeX template** to convert your markdown files to PDF or LaTeX. It is designed for lecture notes and exercises with a focus on computer science.

## Preview

[![A preview of a PDF rendered with the Eisvogel template.](example/example.png)](example/example.pdf)

## Installation

1. Install pandoc from <http://pandoc.org/>. You also need to install [LaTeX](https://en.wikibooks.org/wiki/LaTeX/Installation#Distributions).
2. Move the template `eisvogel.latex` to your pandoc templates folder. The location of the templates folder depends on your operating system:
	- Unix, Linux, macOS: `~/.pandoc/templates/`
	- Windows XP: `C:\Documents And Settings\USERNAME\Application Data\pandoc`
	- Windows Vista or later: `C:\Users\USERNAME\AppData\Roaming\pandoc`
	
	If there are no folders called `templates` or `pandoc` you need to create them and put the template `eisvogel.latex` inside.

## Usage

1. Open the terminal and navigate to the folder where your markdown file is located.
2. Execute the following command
    
    ```bash
    pandoc example.md -o example.pdf --from markdown --template eisvogel --listings --latexmathml
    ```
    
    where `example.md` is the markdown file you want to convert to PDF.

In order to have nice headers and footers you need to supply metadata to your document. You can do that with a [YAML metadata block](http://pandoc.org/MANUAL.html#extension-yaml_metadata_block) at the top of your markdown document (see the [example markdown file](example/example.md)). Your markdown document may look like the following:

```markdown
---
title: "The Document Title"
author: [Example Author, Another Author]
date: 2017-02-20
tags: [Markdown, Example]
...

Here is the actual document text...
```