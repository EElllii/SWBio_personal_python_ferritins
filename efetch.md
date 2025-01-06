#Checking the given accession numbers on the database, I chose WP_010878337.1 for A. fulgidus and WP_011011871.1 for P. furiosus.

#Retrieve the full entries for these accession numbers using Entrez.efetch
from Bio import SeqIO

handle_Af = Entrez.efetch(db="protein", id="WP_010878337.1", rettype="gb", retmode="text")
record_Af = SeqIO.read(handle_Af, "genbank")
print(record_Af)

handle_Pf = Entrez.efetch(db="protein", id="WP_011011871.1", rettype="gb", retmode="text")
record_Pf = SeqIO.read(handle_Pf, "genbank")
print('')
print(record_Pf)
