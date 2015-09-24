#Results

The results of searches or domain-specific transformation are stored in a the `results/` subtree. (The non-domain transformations - such as document -> document and image -> image are in subdirectories of `toplevel`)

##results/

This is created by `ami` and its plugins. 

***ISSUE***: can `results` ever be deleted. manually or automatically?

### `results/plugins`
`results` generally contains subdirectories created by `ami`. The original structure is 

```
    results/
        plugin1/
        plugin2/
        plugin3/
```
Generally the names of the subdirectories are the names of the plugin, e.g. `ami-species` generates `results/species`. Repeated runs with different plugins create new plugin directories. For example:
`ami-species` followed by `ami-gene` will create:

```
    results/
        gene/
        species/
```
***ISSUE***: At present a re-run of a plugin will overwrite the results. If the software has not been updated then the results should generally be the same (unless there is a stochastic element). However a new version could give different results. If we have:
```
    results/
        species1.2.3/
        species1.2.4/
        species2.0.1/
```
this would be precise, but possibly difficult to search for. Any log files should contain the version.

### `results/plugin/parameter`

In a similar way plugins may have parameters. Example:
```
ami-sequence --sq.type dna rna
```
would create:
```
    results/
        sequence/
            dna/
            rna/
```
and a further call of 
```
ami-sequence --sq.type dna rna
```
