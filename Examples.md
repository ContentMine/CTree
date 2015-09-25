#Examples of `CTree`s

These are existing `Ctree`s and probably fail to honour the spec

## norma output in `target`

```
// names are derived from PLoSONE DOIs
plosone
├── 0115884    // this is a single CTree without project
│   ├── fulltext.html
│   ├── fulltext.pdf
│   ├── fulltext.pdf.txt // created by PDF2TXT transformation
│   ├── fulltext.xml
│   └── results.json
├── multiple    // this is a CProject
│   ├── journal.pone.0077058
│   │   ├── fulltext.xml
│   │   └── scholarly.html  // transformed from XML
│   ├── journal.pone.0111303
│   │   ├── fulltext.html  // downloaded but not used
│   │   ├── fulltext.xml
│   │   └── scholarly.html // transformed from XML 
│   ├── journal.pone.0113556
│   │   ├── fulltext.html
│   │   ├── fulltext.tagged.html.xml  // hmm - not sure where this came from
│   │   ├── fulltext.tagged.xml       // tags added via stylesheet (I think)
│   │   ├── fulltext.xml
│   │   └── scholarly.html
│   ├── journal.pone.0115884
│   │   ├── fulltext.html
│   │   ├── fulltext.pdf
│   │   ├── fulltext.xml
│   │   ├── results.json
│   │   └── scholarly.html  // probably from XML (other files unused)
│   └── journal.pone.0115884a
│       ├── fulltext.formatted.xml // ? probably just for viewing
│       ├── fulltext.html
│       ├── fulltext.nodtd.html    // DTD stripped by norma as it adds seconds of lookup time
│       ├── fulltext.nodtd.xml
│       ├── fulltext.pdf
│       ├── fulltext.xml
│       ├── results.json
│       └── scholarly.html
```
