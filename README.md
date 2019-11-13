# PaperSizes
**PaperSizes** contains structured data relating to common paper sizes, such as A3, A4, Letter, 
Tabloid, Legal, etc.

The need to essentially recreate Visio's drop-down lists of page sizes has come up in a few of 
the projects I've worked on, so I decided to create my own list.

In my research, I found a few other standards that aren't built into Visio, but may be useful 
in any application that needs to have pick lists for paper sizes.

The data is not inherently Visio-specific, but there are a few attributes that are Visio-specific, 
such as **DrawingSizeType**, **VisUnitCode** and **BuiltIn**. If you're working outside of Visio, you could ignore or remove these elements.

#Structure
Whether you use the XML or the JSON, the structure is essentially as below. The italicized items are Visio-specific:

* PaperSizes
  * PaperSize
    * Name
    * Category
    * *DrawingSizeType*
    * *VisUnitCode*
    * Units
    * Width
    * Height
    * *BuiltIn*

Categories include:
* Standard
* Metric (ISO)
* ANSI Engineering
* ISO B Sizes
* ISO C Sizes
* British Imperial
* JIS

There are repeated items located in different categories, since some page sizes have multiple names in different standards. 
There is no data related to page orientation, since it is easy enough to determine landscape or portrait orientation.

## TODO
* There is an inconsistency in the categories **Metric (ISO)**, **ISO B Sizes**, and **ISO C Sizes**. The 
first item is named after the drop-down entry in Visio's Page Setup dialog. You may wish to alter these
category names for consistency.
* The JSON file doesn't contain any of the comments that are in the XML file. This may be good or not good,
depending on your perspective.
* Changes to one file should be made in the other. I'm not sure if GitHub has some facility for generating
files from other files. Of course an online converter was used to generate the JSON from the original XML.

