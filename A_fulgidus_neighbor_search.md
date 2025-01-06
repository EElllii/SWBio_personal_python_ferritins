#Using a NeighborSearch to find what residues are in close proximity to K150 and R151

#Import the native A. fulgidus ferritin structure as an mmCIF file

Af_id = '1s3q'     
Af_filename = pdb_list.retrieve_pdb_file(Af_id, pdir='datasets', file_format='mmCif')
Af_data = os.path.join('datasets', '1s3q.cif')

#Parse the mmCIF file

from Bio.PDB.MMCIFParser import MMCIFParser
parser = MMCIFParser(QUIET=True)                         #Create a parse object
Af = parser.get_structure('1s3q', 'datasets/1s3q.cif')   #Parse the mmCIF file into a structure object
atoms = Af.get_atoms()
atom_list = list(atoms)

#Create the NeighborSearch function

from Bio.PDB import NeighborSearch

cutoff_distance = 5  #Maximum distance for a neighbor (usually in A)
neighbor_search = NeighborSearch(atom_list)  #Creates a search variable for the selection

#Perform a neighbor search for K150 and R151

for residue in Af.get_residues():     #Begins a for loop running through every residue in the Af structure
    if residue.id[1] == 150 or residue.id[1] == 151:       #Only selects residues in positions 150 & 151
        coord = residue['CG'].get_coord()                  #Creates a variable of the coordinates of the gamma-carbon (third carbon in side chain)
        neighbors = neighbor_search.search(coord, cutoff_distance, level='R') #Performs a neighbor search from the gamma-carbon coordinate. Level='R' means that it is searching for residues, not atoms
        print(residue.resname, residue.id[1], residue.parent, 'Neighbors:')
        for neighbor in neighbors:
            if neighbor == residue or neighbor.resname == 'HOH':
                pass
            elif neighbor.parent == residue.parent and float(neighbor.id[1]) == float(residue.id[1])+1 or float(neighbor.id[1]) == float(residue.id[1])-1:
                pass
            else:
                print('', neighbor.resname, neighbor.id[1], neighbor.parent)
        print('')           #Adds a gap
        
#The conditional if function within the for loop prevents waters being included, and also stops the residue itself or its immediate primary neighbors in the same polypeptide being recorded
