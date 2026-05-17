1) What is Record? <br>
   a) we can create an immutable data using record. <br>
   b) eg: public record Point(int x, int y) {} <br>
        b1) It is an immutable class with two fields: x and y, of type int. <br>
        b2) It has a canonical constructor, to initialize these two fields. <br>
        b3) The toString(), equals() and hashCode() methods have been created for you by the compiler. <br>
        b4) It can implement the Serializable interface. <br>
        b5) The class that the compiler creates for you when you create a record is final. <br>
        b6) This class extends the java.lang.Record class. So your record cannot extend any class. <br>
        b7) A record can implement any number of interfaces. <br>
        b7) You cannot define any field initializer. <br>
        b8) You cannot add any instance initializer. <br>
        b9) You can create static fields with initializers and static initializers. <br>