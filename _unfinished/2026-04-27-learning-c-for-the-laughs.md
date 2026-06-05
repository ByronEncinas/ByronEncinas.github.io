# Learning C for the laughs

Whatever the reason C has survived this long, it is without a doubt the standards (along with the ugly cousing C++) the best language for speed, resource management and to avoid abstractions. I don't enjoy allocating my variables, but I do mind when I allocate more memory than I have available in the cluster of my university (which happens often). 

I also aim to learn more about computer science, hardware, microcontrollers, and stuff. 

But my experience with python and fortran showed me that learning a language is not as simple as reading the docs. I have to make a project out of it, something useful. 

# Doing a FEM solver with friends!

Through the years, I have had close encounters with FEM, where I have used FEM codes, and I have read MATLAB FEM codes for very specific problems. But doing it all from the ground up implies implementing many utilities form zero, some of which are not necessary, so I guess we only did the ones we cared about. Because, let's be honest, since `LAPACK` and `BLAS` dropped, there has been no good enough reason to implement matrix solvers again, other than to learning some very specific algorithms, which no serious PI is going to take into account when asking if you have coding experience.

Reading through FEM books that use notations that obfuscate the methods is the easy part, designing is quite hard. I tried to direct the project in a `procedural` way. Each functions does a job. So far, the project has developed as kid in a toxic marriage. 

There is no pun for that comment.

The first goal to achieve was to partition space, so we decided to default to delaunay triangulation in convex shapes, though we want to expand in the future to all shapes. Finally, my goal is that this FEM code is able to solve the grad shafranov equation in it simplest form, and for that, defining the tokamak cross section has to be very straightforward.

> ![Cont'd]
> More on that later
