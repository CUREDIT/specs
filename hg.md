# HG Extension Developer Specs

## Bookmarks

Browser bookmarks and bookmark changes need to be provided as an observable stream via the hg-lib

1. Hold bookmarks in memory
2. Position bookmark sub-folders before URLs
3. Provide search, sort, open for bookmarks
4. Provide bookmarks MarkTown card UI
5. Provide option to explode a bookmark folder
6. Provide option to convert a bookmark folder to a playlist
7. Provide option to export and share playlists
8. Update bookmarks on created, removed, changed
9. Update bookmarks on reordered, moved, import
10. Provide bookmarks CRUD UI
11. Bookmark all selected or all opened tabs
12. Create a MarkTown feed of bookmark cards

## Tabs

Browser tabs and tab changes need to be provided as an observable stream via the hg-lib

1. Provide a counter badge for number of open tabs
2. Create a playlist from currently open or selected tab openings

## Playlists

1. Group URLs of a domain under a single parent node with the domain as an abstract MarkTown card
2. The tab from which a new tab is created is a concrete parent node of the new tab
3. The sibling nodes are ordered by their creation time and grouped by their concrete parents
4. Previous and Next load previous and next siblings not individual tabs

## Recipes

1. Form fill up recipes
   * Semantic annotations and content provided in template MarkTown cards
   * Login and payments not yet planned, will possibly use .kdbx
2. Link explosion recipes
3. Scroll and click recipes
4. Hybrid recipes
