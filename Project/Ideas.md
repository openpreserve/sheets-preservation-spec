# Ideas
Below is a list of possible validation checks to consider.

**List of ideas**
- [ ] Font embedding: The file **MAY** have fonts embedded.
- [ ] Chart to image: The file **SHOULD** have charts converted to an image file format.
- [ ] Change CSV file format standard to “CSV Schema Language 1.1": http://digital-preservation.github.io/csv-schema/csv-schema-1.1.html
- [ ] ODS thumbnails: The file **SHOULD NOT** have embedded thumbnails.
- [ ] Only allow ODS extension: The file **SHOULD NOT** have extensions ".fods" and ".ots"
- [ ] IsDocumentShared: The file **SHOULDT NOT** have XML attribute "IsDocumentShared" in settings.xml set as true