# DESIGN.md

```
 self.map
 "a" ──────────────────────┐
 "b" ──────────────┐       │
 "c" ──────┐       │       │
           │       │       │
           v       v       v
 head <-> [c] <-> [b] <-> [a] <-> tail
           MRU                   LRU
```
