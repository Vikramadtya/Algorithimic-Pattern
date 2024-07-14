# Arrays

An array is a chunk of contiguous memory that a program can access by using indices—one index per dimension in the array.



{% hint style="info" %}
Behind the scenes, the program allocates enough contiguous memory to hold the array's data.

* For one-dimensional arrays, the mapping from array indices to memory entries is simple: index i maps to entry i.&#x20;
* For two-dimensional arrays, the program can map the array entries in one of two ways:&#x20;
  * In row-major order, the program maps the first row of array entries to the first set of memory locations. It then maps the second row to the set of memory locations after the first and so on..&#x20;
  * In column-major order, the program maps the first column of array entries to the first set of memory locations. It then maps the second column to the second set of memory locations, and so forth.

Normally, how a program maps array entries to memory locations is irrelevant to how a program works,
{% endhint %}



## One-Dimensional Arrays <a href="#head-2-75" id="head-2-75"></a>



<figure><img src="../.gitbook/assets/Arrays_in_ds-what-is-array-img1.PNG" alt=""><figcaption></figcaption></figure>



### Finding Items

If the items in the array are not sorted, finding an item is a matter of performing a _linear search_ or _exhaustive search_.&#x20;

The linear search run-time algorithm's run time $$\text{O}(n)$$



Finding every item would take a total of&#x20;

$$
1+2+3 ... +n = \frac{n(n+1)}{2}
$$

&#x20;steps. Divide this by the number of searches, $$n$$ , to get the average number of steps to find an item in the array $$\frac{(n+1)}{2}$$ which means that the average run time for finding an item in the array is $$\text{O}(n)$$





#### Finding Minimum, Maximum, and Average

We cannot avoid looking at every item in the array to find these values,  so they have run time $$\text{O}(n)$$

#### Finding Median

In case of an unsorted array either&#x20;

1.  sort the array and find the middle element&#x20;

    Time complexity $$\text{O}(n\log{n})$$
2.  use the quick select to find the mid - element&#x20;

    Time complexity $$\text{O}(n)$$

#### Find mode

In case of unsorted array

1.  sort the array and iterate to find the longest contiguous sequence&#x20;

    Time complexity $$\text{O}(n\log{n})$$, Time complexity $$\text{O}(1)$$&#x20;
2.  store the count of occurrence using count array or hash table&#x20;

    Time complexity $$\text{O}(n)$$ , Space complexity $$\text{O}(n)$$&#x20;

#### Inserting Items <a href="#head-3-47" id="head-3-47"></a>

Inserting an item at the end of a linear array is easy (time complexity $$\text{O}(1)$$) if the array has enough space and doesn't need extending.

For inserting anywhere

1. Find the position to insert the array
2. Move the items to create space&#x20;

#### Deleting Items <a href="#head-3-47" id="head-3-47"></a>

Removing the item with index `k` from an array means moving the items that come after position `k` one position closer to the beginning of the array.&#x20;

{% hint style="info" %}
In some cases, it may be possible to flag an entry as unused instead of actually removing it.&#x20;

This technique can be particularly useful in hash tables, where resizing the array and rebuilding the hash table would be time-consuming.

If flagging many entries as unused, the array could eventually fill up with unused entries. Then, to find an item, would need to examine a lot of empty positions.&#x20;

At some point, may want to compress the array to remove the empty entries.
{% endhint %}

