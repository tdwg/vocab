# TDWG Standards Documentation Specification #

**Title:** TDWG Standards Documentation Specification

**Date Issued:** 

**Date Modified:** 

**Contributors:** Steve Baskauf (TDWG Vocabulary Maintenance Task Group), Roger Hyam (TDWG Infrastructure Project)


**Abstract:** This document defines how TDWG standards should be presented. 

**Legal:** This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by the Taxonomic Databases Working Group.

**Part of TDWG Standard:**

Creator: TDWG Vocabulary Maintenance Specification Task Group

### Table of Contents ###

[generate when complete]

**1 Motivation**

TDWG standards include definitive (normative) and informative (non-normative) components that are expressed in human- and machine-readable documents. This standard specifies how these documents should be presented.

**2 Rationale**

[existing text - evaluate]
Users see a standard as a single 'product'. It is therefore important
that, although TDWG standards may contain multiple files, they are
presented to the user as a single entity and can be downloaded as a
single archive. File names need to be tightly constrained to be robust
across multiple environments. A Cover Page is required for all standards
to supply a uniform metadata interface. [requirements for machine processing]

**3 Parts of standards**

[work on wording of this] The normative and non-normative parts of standards should be clearly labeled as such.  If a single document contains both normative and non-normative content, material in a single section should be of a single type. 

**4 Contents of Standards**

[evaluate]
At a minimum, each standard must contain:

-   the normative (prescriptive) form of the standard itself (e.g., an
    XML Schema or human readable text); and
-   a 'Cover Page' document that summarizes the content of the standard [what does this mean in the current context of GitHub, the TDWG website, etc.?]
    (see below).

A standard should also contain information on:

-   the 'Motivation' for the existence of the standard; and
-   the 'Rationale' for why the standard takes the form it does.

Standards may contain any number of files provided they are of an
appropriate format (see below).

**5 Packaging of Standards**

[evaluate this.  How does this concept of the standard as a "bundle" fit in with our experience in trying to "package up" frozen versions of Darwin Core and Audubon Core that actually "live" as web or wiki pages? This probably needs to be re-thought in the context of version control and GitHub repos.  Maybe it makes more sense to consider a packaged standard as a frozen release in some version control system.]

Standards take the form of a logical folder or directory, but may be
distributed as a zip or tar archive file. The name of the archive must
be the file name of the standard followed by a period and the
appropriate suffix if the standard is compressed.

**6 Naming of Standards**


Every standard must have two names, a full name and a file name.

The **full name** is used in the cover page and as the title of the main
document if it is human readable. The full name must be in English and
must be unique within the scope of TDWG standards, but otherwise is not
controlled and may contain any combination of characters.

[This does not seem to have been followed at all. The OJS system assigns numbers that seem entirely meaningless, so when the archived packages are downloaded there is no relationship between the file names and the standard names.]
The **file name** should be created as a shortened version of the full
name and is used for the logical folder or directory and any
distribution archive. Rules for constructing file names are given below.
The file name must also be unique among TDWG standards.

**7 File Naming**


The following rules govern file names used in standards and for
standards archives:

-   File names must start with ‘tdwg\_’ followed by a shortened version
    of the full name of the standard.
-   File names must consist of only lowercase letters, numbers,
    underscores and hyphens.
-   File names must not contain spaces (replace with underscore).
-   File names must not contain non ASCII characters.
-   File names must not contain periods other than the one used to
    separate the suffix.
-   Suffix should be the commonly used suffix for file type and the
    three letter version where possible; for example, jpg rather than
    jpeg and xsl rather than xslt. [Does this really matter? I thought .html was actually preferred over .htm now.]

**8 Versioning of Standards**

[replace with a description of the version model]

**9 File Formats**


For archival reasons all files in a standard must be in an open format
for which parsers are commonly available. For this purpose an open
format is defined as being one for which it would be possible to write a
parser on the basis of a published specification without having to rely
on code libraries for which the source code is not available or to pay a
license fee. 



**10 Referencing of Standards**

[This needs to be re-written in light of the hierarchy model. Replace use of URI with IRI.]
Each standard must have the following URIs (Uniform Resource
Identifiers)

-   A URI for the standard itself. This must resolve to human readable
    rendering of the information in the standard's cover page.
-   A URI that resolves to an archive file containing all the files in
    the standard. [I don't think this should be a requirement.  Let the cover page contain a link to the archive file, whose URL may change.]
-   A URI for each of the files within the standard. [Currently this is not followed - some files are only obtainable in the zip that's downloaded.]

The URIs are issued as part of the standards process by the
administrator of the standards repository and remain constant from the
point at which they are issued.

Some standards may involve technologies that make use of XML namespaces.
The URIs of the standard and its constituent parts should not be used
for this purpose. TDWG provides a facility for reserving URIs associated
with namespaces with the base namespace http://rs.tdwg.org/.  [what is the significance of this in the current landscape?]

**11 Human Readable Documents**


This section specifies the layout and style that should be followed for
any human readable documents that make up part of a TDWG standard. Normative human readable documents should be in XHTML format. [do we still care about XHTML vs. other flavors of HTML?]
Documents should be divided into three main sections:

-   A header section
-   Table of contents
-   A body section

**11.1 Header Section**

This section must contain the following parts:

**Title:** The official title of the document.

**Date Issued:** The date of initial publication in ISO 8601 Date format. 

**Date Modified:** Date of this version.

**Abstract:** A single paragraph summary of the document.

**Contributors:** A list of the people who are responsible for the
document's creation. The first person in the list should be the
principal contact.

**Legal:** A reference or link to a document containing the Copyright,
Licensing and Disclaimer statements that govern this document. This will
usually be the standard one supplied by TDWG.

**Part of TDWG Standard:** The IRI of the standard this document belongs
to. The IRI should dereference to the standard cover page.

Contributors’ names must be quoted in the following format: "FirstName
Initials LastName (Affiliation)" where:

Either one or both of FirstName and Initials must be present.

Affiliation is the organisation or group the contributor is working with
in relation to this document and is OPTIONAL.

Examples:

-   Roger D. Hyam (TDWG)
-   Roger Hyam (TDWG Infrastructure Project) 
-   R. Hyam 
   
**11.2 Table of Contents Section**

The table of contents section should contain an ordered list of all the
headings (along with their numbers) that occur in the body section and
nothing else. The items in the list should be hypertext links to the
headings in the body.

**11.3 Body Section**

The body text should be divided by a hierarchy of subheadings. The
subheadings must be numbered consecutively using simple decimal system.
The final number must not be followed by a decimal point. [What is the advantage of no final decimal point?  Is this practice followed elsewhere?] An example:

1 First Main Section

1.1 First subsection within first main section.

1.12.5 The fifth sub-subsection within the twelfth subsection of the
first section.

2 Second Main Section

**12 Language**


All normative content must be in English. Translations of
normative documents may be included in the standard but the translations
must be treated as informative documents. 

**12.1 Linguistic Style**

Text should be written with the assumption that it will be read from the
screen rather than paper. [should more be said here about the style of normative sections vs. examples, diagrams, etc. that might be in non-normative sections?]

**12.2 Key Words Governing Compliance**

[we need to spell out the circumstances under which RFC 2119 keywords are appropriate]
This policy is specified in RFC 2119 (http://www.ietf.org/rfc/rfc2119.txt).

**13 Cover Page Contents**


This section specifies content for the Cover Page documents that must be
contained in all TDWG standards. The table below shows the components
that must be contained in the cover page of all TDWG standards. These
are based on a subset of the Dublin Core metadata initiative elements
and terms.

Table 2: Fields for Cover Page documents.


|**Name**      |           **Notes**|
|---------------|----------------|
| Title                   | **Required** The official TDWG title for the standard (see above)|
| Description      |        **Required** A brief (&lt;=250 words) description of the standard|
| Subject             |     **Required** Key words, key phrases and classification codes that describe the topic covered by the standard.|
| Creator           |       **Required** The primary author of the standard following the conventions outlined above. Should only occur once.|
| Contributor      |        A contributor to the standard following the conventions outlined above. This assertion may be repeated.|
|  Date Modified    |        The date the standard was last modified. Will be prior to Date Accepted if that is present.|
|  Date Accepted       |     **Required for accepted standards** The date the standard was officially ratified by TDWG and fixed. If a modified date is present it must be prior to this date.|
|  Identifier      |         The GUID of the standard.|
|  Publisher            |    **Required** Should always contain the text "Biodiversity Information Standards TDWG."|
|  Rights          |         **Required** One or more URLs linking to documents describing the copyright, licensing provisions and disclaimers associated with the standard. Typically this will be contained within another TDWG standard. (see Legal Statements below)|
|  Access Rights        |    **Required** Should always contain the single word 'public'. All TDWG standards should be freely accessible to all via the Internet.|
| Bibliographic Citation  | **Required** How this standard should be cited.|
|  Has Part           |      **Required** The full URL to a file within the standard. This assertion should be repeated for each file within the standard (other than cover.xml itself).|
| Replaced By             | **Required if this standard has been replaced by another.** If the standard has been replaced then this assertion should be present and contain the full URL to the new standard.|
| Replaces          |       **Required if this standard replaces another.** If this standard replaces a previous one then this assertion should be present and contain the full URI of the standard replaced.|


**14 Legal Statements**


TDWG standards must contain explicit statements of copyright (the
assertion of intellectual property rights), the licensing provisions for
the standard, and a disclaimer of liability. This section defines the
texts that should be included in TDWG standards and actions that should
be taken if these texts are deemed not to be suitable for a particular
standard.

**14.1 Copyright**

The usual practice will be for participants in TDWG activities to
contribute their intellectual works to TDWG freely, and to combine them
with the contributions of others to create a TDWG standard. TDWG
strongly recommends that TDWG standards be placed under TDWG copyright.

The following copyright notice should be included in all TDWG documents

Copyright © TDWG *(year)*. All Rights Reserved.

**14.2 Licensing Provisions**

TDWG intends its standards to be used as broadly as possible and should
impose no royalties or licensing fees for their use. TDWG will normally
publish its standards under the Creative Commons Attribution (CC BY)
license. Under this license users may copy, completely or in part, or
create derivative works for any purpose, whether commercial or public
benefit, subject only to the requirement that the original standard must
be cited.



**14.3 Disclaimer**

The following text must be included or referenced in all TDWG standards
documents:

Disclaimer: This document and the information contained herein are
provided on an "AS IS" basis. TDWG MAKES NO WARRANTIES REGARDING THE
INFORMATION PROVIDED, AND DISCLAIMS LIABILITY FOR DAMAGES RESULTING FROM
ITS USE.



**14.5 Departure from Usual Practice**

If the participants in a TDWG activity intend to depart from the legal
framework provided above, the alternative statements of intellectual
property rights and licensing must be described fully in the charter of
that activity as well as the standard itself. [should this be here?]

[Somewhere here we should specify the preferred citation  format for the document.]