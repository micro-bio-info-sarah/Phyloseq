# Phyloseq
Some code to phyloseq package utilisation
#Sarah HUET, master degree internship (2018) ; huetsarah49@live.fr
#Script to write a fasta file from a phyloseq object

#PS : phyloseq object 

library(seqinr)

#we extract the taxa_table from the PS
pstaxa = as.data.frame(tax_table(PS))

#we give a specific id to each taxa
#here, the id we'll be as : Mx_Genus (for x rows)
pstaxa$id = paste0("M",1:nrow(pstaxa),"_",pstaxa$Genus)
#we extract the sequences to a list
seq = as.list(rownames(pstaxa))
#we write the fasta file
write.fasta(seq,pstaxa$id,file.out = "C:/Users/my_folder/my_pstaxa.fasta" )
