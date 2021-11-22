# Hash

**HashMap doesn't allow duplicate keys** but allows duplicate values.&#x20;

If I pass the same key multiple times to `HashMap`’s `put` method, what happens to the original value? . --> Overwritten values for a key

Collision

Absolutely right. In hash set and hash map, Java first use object's hashCode() function to compute the "slot" for the key. If two keys have the same hash code (this is called hash collision and it's actually very rare to happen), they will be compared by using the second key's equals() method, if return true, the two keys are exactly the same, the key will not be added(in set) or its value will be overwritten(in map); if return false, Java will create a linear chain in the slot to store both of them.



map.containsValue: O(n)

contains() / containsKey() : O(1)&#x20;
