# BioPortal Ontology Partitioning
This repository is used to summarize and report the evaluation of partitionability of BioPortal ontologies. The preliminary results of this study is published in 12th International Conference on Semantic Web Applications and Tools for Health Care and Life [SWAT4LSHC] (http://www.swat4ls.org/)
The pipeline used for the study contains the following steps:
 * get all accessible ontologies using the BioPortal API [http://data.bioontology.org/documentation],
 * transform these ontologies into OWL or OBO formats using OWL API [http://owlcs.github.io/owlapi/],
 * partition these ontologies using one of the following partitioning algorithms, and 
 * analyse the partitioning results
The used partitioning tools:
1. PATO is an ontology partitioning tool making use of the following steps to partition an ontology: i) dependency graph creation: a graph structure is created to represent dependencies between ontology entities, where nodes of the graph are the values of "rdf:label" or "rdf:ID". ii) graph partitioning: a set of nodes of given minimal and maximal size for which the strength of the connection between the nodes inside the set is higher than the strength of any connection to nodes outside the set is used to determine sets of ontology elements
that should be in one module, and iii) a distributed ontology is created based on the graph partitioning

