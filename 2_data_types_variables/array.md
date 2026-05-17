1) How will you create an array? <br>
     eg1:   // declares an array of integers <br>
               int[] anArray; <br>
            // allocates memory for 10 integers <br>
               anArray = new int[10]; <br>
      eg2:  double[] prices = {9.99, 15.50, 7.25}; <br>
      eg3:  multi dimension array <br>
      String[][] names = {
            {"Mr. ", "Mrs. ", "Ms. "},
            {"Smith", "Jones"}
        }; <br>
      eg4:  matrix <br>
            int[][] matrix = {
               {1, 2, 3},
               {4, 5, 6},
               {7, 8, 9}
            };<br>

2) How to copy an array? <br>
    eg1 : System.arraycopy(copyFrom, sourcearray-start-index, copyTo, destinationarray-start-index, length); <br>
    eg2: Arrays.copyOfRange(copyFrom, 2, 9); <br>
3) Arrays class has different methods like binarysearch, equals, fill, sort, parallelsort, stream, tostring methods.  <br>