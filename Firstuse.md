# Triple store
I wanted to use Virtuoso as a Triplestore for my vehicle [ontology](https://w3id.org/vehicle/) and the first thing I 
learned was that Virtuoso needs a Graph to store your linked data at the moment you want to insert/load the data. 
In Fuseki you first create the Graph and then you can work within that Graph. In Virtuoso you have to work with the named Graph in the sparql query e.g. 
```
SELECT * FROM <http://example.com> WHERE {GRAPH ?g {?sub ?pre ?obj .} LIMIT 10
```    
You can enter a default Graph in a seperate field if you don't want to use Graph in your sparql. All in all it works a bit different as in Fuseki.  

# SPARQL end-point  
The SPARQL-endpoint is with the docker installation at http://127.0.0.1:8890/sparql (or localhost:8890/sparql but many clients don't understand/allow localhost).  
### errors  
First time use often gives autorization errors. You can find most of them on the internet, but the most common are:  
- Error: Virtuoso RDF02 Error SR619: SPARUL INSERT access denied
- Solution: ```DB.DBA.RDF_DEFAULT_USER_PERMS_SET ('nobody', 7);```

- Error: Executing an stored procedure e.g. DB.DBA.SPARQL_REXEC
- Solution: ```grant execute on DB.DBA.SPARQL_REXEC to "SPARQL";``` 
- Or: ```grant execute on DB.DBA.SPARQL_REXEC to "SPARQL_UPDATE";``` depending on which user gets the error.



