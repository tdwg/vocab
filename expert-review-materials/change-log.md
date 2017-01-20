# Documentation Specification change list (minor changes and typo corrections not listed):

1. Added paragraph to section 4.2:

"In accordance with the distinction made in the Dublin Core FAQ on DC and DCTERMS Namespaces [NAMESPACES] and following the precedent of Sections 1.4 and 3.3 of the Darwin Core RDF Guide [DWC-RDF], when a Dublin Core term has analogs in both the dc: (http://purl.org/dc/elements/1.1/) and dcterms: (http://purl.org/dc/terms/) namespaces, the dc: analog should be used with literal values (i.e. name strings), while the dcterms: analog should be used with an IRI or blank node denoting the object resource.  When an IRI is available to denote an object resource, it is desirable include the dcterms: analog in the metadata describing a resource."

Added [NAMESPACES] and [DWC-RDF] references at the end.

2. Assumed broadening the scope of the existing http://rs.tdwg.org/dwc/dwcattributes/ namespace to serve as a TDWG-wide utility namespace.  In recognition of that, changed the CURIE (namespace) abbreviation from "dwcattributes:" to "tdwgutility:".  

Changed example 4.4.1.1, which uses the definition of http://rs.tdwg.org/dwc/dwcattributes/ as part of the example.  Changed the human-readable definition from "Attributes defined by Darwin Core" to "Utility terms defined by Biodiversity Information Standards (TDWG)". [Note: there are a number of deficiencies of the current RDF defining http://rs.tdwg.org/dwc/dwcattributes/ that should be fixed in concert with the adoption of these standards.]

3. Minted the terms tdwgutility:Vocabulary and tdwgutility:TermList to denote vocabularies and term lists respectively.  Replaced references of dcmitype:Dataset with tdwgutility:Vocabulary, and references of dcat:Dataset with tdwgutility:TermList.

4. Removed references to the DCAT standard and to "datasets".  Changed the definition of "distribution" and rewrote section 4.4.3 and the example in 4.4.3.1 to reflect the discussion on the RDF Task Group mailing list.  **TODO: I am uncertain about whether the SPARQL endpoint part of the example is right.  I could just leave it out.**

5. Revised part of section 4.4.2 (about preferred namespaces) based on Reviewer 1 and Review Manager suggestions.  

6. Simplified the example in Section 4.5.1 and moved the full example to the Appendix Section 6.1.  Simplified the example in Section 4.5.4.1 and moved the full example to Appendix Section 6.2.

7. Added the following to Section 3.1:

"The landing page of a vocabulary standard MUST include information identifying its maintaining Interest Group and SHOULD contain a link to information explaining how changes to the vocabulary can be introduced. See Section 2.1 of the TDWG Vocabulary Maintenance Specification [MAINTENANCE] for more information about the role of Maintenance Interest Groups."

# Vocabulary Maintenance Specification change list

1. Added definition of "issue tracker".

2. Added two figures illustrating described processes.

3. I noticed that in Section 4.2.4, the heading refers to user feedback reports, but the text mentioned only the implementation report.  I modified the text to refer to both kinds of reports.  This change was NOT made in response to reviewer comments.

4. Added definitions of "interest group" and "task group" as recommended by the Review Manager.

5. Revised section 2.1 to say the following:

"At the time of the adoption of a vocabulary standard, an Interest Group charged specifically with the maintenance of that standard will be designated.  In the case of a major vocabulary that is likely to be subject to frequent changes, an Interest Group may be chartered specifically to maintain that vocabulary.  In the case where a new vocabulary is related to an existing vocabulary having an existing maintaining Interest Group, maintenance of the new vocabulary may be assigned to the existing Interest Group.  Several minor vocabularies may be maintained as a group by a single Maintenance Interest Group.  The decision of maintenance responsibility for each vocabulary standard rests with the Executive Committee.

The maintaining Interest Group will be subject to the normal expectations described for Interest Groups in the TDWG Standards Development Process document [PROCESS].  If a TDWG vocabulary continues to be actively developed, a vocabulary maintenance Interest Group will not normally be disbanded.  Therefore, if the Interest Group's convener is unable to continue in that role, that convener should be succeeded by a core member of the Interest Group.  If there are no core members of the Interest Group that are able take on the role of convener, the Executive Committee will appoint a convener who will reorganize the Interest Group.  

If a TDWG vocabulary achieves a level of stability that makes its maintenance unnecessary, or if the status of the standard defining the vocabulary is changed to Retired Standard [STATUS], the Executive Committee may choose to disband the maintaining Interest Group.  If necessary, the Executive Committee may reorganize the maintenance of existing vocabularies among Interest Groups in order to continue effective maintenance of those vocabularies.  In any case, it should be made clear on the landing page of each vocabulary standard which Interest Group is responsible for the maintenance of that standard.  See Section 3.1 of the TDWG Standards Documentation Specification [DOC-SPEC] for more information about standards landing pages."
