<param ve-config
       title="Network examples"
       banner="https://upload.wikimedia.org/wikipedia/commons/c/c8/Netwerkje.jpg"
       layout="vertical"
       author="JSTOR Labs team">

# D3Plus Networks

D3plus is a JavaScript re-usable chart library that extends the popular D3.js to enable the easy creation of beautiful visualizations.  Example diagrams can be seen at [https://d3plus.org/examples/](https://d3plus.org/examples/).  Documentation is available at [https://d3plus.org/docs/](https://d3plus.org/docs/).

## Simple network

This is an example of basic network diagram using the D3Plus library.  The data used used in this diagram is defined in a TSV (tab separated values) file that can be seen [here](https://jstor-labs.github.io/ve-components/public/data/medici.tsv).
<param ve-d3plus-network url="https://jstor-labs.github.io/ve-components/public/data/medici.tsv">

## Ring network

Rings are a way to view network connections focused on 1 node in the network.  this visualization shows primary and secondary connections of a specific node, and allows the user to click on a node to recenter the visualization on that selected node.  This example uses the same TSV input file used in the simple network example above.
<param ve-d3plus-ring-network 
       url="https://jstor-labs.github.io/ve-components/public/data/medici.tsv"
       center="Anna Maria Luisa de' Medici">