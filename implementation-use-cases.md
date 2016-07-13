# Use cases and implementation experience in standards and vocabulary development

Steve Baskauf - TDWG Vocabulary Management Task Group - 2016-07-12

This document contains some reference notes and has no official standing.  It is subject to change at any time and should not be considered to be stable nor citable.

## Background ##

Both the W3C and IETF standards process include a role for documenting implementation experience before a standard is adopted.  Implementation reports document whether particular implementations successfully pass a series of tests that are designed to determine if a feature of the standard has been implemented.  A working group may provide a standardized "test suite" that can be used by developers to evaluate the coverage of an implementation's features.  Implementation reports may also note which terms of a vocabulary were used in particular implementations (e.g. vocabularies or data repositories).

In the [IETF process](https://tools.ietf.org/html/rfc2026#section-4.1.2), there is a requirement of two independent and interoperable implementations from different code bases before a Draft Standard can be elevated to Internet Standard status.  The Working Group chair is responsible for documenting the implementations, but the specifics of the report are not detailed.  However, the documentation must include information about the support of each individual option and feature.  It is also suggested that vendors should deploy implementations in a disruption-sensitive environment and to subject the implementation to unforeseen behavior when subjected to large-scale use.

In the [W3C Process](https://www.w3.org/2015/Process-20150901/#rec-pr), a Working Group must document how adequate implementation experience will be demonstrated before a Candidate Recommendation can move to Proposed Recommendation status.  In order for a Proposed Recommendation to move to W3C Recommendation status, the Working Group must show adequate implementation experience. There is no exhaustive list of requirements for documenting implementation experience (refer to [this](https://www.w3.org/2015/Process-20150901/#implementation-experience) for considerations), but the Working Group must show that independent interoperable implementations of each feature of the specification has been realized.  It is recommended that the Working Group plan for implementation efforts by developing appropriate tests.

In the W3C standards development process, it is also a common practice that working groups accumulate use cases to guide the development of requirements to be met by the specification. Use cases are descriptions of specific tasks whose completion a standard should facilitate.  

"Competency questions are an ontology design paradigm analogous to use case scenarios. They are formulated as queries, either formal or informal, against which the ontologies and a knowledge base may be tested for efficacy and scope. Using the questions, the designer can identify the concepts and their relationships needed for the ontology." (from [Recommendations for the Use of Knowledge Organisation Systems by GBIF](http://www.gbif.org/resource/80656))

## Use cases and implementation reports for application specifications ##

Some standards consist of specifications that should be met by applications that generate, consume, or transmit data.  In such cases, the goal is to ensure interoperability by ensuring that the processing of data by the application is consistent with the requirements of the standard.  

Examples:

The SPARQL 1.1 W3C Recommendation describes both a query language and a communication protocol for transmitting and receiving queries.  Applications implementing SPARQL can demonstrate that they can receive queries, process the queries correctly against a set of triples, and return results in a variety of formats.  The use cases are described [here](https://www.w3.org/TR/rdf-dawg-uc/).  The test case structure is described [here](https://github.com/w3c/rdf-tests/tree/gh-pages/sparql11).  A report summarizing the results of implementation testing is [here](https://www.w3.org/2009/sparql/implementations/).  An example of an implementation report of the SPARQL transmission protocol is [here](https://www.w3.org/2001/sw/DataAccess/impl-report-protocol).  

The JSON-LD W3C Recommendation describes how linked data can be transmitted in the form of JSON.  It also includes processing algorithms and API specifications that specify how applications should handle and transform JSON-LD data.  Some use cases (not exclusively for JSON-LD) are [here](https://www.w3.org/2013/dwbp/wiki/RDF_AND_JSON-LD_UseCases). The input and output expected for a variety of tests and the performance of particular applications on those tests is reported [here](https://dvcs.w3.org/hg/json-ld/raw-file/default/test-suite/reports/cr-20131022.html).  Directions for running the test suite are [here](http://json-ld.org/test-suite/).  Instructions for submitting machine-readable implementation reports are given [here](http://json-ld.org/test-suite/reports/).

## Use-cases and implementation reports for vocabularies ##

W3C standards that describe vocabularies (including ontologies) also have implementation reports.  In some cases, using the vocabularies may be facilitated by applications that do some sort of processing.  In such cases, the implementation reports will be similar to those of specifications that apply to applications that generate, consume, or transmit data.  In other cases, the vocabularies may organize information by providing descriptive terms without requiring applications to perform vocabulary-specific processing.  In those cases, an implementation report may list the usage of vocabulary terms in other vocabularies or implementations.  

Examples:

SKOS ([Simple Knowledge Organization System](https://www.w3.org/TR/skos-reference/)) is a W3C vocabulary that is used to share and link knowledge organization systems across the web.  A description of submitted use cases and their relationship to the requirements set for SKOS is reported [here](https://www.w3.org/TR/skos-ucr/). The call for use cases, including the questionnaire used to gather information is [here](http://lists.w3.org/Archives/Public/public-swd-wg/2006Dec/0036.html).  The SKOS Implementation Report primarily shows which terms were used in reported vocabularies and implementations.  However, there were also examples of applications for editing and converting data, and Web services that served data in SKOS.  Implementation reports for these applications and services were textual rather than a listing of the results of a particular test suite.

[PROV](https://www.w3.org/TR/prov-overview/), a W3C Recommendation for recording provenance, is a suite of documents describing a data model, OWL ontology, XML schema, constraints, etc.  Its use is primarily descriptive, although the variety of forms in which its model can be serialized means that developers will write applications to consume, process, and convert its various forms.  The set of use cases proposed and the actions taken upon them are listed [here](https://www.w3.org/2005/Incubator/prov/wiki/Use_Cases).  The implementation report [here](https://www.w3.org/TR/prov-implementations/) contains several parts: a table showing vocabularies that use PROV terms (broken down by term), datasets that use PROV terms (broken down by term), applications that validate or check PROV data (broken down by constraint), and applications that can generate or consume (or both) PROV data (broken down by term).  There is also a section showing implementations that exchange PROV data and the terms included in those data.  

## Application Profiles ##

Application profiles consist of "a set of metadata elements, policies, and guidelines defined for a particular application" ([Wikipedia](https://en.wikipedia.org/wiki/Application_profile)).   Although an application profile can be constructed based on any vocabulary, Dublin Core is a common basis for application profiles.  DCMI publishes [guidelines](http://dublincore.org/documents/profile-guidelines/) for creating Dublin Core Application Profiles.  The DCMI framework for application profiles assumes a ["Description Set Profile"](http://dublincore.org/documents/dc-dsp/) (describing a metadata record in detail) that is built on a community-developed domain model, but that is also based on the [DCMI Abstract Model](http://dublincore.org/documents/2007/06/04/abstract-model/).  Although well known, the DCMI Abstract Model assumes certain features such as "vocabulary encoding schemes" and "syntax encoding schemes" that are used to impart additional meaning to literals.  Although these features don't seem to have been widely implemented, overall the DCMI Abstract Model was developed to be compatible with vanilla RDF.  Since the encoding scheme designations are optional, an application profile could be built according to the DCMI guidelines and play well in the generic RDF world.  

Because a DCMI Application Profile is built on a consensus domain model and includes guidelines for syntax and data formats, it can facilitate data transfer and aggregation with a high degree of fidelity.  Usage guidelines are also an important component of an application profile.  They allow a human user to better understand the nature of the information included in the description set profile.  

Application profiles may include Dublin Core terms, but generally they "adopt" terms from any vocabularies that contain the necessary terms.  

Several application profiles have been created by groups under the auspices of DCMI.  The [Dublin Core Collections Application Profile](http://dublincore.org/groups/collections/collection-application-profile/) describes collections-level metadata.  The proposed [Library Application Profile](http://dublincore.org/documents/library-application-profile/) clarifies the use of Dublin Core terms in libraries and library-related applications and projects.

DCMI doesn't specify any particular process for accumulating use cases or implementation reports  during the development of application profiles.  It does assume that the needs of particular communities will be considered and that application profiles will be developed by a team with specialized knowledge of the resources that need to be described.

In the TDWG realm, [Apple Core](https://github.com/tdwg/applecore) (see also [this](https://code.google.com/archive/p/applecore/wikis)) could be considered an application profile built on Darwin Core.

## Peter Ansell's comments on Implementation Reports ##

Here's the text of a comment made by Peter Ansell in response to a [request for feedback](https://github.com/tdwg/vocab/issues/16) on the proposed requirement that Implementation Reports be required for "semantic layer" additions to TDWG vocabularies:

>Testsuites are most often used for operation results or transformations between formats, but they can also be useful for testing contract variation for APIs. Each vocabulary is effectively an API and hence could have contract tests executed to verify that changes maintain existing required behaviour.

>At another level, simply testing that the machine readable versions of vocabularies are all syntactically correct after changes can be valuable if it is automated, say using TravisCI. I have done some work with that using the sesame-vocab-builder project in the past:

https://github.com/tkurz/sesame-vocab-builder

...

>There may be some confusion in the current structure and terminology used for Section 4 due to the use of the work Implementation Report to denote an officially created document and not a user-submitted test report as it does at the W3C.

>It may be better to relabel Section 4 "User Feedback Report", or something clearer than that, and relocate the procedures that users need to follow to submit their test reports (compliance reports may be a clearer term than test reports) into a separate section. That may make it simpler to distinguish the steps for users to give feedback from the procedures that the TDWG vocabulary editors will follow to compile the aggregated report on how the change affects current implementations.

...

>In the case of the W3C with the RDF specs, having the test specifications available in a git repository as machine readable and executable documents makes it simple for implementors to pick up new changes and rerun their testsuites to either verify they still comply, or get an indication of which areas they are failing in. The format for the test manifests is still fairly ad-hoc and could be improved on, but the general concept of a machine readable manifest that contains executable test cases is valuable in my experience:

http://www.w3.org/2001/sw/DataAccess/tests/test-manifest#

>The user test reports for the W3C tests are also submitted as machine readable documents, using the EARL/DOAP/FOAF vocabularies so they can be aggregated by automated tools to generate implementation reports, which then could be stored near the manifests, so users could examine what other systems achieved when implementing/testing their own versions, as not every report will indicate 100% compliance.

https://www.w3.org/TR/EARL10-Schema/

https://www.w3.org/ns/earl

http://usefulinc.com/ns/doap#

http://xmlns.com/foaf/0.1/

>A change request should also be allowed to deprecate any existing testd, which can be flagged in the manifest without removing the test cases, so the deprecated tests can be made not to fail a testsuite after an update. The details about why the test case is being deprecated would be included along with the change request goals/aims.

>In my experience, it isn't valuable for long term specifications to allow performance figures to be included in compliance reports, as they may distract from the core information about whether the system actually includes the feature or not and they are not easy to formalise. However, if you feel it is necessary, there could be a comments section for severe regression cases where users could give feedback about features that couldn't be implemented efficiently.

>It isn't strictly necessary for a change request to just refer to a single feature change, but it definitely helps. It is simpler when deciding to approve changes and deciding when to ask for user feedback if the smallest relevant logical unit is the entire subject of a change request. If the suggestions are so broad that they refer to a large number of terms and a large number of existing test cases, then the suggestion is likely too big and may need splitting up. The smallest relevant logical unit doesn't need to be a single vocabulary term, and probably doesn't need to be exactly specified as it is a subjective concept just used to explain to users why their large set of changes need to be split up to be reviewed effectively.

>Overall, the goal of user feedback reports is to reduce the frequency of negative reponses to changes after the fact, that could have been identified before approving a change, not to prevent all possible negative responses in future, and the current text seems to be aligned with that goal.

## Some thoughts on the application of this material to vocabulary management ##

Because the Vocabulary Management Specification that we are developing relates specifically to vocabularies and not necessarily to the development of specifications to be followed by developers of applications, the examples listed for SKOS and PROV are probably the most relevant.  Compiling use cases (or competency questions) early in the process in order to determine the important requirements of the vocabulary enhancement is probably important.  Reporting on implementation experience is most likely to include reporting on which terms and features were used as parts of vocabularies or used within datasets, rather than reporting on the performance of applications on test suites to determine the features that were successfully implemented.  However, there may be cases where running particular application tests might be important.  It probably should be left to the developing group to determine whether such cases exist for a particular vocabulary enhancement.

In the case of application profiles, developers are likely to program validators or software to generate or convert data into a form compliant with the application profile.  In that situation, developing a test suite for applications might be valuable.

The system of machine-readable test suites and reports would be an efficient way of handling implementation testing, but it's probably something that should be worked out outside of the actual Vocabulary Management specification.  It seems like a more generic description of responsibilities for testing and compiling implementation reports would be adequate at the level of the TDWG standard.
