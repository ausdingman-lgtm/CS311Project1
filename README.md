# CS 311 Project 1: The Speed Cache

Thread-safe LRU cache using a hash map plus a doubly linked list.

**Author:** [Your Name]

## Requirements

Python [version], standard library only.

## How to Run

```
python -m unittest test_lru.py
python simulate_hitrate.py
python verify_project1.py
```

## Files

- `doubly_linked_list.py`: list with head/tail sentinels
- `lru_cache.py`: `LRUCache` with `get`, `put`, and a lock
- `test_lru.py`: unit and stress tests
- `simulate_hitrate.py`: hit-rate simulation
- `DESIGN.md`: design sketch

## Complexity

- `get`, `put`, eviction: O(1). One dict lookup plus a fixed number of pointer changes through a direct node reference. No scanning.
- Thread safety: one `threading.Lock` around the full body of `get` and `put`.

## Hit Rates

| Capacity | Hit rate |
|---|---|
| [ ] | [ ]% |
| [ ] | [ ]% |
| [ ] | [ ]% |

[One or two sentences on why the hit rate changes with capacity.]

## Success Token

[paste token]
