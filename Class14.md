Quiz on linked lists and Big(O) notation

Best/Worst Cass efficiency for sorting algorithms
- quick sort for example
  - picking the worst pivots


 Maps
 - a map is a type of a data structure tgat allows key-value pairings
   - in some languages this is called a dictionary

> Common uses of a map
- Contact list
  - key: name
  - value: phone number
- Dictionary

#### Methods Required
- Put
- Remove
- Get
- Contains Key, Contains Value
- isEmpty, size, clear

#### Implementatoion
__What underlying data structures do you use for implementing a map?__

- parallel arrays
  - two array where one contains the key and on contains the value 
- MapEntry Object and store them all in a linked list
  - MapEntry would contain the key and the value

---

Instead of a regular map we will use a HashMap

- you can retrieve stored key/value pairs in constant tiem
- a hashing function passes a key through an algoritm to produce a hash value
 - the hash value is then used to create an index where to store the data

- A hash function must run in constant time, the hash value must be consistrnt every time the key is hashed.
- Minimize collisions

#### Collisions
- when two different keys give the same hash value

How do we prevent collisions?

> Separate Chaining
- store a linked list at everything that hashes to that index

> Open Addressing 

(linear probing)
- look for the next available spot that is open when a collision occurs
- h(k) % size
- h(k + 1) % size
- h(k + 2) % size
- h(k + 3) % size

(quadratic probing)
- h(k) % size
- h(k + 1) % size
- h(k + 4) % size
- h(k + 9) % size
 
Deleted data
- when you delete a value insert a deleted key to let the user know you have deleted information.
  - if you reach the deleted you should keep probing so you find the other element in the collison
---
Load Factor
- the standard measure to describe how full the hash fable is
- a lot of things depend on how big the table is, this is how you choose the sizw

Load factor is defined as: (number of entries in the table)/(size of the table)

- the load factor is a rating of how efficient your hash table will be.

- If LF = 1 and you are using open addressing your table is completely full
- If LF = 0.2 you are not using 80% of the space and the table is probably too large

#### Time Vs. Space

load factor is another example of needing to compromise between speed and memory capacity
