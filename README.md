# VMD tutorial
This tutorial was written for the VMD workshop by CCBRC, March 8-9, 2022. This is a very basic tutorial to an advanced molecular visualizer program VMD. This tutorial aims to show how glycan can be represented in SNFG Representation in 3D images of glycan-containing biomolecules.

## Installation
Download and install VMD if you have not done so. VMD supports all major computer platforms and can be obtained from the [VMD homepage](http://www.ks.uiuc.edu/Research/vmd) 

## Install plugin for SNFG representation

We will also be using a plugin to visualize glycans in SNFG representation. Download plugin from Glycam-Web:

[Linux/Mac](http://legacy.glycam.org/docs/othertoolsservice/download/Software/publication-software/3D-SNFG_v1_mod-vmdrc_Linux-Mac.zip): Download, unzip and move extracted .vmdrc file to your home ```mv .vmdrc ~/```


[Windows Users](http://legacy.glycam.org/docs/othertoolsservice/download/Software/publication-software/3D-SNFG_v1_mod-vmdrc_Windows.zip): Download, unzip and move extracted vmd.rc file to C:/Program Files (x86)/VMD/ \

## Download glycan containing PDB files:
The easiest way to download a protein structure from the protein data bank (PDB) is by typing the PDB ID into the search box of the [PDB Webpage](https://www.rcsb.org).  Go to [PDB Webpage](https://www.rcsb.org) now type PDB ID (case insensitive) into the search box, and then hit enter. Repeat the process for any other file that is of your interest. 

Alternatively, you can download the structure of glycan containing protein from PDBs (i.e. PDB ID: [3SGJ](https://files.rcsb.org/download/3SGJ.pdb) or [2CHB](https://files.rcsb.org/download/3SGJ.pdb), a [Glycan](https://raw.githubusercontent.com/glycodynamics/vmd/main/pdbs/structure.pdb) and [Glycosylated Spike Protein](https://github.com/glycodynamics/vmd/raw/main/pdbs/sprotein_open.pdb) from these links.

## 1 VMD Graphical Interface

One VMD and 3D-SNFG plugin is installed to start VMD following the instructions given below:

• **Mac OS X**: Double-click on the VMD application icon in the Applications directory.\
• **Linux and other Unix platforms**: Type vmd in a terminal window.\
• **Windows**: Select Start → Programs → VMD.

When VMD starts, by default, three windows will open (Fig. 2): the VMD Main window, the OpenGL Display window, and the VMD Console window (or a Terminal window on a Mac). To end a VMD session, go to the VMD Main window, and choose File $ \rightarrow $ Quit. You can also quit VMD by closing the VMD Console window or the VMD Main window.
![VMD DISPLAY](https://github.com/glycodynamics/vmd/blob/main/images/image_vmd_start.png)

### Change Background, on/off axis: 
• You can set the background to white or any other color (VMD Main → Graphics → Colors → Display → Background → White)
• set Display to Orthographic (Display → Orthographic)
• On/off axis (Display → Axes → on/Off)

## 2. Visualizing the Structures Using VMD
First, we will focus on visualizing the protein – after all, the protein is likely to be an essential part of any structure in the PDB.  After that, we will explore representations of carbohydrates/glycans.

### 2.1 Visualizing the protein
• Open VMD, Go to File, and choose New Molecule. Browse the PDB structure you want to load (e.g. 2CHB.pdb) and click load.  
• Now change representation from Main → Graphics → Representations:

In Selected Atoms, type protein. You can choose the following options:
```
Coloring Method: Secondary Structure
Drawing Method: New Cartoon
Material: Opaque
```
**Mouse Modes**
The available mouse modes are as follows:

Rotate Mode (hot key 'r')

When the mouse is in rotate mode, holding the left mouse button and moving the mouse rotates the molecules about axes parallel to the screen, in a `virtual trackball` behavior.\
To get a rotation around the axes coming out of the screen (the `z` axis), hold the middle button down and move the mouse left or right.\
You can leave molecules rotating without continuously moving the mouse. Start the molecule moving with the mouse, as above, then release the mouse button before you stop moving the mouse. With some practice, it becomes easy to impart a slight spin on the molecule.

Translate Mode (hot key 't')

When the mouse is in translate mode, holding the left button down allows you to move the molecules parallel to the screen plane (left, right, up, and down). To move the molecule towards or away from you, hold the middle button down and move the mouse right or left, respectively.

**Hot Keys**
```
|Hot Key|  Command            |      Purpose                      
|-------|---------------------|-----------------------------------
| r, R  |	mouse mode 0 0|	enter rotate mode; stop rotation
| t, T  |	mouse mode 1 0|	enter translate mode
| s, S  |	mouse mode 2 0|	enter scaling mode
|  =    |	              |	Reset View
|  0    |	mouse mode 4 0|	query item
|  c    |	mouse mode 4 1|	pick center
|  1    |	mouse mode 4 2|	pick atom
|  2    |	mouse mode 4 3|	pick bond (2 atoms)
|  3    |	mouse mode 4 4|	pick angle (3 atoms)
|  4    |	mouse mode 4 5|	pick dihedral (4 atoms)

```


Now you should see how the molecule is organized. Looks familiar? Let’s do some more:\

Now change the Drawing Method and see what each representation looks like:

#### VMD representation styles: 
|Representation styles|	Description|
| --------| ------------- |
|Lines|	simple lines for bonds, points for atoms|
|Bonds|	Lighted cylinders for bonds|
|CPK|	scaled VDW spheres, with cylinders for bonds|
|VDW|	solid van der Waal spheres for atoms, no bonds|
|Points|	just points for atoms, no bonds|
|Licorice|	spheres for atoms, cylinders for bonds, same radius|
|Ribbons|	flat ribbon through the C_alpha atoms|
|Tube|	smooth cylindrical tube through the C_alpha atoms|
|Cartoon|	Cartoon diagram (cylinders, sheets, and loops) based on secondary structure|
|PaperChain|display ring structures as polygons, colored by ring pucker| 
|New Cartoon| Smooth cartoon diagram (smooth ribbons) based on secondary structure|
|MSMS|	molecular surface as determined by the program MSMS|
|HBonds|	display hydrogen bonds|
|Surf|	molecular surface as determined by SURF program|
|Dotted|	dotted van der Wall spheres for atoms, no bonds|
|Solvent|	dotted representation of the solvent accessible surface|
|Trace|	connected cylindrical segments through C_alpha atoms||Off|	do not draw anything|


### 2.2 Visualize Glycans 
Open SARS-Cov-2 structures in VMD and then change graphical representation settings as below:

```
Selected Atoms  : protein
Coloring Method : Chain
Drawing Method  : New Cartoon
Material        : Opaque
```
Create a new representation for the membrane :
```
Selected Atoms  : resname POPC POPE POPI POPS CHL1
Coloring Method : Type
Drawing Method  : VDW
Material        : AOChalky

```
Create a new representation for glycans:
```
Selected Atoms  : not protein and not resname POPC POPE POPI POPS CHL1
Coloring Method : Name
Drawing Method  : Licorice
Material        : AOChalky

```
. On your keyboard, use the following shortcut keys:
```
‘b’ – apply the 3D-SNFG representation and label the reducing terminus
‘i’ – apply the SNFG-Icons representation
‘g’ – apply the 3D-SNFG representation
‘d’ – delete the drawn objects
```


## 3. Rendering:
Open the Render window (VMD Main --> File --> Render) and select `Tachyon' from the Render the current scene using the menu. Both of the text boxes will be filled with default values which should not need to be changed for this tutorial. Press the Start Rendering button. After a few moments of processing, you should see the message.

Info) Rendering complete.

The default render command will be:
```"
/usr/local/lib/vmd/tachyon_LINUXAMD64 -aasamples 12 %s -format TARGA -o %s.tga

```

To set the resolution, edit this command and add the keyword ```-res 2400 2400 ``` after ```%s```.
```
/usr/local/lib/vmd/tachyon_LINUXAMD64 -aasamples 12 %s -red 2400 2400 -format TARGA -o %s.tga

```
### 3.1 AO (ambient occlusion lighting)
Turn ambient occlusion lighting on or off. This only affects renderers that support ambient occlusion lighting. It will have no visible effect on the interactive VMD display or on renderers that don't support it. At present, only the Tachyon and TachyonInternal renderers are capable of ambient occlusion lighting.

It is a must to turn on Amb. Occl in (VMD Main --> Display --> Display Setting):
```
Shadows  : on
Amb Occl : on
```
Now render his images with and without these settings and see the difference it makes.


![VMD SPROTEIN](https://github.com/glycodynamics/vmd/blob/main/images/image_vmd_sprotein.png)

Some other example images with ambient occlusion lighting:

![VMD WATER](https://github.com/glycodynamics/vmd/blob/main/images/image_vmd_water.png)

![VMD TOXIN](https://github.com/glycodynamics/vmd/blob/main/images/image_vmd_tc.png)


## 4. ImageMagick
The free program display from ImageMagick - see http://www.imagemagick.org/ - should be able to read and convert between all of these formats generated by VMD.


### Acknowledgement:
This workshop is supported by an Institutional Development Award (IDeA) from the National Institute of General Medical Sciences of the US National Institutes of Health under award number P20GM130460.


### Author:
```
Sushil Mishra, PhD
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

