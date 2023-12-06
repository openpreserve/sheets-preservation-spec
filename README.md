# OPF Spreadsheets Preservation Specification

![Open Preservation Foundation logo](https://openpreservation.org/wp-content/uploads/2023/06/Untitled-design.png)

**Draft v1.0, 2023**

**Important:** This version is an unreleased draft version of the specification's first release. Any changes may be added to the specification without changes to versioning or draft status. It will be announced when the draft is ready for release, and any future changes to the specification will happen with versioning.

**TLDR:** This document describes how to preserve a spreadsheet file to enable access to the data at a later stage. The document is released and maintained by [Open Preservation Foundation](https://openpreservation.org/).

## Table of Contents

* [1 Introduction](/Draft%20v1.0/Specification.md#1-introduction)
* [2 Declarations](/Draft%20v1.0/Specification.md#2-declarations)
  * [2.1 Aim](/Draft%20v1.0/Specification.md#21-aim)
  * [2.2 Scope](/Draft%20v1.0/Specification.md#22-scope)
  * [2.3 Licence](/Draft%20v1.0/Specification.md#23-licence)
* [3 Appraisal and Migration Paths](/Draft%20v1.0/Specification.md#3-appraisal-and-migration-paths)
* [4 File Format Policies](/Draft%20v1.0/Specification.md#4-file-format-policies)
  * [4.1 OpenDocument Spreadsheets](/Draft%20v1.0/Specification.md#41-opendocument-spreadsheets)
  * [4.2 OfficeOpen XML SpreadsheetML](/Draft%20v1.0/Specification.md#42-office-open-xml-spreadsheetml)
  * [4.3 Mark-up Languages](/Draft%20v1.0/Specification.md#43-mark-up-languages)
  * [4.4 Static File Formats](/Draft%20v1.0/Specification.md#44-static-file-formats)
* [5 Guidelines for File Format Policies Compliance](/Draft%20v1.0/Specification.md#5-guidelines-for-file-format-policies-compliance)
  * [5.1 OpenDocument Spreadsheets](/Draft%20v1.0/Specification.md#51-opendocument-spreadsheets)
  * [5.2 OfficeOpen XML SpreadsheetML](/Draft%20v1.0/Specification.md#52-office-open-xml-spreadsheetml)
  * [5.3 Mark-up Languages](/Draft%20v1.0/Specification.md#53-mark-up-languages)
  * [5.4 Static File Formats](/Draft%20v1.0/Specification.md#54-static-file-formats)
* [6 Metadata Preservation Scheme](/Draft%20v1.0/Specification.md#6-metadata-preservation-scheme)
  * [6.1 Metadata Recommendations](/Draft%20v1.0/Specification.md#61-metadata-recommendations)
* [7 Example Spreadsheets Software](/Draft%20v1.0/Specification.md#7-example-spreadsheets-software)
  * [7.1 Manual XML Editing](/Draft%20v1.0/Specification.md#71-manual-xml-editing)
  * [7.2 Programmatic Conversion and Data Manipulation](/Draft%20v1.0/Specification.md#72-programmatic-conversion-and-data-manipulation)
  * [7.3 Comparison](/Draft%20v1.0/Specification.md#73-comparison)
  * [7.4 Validation](/Draft%20v1.0/Specification.md#74-validation)
  * [7.5 Editing and Rendering](/Draft%20v1.0/Specification.md#75-editing-and-rendering)
* [8 Glossary](/Draft%20v1.0/Specification.md#8-glossary)
* [9 References](/Draft%20v1.0/Specification.md#9-references)
* [10 Postface](/Draft%20v1.0/Specification.md#10-postface)
  * [10.1 Authors](/Draft%20v1.0/Specification.md#101-authors)
  * [10.2 Acknowledgments](/Draft%20v1.0/Specification.md#102-acknowledgments)

## Participate

You may:

1. Create an [issue](https://github.com/openpreserve/sheets-preservation-spec/issues/new) to describe and discuss any changes.
2. Send a Pull Request (PR) to resolve issues in the latest in-development version. The PR will undergo review before approval.

## Partners

The following organisations are strategic partners, benefactors and co-creators in the creation of this specification and the OPF ODF Validator.

* [Danish National Archives](https://en.rigsarkivet.dk/)
* [National Archives of the Netherlands](https://www.nationaalarchief.nl/en)
* [National Archives of Estonia](https://www.ra.ee/en/)