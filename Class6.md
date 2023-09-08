
> Generics

* the "is a" test
```Java
Box <Number> box = new Box<Number();
box.add(new Integer(10));

public void boxTest (Box<Number> n)
{

}

```
* you cannot creat an object of the generic type

---
#### Multiple Generics Class

```Java
public class OrderedPair<K,V> // key and value. K and V can be different tyoes from eachother

{
private K key;
private V Value;

public OrderedPair(K key, V value)
{
  this.key = key;
  this.value = value;
}

public getKey
{
  return this.key;
}
public getValue
{
  return this.value;
}
```

// Pay attention to errors in compiler (very helpful with inheritance of gnerics



---
**You can add limitations on the generic type**
* this can extend a class or an interface with the extends keyword

public class GenericClass<T extends **SomeClass*>
{

}

#### Generic Methods

you can have generic methods and classes
and a generic method and be in a non generic class
you can also add bounds on the generic method like the class
