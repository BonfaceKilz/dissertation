


# Introduction

Current efforts in AI/ML are hampered by data that is difficult to access for both non-coders and intelligent machines\autocite{martens2018importance,stall2019make,wilkinson2016fair}. Effectively, even public data that is shared among different communities is often siloed because relationships between data elements have to be guessed from limited information, such as column headers and row names. This is a time-sink in terms of developer hours in trying to work out how to integrate and use such datasets.

In this data science project, I aim to unlock biological data so that it can be made available for machine analysis. I will start with the Genetwork public data repository that contains over 20 years of heterogeneous experimental data.

Genenetwork (GN) is a long-running bio-medical webservice that has been in existence since 1994\autocite{mulligan2017genenetwork,sloan2016genenetwork,wang2003webqtl}. GN aims to give researchers open-access FAIR data that they can run analysis on vis-a-vis: the web; API end-points; and live Jupyter notebooks inside self-hosted GNU Guix containers\autocite{theGuixEnvironment2022Gnu}. GN is uniquely centered on hosting genetics data, phenotyping, QTL and GWA studies in human and model species. Having all this data from different experiments spanning over 20 years in one database with a simple web UI allows any researcher to run analysis and correlate over many studies.

As part of my master's studies at Strathmore University, I has been writing functionality for the web front-end of GN. In the course of this work I have come to realize that underlying data structures&#x2013; some 80 cross-referenced SQL tables and many different additional file types&#x2013; make it hard to access this data for general data mining. A REST API was created to publish part of that data. However, REST API is rigid in it's endpoints, and it takes some level of developer dexterity to meet the needs of the API users. That said, it is clear that more flexible approaches are needed to increase the value of the service.  Unlocking the data means re-organizing the data. Not only that, I aim to make a copy of the current service that is hosted in Memphis TN, USA, and host it in Kenya at KEMRI/Wellcome Trust Kilifi. This will allow us to add African studies and data to GN using the latest methods, including homomorphic encryption of human data \autocite{mott2020private} and differential privacy \autocite{dwork2008differential}.

Underpinning the GN service is a mountain of data that is growing steadily, and with it new challenges, in particular: espousing clear relations between the data given a history of ad-hoc storage; fast data retrieval; non-obvious complex queries to do seemingly straight-forward tasks; connecting with other open databases (e.g. Uniprot) in a coherent way; and unclear means of adding new data that does not align with existing schemata. The aforementioned challenges GN faces present new opportunities to the scientific community; and in particular, African organizations that have faced similar problems. Having more semantic data that's easily accessible and shareable helps in pushing research work forwards. It would be a good first step in answering some difficult open biological questions such as: "There are 10,000's of mice with computable genomes that have never been born yet. Can we compute their phenotype before hand using our dataset?"

**Research Hypothesis**: Moving graph-like biological data from a SQL database into a graph-like structure, RDF, will make it [the data] more semantic, easier to share, and reduce developer hours required during system integration with other data systems.

**Expected Outcomes**:

-   Conversion of GN SQL dump to RDF, and in so doing, creating a tool that changes how data is input to GN.
-   Exposure of GN to SPARQL endpoints.
-   More performant and less complicated database queries with GN.
-   More semantic data structure that makes inserts more easier.
-   Easy integration with external systems such as Uniprot\autocite{apweiler2004uniprot}.

\clearpage

The three specific aims of this research project are:


### Aim 1: Improve the quality of data for Artificial Intelligence (AI) and Machine Learning (ML) tasks

As things stand, it is difficult to run an AI/ ML task against GN's database without creating a data warehouse&#x2013; ideally, such a task should be possible from the web interface. This difficulty is because we have complicated structures and relationships that have been forced on a rigid and constrained 2D tabular structure \footnote{Storing data in SQL is the current standard in biology} that would need human intervention to decipher; and tasks that require human intervention are prone to errors. In GN, such errors can occur when wrong identifiers are used during complicated joins in SQL. The aforementioned complexity arises when graph-like experimental data grows over time and it would therefore take some specialised knowledge, usually from a programmer or database administrator, to decipher some relations within such a database. Unpacking forced relational structures in a SQL database (MariaDB) into a natural graph-like database and format, such as RDF, will create a more semantic representation of GN data that allows easier ingestion by an AI system; and should the data evolve, also preserve it's semantic integrity despite ad-hoc node insertions.


### Aim 2: Demonstrate Reproducibility in a Data Science Research Project

In Africa, as in the rest of the world, reproducibility in research is challenging. Research work accepted by many journals publish *plausible* papers at the expense of repeatable work \autocite{bajpai2017challenges}. To support the culture of reproducible research here in Africa, this research aims at following a set of simple rules outlined by \citeauthor*{sandve2013ten} to ensure that it is repeatable.


### Aim 3: Creating Reliable Data Sharing Pipelines using linked data technology

Sharing data for ML/ AI purposes requires data access. However, sharing this data in a FAIR way is even more challenging. Stringent laws around data privacy in different countries make research even more difficult for an African researcher who requires access to that data. As an example, accessing GN data in it's entirety outside the US requires bureaucratic processes to work through. Similarly, here in Kenya, accessing health-care related data is restricted to our *[Kenya's]* borders. For the purpose of this proposed research work, this presents a golden opportunity: hosting our own GN instance here in Kenya with data that's stored in a more semantic way. Technologies like SPARQL enable an organisation to have federated queries \autocite{buil2013federating} where multiple database instances living in different spaces over the internet are treated as one instance, thereby effectively allowing easier sharing over data. Linked data allows exploration and evaluation by removing the tedious task of designing an integrative schema or working out ways to normalise and/ or warehouse a data subset in order to ask command *domain-spanning* questions.

Creating a reproducible semantic version of GN would provide a useful blueprint for creating the necessary infrastructure for sharing big data sets here in Kenya, particularly around pathogens, a concept that could be extended to other African countries.


## Supervisors

My supervisors for this project are: Prof. Shelby Solomon, Strathmore University Nairobi, who is an expert in data science, AI and ML; Prof Pjotr Prins, University of Tennessee USA, who is an expert on genetics, databases and data privacy; and Dr George Githinji, KEMRI/Wellcome Trust, Kenya, who is the bioinformatics and data science lead.


# Ethical Review

This research primarily involves QTL and omics database systems for major model organisms supplied by GN, and will grow to accommodate human models.
One point of ethical concern for working with a such a data set is privacy and regulations around the same, particularly with human data which is prone to misuse\autocite{gymrek2013identifying,wang2009learning,erlich2014routes}. *Is there a way to anonymize data in a way that you could still perform useful research on it?* There have been active research on this, and in fact, GN has demonstrated one such technique&#x2013; *homormophic encryption*&#x2013; in anonymizing genotype and phenotype data \autocite{hegp22,mott2020private}. Homomorphic encryption and other techniques such as differential privacy \autocite{dwork2008differential} will be explored. The most practical and feasible technique for data anonymisation will be applied so that we can guarantee that any human data used is safe.

For sensitive data, applying anonymization techniques does not necessarily make data easier to work with, nor more easily shareable. In this research, such data should be well annotated, and necessary metadata attached to it. RDF makes this plausible. By having a well annotated FAIR dataset:

-   Machines can easily "discover" and infer (*access)* the data they need;
-   Interoperability is guaranteed because a shared vocabulary can be shared in a machine accessible format;
-   The data becomes more re-usable across disciplines because the data will have contextual information that allows proper and correct interpretation; and
-   Data being in a graph-like structure allows the attachment of rich provenance information which allows for accurate citation.

With data stored in a more semantic way in RDF, this research hopes to show how easy and safe it "should" be to share complex data, and also how cheap it can be to integrate other data sources into a project. The hope is that it would demonstrate how practical RDF is, and how cheap sharing data that lies in different servers on different schemas can be. Achieving this would push Science forward by allowing researchers easy access to data. Linked data graph-databases are going to play an increasingly important role in the bio-medical sciences, next to tabular file formats, SQL databases and the more tree-like storage systems colloquially labeled "NoSQL databases".


# Timeline

This research is expected to run through the entirety of my Master's Program which ends in June 2023. I aim to finish this project by May 2023. The grant will help me support my studies so I can focus fully on this data science project.


# Budget

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left"><i>Item</i></th>
<th scope="col" class="org-left"><i>Budget</i></th>
<th scope="col" class="org-right"><i>Months</i></th>
<th scope="col" class="org-left"><i>Amount</i></th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Monthly Stipend (Msc Program)</td>
<td class="org-left">$ 416.67</td>
<td class="org-right">12</td>
<td class="org-left">$5000</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Total</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">$5000</td>
</tr>
</tbody>
</table>

\newpage

\printbibliography

