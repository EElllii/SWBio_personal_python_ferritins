## Investigating the subunit interfaces of ferritin from Archaeoglobus fulgidus

These Python scripts explore the structure of ferritins from the archaea species Archaeoglobus fulgidus and Pyrococcus furiosus using the Bio.PDB package.  
This code should first use the entrez Python module to perform a pairwise alignment of the two proteins.  
Next, the nglview widget is used to create interactive 3D models that can be used to explore the overall structure of the two proteins, as well as a mutated form of A. fulgidus ferritin with a very different structure.  
Finally, the NeighborSearch function is used to find what interactions may be occurring with key residues from the mutant & wild-type A. fulgidus ferritins, and their equivalents in P. furiosus. Nglview was then used to examine these interactions in 3D.

These scripts were created on a Jupyter Notebook ran through the cloud server ChemCompute. I found that Jupyter notebooks opened through Anaconda were unable to successfully use the nglview widget.  
https://chemcompute.org/jupyterhub/submit  
You should be able to access ChemCompute using your institutional login.  
The nglview widget should run on ChemCompute without additional install. If it does not work, try running:   
pip install nglview   
on a command terminal.

To Run:
1) Login to ChemCompute and reach the HOME / JUPYTERHUB / SUBMIT page
2) Create a new Python 3 (ipykernel) notebook
3) Copy and paste the .md files into separate cells in the following order:

a) entrez_import.md  
b) efetch.md  
c) alignment.md  
d) structure_visualise.md  N.B: The sections of this code which create the view models using the nglview widget should be run in separate cells  
e) A_fulgidus_neighbor_search.md  
f) A_fulgidus_interaction_1.md  
g) A_fulgidus_interaction_2.md  
h) A_fulgidus_mut_neighbor_search.md  
i) A_fulgidus_mut_interaction.md  
j) P_furiosus_neighbor_search.md  
k) P_furiosus_interaction.md

The view models of the proteins are interactive.
Click and drag with the left mouse button to rotate the view.
Click and drag with the right mouse button to translocate your view without rotating.
Left click on sections of the protein to center the view on that point.
Scroll the mouse wheel to zoom in and out.
