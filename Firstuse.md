# Triple store
I wanted to use Virtuoso as a Triplestore for my vehicle [ontology](https://w3id.org/vehicle/) and the first thing I 
learned was that Virtuoso needs a Graph to store your linked data at the moment you want to insert/load the data. 
In Fuseki you first create the Graph and then you can work within that Graph. In Virtuoso you have to work with the named Graphin the sparql query. 
You can enter a default Graph in a seperate field if you don't want to use Graph in yur sparql. All in all it works a bit different as in Fuseki.


