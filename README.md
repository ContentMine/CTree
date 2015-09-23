# CTree

Design specifications for ContentMine `CTree` and `CProject`. 

## CProject

A `CProject` is set up by a local user or a program run by them and will contain `CTree`s . Generally this maps onto operations such as:

 * downloading one or more papers (+ supplemental) with `getpapers` or `quickscrape`.
 * processing a collection of papers already on a user's disk.

A `CProject` will often have a purpose such as:
 * a daily trawl through the literature (e.g. `daily_20150102`)
 * a retrospective crawl of a publisher (`bmc2012-4`)
 * a query (`brontosaurus_2013`)

### spec
 * `CProject's are based on standard filesystem directories.
 * `CProject`s can be set up anywhere on a users disk. 
 * ISSUE. SHOULD they have reserved syntax? e.g. `c_foo`
 * ISSUE. `CProject` filenames should be <= 20 characters and contain only `[A-Za-z][A-Za-z0-9_]. This is to prevent spaces, OS-dependent chars, and support processability with software. Also long filenames may cumulatively be problematic for ZIP.
 * `CProject` MUST have a `manifest` (the files they contain and when they were created/modified)
 * `CProject` MUST have an audit trail (including provenance for legal purposes - when, from where and by what were they created)
 * `CProject` MAY contain 0 or more `CTree`s
 * ISSUE `CProject` MAY / MUST_NOT contain files other than the above.
 * ISSUE `CProject` MUST NOT contain `CProject`.
 
 ### creating `CProject`s
 
 * from a `getpapers` search
 * from a `quickscrape` on a single URL
 * from a `quickscrape` with a list of URLs or a generator of URLs
 * from a list of files on disk (e.g. `*.pdf`). Using `norma`. Files must all be of the same type (*.pdf) OR *.html or *.txt
 * as an empty `CProject.
  

### programs consuming / emitting `CTree` s

 * `getpapers` (output)
 * `quickscrape`  (output)
 * `norma` (input and output)
 * `ami` (input and output)
 * `cat` (input)
 * `canary` (input)
 * `facts`, `bubbles` (aggregated input)
 
 
## `CTree`

A `CTree` is set up by a local user and will contain reserved filetyoes . A `CTree` represents a single logical document (often with multiple physical documents). The archetype is a static document (i.e. mainly for reading and transforming) which will not undergo significant or repeated change. Examples can be:

* a scholarly article, with associated supplemental files
* a thesis
* a book
* a report

`CTree`s are generally not suitable for:
 * web-pages
 * collections of distinct logical objects (e.g. a set of textbooks)
 * dynamically updated notebooks

`CTree`s are often subjected to repeated and varied transformations. The result of each transformation is normally a new file within the `CTree` directory tree. ISSUE should there be provision for versions? or should a new `CTree` be created?

### components

`CTree` consisten of reserved files and directories. Most have hardcoded names, but others will be determined by options in the creating program. Currently:

 * toplevel directory
 * supplemental directories
 * `pdf` directory
 * `svg` directory
 * `image` directories
 * `results` directory
 * `expected` directory
 
These are explained below.

#### toplevel 


### spec
 * `CTree's are based on standard filesystem directories.
 * `CTree`s MAY have a `CProject` parent. ISSUE MUST?
 * ISSUE. SHOULD they have reserved syntax? Currently they are often generated from URLs or filenames.
 * 
 
