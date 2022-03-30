# FLExExport
Format LibreOffice export of FLEx texts in the desired way

We are working on a collection of texts with interlinear glossing and various associated fields that store information about the sources and interpretation of each text, for an indigenous dormant language.  The texts come from archival sources, from earlier linguists who worked with fluent speakers in the 19th and 20th centuries.

We use Fieldworks Language Explorer (FLEx) v. 9 to parse the texts and maintain the information.  We export the texts from FLEx to LibreOffice format, format and add page numbers in LibreOffice, and then export to pdf to create versions of the texts that are easily readable to humans, similar to a book of texts with translations.  The intended audiences are community members of the language community and linguists who might want to analyze some feature of the language.

There are three crucial changes to the text exports from the basic FLEx setup:
1. We want to add labels in front of the various free translation and literal translation fields in the export.  We want to be able to edit these labels to make them easy for the reader to understand.  We use the free and literal translation fields in various writing systems (languages) as additional fields in FLEx to store the various kinds of information our project needed.  This is accomplished by adding a section in the `xml200.xsl` file.

1. We want to assign the free and literal translation fields of a particular language encoding to different styles in the LibreOffice output, so that they can be formatted differently from each other.  For example, free English and literal English should not be assigned the same style.  This is accomplished by adding a section in the `xml200.xsl` file to designate that free and literal translation fields receive different styles, and by adding those new style names to the `xml200Styles.xsl` file.

1. We want to change various parameters of the styles that are assigned to various fields, for example to change which field is bold and change some font colors.

The only files modified from the original installation of FLEx are `xml200.xsl` and `xml200Styles.xsl`.  These have to be placed in
```
C:\Program Files\SIL\FieldWorks 9\Language Explorer\Export Templates\Interlinear
```
to work.
