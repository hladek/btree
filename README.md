# btree
B tree for effective integer array to value mapping.

Designed for usage in natural language processing tools.

C++ header only library designed for counting word n-grams

Features:
- suitlable for large number of items
- integer key
- arbitrary value
- key and value size is set at allocation
- zero copy for keys and values
- reduces memory fragmentation and has small memory overhead
- serialization and deserialization to disk


Requirements:
C++ compiler

Usage:
```c++
#include "btree.h"

// Create map for one integer to one double
BtreeMap btm(1,sizeof(double));
int k = 1;

// Insert key and value
pair<bool,BtreeIterator> it = btm.insert(&k);
it.second.double_value()[0] = 1;

// Search for key
k = 2;
BtreeIterator it2 = btm.find(&k);
if (it2.has_value()){
  cout << "Found key 2" << endl;
}

// Save to disk
ofstream of("mymap");
mtm.serialize(of);
```
