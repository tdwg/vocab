# Use cases for machine-readable metadata as specified by the Documentation Specification #

This document should be considered neither stable nor citable.

**Purpose:** Machine-readable metadata should facilitated the discovery of useful information by a semantic client, or a human interacting with the server via software designed to translate a human-friendly interface into SPARQL queries.  The purpose of this document is to specify goals (use cases) and the means to achieve them (generally in the form of a template for SPARQL queries).

The examples below use metadata about the Darwin Core standard in the form of RDF.  Those data, along with the RDF that defines Dublin Core (some terms from which are incorporated into Darwin Core) can be found in the GitHub repo at https://github.com/tdwg/vocab/tree/master/code-examples/darwin-core .  Those triples are currently (2016-04-28) loaded in the Vanderbilt Heard Library triplestore where they can be queried using the form at http://rdf.library.vanderbilt.edu/sparql?view or interactively via HTTP at
```
<http://rdf.library.vanderbilt.edu/sparql?query= + [encodedQuery]'>
```
where [encodedQuery] is a URL-encoded string containing the SPARQL query.


### Use cases ###

**1. Discover all of the components of a standard** One challenge with a complex standard is knowing exactly what documents and vocabularies comprise the standard.  In the test metadata dataset, only three of the Darwin Core documents have been describe as RDF (the text, XML, and RDF guides) - in reality there are many more.  Also, there currently is no official division of the vocabulary into "basic" and "RDF" forms, although this is implied by the [RDF Guide](http://rs.tdwg.org/dwc/terms/guides/rdf/), which defines some terms that make sense primarily in the context of RDF.  

**Query**
```
SELECT DISTINCT ?name ?type ?definition WHERE {
  <http://www.tdwg.org/standards/450/> dcterms:hasPart ?part.
  ?part rdfs:label ?name.
  ?part a ?type.
  ?part dcterms:description ?definition.
  }
```

**2. Discover the versions of a resource** In this case, the resource is the Darwin Core Basic Vocabulary.  In the metadata, I followed the convention that each release on GitHub was a "version". The exception is the current version, which has never actually been released in full.  In particular, the dwciri: namespace terms defined in the RDF Guide have never been described as RDF.  I have described them in https://github.com/tdwg/vocab/blob/master/code-examples/darwin-core/dwciri.ttl and added their versions to dwctermshistory.ttl .  The 
