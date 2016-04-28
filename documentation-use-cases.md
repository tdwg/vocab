# Use cases for machine-readable metadata as specified by the Documentation Specification #

Steve Baskauf - 2016-04-28

This document should be considered neither stable nor citable.

**Purpose:** Machine-readable metadata should facilitate the discovery of useful information by a semantic client, or a human interacting with the server via software designed to translate a human-friendly interface into SPARQL queries.  The purpose of this document is to specify goals (use cases) and the means to achieve them (generally in the form of a template for SPARQL queries).

**Data:**

The examples below use metadata about the Darwin Core standard in the form of RDF.  Those data, along with the RDF that defines Dublin Core (some terms from which are incorporated into Darwin Core) can be found in the GitHub repo at https://github.com/tdwg/vocab/tree/master/code-examples/darwin-core .  

In the metadata, I followed the convention that each release of Darwin Core on GitHub was a "version" with respect to the vocabularies. The exception is the current version, which has never actually been released in full.  In particular, the dwciri: namespace terms defined in the RDF Guide have never been described as RDF.  I have described them in https://github.com/tdwg/vocab/blob/master/code-examples/darwin-core/dwciri.ttl and added their versions to dwctermshistory.ttl .  

Those triples are currently (2016-04-28) loaded in the Vanderbilt Heard Library triplestore where they can be queried using the form at http://rdf.library.vanderbilt.edu/sparql?view or interactively via HTTP GET at
```
<http://rdf.library.vanderbilt.edu/sparql?query= + [encodedQuery]'>
```
where [encodedQuery] is a URL-encoded string containing the SPARQL query.


### Use cases ###

**1. Discover all of the components of a standard** One challenge with a complex standard is knowing exactly what documents and vocabularies comprise the standard.  In the test metadata dataset, only three of the Darwin Core documents have been describe as RDF (the text, XML, and RDF guides) - in reality there are many more.  Also, there currently is no official division of the vocabulary into "basic" and "RDF" forms, although this is implied by the [RDF Guide](http://rs.tdwg.org/dwc/terms/guides/rdf/), which defines some terms that make sense primarily in the context of RDF.  

**Query:**
```
SELECT DISTINCT ?name ?type ?definition WHERE {
  <http://www.tdwg.org/standards/450/> dcterms:hasPart ?part.
  ?part rdfs:label ?name.
  ?part a ?type.
  ?part dcterms:description ?definition.
  }
```

**2. Discover all versions of a resource**

**Query:**
In this example, the resource is the Darwin Core Basic Vocabulary.  
```
SELECT DISTINCT ?issued ?label WHERE {
  <http://rs.tdwg.org/dwc/basic>  dcterms:hasVersion ?version.
  ?version dcterms:issued ?issued.
  ?version rdfs:label ?label.
  }
ORDER BY desc(?issued)
```

**3. Examine the history of a currently recommended term to see how its definition has changed over time**

**Query:**
```
SELECT DISTINCT ?version ?issued ?dfn ?status WHERE {
  dwc:genus dcterms:hasVersion ?recommendedVersion.
  ?recommendedVersion dwcattributes:status "recommended".
  ?recommendedVersion dcterms:replaces* ?previousVersion.
  ?previousVersion dcterms:issued ?issued.
  ?previousVersion rdfs:comment ?dfn.
  ?previousVersion dwcattributes:status ?status.
  }
ORDER BY desc(?issued)
```
Note that ?previousVersion includes replaced versions that are not necessarily versions of the term itself, e.g. dwc:genus-2009-08-24 is an eventual replacement for <http://digir.net/schema/conceptual/darwin/2003/1.0/Genus-2003-06-13>, but <http://digir.net/schema/conceptual/darwin/2003/1.0/Genus-2003-06-13> is not a version of dwc:genus because of the difference in namespace and capitalization of the local name.

**4. Display all terms that were part of a Darwin Core vocabulary in a particular version of that vocabulary**

**Query:** This example finds all of the terms that were in the version of the basic Darwin Core vocabulary released on 2009-12-07.  Note that terms such as dwc:occurrenceDetails do not have ?termList values because they are deprecated and not part of any current term list.  
```
SELECT DISTINCT ?term ?termVersion ?termList WHERE {
  <http://rs.tdwg.org/dwc/basic> dcterms:hasVersion ?vocabVersion.
  ?vocabVersion dcterms:issued "2009-12-07"^^xsd:date.
  ?vocabVersion dcterms:hasPart ?listVersion.
  ?listVersion dcterms:hasPart ?termVersion.
  OPTIONAL
     {
     ?termVersion dcterms:isVersionOf ?term.
     OPTIONAL
       {
       ?term dcterms:isPartOf ?termList.
       }
    }
  }
ORDER BY ?termList
```
The Dublin Core terms show up only as term versions and not as terms.  That's the reason for the first OPTIONAL clause.  I'm not sure this is right, so we probably should discuss how to better model "borrowed" terms.  

Terms such as dwc:occurrenceDetails do not have ?termList values because they are deprecated and not part of any current term list. That's the reason for the second optional clause.  If dcterms:isPartOf were replaced with rdfs:isDefinedBy in the second OPTIONAL clause, those terms would have ?termList values.

**5. Find differences between vocabulary versions with respect to the terms present in those versions**

**Query:** This example shows terms that were in the 2009-12-07 version of the basic Darwin Core vocabulary that were NOT in the 2009-10-08 version of that vocabulary.  It can be modified to compare any versions issued on the following dates:

```
2015-03-27
2014-11-08
2013-10-23
2011-10-26
2009-12-07
2009-10-08
2009-09-23
2009-07-06
2009-05-25
2009-04-29
2009-02-20

```
by substituting them in the appropriate place in the query.
```
SELECT DISTINCT ?term ?termVersion  WHERE {
  # Version2 is the vocabulary version whose terms are shown that are not in Version1
  <http://rs.tdwg.org/dwc/basic> dcterms:hasVersion ?vocabVersion2.
  ?vocabVersion2 dcterms:issued "2009-12-07"^^xsd:date.
  ?vocabVersion2 dcterms:hasPart ?listVersion2.
  ?listVersion2 dcterms:hasPart ?termVersion.
  MINUS {
        <http://rs.tdwg.org/dwc/basic> dcterms:hasVersion ?vocabVersion1.
        ?vocabVersion1 dcterms:issued "2009-10-08"^^xsd:date.
        ?vocabVersion1 dcterms:hasPart ?listVersion1.
        ?listVersion1 dcterms:hasPart ?termVersion.
        }
  OPTIONAL
     {
     ?termVersion dcterms:isVersionOf ?term.
     }
  }
ORDER BY ?term
```

**6. Show the definitions and comments of terms that were replaced between two versions.**  It is not required that the versions be consecutive.

**Query:**
```
SELECT DISTINCT ?termVersion2 ?definition2 ?comment2 ?termVersion1 ?definition1 ?comment1 WHERE {
  <http://rs.tdwg.org/dwc/basic> dcterms:hasVersion ?vocabVersion2.
  ?vocabVersion2 dcterms:issued "2014-11-08"^^xsd:date.
  ?vocabVersion2 dcterms:hasPart ?listVersion2.
  ?listVersion2 dcterms:hasPart ?termVersion2.
  ?termVersion2 rdfs:comment ?definition2.
  OPTIONAL {?termVersion2 dcterms:description ?comment2.}

  <http://rs.tdwg.org/dwc/basic> dcterms:hasVersion ?vocabVersion1.
  ?vocabVersion1 dcterms:issued "2011-10-26"^^xsd:date.
  ?vocabVersion1 dcterms:hasPart ?listVersion1.
  ?listVersion1 dcterms:hasPart ?termVersion1.
  ?termVersion1 rdfs:comment ?definition1.
  OPTIONAL {?termVersion1 dcterms:description ?comment1.}

  ?termVersion2 dcterms:replaces+ ?termVersion1.
  }
ORDER BY ?termVersion2
```
