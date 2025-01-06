#Import the protein sequences for the two ferritins

#Import the Entrez module
from Bio import Entrez
Entrez.email = 'rx20205@bristol.ac.uk'

#Create a record list of the A. fulgidus ferritin accession numbers
handle_Af = Entrez.esearch(db="protein", term="Archaeoglobus_fulgidus[Orgn] AND ferritin[Protein]", idtype="acc")
record_Af = Entrez.read(handle_Af)
print('Archaeoglobus fulgidus accession numbers', record_Af["IdList"])

#Create a record list of the P. furiosus ferritin accession numbers
handle_Pf = Entrez.esearch(db="protein", term="Pyrococcus_furiosus[Orgn] AND ferritin[Protein]", idtype="acc")
record_Pf = Entrez.read(handle_Pf)
print('Pyrococcus furiosus accession numbers', record_Pf["IdList"])


