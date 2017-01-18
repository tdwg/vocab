# TDWG Vocabulary Maintenance Specification (draft of 2016-08-02 as submitted for review)

**Title:** Vocabulary Maintenance Specification

**Date version issued:**

**Date created:**

**Part of TDWG Standard:** http://www.tdwg.org/standards/x

**This version:** http://something.tdwg.org/x/2016-x-x

**Latest version:** http://something.tdwg.org/x

**Abstract:** This document describes the processes used to modify TDWG vocabularies and their associated documents.

**Contributors:** Steve Baskauf (TDWG Vocabulary Maintenance Specification Task Group), John Wieczorek (TDWG Darwin Core Interest Group), Stan Blum (TDWG Process Interest Group), Robert A. Morris (UMASS-Boston, TDWG Imaging Interest Group), Jonathan Rees (Duke University), Joel Sachs (TDWG RDF Task Group), Greg Whitbread (TDWG Technical Architecture Group).  Review editor: Review editor: Dag Endresen (GBIF Norway/NHM University of Oslo)

**Creator:** TDWG Vocabulary Maintenance Specification Task Group

**Bibliographic citation:** Vocabulary Maintenance Specification Task Group. 2016. Vocabulary Maintenance Specification. Biodiversity Information Standards (TDWG) http://www.tdwg.org/standards/x (put link here to provide access to standardized machine-readable citation export format)

### Table of Contents

```
1 Introduction
1.1 Audience
1.2 Content
1.3 Definitions
1.4 The general structure of TDWG vocabularies

2 Administration
2.1 Vocabulary Maintenance Interest Groups
2.2 Mechanisms for managing change
2.3 Annual review

3 Change Process
3.1 Justifications for change
3.1.1 Version changes
3.2 Errata
3.2.1 Minor editorial errata
3.2.2 Substantive editorial errata
3.3 Changes to vocabulary terms
3.3.1 Initiating a term change
3.3.2 Public comment
3.3.3 Executive Committee decision
3.3.4 Implementing term changes
3.3.4.1 Changes to an existing term
3.3.4.2 Addition of a new term
3.3.4.3 Deprecation of an existing term
3.4 Changes to documents supporting the vocabulary
3.4.1 General principles
3.4.2 Document changes related to term changes
3.4.3 Normative and non-normative content
3.4.4 New documents

4 Vocabulary enhancements
4.1 Development
4.2 User feedback reports
4.2.1 Feature Report
4.2.2 Implementation Experience Report
4.2.3 Use of the user feedback reports
4.2.4 Archiving the user feedback report

5 References
```

## **1 Introduction**

Vocabulary standards differ from other Biodiversity Information Standards (TDWG) standards in that they are likely to change over time as they evolve to meet the changing needs of the biodiversity informatics community.  These changes may be incremental, making it impractical to apply the full TDWG standards process [PROCESS] to every change.  This document details the categories of changes that can be made to a TDWG vocabulary standard, the mechanisms used to achieve those changes, and the entities that are responsible for shepherding those changes through the process.

### **1.1 Audience**

This document is intended for those who are involved in making changes to TDWG vocabulary standards.  That includes those who want to submit change proposals and members of Interest Groups who are responsible for vocabulary maintenance.

### **1.2 Content**

This is the only document associated with the Vocabulary Maintenance Specification.  All parts of it are normative.  

### **1.3 Definitions**

**document** - a unit of information that can be stored or retrieved electronically as a single file.

**implementation** - a component of the workflow of a user or organization.  In the context of this standard, an implementation plays a role in data transmission and storage. It may be involved in sending, generating, or validating data, or it may be involved in processing, storing, aggregating, indexing, or reasoning upon data that is received.  Implementations can include software and data models.

**issue tracker** - a publicly accessible online system managed by a maintaining interest group (Section 2.1) that allows users to officially suggest vocabulary changes.  The issue tracker allows the public to know the current status of proposed changes.  

**normative content** - prescriptive parts of a standard that specify what must be done to comply with the standard

**non-normative content** - informative parts of a standard that provide supplemental information such as history, examples, and additional explanation beyond the information necessary to comply with the standard.

**term** - an entity representing a class, property, or concept.  A term is identified by an Internationalized Resource Identifier [IRI], may have one or more human-readable labels, and is defined by a series of properties that include a human-readable definition.  Terms and their values are used to communicate information about a subject resource.

**vocabulary** - a collection of standardized terms and their definitions.

### **1.4 The general structure of TDWG vocabularies**

All TDWG vocabularies include a "flat", basic layer of terms that have clear human-readable definitions and commentary that promote the terms' consistent use across implementations and disciplines [GBIF-KOS, Section 1.1]. To permit maximal reuse and flexibility, the terms have few constraints with regard to datatyping, no formal range and domain declarations, and few additional semantics added to term metadata that could result in entailments that are not explicitly expressed. The intent is that the terms of the basic layer can be adapted to new purposes without disrupting existing implementations.  

Vocabularies can be enhanced by building upon this basic term layer.  Added features may include:

- constraining the use of literal-value terms through data types
- establishing relationships among class terms by applying a domain model
- introducing additional term properties that generate entailments that can be materialized through machine reasoning

In aggregate, these enhancements may take the form of an application profile or formal ontology.  Unlike the basic layer, which is broadly applicable, vocabulary enhancements may be used by a subset of the community whose interests are served by the constraints imposed by the enhancements.  Thus there may be any number of enhancements developed for a particular vocabulary.

## **2 Administration**

### **2.1 Vocabulary Maintenance Interest Groups**
At the time of the adoption of a vocabulary standard, an Interest Group charged specifically with the maintenance of that standard will be chartered.  That Interest Group will be subject to the normal expectations described for Interest Groups in the TDWG Standards Development Process document [PROCESS].  If a TDWG vocabulary continues to be actively developed, a vocabulary maintenance Interest Group will not normally be disbanded.  Therefore, if the Interest Group's convener is unable to continue in that role, that convener should be succeeded by a core member of the Interest Group.  If there are no core members of the Interest Group that are able take on the role of convener, the Executive Committee will appoint a convener who will reorganize the Interest Group.  If a TDWG vocabulary achieves a level of stability that makes its maintenance unnecessary, or if the status of the standard defining the vocabulary is changed to Retired Standard [STATUS], the Executive Committee may choose to disband the maintaining Interest Group.

### **2.2 Mechanisms for managing changes**
The Interest Group charged with maintaining a vocabulary standard will maintain an issue tracking system and will assess proposed changes according to the procedures described in this document.  The vocabulary maintenance Interest Group may also establish Task Groups to accomplish broader changes to the standard, such as creating or revising associated documents, or determining how the terms of the vocabulary might be used with a new technology.  

### **2.3 Annual review**
The vocabulary maintenance Interest Group bears the primary responsibility for managing the processes associated with changes to vocabulary terms and documents related to the vocabulary.  The Interest Group should review proposed changes annually.  In that annual review, each proposal should be subjected to one of the following actions:
- move the proposal to public comment if there is sufficient support for its adoption.
- leave the proposal in the issue tracker for another year.
- remove the proposal from active consideration if it is clear that it lacks sufficient support.  

At the time of the annual review, the Interest Group will also consider the progress of any Task Groups chartered by the group.  The Task Group's annual status report should be considered as part of this review.  If the Interest Group concludes that there has been insufficient progress or interest in continuing the work of the
Task Group, they should consult with the convener of the Task Group to determine a course of action, which may include reorganizing the Task Group or recommending to the Executive Committee that the Task Group be disbanded.

## **3 Change Process**

### **3.1 Justifications for change**

There are several important attributes of TDWG vocabularies:

- facilitation of data exchange and use (interoperability)
- maximal reusability in multiple contexts
- stability and persistence

The benefits of expansion and evolution of TDWG vocabularies must be balanced against the need to maintain the attributes listed above.  It is the responsibility of the managing Interest Group, in consultation with the community and the Executive Committee, to weigh the potential benefits of changes to the vocabulary against the costs.   Decisions should be guided by assessing the extent to which proposals meet the following requirements.  

Because the primary purpose of TDWG vocabularies is to facilitate data sharing, it is necessary to show that multiple parties will benefit from the change.  As such, it is a minimum requirement that two independent entities indicate that they desire the change (the **demand** requirement).  Additionally, it is required that there is a consensus within the community that the proposed change will accomplish the desired outcome (the **efficacy** requirement), and that making the change will not adversely affect the interoperability of existing implementations that depend on the stability of the vocabulary (the **stability** requirement).

The considerations listed above influence the change process as it is described in the remainder of this document.  In cases where there is no specific course of action prescribed in this document for a proposed change, the general principles outlined above should be used to guide the decisions of the maintaining Interest Group.

**3.1.1 Version changes**

Incrementing the version of a resource signals that an important change has been made to that resource.  In the context of this specification, the version of a resource should be changed in circumstances where the change to the resource might affect interoperability.  That is, the version is incremented when the change might affect the ability of implementations to generate data that is understandable to other implementations, or the ability of implementations to consume data generated by other implementations.

The Interest Group maintaining the vocabulary should maintain a version log that summarizes the changes that have occurred with each version change associated with the vocabulary.  This log can assist implementers to determine whether particular changes are likely to affect their implementations and to take appropriate actions to minimize the effect.

### **3.2 Errata**

**3.2.1 Minor editorial errata**

Errors in spelling, punctuation, grammar, or other clerical mistakes discovered in a term declaration or document associated with the vocabulary may be corrected without a public comment period or Executive Decision. Minor editorial changes of this type do not require a version change for the affected term and/or documents.

**3.2.2 Substantive editorial errata**

A substantive error is one that compromises the usefulness or accuracy of systems based on the vocabulary. Those that are unequivocal (for example, an incorrect URI or reference) may be treated as minor editorial errata (Section 3.2.1) and be corrected accordingly.  If, in the opinion of the Interest Group, the correction is likely to impact existing implementations, the Interest Group should inform the community via the TDWG mailing list [TDWG-CONTENT].

In the case of equivocal substantive errors, the Interest Group will conduct a public comment period and seek an Executive decision to find a solution that minimizes adverse effects on existing implementations. Changes of this nature require a version change for the affected term and/or documents.

### **3.3 Changes to vocabulary terms**

The terms in a vocabulary can be changed by modifying the attributes of an existing term, by adding a new term, or by deprecating an existing term.  Although the nature of the change varies somewhat among these three categories of changes, the process for achieving the change is the same, and is described in Sections 3.3.1 through 3.3.3.

**3.3.1 Initiating a term change**

Terms in TDWG vocabularies may be changed based on public demand and consensus.  In order for a proposed term change to move forward, the maintaining Interest Group must determine that sufficient input has been acquired to conclude that the minimal requirements for demand, efficacy, and stability are likely to be met (Section 3.1).  Evidence in favor of proposed changes may be accumulated as the result of any of a number of possible activities, including: through public discussion on the TDWG email list [TDWG-CONTENT], as the result of activities of a Task Group chartered by the Interest Group, through discussion within self-organized groups, or as the result of a conference.  

A formal proposal for a term change is made through the tracking system maintained by the Interest Group.  It must include the proposed values for the complete list of attributes specified by the Interest Group, along with a statement of justification for the change. If the proposed change is a term addition, the proposal should include an explanation of why no existing term will suffice.  If the proposed change is a deprecation, the proposal should include a description of alternatives or replacements that will avoid disruption to the stability of legacy implementations.  The proposal may include links to other supporting information, such as conference or Task Group reports.

There is no requirement that the official proposal be made either before or after evidence in favor of the proposal is accumulated.  However, the proposal will not move forward to the public comment phase until the Interest Group has determined that sufficient evidence has been accumulated to determine that the minimal requirements for demand, efficacy, and stability are likely to be met.  Therefore, proponents of the change may wish to announce the proposal on the TDWG email list [TDWG-CONTENT] in order to initiate further discussion of the proposal.  

**3.3.2 Public comment**

If the maintaining Interest Group determines that the proposed term change is likely to meet the demand, efficacy, and stability requirements, it will conduct a minimum 30 day comment period.  The start of the comment period will be announced on the TDWG email list [TDWG-CONTENT].  In an effort to reach consensus, the proposal may be modified based on discussion during the comment period. Consensus is indicated by no dissenting opinion expressed publicly on the mailing list for 30 days from the most recent modification of the proposal. The term change proposal may be modified by its submitter or the Interest Group in an attempt to shape a proposal that can achieve community consensus.  A change in the official proposal will trigger the start of a new 30 day period.  

If the Interest Group believes that a consensus has been reached, the proposal will be presented by the Interest Group to the Executive Committee for a decision.  If the Interest Group believes that no consensus has been reached, it has two options.  It may leave the proposal open to allow for further discussion and refinement.  It may also close the proposal if it appears that proposal is not likely to achieve the necessary support in the near future.  There is no specific time requirement for action on the part of the Interest Group - it may allow discussion to continue as long as it seems productive.  However, in the interest of obtaining closure, all open issues should be reviewed annually as described in Section 2.3.

**3.3.3 Executive Committee decision**

After the maintaining Interest Group has forwarded a proposal to the Executive Committee, the Committee will render a decision within 30 days.  The decision may take three forms:

- accept the proposal.  The decision will be recorded in the decision history and appropriate changes will be made in the documentation associated with the vocabulary standard.
- reject the proposal.  The decision will be recorded in the decision history and no changes will be made in the documentation.
- return the proposal to the public review level.  The decision will not be recorded in the decision history.  The Executive committee should provide recommendations for steps to be taken to make the proposal acceptable, e.g. additional discussion, additional work by a Task Group, testing, etc.

In all three of these cases, the decision should be reported to the community via the TDWG email list [TDWG-CONTENT].  

**3.3.4 Implementing term changes**

**3.3.4.1 Changes to an existing term**

Correction of substantive errors that are likely to impact existing implementations (Section 3.2.2) and term changes that are likely to have substantial functional impact on human understanding or machine processing require a version change for the affected term.  The metadata for the current terms and term versions will be modified in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].

**3.3.4.2 Addition of a new term**

If a new term is created as the result of an Executive Committee decision, a term IRI will be constructed according to the guidelines incorporated in the vocabulary standard or TDWG precedents.  Metadata for the term will be generated in accordance with the TDWG Standards Documentation Specification [DOC-SPEC], and added to the vocabulary term list documents.

If a "borrowed" term is added to a vocabulary, metadata for that term will be added to the vocabulary term list in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].

**3.3.4.3 Deprecation of an existing term**

If an existing term is deprecated, this action should be noted in the term metadata in accordance with the TDWG Standards Documentation Specification [DOC-SPEC].  Because of importance of maintaining the interoperability of legacy implementations, it is desirable that providers and developers be provided with guidance for transitioning to the use of alternative terms in the vocabulary's human-readable documents.  

### **3.4 Changes to documents supporting the vocabulary**

**3.4.1 General principles**

The documents included within a vocabulary standard support the vocabulary in various ways.  It is therefore difficult to specify a single change process that is appropriate for all possible changes to documents associated with the vocabulary.  However, the general principles expressed in Section 3.1 apply to changes in associated documents as well as to term changes.  The greater the likelihood that changes to the documents will affect the stability of the vocabulary, the more care must be taken by the Interest Group to inform and consult with the community and the Executive Committee.  In cases that are not specifically described in the subsections of Section 3.4, the Interest Group should weigh the impact of the proposed changes and use its discretion to choose a form of intervention that is appropriate for the level of potential impact on the vocabulary.

**3.4.2 Document changes related to term changes**

In cases where term changes have been approved by the Executive Committee, the Interest Group will make appropriate changes to documents that are necessary to communicate those changes, without invoking any additional change procedures.  

**3.4.3 Normative and non-normative content**

Normative content is the prescriptive part of a standard that specifies that which is necessary to comply with the standard.  As such, changes to normative content are likely to have a significant impact on interoperability.  For that reason, proposed changes to normative content that are not errata (Section 3.2) or that do not result automatically from approved term changes (Section 3.4.2) will generally require the full change process of discussion and formal proposal on the issue tracker (analogous to Section 3.3.1, but without aspects specifically related to terms), public comment (Section 3.3.2), and Executive Committee decision (Section 3.3.3).  Changes to normative content will nearly always trigger a version change for the affected document.

Because non-normative content provides only supplemental information, the Interest Group may use its discretion to decide the extent to which the community should be involved in implementing changes to non-normative content.  For example, relatively cosmetic changes, such as improving figures, changing formatting, minor improvements to examples, etc. can be made without triggering any change process or notification via the TDWG email list [TDWG-CONTENT].  More significant changes or improvements to non-normative content may warrant notification of the community via the TDWG email list [TDWG-CONTENT].  If the Interest Group determines that proposed changes to non-normative content are significant enough, it may chose to invoke the full change process.  Substantive changes to non-normative content will usually trigger a version change for the affected document.

**3.4.4 New documents**

From time to time, new documents may be added to vocabulary standards.  The managing Interest Group should consider the factors described in section 3.4.3 when determining an appropriate process for ratifying new documents.  Since new documents are likely to contain significant amounts of normative content, it will generally be necessary for them to pass through the full change process of discussion, formal proposal, public comment, and Executive Committee decision.  Given the impracticality of creating and editing technical documents via a public forum, writing, discussing, and revising new documents will usually be carried out by a Task Group ahead of the formal proposal for addition to the standard.  

## **4 Vocabulary enhancements**

### **4.1 Development**

Because vocabulary enhancements (Section 1.4) usually involve a coordinated set of additions to the vocabulary, they will generally be developed as a package that will submitted as a single proposal in the tracking system.  This package will usually be developed by a group representing the community whose interests will be served by the enhancements.  The group may be tasked by the Interest Group maintaining the vocabulary as an official Task Group, or it may arise spontaneously in response to community need.  In either case, the group developing the enhancements will be referred to here as the "working group".  

Because a vocabulary enhancement is special category of vocabulary change, the general change process described in the subsections of Section 3 apply.  That is, the vocabulary enhancement as a package will be proposed formally via the tracking system (Section 3.3.1), be subjected to public comment (Section 3.3.2), and forwarded for an Executive Committee Decision (Section 3.3.3) before it is adopted as an addition to the standard.

Because of the complexity involved in developing a vocabulary enhancement, it is important that enhancements be fully developed and tested before they are formally submitted as a proposed addition to the vocabulary.  This development and testing will be documented by user feedback reports (Section 4.2).  The working group developing the enhancement is encouraged to solicit feedback from the Interest Group prior to formal submission in order to increase the likelihood of submitting a successful proposal.  Because TDWG is an open community whose standards are based on consensus, working groups should carry out the development of their enhancements in an open and inclusive manner.  

After submission of a proposal by the working group, the Interest Group charged with maintaining the standard will examine the Feature Report and Implementation Experience Report to evaluate the extent to which the proposal is likely to meet the demand, efficacy, and stability requirements as described in Section 3.1. If the evaluation indicates that the proposed enhancement is likely to meet those requirements, the Interest Group will advance the proposal to the public comment stage.  If the Interest Group identifies deficiencies, it may make suggestions to the working group of additional actions that might be taken to meet the requirements.

### **4.2 User feedback reports**

Proposals to include vocabulary enhancements as part of the vocabulary standard will move through the full change process.  However, because these enhancements also place constraints on use of the basic vocabulary layer, there should be clear evidence of their necessity and effectiveness relative to community need.  This evidence must be reported by the working group developing the enhancements in the form of user feedback reports.   

### **4.2.1 Feature Report**

The first required user feedback report is a Feature Report.  The purpose of the Feature Report is to identify the features that should be included in the enhancement in order to achieve goals identified by the community.  There is no specific format required for the Feature Report.  However, the report should include a numbered list of features and indicate how the need for each feature was determined from community input.  Accumulating submitted use cases or competency questions is a common mechanism for determining necessary features.  Although there is no specified timeline for the creation of the Feature Report, it should be compiled early in the process so that it can guide the development of the enhancements.  

### **4.2.2 Implementation Experience Report**

The second required user feedback report is an Implementation Experience Report.  The purpose of the Implementation Experience Report is to document the experience of independent implementations with the features listed in the Feature Report.  Although there is no specific format required for the Implementation Experience Report, the report should present clearly aggregated data from test reports submitted by individual implementers.  

The report should provide information about the extent to which each implementer successfully included each of the features detailed in the Feature Report.  If the implementation is an application or service, successful implementation of features may be determined by subjecting the implementation to a test suite provided by the working group developing the vocabulary enhancements.  

Because it is desirable for enhancements to be robust, it is helpful if implementers report behavior when features are tested on a large-scale, with "dirty" data, or in a disruptive environment.  Since promoting interoperability is also a goal, documenting interactions involving data generated from different code bases is also valuable.

### **4.2.3 Use of the user feedback reports**

The overall goal of the user feedback reports is to enable the working group to introduce into the enhancement only features that are necessary and implementable.  If the Implementation Experience Report indicates that a feature has not been successfully included in at least two independent implementations, the working group should consider dropping that feature from the enhancement.  

The user feedback reports are also used by the maintaining Interest Group to assist in the decision of whether to advance the formal proposal to public comment (Section 4.1), and as an organized source of information to the community during the public comment period.

### **4.2.4 Archiving the user feedback report**

If the proposed enhancement is adopted as part of the vocabulary standard, the implementation report should be archived as a non-normative document in the standard and a link should be made from the document describing the enhancement to the implementation report.

## **5 References**

[DOC-SPEC] http://www.tdwg.org/standards/x TDWG Standards Documentation Specification (finalize citation when complete)

[GBIF-KOS] http://www.gbif.org/resource/80656 Recommendations for the Use of Knowledge Organisation Systems by GBIF. 04 Feb 2011. Global Biodiversity Information Facility, 49 pp.

[IRI] http://tools.ietf.org/html/rfc3987 Internationalized Resource Identifiers (IRIs). 2005. The Internet Engineering Task Force.

[PROCESS] http://www.tdwg.org/about-tdwg/process/ The Standards Development Process. Biodiversity Information Standards.

[STATUS] http://www.tdwg.org/standards/status-and-categories/ Key to TDWG Standards Status. Biodiversity Information Standards.

[TDWG-CONTENT] http://lists.tdwg.org/mailman/listinfo/tdwg-content TDWG Standards Content Discussions email list.

-----------------
This document is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/). ![http://creativecommons.org/licenses/by/4.0/](https://licensebuttons.net/l/by/4.0/88x31.png).

Copyright 2016 - Biodiversity Information Standards - TDWG - [Contact Us](http://www.tdwg.org/about-tdwg/contact-us/)
