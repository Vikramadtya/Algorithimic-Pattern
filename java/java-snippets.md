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
Arrays.sort(points, (a, b) -> Integer.compare(a[column],b[column]));
```

### List

To sort a list use&#x20;

```java
Collections.sort(list);
```

## Binary Search



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



