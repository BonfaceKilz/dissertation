# Introduction

Genenetwork is a long-running bio-medical service that has been in existence since 1994. It aims to give researchers open-access FAIR data that they can run analysis on vis-a-vis: the web; API end-points; and live Jupyter notebooks inside self-hosted GNU Guix containers \autocite{theGuixEnvironment2022Gnu}. Underlying this service, there is a mountain of data that has been growing consistently, and with it new challenges, in particular: espousing clear relations between the data given a history of ad-hoc storage; fast data retrieval; non-obvious complex queries to do seemingly straight-forward tasks; and unclear means of adding new data that does not align with existing schemata. The aforementioned challenges that Genenetwork faces present new opportunities to the scientific community; and in particular, African organisations that have faced similar problems. Having more semantic data that's easily accessible is a first step in easing the work of answering questions such as: "There are 10,000's of mice with computable genomes that have never been born yet. Can we compute their phenotype?"

The three specific aims of this research project are:


### Aim 1: Improve the quality of data for Artificial Intelligence (AI) and Machine Learning (ML) tasks

As things stand, it is difficult to run an AI/ ML task against Genenetwork's database without creating a data warehouse&#x2013; ideally, such a task should be possible from the web interface. This difficulty is because we have complicated structures and relationships that would need human intervention to decipher. Such complexity arises when graph-like experimental data grows over time. It would take some specialised knowledge, usually from the programmer or database administrator, to decipher some relations within the database. As an example: a term such as "Phenotype" has different semantic meanings in the database depending on the context; one as a dataset (a grouping of traits); and the other as [raw] data. Unpacking forced relational structures in a database (MariaDB) into a natural graph-like database and format, such as RDF, will create a more semantic representation of Genenetwork data that allows easier ingestion by an AI system; and should the data evolve, it's semantic integrity, even with ad-hoc node insertions, will be preserved.


### Aim 2: Demonstrate Reproducibility in a Data Science Research Project

In Africa, as in the rest of the world, reproducibility in research is challenging. Research work accepted by many journals publish *plausible* papers at the expense of repeatable work \autocite{bajpai2017challenges}. To build up on a culture of reproducible research here in Africa, this research aims at following a set of simple rules outlined by \citeauthor*{sandve2013ten} to ensure that it is repeatable.


### Aim 3: Creating Reliable Data Sharing Pipelines using Genenetwork

Sharing data for ML/ AI purposes requires data access. However, sharing this data in a FAIR way is even more challenging. Stringent laws around data privacy in different countries make research even more difficult for an African researcher who requires access to that data. As an example, accessing Genenetwork data in it's entirety outside the US requires bureaucratic processes to work through. Similarly, here in Kenya, accessing health-care related data is restricted to our *[Kenya's]* borders. For the purpose of this proposed research work, this presents a golden opportunity: hosting our own Genenetwork instance here in Kenya with data that's stored in a more semantic way. This would provide a useful blueprint for creating the necessary infrastructure for sharing big data sets here in Kenya, particularly around pathogens, a concept that could be extended to other African countries.


# Research Strategy

TODO: Ethical Review, Timeline, Budget, Dev Environment


# Project Management

TODO

\newpage

\printbibliography