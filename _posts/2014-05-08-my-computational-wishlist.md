---
layout: post
title: My computational wishlist
---

## This is for scientific computing.

1. Single installer, install everything by imports
1. Cross-platform
1. Can call C and Fortran out of the box
1. Will run legacy code without having to write more legacy code glue
1. Lets me be as efficient as I want to be without extra libraries and syntax
1. Simple syntax

and the most important thing of all:

1. Will run on any hardware that I throw at it, without having to do much to my code (builtin parallelism)

Python has failed on all of these in some way over the last 5 years (except 6).

1 and 2 are no longer an issue due to [anaconda](http://continuum.io/downloads); it is a crossplatform
one click installer that hides the Python mess of dependencies for things like Numpy and Ipython notebook.

3 is almost okay for C, but not Fortran. 4 is a fail in many cases. If I want to call just one function
in a specific library just once, the boilerplate code required is taxing. It should be a single line.

5 is difficult to say. There are libraries in Python that will do this, but it is hard to know which ones
to use, and it is hard to know how to make them work with all of my code.

Parallelism is difficult and there are so many solutions that might work for me, but maybe not, and then if
I try to use a small cluster I'll have to switch to a different tool.  There is no simple Python parallel compute
function that will work everywhere and with everything.

I am looking for a single solution that will handle these things. MATLAB almost has it, but they are holding
on too tightly to their monolithic nature as the be-all, end-all of scientific computing.  They need to
be humble enough, when appropriate, to become just a tool in bigger toolchains.  
