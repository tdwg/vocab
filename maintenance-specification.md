1. Introduction

Audience: This document is targeted toward those who want to make changes to the Darwin Core, either by refining terms that already exist or by adding new terms to increase the capabilities of the standard.
This document and the policies contained herein are modeled on the Dublin Core Metadata Initiative Namespace Policy [DCMINAMESPACEPOLICY]. All terms in the Darwin Core must be identified with a unique Uniform Resource Identifier (URI). For convenience, the term URIs are grouped into collections known as Darwin Core namespaces. This document describes the policies associated with Darwin Core namespaces and how term URIs are allocated by the Darwin Core Task Group [DWC-TASK].

2. Namespace URIs

The Darwin Core namespace URI for the collection of all Darwin Core properties, classes, and encoding schemes is:

http://rs.tdwg.org/dwc/terms/
The term identifier for the current (recommended) version of a term is a URI based on the namespace and the term name without version information. Some example Darwin Core term identifiers follow:

http://rs.tdwg.org/dwc/terms/scientificName
is the Darwin Core term identifier for the scientificName property, while

http://rs.tdwg.org/dwc/terms/MachineObservation
is the Darwin Core term identifier for the MachineObservation class.

All Darwin Core identifiers will dereference to a Darwin Core term declaration for the identified term.

3. Term Change Policy

Changes to Darwin Core recommendations or term declarations will occur from time to time for a variety of reasons. Changes have varying implications for the decision making process and for versioning Darwin Core documents and term URIs. The types of changes and appropriate processes are identified and explained in the following sections.

Reporting issues: In all cases the proposed change should be reported to the Technical Architecture Group [TDWG-TAG] and the outcome of the proposal should be announced on the Darwin Core mailing list [TDWG-CONTENT].

Decisions: In cases where an Executive decision is required,the Technical Architecture Group will conduct a minimum 30-day public comment period on the Darwin Core mailing list [TDWG-CONTENT], during which the proposal can be refined based on discussion in an effort to reach consensus (no dissenting opinion expressed publicly on the mailing list for 30 days from the most recent iteration). If a consensus is reached, the proposal will be presented by the Technical Architecture Group to the Executive Committee for a decision [DECISIONS] within 30 days.

Versions: In cases where a decision requires a version change, the attributes Status (recommended, superseded, or deprecated), Date Issued, Date Modified, Decision, Version, Replaces, and Is Replaced By will be modified in the affected terms as appropriate.

3.1. Minor editorial errata

An error in spelling, punctuation, grammar, or other clerical mistake discovered in a Darwin Core recommendation or term declaration may be corrected without a public comment period or Executive Decision. Minor editorial changes of this type do not require a version change for the affected term and/or documents.

3.2. Substantive editorial errata

A substantive error is one that compromises the usefulness or accuracy of systems based on Darwin Core. Those that are unequivocal (for example, an incorrect URI or reference) may be treated as minor editorial errata (Section 3.1).

Otherwise, the Technical Architecture Group will conduct a public comment period and seek an Executive decision to find a solution that minimizes adverse effects on existing applications. Changes of this nature require a version change for the affected term and/or documents.

3.3. Semantic changes to Darwin Core terms

Darwin Core terms may be changed based on public demand and consensus. A request to the Technical Architecture Group for a term change should consist of proposed values for the complete list of attributes given in the term definitions section of the Darwin Core Terms Complete History [HISTORY] along with a statement of justification for the change.

Term changes that are likely to have substantial functional impact on human understanding or machine processing will posted for public commentary and an Executive decision. Changes of this nature require a version change for the affected term and/or documents.

3.4. Addition of Darwin Core terms

New terms may be added to the Darwin Core namespaces based on public demand and consensus. A request to the Technical Architecture Group [TDWG-TAG] for a new term should consist of proposed values for the complete list of attributes given in the term definitions section of the Darwin Core Terms Complete History [HISTORY] along with a statement of justification for the new term, including an explanation of why no existing term will suffice.

New term proposals will be posted for public commentary and an Executive decision. Changes of this nature require a version change for the affected term and/or documents.

4. Persistence Policy

TDWG recognizes that people and applications depend on the persistence of formal documents and machine processable schemas that have been made publicly available. In particular, the stability of Darwin Core term URIs and Darwin Core namespace URIs is critical to interoperability over time. Thus, the wide promulgation of this set of URIs dictates that they be maintained to support legacy applications that have adopted them.
