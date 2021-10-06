# GRAPHENE ELECTRONIC DISPERSION SPECTRUM
import numpy as np
import matplotlib.pyplot as plt


# Calculating the energy values in momentum space positions, kx and ky
def Graphene(kx,ky):
  Y0 = 2.8 #eV
  a = 2.46 #Angstroms
  return Y0 * np.sqrt((4*np.cos(0.5*a*kx)**2)+(4*np.cos(0.5*a*kx))*(np.cos((np.sqrt(3)/2)*a*ky)))


# Creating the momentum space grid
kx = np.linspace(-1.7,1.7,50)
ky = np.linspace(-1.7,1.7,50)
kx,ky = np.meshgrid(kx,ky)


# Finding energy values at given kx and ky values, and assigning them to the array GRA
GRA = Graphene(kx,ky)


# Plotting the 3D and 2D dispersion relation visualisations
fig = plt.figure(1)
ax = plt.gca(projection="3d")
ax.set_xlabel("kx")
ax.set_xticks([-1,0,1])
ax.set_ylabel("ky")
ax.set_yticks([-1,0,1])
ax.set_zlabel("E(k)")
plt.title("Graphene Electronic Dispersion Spectrum")
surf = ax.plot_surface(kx,ky,GRA, linewidth=0, antialiased=False)

fig = plt.figure(2)
ax2 = plt.contourf(kx,ky,GRA)
plt.xlabel("kx")
plt.xticks([-1,0,1])
plt.ylabel("ky")
plt.yticks([-1,0,1])
plt.title("Graphene Electronic Dispersion Spectrum")
cbar = plt.colorbar()
cbar.set_label("E(k)", x = 0.9, rotation = 0, labelpad = 20)

plt.show()