<param ve-config
       title="Network examples"
       banner="https://upload.wikimedia.org/wikipedia/commons/c/c8/Netwerkje.jpg"
       layout="vertical"
       author="JSTOR Labs team">

# D3.js Networks
D3.js is a JavaScript library for producing dynamic, interactive data visualizations in web browsers. Documentation is available at [https://d3js.org/](https://d3js.org/).

# Basic Force Directed Graph network
This is a basic network graphed using the D3.js library. The `ve-d3-network` tag is used to generate this diagram and it takes a `url` attribute for the input data file. The example shown here uses a TSV file that can be viewed here [https://jstor-labs.github.io/ve-components/public/data/medici.tsv](https://jstor-labs.github.io/ve-components/public/data/medici.tsv).
<param ve-d3-network url="https://jstor-labs.github.io/ve-components/public/data/medici.tsv">

# D3Plus Networks

D3plus is a JavaScript re-usable chart library that extends the popular D3.js to enable the easy creation of beautiful visualizations.  Example diagrams can be seen at [https://d3plus.org/examples/](https://d3plus.org/examples/).  Documentation is available at [https://d3plus.org/docs/](https://d3plus.org/docs/).

## Simple network

This is an example of basic network diagram using the D3Plus library.  The data used in this diagram is defined in a TSV (tab separated values) file that can be seen at [https://github.com/JSTOR-Labs/plant-humanities/blob/master/graphs/medici.tsv](https://github.com/JSTOR-Labs/plant-humanities/blob/master/graphs/medici.tsv).  The `ve-d3plus-network` tag is used to generate this diagram and takes a `url` attribute for the input data file.
<param ve-d3plus-network url="https://jstor-labs.github.io/ve-components/public/data/medici.tsv">

## Ring network

Rings are a way to view network connections focused on 1 node in the network.  this visualization shows primary and secondary connections of a specific node, and allows the user to click on a node to recenter the visualization on that selected node.  This example uses the same TSV input file used in the simple network example above.  This diagram is defined with the `ve-d3plus-ring-network` tag and identifies the data file with a `url` attribute.  It also uses a `center` attribute to identify the name of the networks central node.
<param ve-d3plus-ring-network 
       url="https://jstor-labs.github.io/ve-components/public/data/medici.tsv"
       center="Anna Maria Luisa de' Medici">


# Vis.js Networks

Vis.js is a dynamic, browser based visualization JavaScript library. The library is designed to be easy to use, to handle large amounts of dynamic data, and to enable manipulation of and interaction with the data. Examples of network graphs created in Vis.js can be seen at [https://visjs.github.io/vis-network/examples/](https://visjs.github.io/vis-network/examples/). The documentation for networks can be viewed at [https://visjs.github.io/vis-network/docs/network/](https://visjs.github.io/vis-network/docs/network/).

## Simple network

The `ve-vis-network` tag is used to generate this graph and identifies the data file with a `file` attribute. An optional `title` attribute can be defined to give the network graph a title. 
<param ve-vis-network title="Heliconia imbricata and hummingbird mutualistic interactions" file="https://jstor-labs.github.io/plant-humanities/graphs/heliconia-v3.tsv">
