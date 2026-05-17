1) How many different types of variables are there in java? <br>
   instance variables, static/class variables, local variables, parameters <br>
2) Explain primitive data types in java? <br>
   a) byte: 8 bit. range -128 to 127 <br>
   b) short: 16 bit. range -32768 to 32767 <br>
   c) int: 32 bit <br>
   d) long: 64 bit <br>
   e) float: 32 bit <br>
   f) double: 64 bit <br>
   g) boolean: true/false <br>
   h) char: 16 bit unicode character. <br>
3) Explain non primitive data types in java? <br>
   a) String: immutable.  <br>
   b) Array: fixed length. <br>
4) what is var typs? <br>
   a) var must be initialized. <br>
   b) var must be a local variable. <br>
   c) var cannot be used for fields, nor for method or constructor parameters. <br>
5) what is Enum? <br>
   a) Enums are classes where all instances are known to the compiler. They are used for creating types that can only have few possible values. <br>
   example: <br>
   public enum DayOfWeek { <br>
    // enum constants are listed here: <br>
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY <br>
   } <br>
   b) we can use enum constants in switch expressions.  <br>
   c) special methods - name, ordinal, values, valueOf <br>


    