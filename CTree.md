# `CTree`

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

## components

`CTree` consisten of reserved files and directories. Most have hardcoded names, but others will be determined by options in the creating program. Currently:

 * toplevel directory
 * supplemental directories
 * `pdf` directory
 * `svg` directory
 * `image` directories
 * `results` directory
 * `expected` directory
 
These are explained below.

## spec
 * `CTree's are based on standard filesystem directories.
 * `CTree`s MAY have a `CProject` parent. ISSUE MUST?
 * ISSUE. SHOULD they have reserved syntax? Currently they are often generated from URLs or filenames.
 * 
 
 
