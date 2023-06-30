# MADDOG results

Due to the way MADDOG runs on climb vs on your own laptop, the climb run would take far too long to complete! Instead, we'll stop the run by pressing ctrl + z and use the output from an earlier run I completed on this dataset!

# Task 1

Go to the folder shared-team/MADDOG/Example_designation/

You'll see all the new folders and files produced by the MADDOG run!

Start by looking in Report/report.html

This summarises all the MADDOG outputs in a html file. This doesn't work 100% on climb and you'll notice Figure 2 is missing (we'll look at that separately!), but when you run this on your own laptop everything will be included and formatted correctly. 

Read through the file and answer the following questions:
1. How many lineages are there? How does this compare to our answer with assignment? Why is it different?
2. Which lineage was first detected from this dataset?
3. How have the lineage dynamics changed over time? 
4. What are the 2 most prevalent lineages in the dataset? How many sequences do they each have?
5. Looking at table 5, do you think this is an emerging or undersampled lineage? Why?

# Task 2

We'll now look at the missing Figure 2. This can be found in MADDOG/Example_designation/Figures/Example_designation_sunburst.html.

You'll need to download and open the file to view it.

This is called a sunburst plot. It's a way of showing how lineages are related, and how many sequences are in each lineage. We start in the middle with the broadest ancestor of all the lineages, and each circle moving outwards represents a lineage descended from the one inside it. 

E.g. Lineage SEA4_D1 is descended from SEA4_A1.1.2, which is descended from SEA4_A1.1 and so on. 

The plot is interactive! You can hover your mouse over a section to reveal the number of sequences, and click on a section to zoom in on it. To zoom back out, keep clicking on the innermost circle. 

E.g. If you click on SEA4_A1.1, it will zoom in to only include this lineage and those descended from it. Click the SEA4_A1.1 circle to zoom out, and then keep clicking the inner circle until RABV is the inner circle again. 

By exploring the sunburst plot, try to answer the following questions:

1. Which lineage is SEA4_C1 descended from?
2. How many lineages are *direct* descendants of SEA4_A1 (e.g. only 'children', not further descendants)
3. How many sequences from this dataset are from lineage SEA4_A1.2?
4. How many sequences from this dataset are from lineage SEA4_A1.2.1? Why is it included?
5. How many 'levels' of lineages from RABV to SEA4_C1.1.1?
6. If this dataset represents everything we know about lineages in a region, what might some discussion points be about lineage diversity in the region?


# Task 3

Although the summary is very useful, MADDOG also produces other outputs. Some of which we can use for further analsyis. 

The most important of these is MADDOG/Example_designation/Outputs/sequence_data.csv

It might be easiest to download this file and open it in excel so we can sort and view the data more easily.

Have a look at this file and answer the following questions:

1. What lineage is sequence 11 from?
2. Which sequence is most closely related to sequence 101? Could we tell this from GLUE? Could we tell this from our previous assignment output? Why/why not?

3. Given all of the outputs you've looked at here - what further analysis would you do? What further figures would be useful to produce?

4. How do you think detailed lineage information could help with your own research? Try to formulate some research questions that could be addressed using your own current/planned sequencing activities and lineage designation! 

