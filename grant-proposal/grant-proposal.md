


# Introduction

Genenetwork is a long-running bio-medical service
that has been in existence since 1994. It aims to
give researchers open-access FAIR data that they
can run analysis on vis-a-vis: the web; API
end-points; and live Jupyter notebooks inside
self-hosted GNU Guix
containers\autocite{theGuixEnvironment2022Gnu}. Underlying
this service, there is a mountain of data that has
been growing consistently, and with it new
challenges, in particular: espousing clear
relations between the data given a history of
ad-hoc storage; fast data retrieval; non-obvious
complex queries to do seemingly straight-forward
tasks; connecting with other open databases
(e.g. Uniprot) in a coherent way; and unclear
means of adding new data that does not align with
existing schemata. The aforementioned challenges
that Genenetwork faces present new opportunities
to the scientific community; and in particular,
African organisations that have faced similar
problems. Having more semantic data that's easily
accessible and shareable helps in pushing research
work forwards. It would be a good first to
answering questions such as: "There are 10,000's
of mice with computable genomes that have never
been born yet. Can we compute their phenotype
before hand using our dataset?"

**Research Hypothesis**: Moving graph-like biological
data from a SQL database into a graph-like
structure, RDF, will make it [the data] more
semantic, easier to share, and reduce developer
hours required during system integration with
other data systems.

**Expected Outcomes**:

-   Conversion of GeneNetwork SQL dump to RDF.
-   Exposure of GeneNetwork to SPARQL endpoints.
-   More performant and less complicated database queries with GeneNetwork.
-   More semantic data structure that makes inserts more easier.
-   Easy integration with external systems such as
    Uniprot.

The three specific aims of this research project are:


### Aim 1: Improve the quality of data for Artificial Intelligence (AI) and Machine Learning (ML) tasks

As things stand, it is difficult to run an AI/ ML
task against Genenetwork's database without
creating a data warehouse&#x2013; ideally, such a task
should be possible from the web interface. This
difficulty is because we have complicated
structures and relationships that have been forced
on a rigid and constrained 2D tabular structure
\footnote{Storing data in SQL is the current standard in biology}
that would need human intervention to decipher;
and tasks that require human intervention are
prone to errors. In Genenetwork, such errors can
occur when wrong identifiers are used during
complicated joins in SQL. The aforementioned
complexity arises when graph-like experimental
data grows over time and it would therefore take
some specialised knowledge, usually from a
programmer or database administrator, to decipher
some relations within such a database. Unpacking
forced relational structures in a SQL database
(MariaDB) into a natural graph-like database and
format, such as RDF, will create a more semantic
representation of Genenetwork data that allows
easier ingestion by an AI system; and should the
data evolve, also preserve it's semantic integrity
despite ad-hoc node insertions.

\clearpage


### Aim 2: Demonstrate Reproducibility in a Data Science Research Project

In Africa, as in the rest of the world, reproducibility in research is
challenging. Research work accepted by many journals publish *plausible*
papers at the expense of repeatable work
\autocite{bajpai2017challenges}. To build up on a culture of reproducible
research here in Africa, this research aims at following a set of
simple rules outlined by \citeauthor*{sandve2013ten} to ensure that it is
repeatable.


### Aim 3: Creating Reliable Data Sharing Pipelines using linked data technology

Sharing data for ML/ AI purposes requires data
access. However, sharing this data in a FAIR way
is even more challenging. Stringent laws around
data privacy in different countries make research
even more difficult for an African researcher who
requires access to that data. As an example,
accessing Genenetwork data in it's entirety
outside the US requires bureaucratic processes to
work through. Similarly, here in Kenya, accessing
health-care related data is restricted to our
*[Kenya's]* borders. For the purpose of this
proposed research work, this presents a golden
opportunity: hosting our own Genenetwork instance
here in Kenya with data that's stored in a more
semantic way. Technologies like SPARQL enable an
organisation to have federated queries
\autocite{buil2013federating} where multiple database
instances living in different spaces over the
internet are treated as one instance, thereby
effectively allowing easier sharing over
data. Linked data allows exploration and
evaluation by removing the tedious task of
designing an integrative schema or working out
ways to normalise and/ or warehouse a data subset
in order to ask command *domain-spanning* questions.

Creating a reproducible semantic version of
GeneNetwork would provide a useful blueprint for
creating the necessary infrastructure for sharing
big data sets here in Kenya, particularly around
pathogens, a concept that could be extended to
other African countries.


# Ethical Review

This research primarily involves QTL and omics
database systems for major model organisms
supplied by GeneNetwork, and will grow to
accommodate human models. Working with human data
is sensitive and is prone to misuse. Propers steps
will be taken to ensure that the genetic human
data will be de-anonimysed and pseudo-randomized.

With data stored in a more semantic way in RDF,
this research hopes to show how easy it "should"
be to share complex data, and also how cheap it
can be to integrate other data sources into a
project. The hope is that it would demonstrate how
practical RDF is, and how cheap sharing data that
lies in different servers on different schemas can
be. Achieving this would push Science forward by
allowing researchers easy access to data. Linked
data graph-databases are going to play an
increasingly important role in the bio-medical
sciences, next to tabular file formats, SQL
databases and the more tree-like storage systems
colloquially labeled "NoSQL databases".


# Timeline

This research is expected to run through the
entirety of my Master's Program which ends in
June 2023. I aim to finish this project by
May 2023.


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

