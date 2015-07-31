Chapter 1: Getting Started with R and RStudio
=============================================

In this chapter we will walk through a short introduction to R and
RStudio. There are many free and comprehensive tutorials available on
the web, so our focus here will be to introduce only the concepts and
functionality that we need to get started with price analysis as quickly
as possible. Readers who come to this book because they want to do price
analysis professionally using R will probably want to go back and learn
R in a more comprehensive way after they have finished *Commodity Price
Analysis* and the *R Companion*. At the end of this chapter I list some
excellent tutorials available for free on the web, and there are many
more not listed here.

Background
----------

For history on the development of R,
[Wikipedia](https://en.wikipedia.org/wiki/R_(programming_language)) is
probably the best source.

> R is a programming language and software environment for statistical
> computing and graphics. The R language is widely used among
> statisticians and data miners for developing statistical software and
> data analysis. ... R is an implementation of the S programming
> language combined with lexical scoping semantics inspired by Scheme. S
> was created by John Chambers while at Bell Labs. There are some
> important differences, but much of the code written for S runs
> unaltered. R was created by Ross Ihaka and Robert Gentleman at the
> University of Auckland, New Zealand, and is currently developed by the
> R Development Core Team, of which Chambers is a member. R is named
> partly after the first names of the first two R authors and partly as
> a play on the name of S. R is a GNU project. The source code for the R
> software environment is written primarily in C, Fortran, and R. R is
> freely available under the GNU General Public License, and
> pre-compiled binary versions are provided for various operating
> systems. R uses a command line interface; there are also several
> graphical front-ends for it. [Source:
> Wikipedia](https://en.wikipedia.org/wiki/R_(programming_language))

R as an open source project has been developed for decades now - which
means people have written solutions and made them available for free for
all kinds of problems related to statistics, programming, analytics and
much more. Whatever kind of work you want to do related to statistics,
there is a good chance someone has already done the hard work for you.
All you have to do is find it and figure out how to implement it. For
price analysis, we will cover the basics here.

R by itself functions through a command line interface, which is not
very convenient unless you are very technically inclined. Thankfully,
there are several Graphical interfaces (called integrated development
environments (IDE)) which makes life a lot easier. Some key
functionality is available through clickable menus and viewing panes -
just like the vast majority of software we are used to interacting with.
My favorite is RStudio, and it is what we will use throughout this book.

If you do not have any background programming, this may all sound
daunting. Believe me, using R and RStudio is more accessible than it
sounds. Let jump right in and get started. Since R and RStudio are open
source, it is avaiable for free to download.

Download R
----------

Go to [<https://www.r-project.org/>](https://www.r-project.org/), where
the software is avaiable for downloading.

![Screenshot of r-project.org](images\Rpojectsite.jpg)

Click "download R", and scroll to a server mirror close to you. It does
not matter much which one you choose; mirrors that are phyically closer
to you will produce downloads marginally faster, but if you are in the
United States, for example, and you choose any of the mirrors located in
the United States, you are not likely to notice a difference.

When you click a mirror you will see a screen like the following:

![Screenshot of R Download Links](images\rdownload.jpg)

Click the link for your appropriate operating system, and click "base"
on the next screen. Finally, if you are running windows you will see the
following screen:

![Screenshot of Windows .exe Download Links](images\windowsexe.jpg)

Click the *Download R 3.2.1 for Windows* link and run the installation
file. Note that the release number may be different since new releases
of the software periodically come out. Now you have R intalled! Now we
will install RStudio.

Download RStudio
----------------

Downloading RStudio is a bit easier. Go to
[<https://www.rstudio.com/products/rstudio/download/>](https://www.rstudio.com/products/rstudio/download/)
and the download links are on one page for all supported operating
systems. Click your operating system and run the installation file.

![Screenshot of RStudio Download Links](images\downloadrstudio.jpg)

Congratulations, you now have R and RStudio installed!

Orienation to the RStudio IDE
-----------------------------

Now we will get aquainted with the RStudio IDE. First open RStudio. You
will see the main window pane divided into three sections. The large
pane on the left is called the *Console*. It is where commands can be
executed within R. In the upper right corner is a pane with
*Environment* and *History* tabs. The environment will show you what
data or variables have been saved into the environment. Since we have
not done anything, this is empty. In history tab, a record of every
command given in the consule is kept.

The lower right hand corner holds several tabs: *Files*, *Plots*,
*Packages*, *Help*, and *Viewer*. More on these things later.

![Screenshot of RStudio](images\rstudio.png)

The power of R, is not in the line by line excecution of commands, it is
in writing scripts were commands can be stored and reused. In the upper
left hand corner of RStudio, is an icon just below the *File* menu.
Clicking it reveals a menu to open different kinds of script templates.
Click it and choose *R Script*. The R script will open in the RStudio
window and now there are four panes open. Let's assign the value `2` to
a variable called `x` and the value `3` to a variable called `y`. Then
we will add them together and store the result as `z`. This is done by
using the characters `<-` together to assign the values to the variable
names. Type the following into the R script.

~~~~~~~~

    x <- 2
    y <- 3
    z <- x+y
    z

    ## [1] 5

~~~~~~~~

Click on the *Environment* tab in the upper right hand corner. You will
see `x, y, and z` and their values. In this book, notice that output
from R is preceded by '\#\#'. The hashtag symbol indicates comments to
R, so anything to the right of a comment will not be evaluated. This
facilitates copy and pasting from this document into the R console,
since only the intended input will be evaluated.

Basic Calculations
------------------

In the Console type the following to get aquanted with performing
arithmetic in R.

~~~~~~~~

    2+2

    ## [1] 4

    6*7

    ## [1] 42

    12/4

    ## [1] 3

    5^2

    ## [1] 25

    sqrt(2)

    ## [1] 1.414214

    log(100)

    ## [1] 4.60517

    exp(4.60517)

    ## [1] 99.99998

    exp(log(100))

    ## [1] 100

~~~~~~~~

Datatypes
---------

When you assign variables or load data into R, it is defined as one of
several datatypes that have specific attributes. Some basic familiarity
with R's datatypes is neccessary because all R functions expect the
inputs to be of certain datatypes, and will not run if you give it a
character when it is expecting an integer, for example.

### Numeric, Integer, and Character, and Logical

The first four are pretty straightforeward. The *Numeric* datatype is
for floating decimal, like 2.34. *Integer* variables must be whole
numbers, and *Character* variables must be character strings like
`"Hello World"`. Logicals are either `TRUE` or `FALSE`.

### Vector

A vector is a datatype that is a sequence of elements of the same type
(enumerated above).

A vector of numeric elements ~~~~~~~~

    x <- c(2.3, 4, 6, -10)

~~~~~~~~

The function, `c()` is the concatenate function. It just takes the
elements between the comma's and puts them together in one matrix.

A vector of character elements ~~~~~~~~

    y <- c("Hello", "My", "Name", "Is")

~~~~~~~~

A vector of logical elements ~~~~~~~~

    z <- c(FALSE, FALSE, FALSE, TRUE, TRUE, FALSE, TRUE)

~~~~~~~~

### Matrix

Matrices are simply two dimensional vectors. Since we need to specify
how the dimensions work, we will use a specific function for definng a
matrix.

~~~~~~~~

    z <- matrix(c(1,2,3,4,5,6), nrow = 3, ncol=2)
    z

    ##      [,1] [,2]
    ## [1,]    1    4
    ## [2,]    2    5
    ## [3,]    3    6

    z <- matrix(c(1,2,3,4,5,6), nrow = 2, ncol=3)
    z

    ##      [,1] [,2] [,3]
    ## [1,]    1    3    5
    ## [2,]    2    4    6

~~~~~~~~

It takes a vector one one dimension and allocates it to rows and columns
as you define in the function arguments. The datatypes of the elements
of a matrix must be the same type, as is true for vectors.

### List

A list is kind of like a vector, execpt its elements can be of different
types.

~~~~~~~~

    list1 <- list(x, y, z, 22, "R is really fun to learn")
    list1

    ## [[1]]
    ## [1]   2.3   4.0   6.0 -10.0
    ## 
    ## [[2]]
    ## [1] "Hello" "My"    "Name"  "Is"   
    ## 
    ## [[3]]
    ##      [,1] [,2] [,3]
    ## [1,]    1    3    5
    ## [2,]    2    4    6
    ## 
    ## [[4]]
    ## [1] 22
    ## 
    ## [[5]]
    ## [1] "R is really fun to learn"

~~~~~~~~

### Accessing elements of Vectors, Matrices, and Lists by Index

You access elements of a vector, matrix, or list by enclosing square
brackets around the index number and placing it directly after the
variable name. For example, `x` is a vector with 4 elements in it. To
access the third element execute the following lines:

~~~~~~~~

    x

    ## [1]   2.3   4.0   6.0 -10.0

    x[3]

    ## [1] 6

~~~~~~~~

For matrices you have to specify a rown and column index. To get the
element in row 1 column 2,

~~~~~~~~

    z

    ##      [,1] [,2] [,3]
    ## [1,]    1    3    5
    ## [2,]    2    4    6

    z[1,2]

    ## [1] 3

~~~~~~~~

List elements are accessed similarly.

~~~~~~~~

    list1[3]

    ## [[1]]
    ##      [,1] [,2] [,3]
    ## [1,]    1    3    5
    ## [2,]    2    4    6

~~~~~~~~

### Data.frame

#### Basics

#### Subsetting

Setting up a Project
--------------------

Initializing an R project is a good way to keep all of your files and
directories straight. If you do not do this, you will inevitably lose
track of what file directory R is pointing to. Then you will save data,
figures, or images in unexpected locations. To get used to working with
different projects, we will create a new project for each chapter of
this book.

Install and Load a Package into the Library
-------------------------------------------

Other Resources for Getting Started with R
------------------------------------------

1.  [R Tutorial](http://www.cyclismo.org/tutorial/R/input.html) by Kelly
    Black, Department of Math at University of Georgia.
2.  [R and Reproducable Research
    Course](http://eriqande.github.io/rep-res-web/syllabus.html) by Eric
    Anderson, NOAA.
