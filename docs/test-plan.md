# Testing, and Process
I created a chart for my input, and output behavior for progression 4 to the testing phase of my project. By testing through each section of the output by what actions I took, and how the program responded. Whether each test worked correctly. And, then explaining how each function goes through activities such as empty queues, and error cases. To prevent duplicate tracking numbers, and invalid weights

## My Recording Chart, and Program Output
```
| #  | Test Item                          | Action / Input                          | Expected Result                          | Actual Result                              | Pass/Fail |
|----|-------------------------------------|-----------------------------------------|------------------------------------------|-------------------------------------------|-----------|
| 1  | First Package Added             | Option 1 → PKG101, Jane Smith, 1.1          | Added with status Waiting                | Added with status Waiting                  | Pass      |
| 2  | Add packages + verify FIFO         | Add PKG1001–1003, process twice         | Processed in order added                 | PKG1001 → PKG1002 → PKG1003                | Pass      |
| 3  | Reject duplicate tracking number   | Option 1 → existing PKG1001             | Error, package not added                 | “Tracking number already exists”           | Pass      |
| 4  | Reject invalid weight              | Option 1 → weight -5                    | Error, package not added                 | “Weight must be greater than zero”         | Pass      |
| 5  | Process next package               | Option 2                                | Status changes to Processed              | Waiting → Processed                        | Pass      |
| 6  | Process empty queue                | Option 2 (queue empty)                  | Empty queue message                      | “No packages are waiting”                  | Pass      |
| 7  | Search existing + missing          | Option 3 → PKG1001 then PKG9999         | Found no found messages               | Found + details / “Package not found”      | Pass      |
| 8  | Verify hash + linear search        | Option 3                                | Both methods return same result          | Both found + complexity shown              | Pass      |
| 9  | Valid status transitions           | Option 4 twice                          | Processed → In Transit → Delivered       | Processed → In Transit → Delivered         | Pass      |
| 10 | Reject invalid status transition   | Option 4 on Delivered package           | Transition rejected                      | “Already been delivered”                   | Pass      |
| 11 | Display waiting queue              | Add 2 packages → Option 5 twice         | FIFO order, queue unchanged              | FIFO shown, queue unchanged                | Pass      |
| 12 | At least two sorted reports        | Option 7 → Tracking number and Weight   | Correct sorted lists                  | Sorted correctly + insertion sort noted    | Pass      |
| 13 | Original collection after sorting  | After sort → Option 6, and 3            | Original data is accurate              | Original data and lookup still correct     | Pass      |
| 14 | Summary with packages              | Option 8 after several packages         | Correct counts and weights               | Correct totals, average, heaviest          | Pass      |
| 15 | Summary with no packages           | Option 8 on empty system                | Total 0, N/A values, no crash            | Total 0, Average/Heaviest = N/A            | Pass      |
```



### Step 1: Start the Program

I first start the program with all nine menu options that appear when running the program. To make sure that the menu functions are both valid, and invalid, and whether they are working correctly.

### Step 2: Add Packages

Then I add packages that use valid information to test duplicate tracking numbers, empty fields zero or negative weight, and non-numeric weights to make sure the data is accurate. This is also to check invalid entries are rejected, and valid packages are added to the Waiting Status.

### Step 3: Test FIFO Processing

When the queue is empty I test processing after adding multiple packages, to process them sequentially. Then looking at the message appearing in an empty queue so the packets are processed for First-In, First-Out order, and their statuses change to process.

### Step: 4: Searching for Test Packages

I use linear search, and hash-table lookup to discover tracking numbers that are both present, and nonexistent. These approaches helped me locate the current packages, and identify, what is missing.

### Step 5: Test Package Status Updates

Once the packages are updates from Processed to In Transit, are finally at Delivered. I test for invalid status transitions as well. Observing when invalid transitions are rejected, and valid transitions are accurate.

### Step 6: Display Waiting Packages

I show that the Packages are waiting without processing any Packages observing the waiting queue twice. Making sure that packages stay in FIFO order, and are not eliminated by showing the queue.

### Step 7: Display Packages

After adding, and processing records in different delivery statuses, I represent every shipment. So each package will reveal its current state, and information.

### Step 8: Generate Sorted Reports

I create reports that are arranged by tracking number, receiver, and weight to verify the initial collection. So the reports maintain the original vector, and hash-table indexes while conforming to the chosen sorting order.

### Step 9: Calculate System Statistics

I look at the total weight, average weight, and delivery status totals, package counts, and the heaviest package. Checking whether the system is empty. So that the statistics for empty collections are handled without division by zero.

### Step 10: Verify Search, and Sorting Complexity

Then I verify whether the sorting functions, and search confirm that the program uses intended algorithms as a result for linear search that's O(N), O(1) for hash-table lookup, O(N^2) for insertion sort, and O(N^2) for selection sort

### Step 11: Final Verification

I rebuild, and execute the program covering the key features, and examining what is necessary for the program to compile.
