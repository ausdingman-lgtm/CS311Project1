# DESIGN.md

```
 self.map                         self.list
 --------                         ---------
 "a" ──────────────────────┐
 "b" ─────────────┐        │      head <-> [c] <-> [b] <-> [a] <-> tail
 "c" ──┐          │        │              ^MRU                 ^LRU
       │          │        │
       └──> Node c    Node b    Node a     (map values point at these nodes)
```
