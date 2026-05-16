1) Explain about list?
    a) A list is an ordered collection in which duplicate elements are  allowed. <br>
    b) Null values are not allowed. <br>
  

2) How to create unmodifiable list? <br>
   Eg1: <br>
    List.of(...)  //static methods. <br>
   Eg2: <br>
       Set<Item> unmodifiableSet =
       sourceCollection.stream()
                      .map(...) 
                      .collect(Collectors.toUnmodifiableSet()); <br>

3) How to copy a list? <br>
   List.copyOf(...) <br>