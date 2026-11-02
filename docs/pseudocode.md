# Pseudocode, and Algorithms
*We use steps for the program to list out before displaying the information.*

### Step 1: Adding Packages
We add the tracking number, recipient, destination, and weight from the users input, verifying information, rejecting tracking numbers that are duplicated, the package should be kept in the vector, and such as its tracking number in the hash table, and queue. Setting the initial status to waiting.
```cpp
packages.push_back(newPackage); packageIndex[trackingNumber] = packages.size()-1; processingQueue.push(trackingNumber);
```

### Step 2: Processing Packages
We check whether there are no packages in the queue. A message is showed if its empty. If not we take the package out of the front. By setting its status to Processed. And, then showing the details of the package.
```cpp
string tn = processingQueue.front(); processingQueue.pop(); findPackageByHash(tn)->status = "Processed";
```

### Step 3: Searching
We request a tracking number from the user. By using a hash table to conduct a search. If the package is present we display it. And, if not we show a *not-found* message
```cpp
Package* p = findPackageByHash(trackingNumber); if (p) displayPackage(*p); else cout << "Package not found.\n";
```
### Step 4: Updating Status
A tracking number is used for locating the package. For Permit In Transit to replace Processed, and Permit In Transit to be changed to Delivered. And, then rejecting changes in status that aren't valid.
```cpp
if (p->status == "Processed") p->status = "In Transit"; else if (p->status == "In Transit") p->status = "Delivered"
```

### Step 5: Displaying Waiting Packages
We create a duplicate of the queue, and its content shown in FIFO order. Without altering the initial queue.
```cpp
queue<string> temp = processingQueue; while (!temp.empty()) { displayPackage(*findPackageByHash(temp.front())); temp.pop(); }
```

### Step 6: Sorting Packages
We find out the field the user wants to sort. By making a copy of the package collection. By using a chosen sorting technique represented into a report that has been selected.
```cpp
vector<Package> sorted = packages; insertionSortByTrackingNumber(sorted); displayPackageList(sorted);
```

### Step 7: System Summary
Every package is counted to sort them in their status. Determining the average, and total weight. Then understanding which package is the heaviest. With safely handling a collection that is empty. 
```cpp
for (const auto& p : packages) { totalWeight += p.weight; /* count statuses & find heaviest */ }
```
