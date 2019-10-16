# wd_property_paths

In Wikidata there are many different paths that can be used to define an item by a SPARQL query.
[(Info on path queries here)](https://www.w3.org/TR/sparql11-property-paths/)

For example does something need to be an `instance_of` (`wdt:P31`) a disease in order to be considered a Disease?
Would an item that's a `subclass_of` (`wdt:P279`) another item that's an `instance_of` disease also be considered
a disease? (`?item wdt:P279/wdt:P31 wd:Q12136` e.g. dysentery (Q129279), `subclass_of`  colitis (Q2453464)
`instance_of` Disease). What about an item that's an `instance_of` a concept,
which happens to be a `subclass_of` diseaase? (`?item wdt:P31/wdtP279 wd:Q12136`, e.g
Human papillomavirus infection (Q184627) `insance_of` infectious disease (Q18123741) `subclass_of` Disease).

How many `subclass_of` edges are acceptable to traverse in a path? These answers are not obvious.

In these two notebooks, we attempt to look at many biological concetps and see how the results of path queries
differ, and specifically, we will look at Diseases to find examples that only certain path queries will produce.
