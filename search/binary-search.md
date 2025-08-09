# Binary Search

| Pattern                     | Purpose                            | Typical Use Cases                         |
| --------------------------- | ---------------------------------- | ----------------------------------------- |
| **Exact match**             | Find a specific target value       | Search in sorted array                    |
| **Lower bound**             | First value >= target              | Insertion point, minimum satisfying value |
| **Upper bound**             | First value > target               | Counting occurrences, range queries       |
| **Binary search on answer** | Find min/max satisfying a property | Parametric search, optimisation problems  |

## Standard Binary Search (Exact Match)

```java
public int search(int[] nums, int target) {
  int left = 0, right = nums.length-1;
  while(left <= right) {
       int mid = ( ( right -  left ) >> 1) + left;
       if(nums[mid] == target) return mid;
       if(nums[mid] < target) left = mid+1;
       else right = mid-1;
  }
  return -1;
}
```

## **Lower Bound** (First element > target)

```java
public int lowerBound(int[] nums, int target) {
    int left = 0, right = nums.length;
    while (left < right) {
        int mid = left + ((right - left) >> 1);
        if (nums[mid] < target) left = mid + 1;
        else right = mid;
    }
    return left; // Could be nums.length if all elements < target
}
```

## **Upper Bound** (First element ≥ target)

```java
public int upperBound(int[] nums, int target) {
    int left = 0, right = nums.length;
    while (left < right) {
        int mid = left + ((right - left) >> 1);
        if (nums[mid] <= target) left = mid + 1;
        else right = mid;
    }
    return left; // Could be nums.length if all elements <= target
}

```

## **Binary Search on Answer** (Predicate-based)

```java
public int binarySearchAnswer(int low, int high) {
    while (low < high) {
        int mid = low + ((high - low) >> 1);
        if (condition(mid)) {
            high = mid; // Look left
        } else {
            low = mid + 1; // Look right
        }
    }
    return low;
}
```

