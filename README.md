Specifications for curedit ecosystem components

## BreakDown 

A meta package containing various CUREDIT editors. 

### MarkTown

A GF Markdown and Asciidoc based hyperlink card editor with ConText annotation support

1. Accepts gfm or asciidoc hyperlinks with ConText annotations. 
2. A hyperlink always has a default annotation block unless a specific one is specified. 
3. When n hyperlinks are provided but only one annotation block is provided, the node can be exploded to n nodes with the 1 hyperlink each and the same annotation block in each node. 
4. When n hyperlinks are provided but only m of the n links have their own annotation blocks each, only those m links can be separated into m new nodes. 
5. A hyperlink card has content's title and description and may have content preview(s), image and/or icon in the default annotation block. 
6. A default annotation block can be extended using the types of annotations that the Orb UI generates 

### TreeKey

An editor for trees of URL based keys and MarkTown based annotated content

1. A root node always has a MarkTown hyperlink (Content type) node child and, its dual, an annotations (Context type) node child and therefore the two corresponding edges. 
2. A root node always is in a hyperedge that contains related root node(s) and, its dual, a hyperedge that contains its corresponding meta-root node(s). 
3. A meta-root node may contain comparison, ordering and root node relation based standard semantic annotations. 
4. A meta-root node may contain abstraction semantics and thus correspond to one or more root nodes implementing all the constraints from the abstraction(s). 
5. A non-root node of Content type or its successor is implicitly ordered by its depth in the tree and therefore may share its linear embedding position with other nodes. 
6. A non-root node of ConText type or its successor is implicitly ordered by its annotation coordinates and can never share its n-dimensional matrix index e.g. a Maven artifact would have a 3 dimensional coordinate system with groupId, artifactId and version axes where each axis is naturally ordered. 

## ConText

Text based annotations support for additional semantics.

### Orb UI annotations

Radial context menu for generating annotations based on

- [ ] Long, lat, alt, radius selection
- [ ] Time, date, specific day (by cultural name) selection
- [ ] Velocity, linear accln ranges
- [ ] Weather metrics
- [ ] Ambience - light, noise, weather, [pollution?]
- [ ] Battery level, wifi, mobile data
- [ ] Health metrics
- [ ] Preferred incoming/outgoing annotations



### n-Graf Mod

URI based automation mods, see gitlab repo Readme for full API description 



## h-Graf Mod

Hypergraph KB mods 

### Hybridge API
GRAKN RIFs and SKOS for Graql + SPARQL

### MAMBA
- [ ] T-Pla
- [ ] X-Pla
- [ ] MTX-Pla
- [ ] MoOSE
- [ ] GVS
