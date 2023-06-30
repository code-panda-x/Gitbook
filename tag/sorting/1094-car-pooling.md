# 1094 Car pooling

There is a car with `capacity` empty seats. The vehicle only drives east (i.e., it cannot turn around and drive west).

You are given the integer `capacity` and an array `trips` where `trips[i] = [numPassengersi, fromi, toi]` indicates that the `ith` trip has `numPassengersi` passengers and the locations to pick them up and drop them off are `fromi` and `toi` respectively. The locations are given as the number of kilometers due east from the car's initial location.

Return `true` _if it is possible to pick up and drop off all passengers for all the given trips, or_ `false` _otherwise_.

&#x20;

**Example 1:**

<pre><code><strong>Input: trips = [[2,1,5],[3,3,7]], capacity = 4
</strong><strong>Output: false
</strong></code></pre>

**Example 2:**

<pre><code><strong>Input: trips = [[2,1,5],[3,3,7]], capacity = 5
</strong><strong>Output: true
</strong></code></pre>

```java
class Solution {
    public boolean carPooling(int[][] trips, int capacity) {
        TreeMap<Integer, Integer> map = new TreeMap<>();
        for(int[] trip : trips){
            map.put(trip[1], map.getOrDefault(trip[1],0) + trip[0]);
            map.put(trip[2], map.getOrDefault(trip[2],0) - trip[0]);
        }
        for(int v : map.values()){
            capacity -= v;
            if(capacity < 0)
                return false;
        }
        return true;
    }
}
```
