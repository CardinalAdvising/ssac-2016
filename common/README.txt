CARDINALREPORT README
BT, 8/17/2015 

== Source files ==
- The cardinalreport.cls class defines a Latex template for creating reports branded for Cardinal Advising for the use with R Markdown documents.
- Additional parameters are set in the default.tex file used by the Pandoc compiler for parsing YAML-based .rmd files, and the .rmd file itself that also specifies the content of the report. The .rmd file references the template  file in the YAML header (documentclass: cardinalreport).
- The .cls file and the .tex file require other Latex packages to work properly; install all packages the compiler asks.
- The .rmd file and the .cls file should be kept in the same local directory, or the .cls file moved to the directory where the other Latex class files are (~\texmf\tex\latex\). Remember to  update the global package database so that the Latex compiler can find it.
- The default.tex file should be in the ~\USER\Documents\R\win-library\3.2\rmarkdown\rmd\latex\ directory or somewhere similar, depending on the version of the RStudio.
- The .rmd source file can be renamed and modified but the cardinalreport.cls file and default.tex should not be changed.

== Comments ==
- Comments in the .rmd files are set between <!-- and --> tags
- YAML fields in the .rmd header cannot contain comments or empty lines and need to be indented as is.

== Title ==
- The title and subtitle of the report are set in the title and subtitle YAML fields in the .rmd file.
- The (shorter) title for the report to be used in the document header can be set in the .rmd file header-includes YAML  field.

== Author ==
Authors, their titles, affiliation and e-mail are set in the author YAML fields in the .rmd file. Each author should be on a separate indented line that starts with a | and a space. Author names are formatted bold by a Latex command.

== Date ==
Set in the date YAML field.

== Logos ==
The names of the image files and their paths (if located in a different directory) are set in the companylogo and clientlogo YAML fields.

== Formatting ==
- Font size can be changed to 10, 11 or 12 points in the fontsize YAML field.
- linkcolor, citecolor and urlcolor YAML fields define colors for linked text.
- Colors themselves are defined *after* the .rmd header (after the --- line) by \definecolor commands. The RGB values for the red and gray of the Cardinal Advising logo are 209,72,37 and 123,121,121. ColorOne is used in titles and links; ColorTwo is used in subsection titles.

== Sections ==
Sections can be numbered or un-numbered; this is specified in the output:pdf_document:number_sections YAML field.

== Table of Contents == 
Table of Contents is included in the report if the value of the toc YAML field is yes and excluded if the value is no. 

== Bibliography ==
Bibliography is included if the last chapter of the .rmd file is # References and excluded otherwise. The name of the bibliography database (a .bib file or similar) needs to be specified in the YAML field. A sample bibliography file is included with deliverables.

== Executive Summary == 
Executive summary is defined in the abstract YAML field, it can be excluded by leaving it out from the YAML field.

== About the Authors ==
The content for the section is specified in the include-after YAML field. The title of the section is in {curly brackets} and can be changed. The \\-marks denote line breaks.

== Watermarks ==
- Watermarks are defined by the \newwatermark command after the .rmd header YAML fields.
- To use no watermarks:
Delete or comment out the \newwatermark command
- To change watermark color, size, text: 
\newwatermark[allpages,color=ColorOne!85,angle=45,scale=6]{CONFIDENTIAL}
- To include watermarks on some pages only: 
\newwatermark[pages=2-10,color=gray!15,angle=45,scale=3]{DRAFT}
- To use image watermarks: 
\newwatermark[allpages,angle=45,scale=0.5,xpos=0,ypos=0]{\includegraphics{cardinallogo.png}} 

