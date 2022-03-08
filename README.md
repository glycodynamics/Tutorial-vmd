# VMD tutorial
This tutorial was written for the VMD workshop by CCBRC, March 8-9, 2022. This is vary basic tutorial to a avanced molecular visualizer program VMD. Aim of this tutorial is just to show how glycan can be represented in SNFG Representation in 3D images of g;cyan containing biomolecules.

Download and install VMD if you have not done so for. VMD supports all major computer platforms and can be obtained from the [VMD homepage](http://www.ks.uiuc.edu/Research/vmd) 

We will also be using a pluging to visualize glycans in SNFG representtaion. Download pluging from Glycam-Web:

[Linux/Mac](http://legacy.glycam.org/docs/othertoolsservice/download/Software/publication-software/3D-SNFG_v1_mod-vmdrc_Linux-Mac.zip): Download, unzip and move extracted .vmdrc file to your home ```mv .vmdrc ~/```


[Windows Users](http://legacy.glycam.org/docs/othertoolsservice/download/Software/publication-software/3D-SNFG_v1_mod-vmdrc_Windows.zip): Download, unzip and move extracted vmd.rc file to C:/Program Files (x86)/VMD/ \

## Download glcyan containing PDB files:
The easiest way to download a protein structure from the protein data bank (PDB) is by typing the PDB ID into the search box of the [PDB Webpage](https://www.rcsb.org).  Go to rcsb.org now and type 1G1Y (case insensitive) into the search box, and then then hit enter. Repeat the process for 2CHB, 3SGJ, 1G1R, 1RVZ, and for any other file that is of yor interest. Alternatively, you can download some PDB files from here:  

## 1 VMD Graphical Interface

One VMD and 3D-SNFG plugin is installed, to start VMD folling the instructions given below:

• **Mac OS X**: Double click on the VMD application icon in the Applications directory.\
• **Linux and other Unix platforms**: Type vmd in a terminal window.\
• **Windows**: Select Start → Programs → VMD.\

When VMD starts, by default three windows will open (Fig. 2): the VMD Main window, the OpenGL Display window, and the VMD Console window (or a Terminal window on a Mac). To end a VMD session, go to the VMD Main window, and choose File $ \rightarrow $ Quit. You can also quit VMD by closing the VMD Console window or the VMD Main window.
![VMD DISPLAY](https://github.com/glycodynamics/vmd/upload/main/images/image_vmd_start.png)

### Change Background, on/off axis: 
• You can set the background to white or any other color (VMD Main → Graphics → Colors → Display → Background → White), 
• set Display to Orthographic (Display → Orthographic)
• Turn on/off axis (Display → Axes → on/Off).

## Visualizing the Structures Using VMD
First, we will focus on visualizing the protein – after all, the protein is likely to be an important part of any structure in the PDB.  After that, we will explore representations of the carbohydrates/glycans.

### Visualizing the protein
• Open VMD, Go to File and choose New Molecule. Brows the PDB structure (e.g. 2CHB.pdb) you want to load and click Load.  
• Now change representation from Main → Graphics → Representations:\

In Selected Atoms, type protein. can choose follwoing options:
```
Coloring Method: Secondry Structure
Drawing Method : New Cartoon
Material : Opaque
```
Now you should see how the molecule is organized. Looks familier? Let’s do some more:
• Now chnge Drawing Method and see how each representation looks like:

#### VMD representation styles: 
|Representation styles|	Description|
| --------| ------------- |
|Lines|	simple lines for bonds, points for atoms|
|Bonds|	lighted cylinders for bonds|
|CPK|	scaled VDW spheres, with cylinders for bonds|
|VDW|	solid van der Waal spheres for atoms, no bonds|
|Points|	just points for atoms, no bonds|
|Licorice|	spheres for atoms, cylinders for bonds, same radius|
|Ribbons|	flat ribbon through the C_alpha atoms|
|Tube|	smooth cylindrical tube through the C_alpha atoms|
|Cartoon|	cartoon diagram (cylinders, sheets and loops) based on secondary structure|
|PaperChain|display ring structures as polygons, colored by ring pucker| 
|New Cartoon| smooth cartoon diagram (smooth ribbons) based on secondary structure|
|MSMS|	molecular surface as determined by the program MSMS|
|HBonds|	display hydrogen bonds|
|Surf|	molecular surface as determined by SURF program|
|Dotted|	dotted van der Wall spheres for atoms, no bonds|
|Solvent|	dotted representation of the solvent accessible surface|
|Trace|	connected cylindrical segments through C_alpha atoms||Off|	do not draw anything|

#### VMD representation styles: 


### Visualize Glycans

Load a file containing a glycan into VMD (i.e. PDB ID: 3SGJ or 2CHB). On your keyboard, use the following shortcut keys:
```
‘i’ – apply the SNFG-Icons representation
‘g’ – apply the 3D-SNFG representation
‘b’ – apply the 3D-SNFG representation and label the reducing terminus
‘d’ – delete the drawn objects
```

## AO (ambient occlusion lighting)

## ImageMagick
The free program display from ImageMagick - see http://www.imagemagick.org/ - should be able to read and convert between all of these formats.

![VMD WATER](https://github.com/glycodynamics/vmd/upload/main/images/image_vmd_water.png)

![VMD TOXIN](https://github.com/glycodynamics/vmd/upload/main/images/image_vmd_tc.png)

![VMD SPROTEIN](https://github.com/glycodynamics/vmd/upload/main/images/image_vmd_sprotein.png)


### Acknowledgement:
This workshop is supported by an Institutional Development Award (IDeA) from the National Institute of General Medical Sciences of the US National Institutes of Health under award number P20GM130460.
### Author:
```
Dr. Sushil K. Mishra, PhD
Research Scientist | Core-Manager
Computational Chemistry and Bioinformatics Research Core
Glycoscience Centre of Research Excellence (GlyCORE) 
The University of Mississippi, P.O. Box 1848
University, MS 38677-1848, USA
sushil_at_olemiss.edu
```
[Twitter](https://twitter.com/glycodynamics)\
[GlyCORE Twitter](https://twitter.com/UM_glycore)\
[CCBRC Web-page](https://pharmacy.olemiss.edu/glycore/computationalchemistrybioinformaticscore)

 


