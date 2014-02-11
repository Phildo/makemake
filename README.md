makemake
========

VERY basic, VERY brittle, (but VERY lightweight) alternative to autohell/makedepend. 

Currently in primitive state set specifically to my current needs on one project- might generalize in the future.

Just call it like so:

    makemake src/*.cpp
    
It will read a 'makemakefile' if it exists, and switch out all the content between

    #MAKEMAKE<
    
and

    #MAKEMAKE>
    
with the dependancies of the .cpp files you want to calculate dependancies for, in the following format:

    a.o : a.cpp a.h b.h c.h
      $(CC) $(CFLAGS) a.cpp -o $(OUT)/a.o
      
    b.o : b.cpp b.h d.h
      $(CC) $(CFLAGS) a.cpp -o $(OUT)/b.o
      
    ...
    
It will read various variables from the makemakefile-

    CC = g++ #will use this to determine dependancies
    CFLAGS = blah #will pass this to CC when determining dependancies
