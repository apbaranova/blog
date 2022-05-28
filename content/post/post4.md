---
title: Scientific Programming Languages
subtitle: Языки научного программирования

# Summary for listings and search engines
summary: As computers become more ubiquitous in physics research (and scientific research in general), the issue of which programming languages to use becomes more important. Factors which especially influence the importance of this question are the increasing complexity of the tasks being programmed; the increasing complexity and diversity of the machines being programmed; the increasing use of graphical visualization and interfacing to scientific programs; and the increasing number of the programming languages available in which to program.

# Link this post with a project
projects: []

# Date published
date: '2022-05-28T00:00:00Z'

# Date updated
lastmod: '2022-05-28T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
#  focal_point: ''
#  placement: 2
#  preview_only: false

authors:
  - admin

tags:
  - Academic

categories:
  - Demo
---

# Fortran

Fortran is the language of the past in scientific computation, and one of the main languages of the present, as far as physics is concerned. Its main strengths at the moment are

- a huge body of well-debugged and working code available;
- a large base of experience residing in "older" physicists (pretty much all of us over the age of thirty?);
- ease of use. 

The last point is perhaps the most important, as Fortran has a "model" of the computer which is simple enough that one does not have to be a professional (i.e., extensive training or self-education in computer science or programming) to produce a reasonable Fortran program.

This is not to say that it is not possible to produce a bad Fortran program. It is quite easy, but that is true of pretty much every computer language to some degree.

Fortran 90 extends fortran in several useful ways, and makes it a more modern programming language, while retaining full compatibility with Fortran-77 code. Two of the more interesting features are aggregrate data types ("structures") and built-in operations on arrays and matrices. In my opinion, Fortran tends to lose big as projects get more complex. The support for reuse and encapsulation of code is fairly poor in Fortran, at least in Fortran-77. Fortran 90 has more support for this, but I have little experience with it. Also, most graphical-interface and visualization packages have no native Fortran support.

Some Fortran 90 proponents would like to see some of the "dangerous" elements of Fortran-77 removed from the language. I think this is a bad idea. Go here to read why I think so.

# C and C++

C is an interesting choice as a scientific language. It is extremely flexible and available on about every machine known to man. Also, one of the best C compilers (gcc) is available for free. Almost all visualization and user-interface packages support the C language. C is frequently taught as a first or second language in university computer-science departments.

A long-standing gripe about C is that it produces slower code than does the equivalent Fortran. Nowadays, computer speeds are doubling every year or so, and C compilers don't seem to be doing that bad compared to Fortran anymore (typical C code runs between 50 and 100% as fast as the equivalent Fortran, depending on the application). In light of this, I think it's hard to discard C on the basis of the speed of the code it produces.

Nevertheless, I don't think it's a good scientific programming language. The C language is fairly close to the hardware, and it is quite easy to make big mistakes in coding an application. These mistakes often don't display themselves in small test cases, since they involve memory-management issues and the like. Also, programming large applications in C requires some degree of professionalism, meaning a fairly deep grasp of the language. As such, it is a bad language for mainstream scientific programming; typically only the creator of a program, or people with real expertise in computer programming, will be able to understand a large C application unless it is very carefully written.

I believe these comments also apply to C++ coding. The concerns about readability and professionalism apply perhaps even more strongly here than for "just C". C++ has the advantage of being the most-popular object-oriented language, but it is also recognized as being a fairly cryptic one. Again, a certain degree of professionalism is necessary to program a C++ application which is understandable to others. Packages which automatically generate C++ code from user-specified pseudocode help alleviate the problem, but then we are faced with asking all users to use the same C++ generator, which is another problem of the same magnitude.

The above two are the "traditional" choices. I now turn to newer languages which are less well known in the scientific community.

# Python

Python is an object-oriented, extensible, interpreted language. It runs on essentially all Unix systems, as well as on DOS/Windows platforms and on the Mac. It is free and comes with complete source code. It is very easy to begin using Python --- at a simple level, it resembles Basic and can be used interactively in the same way as Basic. However, it supports object methods and "scales" nicely. Scaling indicates the relative difficulty of writing small vs. large applications. The object facilities help and encourage one to write an application in small pieces. These small pieces can be put together to make the big program, and the small pieces can also be used in other applications.

Another advantage of Python is its extensibility. One can write an object library in C, C++, or native Python, which can then either be dynamically or statically linked with the main Python system and used in Python programs. One can use this to make a programmable application, such as a data-plotting package. One would add a package to the interpreter which contained commands to set up your plots and to actually plot the data. This Python+graphics interpreter can be given a different name, such as "pygraph", and invoked as a command. The interpreter will process the graphics commands and perform them. However, at the same time you can use any other valid Python command as a command to this graphics program! Thus one graphics input file for this program could first compute the result and then manipulate and plot it.

The leap from this to having Python+package systems such as data-analysis programs, or experiment-control programs, is fairly obvious. This can also solve to some extent the above-mentioned dilemma about the use of C++. A professional programmer can produce a well-defined library package with a well-defined interface in C++, and this can be included into the Python programs for use. As Python is quite readable in much the same was as is Fortran, a "normal person" (i.e. someone who is not a professional programmer) can use this library in his programs. Both the professionals, who want the power and efficiency of C or C++, as well as the group who must use the result and be able to read and understand the program, can be happy.

My experience with Python started when I used it simply as an interactive calculator application --- I had found the standard Unix calculator "bc" lacking. At some point, I programmed a four-vector object package in Python and used it to write some nuclear-reaction kinematics computations which I needed. I later in turn used both the four-vector and kinematics modules in a large application used to predict counting rates for a large nuclear-physics experiment. I have since then also written a multiparameter batch data-analysis facility in Python.

Several graphical-interface tools exist for Python, and a graphical-visualization package is now in beta test. A Numerical Python extension (a C package as described above in the extensions section) also exists which has built-in support for whole-array and matrix operations (which run at the speed of compiled C code rather than at the speed of interpreted Python.)

To see what Python can do with this numerical-computing package, check out this link. It will also give you a feel for what Python looks like, and allow you to assess its readability. Also check out the Python Tutorial on the Python Web Page link below (sublink "The Full Scoop on Python Documentation.")

An article on Numerical Programming in Python appears in the May/June 1996 issue of Computers in Physics. More Python information can be found on the newsgroup comp.lang.python, or on the Python Web Page. Of particular interest is the page on contributed Python software, which describes add-on packages available for Python. These are extensions in the vein mentioned above, which add new functionality to the core language. 