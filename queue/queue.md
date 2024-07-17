# Queue

A queue is a data structure where items are added and removed in first-in-first-out order. Because of this first-in-first-out (FIFO, usually pronounced “fife-oh”) behavior, stacks are sometimes called FIFO lists or FIFOs.

<figure><img src="../.gitbook/assets/Data_Queue.svg" alt=""><figcaption></figcaption></figure>

The method that adds an item to a queue is called `Enqueue`, and the item that removes an item from a queue is called `Dequeue`.



## Linked-List Queues <a href="#head-3-59" id="head-3-59"></a>

The `Enqueue` method simply adds a new cell to the top of the list, and the `Dequeue` method removes the bottom cell from the list.



<mark style="background-color:yellow;">To make removing the last item from the queue easy, the queue should use a doubly linked list.</mark> With a doubly linked list, enqueueing and dequeueing items have $$\text{O}(1)$$ run times.



## Array Queues <a href="#head-3-60" id="head-3-60"></a>

To keep track of the array positions that are in use, use two variables:&#x20;

* `Next`, to mark the next open position
* `Last`, to mark the position that has been in use the longest



If we simply store items at one end of an array and remove them from the other, however, the occupied spaces move down through the array.



<figure><img src="../.gitbook/assets/c05f009.jpg" alt="" width="268"><figcaption></figcaption></figure>



A more effective approach is to build a _circular array_, in which we treat the last item as if it were immediately before the first item. Now when `Next` falls off the end of the array, it wraps around to the first position, and the program can store new items there.

<figure><img src="../.gitbook/assets/c05f010.jpg" alt=""><figcaption></figcaption></figure>



Since when the queue is empty, `Next` is the same as `Last` and in case of full queue `Next` goes all the way around the array and catches up to `Last` , so there's no obvious way to tell whether the queue is empty or full. Solution are to

* track the number of items in the queue
* keep track of the number of unused spaces in the queue,&#x20;
* keep track of the number of items added to and removed from the queue



If the queue is full and to add more items, allocate a larger storage array, copy the data into the new array, and then use the new array instead of the old one.

## Specialized Queues <a href="#head-3-61" id="head-3-61"></a>



### **Priority Queues**

Each item has a priority, and the dequeue method removes the item that has the highest priority. Basically, high-priority items are handled first.\
\


### **Deques**

A _deque_ (usually pronounced “deck,") is a queue that allows to add items to and remove items from either end of the queue.

Deques are useful in algorithms where you have partial information about the priority of items. For example, might know that some items are high priority and others are low priority, but you might not necessarily know the exact relative priorities of every item.





<mark style="background-color:yellow;">Deques are easy to build with doubly linked lists.</mark>

## Binomial Heaps

A _binomial heap_ lets insert new items and remove the highest priority item relatively quickly.

A binomial heap contains a collection of _binomial trees_ that contain the heap's values.&#x20;

To make rearranging the trees easier, the heap normally stores the tree roots in a linked list. \


{% hint style="info" %}
A disjoint union of trees, is sometimes called a _forest_.
{% endhint %}





