## This material will remain a part of the Darwin Core Namespace Policy, with minor edits. The parts of the existing Namespace Policy page that are not present here have been incorporated into the Vocabulary Maintenance Specification


1\. Introduction

Audience: This document is targeted toward those who want to make changes to the Darwin Core, either by refining terms that already exist or by adding new terms to increase the capabilities of the standard.
This document and the policies contained herein are modeled on the Dublin Core Metadata Initiative Namespace Policy [DCMINAMESPACEPOLICY]. All terms in the Darwin Core must be identified with a unique Uniform Resource Identifier (URI). For convenience, the term URIs are grouped into collections known as Darwin Core namespaces. This document describes the policies associated with Darwin Core namespaces and how term URIs are allocated by the Darwin Core Task Group [DWC-TASK].

2\. Namespace URIs

The Darwin Core namespace URI for the collection of all Darwin Core properties, classes, and encoding schemes is:

http://rs.tdwg.org/dwc/terms/
The term identifier for the current (recommended) version of a term is a URI based on the namespace and the term name without version information. Some example Darwin Core term identifiers follow:

http://rs.tdwg.org/dwc/terms/scientificName
is the Darwin Core term identifier for the scientificName property, while

http://rs.tdwg.org/dwc/terms/MachineObservation
is the Darwin Core term identifier for the MachineObservation class.

All Darwin Core identifiers will dereference to a Darwin Core term declaration for the identified term.

3\. Persistence Policy

TDWG recognizes that people and applications depend on the persistence of formal documents and machine processable schemas that have been made publicly available. In particular, the stability of Darwin Core term URIs and Darwin Core namespace URIs is critical to interoperability over time. Thus, the wide promulgation of this set of URIs dictates that they be maintained to support legacy applications that have adopted them.
