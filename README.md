Specifications for curedit ecosystem components

## BreakDown 

A meta package containing various CUREDIT editors. 

### MarkTown

GF Markdown and Asciidoc based hyperlink card editor with ConText annotation support

1. Accepts gfm or asciidoc hyperlinks with Context annotations. 
2. A hyperlink always has a default annotation block unless a specific one is specified. 
3. When n hyperlinks are provided but only one annotation block is provided, the node can be exploded to n nodes with the 1 hyperlink each and the same annotation block in each node. 
4. When n hyperlinks are provided but only m of the n links have their own annotation blocks each, only those m links can be separated into m new nodes. 
5. A hyperlink card has title and description and may have content preview(s), image and icon. 

### TreeKey

An editor for trees of URL based keys and MarkTown based annotated content



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
