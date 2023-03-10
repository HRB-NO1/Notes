## 1.Runtime Analysis
***Give the order of growth (as a function of N) of the running times of each of the following code fragments:***
```
# Block (a)
sum = 0;
n = N
while n > 0: 
    for i in range(0, n):
        sum += 1;
    n = n // 2


# Block (b)
sum = 0
i = 1
while i < N:
    for j in range(0, i):
        sum += 1
    i = i * 2

# Block (c)
sum = 0
i = 1
while i < N:
    for j in range(0, N):
        sum += 1
    i = i * 2
```
### ***python_script:***
```
import time
​
​
def time_convert(sec):
    mins = sec // 60
    sec = sec % 60
    hours = mins // 60
    mins = mins % 60
    print("Time Lapsed = {0}:{1}:{2}".format(int(hours), int(mins), sec))
​
​
# Block (a)
def block_a(N):
    sum = 0;
    n = N
    while n > 0:
        for i in range(0, n):
            sum += 1;
        n = n // 2
​
​
# Block (b)
def block_b(N):
    sum = 0
    i = 1
    while i < N:
        for j in range(0, i):
            sum += 1
        i = i * 2
​
​
# Block (c)
def block_c(N):
    sum = 0
    i = 1
    while i < N:
        for j in range(0, N):
            sum += 1
        i = i * 2
​
​
def calculate_time(N, block_number):
    start = time.time()
    if block_number == 'a':
        block_a(N)
    elif block_number == 'b':
        block_b(N)
    elif block_number == 'c':
        block_c(N)
    end = time.time()
    print("Time Lapsed = ", end - start)
    return end - start
​
​
while True:
    block = input("Which block do you want to run? (a, b, c), or q to quit: ")
    if block == 'q':
        break
    N = int(input("initial value of N: "))
    while N < 100000000:
        print("N = ", N)
        calculate_time(int(N), block)
        N = N * 2
```
### ***output:***
```
Which block do you want to run? (a, b, c), or q to quit: a
initial value of N: 50
N =  50
Time Lapsed =  0.0
N =  100
Time Lapsed =  0.0
N =  200
Time Lapsed =  0.0
N =  400
Time Lapsed =  0.0
N =  800
Time Lapsed =  0.0005102157592773438
N =  1600
Time Lapsed =  0.0
N =  3200
Time Lapsed =  0.0005116462707519531
N =  6400
Time Lapsed =  0.0005142688751220703
N =  12800
Time Lapsed =  0.0015649795532226562
N =  25600
Time Lapsed =  0.0030813217163085938
N =  51200
Time Lapsed =  0.006153106689453125
N =  102400
Time Lapsed =  0.012530803680419922
N =  204800
Time Lapsed =  0.025861740112304688
N =  409600
Time Lapsed =  0.052530527114868164
N =  819200
Time Lapsed =  0.10734415054321289
N =  1638400
Time Lapsed =  0.21431636810302734
N =  3276800
Time Lapsed =  0.4287128448486328
N =  6553600
Time Lapsed =  0.8500044345855713
N =  13107200
Time Lapsed =  1.6942682266235352
N =  26214400
Time Lapsed =  3.410715341567993
N =  52428800
Time Lapsed =  6.790171146392822
Which block do you want to run? (a, b, c), or q to quit: b
initial value of N: 50
N =  50
Time Lapsed =  0.0
N =  100
Time Lapsed =  0.0
N =  200
Time Lapsed =  0.0
N =  400
Time Lapsed =  0.0
N =  800
Time Lapsed =  0.0005273818969726562
N =  1600
Time Lapsed =  0.0
N =  3200
Time Lapsed =  0.0
N =  6400
Time Lapsed =  0.0005118846893310547
N =  12800
Time Lapsed =  0.001020669937133789
N =  25600
Time Lapsed =  0.001689910888671875
N =  51200
Time Lapsed =  0.004091978073120117
N =  102400
Time Lapsed =  0.009023189544677734
N =  204800
Time Lapsed =  0.017470359802246094
N =  409600
Time Lapsed =  0.0339808464050293
N =  819200
Time Lapsed =  0.06485772132873535
N =  1638400
Time Lapsed =  0.13858699798583984
N =  3276800
Time Lapsed =  0.2649369239807129
N =  6553600
Time Lapsed =  0.5348131656646729
N =  13107200
Time Lapsed =  1.079425573348999
N =  26214400
Time Lapsed =  2.1658883094787598
N =  52428800
Time Lapsed =  4.313527822494507
Which block do you want to run? (a, b, c), or q to quit: c
initial value of N: 50
N =  50
Time Lapsed =  0.0
N =  100
Time Lapsed =  0.0
N =  200
Time Lapsed =  0.0
N =  400
Time Lapsed =  0.0
N =  800
Time Lapsed =  0.0005078315734863281
N =  1600
Time Lapsed =  0.0015249252319335938
N =  3200
Time Lapsed =  0.0019085407257080078
N =  6400
Time Lapsed =  0.005141019821166992
N =  12800
Time Lapsed =  0.010999917984008789
N =  25600
Time Lapsed =  0.02350783348083496
N =  51200
Time Lapsed =  0.053063392639160156
N =  102400
Time Lapsed =  0.11086845397949219
N =  204800
Time Lapsed =  0.23626708984375
N =  409600
Time Lapsed =  0.5064866542816162
N =  819200
Time Lapsed =  1.0619900226593018
N =  1638400
Time Lapsed =  2.1911447048187256
N =  3276800
Time Lapsed =  4.60476279258728
N =  6553600
Time Lapsed =  9.570655107498169
N =  13107200
Time Lapsed =  20.005729913711548
N =  26214400
Time Lapsed =  41.6776008605957
N =  52428800
Time Lapsed =  87.81230282783508
```
## Analysis: 
![](https://coderzpy.com/wp-content/uploads/2020/08/WcBRI.png)

**Block (a) explanation: Inner loop: n/2 + n/4 + n/8 + ... + 2 + 1 = 2n-1. Outer loop: Log(n). Total = 2n-1+Log(n) = n. Thus O(n)**

**Block (b) explanation: Inner loop: 1 + 2 + 4 + 8 + 16 + ... + N/2(or a bigger number smaller than N) = 2n-1. Outer loop: Log(n). Total = 2n-1+Log(n) = n. Thus O(n)**

**Block (c) explanation: Inner loop repeats constant N times in each iteration. Outer loop iterate Log(n) times. Total = N*Log(N) = O(nlogn)**


## 2.Selection/Insertion Sort
***Show in the style of the example trace with selection sort, how selection sort sorts the array***

>Selection sort: Find the minimum element in unsorted array, and switch position between the first and the minimum element. 
>https://www.youtube.com/watch?v=xWBP4lzkoyM

>Insertion sort: Read from the beginning of unsorted array, insert the element to the correct position.
>https://www.youtube.com/watch?v=OGzPmgsI-pQ
![051a0139807912ad4ba64516d2f3d94](https://user-images.githubusercontent.com/54606160/225119514-30b63cfe-05eb-4984-8123-8418ac95b783.jpg)


**2.1 What is the maximum number of exchanges involving any particular item during selection sort? E A S Y Q U E S T I O N**

Worst case will be N-1. In this case 12 - 1 = 11

![08843551063dfb25723f8d4323d27d0](https://user-images.githubusercontent.com/54606160/223071918-91e17293-6bf0-445b-af31-6d189a5d7647.jpg)

**2.2 Show in the style of the example trace with insertion sort, how insertion sort sorts the array E A S Y Q U E S T I O N**

![61f3b6a8369c6767930cae45d4a6be8](https://user-images.githubusercontent.com/54606160/223069527-fbae98ce-58b3-4033-b26d-a1624d901a51.jpg)


**2.3 Which method runs fastest for an array with all keys identical, selection sort or insertion sort?**

Insertion sort runs faster, because it will take the first element of unsorted array and compare it with the sorted array once(compare only once with thelast element of sorted array).
Selection sorting takes more time because it will iterate through the unsorted array once in each iteration to find the smallest element.

**2.4 Expensive exchange. A clerk at a shipping company is charged with the task of rearranging a number of large crates in order of the time they are to be shipped out. Thus, the cost of compares is very low (just look at the labels) relative to the cost of exchanges (move the crates). The warehouse is nearly full: there is extra space sufficient to hold any one of the crates, but not two. Which sorting method should the clerk use?**

This situation will indicates that the cost of finding the smallest value is low. And the cost of moving large crates is high. So, selection sort will be a better choice because it only requires at most one swtich in each loop.

## 3. Mergesort  
**3.1 Describe in words why mergesort is a stable sort.**

Stable sort: If the relative positions of two equal numbers before and after sorting remain unchanged, the algorithm is stable. eg: Insertion sort
Unstable sorting: if the relative positions of two equal numbers before and after sorting change, the algorithm is unstable. eg: Selection sort
Mergesort is considered as stable sort.

**3.2 Give traces, in the style of the trace given in this section, showing how the keys E A S Y Q U E S T I O N  are sorted with top-down mergesort and with bottom-up mergesort.**
>https://www.baeldung.com/cs/merge-sort-top-down-vs-bottom-up#:~:text=Top%2Ddown%20merge%20sort%20begins,returns%20the%20merged%20output%20array.

![c3b0cec9639971e9e6f71b4a579b198](https://user-images.githubusercontent.com/54606160/223093007-b0ad38e9-a1d5-4c1c-b33e-c9012cd535a6.jpg)
![7f5a861f433485a660366e8c6fe3761](https://user-images.githubusercontent.com/54606160/223093026-737ce744-eb86-4c6c-a0d9-85b08f27138c.jpg)

## 4. Quicksort  
```
1. Choose the first element in the array as the pivot element.
2. Initialize two pointers, i and j. Set i to the second element (1 index) and j to the last element of the array.
3. Move pointer i from left to right until an element greater than the pivot is found.
4. Move pointer j from right to left until an element less than or equal to the pivot is found.
5. If i is less than or equal to j, swap the elements at positions i and j, and increment i and decrement j.
6. Repeat steps 3-5 until i is greater than j.
7. Swap the pivot element (which is at the beginning of the array) with the element at position j.
8. recursively sort the sub-array to the left of j and the sub-array to the right of j.

When array size is 2:
1. Choose the first element as the pivot.
2. Compare the pivot with the second element.
3. If the pivot is greater than the second element, swap the two elements. If the pivot is less than or equal to the second element, no action is needed.
4. Since the sub-array has only two elements and is now sorted, the recursion stops, and the algorithm moves on to other parts of the array.
```
**4.1 Show, in the style of the trace given with partition(), how that method partitions the array E A S Y Q U E S T I O N.**

![image](https://user-images.githubusercontent.com/54606160/225136778-456f680b-235c-4b23-99e1-fefe26c28b0d.png)

**4.2 Show, in the style of the quicksort trace, how quicksort sorts the array E A S Y Q U E S T I O N. (For the purposes of this exercise, ignore the initial shuffle.)**

![image](https://user-images.githubusercontent.com/54606160/225144627-0a49ecf3-cfac-4c09-a2ec-44a6efabc1ca.png)

**4.3 About how many compares will Quick.sort() make when sorting an array of N items that are all equal?**

if (<, >=) and first or last element as pivot, O(n^2)
if (<, >=) and median as pivot, O(n) < comparisons < O(nlogn)
if (<, =, >), O(n)

**4.4 Show, in the style of the trace given with the code, how the entropy-optimal sort first partitions the array B A B A B A B A C A D A B R A**

```
1. Choose the first element as the pivot (B).
2. Initialize three pointers: lt (less than), gt (greater than), and i (index). Set lt and i to the second element, and gt to the last element.
3. Process the array from left to right with the i pointer:
4. If a[i] is less than the pivot (B), swap a[lt] and a[i], increment lt and i.
5. If a[i] is equal to the pivot (B), just increment i.
6. If a[i] is greater than the pivot (B), swap a[i] and a[gt], and decrement gt (do not increment i in this case, as we need to examine the swapped element).

Initial array: B A B A B A B A C A D A B R A (pivot: B, lt: 1, i: 1, gt: 14)

A B B A B A B A C A D A B R A B (lt: 1, i: 2, gt: 14)
A A B B A B A B C A D A B R A B (lt: 2, i: 3, gt: 14)
A A B B B B A B C A D A B R A B (lt: 2, i: 6, gt: 14)
A A B B B B B B C A D A B R A B (lt: 2, i: 8, gt: 14)
A A B B B B B B B B C A D A B R A (lt: 2, i: 10, gt: 14)
A A B B B B B B B B B B C A D A R A (lt: 2, i: 12, gt: 14)
A A B B B B B B B B B B B B C D A R A (lt: 2, i: 13, gt: 13)

Less than pivot (B): A A
Equal to pivot (B): B B B B B B B B B B B B B B
Greater than pivot (B): C D A R A
```

**4.5 Bad partitioning. How does not stop on equal keys make quicksort go quadratic when all keys are equal? Give an example of this input.**

Not stop on strategy will divide the array into 2 different sizes sub-array(often). When encounter the array with all equal key, it will divide the array into size of n-1 sub-array and size 1 array like this: [1,1,1,1] [1], leading to recursion depth of n and n comapres per recursion, which is n^2

## 5. Heapsort  
**5.1 Criticize the following idea: to implement find the maximum in constant time, why not keep track of the maximum value inserted so far, then return that value for find the maximum?**

For example, there is a such unsorted array[3,2,1,4,5]
If track the maxium value of the recorded max number:
insert 3, max = 3
insert 2, max = 3
insert 1, max = 3
insert 4, max = 4
insert 5, max = 5
result = [3,3,3,4,5]
If seen 3 as the max value in the array, this will not creat a sorted array, but only get the max value of inputted array.
Thus this is not a contruction of a heapsort.

**5.2 Is an array that is sorted in decreasing order a max-oriented heap?**

Yes,  [9, 7, 5, 3, 1]
```
       9
     /   \
    7     5
   / \
  3   1
```

**5.3 Suppose that the sequence (where a letter means insert and an asterisk means remove the maximum) is inserted to an initially empty max heap. Give the sequence of values returned by del_max operations.**

>P R I O * R * * I * T * Y * * * Q U E * * * U * E

RRPOTYIIUQEU(E is left on heap)


# All in Together #

![image](https://user-images.githubusercontent.com/54606160/224256749-41966b97-d3d4-40e7-b9f2-783e32eb5f58.png)

***B: Mergesort(top-down) Sorted as 16+8+8, because top-down is recursively implemented. The sub-array can have different size, because it's still in the intermediate step***


***C: Quicksort(standard). ['HELP'] is the pivot. All elements before ['HELP'] is smaller or equal than ['HELP']. All elements after ['HELP'] is bigger than ['HELP']. Futhermore, the sub-array is not sorted yet***


***D: Mergesort(bottom-up) Sorted as 4+4+4+4+4+4+4+4. All sub-array are equal, satisfied bottom-up algr.***


***E: Shell sort. I found E is in 4 gap process. I found this because each 4 gaps elements have a ascending[A-Z] order***
>|'DINS'|'HELP|'HELP'|'LCAE'|'RATS'|'SEND'|'THEP'|'UARE'


***F: Insertion sort. The characterise of Insertion sort is iteratively picking element in order in the unsorted array and insert into its correct position in the sorted array. I found the sorted array stopped at UARE. There is no change after UARE compare to original array , so it tells that the elements was picked in order which satisfied Insertion sort's pattern***


***G: Heapsort. First element 'WATC' is the biggest element, meaning this array is making a max-heap***


***H: Selection sort. Sorted part stops at IDEA, and all elements was sorted before IDEA, all elements after IDEA is unsorted. Needed to point that all of the strings after IDEA is equal or bigger than IDEA. This will imply that the elements picked was in an order[A-Z]. Thus [A-I] elements was picked, there will be no elements smaller than IDEA. The string after IDEA is not sorted but still bigger than IDEA. This satisfie Selection sort pattern.***
