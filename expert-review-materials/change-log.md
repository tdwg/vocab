# Documentation Specification change list (minor changes and typo corrections not listed):

1. Added paragraph to section 4.2:

"In accordance with the distinction made in the Dublin Core FAQ on DC and DCTERMS Namespaces [NAMESPACES] and following the precedent of Sections 1.4 and 3.3 of the Darwin Core RDF Guide [DWC-RDF], when a Dublin Core term has analogs in both the dc: (http://purl.org/dc/elements/1.1/) and dcterms: (http://purl.org/dc/terms/) namespaces, the dc: analog should be used with literal values (i.e. name strings), while the dcterms: analog should be used with an IRI or blank node denoting the object resource.  When an IRI is available to denote an object resource, it is desirable include the dcterms: analog in the metadata describing a resource."

Added [NAMESPACES] and [DWC-RDF] references at the end.

2. Assumed broadening the scope of the existing http://rs.tdwg.org/dwc/dwcattributes/ namespace to serve as a TDWG-wide utility namespace.  In recognition of that, changed the CURIE (namespace) abbreviation from "dwcattributes:" to "tdwgutility:".  

Changed example 4.4.1.1, which uses the definition of http://rs.tdwg.org/dwc/dwcattributes/ as part of the example.  Changed the human-readable definition from "Attributes defined by Darwin Core" to "Utility terms defined by Biodiversity Information Standards (TDWG)". [Note: there are a number of deficiencies of the current RDF defining http://rs.tdwg.org/dwc/dwcattributes/ that should be fixed in concert with the adoption of these standards.]

3. Minted the terms tdwgutility:Vocabulary and tdwgutility:TermList to denote vocabularies and term lists respectively.  Replaced references of dcmitype:Dataset with tdwgutility:Vocabulary, and references of dcat:Dataset with tdwgutility:TermList.

4. Removed references to the DCAT standard and to "datasets".  Changed the definition of "distribution" and rewrote section 4.4.3 and the example in 4.4.3.1 to reflect the discussion on the RDF Task Group mailing list.  **TODO: I am uncertain about whether the SPARQL endpoint part of the example is right.  I could just leave it out.**

5. Revised part of section 4.4.2 (about preferred namespaces) based on Reviewer 1 and Review Manager suggestions.  

# Vocabulary Maintenance Specification change list

1. Added definition of "issue tracker".

2. Added two figures illustrating described processes.

3. I noticed that in Section 4.2.4, the heading refers to user feedback reports, but the text mentioned only the implementation report.  I modified the text to refer to both kinds of reports.  This change was NOT made in response to reviewer comments.
