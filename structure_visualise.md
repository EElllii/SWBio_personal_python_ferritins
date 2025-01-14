#Retrieve the PDB files

from Bio.PDB import PDBList

pdb_list= PDBList() #Creates a PDBList instance
Af_id = '1s3q'     #Choose the PDB ID of your desired structure
Af_filename = pdb_list.retrieve_pdb_file(Af_id, pdir='datasets', file_format='pdb')
#Downloads the specified file


Pf_id = '2x17'     
Pf_filename = pdb_list.retrieve_pdb_file(Pf_id, pdir='datasets', file_format='pdb')
#Downloads the specified file

Afmut_id = '3kx9'
Afmut_filename = pdb_list.retrieve_pdb_file(Afmut_id, pdir='datasets', file_format='pdb')

import os
Af_structure = os.path.join('datasets', 'pdb1s3q.ent')
Pf_structure = os.path.join('datasets', 'pdb2x17.ent')
Afmut_structure = os.path.join('datasets', 'pdb3kx9.ent')

#The code for displaying the proteins is best executed in separate cells

#Creating a view model of A. fulgidus ferritin
import nglview as nv

view_Af=nv.show_file(Af_structure)   #Creates a view model of the A. fuglidus ferritin structure
view_Af.add_representation ('surface', opacity=0.15)  #Adds a space-filling representation at 15% opacity
view_Af                                               #Views the interactive 3D model

#Creating a view model of P. furiosus ferritin

view_Pf=nv.show_file(Pf_structure)   #Creates a view model of the P. furiosus ferritin structure
view_Pf.add_representation('surface', opacity=0.15)
view_Pf 

#Create a view model of K150A/R151A mutant A. fulgidus ferritin 
view_Afmut=nv.show_file(Afmut_structure)  
view_Afmut.add_representation ('surface', opacity=0.15) 
view_Afmut 
