#Examples of `CTree`s

These are existing `Ctree`s and in places fail to honour the draft spec, which may need to accommodate them.

## norma output in `norma/target/plosone/`

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

## images in `norma/target/images/`

CTree created from a single PNG image and OCR'ed with Tesseract. Original file was `ijs.0.003566-0-000.pbm.png`. 

***ISSUE***: cannot cope with more than one image per `CTree`

The OCR transformation is:
```
foo.png => foo.hocr => foo.svg
```

 * The HOCR is HTML from Tesseract, 
 * The SVG contains the coordinates, fonts/styles/sizes and words/phrases from HOCR.

```
ijsem_003566/    // CTree
└── image        // reserved directory
    ├── ijs.0.003566-0-000.pbm.png
    ├── ijs.0.003566-0-000.pbm.png.hocr
    └── ijs.0.003566-0-000.pbm.png.hocr.svg

```

## HTML transformation (`norma/target/ieee/`)

The XHTML are created from the non-well-formed HTML (a potentially lossy and corrupting process). Then
`scholarly.html` are created from XHTML.
```
ieee
├── 1196402
│   ├── fulltext.html
│   ├── fulltext.pdf
│   ├── fulltext.xhtml
│   ├── fulltext.xml
│   └── results.json
├── src_test_resources_org_xmlcml_norma_pubstyle_ieee_1196402_html
│   ├── fulltext.html
│   ├── fulltext.xhtml
│   └── scholarly.html
├── src_test_resources_org_xmlcml_norma_pubstyle_ieee_1196402edited_html
│   ├── fulltext.html
│   ├── fulltext.xhtml
│   └── scholarly.html
├── src_test_resources_org_xmlcml_norma_pubstyle_ieee_1196402site_html
│   ├── fulltext.html
│   ├── fulltext.xhtml
│   └── scholarly.html
├── src_test_resources_org_xmlcml_norma_pubstyle_ieee_1320344_html
│   ├── fulltext.html
│   ├── fulltext.xhtml
│   └── scholarly.html
```

## PDF ingestion (`cmine/target/project/theses1/`)

Directory `foo/` contained 3 theses.
```
├── HalThesis1.pdf
├── HalThesis2.pdf
└── smigaj.pdf
```
these have been ingested into new `CTree`s whose names are derived from the PDFs, and where the files
have been COPIED into `fulltext.pdf` without change.

```
theses1/
├── HalThesis1_pdf
│   └── fulltext.pdf
├── HalThesis2_pdf
│   └── fulltext.pdf
└── smigaj_pdf
    └── fulltext.pdf
```

