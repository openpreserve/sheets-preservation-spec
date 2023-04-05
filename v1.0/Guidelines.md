# Guidelines for File Format Policies Compliance

## Table of Contents

* [1 Introduction](#1-introduction)
* [2 Guidelines](#2-guidelines)
    * [2.1 OpenDocument Spreadsheets](#21-opendocument-spreadsheets)
    * [2.2 OfficeOpen XML SpreadsheetML](#22-office-open-xml-spreadsheetml)
    * [2.3 Mark-up Languages](#23-mark-up-languages)
    * [2.4 Static file formats](#24-static-file-formats)

## 1 Introduction

This specification includes guidelines on how to comply with the file format policies in section 3. Guidelines are recommended approaches on how to obtain compliance, but many other approaches than specified in these guidelines may exist, especially over time. The guidelines do not specify which tools to use to obtain compliance with the file format policies.

Each file format policy has a guideline with a table containing:
* ID is a unique identifier for the requirement
* Description is the detailed explanation of the guideline

The following subsections go through each guideline and at the end has a section on considerations related to appraisal and migration paths for spreadsheets.

## 2 Guidelines

### 2.1 OpenDocument Spreadsheets

The following table gives guidelines for how to comply with the requirements in section 3.1.

**Table 5. OpenDocument Spreadsheets guidelines**

| ID | Description |
| --- | --- |
| ODS_1 | The password can be manually obtained and input to unlock and resave the file without password protection. Obtaining the password may involve searching through records management systems, other registries or asking the creator of the file.<br><br>When the password for a protected file cannot be obtained, then the spreadsheet cannot be migrated to a preservation format. Your organisation might preserve the original submission or you may instead decide against preserving material that is effectively encrypted. |
| ODS_2 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| ODS_3 | Extension should be lowercase. |
| ODS_4 | Any external data references such as data connections, RTD functions, cell references or objects can be removed, however the calculated cell value MUST be preserved.<br><br>Removal of data connections will not result in any risk in loss of calculated cell values.<br><br>Removal of RealTimeData functions and cell references by removing the underlying formula must happen by simultaneously preserving the calculated cell value.<br><br>External object references may be included as an independent object and child/parent relationships created. Thirdly, external object references can be removed with an appraised acceptance of the data loss.<br><br> Cell hyperlinks are exempt and covered in ODS_11.<br><br> Removed external data can be saved as metadata in a sidecar file or in an associated table, to document its existence before removal. |
| ODS_5 | Embedded objects can be converted to a file format, your organisation accepts. Secondly, embedded objects can be removed with an appraised acceptance of the data loss. |
| ODS_6 | A spreadsheet without any cell values or objects is most likely empty of content. To easily check this, read the “meta.xml” and check if “meta:cell-count” or “meta:object-count” is greater than 0.<br><br>If no cell values or objects exist, the file must be appraised to determine if other kind of content exists. If so the file may be preserved.<br><br>Information may be stored in user defined properties or color formatting of cells may have been used to semantically convey a message. These are potential occurences, which after appraisal could lead to preserving the spreadsheet. |
| ODS_7 | Macros contain programming code that can execute and manipulate data in the spreadsheet and the file system. These may present security risks, and it is therefore prudent to remove any macros. Removal may result in loss of information, but typically macros are used to change data, and this goes against the intentions of preserving the data fixed in time, and removal may therefore often happen with no implications. |
| ODS_8 | An OpenDocument file may be marked as “read only” in the file’s XML attribute “LoadReadonly” in “settings.xml”. This means the data won’t be editable unless a copy is created. |
| ODS_9 | Printer settings are information related to local and/or network printers. This data may contain encrypted information on how to connect to the printer. For security reasons, this data may be removed. Removing the data will not result in the loss of any significant properties. |
| ODS_10 | Metadata in the file property information and “meta.xml” such as author, title, category and user defined properties etc. can be misleading if i.e. the document was reused as a template. User defined custom properties may be created and stored in “meta.xml”.<br><br>You may consider removing this information from the file to not mislead any future user of the data.<br><br>Metadata can be saved in a sidecar file or in an associated table, to document their existence before removal. |
| ODS_11 | Cell hyperlinks are in essence unproblematic to keep in a spreadsheet, but your organisation may want to remove cell hyperlinks, since they reference external information.<br><br>Cell hyperlinks may be opened using an internet archive, if the cell hyperlinks are no longer active.<br><br>Broken (unavailable URL) cell hyperlinks may be checked for upon ingest and reported.<br><br>Cell hyperlinks can be saved in a sidecar file or in an associated table, to document their existence before removal. |

## 2.2 Office Open XML SpreadsheetML

The following table gives guidelines for how to comply with the requirements in section 3.2.

**Table 6. Office Open XML SpreadsheetML guidelines**

| ID | Description |
| --- | --- |
| OOXML_1 | The password can manually be obtained and input to unlock and resave the file without password protection. Obtaining the password may involve searching through records management systems, other registries or asking the creator of the file. If the password cannot be obtained the spreadsheet should not be preserved. |
| OOXML_2 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| OOXML_3 | Extension should be lowercase.<br><br>Extension “.xlam” is not allowed, since this data are an “macro-enabled workbook add-in” and only contains technical data, that changes or enhances the interface and functionality of the rendering application i.e. Excel. |
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

## 2.3 Mark-up languages

The following table gives guidelines for how to comply with the requirements in section 3.3.

**Table 7. Mark-up language guidelines**

| ID | Description |
| --- | --- |
| CSV_1 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| CSV_2 | Extension should be lowercase. |
| CSV_3 | It is necessary to preserve each sheet in a spreadsheet, therefore you must make sure to export each sheet manually, or if applying a programmatic solution to loop all the sheets for exporting. The name of the sheet must be given “Sheet1.csv”, “Sheet2.csv” etc. |
| CSV_4 | The file format of the graphical material should be any appropriate image file format, your organisation already has a file format policy for, or a new file format policy should be created. |

## 2.4 Static file formats

 The following table gives guidelines for how to comply with the requirements in section 3.4.

**Table 8. Static file format guidelines**

| ID | Description |
| --- | --- |
| STATIC_1 | You must choose one of these file formats to preserve a static representation of the spreadsheet in: JPEG-2000, PDF/A, PNG or TIFF file formats. A wide range of other image file formats exists, but these are typically not used for preservation of data, unless the data was originally created in the file format.<br><br>This specification limits the number of possible file formats to use for preserving a static representation of the spreadsheet, because it is necessary to specify exact file formats, otherwise it is not possible to validate the file format. Simply stating that “your organisation must use any static file format, that your organisation has a file format policy for” is not sufficient, because it is not feasible for software validation workflows to universally validate any possible static file format. |
| STATIC_2 | Extension should be lowercase. |
| STATIC_3 | It is necessary to preserve each sheet in a spreadsheet, therefore you must make sure to export each sheet manually, or if applying a programmatic solution to loop all the sheets for exporting. It is up to your organisation to determine if sheets should be split into multiple export files, or if you combine them into a single multipage file. When using a single multipage file, each page must have the name of the sheet in it. This specification does not recommend one approach over the other, and if your organisation does not have any preference, you may allow both approaches. |
| STATIC_4 | Before exporting, you must applying text wrapping to all cells of the sheet, otherwise truncated cells with information will result in information loss, since this information will be hidden behind the proceeding column’s cell, if this cell contains information. |
| STATIC_5 | The new static file representation of the formulas should have three columns with the following information:<ul><li>Column 1: Sheet name</li><li>Column 2: Cell reference</li><li>Column 3: Formula</li></ul>The first three cells of the first row should be filled with strings “Sheet names”, “Cell reference” and “Formulas”.<br><br>If STATIC_5 is relevant, columns 1 and 2 may be shared. |
| STATIC_6 | The static file representation of the cell hyperlinks should be shared with the file created in STATIC_4 and have a fourth column appended with the following information:<ul><li>Column 4: Cell hyperlink</li></ul>The fourth cell of the first row should be filled with the string “Cell hyperlinks”. |