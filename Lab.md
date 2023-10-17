








```Java

package dataStructures2;
import java.util.List;

public class ListTester{
	public static void main(String[] args) {

		System.out.println();

		System.out.println("Testing doubly linked list...");
		DLinkedList<Integer> numberList = new DLinkedList<>();
		testListWithIntegers(numberList);

		DLinkedList<String> strList = new DLinkedList<>();
		testListWithStrings(strList);
		System.out.println("...end of double link tests");

	}

	public static void testListWithIntegers(List<Integer> numList){
		numList.add(12);
		numList.add(3);
		numList.add(0, 15);

		try {
			numList.add(5, 45);
			System.out.println("ERROR - exception missed");
		} catch (IndexOutOfBoundsException e) {
			System.out.println("Correctly caught add out of bounds exception");
		}

		System.out.println(numList);
		System.out.println("Expected list: 15, 12, 3");

		System.out.println();
	}

	public static void testListWithStrings(List<String> wordList){

		wordList.add("house");
		wordList.add("window");
		wordList.add("door");
		wordList.add(1, "roof");

		if ( wordList.size() != 4 ){
			System.out.println("ERROR - incorrect size");
		}

		System.out.println(wordList);
		System.out.println("Expected list: house, roof, window, door");

		String test = wordList.get(2);
		if ( !test.equals("window")){
			System.out.println("Error - Unexpected element at index 2");
		}
		
		System.out.println(wordList);
		System.out.println("Expected list: house, roof, window, door");

	}
}

```






```Java

package dataStructures2;

import java.util.AbstractList;

public class DLinkedList<E> extends AbstractList<E>{

	private DNode<E> head;
	private DNode<E> tail;
	private int size;

	public DLinkedList(){
		head = new DNode<E>();
		tail = head;
		size = 0;
	}

	/* appends element to end of the list */
	public boolean add(E e){
		//TODO: COMPLETE THIS METHOD
		
		// create new node and pass in the value e to the constructor
		DNode <E> newNode = new DNode <E>(e);
		if(isEmpty())
		{
			head = newNode;
		}
		
		else
		{
			tail.next = newNode;
			newNode.prev = tail;
		}
		
		tail = newNode;
		size++;
		return true;
		/* this method will always return true there is no
		 * implemented knowledge to tell it to return false if the 
		 * node does not add into the DLL due to memory error or hardware issues.
		 * 
		 * I feel this method could have been a void return type.
		 */

		
	}

	/* insert element at the given index 
	if the index is out of bounds throw an IndexOutOfBoundsException */
	public void add(int index, E e){
		//TODO: COMPLETE THIS METHOD
		
		if(index < 0 || index > size)
		{
			throw new IndexOutOfBoundsException("Index given is too large!");
		}
		
		// pass in the information for the new node
		DNode <E> newNode = new DNode <>(e);
		
		if(index == 0)
		{
			newNode.next = head;
			
			if(head != null)
			{
				head.prev = newNode;
			}
			
			head = newNode;
		}
		
		else 
		{
			DNode <E> current = head;
			for(int i = 0; i < index - 1; i++)
			{
				current = current.next;
			}
			
			newNode.next = current.next;
			newNode.prev = current;
			
			// if not inserting at the tail
			if(current.next != null)
			{
				current.next.prev = newNode;
			}
			
			current.next = newNode;
		}
		
		// increment the size of the linked list by one 
		size++;
	}

	public void clear(){
		head.next = null;
		tail = head;
		size = 0;
	}

	
	/* get the data from the node at the given index 
	 * if the index does not exist throw an IndexOutOfBoundsException
	 * May have to handle cases where the index is the head or tail
	 */
	
	public E get(int index){
		//TODO: COMPLETE THIS METHOD
		if( index < 0 || index > size)
		{
			throw new IndexOutOfBoundsException("Invalid Index");
		}
		
		DNode <E> current = head;
		for(int j = 0; j < index - 1; j++)
		{
			current = current.next;
		}
		
		return current.getData();
	}

	/* remove the node at the given index from the list and return its data 
		if the index does not exist throw an IndexOutOfBoundsException */
	public E remove(int index){
		//TODO: COMPLETE THIS METHOD
		if( index < 0 || index > size)
		{
			throw new IndexOutOfBoundsException("Invalid Index");
		}
		
		// find node that you want to delete
		DNode <E> current = head;
		for(int j = 0; j < index - 1; j++)
		{
			current = current.next;
		}
		
		if(index == size - 1) // if index is equal to tail
		{
			current.prev.next = null;
		}
		
		else
		{
			current.prev.next = current.next;
			current.next.prev = current.prev;
		}
		return current.getData();
	}

	
	
	/* replace the contents at the given index with the data given
		return the data that was previously at that index 
		if the index does not exist throw an IndexOutOfBoundsException */
	public E set(int index, E element){
		//TODO: COMPLETE THIS METHOD
		if( index < 0 || index >= size)
		{
			throw new IndexOutOfBoundsException("Invalid Index");
		}

		// new node to replace current
		DNode<E> newNode = new DNode <>(element);
		// current node for iteration, which will get data returned
		DNode <E> current = head;
		// find node that you want to delete
		
		if(index == 0)
		{
			newNode.next = current.next;
			
			if(current.next != null)
			{
				current.next.prev = newNode;
			}
			
			newNode.prev = null;
			head = newNode;
		}
		
		else
		{
			for(int j = 0; j < index; j++)
			{
				current = current.next;
			}
			
			newNode.next = current.next;
			
			if(current.next != null)
			{
				current.next.prev = newNode;
			}

			
			newNode.prev = current.prev;
			current.prev.next = newNode;
			
			if(index == size)
			{
				tail = newNode;
			}
		}
		
		return current.data;
	}

	
	
	public int size()
	{
		return size;
	}
	
	
	// helper function for me to determine if the list is empty
	// this will deal with special cases of insertion/deletions
	public boolean isEmpty()
	{
		return size == 0;
		
		// if length == 0 return true
		// otherwise return false
	}

	public String toString(){
		//TODO: COMPLETE THIS METHOD
		
		String r = "[";
		
		DNode<E> current = head;
		
		while(current != null)
		{
			r = r + current.data;
			if(current.next != null)
			{
				r = r + ", ";
			}
				
			current = current.next;
		}
		
		r = r + "]";
		return r;
	}

	// internal class for single linking nodes
	class DNode<E> {
		E data;
		DNode<E> next;
		DNode<E> prev;

		public DNode(){
			this(null);
		}

		public DNode(E data){
			this.data = data;
			next = null;
			prev = null;
		}

		public DNode(E data, DNode<E> prev, DNode<E> next){
			this.data = data;
			this.prev = prev;
			this.next = next;
		}
		
		
		public E getData()
		{
			return this.data;
		}
	}
	
}

```
