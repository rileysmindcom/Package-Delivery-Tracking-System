# Design - System Design

## Step 1: Package Record
We record the information contained to struct a package in the program. To keep the information of a single package together.
```cpp
struct Package {
    string trackingNumber;
    string recipient;
    string destination;
    double weight;
    string status;
};
```

### Step 2: Package Queue
The program uses the lines of
```cpp
std::vector<Package>
```
To store package records maintaining, and displaying the package collection with a vector

### Step: 3 Processing Queue
The program uses FIFO order for processing packages in the program by using
```cpp
std::queue
```
So the first package is processed, and added.

### Step: 4 Hash Table
We make a connection with the package locations in the vector by using
```cpp
std::unordered_map
```
To link the tracking numbers through searches making them efficient to find their results.

### Step: 5 Duplication Prevention
Before we determine whether the package's tracking number exists already before adding it. The program rejects the incorrect package information, and empty tracking numbers.

### Step: 6 Keep Consistent Data
The tracking numbers on *Pending Packages* are stored in the queue so the package records can be stored in the vector. So their records can be accessible through the hash table. Changes in the package status reflect on the primary collection.

### Step 7: Functions
We look at the functions whether they add packages, process packages, search, and update statuses, and show their results, and output responses by these functions in the program that divide each of their roles.

### Step 8: Sorting Reports
Packages are sorted by using many fields in the program such as weight, tracking number, recipient, and destination. To look at how these lines work together, and why each of their data structure works.

## Flowchart
<img width="582" height="411" alt="672738909-7d47bd11-d8ac-4f22-8fcc-06be020c2d3b" src="https://github.com/user-attachments/assets/1e936b4a-73a7-4d5c-81ad-45ff6d098f4d" />




