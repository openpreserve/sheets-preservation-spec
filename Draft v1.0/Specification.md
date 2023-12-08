# Spreadsheets Preservation Specification

**Draft v1.9, December 2023**

## Table of Contents

## Introduction

This document describes the considerations to make when digitally preserving data created in a spreadsheet file format.
This document specifies the usage of ODF 1.3 as the chosen format for the archiving of spreadsheets.
See <https://docs.oasis-open.org/office/OpenDocument/v1.3/os/part1-introduction/OpenDocument-v1.3-os-part1-introduction.html>

The document is formalized as a specification to be used in Archival Information Packages (AIP), ideally in parallel with bit preservation of the original data. The migration of spreadsheet data should not be conducted prior to appraisal and technical analysis to ensure data loss is reduced to a minimum and any incurred is acceptable.

The specification should be supported by software tools to automatically process the conversion and validation of spreadsheets to comply with this specification.

## Declarations

### Aim

The specification is intended to define a concise and general approach to the testing of data saved in spreadsheet file formats.
Scope

### Scope

The specification defines file formats and data quality suitable for an Archival Information Package (AIP). The specification may be adopted by any preservation institution, which ingests spreadsheets and maintains a migration strategy.

### Licence

The specification is released under Creative Commons Attribution-ShareAlike 4.0 International Public Licence.
You are not free to release any specification which uses the Open Preservation Foundation name or branding. The rights to the Open Preservation Foundation name and branding belongs to the Open Preservation Foundation.

## File Format Policies

There are two classes of checks defined, Validation and Policy as follows:

* **Validation:** These checks ensure that a spreadsheet is well-formed and valid as per the [ODF 1.3 specification](https://docs.oasis-open.org/office/OpenDocument/v1.3/os/part1-introduction/OpenDocument-v1.3-os-part1-introduction.html). The validation process comprises other multiple checks taken directory from the ODF 1.3 standard.
* **Policy:** These checks are beyond the scope of the ODF specification validation. They flag features/properties of ODF documents that do not comply with an institution's preservation policies. Examples include the use of formula, macros, embedded objects, etc.

The importance of this division is that Validation checks MUST always be applied, whilst the choice Policy checks is left to individual institutions.

The normal standard for evaluating file format policies is usually done in accordance with the following levels of requirements adopted from Key words for use in RFCs to Indicate Requirement Levels (Bradner, 1997):

* ERROR is equal to **MUST**/**MUST NOT** conformance
* WARNING is equal to **SHOULD**/**SHOULD NOT** conformance
* INFO is equal to **MAY** conformance

## OpenDocument Validation

Note that we are validating to show conformance to ODF 1.3 See <https://docs.oasis-open.org/office/OpenDocument/v1.3/os/part1-introduction/OpenDocument-v1.3-os-part1-introduction.html>.

The items given below are easily recognizable from this ODF 1.3 standard. This does not include ODF extended package format, encryption, digital signatures or sub documents.

### Package

OpenDocument defines a package file to store the XML content of a document as separate parts together with associated binary data as file entries in a single package file. These file entries may be compressed to further reduce the storage taken by the package. This package is a Zip file. OpenDocument Packages impose additional structure on the Zip file to accomplish the representation of OpenDocument Format documents.

The definitions here come from the OpenDocument specfications that use alternative normative terminology. The table below maps the terms used in the OpenDocument specification to the terms used in this specification, the original wording is retained.

| Error Level | RFC Term | ODF Term |
|-------------|----------|----------|
| ERROR | MUST/MUST NOT | SHALL/SHALL NOT |
| WARNING | SHOULD/SHOULD NOT | SHOULD/SHOULD NOT |
| ERROR | MAY | MAY |

| Ref | Description |
|-----|-------------|
| PKG-1 | An OpenDocument Package SHALL be a Zip file as defined in PKWARE Inc. Zip APPNOTE Version 6.2.0, <http://www.pkware.com/support/application-note-archives>, 2004 |
| PKG-2 | All files contained in the Zip file SHALL be non compressed (STORED) or compressed using the “deflate” (DEFLATED) algorithm |
| PKG-3 | An OpenDocument Package SHALL contain a file “META-INF/manifest.xml”. |
| PKG-4 | It SHOULD contain a file “mimetype”. |
| PKG-5 | It SHALL not contain other files whose relative path begins with “META-INF/” other than manifest.xml. This is a property of extend packages which is not permitted. |
| PKG-7 | Unless a document is encrypted, package producers SHOULD generate a preview image of the document that is contained in the package. It should be a representation of the first page, first sheet, etc. of the document. For maximum re-usability of the preview images they shall be generated without any effects, surrounding frames, or borders. The preview image shall be contained in a file named “Thumbnails/thumbnail.png”. |
| PKG-8 | Encrypted file entries SHALL be flagged as "STORED" rather than "DEFLATED" in the zip file's central directory. |

### Manifest

All OpenDocument Packages SHALL contain a file named “META-INF/manifest.xml”. This file is the OpenDocument Package manifest. The manifest provides:

* A list of all of the files in the package (except those specifically excluded from the manifest).
* The MIME media type of each file in the package.
* If a file is stored in the file data in encrypted form, the manifest provides information required to decrypt the file correctly when the encryption key is also supplied.

| Ref | Description |
|-----|-------------|
| MAN-1 | The manifest MUST contain an file entry for every zip entry in the package. A zip entry has no corresponding manifest file entry. For all files contained in a package, with exception of the “mimetype” file and files whose relative path starts with “META-INF/”, the “META-INF/manifest.xml” file SHALL contain exactly one <manifest:file-entry> element whose manifest:full-path attribute's value references the file. |
| MAN-2 | An OpenDocument Package manifest SHALL NOT contain a file entry for itself. The file SHALL NOT contain <manifest:file-entry> elements whose manifest:full-path attribute value references the “META-INF/manifest.xml” file itself. |
| MAN-3 | An OpenDocument Package manifest SHALL NOT contain a file entry the mimetype file. The file SHALL NOT contain <manifest:file-entry> elements whose manifest:full-path attribute value references the “mimetype” file. |
| MAN-4 | An OpenDocument Package's zip archive SHALL contain an zip entry for every file entry in the package's "META-INF/manifest.xml" manifest file. A manifest file entry has no corresponding zip entry. For all files contained in a package, with exception of the “mimetype” file and files whose relative path starts with “META-INF/”, the “META-INF/manifest.xml” file SHALL contain exactly one <manifest:file-entry> element whose manifest:full-path attribute's value references the file |
| MAN-5 | An OpenDocument Package manifest SHALL contain a <manifest:file-entry> element whose manifest:full-path attribute has the value \"/\" if a mimetype file is present. |
| MAN-6 | The OpenDocument Package manifest NEED NOT contain entries for file paths starting with "META-INF/". |
| MAN-7 | An OpenDocument Package SHOULD contain a <manifest:file-entry> element whose manifest:full-path attribute has the value "/". |
| MAN-8 | For directories, the manifest file SHOULD contain a <manifest:file-entry> element only if a directory contains a document or a sub document. |
| MAN-9 | A directory for administrative or convenience purposes, such as a directory that contains various unrelated image files, SHOULD NOT have an entry in the manifest file. |

### MIME Media Type

If a MIME media type for a document exists, then an OpenDocument Package SHOULD contain a file with name `mimetype`.

| Ref | Description |
|-----|-------------|
| MIM-1 | The `mimetype` file SHALL be the first file of the zip file. |
| MIM-2 | It SHALL NOT be compressed. |
| MIM-3 | It SHALL NOT use an "Extra field" in the header. See <https://users.cs.jmu.edu/buchhofp/forensics/formats/pkzip.html#localheader>. |
| MIM-4 | An OpenDocument Package SHALL contain a mimetype file IF the manifest contains a `<manifest:file-entry>` element whose `manifest:full-path` attribute has the value "\". |
| MIM-5 | An OpenDocument Package mimetype file content SHALL be equal to the `manifest:media-type` attribute of the manifest `<manifest:file-entry>` element whose manifest:full-path attribute has the value "/".
| MIM-6 | The content of this file SHALL be the ASCII encoded MIME media type associated with the document. See [RFC6838]. |

### XML Content

Much of OpenDocument valdiation is a process of matching package entry filenames to appropriate XML schema. This section details the errors given when XML content is not well formed or does not validate against the appropriate schema. Full details can be found in [Section 2.2 of the ODF specification v1.3 part 3](https://docs.oasis-open.org/office/OpenDocument/v1.3/os/part3-schema/OpenDocument-v1.3-os-part3-schema.html#a_2_2_1_OpenDocument_Document). The text below is paraphrased from the standard.

Essentially an OpenDocument Package SHALL contain at least one of the following files: content.xml and styles.xml. It may contain additional files.

If the document is an OpenDocument Package, then the following requirements SHALL be met for files named content.xml, styles.xml, settings.xml, meta.xml, and manifest.xml if present:

* The files SHALL be well-formed XML documents with respect to the XML 1.0 specification.
* The XML root elements of the files SHALL be:
  * `<office:document-content>`, or `<math:math>` for files named content.xml,
  * `<office:document-styles>` for files named styles.xml,
  * `<office:document-meta>` for files named meta.xml,
  * `<office:document-settings>` for files named settings.xml.
  * `<manifest:manifest>` for files named manifest.xml.

If the XML root element of a file is `<office:document-content>`, `<office:document-styles>`, `<office:document-meta>`, `<office:document-settings>`, `<math:math>`, or `<manifest:manifest>`, then the XML file SHALL be valid with respect to the appropriate schema.

| Ref | Description |
|-----|-------------|
| XML-1 | SaxException: `<message>`. This indicates the occurence of an XML parsing error. The error message will be appended to the header and more details given in the sub-message. |
| XML-2 | Root element of XML file %s, MUST be %s but found value %s. This message is triggered when a packages file names and root elements do not comply with the rules in the list above. |
| XML-3 | Not a well formed XML document. XML parsing exception at line `<x>` and column `y`: `<message>`. This error is triggered when one of the OpenDocument XML files isn't well formed. This could be considered a parsing error. |
| XML-4 | Not a valid XML document. Validation exception at line `<x>` and column `<y>`: `<message>`. This message indicates an XML validation error when the document was checked against the appropriate schema. |

## OpenDocument Spreadsheet Policy Checks

This specification defines the file format policies. The policies do not specify which tools to use to obtain compliance with the file format policies.

| ID | Name | Description |
| --- | --- | --- |
| POL_1 | Encryption | The file **MUST NOT** be encrypted, either using a password or a GPG key. |
| POL_2 | Standard compliance | The file **MUST** comply with the standard “OASIS Open Document Format for Office Applications (OpenDocument) v1.3”. Note that an ODF 1.3 extended package is not permitted. |
| POL_3 | Package mimetype entry | An ODF package **MUST** have a `mimetype` entry as specified in the [Section 3.3 of the ODF specification v1.3](https://docs.oasis-open.org/office/OpenDocument/v1.3/os/part2-packages/OpenDocument-v1.3-os-part2-packages.html#__RefHeading__752809_826425813). A MIME type declaration is required in the first line of the file "mimetype" and an entry in the file "\META-INF\manifest.xml" |
| POL_4 | Extension & MIME type | The file **MUST** have the matching extension and MIME type pairs. MIME type: application/vnd.oasis.opendocument.spreadsheet", Extension: ".ods". |
| POL_5 | External data | The package **MAY** have any references to external data. This includes data connections, RealTimeData functions, cell formula references and objects. Any external data references such as data connections, RTD functions, cell references or objects **MAY** be removed, however the calculated cell value **MUST** be preserved. |
| POL_6 | Embedded objects | Embedded files **MAY** be present in the the spreadsheet OpenDocument package. |
| POL_7 | Content | The package **MUST** have values or objects in at least one cell. It is quite possible that some cell values in a spreadsheet are missing.  This is not considered an error. |
| POL_8 | Macros | The package **MUST NOT** contain any macros. |
| POL_9 | Signatures | The package **MUST NOT** contain any digital signatures. |

## Appendix A: Editing and Rendering

**Table 14. Software for editing and rendering spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| Apache OpenOffice Calc | The application uses OpenDocument by default but you can also open and edit Excel file formats and Apple NUMBERS. | Linux, macOS, Windows | Free to use |
| Aspose.Cells | An online platform for editing viewing and many other features. | Browser | Free to use |
| Calligra Sheets | The application uses OpenDocument by default but you can also open and edit Excel and several other file formats. | Linux macOS, WIndows | GPL-2.0 |
| Gnumeric | The application uses its own file format Gnumeric XML by default but you can also open and edit Excel file formats and OpenDocument. | Linux, Windows | GPL-2.0 or GPL-3.0 |
| LibreOffice Calc | The application uses OpenDocument by default but you can also open and edit Excel file formats and Apple NUMBERS. | Linux, macOS, Windows | Mozilla Public 2.0 |
| Microsoft Excel | The application uses Office Open XML file formats by default but you can also open and edit OpenDocument file formats. | Browser, macOS, Windows | Commercial |
| ONLYOFFICE Spreadsheet Editor | The application uses Office Open XML file formats by default but you can also open and edit OpenDocument file formats. | Android, browser, iOS, Linux, macOS, Windows | Free to use |

## Glossary

Table with terms used in the specification.

**Table 15. Glossary**

| Term | Description |
| --- | --- |
| **Archival Information Package (AIP)** | *From OAIS:* An Information Package, consisting of the Content Information and the associated Preservation Description Information (PDI), which is preserved within an OAIS. |
| **Appraisal** | A preservation assessment to determine whether or not the data should be preserved. |
| **Artefact** | An artefact is a spreadsheet property not considered significant for long-term preservation and future reuse. While preserving artefacts are unnecessary, removing them may also be considered a preservation risk. It is safe to ignore artefacts when migrating between formats and representations. |
| **Cell** | A spreadsheet consists of sheets, which consist of cells. The cell is the minimal structure for storing computational data in a spreadsheet. A cell has an address composed of the column and row ids i.e. A1 is the address of the first cell on a sheet, and is composed of column A and row 1. |
| **Compliance** | In this context, compliance means to abide by any requirement set in a specification or standard. |
| **Conformance** | Conformance is any defined differentiation in a specification. This means the number or definition of requirements of the specification may be stricter at one conformance level over another conformance level. |
| **CSV** | Abbreviation of Comma-separated values. File format used to data exchange of datasets with tabular data. |
| **Data connections** | Data connections in a spreadsheet is a type of connection, which can connect to an external database or file to feed and update cell values. |
| **Designated community** | *From OAIS:* An identified group of potential Consumers who should be able to understand a particular set of information. The Designated Community may be composed of multiple user communities. A Designated Community is defined by the Archive and this definition may change over time. |
| **Embedded objects** | An object embedded in the file/package i.e. an image, another spreadsheet or 3D object. |
| **Encryption** | An ODF document may encrypt some of it's internal file entries using either a password or GPG key. The password or matching key MUST be supplied to decrypt these entries. |
| **External cell references** | External cell references is a type of cell formula, which fetches data from another spreadsheet. |
| **External objects** | An object that is linked as an OLE object, but is not embedded into the file/package. |
| **File format** | *From Digital Preservation Handbook:* A file format is a standard way that information is encoded for storage in a computer file. It tells the computer how to display, print, and process, and save the information. It is dictated by the application program which created the file, and the operating system under which it was created and stored. Some file formats are designed for very particular types of data, others can act as a container for different types. A particular file format is often indicated by a file name extension containing three or four letters that identify the format. |
| **File format extension** | A file format extension is an identifier set at the end of the filename and delimited by a dot/period e.g. ".ods" or ".xlsx". The identifier helps the operating system to associate an application for opening the file. |
| **File format signature** | A file format signature is a unique combination of bits, which identifies a specific file format. The signature, also called a "magic number", authoritatively identifies a file's format. |
| **Macros** | A sequence of code, which the spreadsheet can execute. This code may change data in the spreadsheet or the operating system. |
| **OAIS** | The Reference Model for an Open Archival Information System, ISO 14721 |
| **Office Open XML (OOXML)** | Office Open XML ECMA- and ISO-standard. |
| **OpenDocument Spreadsheets (ODS)** | OpenDocument Spreadsheet subset of the OpenDocument ISO-standard. |
| **RealTimeData functions (RTD)** | RealTimeData functions is a type of cell formula in an OOXML spreadsheet, which can fetch data from a server in a specified interval. |
| **Sheets** | A spreadsheet MUST contain at least one sheet but may contain a large number of sheets. Sheets are the “pages” of a spreadsheet, and any cell exists in a sheet. Sheets are the structural wrapper of spreadsheet data. |
| **Significant properties** | Significant properties are the properties of data, which a designated community has deemed important to preserve for future reuse of data. A significant property is also termed a “Transformational Information Property” in the OAIS. |
| **Validation** | Validation is the act of confirming something, and in this context a spreadsheet, conforms to the regulations specified in a document, typically referred to as a standard. Validation results in either an approval or a disapproval of any data property or attribute according to a chosen conformance level.<br><br>Validation processes should be supported by software to automate the process, but validation may involve manual inspection of the data. |

## References

The following is a complete list of references used in the specification.

*Creative Commons Attribution-ShareAlike 4.0 International Public License*
URL: <https://creativecommons.org/licenses/by-sa/4.0/legalcode>

Bradner, S. (1997): *Key words for use in RFCs to Indicate Requirement Levels*, Harvard University
URL: <https://www.ietf.org/rfc/rfc2119.txt>

*Open Document Format for Office Applications (OpenDocument) v1.3*. 2020. OASIS. Parts:

* Part 1: Introduction
* Part 2: Packages
* Part 2: Open Document Schema
* Part 3: Recalculated Formula (OpenFormula) Format
* XML/RNG schemas and OWL ontologies

*Office Open XML File Formats*. ISO. Parts:

* ISO/IEC 29500-1:2016 - Part 1: Fundamentals and Markup Language Reference
* ISO/IEC 29500-2:2021 - Part 2: Open packaging conventions
* ISO/IEC 29500-3:2015 - Part 3: Markup Compatibility and Extensibility
* ISO/IEC 29500-4:2016 - Part 4: Transitional Migration Features

*Common Format and MIME Type for Comma-Separated Values (CSV) Files*. RFC 4180. 2005. The Internet Society
URL: <https://www.ietf.org/rfc/rfc4180.txt>

*The Reference Model for an Open Archival Information System (OAIS)*. 2012. CCSDS Secretariat

*The Significant Properties of Spreadsheets*. 2021. Open Preservation Foundation, Archives Interest Group.
URL: <https://zenodo.org/record/5468116#.Y_YMmXbMKUk>

## Postface

The following includes information about the authors and other publication info.

### Authors

Names of the persons, who wrote the first version of the specification.

**Table 16. Authors of this specification**

| Author | Organisation |
| --- | --- |
| Asbjørn Skødt | Danish National Archives |
| Remco van Veenendaal | National Archives of the Netherlands |
| Kaido Kivilaan | National Archives of Estonia |
| Martin Dew-Hattens | Danish National Archives |

### Acknowledgments

Thanks to Carl Wilson of the Open Preservation Foundation who acted as a reviewer.

This specification draws inspiration from and is a natural by-product of the Open Preservation Foundation’s discontinued Archives Interest Group (AIG), which in the years 2016-21 investigated the significant properties of spreadsheets. The group won the audience award for best poster at the international digital preservation conference iPRES in 2019 and published their work in a final report in 2021, which also was presented as a paper at iPRES the same year.
