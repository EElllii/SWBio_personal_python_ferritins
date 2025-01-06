#Create a  pairwise alignment of the two ferritin genes

from Bio import Align
aligner = Align.PairwiseAligner(match_score=1.0, mismatch_score=-2.0, gap_score=-2.5)   #Creating an object needed to perform a  pairwise alignment
#The scoring used is the normal BLAST scoring parameters

alignments = aligner.align(record_Af.seq, record_Pf.seq)
#Using the .seq elements of the retrieved entries for the alignment

alignment = alignments[0]
print(alignment)                                   #Prints out the alignments
print(alignment.counts())                          #Prints the number of identities, mismatches, gaps etc. for the alignment
print(aligner.score(record_Af.seq, record_Pf.seq)) #Prints out the alignment 'score'
