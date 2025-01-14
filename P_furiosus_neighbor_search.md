#Performing the neighbor search for P. furiosus
Pf_id = '2x17'     
Pf_filename = pdb_list.retrieve_pdb_file(Pf_id, pdir='datasets', file_format='mmCif')
Pf_data = os.path.join('datasets', '2x17.cif')

#Parse the mmCIF file into a structure object

Pf = parser.get_structure('2x17', 'datasets/2x17.cif')   
atoms = Pf.get_atoms()
atom_list = list(atoms)

cutoff_distance = 5  #Maximum distance for a neighbor (usually in A)
neighbor_search = NeighborSearch(atom_list)  #Creates a search variable for the selection

for residue in Pf.get_residues():     
    if residue.resname=='PRO' and residue.id[1] == 148 or residue.id[1] == 149 or residue.id[1] == 150:       
        coord = residue['CB'].get_coord()                 
        neighbors = neighbor_search.search(coord, cutoff_distance, level='R') 
        print(residue.resname, residue.id[1], residue.parent, 'Neighbors:')
        for neighbor in neighbors:
            if neighbor == residue or neighbor.resname == 'HOH':
                pass
            elif neighbor.parent == residue.parent and float(neighbor.id[1]) == float(residue.id[1])+1 or float(neighbor.id[1]) == float(residue.id[1])-1:
                pass
            else:
                print('', neighbor.resname, neighbor.id[1], neighbor.parent)
        print('')           #Adds a gap
    elif residue.id[1] == 148 or residue.id[1] == 149 or residue.id[1] == 150:       
        coord = residue['CG'].get_coord()                 
        neighbors = neighbor_search.search(coord, cutoff_distance, level='R') 
        print(residue.resname, residue.id[1], residue.parent, 'Neighbors:')
        for neighbor in neighbors:
            if neighbor == residue or neighbor.resname == 'HOH':
                pass
            elif neighbor.parent == residue.parent and float(neighbor.id[1]) == float(residue.id[1])+1 or float(neighbor.id[1]) == float(residue.id[1])-1:
                pass
            else:
                print('', neighbor.resname, neighbor.id[1], neighbor.parent)
        print('')  

#The code was modified slightly so that if the residue chosen by the for loop was a proline the coordinate used for the neighbor search was the beta-carbon
#While if the residue chosen was not a proline the cooridnate used was the delta-carbon (fourth carbon in side chain)
