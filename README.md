# BRIDGModel2Graph
BRIDG Model by version used to populate a Graph Database.

The BRIDG (Biomedical Research Intengrated Domain Group) is a publically-available model for semantic alignment of Clinical Outcomes data and its associated regulatory artifacts.  It is maintained by the BRIDG Semantics Coordinating Committee (SCC).  Questions about the BRIDG Model itself should be directed to that group --> https://bridgmodel.nci.nih.gov

CIBMTR is a research collaboration between the NMDP and Medical College of Wisconsin -->  https://www.cibmtr.org/Pages/index.aspx.  CIBMTR manages definitions on the Clinical Outcomes information it gathers.  We are experimenting with using graph databases to organize the metadata about the Clinical Outcomes data recieved by CIBMTR.

This repository contains files that have been extracted from various BRIDG model versions and the scripts used to upload that data into a neo4j graph database.  The README file will briefly address setup activities so the scripts can be run.

I.    Install a neo4j database.  (Needs to be done only once) 

      A.  neo4j has instructions on how to install a neo4j database --> https://neo4j.com/docs/operations-manual/current/installation/ 

      B.  Alternately, if using MacOS, use homebrew to download the latest neo4j repository -->  https://brew.sh/  
	
          1.  Using homebrew,  A directory is created for import files -->
              /usr/local/Cellar/neo4j/3.5.0/libexec/import
	  

II.   Copy the csv files for a version to the import file directory. (Needs to be done only once per version)

      A. Clone or Download the files to your desired local directory.  If you Download in a zip format,  you can extract a desired version.
      
      	1.  Unless you change the default location of the import directory,  the csv files must exist in the import diretory.  (See above)
	
	2.  The txt file (the run script) should be in a convenient location to the cypher-shell utility.  For homebrew installations,  this is /usr/local/Cellar/neo4j/3.5.0/bin
	
III.  Open a neo4j terminal session to run script. (Needs to be done every time you want to run a script)
	
      A.  The neo4j database needs to be running. 
      B.  First Method:  Run the script in total
      
      [terminal]$ /usr/local/Cellar/neo4j/3.5.0/bin/cypher-shell -uneo4j -pne04j < Load_BRIDGModel_5_2_toNeo4j.txt  <return>
      
      
      C.  Second Method:  Run the script one line at a time
      [terminal]$ /usr/local/Cellar/neo4j/3.5.0/bin/cypher-shell. <return>
		username: neo4j
		password: *****
		Connected to Neo4j 3.5.0 at bolt://localhost:7687 as user neo4j.
		Type :help for a list of available commands or :exit to exit the shell.
		Note that Cypher queries must end with a semicolon.
		neo4j> 
		
		Cut and paste each command from the file Load_BRIDGModel_5_2_toNeo4j.txt to the cypher-shell session.  This allows you to monitor progress and errors.
	
IV.   Validate the model version is complete.

	A.   Run the following command to validate loaded versions are complete. (Table shows expected output)
	
		neo4j> MATCH (n:ClassName) return n.version, count(*);  <return>
		+----------------------+
		| n.version | count(*) |
		+---------------------+
		| "3.2"     | 233      |
		| "3.0.3"   | 202      |
		| "5.1"     | 320      |
		| "5.2"     | 326      |
		+----------------------+
		
	B.    Terminate the cypher-shell gracefully --> :exit <return>
		
	


