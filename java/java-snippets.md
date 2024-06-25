---
description: commonly used java snippets
---

# Java Snippets



## Sorting

### Arrays

To sort an array use&#x20;

```java
Arrays.sort(arr); // Sorts the array in ascending order
```

{% hint style="info" %}
To sort an array in descending order&#x20;

```java
Arrays.sort(arr,Collections.reverseOrder());
```

this only works for non-primitive array i.e `Integer [] array` not `int [] array`
{% endhint %}



If we want to sort array from some index to some index use

```java
Arrays.sort(arr,fromIndex,toIndex);
```

> Read more about the array operation [here](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)

If its a multi-dimensional array&#x20;

```java
Arrays.sort(arr, (a, b) -> Integer.compare(a[column],b[column]));
```

### List

To sort a list use&#x20;

```java
Collections.sort(list);
```

## Binary Search



#### Arrays

Searches a range of the specified array for the specified value

```java
public static T binarySearch(T[] a,int fromIndex,int toIndex,T key)
```

* index of the search key, if it is contained in the array within the specified range.&#x20;
* Otherwise, $$-(insertion point) - 1$$&#x20;
  * the _insertion point_ is defined as the point at which the key would be inserted into the array

#### List

If its&#x20;





## String Operations

### Split String

To split a string on a delimiter

```java
String [] strArray =  string.split("<delimiter>");
```

### Join String

To join the characters/string on a delimiter&#x20;

```java
String joinedString = String.join("<delimiter>",<list/array_of_string>);
```

### Change case

To convert the string to lower case

```java
string.toLowerCase();
```

to convert it to upper case

```java
string.toUpperCase();
```



> Read more about the possible string operation [here](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)



## Splice

### Array

To create the sub-array&#x20;

* _startInclusive_ – the start index to extract from the array  inclusive
* _endExclusive_ – the end index to extract exclusive

```java
String[] result = Arrays.stream(<array>, <startInclusiveIndex>, <endExclusiveIndex>).toArray(String[]::new);
```





