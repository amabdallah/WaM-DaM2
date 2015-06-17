#### The Water Management Data Model (WaM-DaM)

Water Management Data Model (WaM-DaM) is a persistent information model to organize and synthesize disparate systems Water management data. The information model aimes to help scientists and practitioners organize, search, discover, and interpret their disparate and diverse data to save time plus facilitate modeling.

WaM-DaM supports this collection of nine data types that are used in systems analysis: binary, numeric parameters, seasonal, parameters, file based, rules, time series, and multi-column arrays. WaM-DaM uses modulur objects of data with their attributes. Objects can be replicated as instances with specific data for resources and infrasturcutre componanants.The componnanats can be connected through a network of nodes and links. WaM-DaM supports scenarios that track changes in networks and allows users to compare them and identify differences among scenarios.   

You can think of WaM-DaM as a repository of systems data (purple cylinder) plus a middle-person translator between the vast data sources at the left and your different models at the right as shown in this flowchart

![](https://github.com/amabdallah/WaM-DaM1.0/blob/master/Files/WIKI/WaM-DaM.jpg)


#### Getting Started with WaM-DaM
 
WaM-DaM informatio model is implemeted in a relational database which is ready for use to load your data into it. You can choose one of these relational database systems. If you are a beginner, We recommend you to use SQLite becasue it is very simple to use and set up, doesnt require a server, and you can use the free Mozzila FireFox Manager to interact with its data.  
Here are the SQL scripts that you can use to create a blank WaM-DaM database. The differences among them are minor and technical due to differences in physical data types used by each system.
* [SQLite](https://github.com/amabdallah/WaM-DaM1.0/blob/master/Files/BlankSchemas/WaM-DaM_for_SQLite.sql)
* [Microsoft SQL Server] (https://github.com/amabdallah/WaM-DaM1.0/blob/master/Files/BlankSchemas/WaM-DaM_for_MSSQL.sql)
* [MySQL](https://github.com/amabdallah/WaM-DaM1.0/blob/master/Files/BlankSchemas/WaM-DaM_for_MySQL.sql)
* [PostgreSQL](https://github.com/amabdallah/WaM-DaM1.0/blob/master/Files/BlankSchemas/WaM-DaM_for_PostgreSQL.sql)

Check out the [Instructions](https://github.com/amabdallah/WaM-DaM/blob/master/docs/SQLiteInstructions%20.md) on how you can set up a WaM-DaM database in SQLite. The instructions are demostrated live in a video screenshot :)

#### Documentation of WaM-DaM
Here we document the archtercher of WaM-DaM design to help you make sense of its tables and how they're connected. WaM-DaM has 48 interrelated tables that are organized into four groups: i) Core constructs (blue) which represent the key configuring constructs of WaM-DaM modular design, ii) Metadata (orange) which represents key metadata that help users correctly and unambiguously interpret their data, iii) Controlled Vocabularies (CVs) (purple) which enforces the consistent use of terms across disparate data sources (only one CV box is shown for simplicity), and iv) Data Storage (red) which holds data values of different types based on the user’s choice (e.g., time series and text)
[Documentation](https://github.com/amabdallah/WaM-DaM/wiki/Documentation)

 Check out the current WaM-DaM logical data model [schema](http://amabdallah.github.io/WaM-DaM/




#### View Diagrams and Documentation of the WaM-DaM Schema


#### Data Use Cases
Matlab Script to load data to WaM-DaM SQLite [here](https://github.com/amabdallah/WaM-DaM/blob/master/Files/MatlabScript/AutomateLoadingDataToWaMDaM.m) 

Populated SQLite WaM-DaM database [here]()


Check out the use cases and their results at the WIKI pages [here](https://github.com/amabdallah/WaM-DaM1.0/wiki/Use-Cases)



#### Publications:
A preliminary WaM-DaM design was published in 2014 as a peer-reviewd conference paper:
[WaM-DaM:A Data Model to Organize and Synthesize Water Management Data](http://www.iemss.org/sites/iemss2014/papers/iemss2014_submission_406.pdf)

Please cite WaM-DaM as:
Abdallah, A., Rosenberg, D., 2014. WaM-DaM: A Data Model to Organize and Synthesize Water Management Data. In: Ames, D.P., Quinn, N.W.T., Rizzoli, A.E. (Eds.), Proceedings of the 7th International Congress on Environmental Modelling and Software, June 15-19, San Diego, California, USA. ISBN: 978-88-9035-744-2

#### Presentatons:
Check out the profiesnioan and conference [presentations] (https://github.com/amabdallah/WaM-DaM/blob/master/docs/Presentations.md)


For more info, please free to email Adel Abdallah at:
amabdallah@aggiemail.usu.edu


## Sponsors and Credit 

This material is based upon work supported by the National Science Foundation Grant [NSF grant](http://www.nsf.gov/awardsearch/showAward?AWD_ID=1135482) . Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the National Science Foundation.

This WaM-DaM project is funded as part of the CI-Water Project. An interdisciplinary team of Utah and Wyoming researchers has received a $6 million, three-year award from the National Science Foundation (NSF) to develop a better understanding of the interconnectivity of natural and human water resources systems – a critical environmental sustainability problem facing both Western states.

The award will allow the team of researchers to develop high-performance computer modeling and computational resources (known as cyberinfrastructure or CI for short) to simulate and study how factors such as population growth, shifting land uses and climate variability will impact water storage and availability in the Intermountain West. This award is made under the NSF Experimental Program to Stimulate Competitive Research (EPSCoR), which supports states' efforts to enhance research, science and mathematics education, and workforce development.

The CI-WATER project includes researchers from Brigham Young University, the University of Utah, Utah State University, and the University of Wyoming. BYU and the University of Wyoming are the lead institutions for their respective states in the consortium.

This work is part of a large cyberinfrastructure project [(CI-WATER)](http://ci-water.org/) to advance water resources modeling that involves Utah State University, Brigham Young University, University of Utah and University of Wyoming. 

Check out WaM-DaM documentation and development at the [GitHub Wiki](https://github.com/amabdallah/WaM-DaM1.0/wiki)



[![NSF](http://www.nsf.gov/images/logos/nsf1v.jpg)](http://www.nsf.gov/awardsearch/showAward?AWD_ID=1135482&HistoricalAwards=false)[![CI-Water](http://ci-water.org/images/logo/ciwater.png)](http://ci-water.org/)



