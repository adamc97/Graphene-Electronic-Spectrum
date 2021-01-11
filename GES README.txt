README


This repository contains Python code to create a 3D surface plot and a 2D 
contour plot showing the electronic spectrum for pristine, monolayer graphene.

Matplotlib and NumPy are both included to allow for the use of 1D matrices
as well as data visualization. 


It is important to understand that while the hexagonal shape of the graphene
unit cell is produced, the results do not represent the unit cell itself, rather
the momentum space representation of the unit cell, denoted by the letter k.

Further, in both plots, only the bonding spectrum is shown, and whilst it was
possible to include the antibonding spectrum, it was not included as is it 
a mirror of the bonding spectrum with negative energy. To plot the antibonding,
simply use the negative bonding equation.

