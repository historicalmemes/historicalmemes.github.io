# DBpedia
DBpedia is a project aiming to extract structured content from the information in Wikipedia. DBpedia allows users to semantically query relationships and properties of Wikipedia resources, including links to other related datasets, using the SPARQL query language.

# SPARQL
SPARQL (pronounced "sparkle", short for SPARQL Protocol and RDF Query Language) is a query language used to retrieve and manipulate data stored in RDF ([Resource Description Framework]( https://en.wikipedia.org/wiki/Resource_Description_Framework)) format.

A SPARQL query comprises, in order, of:
* **Prefix declarations** for abbreviating URIs
* **Dataset definition** stating what RDF graph(s) are being queried
* A **result clause** identifying what information to return from the query
* The **query pattern** specifying what to query for in the underlying dataset
* **Query modifiers** slicing, ordering, and otherwise rearranging results

```
# prefix declarations
PREFIX foo: <http://example.com/resources/>
...
# dataset definition
FROM ...
# result clause
SELECT ...
# query pattern
WHERE {
    ...
}
# query modifiers
ORDER BY ...
```

## Example query on the graph http://www.w3.org/People/Berners-Lee/card
This information is in the FOAF format which is a way to describe machine readable ontologies (relationships between things) using RDF.

```
PREFIX foaf:  <http://xmlns.com/foaf/0.1/>
SELECT ?name
WHERE {
    ?person foaf:name ?name .
}
```

* SPAQRL **variables** start with an ? and can match and node (resource or literal) in the RDF dataset.
* **Triple patterns** are just like triples, except that any of the parts of a triple can be replace with a variable.
* The **SELECT** result clause returns a table of variables and values that satisfy the query.

### Results
&nbsp;&nbsp;&nbsp;name  
"mc schraefel"  
"John Klensin"  
"Libby Miller"  
"Henrik Nielsen"  
"John Markoff"  
"Edd Dumbill"  
"Nicholas Gibbins"  
"Daniel Krech"  
"Coralie Mercier"  
"Norman Walsh"  
"Les Carr"  
"Shinnyih Huang"  
"Philippe Le Hégaret"  
"Oshani Seneviratne"  
"Joe Lambda"  
…
