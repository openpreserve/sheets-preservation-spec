# Guidelines for File Format Policies Compliance

## Table of Contents
* [1 Introduction](#1-introduction)
* [2 Guidelines](#2-guidelines)
    * [2.1 OpenDocument Spreadsheets](#21-opendocument-spreadsheets)
    * [2.2 OfficeOpen XML SpreadsheetML](#22-office-open-xml-spreadsheetml)
    * [2.3 Mark-up Languages]()
    * [2.4 Static file formats]()

## 1 Introduction
This specification includes guidelines on how to comply with the file format policies in section 3. Guidelines are recommended approaches on how to obtain compliance, but many other approaches than specified in these guidelines may exist, especially over time. The guidelines do not specify which tools to use to obtain compliance with the file format policies.

Each file format policy has a guideline with a table containing:
* ID is a unique identifier for the requirement
* Description is the detailed explanation of the guideline

The following subsections go through each guideline and at the end has a section on considerations related to appraisal and migration paths for spreadsheets.

# 2 Guidelines

### 2.1 OpenDocument Spreadsheets
The following table gives guidelines for how to comply with the requirements in section 3.1.

**Table 5. OpenDocument Spreadsheets guidelines**

| ID | Description |
| --- | --- |
| ODS_1 | The password can be manually obtained and input to unlock and resave the file without password protection. Obtaining the password may involve searching through records management systems, other registries or asking the creator of the file. 

When the password for a protected file cannot be obtained, then the spreadsheet cannot be migrated to a preservation format. Your organisation might preserve the original submission or you may instead decide against preserving material that is effectively encrypted. |
| ODS_2 | File format compliance should be validated using a tool, since the manual inspection of each property is an unfeasible task for any human. |
| ODS_3 | Extension should be lowercase. |
| ODS_4 | Any external data references such as data connections, RTD functions, cell references or objects can be removed, however the calculated cell value MUST be preserved.

Removal of data connections will not result in any risk in loss of calculated cell values. 

Removal of RealTimeData functions and cell references by removing the underlying formula must happen by simultaneously preserving the calculated cell value.

External object references may be included as an independent object and child/parent relationships created. Thirdly, external object references can be removed with an appraised acceptance of the data loss.

Cell hyperlinks are exempt.

Removed external data can be saved as metadata in a sidecar file or in an associated table, to document its existence before removal. |
| ODS_5 | Embedded objects can be converted to a file format, your organisation accepts. Secondly, embedded objects can be removed with an appraised acceptance of the data loss. |
| ODS_6 | A spreadsheet without any cell values or objects is most likely empty of content. To easily check this, read the “meta.xml” and check if “meta:cell-count” or “meta:object-count” is greater than 0.

IF no cell values or objects exist, the file must be appraised to determine if other kind of content exists. If so the file may be preserved.

Information may be stored in user defined properties or color formatting of cells may have been used to semantically convey a message. These are potential occurences, which after appraisal could lead to preserving the spreadsheet. |
| ODS_7 | Macros contain programming code that can execute and manipulate data in the spreadsheet and the file system. These may present security risks, and it is therefore prudent to remove any macros. Removal may result in loss of information, but typically macros are used to change data, and this goes against the intentions of preserving the data fixed in time, and removal may therefore often happen with no implications. |
| ODS_8 | An OpenDocument file may be marked as “read only” in the file’s XML attribute “LoadReadonly” in “settings.xml”. This means the data won’t be editable unless a copy is created. |
| ODS_9 | Printer settings are information related to local and/or network printers. This data may contain encrypted information on how to connect to the printer. For security reasons, this data may be removed. Removing the data will not result in the loss of any significant properties. |
| ODS_10 | Metadata in the file property information and “meta.xml” such as author, title, category and user defined properties etc. can be misleading if i.e. the document was reused as a template. User defined custom properties may be created and stored in “meta.xml”.

You may consider removing this information from the file to not mislead any future user of the data.

Metadata can be saved in a sidecar file or in an associated table, to document their existence before removal. |
| ODS_11 | Cell hyperlinks are in essence unproblematic to keep in a spreadsheet, but your organisation may want to remove cell hyperlinks, since they reference external information.

Cell hyperlinks may be opened using an internet archive, if the cell hyperlinks are no longer active.

Broken (unavailable URL) cell hyperlinks may be checked for upon ingest and reported.

Cell hyperlinks can be saved in a sidecar file or in an associated table, to document their existence before removal. |

## 2.2 Office Open XML SpreadsheetML
The following table gives guidelines for how to comply with the requirements in section 3.2.

**Table 6. Office Open XML SpreadsheetML guidelines**
| ID | Description |
| --- | --- |
|  |  |