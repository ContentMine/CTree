# `results.xml`

The output of a search will normally be in `results.xml` as a great-grandchild of `results/`, e.g. 
```
  results/
    species/
      binomial/
        results.xml
```

## content

The content is (normally) a list of individual extracted ***entities in context***:
```
<?xml version="1.0" encoding="UTF-8"?>
<results title="binomial">
 <result pre="ntimicrobial activity (assessed on " wikipedia="3761158" match="Vibrio harveyi" post=" cultures) was 
     limited in both H an"/>
 <result pre="ia genus Vibrio, including; " match="Vibrio harveyi" post=" [ [14]], V. mediterranei [ "/>
 <result pre="luding; V. harveyi [ [14]], " match="Vibrio mediterranei" post=" [ [7]], V. owensii [ [15]] "/>
...
```
There is currently no namespace and no schema. The crude schema is:
```
    results
        result pre="foo" post = bar" match="V. harveyi" target="Vibrio harveyi" wikipedia="abc" ...
***ISSUE***: The attributes are messy and need normalising. Where regexes with named capture groups are used , 
we suggest using actual names and values (JSON-like):
```
species length="120cm" width="45cm"

There can be zero or many hundreds of lines. If a line contains two or more entities (as in the last Vibrios) the
entities will occur separately.

## domain-specific objects
At present some objects such as molecules may be emitted in `results.xml`
