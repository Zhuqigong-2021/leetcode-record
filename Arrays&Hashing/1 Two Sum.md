# Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

Question

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

    }
}
```

# Solution 1

this is easy solution to come up with

- Time complexity: O(n^2)
- Space complexity: O(1)

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i =0; i<nums.length;i++){
            for(int j= i+1; j<nums.length;j++){
               if(nums[i]+nums[j] == target) {
                   return new int[]{i,j};
               }

            }
        }
        return new int[]{};
    }
}
```

# Solution 2

hashmap

- Time complexity: O(n)
- Space complexity: O(n)

```java

class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int i =0; i<nums.length;i++){
            for(int j= i+1; j<nums.length;j++){
                int complement = target - nums[i];
               if(map.containsKey(complement)) {
                   return new int[]{map.get(complement),i};
               }
               map.put(nums[i],i)

            }
        }
        return new int[]{-1,-1};
    }
}

```

# Summary

## polymorphism

Map<Integer,Integer> map = new HashMap<>();

## Hashmap most commonly used methods:

int size()
Returns the number of key-value mappings in this map.

Collection<V> values()
Returns a Collection view of the values contained in this map.

| return              | method                                          | description                                                                                                                   |
| ------------------- | ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| int                 | size()                                          | Returns the number of key-value mappings in this map.                                                                         |
| Collection<V>       | values()                                        | Returns a Collection view of the values contained in this map.                                                                |
| boolean             | isEmpty()                                       | Returns true if this map contains no key-value mappings.                                                                      |
| boolean             | containsKey(Object key)                         | Returns true if this map contains a mapping for the specified key.                                                            |
| boolean             | containsValue(Object value)                     | Returns true if this map maps one or more keys to the specified value.                                                        |
| V                   | get(Object key)                                 | Returns the value to which the specified key is mapped, or null if this map contains no mapping for the key.                  |
| V                   | getOrDefault(Object key, V defaultValue)        | Returns the value to which the specified key is mapped, or defaultValue if this map contains no mapping for the key.          |
| V                   | put(K key, V value)                             | Associates the specified value with the specified key in this map.                                                            |
| V                   | remove(Object key)                              | Removes the mapping for the specified key from this map if present.                                                           |
| boolean             | remove(Object key, Object value)                | Removes the entry for the specified key only if it is currently mapped to the specified value.                                |
| Set<Map.Entry<K,V>> | entrySet()                                      | Returns a Set view of the mappings contained in this map.                                                                     |
| Set<K>              | keySet()                                        | Returns a Set view of the keys contained in this map.                                                                         |
| void                | forEach(BiConsumer<? super K,? super V> action) | Performs the given action for each entry in this map until all entries have been processed or the action throws an exception. |
