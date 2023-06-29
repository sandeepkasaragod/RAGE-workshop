# EXTENSION ACTIVITY - Trees in R

## 4.2.1b.8: Trees in R

We can also visualise trees using R! This means we code and create all our figures in one file, and keep colour schemes consistent across them all. It also can be really useful for automation, as we'll see later!

We'll build upon the script you've just written.

This should currently read something like:

```
alignment<-seqinr::read.alignment("/home/user1/Phylogenetic_analysis/omicron_subset_countries.fasta", format = "fasta")

m<-data.frame(ID = alignment$nam, country = NA)

m$country<-sapply(strsplit(m$ID, "/"), "[", 1)

m$country[which(m$country != "Philippines")]<-"Other"
write.table(m, file = "/home/user1/Phylogenetic_analysis/omicron_subset_countries_PHLOther.txt", sep = "\t", row.names = FALSE)
```

___

### Task 24

We need to install some more packages first!

`install.packages("ape")`
`install.packages("BiocManager")`
`BiocManager::install("ggtree")`
`install.packages("ggplot2")`

We now need to import our tree into R

Add in R this code: `tree<-ape::read.tree("PATH_TO_TREE")`, replacing `PATH_TO_TREE` with the filepath to the `.contree` file you created. 

You should now see this appear in your environment tab.

___

We now want to plot our tree. We can do this using a package called `ggtree`

___

### Task 24

Call on the ggtree library by running `library(ggtree)`

Run the following code:
```
plot_tree<-ggtree::ggtree(tree, colour = "grey50", ladderize = T, size = 1) +
  ggtree::geom_tippoint(color="grey50", size=2)+
  ggtree::geom_tiplab()
```

This makes the tree and saves it in the R environment as `plot_tree`

Normally, we could make this appear in the plot window in R, however using the server we will have to save and download the figure to view it.

To do this, we use ggsave from the ggplot2 library:

`ggplot2::ggsave("PATH_TO_DIRECTORY/tree.png", plot_tree)`

Replacing `PATH_TO_DIRECTORY` with the full path to your Phylogenetic analysis directory.

In the bottom right window of R, under the files tab, if you navigate to your Phylogenetic_analysis directory, you should see `tree.png` saved there. Click this to view it!

___

### Task 25

Change the `plot_tree` command so the first line `colour = "black"` and `size = 1`, and the second line `colour = "blue"` and `size = 0.5`. Again, save and view the tree. 

What do these arguments do?

___

### Task 25

Remove the 3rd line of the tree code, and the plus, so it reads: 


```
plot_tree<-ggtree::ggtree(tree, colour = "grey50", ladderize = T, size = 1) +
  ggtree::geom_tippoint(color="grey50", size=2)
```

Save and view this tree. What did this argument do? 

___
### Task 26

We can also incorporate our annotations into the tree!

We should still have `m` in our environment window, which details Philippines or Other for each tip.

Run the following code:

```
plot_tree<-ggtree::ggtree(tree, colour = "grey50", ladderize = T, size = 1) %<+% m +
  ggtree::geom_tippoint(color="grey50", size=2) +
  ggtree::geom_tippoint(ggplot2::aes(color=country), size=1)
  
```

Save and view the tree. What has this line of code done? Can you identify which tips represent sequences from the Philippines?

___

### Task 27

Play around with the arguments you've been testing to make a tree you're happy with and save the tree.

You should also save your R Script!

___
