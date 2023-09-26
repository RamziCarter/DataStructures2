
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
