
[[Blink-Tree]] add a Kn+1 key to each node. It specifies an upper bound of keys that can be stored in the subtree to which the pointer Pn points. And therefore an upper boundof values that can be stored in the current subtree.


| P0  | K1  | P1  | ... | Kn  | Pn  |
| --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     |
[[B-tree]] without a high key


| P0  | K1  | P1  | ... | Kn  | Pn  | Kn+1 |
| --- | --- | --- | --- | --- | --- | ---- |
|     |     |     |     |     |     |      |
[[B-tree]] with a high key