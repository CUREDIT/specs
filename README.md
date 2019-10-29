Specifications for curedit ecosystem components to 
transform file/web browsers to file/web editors

## Hg (Mercury)

Hg is a browser extension that manages your bookmarks and browsing session using media control semantics like 
* Record/Playlist
* Play/Pause
* Previous/Next
* Load/Buffer
* Save/Share/Delete 

Clicking 'Record' allows you to open as many links as you want without worrying about slow down, unresponsiveness or screen clutter. 
You could open 1000s of links thanks to lazy loading. You can see only a specified number (see Buffer) of tabs at once in your tab bar. You can still jump to any link from the session using the URL Playlist. 
A recording is saved as a bookmarks folder and the resulting shareable playlist can be viewed as a list, tree or map. 
Previous and Next buttons (un)load previous or next
- tabs into view and 
- links into buffered tabs

Simply delete the bookmarks or bookmark folders to delete links or playlists respectively. 
Share the playlist's generated URL to share the playlist. You can set your own domain as your playlist host. 

This extension is meant to showcase some of the capabilities of the components of the CUREDIT platform. Perhaps a refreshing browsing experience for you could be a happy side effect. Feedbacks are welcome, for both the extension and its building blocks. 


Settings:

- Buffer: Max number of tabs open in a recording session
- Exclusions: Pages to exclude from recording eg searches
- Playlist view: Linear, Tree, Map
- Playlists Host: Url to POST your playlists 


## BreakDown

A meta package containing a family of CUREDIT editors where the key-value pair of the root node of the tree being edited is a composite obtained from all its children nodes' key-value. 

````
type ConTree<T> = {
    key: URI;
    value: T;
    content: Array<ConTree<T>>;
    context: Array<ConTree<T>>;
}
````

### MarkTown: Array\<Card\>

````
type Card = {
  type: 'gfm' | 'markdown' | 'asciidoc';
  links: Array<{
    uri: URI, 
    text: string, 
    annotations: Array<ConText | string>
  }> 
} 
````


An editor for cards with GFMarkdown/Asciidoc based hyperlinks and ConText annotations

1. Accepts gfm or asciidoc hyperlinks with ConText annotations. 
2. A hyperlink always has a default annotation block unless a specific one is specified.
3. When n hyperlinks are provided but only one annotation block is provided, the node can be exploded to n children nodes with the 1 hyperlink each and the same annotation block in each child. 
4. When n hyperlinks are provided but only m of the n links have their own annotation blocks each, only those m links can be separated into m new nodes. 
5. A hyperlink card has content's title and description and may have content preview(s), image and/or icon in the default annotation block. 
6. A default annotation block can be extended using the types of annotations that ConText's Orb UI generates 

Notes:

1. One trivial use case would be link preview card generation. 
2. Other use cases like messaging and automation are explained in the projects below. 
3. A MarkTown card will be hereafter referred to as card (instance) or Card (type). 

### TreeKey: ConTree\<Card\>

An editor for trees consisting of nodes with URI key and MarkTown card value

1. A root node always has a MarkTown hyperlink (Content type) node child and, its dual, an annotations (Context type) node child and therefore the two corresponding edges.
2. A root node always is in a hyperedge that contains related root node(s) and, its dual, a hyperedge that contains its corresponding meta-root node(s). 
3. A meta-root node may contain comparison, ordering and root node relation based standard semantic annotations. 
4. A meta-root node may contain abstraction semantics and thus correspond to one or more root nodes implementing all the constraints from the abstraction(s). 
5. A non-root node of Content type or its successor is implicitly ordered by its depth in the tree and therefore may share its linear embedding position with other nodes. 
6. A non-root node of ConText type or its successor is implicitly ordered by its annotation coordinates and can never share its n-dimensional matrix index with another node e.g. a Maven artifact would have a 3 dimensional coordinate system with groupId, artifactId and version axes where each axis is naturally ordered. 

Notes:

1. A card when converted into a TreeKey structure will be hereafter referred to as a playlist (instance) or Playlist (type). 
2. A Playlist is an atomic type for messaging and automation components of CUREDIT in the sense that reading (and slicing from the TreeKey store) on this immutable type is guaranteed to not cause any data races. 
3. A single card can be converted to a trivial playlist using preset defaults for root node and meta-root node. 

### Gredict: ConTree\<Playlist\>

An editor for trees consisting of nodes with a unique concept name key (hereafter referred to as a word) and TreeKey tree value (hereafter referred to as its meanings)

1. A root node key when composed from its children node keys may have a root node value entirely different from the composite of its children node values, unlike the case with that of Cards or Playlists.
2. Meanings may be defined semantically with ConText annotations and/or Hybridge API calls on words or behaviorally using ConText annotations on functions written in either any JVM language (when server side sandbox is available) or any transpile-to-JS language (when web embedding is available).
3. A word can be a sequence of natural language words, URNs, URIs or any custom unique identifier. 
4. Since a word is mapped to multiple meanings, a particular meaning (by context) is accessed by using a ConText ID and a set of applicable meanings (by structure) can be accessed by Content ID. 
5. Semantic annotations can be aggregated whereas behavioral annotations can be composed. 
6. A word in a semantic annotation can be further unfolded to fetch more semantically annotated words whereas a function in a behavioral annotation may output a lazily invocable reference to other behaviorally annotated functions, ad infinitum. 

Notes:

1. A trivial use case would be to create 
 * a natural language dictionary or
 * a x language to y language dictionary. 
2. A RAD or rapid prototyping tool can developed using a function dictionary. 
3. The components that follow are built using the approach in 1.ii and 2.


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

URI based automation mods, see gitlab curedit repo's Readme for full API description 

- [ ] Popup mode with detachable, draggable, autohiding media controls (prev, play/pause, next) and playlist selector
- [ ] Context menu with prev, play/pause, next and add page options
- [ ] Bookmarks to watched folders (set in settings) are automatically added to a playlist of the folder's name
- [ ] Options page displays TreeKey UI 

## h-Graf Mod

Hypergraph KB mods using the Gredict UI

### Hybridge API
GRAKN RIFs and SKOS for Graql + SPARQL

### MAMBA
- [ ] T-Pla
- [ ] X-Pla
- [ ] MTX-Pla
- [ ] MoOSE
- [ ] GVS
