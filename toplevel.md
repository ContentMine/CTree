#toplevel directory of `CTree`


This is the toplevel of a `CTree` and hs no reserved name. 

##name

ISSUE should there be reserved syntax? 

Currently the name is created by:
 * `getpapers`explicitly using `-o `*outdir*
 * from `quickscrape` converting an input URL into a directory name (`http_www_foo_com_bar_plugh`). ISSUE do filename pengths matter?
 * from local files converted by `norma` , e.g. `/usr/bar/foo.pdf` => `_usr_bar_foo` (and `fulltext.pdf`)
 * bespoke creation (?)
 
##non-directory files

`toplevel` MUST only contain reserved filename and directory names.

### fulltext.pdf
raw PDF for main text of document

### fulltext.html
raw HTML for main text of document. Often cluttered with non-content from publishers

### fulltext.txt
raw TXT for main text of document. Very little can be guranteed from this.

### fulltext.xml
raw XML. This MUST be well-formed. However some publishers fail to resolve namespace prefixes and these may need to be deleted.
This MAY have a DTD. This causes problems as some parser will try to retrieve it and may fail if they cannot download it. The system MAY have the power to delete DTD declarations.


