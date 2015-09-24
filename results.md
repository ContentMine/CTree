#Results

The results of searches or domain-specific transformation are stored in a the `results/` subtree. (The non-domain transformations - such as document -> document and image -> image are in subdirectories of `toplevel`)

##results/

This is created by `ami` and its plugins. 

***ISSUE***: can `results` ever be deleted. manually or automatically?

`results` generally contains subdirectories created by `ami`. The original structure is 

```
    results/
        plugin1/
        plugin2/
        plugin3/
```
General the names are the names of the plugin, e.g. `ami-species` generates `results/species`