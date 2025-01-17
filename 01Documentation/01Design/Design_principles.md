### WaM-DaM Design principles


We elaborate on each of the eight common features identified in the previous section as design principles as the basis for a generic WaM-DaM design based on these motivating research questions: 
•	What are the basic attributes that are needed to describe the data values of different types (e.g., time series, multi-column arrays) for diverse water management systems and models? 
•	How to overcome semantic and syntactic heterogeneity in these attributes for disparate water management data for various domains?
•	How these identified attributes can be organized to answer the important data questions for users for to automate discovering data for models? 


The design pinciples of WaM-DaM are compiled based on the reviewed systems, important questions, and uses cases. It is the key contribution of WaM-DaM to support all these principles together: flexible and extensible modular design, networks, scenarios, conditional query for subsets of data, dynamic controlled vocabulary, reusable descriptive and explicit metadata, multiple data formats for systems models, and open-source environment.

|**Data management system**|Flexible and extensible|Supports networks|Supports scenarios|Dynamic controlled vocabulary |Reusable descriptive and explicit metadata|Multiple data formats for sys. models|Conditional query| Open source environment|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ODM | x | | | x | x  | | x  | x  |
| HydroPlatform | x | x |  |  |  | x  |  | x   |
| HEC-DSS | | x  |x   | | | x | |  |
|**Modeling Software**|   |
| RiverWare | | x  | x | | | x | |   |
| Arc Hydro | | x  |   | x  | | | | |
| WEAP | | x | x  | | | x | |   |
|**WaM-DaM**| x | x  | x  | x | x | x |x | x  |




#### 1. Flexible and extensible modular design
Modularity is a fundamental principle to achieve a flexible and extensible data model design (Connolly and Begg, 2010; Goodall et al., 2011; Kokkonen et al., 2003; Pokorný, 2006). The objected-oriented database systems use modules (Connolly and Begg, 2010) to create generic objects (also known as classes) of data. These object of data can represent virtual or physical components of the water resources system (e.g., a physical reservoir or a virtual water loss node). Users can then use the objects to create instances that are specific to a location and can take data values as in HydroPlatform (Harou et al., 2010). 

A flexible design allows users to configure their objects by associating with them as many properties as desired to represent qualitative or quantitative (i.e., variable) attributes. An extensible design allows users to create as many objects as desired to represent their water resource system components with no limitation to a set of pre-defined objects. Therefore, the modular design allows users to create infinite combinations of objects that fit their modeling needs (Wurbs, 2012; Zagona et al., 2001). In WaM-DaM a collection of objects and their configurations of associated attributes for a specific domain (e.g., water supply, wastewater collection) comprise a Data Structure. The Data Structure concept helps users configure, share, search, and reuse different combinations of water management objects for various domains. 

#### 2.	Networks
Systems analysis use vector networks to represent connectivity and interaction between water system components (e.g., node and link instances of object types) for a specific domain (Loucks et al., 2005) as in WEAP and RiverWare (Yates et al., 2005; Zagona et al., 2001). Other approaches use a mix of grids, triangulated networks, and node and links networks to represent their data in space like in Arc Hydro (Maidment, 2002), AdHydro (Lai et al., 2013), and Arc SWAT (Olivera et al., 2006). Systems analysis data as the focus on this paper aggregates internal changes within objects and represents them in the center of the node or constant along the link (Loucks et al., 2005). Therefore, tracking spatial changes within nodes (e.g., watershed) like Arc SWAT (Soil Water Assessment Tool) (Olivera et al., 2006) or within links like in the RiverML Data Model (Jackson, 2014) and the Arc River Data Model (Kim et al., 2015) is out of the scope of WaM-DaM.

Networks in WaM-DaM help researchers to organize and then search groups of instances that belong to a Data Structure in space. A network is a collection of node and link instances that are related for a meaningful purpose (e.g., evaluate water resources management alternatives) for a specific domain and are using one spatial reference or a coordinate system (e.g., NAD 83). In fact, a network is a specific implementation of a Data Structure, instances, and their data values within a spatial location (e.g., Bear River Watershed, Utah). For example, a Data Structure that replicates a WEAP model objects can be used to create separate WEAP model instances for the Bear River and the Weber River watersheds in Utah. Networks can be drawn to scale or they could be drawn as conceptual schematics of water systems. Nodes and links could be geo-referenced with longitude and latitude coordinates to reference the component center in space. 

#### 3.	Scenarios
A scenario represents a special case network of collection of instances with their data for a specific physical, operation, and socio-economic configuration of a systems model as supported in Hydra-Platform (Meier et al., 2014). Scenarios are important in systems analysis to examine implications of different management alternatives in the water system (Dong et al., 2013). WaM-DaM preserves different changes in the same network as scenarios to represent different configurations of networks. These changes could be due to alterations in the network topology, metadata, and data values. A scenario change in a network is either a one or a combination of these changes from the original network: i) add or remove an infrastructure element (i.e., topology), ii) change metadata (i.e., method or data source) for an attribute, iii) or change data values for an attribute. Data values of attributes may change over time like an inflow time series data for a reservoir in a future scenario. Data values might not change though, like a maximum capacity attribute for reservoir or a pipe. 
A network in WaM-DaM may contain many scenarios that could share identical network instances and their data. Thus, WaM-DaM does not duplicate similar networks data across its scenarios. Section 4 identifies how WaM-DaM supports comparing differences and similarities between scenarios of the same network. 

#### 4.	Conditional data queries
A relational data management system allows conditional queries for subsets of data that are required for different modeling needs. The relational data method supports data querying, population, and retrieval for various analyses (Horsburgh et al., 2008) using the standardized Structured Query Language (SQL) (Connolly and Begg, 2010). Relational data base systems (RDBMS) are known to increase the value of information, minimize data redundancy, improve data integrity, and enforce consistency (Connolly and Begg, 2010). Relational data models also can be implemented in any RDBMS like SQL Server, SQLite, MySQL, and PostgreSQL (Connolly and Begg, 2010). NoSQL recent technologies are promising like Cypher in Graph Database and yet to be stable and develop community standards (Robinson et al., 2013). Finally, Relational models are popular in the water resources community (Horsburgh et al., 2008; Maidment, 2002) and may applications have been developed on top on them like HydroDesktop (Ames et al., 2012). Thus WaM-DaM adopts the relational method and demonstrate its capabilities to query subsets of water management data across different sources.

#### 5.	Dynamic controlled vocabulary
Controlled vocabularies (CVs) are terms that are adopted with clear definitions to enforce the use of consistent terminology for data fields across disciplines. In WaM-DaM, names of attributes and objects are controlled to maintain consistency across multidisciplinary data and users. Dynamics CVs here mean that users can add new vocabulary if they choose to, and they are not limited to a static pre-defined vocabulary like in most of the reviewed data systems (Yates et al., 2005; Zagona et al., 2001). CVs have been successfully adopted to overcome semantic heterogeneity in time series data as in Horsburgh et al. (2008); (Horsburgh et al., 2011). 

To help search and discover terms, CVs are usually categorized into a set of hierarchal concepts and the relationships between them which is referred as ontology (Piasecki and Beran, 2009; Simons et al., 2013; Uschold and Gruninger, 1996). In addition, controlled vocabularies with their ontology, support interoperability across different models (Duval et al., 2002; Horsburgh et al., 2008; Moine et al., 2014; Piasecki and Beran, 2009). Interoperability in this context refers to the capability to relate and share data across different models irrespective of their original semantic and syntactic heterogeneity (Argent, 2014; Brandmeyer and Karimi, 2000). 

WaM-DaM uses CVs for many fields in the data model. At the same time, WaM-DaM preserves the native vocabularies that come with data sources and allows users to tag their own terms with WaM-DaM vocabularies. For example, a user can use the native attribute term “Area_mi” or “Area” in their model for a reservoir object and then tag them to the controlled term “surface area.” Tagging synonymous native data terms to the same controlled term relates them together. Users can search and discover various synonymous native vocabularies through the tagged CV term. Preserving native vocabularies would appeal to various multidiscipline users. Native vocabularies also help to export WaM-DaM data in the required native semantics. Section 4 elaborates how WaM-DaM represents CVs, their categories, and native vocabularies.
Developing a comprehensive list of CVs and their ontologies mainly for object and attribute names is out of the scope of WaM-DaM. So here we use several CVs as a proof of concept. Future work may develop a water resources community ontology for water management data like in Piasecki and Beran (2009) for time series data. 

#### 6.	Reusable descriptive and explicit metadata
Metadata are the ancillary information about data that helps users correctly and unambiguously interpret the meanings of data values. Metadata keep the data provenance that is needed to track the history and context of data like the sources, methods, people and organizations that contributed to create a data value (Campbell et al., 2013; Carata et al., 2014; DCMI, 2013; Goodman et al., 2014; Gray et al., 2005; Horsburgh et al., 2008; Pokorný, 2006). Metadata also help users asses the reliability, trustworthiness, and quality of data (Moreau and Missier, 2013). Several of the reviewed methods tend to only document units metadata which are important in modeling to keep track of quantities to maintain conservation of mass and energy. Other metadata like methods and sources are usually overlooked since they are not directly used in modeling algorithms. Thus users may document their sources and methods separately in reports or just keep them verbally.  

WaM-DaM strived to adapt the relevant metadata elements within the context of system analysis and tries to balance between the principles and practicality as recommended by Duval et al. (2002). Too much metadata can be overwhelming to users and too little metadata can be insufficient to correctly interpret data. WaM-DaM design is also driven by the key questions that users want to answer and example uses cases. Thus, WaM-DaM supports these metadata tables: the providing source of an attribute data values, the method of collecting data values of an attribute and whether there is modeling in generating data values, the organization and people who generate methods and serve as sources, and the unit of data values of an attribute. Other metadata elements may be incorporated to future WaM-DaM designs based on the needs of water resources community. 
A defined explicit structure of metadata (e.g., sources, methods) guide users to consistently document their metadata. A consistent metadata structure also helps users to access metadata directly and re-uses it to describe data values where applicable. Here we elaborate on each of these metadata constructs. 

#### 7.	Multiple data types for systems modeling
Systems modeling uses a variety of data types from simple binary, to categorical attributes, time series, and complex multi-columns data (Zagona et al., 2001). Table 1 lists nine data types that are frequently used in water management models to represent among others physical and operational data and provides their definitions. Section 5 elaborates how WaM-DaM incorporates these data types in the design. 

Here we discuss time series data because it is very common in hydrologic and systems data. However, WaM-DaM is designed to organize processed (i.e., aggregated) time series data. ODM can be used to complement WaM-DaM to organize original detailed and near real-time time series data (Horsburgh et al., 2008). So WaM-DaM supports metadata that is attached to the block of time series rather than every individual data value. Thus, WaM-DaM supports the important metadata that are necessary to unambiguously interpret time series data within the context of water management modeling. 

WaM-DaM uses the time scale triplet in time series data which represents i) extent which is the full time range over of measurements, ii) spacing which is the time spacing between measurements, and iii) support which is the time interval when statistical aggregation applies to a set of measurement and then the aggregated value is reported (e.g., hourly measurement values are averaged over a day to report daily values). Refer to (Tarboton et al., 2008) for further details on time scale triplet.
Additional or more complex data types can be incorporated in future improvements to WaM-DaM. Details on each data type are posted at the GitHub repository.

| Data type         | Definition   | Example |
| ------------- |:-------------|:-------------|
| Binary      | numerical values that refer to categorical duel status of an attribute |0 or 1 to a canal gate being “close” or “open” |
| Parameters      | parameter that changes with categorical time | dam elevation is 45.5 feet |
| Seasonal parameter      | categorical descriptive values that are re-used across instances. Each data value is a controlled vocabulary term | water right variable can have 20 acre-feet in winter and 5 acre-feet in summer or a water demand parameter can take 10 cfs at day and 5 cfs at night |
| Text Controlled      | descriptive value that can have any text data value | reservoir purpose “irrigation” and “flood control”|
| Text Free      | descriptive value that can have any text data value | a dam release rule could be stored as block of text |
| File based      | images, PDF documents, NetCDF and shape-files | images, PDF documents, NetCDF and shape-files |
| Rule       | relates attributes in an algebraic form | addition=Inflow + precipitation; withdrawal rate=outflow + evap. |
| Time series       | regular or irregular  numerical values with time stamps | stream discharge, evaporation, inflow, demand, supply, and model calibration sporadic time series data  |
| Multi Column Array     | a set of paired numeric values for two or more attributes (i.e., columns)| reservoir volume and surface area that change with elevation or water cost that changes with demand and time (e.g., month of the year)|


#### 8.	Open-source and free software environment
Public open-source software environment and code, promotes reproducibility and helps others to adopt and advance the development of models (Easterbrook, 2014; Goodman et al., 2014). Most of the reviewed data systems were either proprietary or they privately kept their source-code and data schema. WaM-DaM, its source-code, and documentation are available to the public at the GitHub collaboration repository github.com/amabdallah/WaM-DaM in an open-source environment under the New Berkeley Software Distribution (BSD) License, which allows for liberal reuse of the software and code. 

WaM-DaM as a generic data model will holistically support all these eight principles to meet the diverse needs of water management systems. The next section employs these eight principles and important design questions in conceptual, logical, and physical methodological design steps of WaM-DaM.



