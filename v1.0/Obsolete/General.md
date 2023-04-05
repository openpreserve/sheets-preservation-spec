# General

Open Preservation Foundation Spreadsheets Preservation Specification v1.0.

## Table of Contents

* [1 Introduction](#1-introduction)
* [2 Declarations](#2-declarations)
    * [2.1 Aim](#21-aim)
    * [2.2 Scope](#22-scope)
    * [2.3 Licence](#23-licence)
* [3 Appraisal and Migration Paths](#3-appraisal-and-migration-paths)
* [4 Glossary](#4-glossary)
* [5 References](#5-references)
* [6 Postface](#6-postface)
    * [6.1 Authors](#61-authors)
    * [6.2 Acknowledgments](#62-acknowledgments)

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

## 4 Glossary

Table with terms used in the specification.

**Table 1. Glossary**

| Term | Description |
| --- | --- |
| Archival Information Package (AIP) | *From OAIS:* An Information Package, consisting of the Content Information and the associated Preservation Description Information (PDI), which is preserved within an OAIS. |
| Appraisal | A preservation assessment to determine whether or not the data should be preserved. |
| Cell | A spreadsheet consists of sheets, which consist of cells. The cell is the minimal structure for storing computational data in a spreadsheet. A cell has an address composed of the column and row ids i.e. A1 is the address of the first cell on a sheet, and is composed of column A and row 1. |
| Compliance | In this context, compliance means to abide by any requirement set in a specification or standard. |
| Conformance | Conformance is any defined differentiation in a specification. This means the number or definition of requirements of the specification may be stricter at one conformance level over another conformance level. |
| CSV | Abbreviation of Comma-separated values. File format used to data exchange of datasets with tabular data. |
| Data connections | Data connections in a spreadsheet is a type of connection, which can connect to an external database or file to feed and update cell values. |
| Designated community | *From OAIS:* An identified group of potential Consumers who should be able to understand a particular set of information. The Designated Community may be composed of multiple user communities. A Designated Community is defined by the Archive and this definition may change over time. |
| Embedded objects | An object embedded in the file/package i.e. an image, another spreadsheet or 3D object. |
| External cell references | External cell references is a type of cell formula, which fetches data from another spreadsheet. |
| External objects | An object that is linked as an OLE object, but is not embedded into the file/package. |
| Macros | A sequence of code, which the spreadsheet can execute. This code may change data in the spreadsheet or the operating system. |
| Mark-up language | A mark-up language is a structured and text-encoded model for annotating data. CSV and HTML are mark-up languages. |
| Migration path | The chosen output file format for an input file format in a data conversion process. The migration path should to do the widest possible extent preserve all the significant properties of the input file format. Methodical assessments are necessary to define acceptable migration paths. |
| OAIS | The Reference Model for an Open Archival Information System, ISO 14721 |
| Office Open XML (OOXML) | Office Open XML ECMA- and ISO-standard. |
| OpenDocument Spreadsheets (ODS) | OpenDocument Spreadsheet subset of the OpenDocument ISO-standard. |
| Printer settings | Printer settings contains information on registered printers available for printing. This may contain encrypted information about connecting to the printer. |
| Protection | A spreadsheet may have read and/or write protection on structure, sheets and/or cells, that may demand a password to enable reading and/or writing. |
| RealTimeData functions (RTD) | RealTimeData functions is a type of cell formula in an OOXML spreadsheet, which can fetch data from a server in a specified interval. |
| Sheets | A spreadsheet must contain at least one sheet but may contain a large number of sheets. Sheets are the “pages” of a spreadsheet, and any cell exists in a sheet. Sheets are the structural wrapper of spreadsheet data. |
| Significant properties | Significant properties are the properties of data, which a designated community has deemed important to preserve for future reuse of data. A significant property is also termed a “Transformational Information Property” in the OAIS. |
| Static file format | A static file format is typically an image file format or the PDF file format, which editable files are converted to. This may result in loss of significant properties and hence data quality. |
| Validation | Validation is the act of confirming something, and in this context a spreadsheet, conforms to the regulations specified in a document, typically referred to as a standard. Validation results in either an approval or a disapproval of any data property or attribute according to a chosen conformance level.<br><br>Validation processes should be supported by software to automate the process, but validation may involve manual inspection of the data. |

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

## 6 Postface

The following includes information about the authors and other publication info.

### 6.1 Authors

Names of the persons, who wrote the first version of the specification.

Table 10. Authors of v1.0 of this specification

| Author | Organisation |
| --- | --- |
| Asbjørn Skødt | Danish National Archives |
| Carl Wilson | Open Preservation Foundation |
| Remco van Veenendaal | National Archives of the Netherlands |
| Kaido Kivilaan | National Archives of Estonia |

### 6.2 Acknowledgments

This specification draws inspiration from and is a natural by-product of the Open Preservation Foundation’s discontinued Archives Interest Group (AIG), which in the years 2016-21 investigated the significant properties of spreadsheets. The group won the audience award for best poster at the international digital preservation conference iPRES in 2019 and published their work in a final report in 2021, which also was presented as a paper at iPRES the same year.