# Introduction to R #

This repository contains a set of lectures I developed to introduce R to
undergraduate and graduate students for the class *Mathematical and Computational
Modeling in Ecology* (UCLA, Winter 2012).  I assume the students have little or
no programming experience and start with very basic material.  Ideally, these
lectures should be coupled with computer lab examples and homework to practice
the material.

I stopped during lecture to demonstrate basic operations using the command line 
as well as Rstudio.  Given this presentation style, the approximate lecture 
time was:

+ Lecture 01: 1 hour 15 minutes
+ Lecture 02: 45 minutes
+ Lecture 03: 1 hour
+ Lecture 04: 1 hour

## Installation ##

If you are not a git or github user, links to the right allow you to
download a **zip** archive.  If you'd like to develop you own version, fork
the repository and play away.  A clone of the repository on your local machine
can be obtained with the usual:

    $git clone git@github.com:cstrelioff/introduction_to_R_ecology.git

## How to use ##

The provided files are **.Rnw** and **makefiles** for each lecture.  I used a
complete install of Tex Live 2011 (including beamer and pgf/tikz) as well as a
current version of R to compile the slides.  Later versions of Tex Live should
work as well. The lectures use Sweave to generate a  **.tex** file as well as a
functional **.R** script.

+ If you are using Mac/Linux, you should be able to create the lecture slides
  by typing **make** in each lecture directory:

        $ make
 
* If you don't have make available, the commands executed to generate the 
slides are (assuming *Lecture01* is being built):

        $ R CMD Sweave Lecture01.Rnw
        $ pdflatex Lecture01.tex
  
An **.R** script containing all code from the lecture is generated using (again,
assuming *Lecture01*):

    $ R CMD Stangle Lecture01.Rnw

## Potential Problems ##

**2014, Nov 6:**  I am now running Ubuntu 14.04 with custom TeXLive 2013
and R installations.  When I tried making the slides using the
make command I got a complaint about *not finding* **Sweave.sty**.

Turns out I need to tell LaTeX where to find this file.  To do that, I created 
a directory LaTeX searches by default:

    $ mkdir ~/texmf/tex/latex

Then, I created a link to the Sweave.sty file (the location is good for my 
Ubuntu 14.04 machine-- you might find it elsewhere):

    $ cd ~/texmf/tex/latex
    $ sudo ln -s /usr/share/R/share/texmf/tex/latex/Sweave.sty Sweave.sty

That fixed it for me.

## Help ##

I provide these materials as examples for others to use and would welcome
comments and suggestions, particularly if you find any errors.  Also, please
let me know if you use this material.  I will attempt to answer questions when
possible, but I can not promise a quick response in all cases.  Enjoy!

