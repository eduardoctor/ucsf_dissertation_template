
# Dissertation Template

This dissertation template was created to be able to use it in [overleaf](https://overleaf.com), a **LaTeX** reader. Hence all the files are in .tex format. 


## Usage
### Project organization


The organization of the project is not static and it can be customized. However, to keep things together and for simplicity it was organized as follows:

```{bash}
dissertation_template
├── main.tex
└── setup.tex
└──  chapters
│   ├── preliminary_pages.tex
│   ├── introduction.tex
│   ├── paper1.tex
│   ├── paper2.tex
│   ├── paper3.tex
│   ├── appendices.tex
│   └── references.bib
└── figures
│   ├──  paper1
│   ├──  paper2
│   └──  paper3
└──  Tables
│   ├──  paper1
│   ├──  paper2
│   └──  paper3
```

You can create as many folders as needed or delete folders as needed. 

### Setup.tex

This is the file that contains all the formatting parameters. All formatting has been done as per the [UCSF Dissertation and Thesis Guidelines](https://graduate.ucsf.edu/students/dissertation-thesis-guidelines). Since LaTeX Does not have directly Arial fonts it is using a similar font. However, If you want to change the font please feel free to do so. Here's the [LaTeX font catalogue](https://tug.org/FontCatalogue/). 

You can adjust setting the parameters in the appropriate font section. 


## Main.tex

This file contains The overall order and structure of the document. As default it follows the structure of the [UCSF guidelines](https://graduate.ucsf.edu/students/dissertation-thesis-guidelines/content-guidelines). You will notice there's not title page as this has to come from Docusign and you can embed it later.

## Preliminary_pages

This file contained under the **chapters** directory contains all the mandatory and some optional sections as per the UCSF guidelines. You can delete or adjust as necessary.  
The table of contents, list of figures, and list of figures do not have a "chapter" name since this is directly inserted when calling the command the appropriate commands. If you want to make any changes to these titles, you need to make changes to the `setup.tex` file under the appropriate section. 

### TOC, List of tables and figures

This part is formatted as per the UCSF guidelines including the captions for the figures. Note that they will be formatted according to order of appearance. For example, if you have an introductory section and insert a table or figure, this will start with 1.1. And subsequent chapters will be 2.1, 3.1, 4.1 accordingly. If you notice that the title that is showing up in the list of figures or tables is too long you can change it. *See the figures and tables section to see how to change this*

## Writing files (introduction and chapters)

These are the files where the actual writing will take place. If you don't need an introductory chapter, simply delete this page from the `main.tex` file. If you do have an introductory section, this will be accounted as "chapter 1". This is according to the guidelines. 

### Reference formatting

References are formatted using the *NEJM* style and they look similar to this: 
* 1. Balzano E, Di Tommaso E, Antoccia A, Pelliccia F, and Giunta S. Characterization of Chromosomal Instability in Glioblastoma. Frontiers in Genetics 2022;12:810793.

This is acceptable for most cases, and I found it to be the most organized and homogenous way of organizing references. However, you can use a different style if preferred. You would have to change the appropriate settings in the **references** section of the `setup.tex` file. 

One caveat with this is that, the numbering in the actual text is not on a superscript. However, you can write your citations inside the text using `\superscript{\cite{citation_label}}` this will ensure that the number of the citation is on a superscript as it is typical in research papers. 

For better formatting and reference management I recommend to download the entire library of references used on a given paper in `.bib` format and then make them homogenous using software like [JabRef](https://www.jabref.org/). This software allows you to delete fields that you don't need from your references and creates short, friendly reference labels for easy management of your references. After you clean them up you can export the resulting file as "plain BibTex". Then you can upload your references to Overleaf and start entering your citations. The bibliography will be automatically inserted and formatted. 

### Figure formatting

Figures can be tricky especially when inserting within the margins of the document allowed by the guidelines.   
To begin, you can upload all your figures to the appropriate folder and then just insert them. I format them as follows: 

```
\begin{figure}[htbp] 
    \centering 
    \includegraphics[scale=0.76]{figures/paper1/Figure1_survival curves.jpg} 
    \caption[Short title for List of Figures]{\textbf{Figure \thefigure} The rest of the caption of your figure will be here including a description or explanation of subpannels}
    \label{fig:te_surv_curves}
\end{figure}
```

* The first line `\begin{figure}[htbp]` ensures that the figure is inserted at that specific position in the manuscript. If you don't apply at least the `[h]` parameter the figure will be placed at the end of the chapter.  
* The line for `\caption` has square brackets `[ ]` This is only neccesary if you caption is too long. The text that is placed insider the brackets is the title that will appear in the **List of Figures** in the preliminary pages. Next `{\textbf{Figure \thefigure} ` will Produce the caption **Figure X.X** according to the guidelines. The rest of the text can be left in normal font.
* You can find an example of a figure inside `paper1.tex`
### Table formatting

I would suggest to create each table on a separate `.tex` file since creating tables is different depending on the formatting needs of the table and it can create large chunks of text that can make difficult when focusing on writing. After the table is create it can simply be inserted by referencing it: `\input{tables/paper1/table1.tex}`. You can find an example of how to create a table inside `paper1.tex` Similar to the figures, the caption has been formatted to show as **Table X.X** in bold as per the guidelines and show up in the top part of the table. This is only one way of producing tables, but LaTeX has different ways of producing tables. 


## Final thoughts

writing in Tex is a learning curve compare to other word processors. However, once this learning curve is overcame you will find that is much nicer and friendlier to have a template and just focus on the writing. For further resources you can consult the [Official LaTeX Documentation](https://www.overleaf.com/learn) as it contains valuable resources. I welcome your comments/fixes.  **Happy writing!!**

