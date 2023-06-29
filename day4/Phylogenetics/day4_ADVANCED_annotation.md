# Tree Annotation - Advanced


## 4.2.1b.6: Extracting metadata

We can add additional information to our tree. Sometimes the sequence IDs contain useful information that we want to extract. 

___

### Task 13

Going back to the VM, use `grep` to take a look at the format of the sequence IDs in your fasta file.

What information might we want to extract from the sequence IDs?

### Data Processing in R

To extract this information manually would take ages! Instead, we can write a pipeline in R to process this for us.

___

### Task 14

Open RStudio. This can be done within the VM. Click the plus button above the menu, and select RStudio. 

___

### Task 15

You first need to install the necessary libraries using `install.packages("seqinr")`

You'll need to import the `omicron_subset_countries_aligned.fasta` file you created. This first involves knowing where it is. You can find this out using the command `file.choose()`. This will open a window where you can navigate your directories and select the file in `Phylogenetics_analysis`. The full path to this will appear in the console in R studio. 

To import and store your alignment in R, run:
`alignment<-seqinr::read.alignment("PATH_TO_FILE", format = "fasta")` replacing the PATH_TO_FILE with the path you generated in the last step. 

Running this command should result in an element called `alignment` appearing in the environment tab in Rstudio. 

___

### Task 16
We're now going to create a table listing the country for each sequence. First, we'll create a table with all the sequence IDs and an empty country column ready to fill with data:

`m<-data.frame(ID = alignment$nam, country = NA)` 

This table should now have appeared under the alignment in your environment tab! Click on it to take a look.

___

### Task 17

You should have seen from looking at the sequence IDs that the information in the ID is separated by `/`s, with the country being the first element. We can therefore write some code to split the ID by the `/` and extract the first element:

`m$country<-sapply(strsplit(m$ID, "/"), "[", 1)` 

If you click on table `m` in your environment tab, you should now see that the country column has been filled in! 

___

### Task 18

We now want to save this table in a form that can be used by FigTree to annotate our tree. This is tab delimited text. To save this:

`write.table(m, file = "PATH_TO_DIRECTORY/omicron_subset_countries.txt", sep = "\t", row.names = FALSE)` 

Replacing the PATH_TO_DIRECTORY with the full file path to your analysis directory (one step up from the file path we generated last time!).

If we check in our directory in the `Files` tab in the bottom right window in R, we should now see the `.txt` file! Check the box next to it, click the `More` tab along the top of the window, and select `export` to download to your computer.

___

## 4.2.1b.7: Annotating the tree

If we go back to our FigTree tree, we can now annotate it with the metadata file we just created! 

___

### Task 19

Check your annotations file by opening it in excel. If it all looks right, click save.

Import the annotations file in to FigTree. We do this by going to File->Import annotations and selecting the txt file we just made. 

We can now colour our tips by country! In the side tab, go to Tip labels and colour by country.

___

### Task 20

You can also colour branches according to your annotations. Go to Tree->Annotate Nodes from Tips and select `country` as the annotation. 

Now, if you go to the Appearance tab, you can colour by country. 

___

### Task 21

Again, play around until you have a tree you're happy with. 

When you've finalised your tree, you can export it by File->Export X where X is the file type. 

___

Go back to RStudio and try to extract some other useful metadata!

First, try extracting the year for each sequence. 

Most of the code will be the same as you ran before, but think about the element of the ID you want to extract! Hint: The working code will be at the end of this document if you need assistance!

___

### Task 22

Create and save a file for annotating by year in FigTree. 

Annotate your tree in FigTree with tips coloured by year.

___

It might also be useful to colour tips by country of interest - e.g. colour sequences from the Philippines one colour, and other countries another colour. 

You could do this by editing the country `.txt` file you made manually in excel. Or we can practice some R skills!

There are a few ways of doing this, but to save writing additional code, we can start with the same code we ran before to extract the countries.

Before we save the table, we want to convert any country that doesn't say `Philippines` to `Other`.

To do this, we need to find which entries do not say `Philippines`. For this we use the `!=` operator, meaning 'not equal to'. We then need to tell R which positions these entries are in the table (their row numbers), and tell it to change these row entries to 'Other':

`m$country[which(m$country != "Philippines")]<-"Other"`

Check table `m` to make sure this has changed, then save the file!

___

### Task 23

Create and save a file for annotating your tree in FigTree with tips colourd by PHL/Other

Annotate your tree in FigTree with tips coloured by PHL/Other 
___

Code for year colouring: 

`m<-data.frame(ID = alignment$nam, year = NA)`
`m$year<-sapply(strsplit(m$ID, "/"), "[", 3)`

