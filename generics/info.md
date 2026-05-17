1) In a nutshell, generics enable types (classes and interfaces) to be parameters when defining classes, interfaces and methods. Much like the more familiar formal parameters used in method declarations, type parameters provide a way for you to re-use the same code with different inputs. The difference is that the inputs to formal parameters are values, while the inputs to type parameters are types. <br>

2) Code that uses generics has many benefits over non-generic code: <br>

Stronger type checks at compile time. A Java compiler applies strong type checking to generic code and issues errors if the code violates type safety. Fixing compile-time errors is easier than fixing runtime errors, which can be difficult to find. <br>

Elimination of casts. <br>

3) General without any specific type<br>
   eg: public class Box { <br>
    private Object object; <br>

    public void set(Object object) { this.object = object; } <br>
    public Object get() { return object; } <br>
    } <br>

    a) we can pass any Object to above box class object <br>

    eg2: generic version of above type. <br>
    public class Box<T> { <br>
    private T t; <br>
    public void set(T t) { this.t = t; } <br>
    public T get() { return t; } <br>
    } <br>

    Box<Integer> integerBox;

4) Type parameter naming convention. <br>
   The most commonly used type parameter names are: <br>
    E - Element (used extensively by the Java Collections Framework) <br>
    K - Key <br> 
    N - Number <br>
    T - Type <br>
    V - Value <br>
    S, U, V etc. - 2nd, 3rd, 4th types <br>

5) Diamond <br>
   Box<Integer> integerBox = new Box<>(); <br>

6) Multiple type parameters <br>
   public interface Pair<K, V> { <br>
    public K getKey(); <br>
    public V getValue(); <br>
    } <br>

    public class OrderedPair<K, V> implements Pair<K, V> { <br>

    private K key; <br>
    private V value; <br>

    public OrderedPair(K key, V value) { <br>
    this.key = key; <br>
    this.value = value; <br>
    } <br>

    public K getKey()    { return key; } <br>
    public V getValue() { return value; } <br>
} <br>

Pair<String, Integer> p1 = new OrderedPair<String, Integer>("Even", 8); <br>
Pair<String, String>  p2 = new OrderedPair<String, String>("hello", "world"); <br>

OrderedPair<String, Box<Integer>> p = new OrderedPair<>("primes", new Box<Integer>(...)); <br>