# Further Phylodynamics and Phylogeography

## Contents

* [4.2.2: Further Phylodynamics and Phylogeography](#4.2.1-tree-building)
	+ [4.2.2.1: Tempest](#4.2.1.1-preparation)
	+ [4.2.2.2: BEAST](#4.2.1.3-model-selection)
	+ [4.2.2.3: SPREAD](#4.2.1.4-tree-building)
	+ [4.2.1.5: Tree visualisation](#4.2.1.5-tree-visualisation)
	+ [4.2.1.6: Extracting metadata](#4.2.1.6-extracting-metadata)
	+ [4.2.1.7: Annotating the tree](#4.2.1.7-annotating-the-tree)
	
## 4.2.2: Further Phylodynamics and Phylogeography

In this practical you will be briefly introduced to further phylodynamic and phylogeographic analyses that can be undertaken. This is in no way a complete tutorial, and should you want to recreate the analyses viewed here you should complete the tutorials available at https://beast.community/index.html. Instead, you will be introduced to some initial concepts, and the end results you can expect to achieve.

For this practical we will be using premade datasets and trees from rabies virus sequences from the Cosmopolitan AF1b_B1.1.1 lineage. 



## 4.2.2.1: Tempest

Once you have your tree and the collection date associated with each sequence, you can do some further analysis! We first want to check if the data shows a temporal signal. We do this using Tempest, which can be downloaded from http://tree.bio.ed.ac.uk/software/tempest/ 

Tempest needs a tree and a set of dates to run.

___

### Task 1

Download the AF1b_B1.1.1 .contree and .txt files in `shared-team/Phylogenetic_data/`

Open the metadata file in excel and make a note of the format the dates are written in.

___

### Task 2

Open tempest and, when prompted, select the .contree file you just downloaded

___

### Task 3

Click `import dates` and select the metadata file you just downloaded.

Select `Parse as calendar date` and enter the date format you noted in the first step.
Hint: press the question mark button next to the entry box to see how this should be written! 

___

You should see a list of dates appear beside the sequence IDs in Tempest. If you've parsed the dates correctly, the date for `KY210234` should be `2011.5013698630137`.

We can now assess the temporal signal of the data. 

___

### Task 4

Click the `root-to-tip` tab, then select the box in the top left corner titled `best-fitting root`. Each sequence is now represented by a dot, indicating the divergence of the sequence from the root (or MRCA) over time. Sequences with more divergence than expected appear above the line, while sequences with less divergence than expected appear below the line. 

___

### Task 5

Click the `tree` tab. You'll notice that some of the branches are coloured red and blue. If you draw a box around the tip by clicking and dragging with your mouse, you'll highlight the tip. With the sequence highlighted, click back on the `root-to-tip` tab. The sequence you selected is now highlighted here too. 

Using the information here, and highlighting the sequences of interest, figure out:

  1. What do red branches mean?
  2. What do blue branches mean?
  
___

### Task 6

Tempest can also give initial predictions of the age of the root (the time the MRCA of all the sequences occured) and the rate of evolution, in substitutions per sute per year. In the `root-to-tip` tab, try to figure out:

  1. When was the MRCA of these sequences predicted to have been?
  2. What is the estimate of evolutionary rate?

  3. Do you think this data shows good temporal signal? 
      + Why, and what evidence backs this up?
      
___

