
we went over the quiz. Get a extra copy and redo it later

Go over the comparable interface and the use cases

comparable is a widely used interface..

---
**SLide 23**

The question mark is called a wildcard and it signifies and unknown class

```Java

public statc voud printColection (Collection<?> c)
  {
    for (Object e : c)
      {
          System.out.println(e);
      }
  }
```

The ? means it is a specific type of class but I don't know yet

List <?> list1 = new ArrayList<ExampleClass>();
List <? extends ExampleClass> list1 = new ArrayList<ExampleClass>();
List <? super ExampleClass> list1 = new ArrayList<ExampleClass>();


__you cannot use the wildcard as the type in your generic class!__


uppweBound wildCard

similar to the upperbound in generics
#### Silde 42

---

Lower bound wildcard also exists
accepts a generic class and any of its super classes

public static void addNumbers (List <? super Integer> list)
{
  list.add();
}


when not to use wildcard SLIDE 51 TESTABLE


The collections class in java is really a library that java uses for data structure to compare items
