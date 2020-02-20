# Maintenance Manual
1. INTRODUCTION
Maintenance manual for developer
This maintenance manual provides information regarding three aspects of the program: System Description, Support Environment and Error Conditions.
System Description talks about the aim and work flow of the whole program. Support Environment is about the equipment support environment (support software, database used etc). Error Conditions gives details information of possible errors in each unit of the program.
2. SYSTEM DESCRIPTION
2.1 System Application
This pipeline program built using Python3 is aiming at analyzing a user-defined subset of protein sequence. This program can take user input (protein name/taxonomical group name) and generate protein sequence data from NCBI in a FASTA format. After that this program will perform several checks of the original FASTA file. Then this program will plot the level of conservation, search for motif based on Prosite database, and at last plot the phylogenetic tree.
2.2 System Organization
This program is composed of 4 big units. Below the process flowchart of this program (figure 2.1) can be found.
Ø First one is to get the user input specifying the protein family and the taxonomic
group. Then the input will be passed to Edirect (bash script) to generate a FASTA sequence file from NCBI. During this whole stage the user can choose (1) whether partial/predicted sequence is wanted; (2) whether to move on based on the number of sequence/species in the output file. For each user input, a while-loop error trap is created to make sure the input is valid.
Ø Second part is plotting the level of conservation. For an output with less than 250 files, this program will directly perform Clustalo Multiple sequence alignment and plotcon. If there are more than 250 sequence, a consensus sequence will be generated using cons (from EMBOSS). After this, blast will be performed to find the 250 sequences with the highest identities. The processed (replace all the gap “-” with space) consensus sequence is the input sequence. And the original fasta protein sequence file generated from step1 will be the database.
Ø Third part will perform motif searching from Prosite database using patmatmotifs (EMBOSS). Patmatmotifs can only examine one sequence per time. A for loop is created that can extract one sequence each time, and then perform patmatmotifs. Also, the output file from patmatmotifs will be overwritten each time. So inside
