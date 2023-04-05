# General
Open Preservation Foundation Spreadsheets Preservation Specification v1.0.

## Table of Contents
[1 Introduction](#1-introduction)
[2 Declarations](#2-declarations)
    * [2.1 Aim](#21-aim)
    * [2.2 Scope](#22-scope)
    * [2.3 Licence](#23-licence)
[3 Appraisal and Migration Paths](#3-appraisal-and-migration-paths)
[4 Postface](#4-postface)
    * [4.1 Authors](#41-authors)
    * [4.2 Acknowledgments](#42-acknowledgments)
[5 References](#5-references)

## 1 Introduction
This document describes the considerations to make when digitally preserving data created in a spreadsheet file format (i.e. .xlsx, .numbers, .ods).

The document is formalized as a specification to be used in Archival Information Packages (AIP), ideally in parallel with bit preservation of the original data. The migration of data should not be conducted prior to a careful appraisal and technical analysis to ensure data loss is reduced to a minimum and any incurred is acceptable within your organisation.

The specification should be supported by software tools to automatically process the conversion and validation of spreadsheets to comply with this specification.

## 2 Declarations

### 2.1 Aim
The specification is intended to define a concise and general approach to the preservation of data saved in spreadsheet file formats.

The specification defines recommended conversion paths to select file formats in order to reduce the probability of technological obsolescence and make your collections more manageable.

### 2.2 Scope
The specification defines file formats and data quality suitable for an Archival Information Package (AIP). The specification may be adopted by any preservation institution, which ingests spreadsheets and maintains a migration strategy.

### 2.3 Licence
The specification is released under Creative Commons Attribution-ShareAlike 4.0 International Public Licence.
You are not free to release any specification which uses the Open Preservation Foundation name or branding. The rights to the Open Preservation Foundation name and branding belongs to the Open Preservation Foundation.

## 3 Appraisal and Migration Paths
If a file format is not covered in the section “File Format Policies”, then this file format is not considered suitable as an AIP file format. In the case of converting to section "XXXX" and section "XXXX", an appraisal of the significant properties must be made prior to conversion to assess and document the possible data loss.

As mentioned in “2.2 Scope”, this specification does not specify which file formats to submit data to an organisation in. It is up to this institution to determine their policy for how data are submitted to them. However, this specification does specify which file formats may be used for archival storage of spreadsheets, potentially in parallel with bit preservation of an original master copy of the data.

The original master copy may be corrupt or password protected, and hence a migration copy for archival storage cannot be created. It is up to the receiving organisation to appraise, whether these master copies should be preserved or destroyed.

## 4 Postface
The following includes information about the authors and other publication info.

### 4.1 Authors
Names of the persons, who wrote the first version of the specification.

Table 10. Authors of v1.0 of this specification

| Author | Organisation |
| --- | --- |
| Asbjørn Skødt | Danish National Archives |
| Carl Wilson | Open Preservation Foundation |
| Remco van Veenendaal | National Archives of the Netherlands |
| Kaido Kivilaan | National Archives of Estonia |

### 4.2 Acknowledgments
This specification draws inspiration from and is a natural by-product of the Open Preservation Foundation’s discontinued Archives Interest Group (AIG), which in the years 2016-21 investigated the significant properties of spreadsheets. The group won the audience award for best poster at the international digital preservation conference iPRES in 2019 and published their work in a final report in 2021, which also was presented as a paper at iPRES the same year.

## 5 References
The following is a complete list of references used in the specification.

*Creative Commons Attribution-ShareAlike 4.0 International Public License*
URL: https://creativecommons.org/licenses/by-sa/4.0/legalcode

Bradner, S. (1997): *Key words for use in RFCs to Indicate Requirement Levels*, Harvard University
URL: https://www.ietf.org/rfc/rfc2119.txt

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
URL: https://www.ietf.org/rfc/rfc4180.txt

*The Reference Model for an Open Archival Information System (OAIS)*. 2012. CCSDS Secretariat

*The Significant Properties of Spreadsheets*. 2021. Open Preservation Foundation, Archives Interest Group.
URL: https://zenodo.org/record/5468116#.Y_YMmXbMKUk

