# DBpedia
DBpedia is a project aiming to extract structured content from the information in Wikipedia. DBpedia allows users to semantically query relationships and properties of Wikipedia resources, including links to other related datasets, using the SPARQL query language. DBpedia stores information in a RDF database.

# RDF
RDF ([Resource Description Framework]( https://en.wikipedia.org/wiki/Resource_Description_Framework)) databases are different than typical "spreadsheet" type databases as they are in the form of a graph rather than a table. This graph consists of nodes representing objects with directed edges representing relationships between them. The term _triple_ is used to describe any two nodes with an edge connecting them.

## Example RDF Graph with 9 triples
![](example_rdf_graph.png)
(source https://www.researchgate.net/figure/Example-RDF-graph-containing-9-triples-describing-the-city-of-Leipzig-and-its-mayor_fig2_221510762)

# SPARQL
SPARQL (pronounced "sparkle", short for SPARQL Protocol and RDF Query Language) is a query language used to retrieve and manipulate data stored in RDF format.

## Specifics
**URIs**    
 
<http://this.is.a/full/URI/written#out>  

**Literals**

*Plain literals*  
`"a plain literal"`

*Plain literal with language tag*  
`"bonjour"@fr`

*Typed literal*  
`"13"^^xsd:integer`

*Shortcuts*  
`true` -> `"true"^^xsd:boolean`  
`3` -> `"3"^^xsd:integer`  
`4.2` -> `"4.2"^^xsd:decimal`  

**Variables**

`?var1`  
`?anotherVar`  
`?and_one_more`  

**Comments**
```
# Comments start with a '#'  
# continue to the end of the line
```

**Triple patterns**  
Triple patterns match two nodes (objects) and the directed edge (relationship) between them ( node1 --> node2 )  
The format of a triple is:  
`[literal/variable for node1] [literal/variable for edge] [literal/variable for node2]`  
You can put a dot at the end of the line to seperate triples.  

**Examples**  

*Match an exact RDF triple*  
`ex:myWidget ex:partNumber "XY24Z1" .`

*Match one variable*  
`?person foaf:name "Lee Feigenbaum" .`

*Match multiple variables*  
`conf:SemTech2009 ?property ?value .`

## Query format
A SPARQL query comprises, in order, of:
* **Prefix declarations** for abbreviating URIs
* **Dataset definition** stating what RDF graph(s) are being queried
* A **result clause** identifying what information to return from the query
* The **query pattern** specifying what to query for in the underlying dataset
* **Query modifiers** slicing, ordering, and otherwise rearranging results

![](anatomy_of_a_query.png)
(source http://www.iro.umontreal.ca/~lapalme/ift6281/sparql-1_1-cheat-sheet.pdf)

# Example DBpedia queries
