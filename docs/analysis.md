# Analysis, and Reflection

There are three primary data structures used by the Package Delivery Tracking System. The first is an unordered map used for effective tracking-number look-ups as a vector to store package records, and a queue for processing shipments in First-In First-out order. While the hash table lookup for averages O(1), and can approach O(N) in worst case since linear search has O(N) time complexity. While insertion sort, and selection sort would require O(N^2) time queue insertion, and removal take O(1). To maintain the original records, and their hash-table indexes so the program can sort, and copy the package collection. This project helped me understand to maintain consistent package information through applying searching, and sorting techniques to choose a suitable data structure. I also reflect on the software functions. Recognizing why it is important to test invalid inputs, and duplicate tracking numbers such checking empty queues, and status updates.

## Steps To Each Analysis

### Step 1: Linear Search
We use Linear search to check pages each time until it finds the matching tracking number. Because of Time complexity is O(N) the amount of time will be necessary to grow the number of packages.

```cpp
for (const auto& package : packages)
```

### Step 2. Hash Table Lookup
The program will use
```cpp
std::unordered_map
```
To track numbers to find a package without looking at every record we look at its average time complexity is O(1). Meaning the worst-case complexity is O(N) because of collisions.

### Step 3: Queue Complexity 
When we process queues based on *First In, First Out, and FIFO* are used to process the queue. So it would take O(1) time to add, and remove packages from 
```cpp
std::queue
```

### Step 4: Sorting Algorithm
I used Bubble Sortion to arrange packages based on their tracking numbers. So both average, and wort scenarios is time complexity *O(N^2)*

### Step 5: Sorting a Copy
So Instead of altering the original records in the program. We sort a copy of the package collection. This protects hash-table relationships, and the original package information.

