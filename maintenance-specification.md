# TDWG Vocabulary Maintenance Specification #

This draft should be considered neither stable nor citable.

**Title:** TDWG Vocabulary Maintenance Specification

**Date Issued:**

**Date Modified:**

**Contributors:** Steve Baskauf (TDWG Vocabulary Maintenance Specification Task Group), John Wieczorek (TDWG Darwin Core Interest Group), Markus Döring (GBIF), Renato De Giovanni (CRIA), Tim Robertson (GBIF), Dave Vieglais (KUNHM)

**Creator:** TDWG Vocabulary Maintenance Specification Task Group

**Abstract:** This document describes the processes used to modify TDWG vocabularies and their associated documents.

**Legal:** This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by Biodiversity Information Standards (TDWG).

**Part of TDWG Standard:**

### Table of Contents ###

[generate when complete]

## **1 Introduction** ##

Vocabulary standards differ from other Biodiversity Information Standards (TDWG) standards in that they are likely to change over time as they evolve to meet the changing needs of the biodiversity informatics community.  These changes may be incremental, making it impractical to apply the full TDWG standards process [PROCESS] to every change.  This document details the categories of changes that can be made to a TDWG vocabulary standard, the mechanisms used to achieve those changes, and the entities that are responsible for shepherding those changes through the process.

### **1.1 Audience** ###

This document is intended for those who are involved in making changes to TDWG vocabulary standards.  That includes those who want to submit change proposals and members of Interest Groups that are responsible for vocabulary maintenance.

### **1.2 Content** ###

This is the only document associated with the Vocabulary Maintenance Specification.  All parts of it are normative.  

### **1.3 Definitions** ###

**document** - a unit of information that can be stored or retrieved electronically as a single file.

**normative** - the prescriptive part of a standard that specifies that which is necessary to comply with the standard

**non-normative** - an informative part of a standard that provides supplemental information such as history, examples, and additional explanation beyond the information necessary to comply with the standard.

**term** - an entity representing a class, property, or concept.  A term is identified by an Internationalized Resource Identifier (IRI), may have one or more human-readable labels, and is defined by a series of properties that include a human-readable definition.

**vocabulary** - a collection of standardized terms and their definitions.

## **2 Administration** ##

### **2.1 Vocabulary Maintenance Interest Groups** ###
At the time of the adoption of a vocabulary standard, an Interest Group charged specifically with the maintenance of that standard will be chartered.  That Interest Group will be subject to the normal expectations described for Interest Groups in the TDWG Standards Development Process document [PROCESS].  Because of its special relationship to an active TDWG vocabulary, a vocabulary maintenance Interest Group cannot be disbanded unless the vocabulary it maintains is deprecated.  Therefore, if the Interest Group's convener is unable to continue in that role, that convener should be succeeded by a core member of the Interest Group.  If there are no core members of the Interest Group that are able take on the role of convener, the Executive committee will appoint a convener who will reorganize the Interest Group.

### **2.2 Mechanisms for managing changes** ###
The Interest Group charged with maintaining a vocabulary standard will maintain an issues tracking system and will assess proposed changes according to the procedures described in this document.  The vocabulary maintenance Interest Group may also establish Task Groups to accomplish broader changes to the standard, such as creating or revising associated documents, or determining how the terms of the vocabulary might be used with a new technology.  

### **2.3 Annual review** ###
The vocabulary maintenance Interest Group bears the primary responsibility for managing the processes associated with changes to vocabulary terms and documents related to the vocabulary.  The Interest Group must ensure that justifiable changes occur in a timely fashion and should review proposed changes annually.  In that annual review, each proposal should be subjected to one of the following actions:
- move the proposal to public comment if there is sufficient support for its adoption.
- leave the proposal in the issue tracker for another year.
- remove the proposal from active consideration if it is clear that it lacks sufficient support.  

At the time of the annual review, the Interest Group will also consider the progress of any Task Groups chartered by the group.  The Task Group's annual status report should be considered as part of this review.  If the Interest Group concludes that there has been insufficient progress or interest in continuing the work of the
Task Group, they should consult with the convener of the Task Group to determine a course of action, which may include reorganizing the Task Group or recommending to the Executive Committee that the Task Group be disbanded.

## **3 Change Process** ##

### **3.1 Justifications for change** ###

There are several important attributes of TDWG vocabularies:

- facilitation of data sharing
- maximal reusability in multiple contexts
- stability and persistence

The benefits of expansion and evolution of TDWG vocabularies must be balanced against the need to maintain the attributes listed above.  It is the responsibility of the managing Interest Group, in consultation with the community and the Executive Committee, to weigh the potential benefits of changes to the vocabulary against the costs.   These considerations influence the term change process as it is described in the remaining subsections of Section 3.

### **3.2 Errata** ###

**3.2.1 Minor editorial errata**

Errors in spelling, punctuation, grammar, or other clerical mistakes discovered in a term declaration or document associated with the vocabulary may be corrected without a public comment period or Executive Decision. Minor editorial changes of this type do not require a version change for the affected term and/or documents.

**3.2.2 Substantive editorial errata**

A substantive error is one that compromises the usefulness or accuracy of systems based on the vocabulary. Those that are unequivocal (for example, an incorrect URI or reference) may be treated as minor editorial errata (Section 3.2.1) and be corrected accordingly.  If, in the opinion of the Interest Group, the correction is likely to impact existing implementations, the Interest Group should inform the community via the TDWG mailing list [TDWG-CONTENT].

in the case of equivocal substantive errors, the Interest Group will conduct a public comment period and seek an Executive decision to find a solution that minimizes adverse effects on existing applications. Changes of this nature require a version change for the affected term and/or documents.

### **3.3 Changes to vocabulary terms** ###

The terms in a vocabulary can be changed by modifying the attributes of an existing term, by adding a new term, or by deprecating an existing term.  Although the nature of the change varies somewhat among these three categories of changes, the process for achieving the change is the same, and is described in Sections 3.3.1 through 3.3.3.

**3.3.1 Initiating a term change**

Terms in TDWG vocabularies may be changed based on public demand and consensus.  Because the primary purpose of TDWG vocabularies is to facilitate data sharing, it is necessary to show that multiple parties will benefit from the change.  As such, it is a minimum requirement that two independent entities indicate that they desire the change (the **demand** requirement).  Additionally, it is required that there is a consensus within the community that the proposed change will accomplish the desired outcome (the **efficacy** requirement), and that making the change will not adversely affect the interoperability of existing applications that depend on the stability of vocabulary terms (the **stability** requirement).  In order for a proposed term change to move forward, the maintaining Interest Group must determine that sufficient input has been acquired to conclude that the minimal requirements for demand, efficacy, and stability are likely to be met.  Evidence in favor of proposed changes may be accumulated as the result of any of a number of possible activities, including: through public discussion on the TDWG email list [TDWG-CONTENT], as the result of activities of a Task Group chartered by the Interest Group, through discussion within self-organized groups, or as the result of a conference.  

A formal proposal for a term change is made through the tracking system maintained by the Interest Group.  It must include the proposed values for the complete list of attributes specified by the Interest Group, along with a statement of justification for the change. If the proposed change is a term addition, the proposal should include an explanation of why no existing term will suffice.  If the proposed change is a deprecation, the proposal should include a description of alternatives or replacements that will avoid disruption to the stability of legacy applications.  The proposal may include links to other supporting information, such as conference or Task Group reports.

There is no requirement that the official proposal be made either before or after evidence in favor of the proposal is accumulated.  However, the proposal will not move forward to the public comment phase until the Interest Group has determined that sufficient evidence has been accumulated to determine that the minimal requirements for demand, efficacy, and stability are likely to be met.  Therefore, proponents of the change may wish to announce the proposal on the TDWG email list [TDWG-CONTENT] in order to initiate further discussion of the proposal.  

**3.3.2 Public comment**

If the maintaining Interest Group determines that the proposed term change is likely to meet the demand, efficacy, and stability requirements, it will conduct a minimum 30 day comment period.  The start of the comment period will be announced on the TDWG email list [TDWG-CONTENT].  During the comment period, the proposal can be refined based on discussion in an effort to reach consensus (no dissenting opinion expressed publicly on the mailing list for 30 days from the most recent iteration). As necessary, the term change proposal may be modified by its submitter or the Interest Group in an attempt to shape a proposal that can achieve community consensus.  An official change in the proposal will trigger the start of a new 30 day period.  

If the Interest Group believes that a consensus has reached, the proposal will be presented by the Interest Group to the Executive Committee for a decision [DECISIONS].  If the Interest Group believes that no consensus has been reached, it has two options.  It may leave the proposal open to allow for further discussion and refinement.  It may also close the proposal if it appears that proposal is not likely to achieve the necessary support in the near future.  There is no specific time requirement for action on the part of the Interest Group - it may allow discussion to continue as long as it seems productive.  However, in the interest of providing closure, all open issues should be reviewed annually as described in Section 2.3.

**3.3.3 Executive Committee decision**

After the maintaining Interest Group has forwarded a proposal to the Executive Committee, the Committee will render a decision within 30 days.  The decision may take three forms:

- accept the proposal.  The decision will be recorded in the decision history
[DECISIONS] and appropriate changes will be made in the documentation associated with the vocabulary standard.
- reject the proposal.  The decision will be recorded in the decision history and no changes will be made in the documentation.
- return the proposal to the public review level.  No decision will be recorded in the decision history.  The Executive committee should provide recommendations for steps to be taken to make the proposal acceptable, e.g. additional discussion, additional work by a Task Group, testing, etc.

In all three of these cases, the decision should be reported to the community via the TDWG email list [TDWG-CONTENT].  

**3.3.4 Implementing term changes**

**3.3.4.1 Changes to an existing term**

Correction of substantive errors that are likely to impact existing implementations (Section 3.2.2) and term changes that are likely to have substantial functional impact on human understanding or machine processing require a version change for the affected term.  The metadata for the current terms and term versions will be modified in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].

**3.3.4.2 Addition of a new term**

If a new term is created as the result of an Executive Committee decision, a term IRI will be constructed according to the guidelines incorporated in the vocabulary standard or TDWG precedents.  Metadata for the term will be generated in accordance with the TDWG Standards Documentation Specification [DOC-SPEC], and added to the vocabulary term list documents.

If a "borrowed" term is added to a vocabulary, metadata for that term will be added to the vocabulary term list in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].

**3.3.4.3 Deprecation of an existing term**

If an existing term is deprecated, this action should be noted in the term metadata in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].  Because of importance of maintaining the interoperability of legacy applications, it is desirable that providers and developers be provided with guidance for transitioning to the use of alternative terms in the vocabulary's human-readable documents.  

### **3.4 Changes to documents supporting the vocabulary** ###

**3.4.1 General principles**

The documents included within a vocabulary standard support the vocabulary in various ways.  It is therefore difficult to specify a single change process that is appropriate for all possible changes to documents associated with the vocabulary.  However, the general principles expressed in Section 3.1 apply to changes in associated documents as well as to term changes.  The greater the likelihood that changes to the documents will affect the stability of the vocabulary, the more care must be taken by the Interest Group to inform and consult with the community and the Executive Committee.  In cases that are not specifically described in the subsections of Section 3.4, the Interest Group should weigh the impact of the proposed changes and use its discretion to choose a form of intervention that is appropriate for the level of potential impact on the vocabulary.

**3.4.2 Document changes related to term changes**

In cases where term changes have been approved by the Executive Committee, the Interest Group will make appropriate changes to documents that are necessary to communicate those changes, without invoking any additional change procedures.  

**3.4.3 Normative and non-normative content**

Normative content is the prescriptive part of a standard that specifies that which is necessary to comply with the standard.  As such, changes to normative content is likely to have a significant impact on interoperability.  For that reason, proposed changes to normative content that are not errata (Section 3.2) or that do not result automatically from approved term changes (Section 3.4.2) will generally require the full change process of discussion and formal proposal on the issue tracker (analogous to Section 3.3.1, but without aspects specifically related to terms), public comment (Section 3.3.2), and Executive Committee decision (Section 3.3.3).  Changes to normative content will nearly always trigger a version change for the affected document.

Because non-normative content provides only supplemental information, the Interest Group may use its discretion to decide the extent to which the community should be involved in implementing changes to non-normative content.  For example, relatively cosmetic changes, such as improving figures, changing formatting, minor improvements to examples, etc. can be made without triggering any change process or notification via the TDWG email list [TDWG-CONTENT].  More significant changes or improvements to non-normative content may warrant notification of the community via the TDWG email list [TDWG-CONTENT].  If the Interest Group determines that proposed changes to non-normative content are significant enough, it may chose to invoke the full change process.  Substantive changes to non-normative content will usually trigger a version change for the affected document.

**3.4.3 New documents**

From time to time, new documents may be added to vocabulary standards.  The managing Interest Group should consider the factors described in section 3.4.3 when determining an appropriate process for ratifying new documents.  Since new documents are likely to contain significant amounts of normative content, it will generally be necessary for them to pass through the full change process of discussion, formal proposal, public comment, and Executive Committee decision.  Given the impracticality of creating and editing technical documents via a public forum, writing, discussing, and revising new documents will usually be carried out by a Task Group ahead of the formal proposal for addition to the standard.  

## **4 Implementation reports** ##

Each TDWG vocabulary term has a definition and commentary that are meant to promote the consistent use of the term across applications and disciplines. The intention is that the basic terms can be adapted to new purposes without disrupting existing applications.  Vocabularies can be enhanced by building upon this basic term layer.  For example, added features may constrain the use of basic terms through data types or may apply additional semantics to term metadata that may result in entailments that are not explicitly expressed. An enhancement may also take the form of a formal application profile.

If a group proposes that vocabulary enhancements be included as part of the vocabulary standard, the proposal will move through the full change process.  However, before the proposal can move to the public comment stage, the proposer must submit an implementation report

### **4.1 Content of the implementation report** ###

In general, the implementation report should specify the goals of the enhancement, the features that enable the enhancement to meet the goals, and a report of efforts to implement those features.

**4.1.1 Goals**

The goals of the enhancement should be summarized clearly in a paragraph.  It is also desirable to specify use-cases to be satisfied by the enhancement.  

**4.1.2 Features**

The features of the enhancement must be listed with an explanation of how each feature contributes to accomplishing the stated goals.

**4.1.3 Implementation experience**

The report should describe each independent and interoperable implementation that was tested.  In the description of each implementation, the features (Section 4.1.2)  that were successfully included in the implementation must be reported. The report for each implementation should include links to code, sample datasets, etc. that were used in the test implementations.  

 If the implementation tests included performance testing, the report should describe test conditions and any benchmarks used.  The results of interoperability testing should be included, if available.

 ### **4.2 Use of the implementation report** ###

The Interest Group charged with maintaining the standard will examine the implementation report along with other supporting evidence to evaluate the extent to which the proposal is likely to meet the demand, efficacy, and stability requirements as described in Section 3.3.1.  If the evaluation indicates that the proposed enhancement is likely to meet those requirements, the Interest Group will advance the proposal to the public comment stage.  If the Interest Group identifies deficiencies, it may make suggestions to the proposers of additional actions that might be taken to meet the requirements.  

### **4.3 Timing of the implementation report** ###

Test implementations and creation of an implementation report will generally be completed before a formal change proposal is made.  However, if the proposed enhancements have already been partially implemented, a formal proposal may provide an opportunity to solicit additional implementers to participate in testing the enhancements.  The only requirement is that the implementation report must be complete and published before the Interest Group can move the proposal to public comment.

### **4.4 Archiving of the implementation report** ###

If the proposed enhancement is adopted as part of the vocabulary standard, the implementation report should be archived as a non-normative document in the standard and a link should be made from the document describing the enhancement to the implementation report.

## **5 References** ##

[DECISIONS] (will there be a separate decision history for each vocabulary, or will the current Darwin Core decision history morph into a decision history for all TDWG vocabularies?)

[DOC-SPEC] (put the reference to the Standards Documentation Specification here)

[PROCESS] Biodiversity Information Standards. The Standards Development Process. http://www.tdwg.org/about-tdwg/process/

[TDWG-CONTENT] TDWG Standards Content Discussions email list. http://lists.tdwg.org/mailman/listinfo/tdwg-content

---------------------------
## The sections below this point will remain a part of Darwin Core, with minor edits. ##

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

4. Persistence Policy

TDWG recognizes that people and applications depend on the persistence of formal documents and machine processable schemas that have been made publicly available. In particular, the stability of Darwin Core term URIs and Darwin Core namespace URIs is critical to interoperability over time. Thus, the wide promulgation of this set of URIs dictates that they be maintained to support legacy applications that have adopted them.
