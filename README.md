# BRIDGModel2Graph
BRIDG Model by version used to populate a Graph Database.

The BRIDG (Biomedical Research Intengrated Domain Group) is a publically-available model for semantic alignment of Clinical Outcomes data and its associated regulatory artifacts.  It is maintained by the BRIDG Semantics Coordinating Committee (SCC).  Questions about the BRIDG Model itself should be directed to that group: https://bridgmodel.nci.nih.gov

CIBMTR is a research collaboration between the NMDP and Medical College of Wisconsin: https://www.cibmtr.org/Pages/index.aspx.  CIBMTR manages definitions on the Clinical Outcomes information it gathers.  We are experimenting with using graph databases to organize the metadata about the Clinical Outcomes data recieved by CIBMTR.

This repository contains files that have been extracted from various BRIDG model versions and the scripts used to upload that data into a neo4j graph database.  The README file will briefly address setup activities so the scripts can be run.

I.    Install a neo4j database.  (Needs to be done only once)  
      A.  neo4j has instructions on how to install a neo4j database:https://neo4j.com/docs/operations-manual/current/installation/ 
      B.  Alternately, if using MacOS, use homebrew to download the latest neo4j repository: https://brew.sh/  
          1.  Using homebrew,  A directory is created for import files:
              /usr/local/Cellar/neo4j/3.5.0/libexec/import
II.   Copy the csv files for a version to the input file directory. (Needs to be done only once per version)
      A. To Be Done:  Instructions on how to get the input files from the repository
III.  Open a neo4j terminal session to run script. (Needs to be done every time you want to run a script)
      A.  To Be Done:  Instructions on how to get the input files from the repository
IV.   Validate the model version is complete. 
      A.  To be Done:  Instructions on how to validate everything exists.
