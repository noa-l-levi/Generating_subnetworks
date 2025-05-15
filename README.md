*****************************************************************

	Independent Decomposition of Chemical Reaction Networks

*****************************************************************

This code is used to partition the reactions of a chemcial reaction network (CRN) into independent
subnetworks and to generate new Catalyst-defined CRNs which can the be analysed independently. 

This code was adapted for Julia from the MATLAB function indepDecomp within the package 
COMPILES (see reference below)

Hernandez BS, Lubenia PVN, Johnston MD, Kim JK (2023) 
A framework for deriving analytic steady states of biochemical reaction networks. 
PLOS Computational Biology 19(4): e1011039. https://doi.org/10.1371/journal.pcbi.1011039

The function independent_decomposition requires the following Julia packages to be installed:
RowEchelon, Catalyst, Graphs, Combinatorics, MetaGraphs

INPUT : Julia file containing a Catalyst-defined reaction network (See Catalyst.jl for details on how to define your network).
The name of the file must be "-name-of-your-reaction-network.jl"
OUTPUT : The finest possible partition of the network reactions into independent subnetworks. 
*Note that reactions are numbered in the order they appear in the Catalyst reaction network.

The function generate_subnet_files requires the following Julia packages to be installed:
Catalyst, ModelingToolkit

INPUT : The name of the Julia file containing the CRN to be decomposed preceded by a :. 
Note that the file name and the reaction network defined within the file should be identical. 
For example, if the reaction network is called example_net, then the file name should be example_net.jl.
So to run this function, we would use generate_subnet_files(:example_net)
OUTPUT : The decomposition of the input CRN into independent subnetworks.
A file will also be generated to define each independent network.

We have included an example network - "Retina.jl", which is a reaction network for cellular cholesterol regulation in the retina. 
The Jupyter notebook demonstrates how we can decompose the Retina CRN and begin to analyse a subnetwork.
