# File Format Policies

## Table of Contents
* [1 Introduction](#1-introduction)
* [2 Policies](#2-policies)
    * [2.1 OpenDocument Spreadsheets](#21-opendocument-spreadsheets)
    * [2.2 OfficeOpen XML SpreadsheetML](#22-office-open-xml-spreadsheetml)
    * [2.3 Mark-up Languages](#23-mark-up-languages)
    * [2.4 Static file formats](#24-static-file-formats)

## 1 Introduction
Each file format policy has a table with:
* ID is a unique identifier for the requirement
* Name is a short title for the requirement
* Description is the detailed explanation of the requirement including the level of conformance
* Cardinality is the detailing of occurrences of the requirement

The file format policies must be validated in accordance with the following levels of requirements adopted from Key words for use in RFCs to Indicate Requirement Levels (Bradner, 1997):
* ERROR is equal to **MUST**/**MUST NOT** conformance
* WARNING is equal to **SHOULD**/**SHOULD NOT** conformance
* INFO is equal to **MAY** conformance

## 2 Policies
The following subsections cover each file format policy.

### 2.1 OpenDocument Spreadsheets
The following table describes the requirements for data quality when preserving spreadsheets in OpenDocument Spreadsheets file format.

**Table 1. OpenDocument Spreadsheets requirements**

| ID | Name | Description |
| --- | --- | --- |
| ODS_1 | Password protection | The file **MUST NOT** have read or write password protection. |
| ODS_2 | Standard compliance | The file **MUST** comply with the standard “OASIS Open Document Format for Office Applications (OpenDocument) v1.3”. |
| ODS_3 | Extension | The file **MUST** have extension “.fods”, “.ods” or “ots”. |
| ODS_4 | External data | The file **MUST NOT** have any references to external data. This includes data connections, RealTimeData functions, cell formula references and objects. |
| ODS_5 | Embedded objects | The file **MUST NOT** have any embedded objects, which are in violation of your organisation’s file format policies. |
| ODS_6 | Cell values | The file **SHOULD** have cell values or objects. |
| ODS_7 | Macros | The file **SHOULD NOT** have any macros. |
| ODS_8 | Set “LoadReadonly” | The file **SHOULD** have XML attribute “LoadReadonly” in “settings.xml” set as true. |
| ODS_9 | Printer settings | The file **MAY** have XML attributes “PrinterName”, “PrinterPaperFromSetup” and “PrinterSetup”. |
| ODS_10 | Metadata | The file **MAY** have metadata in the file’s properties or any user defined custom properties in “meta.xml”. |
| ODS_11 | Cell hyperlinks | The file **MAY** have cell hyperlinks. |

## 2.2 Office Open XML SpreadsheetML
The following table describes the requirements for data quality, when preserving spreadsheets in Office Open XML SpreadsheetML file format.

**Table 2. Office Open XML SpreadsheetML requirements**

| ID | Name | Description |
| --- | --- | --- |
| ODS_1 | Password protection | The file **MUST NOT** have read or write password protection. |
| ODS_2 | Standard compliance | The file **MUST** comply with the standard “ISO/IEC 29500 Office Open XML File Formats”. |
| ODS_3 | Extension | The file **MUST** have extension “.fods”, “.ods” or “ots”. |
| ODS_4 | Conformance | The file **SHOULD** comply with “strict” conformance class. |
| ODS_5 | External data | The file **MUST NOT** have any references to external data. This includes data connections, RealTimeData functions, cell formula references and objects. |
| ODS_6 | Embedded objects | The file **MUST NOT** have any embedded objects, which are in violation of your organisation’s file format policies. |
| ODS_7 | Cell values | The file **SHOULD** have cell values or objects. |
| ODS_8 | Macros | The file **SHOULD NOT** have any macros. |
| ODS_9 | Absolute filepath | The file **SHOULD NOT** have absolute filepath to local file system in the XML attribute “x15ac:absPath” in “workbook.xml”. |
| ODS_10 | Mark “final” | The file **SHOULD** have “final” mark. |
| ODS_11 | Printer settings | The file **MAY** have XML attributes “PrinterName”, “PrinterPaperFromSetup” and “PrinterSetup”. |
| ODS_12 | Metadata | The file **MAY** have metadata in the file’s properties or any user defined custom properties in “meta.xml”. |
| ODS_13 | Cell hyperlinks | The file **MAY** have cell hyperlinks. |

## 2.3 Mark-up languages
The following table describes the requirements for data quality, when preserving spreadsheets in a text-based mark-up language file format.

***Be aware!***
*Significant properties may be lost when converting spreadsheets to CSV file format. Examples of properties are pivot tables, images, charts, formulas and formatting. Converting to CSV should therefore only be used after careful appraisal.*

**Table 3. Mark-up language requirements**

| ID | Name | Description |
| --- | --- | --- |
| CSV_1 | CSV file format | The file **MUST** comply with the specification “Common Format and MIME Type for Comma-Separated Values (CSV) Files, RFC 4180”. |
| CSV_2 | Extension | The file **MUST** have extension “.csv”. |
| CSV_3 | Sheets | The spreadsheet **MUST** have each sheet converted to an independent file named “Sheet1”, “Sheet2” etc. |
| CSV_4 | Graphical material | The spreadsheet **MAY** have any graphical material i.e. images, charts, diagrams, shapes extracted as independent files named “Image1”, “Image2” etc. |

## 2.4 Static file formats
The following table describes the requirements for data quality, when preserving spreadsheets in a static file format.

***Be aware!***
*Significant properties may be lost when converting spreadsheets to a static file format. Examples of properties are formulas, hyperlinks and dynamic content such as pivot tables, searching and filtering. Converting to a static file format should therefore only be used after careful appraisal.*

**Table 4. Static file formats requirements**

| ID | Name | Description |
| --- | --- | --- |
| STATIC_1 | File format | The file **MUST** comply with one of these file format specifications.
* JPEG-2000
* PDF/A
* PNG
* TIFF |
| STATIC_2 | Extension | The file **MUST** have one of these extensions.
* “.jp2”
* “.pdf”
* “.png”
* “.tif” or “.tiff” |
| STATIC_3 | Sheets | The spreadsheet **MUST** have each sheet converted to an independent file named “Sheet1”, “Sheet2” etc. |
| STATIC_4 | Truncated cells | Any truncated cells **MUST NOT** have text wrap. |
| STATIC_5 | Formulas | The spreadsheet **MUST** have any formulas printed to a static file named “Data”. |
| STATIC_6 | Cell hyperlinks | The spreadsheet **SHOULD** have any cell hyperlinks printed to a static file named “Data”. |