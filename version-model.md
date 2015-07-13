#TDWG Version Model
Preliminary Draft 2015-07-08 - Steve Baskauf - TDWG Vocabulary Management Task Group

Note: This document has no official standing. It is subject to change at any time and should not be considered to be stable nor citable.

##Definitions
**Current resource** - a resource in its current state. A current resource is identified by the permanent IRI of the resource.


*Example:* 

`dwc:recordedBy` (`http://rs.tdwg.org/dwc/terms/recordedBy`)


**Versioned resource** - a version of a resource at some particular time.  The latest version of a resource will have the same properties as its corresponding current resource except for properties that relate it to the current resource and other related versioned resources.  The normal convention is to append the value of **dcterms:issued** (in form of the **xsd:date** datatype) to the local name of the IRI, although there may be circumstances where this is not possible nor desirable. Clients should not parse the IRI to discover the date of issue; rather they should retrieve the value of dcterms:issued.

*Example:* 
```turtle
dwc:recordedBy-2014-10-23 (http://rs.tdwg.org/dwc/terms/recordedBy-2014-10-23)
```

##Status of current terms and versioned terms

Current terms are either in use or deprecated. A deprecated current term has an owl:deprecated property with a boolean value of "true". For example:
```turtle
dwc:individualID owl:deprecated "true"^^xsd:boolean.
```
Any current term without an owl:deprecated property can be assumed to be in use.  Current terms never "go away" - they should persist so that a client dereferencing an obsolete term IRI can "follow its nose" and discover that use of the term should be discontinued.

Versioned terms are either recommended or superseded.  A recommended version of a term has a dwcattributes:staus value of "recommended", while a superseded version of a term has a dwcattributes:staus value of "superseded".  For example:
```turtle
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23> dwcattributes:staus "recommended"^^xsd:string.
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24> dwcattributes:staus "superseded"^^xsd:string.
```
Versioned terms are not deprecated, since they are a historical record of the state of a current term at some particular time.  A current term that is in use should have only one version that is recommended and one-to-many versions that are superseded.  A current term that is deprecated should have no versions that are recommended and one-to-many versions that are superseded.

A versioned term may replace or be replaced by another versioned term. A current term that is in use may replace a deprecated current term, in which case the deprecated current term will be replaced by the current term that is in use.  However, a deprecated current term will not necessarily be replaced by any current term. 

*Examples:*
*A current term in use that replaces deprecated current terms.*
```turtle
dwc:recordedBy dcterms:replaces <http://rs.tdwg.org/dwc/dwcore/Collector>.
dwc:recordedBy dcterms:replaces <http://digir.net/schema/conceptual/darwin/2003/1.0/Collector>
```

*Statuses of versioned terms.*
Note that only one version of recordedBy is recommended and that no versions of Collector are recommended since the current term Collector is deprecated.
```turtle
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23> dwcattributes:status "recommended"^^xsd:string.
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24> dwcattributes:status "superseded"^^xsd:string.
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2008-11-19> dwcattributes:status "superseded"^^xsd:string.
<http://rs.tdwg.org/dwc/terms/history/#Collector-2007-04-17> dwcattributes:status "superseded"^^xsd:string.

```

*Versioned terms that replace or are replaced by other versions.*
```turtle
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23> dcterms:replaces <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24>;
                                                              dcterms:isVersionOf dwc:recordedBy.
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24> dcterms:replaces <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2008-11-19>;
                                                              dcterms:isVersionOf dwc:recordedBy.
<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2008-11-19> dcterms:replaces <http://rs.tdwg.org/dwc/terms/history/#Collector-2007-04-17>;
                                                              dcterms:isVersionOf dwc:recordedBy.
<http://rs.tdwg.org/dwc/terms/history/#Collector-2007-04-17> dcterms:isVersionOf <http://rs.tdwg.org/dwc/dwcore/Collector>.
```


##Property relationships
A current resource is linked to a versioned resource by the property **dcterms:hasVersion**.  A versioned resource is linked to its current resource by the property **dcterms:isVersionOf**.  Note: DCMI does not explicitly declare that `dcterms:hasVersion owl:inverseOf dcterms:isVersionOf`.  So unless this is declared and reasoning is performed, both of these relationships between current and versioned resources will exist only if both kinds of triples are explicitly declared.

*Examples:*

```turtle
dwc:recordedBy dcterms:hasVersion dwc:recordedBy-2014-10-23.
dwc:recordedBy-2014-10-23 dcterms:isVersionOf dwc:recordedBy.
```

----------

A versioned resource is related to a previous version by the property **dcterms:replaces**.  A versioned resource is related to a subsequent version by the property **dcterms:isReplacedBy**. Note: DCMI does not explicitly declare that `dcterms:replaces owl:inverseOf dcterms:isReplacedBy` with the same implications as above.   

*Examples:*

```turtle
dwc:recordedBy-2014-10-23 dcterms:replaces dwc:recordedBy-2009-04-24.
dwc:recordedBy-2009-04-24 dcterms:isReplacedBy dwc:recordedBy-2014-10-23.
```

----------

A versioned resource is linked to another related versioned resource by the same property that links its corresponding current resource to the corresponding related current resource.

*Example:*

If 
```turtle
dwc:recordedBy rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/>.
```

then 
```turtle
dwc:recordedBy-2014-10-23 rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms-2014-10-23>.
```

A versioned resource may have multiple values if it is related to several versioned related resources.  

*Example:*

```turtle
dwc:recordedBy-2014-10-23 rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms-2014-10-23>;
     rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms-2015-03-19>.
```

----------
The publication date for a versioned resource is designated by the property **dcterms:issued**.  The modified date of a current resource is designated by the property **dcterms:modified**; its value will be the same as the **dcterms:issued** property of its most recent  corresponding versioned resource.  

*Example:*

```turtle
dwc:recordedBy dcterms:modified "2014-10-23"^^xsd:date;
     dcterms:hasVersion dwc:recordedBy-2014-10-23, dwc:recordedBy-2009-04-24.
dwc:recordedBy-2014-10-23 dcterms:issued "2014-10-23"^^xsd:date;
     dcterms:replaces dwc:recordedBy-2009-04-24.
dwc:recordedBy-2009-04-24 dcterms:issued "2009-04-24"^^xsd:date.
```
## Competency questions
The following SPARQL queries show how this model enables reconstruction of the state of a current resource at particular times in the past.

----------


Display the definitions of all versions of the term **dwc:recordedBy** and the date that each definition was adopted.

```sparql
SELECT ?date ?definition WHERE {
  dwc:recordedBy dcterms:hasVersion ?version.
  ?version dcterms:issued ?date.
  ?version rdfs:comment ?definition.
}
```

----------
List all properties that were in the 2014-10-23 release of the Darwin Core recommended dwc: terms list.

```sparql
SELECT ?property WHERE {
  <http://rs.tdwg.org/dwc/terms/> dcterms:hasVersion ?listVersion.
  ?listVersion dcterms:issued "2014-10-23"^^xsd:date.
  ?termVersion rdfs:isDefinedBy ?listVersion.
  ?property dcterms:hasVersion ?termVersion.
  ?property a rdfs:Property.
}
```

----------

Construct a graph that contains properties of all terms that were in the 2014-10-23 release of the Darwin Core recommended dwc: terms list.  

```sparql
CONSTRUCT {
  ?term rdfs:label ?labelObject.
  ?term rdfs:comment ?commentObject.
  ?term dcterms:description ?descriptionObject.
  ?term rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/>.
  ?term dcterms:modified ?modifiedObject.
  ?term a ?typeObject.
  ... [continue with remaining properties]
}
WHERE {
  <http://rs.tdwg.org/dwc/terms/> dcterms:hasVersion ?listVersion.
  ?listVersion dcterms:issued "2014-10-23"^^xsd:date.
  ?termVersion rdfs:isDefinedBy ?listVersion.
  ?termVersion rdfs:label ?labelObject.
  ?termVersion rdfs:comment ?commentObject.
  ?termVersion dcterms:description ?descriptionObject.
  ?termVersion dcterms:issued ?modifiedObject.
  ?termVersion a ?typeObject.
  ... [continue with additional properties]
  ?term dcterms:hasVersion ?termVersion.
}
```
Note: this query will fail for terms that are missing any of the specified properties.  For example, **dwc:accordingTo** does not have a **dcterms:description** property and would be missed.  One could replace the given **dcterms:description** triple pattern with 
```sparql
    OPTIONAL { ?termVersion dcterms:description ?descriptionObject. }
```
to catch this case.  

The point is that this system would allow a semantic client to reconstruct the state of a current resource (such as the Darwin Core term list) at any point in time by extracting saved data about its corresponding versioned resource at that time.