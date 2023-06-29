![Open Preservation Foundation logo](https://openpreservation.org/wp-content/uploads/2023/06/Untitled-design.png)

# OPF Spreadsheets Preservation Specification

**Draft v1.0, 2023**

## Table of Contents

* [1 Introduction](#1-introduction)
* [2 Declarations](#2-declarations)
    * [2.1 Aim](#21-aim)
    * [2.2 Scope](#22-scope)
    * [2.3 Licence](#23-licence)
* [3 Appraisal and Migration Paths](#3-appraisal-and-migration-paths)
* [4 File Format Policies](#4-file-format-policies)
    * [4.1 OpenDocument Spreadsheets](#41-opendocument-spreadsheets)
    * [4.2 OfficeOpen XML SpreadsheetML](#42-office-open-xml-spreadsheetml)
    * [4.3 Mark-up Languages](#43-mark-up-languages)
    * [4.4 Static File Formats](#44-static-file-formats)
* [5 Guidelines for File Format Policies Compliance](#5-guidelines-for-file-format-policies-compliance)
    * [5.1 OpenDocument Spreadsheets](#51-opendocument-spreadsheets)
    * [5.2 OfficeOpen XML SpreadsheetML](#52-office-open-xml-spreadsheetml)
    * [5.3 Mark-up Languages](#53-mark-up-languages)
    * [5.4 Static File Formats](#54-static-file-formats)
* [6 Metadata Preservation Scheme](#6-metadata-preservation-scheme)
    * [6.1 Metadata Recommendations](#61-metadata-recommendations)
* [7 Example Spreadsheets Software](#7-example-spreadsheets-software)
    * [7.1 Manual XML Editing](#71-manual-xml-editing)
    * [7.2 Programmatic Conversion and Data Manipulation](#72-programmatic-conversion-and-data-manipulation)
    * [7.3 Comparison](#73-comparison)
    * [7.4 Validation](#74-validation)
    * [7.5 Editing and Rendering](#75-editing-and-rendering)
* [8 Glossary](#8-glossary)
* [9 References](#9-references)
* [10 Postface](#10-postface)
    * [10.1 Authors](#101-authors)
    * [10.2 Acknowledgments](#102-acknowledgments)

## 1 Introduction

This document describes the considerations to make when digitally preserving data created in a spreadsheet file format (i.e. .xlsx, .numbers, .ods).

The document is formalized as a specification to be used in Archival Information Packages (AIP), ideally in parallel with bit preservation of the original data. The migration of spreadsheet data should not be conducted prior to appraisal and technical analysis to ensure data loss is reduced to a minimum and any incurred is acceptable within your organisation.

The specification should be supported by software tools to automatically process the conversion and validation of spreadsheets to comply with this specification.

This specification is released and maintained by [Open Preservation Foundation](https://openpreservation.org/).

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

If a file format is not covered in the section “4 File Format Policies”, then this file format is not considered suitable as an AIP file format. In the case of conversion using sections "4.3 Mark-up languages" and section "4.4 Static File Formats", an appraisal of the significant properties must be made prior to conversion to assess and document the possible data loss.

As mentioned in “2.2 Scope”, this specification does not specify which file formats to submit data to an organisation in. It is up to this institution to determine their policy for how data are submitted to them. However, this specification does specify which file formats may be used for archival storage of spreadsheets, potentially in parallel with bit preservation of an original master copy of the data.

The original master copy may be corrupt or password protected, and hence a migration copy for archival storage cannot be created. It is up to the receiving organisation to appraise, whether these master copies should be preserved or destroyed.

## 4 File Format Policies

Each file format policy has a table with:
* ID is a unique identifier for the requirement
* Name is a short title for the requirement
* Description is the detailed explanation of the requirement including the level of conformance
* Cardinality is the detailing of occurrences of the requirement

The file format policies must be validated in accordance with the following levels of requirements adopted from Key words for use in RFCs to Indicate Requirement Levels (Bradner, 1997):
* ERROR is equal to **MUST**/**MUST NOT** conformance
* WARNING is equal to **SHOULD**/**SHOULD NOT** conformance
* INFO is equal to **MAY** conformance

The following subsections cover each file format policy.

### 4.1 OpenDocument Spreadsheets

The following table describes the requirements for data quality when preserving spreadsheets in OpenDocument Spreadsheets file format.

**Table 1. OpenDocument Spreadsheets requirements**

| ID | Name | Description |
| --- | --- | --- |
| ODS_1 | Password protection | The file **MUST NOT** have read or write password protection. |
| ODS_2 | Standard compliance | The file **MUST** comply with the standard “OASIS Open Document Format for Office Applications (OpenDocument) v1.3”. |
| ODS_3 | Extension & MIME type | The file **MUST** have one of the following matching extension and MIME type pairs:<ul><li>Extension: ".fods", MIME type: "application/vnd.oasis.opendocument.spreadsheet"</li><li>Extension: ".ods", MIME type: "application/vnd.oasis.opendocument.spreadsheet"</li><li>Extension: ".ots", MIME type: "application/vnd.oasis.opendocument.spreadsheet-template"</li></ul> |
| ODS_4 | External data | The file **MUST NOT** have any references to external data. This includes data connections, RealTimeData functions, cell formula references and objects. |
| ODS_5 | Embedded objects | The file **MUST NOT** have any embedded objects, which are in violation of your organisation’s file format policies. |
| ODS_6 | Content | The file **SHOULD** have cell values or objects. |
| ODS_7 | Macros | The file **SHOULD NOT** have any macros. |
| ODS_8 | Fonts | The file **SHOULD** have any used fonts embedded. |
| ODS_9 | Settings file |The file **MAY** have the "settings.xml" file. |
| ODS_10 | Metadata | The file **MAY** have metadata in the file’s properties or any user defined custom properties in “meta.xml”. |
| ODS_11 | Cell hyperlinks | The file **MAY** have cell hyperlinks. |
| ODS_12 | Preview image | The file **MAY** have a preview image. |

### 4.2 Office Open XML SpreadsheetML

The following table describes the requirements for data quality, when preserving spreadsheets in Office Open XML SpreadsheetML file format.

**Table 2. Office Open XML SpreadsheetML requirements**

| ID | Name | Description |
| --- | --- | --- |
| OOXML_1 | Password protection | The file **MUST NOT** have read or write password protection. |
| OOXML_2 | Standard compliance | The file **MUST** comply with the standard “ISO/IEC 29500 Office Open XML File Formats”. |
| OOXML_3 | Extension | The file **MUST** have extension ".xlsm", “.xlsx”, “.xltx” or ".xltm". |
| OOXML_4 | Conformance | The file **SHOULD** comply with “strict” conformance class. |
| OOXML_5 | External data | The file **MUST NOT** have any references to external data. This includes data connections, RealTimeData functions, cell formula references and objects. |
| OOXML_6 | Embedded objects | The file **MUST NOT** have any embedded objects, which are in violation of your organisation’s file format policies. |
| OOXML_7 | Content | The file **SHOULD** have cell values or objects. |
| OOXML_8 | Macros | The file **SHOULD NOT** have any macros. |
| OOXML_9 | Absolute filepath | The file **SHOULD NOT** have absolute filepath to local file system in the XML attribute “x15ac:absPath” in “workbook.xml”. |
| OOXML_10 | Final | The file **SHOULD** have “final” mark. |
| OOXML_11 | Printer settings | The file **MAY** have printer settings files in the "printerSettings" folder. |
| OOXML_12 | Metadata | The file **MAY** have metadata in the file’s properties or any user defined custom properties. |
| OOXML_13 | Cell hyperlinks | The file **MAY** have cell hyperlinks. |

### 4.3 Mark-up Languages

The following table describes the requirements for data quality, when preserving spreadsheets in a text-based mark-up language file format.

***Be aware!***
*Significant properties may be lost when converting spreadsheets to CSV file format. Examples of properties are pivot tables, images, charts, formulas and formatting. Converting to CSV should therefore only be used after careful appraisal.*

**Table 3. Mark-up language requirements**

| ID | Name | Description |
| --- | --- | --- |
| CSV_1 | CSV file format | The file **MUST** comply with the specification “Common Format and MIME Type for Comma-Separated Values (CSV) Files, RFC 4180”. |
| CSV_2 | Extension | The file **MUST** have extension “.csv”. |
| CSV_3 | Sheets | The file **MUST** have each sheet converted to an independent file named “Sheet1”, “Sheet2” etc. |
| CSV_4 | Graphical material | The file **MAY** have any graphical material i.e. images, charts, diagrams, shapes extracted as independent files named “Image1”, “Image2” etc. |
| CSV_5 | Metadata | The file **MAY** have metadata in the file’s properties. |

### 4.4 Static File Formats

The following table describes the requirements for data quality, when preserving spreadsheets in a static file format.

***Be aware!***
*Significant properties may be lost when converting spreadsheets to a static file format. Examples of properties are formulas, hyperlinks and dynamic content such as pivot tables, searching and filtering. Converting to a static file format should therefore only be used after careful appraisal.*

**Table 4. Static file formats requirements**

| ID | Name | Description |
| --- | --- | --- |
| STATIC_1 | File format | The file **MUST** comply with one of these file format specifications.<ul><li>JPEG-2000</li><li>PDF/A</li><li>PNG</li><li>TIFF</li></ul> |
| STATIC_2 | Extension | The file **MUST** have one of these extensions.<ul><li>“.jp2”</li><li>“.pdf”</li><li>“.png”</li><li>“.tif” or “.tiff”</li></ul> |
| STATIC_3 | Sheets | The spreadsheet **MUST** have each sheet converted to an independent file named “Sheet1”, “Sheet2” etc. |
| STATIC_4 | Truncated cells | Any truncated cells **MUST NOT** have text wrap. |
| STATIC_5 | Formulas | The file **MUST** have any formulas printed to a static file named “Data”. |
| STATIC_6 | Metadata | The file **MAY** have metadata in the file’s properties. |
| STATIC_7 | Cell hyperlinks | The file **SHOULD** have any cell hyperlinks printed to a static file named “Data”. |

## 5 Guidelines for File Format Policies Compliance

This specification includes guidelines on how to comply with the file format policies in section 3. Guidelines are recommended approaches on how to obtain compliance, but many other approaches than specified in these guidelines may exist, especially over time. The guidelines do not specify which tools to use to obtain compliance with the file format policies.

Each file format policy has a guideline with a table containing:
* ID is a unique identifier for the requirement
* Description is the detailed explanation of the guideline

The following subsections go through each guideline and at the end has a section on considerations related to appraisal and migration paths for spreadsheets.

### 5.1 OpenDocument Spreadsheets

The following table gives guidelines for how to comply with the requirements in section 4.1.

**Table 5. OpenDocument Spreadsheets guidelines**

| ID | Description |
| --- | --- |
| ODS_1 | The password can be manually obtained and input to unlock and resave the file without password protection. Obtaining the password may involve searching through records management systems, other registries or asking the creator of the file.<br><br>When the password for a protected file cannot be obtained, then the spreadsheet cannot be migrated to a preservation format. Your organisation might preserve the original submission or you may instead decide against preserving material that is effectively encrypted. |
| ODS_2 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| ODS_3 | A MIME type declaration is required in the first line of the file "mimetype" and an entry in the file "\META-INF\manifest.xml" with: <br>"<manifest:file-entry manifest:full-path="/" manifest:version="INSERT ODF VERSION" manifest:media-type="INSERT MIME TYPE"/>".<br><br>The MIME type must match the extension. The pairs are: <ul><li>Extension: ".fods", MIME type: "application/vnd.oasis.opendocument.spreadsheet"</li><li>Extension: ".ods", MIME type: "application/vnd.oasis.opendocument.spreadsheet"</li><li>Extension: ".ots", MIME type: "application/vnd.oasis.opendocument.spreadsheet-template"</li></ul>Extension should be lowercase. |
| ODS_4 | Any external data references such as data connections, RTD functions, cell references or objects can be removed, however the calculated cell value MUST be preserved.<br><br>Removal of data connections will not result in any risk in loss of calculated cell values.<br><br>Removal of RealTimeData functions and cell references by removing the underlying formula must happen by simultaneously preserving the calculated cell value.<br><br>External object references may be included as an independent object and child/parent relationships created. Thirdly, external object references can be removed with an appraised acceptance of the data loss.<br><br> Cell hyperlinks are exempt and covered in ODS_11.<br><br> Removed external data can be saved as metadata in a sidecar file or in an associated table, to document its existence before removal. |
| ODS_5 | Embedded objects can form preservation risks, as explained in Artefactual's Preserving Spreadsheet Guidance Note (available at dpconline.org). It is important to check what type of object is embedded in your spreadsheet, and what its function is. Embedded objects SHOULD BE preserved when they are considered significant properties of the spreadsheet. If they are considered artifacts, they MAY BE removed from the spreadsheet file and/or migrated to a format that complies with your file format policy if needed. Artifact embedded objects MAY BE deleted in case of an appraised acceptance of the data loss. Preserve in metadata the relationship between the spreadsheet and the removed and/or migrated or deleted object, and the cell (range) which the object covered. |
| ODS_6 | A spreadsheet without any cell values or objects is most likely empty of content. To easily check this, read the “meta.xml” and check if “meta:cell-count” or “meta:object-count” is greater than 0.<br><br>If no cell values or objects exist, the file must be appraised to determine if other kind of content exists. If so the file may be preserved.<br><br>Information may be stored in user defined properties or color formatting of cells may have been used to semantically convey a message. These are potential occurences, which after appraisal could lead to preserving the spreadsheet. |
| ODS_7 | Macros contain programming code that can execute and manipulate data in the spreadsheet and the file system. These may present security risks, and it is therefore prudent to remove any macros. Removal may result in loss of information, but typically macros are used to change data, and this goes against the intentions of preserving the data fixed in time, and removal may therefore often happen with no implications. |
| ODS_8 | Any fonts used in the spreadsheet should be embedded in the file to enable authentic rendering of the spreadsheet in operating environments, that does not have the fonts installed. The policy is not a MUST requirement, because spreadsheets typically does not use uncommon or special fonts, and in those cases where it may happen, the fonts are typically not essential for the reuse of the data. However, your organisation may take their own decision on how to handle fonts. |
| ODS_9 | An OpenDocument file may have a file called "settings.xml". This file stores XML attributes defining how an application should render the spreadsheet file. However, the "settings.xml" is not required by the ODF standard and it neither defines any XML attributes leaving the attributes entirely custom for the application, which created the file. Furthermore, only some applications creates or renders a "settings.xml" file.<br><br>The "settings.xml" file may be considered an artefact and either ignored or removed from the spreadsheet. |
| ODS_10 | Metadata in the file property information and “meta.xml” such as author, title, category and user defined properties etc. can be misleading if i.e. the document was reused as a template. User defined custom properties may be created and stored in “meta.xml”.<br><br>You may consider removing this information from the file to not mislead any future user of the data.<br><br>Metadata can be saved in a sidecar file or in an associated table, to document their existence before removal. |
| ODS_11 | Cell hyperlinks are in essence unproblematic to keep in a spreadsheet, but your organisation may want to remove cell hyperlinks, since they reference external information.<br><br>Cell hyperlinks may be opened using an internet archive, if the cell hyperlinks are no longer active.<br><br>Broken (unavailable URL) cell hyperlinks may be checked for upon ingest and reported.<br><br>Cell hyperlinks can be saved in a sidecar file or in an associated table, to document their existence before removal. |
| ODS_12 | Preview image is a thumbnail image stored in the spreadsheet's zipped path “Thumbnails/thumbnail.png”. The preview image may be used by the operating system as the file's icon in the file browser/manager.<br><br>The preview image should be considered insignificant for preservation, since it may be generated at any given time and serves no essential purpose. It  may be considered an artefact. |

### 5.2 Office Open XML SpreadsheetML

The following table gives guidelines for how to comply with the requirements in section 4.2.

**Table 6. Office Open XML SpreadsheetML guidelines**

| ID | Description |
| --- | --- |
| OOXML_1 | The password can manually be obtained and input to unlock and resave the file without password protection. Obtaining the password may involve searching through records management systems, other registries or asking the creator of the file. If the password cannot be obtained the spreadsheet should not be preserved. |
| OOXML_2 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| OOXML_3 | Extension should be lowercase.<br><br>Extension “.xlam” is not allowed, since this data are an “macro-enabled workbook add-in” and only contains technical data, that changes or enhances the interface and functionality of the rendering application i.e. Excel. Extension ".xlsb" is not allowed since this is a binary file format. |
| OOXML_4 | Conformance may be “transitional” but should be “strict”. Conforming to “strict” involves converting or removing any legacy features imported from older Excel file formats i.e. .xls and .xlt. If a spreadsheet was created as an OOXML spreadsheet, the conformance will by default be “transitional”. However, this spreadsheet will not contain any legacy features and will de facto conform to “strict” and to obtain “strict” conformance only conformance class workbook attribute and namespaces must be changed.<br><br>At the time of writing of this specification tool support for conversion and validation of Strict is poorly supported. |
| OOXML_5 | Any external data references such as data connections, RTD functions, cell references or objects can be removed, however the calculated cell value MUST be preserved.<br><br>Removal of data connections will not result in any risk in loss of calculated cell values.<br><br>Removal of RealTimeData functions and cell references by removing the underlying formula must happen by simultaneously preserving the calculated cell value.<br><br>External object references may be included as an independent object and child/parent relationships created. Thirdly, external object references can be removed with an appraised acceptance of the data loss.<br><br>Cell hyperlinks are exempt and covered in OOXML_13.<br><br>Removed external data can be saved as metadata in a sidecar file or in an associated table, to document its existence before removal. |
| OOXML_6 | Embedded objects can be converted to a file format, your organisation accepts. Secondly, embedded objects can be removed with an appraised acceptance of the data loss. |
| OOXML_7 | A spreadsheet without any cell values may still contain images, charts and other objects. However, if any cell values does not exist this may be an indicator, that the spreadsheet is empty and therefore should be assessed, if this is the case. If empty, the spreadsheet should not be preserved. |
| OOXML_8 | Macros contain programming code that can execute and manipulate data in the spreadsheet and the file system. This may have security risks, and it is therefore prudent to remove any macros. Removal may result in loss of information, but typically macros are used to change data, and this goes against the intentions of preserving the data fixed in time, and removal may therefore often happen with no implications.<br><br>Removing macros happens by converting the spreadsheet from “.xlsm” or “.xltm” to “.xlsx”. |
| OOXML_9 | Absolute filepath value in the XML attribute “x15ac:absPath” in “workbook.xml” may contain personal or confidential information in the naming of folders/directories of the file system, which the file was last opened and saved to.<br><br>Absolute filepath can be removed without loss of any significant properties.<br><br>Absolute filepath can be saved in a sidecar file or in an associated table, to document its existence before removal. |
| OOXML_10 | An OOXML file may be marked as “final”. |
| OOXML_11 | Printer settings are information related to local printers or printer on the network. This information may contain encrypted information on how to connect to the printer. For security reasons, this data may be removed. Removing the data will not result in the loss of any significant properties. |
| OOXML_12 | Metadata in the file property information such as author, title, category etc. can be misleading if i.e. the document was reused as a template. You may consider removing this information from the file to not mislead any future user of the data.<br><br>Metadata can be saved in a sidecar file or in an associated table, to document their existence before removal. |
| OOXML_13 | Cell hyperlinks are in essence unproblematic to keep in a spreadsheet, but your organisation may want to remove cell hyperlinks, since they reference external information.<br><br>Cell hyperlinks may be opened using an internet archive, if the cell hyperlinks are no longer active.<br><br>Broken (unavailable URL) cell hyperlinks may be checked for upon ingest and reported.<br><br>Cell hyperlinks can be saved in a sidecar file or in an associated table, to document their existence before removal. |

### 5.3 Mark-up Languages

The following table gives guidelines for how to comply with the requirements in section 4.3.

**Table 7. Mark-up language guidelines**

| ID | Description |
| --- | --- |
| CSV_1 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| CSV_2 | Extension should be lowercase. |
| CSV_3 | It is necessary to preserve each sheet in a spreadsheet, therefore you must make sure to export each sheet manually, or if applying a programmatic solution to loop all the sheets for exporting. The name of the sheet must be given “Sheet1.csv”, “Sheet2.csv” etc. |
| CSV_4 | The file format of the graphical material should be any appropriate image file format, your organisation already has a file format policy for, or a new file format policy should be created. |
| CSV_5 |  Metadata in the file property information such as author, title, category etc. can be misleading if i.e. the document was reused as a template. You may consider removing this information from the file to not mislead any future user of the data.<br><br>Metadata can be saved in a sidecar file or in an associated table, to document their existence if removed. |

### 5.4 Static File Formats

 The following table gives guidelines for how to comply with the requirements in section 4.4.

**Table 8. Static file format guidelines**

| ID | Description |
| --- | --- |
| STATIC_1 | You must choose one of these file formats to preserve a static representation of the spreadsheet in: JPEG-2000, PDF/A, PNG or TIFF file formats. A wide range of other image file formats exists, but these are typically not used for preservation of data, unless the data was originally created in the file format.<br><br>This specification limits the number of possible file formats to use for preserving a static representation of the spreadsheet, because it is necessary to specify exact file formats, otherwise it is not possible to validate the file format. Simply stating that “your organisation must use any static file format, that your organisation has a file format policy for” is not sufficient, because it is not feasible for software validation workflows to universally validate any possible static file format. |
| STATIC_2 | Extension should be lowercase. |
| STATIC_3 | It is necessary to preserve each sheet in a spreadsheet, therefore you must make sure to export each sheet manually, or if applying a programmatic solution to loop all the sheets for exporting. It is up to your organisation to determine if sheets should be split into multiple export files, or if you combine them into a single multipage file. When using a single multipage file, each page must have the name of the sheet in it. This specification does not recommend one approach over the other, and if your organisation does not have any preference, you may allow both approaches. |
| STATIC_4 | Before exporting, you must applying text wrapping to all cells of the sheet, otherwise truncated cells with information will result in information loss, since this information will be hidden behind the proceeding column’s cell, if this cell contains information. |
| STATIC_5 | The new static file representation of the formulas should have three columns in row 1 with the following information:<ul><li>*Column 1:* Sheet name</li><li>*Column 2:* Cell reference</li><li>*Column 3:* Formula</li></ul> |
| STATIC_6 |  Metadata in the file property information such as author, title, category etc. can be misleading if i.e. the document was reused as a template. You may consider removing this information from the file to not mislead any future user of the data.<br><br>Metadata can be saved in a sidecar file or in an associated table, to document their existence if removed. |
| STATIC_7 | The static file representation of the cell hyperlinks should be shared with the file created in STATIC_5 and have a fourth column appended in row 1 with the following information:<ul><li>*Column 4:* Cell hyperlink</li></ul> |

## 6 Metadata Preservation Scheme

This specification defines a preservation scheme for the metadata in a spreadsheet or metadata related to altering the content of a spreadsheet.

Spreadsheets can contain metadata such as (original) filename, title, author and creation date, or have associated metadata about the context of or events related to the spreadsheet, Spreadsheet metadata should be preserved when considered a significant property. It is up to your organization to determine the best approach and metadata standard for preserving such metadata. Metadata that is considered an artifact may be removed.

The metadata may be preserved in a sidecar file for each spreadsheet or preserved in a database table with metadata for multiple spreadsheets. It is up to your organisation to determine the best approach and metadata standard for capturing the recommended metadata.

###  6.1 Metadata Recommendations

The following table recommends which metadata should be preserved and in which circumstances.

**Table 9. Metadata that may be preserved.**

| Relevant IDs | Name | Description | Circumstance |
| --- | --- | --- | --- |
| ODS_9, OOXML_12, CSV_5, STATIC_6 | Filename | The filename of the spreadsheet. | Every time |
| ODS_9, OOXML_12, CSV_5, STATIC_6 | Creator | The creator of the spreadsheet in the file properties. | If value exist |
| ODS_9, OOXML_12, CSV_5, STATIC_6 | Creation date | The creation date of the spreadsheet in the file properties. | Every time |
| ODS_9, OOXML_12, CSV_5, STATIC_6 | Title | The title of the spreadsheet in the file properties.| If value exist |
| ODS_9, OOXML_12, CSV_5, STATIC_6 | Category | The categories of the spreadsheet in the file properties. | If value exist |
| CSV_3, STATIC_3 | Sheets | The names of all sheets. | Every time |
| ODS_4, OOXML_5 | External references | Any external reference to data e.g. data source, cell reference, RealTimeData. The cell position of the external reference should be preserved. Recommendations for the following types of content:<br>- Data sources: The database name, description and type should be preserved<br>- External cell references: The formula should be preserved.<br>- RealTimeData: The formula should be preserved.<br>- External OLE objects: The target and content type should be preserved. | If removed |
| ODS_5, OOXML_6 | Embedded objects | Any embedded object that has been removed. The cell position of the embedded object should be preserved. The content type should be preserved. | If removed |
| STATIC_6 | Formulas | Any formulas that has been removed from the spreadsheet. The cell position of the formula should be preserved. | Every time |
| ODS_7, OOXML_8 | Macros | Any macros that has been removed from the spreadsheet. The entire macro code should be preserved. The name of the macro should be preserved. | If removed |
| ODS_10, OOXML_13, STATIC_6 | Cell hyperlinks | Any hyperlinks to websites in any cells. The cell position of the hyperlink should be preserved. | Every time |

## 7 Example Spreadsheets Software

This section is a collation of existing, example software for
* editing,
* converting,
* comparing,
* validating, and
* rendering spreadsheet file formats.

The collation of example software are subject to obsolescence according to software becoming deprecated or newer software is released with the passing of time. Therefore, only use this collated information after careful consideration and always only use the most updated version of the specification.

This collation of information should not be viewed as an endorsement or recommendation of the software. The collation is a means for you to identify possible ways of complying with this specification using tools to support your work.

The following sub sections provide tables of example software covering different purposes.

### 7.1 Manual XML Editing

**Table 10. List of software for manual editing of spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| OOXML Tools | Chrome extension | Chrome | Free to use |
| OOXML Viewer | Visual Studio Code extension | Linux, macOS, Windows | MIT |

### 7.2 Programmatic Conversion and Data Manipulation

**Table 11. Software for programmatic conversion and data manipulation of spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| Aspose.Cells | **Input/Output:** CSV, HTML, MHTML, NUMBERS, ODS, TSV, XLS, XLSB, XLSM, XLSX, XLT, XLTM, XLTX and XML<br>**Output only:** BMP, DIF, EMF, GIF, JPEG, PDF, PDF/A, PNG, SVG, TIFF and XPS | Android via Java, C++, Java, .Net, Node.js. PHP, Python | Commercial |
| Apache POI | **Input/Output:** XLA, XLS, XLT, XLAM, XLSM, XLSX, XLTM and XLTX | Java | Apache 2.0 |
| ClosedXML | **Input/Output:** XLAM, XLSM, XLSX, XLTM and XLTX | .Net | MIT |
| docx4j | **Input/Output:** XHTML, XLSX<br>**Output only:** PDF | Java | Apache 2.0 |
| Excel Interop | **Input/Output:** CSV, HTML, ODS, XLA, XLS, XLT, XLAM, XLSM, XLSX, XLTM and XLTX | .Net | Proprietary |
| Excelize | **Input/Output:** XLAM, XLSM, XLSX, XLTM and XLTX | Go | BSD-3-Clause |
| EPPlus | **Input/Output:** XLSX and XLSM<br>**Output only:** HTML and JSON | .Net | Commercial |
| GemBox | **Input/Output:** XLS, XLSX, XLSB, XLSM, XLTX, ODS CSV, TXT, HTML and MHTML<br>**Output only:** PDF, XPS, PNG, JPEG, GIF, BMP, TIFF and WMP | .Net | Commercial |
| NPOI | **Input/Output:** XLS and XLSX | .Net | Apache 2.0 |
| ODF Toolkit | **Input/Output:** FODS, ODS and OTS | Java | Apache 2.0 |
| Open XML SDK | **Input/Output:** XLAM, XLSM, XLSX, XLTM and XLTX | .Net | MIT |
| PhpSpreadsheet | **Input/Output:** ODS, XLS (BIFF 8) and XLSX<br>**Input only:** XLS (BIFF 5), Excel 2003, Gnumeric and SYLK<br>**Output only:** PDF | PHP | MIT |
| Spire.XLS | **Input/Output:** CSV, HTML, ODS, XLS, XLSB, XLSM, XLSX<br>**Output only:** JPEG, OFD, PDF, PNG, PostScript, SVG, TXT, XML, UOS, XPS | Android via Java, C++, Java, .Net | Commercial |
| Syncfusion | **Input/Output:** CSV, Excel 2003, JSON, TSV, XLS, XLT, XLSM, XLSX, XLTM and XLTX<br>**Output only:** BMP, HTML, JPEG, ODS, PDF and PNG | .Net | Commercial |

### 7.3 Comparison

**Table 12. Software for comparing spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| Aspose.Cells | Compare the content of two spreadsheet files online. | Browser | Free to use |
| Beyond Compare | Compare the cell values of two spreadsheets. Can be extended using  | Linux, macOS, Windows | Commercial |
| Diffchecker | Compare the content of two spreadsheets online. | Browser | Free to use, commercial |
| Microsoft Spreadsheet Compare | Application is bundled with Office Pro. | Windows | Commercial |
| Spreadsheets Complexity Analyser | Java application for bulk extraction of spreadsheet properties and assessing the complexity of the files. | Linux, macOS, Windows | Free to use |
| XL Comparator | Compare the content of specific columns of two spreadsheet files (Excel and CSV) online. | Browser | Free to use |

### 7.4 Validation

**Table 13. Software for validating spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| KEEPS Validator ODF | Java application. | Linux, macOS, Windows | LGPL 3.0 |
| ODF Validator | Both a Java application and an online tool is available. | Linux, macOS, Windows | Apache |
| OPF ODF Validator | Java application. Created and maintained by Open Preservation Foundation. | Linux, macOS, Windows | BSD 3-Clause License |
| OOXML Validator | Both a Visual Studio Code extension and a CLI tool is available. | Linux, macOS, Windows | MIT |
| Open XML SDK | The framework has a validator built-in, which you can use to create your own application for validating OOXML. | .Net | MIT |

### 7.5 Editing and Rendering

**Table 14. Software for editing and rendering spreadsheets.**

| Name | Description | Prerequisites | Licence |
| --- | --- | --- | --- |
| Apache OpenOffice Calc | The application uses OpenDocument by default but you can also open and edit Excel file formats and Apple NUMBERS. | Linux, macOS, Windows | Free to use |
| Apple Numbers | The application uses its own file format NUMBERS by default but you can also open and edit Excel file formats. | Browser, macOS | Commercial |
| Aspose.Cells | An online platform for editing viewing and many other features. | Browser | Free to use |
| Calligra Sheets | The application uses OpenDocument by default but you can also open and edit Excel and several other file formats. | Linux macOS, WIndows | GPL-2.0 |
| Gnumeric | The application uses its own file format Gnumeric XML by default but you can also open and edit Excel file formats and OpenDocument. | Linux, Windows | GPL-2.0 or GPL-3.0 |
| LibreOffice Calc | The application uses OpenDocument by default but you can also open and edit Excel file formats and Apple NUMBERS. | Linux, macOS, Windows | Mozilla Public 2.0 |
| Microsoft Excel | The application uses Office Open XML file formats by default but you can also open and edit OpenDocument file formats. | Browser, macOS, Windows | Commercial |
| ONLYOFFICE Spreadsheet Editor | The application uses Office Open XML file formats by default but you can also open and edit OpenDocument file formats. | Android, browser, iOS, Linux, macOS, Windows | Free to use |

## 8 Glossary

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
| **External cell references** | External cell references is a type of cell formula, which fetches data from another spreadsheet. |
| **External objects** | An object that is linked as an OLE object, but is not embedded into the file/package. |
| **File format** | *From Digital Preservation Handbook:* A file format is a standard way that information is encoded for storage in a computer file. It tells the computer how to display, print, and process, and save the information. It is dictated by the application program which created the file, and the operating system under which it was created and stored. Some file formats are designed for very particular types of data, others can act as a container for different types. A particular file format is often indicated by a file name extension containing three or four letters that identify the format. |
| **File format extension** | A file format extension is an identifier set at the end of the filename and delimited by a dot/period e.g. ".ods" or ".xlsx". The identifier helps the operating system to associate an application for opening the file. |
| **File format signature** | A file format signature is a unique combination of bits, which identifies a specific file format. The signature, also called a "magic number", authoritatively identifies a file's format. |
| **Macros** | A sequence of code, which the spreadsheet can execute. This code may change data in the spreadsheet or the operating system. |
| **Mark-up language** | A mark-up language is a structured and text-encoded model for annotating data. CSV and HTML are mark-up languages. |
| **Migration path** | The chosen output file format for an input file format in a data conversion process. The migration path should to do the widest possible extent preserve all the significant properties of the input file format. Methodical assessments are necessary to define acceptable migration paths. |
| **OAIS** | The Reference Model for an Open Archival Information System, ISO 14721 |
| **Office Open XML (OOXML)** | Office Open XML ECMA- and ISO-standard. |
| **OpenDocument Spreadsheets (ODS)** | OpenDocument Spreadsheet subset of the OpenDocument ISO-standard. |
| **Printer settings** | Printer settings contains information on registered printers available for printing. This may contain encrypted information about connecting to the printer. |
| **Protection** | A spreadsheet may have read and/or write protection on structure, sheets and/or cells, that may demand a password to enable reading and/or writing. |
| **RealTimeData functions (RTD)** | RealTimeData functions is a type of cell formula in an OOXML spreadsheet, which can fetch data from a server in a specified interval. |
| **Sheets** | A spreadsheet must contain at least one sheet but may contain a large number of sheets. Sheets are the “pages” of a spreadsheet, and any cell exists in a sheet. Sheets are the structural wrapper of spreadsheet data. |
| **Significant properties** | Significant properties are the properties of data, which a designated community has deemed important to preserve for future reuse of data. A significant property is also termed a “Transformational Information Property” in the OAIS. |
| **Static file format** | A static file format is typically an image file format or the PDF file format, which editable files are converted to. This may result in loss of significant properties and hence data quality. |
| **Validation** | Validation is the act of confirming something, and in this context a spreadsheet, conforms to the regulations specified in a document, typically referred to as a standard. Validation results in either an approval or a disapproval of any data property or attribute according to a chosen conformance level.<br><br>Validation processes should be supported by software to automate the process, but validation may involve manual inspection of the data. |

## 9 References

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

## 10 Postface

The following includes information about the authors and other publication info.

### 10.1 Authors

Names of the persons, who wrote the first version of the specification.

**Table 16. Authors of this specification**

| Author | Organisation |
| --- | --- |
| Asbjørn Skødt | Danish National Archives |
| Remco van Veenendaal | National Archives of the Netherlands |
| Kaido Kivilaan | National Archives of Estonia |

### 9.2 Acknowledgments
Thanks to Carl Wilson of the Open Preservation Foundation who acted as a reviewer.

This specification draws inspiration from and is a natural by-product of the Open Preservation Foundation’s discontinued Archives Interest Group (AIG), which in the years 2016-21 investigated the significant properties of spreadsheets. The group won the audience award for best poster at the international digital preservation conference iPRES in 2019 and published their work in a final report in 2021, which also was presented as a paper at iPRES the same year.
