#The neighbor search suggested that K150 and R151 could interact with neighboring residues in two different modes

#Create a zoomed-in view of an example of the first interaction mode

view_Af=nv.show_file(Af_structure)
view_Af.add_representation('cartoon')
view_Af.add_representation('ball+stick', selection=':A/0 and (145 or 146 or 150 or 151)', color='element') #Turns selected residues into a ball and stick representation
view_Af.add_representation('label', selection=':A.CG/0 and (145 or 150 or 151)', color='black')     #Adds a label of residue name and number
view_Af.add_representation('label', selection='146:A.CB/0', color='black')
view_Af.add_representation('ball+stick', selection=':H/0 and (111 or 116 or 119)', color='element') 
view_Af.add_representation('label', selection=':H.CG/0 and (111 or 116 or 119)', color='black')
view_Af.add_representation('ball+stick', selection=':F/0 and (150 or 151)', color='element')
view_Af.add_representation('label', selection=':F.CG/0 and (150 or 151)', color='black')
view_Af.center(selection='151:A/0')        #Centers the default view on R151
view_Af

#The selection instruction has the format :chain_id/model_id and (residue_id's). For a single residue it would be residue_id:chain_id/model_id.

#Residues are coloured by element: Red = Oxygen; Blue = Nitrogen; Yellow = Sulphur
