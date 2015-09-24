#toplevel directory of `CTree`


This is the toplevel of a `CTree` and hs no reserved name. It is normally a child of a `CProject` and has `CTree` siblings.

##name

ISSUE should there be reserved syntax? 

Currently the name is created by:
 * `getpapers`explicitly using `-o `*outdir*
 * from `quickscrape` converting an input URL into a directory name (`http_www_foo_com_bar_plugh`). ISSUE do filename pengths matter?
 * from local files converted by `norma` , e.g. `/usr/bar/foo.pdf` => `_usr_bar_foo` (and `fulltext.pdf`)
 * bespoke creation (?)
 
`toplevel` MUST only contain reserved filename and directory names.


## raw files

### fulltext.pdf
raw PDF for main text of document

### fulltext.html
raw HTML for main text of document. Often cluttered with non-content from publishers

### fulltext.txt
raw TXT for main text of document. Very little can be guranteed from this.

### fulltext.xml
raw XML. This MUST be well-formed. However some publishers fail to resolve namespace prefixes and these may need to be deleted.
This MAY have a DTD. This causes problems as some parser will try to retrieve it and may fail if they cannot download it. The system MAY have the power to delete DTD declarations.

## transformed files

### scholarly.html
Created from raw XML, HTML - possibly PDF.
This is the primary input into `ami` and is [described here](https://github.com/ContentMine/CTree/blob/master/scholarly_html.md)

### fulltext.pdf.txt
A fast conversion of PDF into Text. Results and usefulness depend heavily on the formatting of the PDF (e.g. 2-columns may run into each other).

## metadata files
 
### `results.json` . 
Metadata extracted with `quickscrape` downloads. Typically includes 
 * presence of reserved files
 * certain metadata in HTML headers e.g. authors, licence, 
 * 
*ISSUE*: Should this continue to be called `results.json`?

*ISSUE*: Should the contents only be created by `quickscrape`?



## subdirectories (see CTree) 


