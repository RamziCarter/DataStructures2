
> I was late to class; when I cam in we were on slide 16

#### Linked Lists

* Singly linked list
  * in a linked list each element is actually contained within a Node Structure
    * 2 pieces to a Nide
      * data
      * pointer to the next Node
    * The linked list itself only keeps track of the very first node in the list
   
```Java
class SNode <T>
{
E data;
SNode <T> next

// default constructor
public SNode()
{
  data = null;
  next = null;
}

// constructor with paramater
public SNode(E data)
{
  this.data = data;
  next = null;
}

public SNode(E data, SNode <T> next)
{
  this.data = data;
  this.next = next;
}
}
```

---

#### Linked List notes
- the first node is called the head
- the last node is called the tail
- to traverse the list you must create a reference and assign it to your first node (usually that is the first node
- 
- 


Snode <E> current = head;
while current.next != null)
{
 // do something
 current = current.next;
}
