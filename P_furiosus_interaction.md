view_Pf=nv.show_file(Pf_structure)
view_Pf.clear_representations
view_Pf.add_representation('cartoon', color='chainname')
view_Pf.add_representation('ball+stick', selection=':0/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='element')
view_Pf.add_representation('label', selection=':0.CB/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='black')
view_Pf.add_representation('ball+stick', selection=':G/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='element')
view_Pf.add_representation('label', selection=':G.CB/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='black')
view_Pf.add_representation('ball+stick', selection=':H/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='element')
view_Pf.add_representation('label', selection=':H.CB/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='black')
view_Pf.add_representation('ball+stick', selection=':2/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='element')
view_Pf.add_representation('label', selection=':2.CB/0 and (143 or 147 or 148 or 149 or 150 or 153)', color='black')
view_Pf.center(selection='149:0/0')
view_Pf
