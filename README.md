# Detektor

A library for finding similarities in code.


## Motivation

Created to find similarities of a set of code files. Used to compare a set of
hand-ins in programming education courses, and can report if similarity of code
in files are high.

## Usage

Takes a filehandler, reads it, creates some sort of signature based on keywords
and operators for a spesific language.

## Install

This package will be added to pypi soon, but for now:

    $ git clone git@github.com:apparator/detektor.git

No virtualenv? Currently this package uses standard Python modules only.

## Run demo

    $ fab demo

## Run tests

    $ fab test

## Details

Detektor is implemented in Python, and it is designed for easy adding of
functionality. Currently, it only finds similarities in programs written in the
Python and Perl programming languages, but adding support for new languages
should be straightforward. For any programming language, including assembler
languages and 'home-made' languages especially developed for education purposes.

To find similarities, the only thing that is kept from a program is the keywords
and the operators. Everything else is stripped away. The finding of similarities
is done by comparing:

* The number of each keyword and operator used 
* The whole string of keywords and operators
* Parts of a string build of these keywords and operators

A code supplied as a file handler opened for reading is given a tuple of values
as a "fingerprint". These are:

* Total number of keywords
* A string representing the number of each keyword used in the code
* Total number of operators
* A string representing the number of each keyword used in the code
* The hashvalue of the string of all keywords
* A hash for each function in the program

Each comparison of two programs is given scores, and if the scores of a
comparison is higher than 20 percent (or which ever limit is supplied as
argument) average it is reported.


## Adding support for new languages

Make a new file in the "/dat" directory where you put the keywords and the
operators to look for in the new language and use KEYWORDS: and OPERATORS: tags
in this file. See "dat/python.dat" for example.

Open the "dat/supported_languages.dat" file and add a new line with the name of
the new language, the filesuffix to look for, and the name of the file with the
reserved words and the operators.



