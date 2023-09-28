
Linked list operations

- deleting a node in a linked list
  - must go the the node before you reach the one you want to delete


```Java
public E remove(int index)
{
  if(index >= size)
  {
    throw new indexOutOfBoundsException();
  }

  if(index == 0)
  {
    E content = head.data;
    head = head.next;
    size --;
    return content;
  }

  SNode<E> current = head;
  for(int i = 0; i < index - 1; i++)
  {
    current = curent.next;
  }

  SNode <E> previousNode = current;
  SNode<E> toBeDeleted = previousNode.next;

  E content = toBeDeleted.data;
  previousNode.next = toBeDeleted.next;
  size --;
  return content;
}
```
