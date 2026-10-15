# CS 311 Project 1: The Speed Cache

Thread-safe LRU cache using a hash map plus a doubly linked list.

**Author:** [Austin Dingman]

## Requirements

Python [3.15.0], standard library only.

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
| [5] | [16.80]% |
| [200] | [86.54]% |


[A larger cache keeps more pages in memory before evicting them, so more repeat requests find their page still cached. The gains level off once the cache can hold all the frequently requested pages.]

[Running non-concurrent unittest suite (test_lru.py)...

  [PASS] unittest suite: 0 tests run, 0 failed

Running concurrency stress test (20 threads x 500 ops)...

  [PASS] concurrency stress test: no thread raised an exception
  [PASS] post-stress: list traversal reaches exactly as many nodes as map entries
  [PASS] post-stress: every list node is the exact mapped node and links agree
  [PASS] post-stress: cache never exceeded its capacity

Running hit-rate simulation sanity check...

  hit rate at capacity=5:   16.80%
  hit rate at capacity=200: 86.54%
  [PASS] hit rate improves as capacity grows

Enter your USI username (e.g. cwill): amdingman

============================================================
  ALL CHECKS PASSED -- PROJECT1
  STUDENT: amdingman
  SUCCESS TOKEN (paste this into Blackboard):
  Q1MzMTF8UFJPSkVDVDF8YW1kaW5nbWFufFBBU1N8YzA2N2ZkYWU1ZTRmNjRhMw==
============================================================]
