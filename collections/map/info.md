1) What is map? <br>
    a) Each key is associated with one value. <br>
    b) A Map cannot contain duplicate keys. If a duplicate key is detected, then an IllegalArgumentException is thrown. <br>
    c)  Null cannot be used for either Map keys or values. <br>
    d) Randomized iteration order applies to the collection instances created by Map.of, and Map.ofEntries methods and the toUnmodifiableMap collectors. The iteration ordering of collection implementations such as HashMap is unchanged. <br>

2) How to create unmodifiable map? <br>
   Map.of(...)