1) what is an interface?<br>
   a) it is a specification.  <br>
   b) example: interface Abc{} <br>
               class Xyz implements Abc {} <br>

2) Default methods and abstract methods in interfaces are inherited like instance methods. <br>

eg: public interface Mythical { <br>
    default public String identifyMyself() { <br>
        return "I am a mythical creature."; <br>
    } <br>
} <br>
 
public class Pegasus extends Horse implements Mythical { <br>
    public static void main(String... args) { <br>
        Pegasus myApp = new Pegasus(); <br>
        IO.println(myApp.identifyMyself()); <br>
    } <br>
} <br>


3) In the Java programming language, an interface is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods (private or public, not protected), instance non-abstract methods (private, not public, not protected), and nested types. <br>

4) In addition to default methods, you can define static methods in interfaces. (A static method is a method that is associated with the class in which it is defined rather than with any object. Every instance of the class shares its static methods.) This makes it easier for you to organize helper methods in your libraries; you can keep static methods specific to an interface in the same interface rather than in a separate class. <br>

 public interface TimeClient { <br>
    // ... <br>
    static public ZoneId getZoneId (String zoneString) { <br>
        try { <br>
            return ZoneId.of(zoneString);  <br>
        } catch (DateTimeException e) { <br>
            System.err.println("Invalid time zone: " + zoneString + <br>
                "; using default time zone instead."); <br>
            return ZoneId.systemDefault(); <br>
        } <br>
    } <br>

    default public ZonedDateTime getZonedDateTime(String zoneString) { <br>
        return ZonedDateTime.of(getLocalDateTime(), getZoneId(zoneString)); <br>
    }     <br>
} <br>