Blink-Tree is build on a top of [[B star - tree]] (B\*tree)and add [[Node high keys]] and [[Sibling links]] pointer. 
Blink-Tree allow a ==half-split== state - when a new node already referenced by [[Sibling links]] but not by child link from parent.  That node has broken invariant - the high key is less then a search key, therefore, it is a sign we need to switch to the next sibling.
The pointer has to be quickly added to the parent guarantee the best performance and the search process doesn't have to be restarted.
The advantage here is that we do not have to hold the parent lock when descending to the child level.
![[Blink-Trees 2024-06-27 22.12.40.excalidraw]]
