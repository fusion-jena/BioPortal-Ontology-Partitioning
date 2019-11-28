# BioPortal Ontology Partitioning
This repository is used to summarize and report the evaluation of partitionability of BioPortal ontologies. The preliminary results of this study is published in 12th International Conference on Semantic Web Applications and Tools for Health Care and Life (SWAT4LSHC) (http://www.swat4ls.org/)
The pipeline used for the study contains the following steps:
 * get all accessible ontologies using the BioPortal API [http://data.bioontology.org/documentation],
 * transform these ontologies into OWL or OBO formats using OWL API [http://owlcs.github.io/owlapi/],
 * partition these ontologies using one of the following partitioning algorithms, and 
 * analyse the partitioning results
 
The used partitioning tools:
1. PATO is an ontology partitioning tool making use of the following steps to partition an ontology: i) dependency graph creation: a graph structure is created to represent dependencies between ontology entities, where nodes of the graph are the values of "rdf:label" or "rdf:ID". ii) graph partitioning: a set of nodes of given minimal and maximal size for which the strength of the connection between the nodes inside the set is higher than the strength of any connection to nodes outside the set is used to determine sets of ontology elements
that should be in one module, and iii) a distributed ontology is created based on the graph partitioning

2. The ontology analysis and partitioning tool (OAPT)  aims to partition ontologies into a set of modules based on exploiting the seeding-based clustering algorithm. The algorithm has the following steps: i) ranking the ontology concepts: A first step is to quantify the importance of each concept within the concept graph (ontology) to select which concepts could be used later as important concepts. Some of these important concepts are then elected to be cluster heads, the seed of the partition. ii) determine cluster heads: the next step is to select which concepts represent cluster heads. In this context, we have to deal with two arising questions: how many cluster heads should we select? and which cluster heads? iii) partitioning: the seed-based algorithm initiates one partition for each cluster head. Then, it places direct children in the corresponding partition and finally, for the remaining (non-partitioned) concepts, a membership function to assign remaining nodes to their fitting partition is developed. and v) generate module: the following step is to generate a module for each partition preserving the required intra-relationships between concepts in the same partition as well as inter-links between concepts from different partitions.

3. The atomic decomposition (AD) is a compact representation of modular structure of the ontology. AD of an ontology O is a pair consisting of a set of atoms and a directed dependency relation over these atoms, where an atom is a maximal set of axioms which are tightly bound to each other. For computing Atomic Decompositions we used the off-the-shelf implementation provided by Del Vescovo and Palmisano. The implementation is available via Maven Central (maven.org) with an artifactId of owlapitools-atomicdecomposition.
The current implementation of the AD approach supports extracting three types of syntactic-locality-based modules: the bottom module, the top module, and the star module

Acknowledgments: This work has been mostly funded by the Deutsche Forschungsgemeinschaft (DFG) as part of the CRC 1076 AquaDiva [http://www.aquadiva.uni-jena.de/]
