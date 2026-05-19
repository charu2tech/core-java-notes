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

6) Raw type  <br>
public class Box<T> { <br>
    public void set(T t) { /* ... */ } <br>
    // ... <br>
}  <br>

7) Generic Methods <br>
Generic methods are methods that introduce their own type parameters. This is similar to declaring a generic type, but the type parameter's scope is limited to the method where it is declared. Static and non-static generic methods are allowed, as well as generic class constructors. <br>
 eg1: static methods <br>
 public static <K, V> boolean compare(Pair<K, V> p1, Pair<K, V> p2)  <br>

 eg2; non static methods <br>
 public class Pair<K, V> { <br>

    private K key; <br>
    private V value; <br>
    public K getKey()   { return key; } <br>
    public V getValue() { return value; } <br>
} <br>

8) Bounded type parameter <br>
eg1:  public <U extends Number> void inspect(U u) <br>
eg2:  public class NaturalNumber<T extends Integer> { <br>

9)  Box<Integer> is not a subtype of Box<Number> even though Integer is a subtype of Number. <br>

10) Upper Bounded Wildcards <br>
eg: List<? extends Number> <br>

11) Unbounded Wildcards <br>
List<?>   <br>
It is generally useful if we pass Object <br>

12) Lower Bounded Wildcards <br>
<? super A> <br>

13) super/sub types <br>
class A { /* ... */ } <br>
class B extends A { /* ... */ } <br>

B b = new B(); <br>
A a = b; <br>

This example shows that inheritance of regular classes follows this rule of subtyping: class B is a subtype of class A if B extends A. This rule does not apply to generic types <br>

List<B> lb = new ArrayList<>(); <br>
List<A> la = lb;   // compile-time error <br>

14) Erasure of Generic Types  <br>
Generics were introduced to the Java language to provide tighter type checks at compile time and to support generic programming.  <br>
Type erasure ensures that no new classes are created for parameterized types; consequently, generics incur no runtime overhead.  <br>

During the type erasure process, the Java compiler erases all type parameters and replaces each with its first bound if the type parameter is bounded, or Object if the type parameter is unbounded.  <br>
 





