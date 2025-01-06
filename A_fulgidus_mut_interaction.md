#Visualising the interface in A.fulgidus K150A/R151A ferritin

view_Afmut=nv.show_file(Afmut_structure)
view_Afmut.add_representation('cartoon')
view_Afmut.add_representation('ball+stick', selection=':A/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='element')
view_Afmut.add_representation('label', selection=':A.CB/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='black')
view_Afmut.add_representation('ball+stick', selection=':L/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='element')
view_Afmut.add_representation('label', selection=':L.CB/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='black')
view_Afmut.add_representation('ball+stick', selection=':F/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='element')
view_Afmut.add_representation('label', selection=':F.CB/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='black')
view_Afmut.add_representation('ball+stick', selection=':G/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='element')
view_Afmut.add_representation('label', selection=':G.CB/0 and (145 or 146 or 149 or 150 or 151 or 152)', color='black')
view_Afmut.center(selection='150:A/0')
view_Afmut
