SimpleScalar sim-outorder simulator with RRIP policy cache
===

We implement the 
**Static Re-Reference Interval Prediction with Hit Priority** (RRIP-HP) from the [ISCA'2010 paper][1]
in the _SimpleScalar_(http://www.simplescalar.com/) sim-outorder simulator.

Note:
NRU is also a degenerated case of RRIP (by setting the width of RRPV is 1).

## Configuration ##

Format:

```
<name> <nsets>:<bsize>:<assoc>:<width_RRPV>:<repl>
```

Cache replacement policy:
```
l: LRU;
R: RRIP;
r: Random;
f: FIFO;
```

Example:

```
 # l2 data cache config, 256KB, 64-byte line, 8-way, RRIP
-cache:dl2             ul2:512:64:8:3:R
```

## Compilation ##

```bash
make config-alpha
make clean
make sim-outorder
```


[1] Jaleel A, Theobald K B, Steely Jr S C, et al. High performance cache replacement using re-reference interval prediction (RRIP)[C]//ACM SIGARCH Computer Architecture News. ACM, 2010, 38(3): 60-71.