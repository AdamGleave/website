---
title: 'Writing Beautifully in LaTeX'
subtitle: 'Design Patterns for Composing LaTeX Documents'
summary: LaTeX is the typesetting system of choice in most STEM fields. Yet even experienced LaTeX users often fall prey to many gotchas, or fail to exploit some powerful aspects of the language. In this document, I collect together *design patterns* to help efficiently produce clear LaTeX documents.
authors:
- AdamGleave
date: "2020-08-06"
lastmod: "2020-08-06"
featured: false
draft: false
projects: []
---

[LaTeX](https://www.latex-project.org/) is the typesetting system of choice in most STEM fields -- indeed, many computer science venues *only* accept submissions produced by LaTeX.
Unlike [What You See Is What You Get](https://en.wikipedia.org/wiki/WYSIWYG) (WYSIWYG) word processors, in LaTeX one is writing source code that LaTeX will then compile into a document, such as a PDF.
Once mastered, LaTeX can be more flexible and efficient than alternatives, however it comes with a steep learning curve.
There exist [many](https://en.wikibooks.org/wiki/LaTeX/Introduction) [excellent](https://en.wikibooks.org/wiki/LaTeX/Introduction) [introductions](https://www.andy-roberts.net/writing/latex) to LaTeX.
However, I've found that even experienced LaTeX users often fall prey to many gotchas, or fail to exploit some powerful aspects of the language.

This document aims to collect together *[design patterns](https://en.wikipedia.org/wiki/Software_design_pattern)* in LaTeX that enable efficient and clear writing, and warn of *antipatterns* which interfere with this goal.
Take these patterns as suggestions, not strict rules.
What may be a pattern in one document can be an antipattern in another: for example, defining macros for notation may be beneficial in a PhD thesis, but is likely overkill for an extended abstract.
Furthermore, while I anticipate these suggestions to be applicable to many LaTeX users, most of my experience has been in preparing papers for machine learning and computer science.
When in doubt, defer to the publication norms of the field you operate in.

I am indebted to my advisors throughout the years patiently correcting my own writing, especially [Jan Leike](https://jan.leike.name/) and [Malte Schwarzkopf](http://cs.brown.edu/people/malte/).
I would also like to thank [Cody Wild](http://decodyng.com/) and others for contributing their own suggestions to this list.

# LaTeX As Software Engineering

LaTeX is highly extensible (indeed, the language is [Turing complete](https://web.archive.org/web/20160110102145/http://en.literateprograms.org/Turing_machine_simulator_%28LaTeX%29)).
This suggests treating writing LaTeX documents similar to software engineering.
The analogy is not perfect: software must often be maintained for decades or more, whereas hopefully your paper will be published sooner than this!
Nonetheless, there are some similar design patterns.

**[Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) (DRY)**: Define LaTeX [macros](https://en.wikibooks.org/wiki/LaTeX/Macros) for repeated functionality. A common example of repeated LaTeX code is in mathematical notation. Perhaps you start by writing your document using $P$ everywhere for probability. One day, you decide $\mathbb{P}$ would be clearer. A find-and-replace of every occurrence of ``P`` in your document would have many false positives. You are left painstakingly working through your document and, since to err is human, you will likely end up with inconsistent notation. Instead, save yourself some time -- define ``\newcommand{\probability}{P}`` at the start, and you can easily change notation later to your heart's content.

Another source of duplicated code are theorems that must be presented multiple times in the document: for example, the statement in the main body and a proof in an appendix. Instead, use tools to recall an earlier statement of the [theorem](https://tex.stackexchange.com/questions/51286/recalling-a-theorem). Similarly, if you have boilerplate duplicated across figure captions (for example, the same legend), define a macro to consolidate it.

**Pay Attention To Errors and Warnings**: The LaTeX compiler issues warnings for a variety of common problems, such as citations to undefined references. I encourage immediately fixing these warnings or, if they are spurious, [suppressing them](https://tex.stackexchange.com/questions/66958/how-do-you-suppress-specific-warnings-generated-by-pdflatex). Having zero warnings by default makes it immediately noticeable when an edit has caused a new issue, enabling you to fix the problem immediately when the code is fresh in your mind.

Errors should always be fixed immediately. Unfortunately, the otherwise excellent [Overleaf](https://www.overleaf.com/) cloud IDE encourages sloppy practices here, by allowing LaTeX to continue compiling a document after an error. The problem is the LaTeX compiler is often unable to recover from an error, causing the rest of the parse tree to be incorrect, and causing far-reaching and hard to predict effects. Fix errors as they occur so you can focus on *writing* and not debugging.

**Automated Checks**: In a similar vein, use automated checks to catch common mistakes. This doesn't have to be limited to code -- you can also use or develop tools to automatically check your writing. A spellchecker is a simple example, but you can be more creative: for example, Matt Might wrote shell scripts to check for [passive voice, weasel words and lexical illusions](http://matt.might.net/articles/shell-scripts-for-passive-voice-weasel-words-duplicates/).

**Use and Master an IDE**: Find an [integrated development environment](https://en.wikipedia.org/wiki/Integrated_development_environment) (IDE) for LaTeX that works for you. I like to use [Overleaf](https://www.overleaf.com/) when collaboratively editing due to its real-time synchronization and commenting. However, I find Overleaf to be lacking in features and compile notably slower than on a local machine, so I also use the [TeXiFy IDEA](https://plugins.jetbrains.com/plugin/9473-texify-idea) plugin for IntelliJ. There are many other excellent IDEs, though -- the main thing is to pick one and master it. 

**Use Source Control**: This should go without saying, but do use a version control system like [Git](https://git-scm.com/) and regularly push changes. Sooner or later, you *will* delete or otherwise corrupt your files, and will be very glad you have this. I also find it cognitively liberating: I can make substantial edits, knowing it will be easy to revert to a previous version if I want. I find this particularly valuable when working on multiple versions of a document at once -- for example, a workshop and conference version -- since I can make edits on multiple branches and merge them. If you use Overleaf then you may be satisfied with it's built-in version control, however I still prefer [using Git with Overleaf](https://www.overleaf.com/learn/how-to/How_do_I_push_a_new_project_to_Overleaf_via_git%3F) since this offers more powerful version control and allows one to make edits both locally and in the cloud.

# Mathematics

LaTeX has excellent support for typesetting mathematical formulas, and so is widely used in mathematics and related disciplines.

**Punctuate Your Math**: Mathematics forms an integral part of your text, and should be punctuated accordingly. For example, if your sentence ends with an equation, the equation should end with a period. It can often be helpful to imagine punctuating everything as if it was inline math (`$...$`), even if you are using display math (`$$...$$` or `\begin{equation}...\end{equation}`). [Stack Exchange](https://tex.stackexchange.com/questions/7542/for-formal-articles-should-a-displayed-equation-be-followed-by-a-punctuation-to) has a good discussion on this.

**Use Detexify**: More a tip than a design pattern. If you know how a symbol is written but do not know the LaTeX command to produce it, you can sketch the symbol on [Detexify](http://detexify.kirelabs.org/classify.html) to find it.

# Typography

LaTeX encourages writers to specify the *structure* of the document, and leave formatting details to LaTeX. This usually works well, however there are some common problems that can mislead LaTeX into producing the wrong output.

**[Be Semantic](https://tex.stackexchange.com/questions/1980/emph-or-textit)**: If you want to emphasize some text, use `\emph{}`. Do *not* use `\textit{}`. Though they may seem to produce the same effect of italicized text, `\emph{}` will automatically switch between italic and Roman: for example, `\emph{emphasis \emph{nested} works}'` produces "*emphasis* nested *works*" whereas `\textit{italics \textit{is} idempotent}` produces "*italices is idempotent*". This behaviour of `\emph{}` is useful since environments (such as `\begin{theorem}`) may italicize blocks of text, in which case Roman text stands out from the italic surroundings.

**[Spacing after abbreviation periods](https://tex.stackexchange.com/questions/2229/is-a-period-after-an-abbreviation-the-same-as-an-end-of-sentence-period)**: LaTeX adds extra space between sentences. This improves readability, but LaTeX can misinterpret periods in abbreviations as being the end of a sentence: for example, in `e.g. this` LaTeX will insert a sentence space after `e.g.`. To avoid this problem, use `\ ` to instruct LaTeX to use a regular space: `e.g.\ this`. More rarely, LaTeX may incorrectly believe a period [does not end a sentence](https://tex.stackexchange.com/questions/22561/what-is-the-proper-use-of-i-e-backslash-at), for example after a capital letter: in this case, you can force it using `\@` as in `LaTeX was invented in the US\@.`

**[Use \` and \' Quote Marks](https://www.andy-roberts.net/writing/latex/formatting)**: Use `` ` `` and `'` at the left and right end of single quotes, and ``` `` ``` and `''` for double quotes. This allows LaTeX to generate appropriate quotation characters. Be consistent with single vs double quotes within a document.

# Figures

LaTeX has excellent support for figures, both in the form of [float](https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions) environments and packages to [include external graphics](https://www.overleaf.com/learn/latex/Inserting_Images) or even [generate vector figures](https://en.wikibooks.org/wiki/LaTeX/PGF/TikZ) inside your document.

**Use Vector Graphics**: Wherever possible, generate figures as [vector graphics](https://en.wikipedia.org/wiki/Vector_graphics) such as SVG or PDF rather than [raster](https://en.wikipedia.org/wiki/Raster_graphics) graphics formats such as PNG. Vector graphics can be visualized at arbitrarily high resolutions without any loss of fidelity -- this will allow your readers to zoom in on plots to better read them, and print your paper in a high quality. They also tend to be smaller than saving the file as raster graphics. It is almost always possible to save plots and schematic diagrams as vector graphics. Raster graphics are appropriate for figures such as photographs or screenshots.

**Match the Paper Style**: Even though you will often be generating your figures outside of LaTeX in a package like [matplotlib](https://matplotlib.org/), to the reader your figures are an integral part of the paper. Accordingly, you should use the same font and -- where possible -- font size as in the rest of the paper. It's particularly important to save your figures with the same geometric dimensions as they will be embedded in the paper. While LaTeX does support rescaling included graphics, this will make it impossible to match font sizes exactly. Moreover, many packages like `matplotlib` will adjust the figure based on the size, adding more tick labels when the figure is larger -- giving it the right dimensions will help optimize the figure for clarity at the target size.

**Make each Figure Self Contained**: Readers will often skip ahead to figures without reading all the context, or will have forgotten some of the relevant context by the time they get to your figure. As far as practical, make each figure comprehensible in isolation. In particular, include clear axis labels, a legend and specify any extra information needed to understand the figure in the caption. Some people go as far as to aim for the key points of their paper to be understood *just* by reading the figures and captions!

# Citations and References

As LaTeX was designed around the needs of academic documents, it has extensive support for citations.
However, there are a number of subtle details it is important to get right.

**Use BibLaTeX Where Possible**: [BibLaTeX](https://ctan.org/pkg/biblatex) ([guide](https://www.overleaf.com/learn/latex/bibliography_management_with_biblatex)) is the most modern approach to bibliography management in LaTeX, designed as a replacement for [BibTeX](http://www.bibtex.org/) ([guide](https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex)). BibLaTeX adds many useful features, such as new [entry types](https://en.wikibooks.org/wiki/LaTeX/Bibliography_Management#Entry_and_field_types_in_.bib_files) like `@online` and localization in several languages. However, often you won't have a choice -- if you are submitting to a conference or journal, their LaTeX style file will usually specify a particular bibliography manager.

**Use The Right Citation Command**: In particular, it is important to distinguish between *parenthetical* citations (Gleave et al, 2020) v.s. *in-text* citations, claims Gleave et al (2020). For parenthetical citations, use `\parencite` (BibLaTeX) or `\citep` (BibTeX); for in-text citations, use `\textcite` (BibLaTeX) or `\citet` (BibTeX). Avoid nested brackets: use `\citep[see]{gleave2020}` to produce "(see Gleave et al, 2020)", rather than `(see~\citep{gleave2020})` producing "(see (Gleave et al, 2020))".

**Use Non-Breaking Spaces**: Citations should be on the same line as the word or sentence they are attached to, so use the [non-breaking space](https://en.wikibooks.org/wiki/LaTeX/FAQ#Non-breaking_spaces) `~` to instruct LaTeX to avoid orphaning the citation, as in `Knuth developed LaTeX~\citep{latex}`.

**Bibliography Management**: A sloppy bibliography is often symptomatic of a sloppy paper and, rightly or wrongly, readers (and reviewers!) may judge you for this. A common problem is LaTeX reformatting the capitalization of paper titles. This is usually desirable, since it ensures consistency across bibliography entries. However, it is undesirable when the title includes an acronym: these should be guarded with `{}`, as in `{DQN}`. It is also important to choose the correct [entry type](https://en.wikibooks.org/wiki/LaTeX/Bibliography_Management#BibTeX), for example `@inproceedings` for a conference, `@article` for a journal and `@misc` for preprints. Finally, it is essential to be consistent in your bibliography. Author names should always be spelt the same way (look out for middle initials, abbreviations); conference and journal names should always be abbreviated or spelt out in full; you should always include [DOI](https://en.wikipedia.org/wiki/Digital_object_identifier) links or never.