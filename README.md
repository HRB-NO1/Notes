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
"""
In block a, there is a nested loop(while, for),
the inner loop repeats n times, and the outer loop repeats log2(n) times.
n * (1 + 1/2 + 1/4 + 1/8 + ... + 1/n)
= n * 2
= 2n
So the time complexity is O(n)
"""
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
"""
​
"""
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
"""
In block c, there is a nested loop(while, for),
the inner loop repeats n times, and the outer loop repeats log2(n) times.
n * log2(n)
"""
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
**As the output, I can find that block a and block b tend to be O(n) which means the bigger the N is, the more time they will take, and it's a linear increase.** 
**I can find that block c tend to be O(nLogn) which means the bigger the N is, the more time they will take, and it's not a linear increase.**

![](https://coderzpy.com/wp-content/uploads/2020/08/WcBRI.png)

**Block a explanation:**



## 2.Selection/Insertion Sort
***Show in the style of the example trace with selection sort, how selection sort sorts the array***

>Selection sort: Find the minimum element in unsorted array, and switch position between the first and the minimum element. 
>https://www.youtube.com/watch?v=xWBP4lzkoyM

>Insertion sort: Read from the beginning of unsorted array, insert the element to the correct position.
>https://www.youtube.com/watch?v=OGzPmgsI-pQ

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
1. Choose the last element in the array as the pivot element.
2. Initialize two pointers, i and j, at the beginning of the array.
3. Move pointer i from left to right until an element larger than or equal to the pivot is found.
4. Move pointer j from right to left until an element smaller than the pivot is found.
5. If i is less than or equal to j, swap the elements at positions i and j, and increment i and decrement j.
6. Repeat steps 3-5 until i is greater than j.
7. Swap the pivot element (which is at the end of the array) with the element at position i.
8. Recursively sort the sub-array to the left of i and the sub-array to the right of i.
```
**4.1 Show, in the style of the trace given with partition(), how that method partitions the array E A S Y Q U E S T I O N.**

![23fa7874f3fc56373f92b775060d70e](https://user-images.githubusercontent.com/54606160/223111901-33559bb5-a5a5-489d-839c-a56282d04a28.jpg)

**4.2 Show, in the style of the quicksort trace, how quicksort sorts the array E A S Y Q U E S T I O N. (For the purposes of this exercise, ignore the initial shuffle.)**

**4.3 About how many compares will Quick.sort() make when sorting an array of N items that are all equal?**

N*logN, in this situation, the array will be cut into two same size sub-array that is logN. And each iteration make n compares

**4.4 Show, in the style of the trace given with the code, how the entropy-optimal sort first partitions the array B A B A B A B A C A D A B R A**

**4.5 Bad partitioning. How does not stop on equal keys make quicksort go quadratic when all keys are equal? Give an example of this input.**

Not stop on strategy will divide the array into 2 different sizes sub-array(often). When encounter the array with all equal key, it will divide the array into size of n-1 sub-array and size 1 array like this: [1,1,1,1] [1], leading to recursion depth of n and n comapres per recursion, which is n^2

## 5. Heapsort  
**4.1 Criticize the following idea: to implement find the maximum in constant time, why not keep track of the maximum value inserted so far, then return that value for find the maximum?**

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

**4.2 Is an array that is sorted in decreasing order a max-oriented heap?**

Yes,  [9, 7, 5, 3, 1]
```
       9
     /   \
    7     5
   / \
  3   1
```

**4.3 Suppose that the sequence (where a letter means insert and an asterisk means remove the maximum) is inserted to an initially empty max heap. Give the sequence of values returned by del_max operations.**

>P R I O * R * * I * T * Y * * * Q U E * * * U * E

RRPOTYIIUQEU(E is left on heap)


# All in Together #
![n2as7kxfhqkpglf3juj2](https://user-images.githubusercontent.com/54606160/223387032-dc0836b8-7d18-4cd6-be5d-587e872c7db8.png)

