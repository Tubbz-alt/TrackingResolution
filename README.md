The package is written in Python 3.6.8

To run the package in terminal: 

python3 trackaingerror.py [-h] [-f filename] [-p momentum] [-m mass] [-B MagneticField][-eta pseudorapidity][-verbose v]

e.g. in terminal run: python3 trackaingerror.py -f example.txt

To see the help: python3 trackaingerror.py -h

To run it in Jupyter Notebook: %run trackingerror.py

Example of the usage in Jupyter Notebook: example.ipynb

The supported layer configuration is cylinder, with origin set at its center. 
xy plane denotes the transeverse plane. z-direction is in the direction of the cylinder axis.
All layers are assumed to be infinite long along z-axis.
Particle is assumed to be of unit charge e.

The units of output are:

	sigma(pt)/pt: no unit
	
	sigma(d): micrometer
	
	sigma(phi): radians
	
	sigma(z): micrometer
	
	sigma(theta): radians
	
About the input file: 
The "-f" option allows you to read from the detector configuration from a txt file, but the file must be in certain format:
	
	To comment out a line use "#"
	
	Each line is a layer configuration.
	
	The first colomn is the layer width (unit: radiation length X0).
	
	The second colomn is the detector resoluton in xy plane (unit: meter).
	
	The third colomn is the detector resolution in z direction (unit: meter).
	
	The final colomn is the layer position in the radial direction with respect to the origin (unit: meter).
	
	The order of the lines does not matter, but two layers with the same position must be avoided.

An example of input file format can be found in example.txt. 
This is just a placeholder with material thickness set at 0, equally spaced layers and same detector resolution in the longitudinal and radial directions.

To change parameters from command line:

	-m M, --m M          mass of the particle in GeV/c^2 (default: muon mass)
	
  	-B B, --B B          magnetic field in T (default: 2T)
	
  	-eta ETA, --eta ETA  pseudorapidity (default: 0)
	
  	-p P, --p P          momentum of the particle in GeV/c (default: 1 GeV)
