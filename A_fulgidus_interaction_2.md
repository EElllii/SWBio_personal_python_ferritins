#Create a zoomed-in view of an example of the second interaction mode

view_Af=nv.show_file(Af_structure)
view_Af.add_representation('cartoon')
view_Af.add_representation('ball+stick', selection=':B/0 and (150 or 151)', color='element')
view_Af.add_representation('label', selection=':B.CG/0 and (150 or 151)', color='black')
view_Af.add_representation('ball+stick', selection=':D/0 and (145 or 146 or 150 or 151 or 152 or 155)', color='element')
view_Af.add_representation('label', selection=':D.CG/0 and (145 or 146 or 150 or 151 or 152 or 155)', color='black')
view_Af.add_representation('ball+stick', selection=':I/0 and (111 or 116 or 119)', color='element')
view_Af.add_representation('label', selection=':I.CG/0 and (111 or 116 or 119)', color='black')
view_Af.center(selection='151:B.N/0')
view_Af
