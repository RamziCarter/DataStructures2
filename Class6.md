
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




**You can add limitations on the generic type**



public class GenericClass<T extends **SomeClass*>
{

}

