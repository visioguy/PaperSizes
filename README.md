# PaperSizes
PaperSizes contains structured data relating to common paper sizes, such as A3, A4, Letter, 
Tabloid, Legal, etc. The size definitions include numerical sizes, units of measurement, categories, along
with some Visio-specific information that you may not need for your purposes.
  
For example:  
  
![Sample Paper Sizes](https://raw.githubusercontent.com/visioguy/PaperSizes/master/img/paper-sizes-sample.png)

The need to essentially recreate Visio's drop-down lists of page sizes has come up in a few of 
the projects I've worked on, so I decided to create my own list.

In my research, I found a few other standards that aren't built into Visio, but may be useful 
in any application that needs to have pick lists for paper sizes.

The data is not inherently Visio-specific, but there are a few attributes that are Visio-specific, 
such as **DrawingSizeType**, **VisUnitCode** and **BuiltIn**. If you're working outside of Visio, you could ignore or remove these elements.

## Sample Code
Here's a quick sample of how the paper size data is structured:  
```xml
<!-- XML Paper Sizes -->
<PaperSizes>
	<!-- Standard -->
	<PaperSize Name="Letter" Category="Standard" DrawingSizeType="2" VisUnitCode="visInches" Units="in" Width="8.5" Height="11" BuiltIn="true" />
	<PaperSize Name="Folio" Category="Standard" DrawingSizeType="2" VisUnitCode="visInches" Units="in" Width="8.5" Height="13" BuiltIn="true" />
```
```js
// JSON Paper Sizes:
{
  "PaperSizes": {
    "PaperSize": [
      {
        "name": "Letter",
        "category": "Standard",
        "drawingSizeType": "2",
        "visUnitCode": "visInches",
        "units": "in",
        "width": "8.5",
        "height": "11",
        "builtIn": "true"
      },
      {
        "name": "Folio",
        "category": "Standard",
        "drawingSizeType": "2",
        "visUnitCode": "visInches",
        "units": "in",
        "width": "8.5",
        "height": "13",
        "builtIn": "true"
      },
```

## Structure
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


