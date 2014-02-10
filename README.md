makemake
========

VERY basic, VERY brittle, (but VERY lightweight) alternative to autohell/makedepend. 

Currently in primitive state set specifically to my current needs on one project- might generalize in the future.

Just call it like so:

    makemake src/*.cpp
    
with all the .cpp files you want to calculate dependancies for, and it will output with the following format:

    a.o : a.cpp a.h b.h c.h
      g++ a.cpp -o a.o
      
    b.o : b.cpp b.h d.h
      g++ a.cpp -o a.o
      
    ...
    
there are a bunch of cflags in there too. again- this is currently catering to one project of mine. will generalize later.
