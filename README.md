# protein_analysis-Help manual for user
### (It needs to be used on the university of Edinbburgh bioinformatics server terminal)

This program can take user input (protein name/taxonomical group name) and generate protein sequence data from NCBI in a fsata format. After that this program will perform several checks of the original fasta file. Then this program will plot the level of conservation, search for motif based on Prosite database, and at last plot the phylogenetic tree. The details of all these procedures are as follow:

### 1.	Input

![图片 1](https://user-images.githubusercontent.com/46657555/74937588-42684500-53e4-11ea-86f6-d0e276bda457.png)

(1) First the program will ask for the name of the protein and taxonomy group. Make sure that the name is typed in correctly. If the input taxonomy group name cannot be found in the database, the program will give a warning message and ask again .
 
(2)	Remember if you don’t want to search the whole field, type in the name like glucose-6-phosphatase[PROT] and aves[organism].

(3)	Then choices will be given to determine whether partial/predicted sequence is wanted or not. Make sure that you choose one of the instructions in the bracket (). For unrecognized instruction, a warning message will appear and ask you to type in again.

(4)	If more than 10,000 sequences are found, the program will automatically ask the user to refine the search input. Because the default setting of maximum sequence that can be handled at one time is 10,000.

(5)	At the end the program will offer information of how many species are there and print a list of names. During this stage, you can choose whether to move on or change the name of the group name typed in (figure 1.2).

![图片 2](https://user-images.githubusercontent.com/46657555/74937726-94a96600-53e4-11ea-80de-42952b96c0f1.png)

Figure 1.2
use glucose-6-phosphatase [PROT] and aves[Organisms] as query

### 2.	Level of conservation

(1) If there are less than 250 sequences found in the database, the program will directly enter the conservation check stage.

(2) If there are more than 250 sequences, to insure the accuracy, the program will only pick out the most similar 250 sequences for future analysis;

(3) A plot indication the level of conservation between protein sequences will be shown in Firefox (as shown in figure 2.1) and be saved in the working directory as “plotcon.svg”.
 
 ![图片 3](https://user-images.githubusercontent.com/46657555/74937844-cae6e580-53e4-11ea-8507-0e89c25bf61f.png)
 
 Figure 2.1
y-axis represent the similarity score, the higher the score the more the similarities; x-axis represent the position of each protein base. This picture is based on the input “glucose-6-phosphatase [PROT], aves[Organism],not partial and not predicted

(4)	The user needs to close the Firefox to enable the code continue to the next stage.

### 3.	Motif searching

(1) This program will search for motif in the subset’s sequences (250 most similar) base on prosite databse.

(2) At the end of the program, a list of motifs being found will be printed to the screen (figure 3.1).
 
![图片 4](https://user-images.githubusercontent.com/46657555/74937917-f669d000-53e4-11ea-942c-03a3be8663b1.png)

Figure 3.1, 
use glucose-6-phosphatase [PROT] and aves[Organisms] as query

(3) A file named “summary_motif.txt” containing protein sequence name and its related motif will be saved in the current working directory.

### 4.	Phylogenetic tree

(1)	A phylogenetic tree will be generated based on the MSA output file. User can access the output by opening a file called “pseq.out.iqtree”.
