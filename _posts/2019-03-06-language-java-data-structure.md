---
layout: post
title:  "[Languages] Java data structure"
date:   2019-03-06 21:00:00
categories: ProgrammingLanguages
tags: ProgrammingLanguages Java
author: Hailey Gu
---

* content
{:toc}


## Reference

- book1 : Java programming to stimulate the brain, chapter 13 // Korean
- book2 : Head first java
- document : [link : https://docs.oracle.com/javase/7/docs/api/ ](https://docs.oracle.com/javase/7/docs/api/)

## Basic of Java

* keyword (50) : class, static, public, avoid

 | - | - | - | - | - |
 |---|---|---|---|---|
 | abstract | continue | for | new | switch |
 | assert | default | if | package | synchronized |
 | boolean | do | goto | private | This |
 | break | double | implements | protected | throw |
 | byte | else | import | public | throws |
 | case | enum | instanceof | return | transient |
 | catch | extends | int | short | try |
 | char | final | interface | static | void |
 | class | finally | long | strictfp | volatile |
 | const | float | native | super | while |

* constant(3)

 | true | false | null |

* identifier : HelloJava, main, String, out, System

* Class.Valuable.method (System.out.println)

* Type

| type | size | range |
|---|---|---|---|---|
 | byte | 1 | -128~127 |
 | short | 2 | -32768~32767 |
 | int | 4 | -2147483648 ~ 2147483648 (10^9) |
 | long | 8 | -9223372036854775808 ~ 9223372036854775807 (10^18) |
 | float | 4 | |
 | double | 8 | |
 | char | |
 | boolean | x | |
 | String | |
// except String, There are called primitive type

1. primitive type
1.1. numeric Type
1.1.1. integral type(byte, short, int, long, char)
1.1.2. floating point type(float, double)
1.2. boolean Type(boolean)
2. reference Type
2.1. class Type
2.2. interface Type
2.3. array Type
2.4. enum type

- MSB : + is 0, - is 1
- 2's complement(27->-27 : 27+-27 == 0) : change 1->0, 0->1 than +1

- float : 1/8/23 (signed, exp, number)
- double : 1/11/52

- constant

| float | double |
|---|---|
 | Float.MAX_VALUE | Double.MAX_VALUE |
 | Float.MIN_VALUE | Double.MIN_VALUE |
 | Float.POSITIVE_INFINITY | Double.POSITIVE_INFINITY |
 | Float.NEGATIVE_INFINITY | Double.NEGATIVE_INFINITY |
 | Float.NaN | Double.NaN |

* wrapper

Boolean
Character
Byte
Short
Integer
Long
Float
Double



* Arrays

```java
int arr[]; // 1
int[] arr; // 2
arr = new int[];  // create

int arr[] = new int[];
int arr[] = {10,20,30,40,100};

int num = arr.length;
```

* method

```java
num = Integer.parseInt("12");
str = Integer.toBinaryString(12); //

double num1 = 3.14;
long num2 = Double.doubleToRawLongBits(num1);
String str = Long.toBinaryString(num2);

System.out.printf("%.2f", num);
System.out.printf("%x", num); // 16


boolean b = new Boolean("true").booleanValue();
double d = 42.5;
String doubleString = "" + d; // 1
String doubleString = Double.toString(d); // 2

String s = String.format("%, d", 1000000000); // -> 1,000,000,000
String s = String.format("I have %.2f bugs to fix.", 476578.09876); //-> I have 476578.09 bugs to fix.
String s = String.format("I have %,.2f bugs to fix.", 476578.09876); //-> I have 476,578.09 bugs to fix.
```

* exception
```java
class SmartExample {
  public static void main(String args[]) {
    int a = 3, b = 0;
    int result;
    try {
      result = a/b;
      System.out.println(result);
    }
    catch(java.lang.ArithmeticException e) { // can repeat
      System.out.println("wrong");
    }
    catch(java.lang.ArrayIndexOutOfBoundsException e) { // can process multiple type of exception
      System.out.println("wrong");
    }
    finally { // can skip
      System.out.println("Done.");
    }
  }
}
```





## Data structure of Java

* list : search, insert, remove (array list, linked list)
- ArrayList LinkedList (Vector)
* stack, queue
- LinkedList (stack)
* hash table (key) : fast search
- HashMap (Hashtable)
* set (no duplicate)
- HashSet

### Type parameters

"<E> element"
"<K> key"
""<V> value"

### classes for list

#### ArrayList

```java
ArrayList<String> list = new ArrayList<String>(); // count = 10
list.add("apple");

ArrayList<String> list = new ArrayList<String>(50); // size

list.get(0);
list.get(1);
list.get(2);

int num = list.size();

list.remove(1); // index 2->1, index 3->2
list.remove("apple");

int index = list.indexOf("apple");
int index = list.lastIndexOf("apple"); // if duplicated,
```
get(int index)
add(Object elem)
remove(int index)
remove(Object elem)
contains(Object elem)
isEmpty()
indexOf(Object elem) // return index or -1
size()



#### LinkedList

check list.get(2); is O(N)
```java
String str = list.get(2);
```

#### Iterator
```java
Iterator<String> iterator = list.iterator();
String str = iterator.next(); // when call next(), return first, second, third...

while(iterator.hasNext()) {
  String str = iterator.next();
}

// JDK 5.0~
for(String str : list) {
  // to do
}
```

### classes for stack

```Java
LinkedList<Integer> stack = new LinkedList<Integer>();
list.addLast(new Integer(12));
list.addLast(new Integer(59));
list.addLast(new Integer(7));
Integer obj = list.removeLast();  // pop
Integer obj = list.getLast();  // top
```

7 -> popped
59
12

addFirst(), removeFirst(), getFirst()

### classes for queue

```java
LinkedList<String> queue = new LinkedList<String>();
queue.offer("rabbit");
queue.offer("deer");
queue.offer("tiger");

str = queue.poll(); // pop
str = queue.peek(); // front
```

### classes for Hash table

#### HashMap
```java
HashMap<String, Integer> hashtable = new HashMap<String, Integer>();  // count = 16
HashMap<String, Integer> hashtable = new HashMap<String, Integer>(100); // count = 100

hashtable.put("harry", new Integer(95)); // harry->85
hashtable.get("harry");
hashtable.remove("harry");

```

hash code?
```java
String obj = new String("harry");
int hash1 = obj.hashCode();
```

use custom class as a key
```java
class Name{
    String firstName;
    String lastName;
    Name(String firstName, String lastName) {
      this.firstName = firstName;
      this.lastName = lastName;
    }

    // need to override hashCode() function in Name class
    public int hashCode() {
      return 1; // not good
    }
    public int hashCode() {
      return firstName.length() + lastName.length(); // also not good
    }
    public int hashCode() {
      return firstName.hashCode() + lastName.hashCode(); // good but still return null <- can not get value by get()
    }
    // put, get, remove is now working, because equals method also need to be override
    public boolean equals(Object obj) {
      if(!(obj instanceof Name)) {
        return false;
      }
      Name name = (Name) obj;
      if(firstName.equals(name.firstName) && lastName.equals(name.lastName)) {
        return true;
      }
      else {
        return false;
      }
    }
}

class HashMapExample {
  public static void main(String args[]) {
    HashMap<Name, Integer> hashtable = new HashMap<Name, Integer>();
    hashtable.put(new Name("harry", "porter"), new Integer(95));
    Integer num = hashtable.get(new Name("harry", "porter")); // return null

    // why?
    Name obj1 - new Name("harry", "porter");
    Name obj2 - new Name("harry", "porter");
    int hash1 = obj1.hashCode(); // diffrent with hash2
    int hash2 = obj2.hashCode(); // diffrent with hash1

    // Name class' hashCode is from object class
    // need to override in Name class
     // go to  Name class
  }
}
```

### classes for set
```java
HashSet<String> set = new HashSet<String>();
set.add("java");
set.add("mocha");
int num = set.size();

// no sequence
Iterator<String> iterator = set.iterator();
while(iterator.hasNext()) {
  String str = iterator.next();
  // do something
}
```

### additional
* TreeSet : sorted, not duplicated
* HashMap : key/value
* LinkedList
* HashSet : fast search, not duplicated
* LinkedHashMap : sequence by insert, save the last access

Collections.sort()


#### String
```java
length
charAt
String str = new String(arr) // Array
String str1 = new String("Hello java"); // string literal

// 1 string literal object and 3 string object(string refer literal object)
String str1 = new String("Hello World"); // string literal
String str2 = new String("Hello World"); // string literal
String str3 = new String("Hello World"); // string literal

// compare
if(str1 == str2) {} // compared by address
str.equals(str2)

// Extracting
str.substring(3); // 3~end
str.substring(3,7); // 3~6(endIndex-1)
```

String concat(String str) | source+target
String trim() | delete blank at beginning and end
String toUpperCase() |
String toLowerCase() |
String replace(char oldChar, char newChar) |

#### StringBuilder
```java
sb1 = new StringBuilder("Hello"); // size 11
sb2 = new StringBuilder(100);   // size 21
sb3 = new StringBuilder(); // size 16
```
StringBuilder append(String str) | source+target
StringBuilder insert(int offset, String str) |
stringBuilder delete(int start, int end) | dele start~ end-1
stringBuilder deleteCharA(int index) | delete one char

return is not the object, just reference

* buffer size is capacity
int bufSize = sb.capacity(); // return sb'size
```java
StringBuilder sb;
sb = new StringBuilder("Hello");
String str = sb.toString();
int len = sb.length();
int bufSize = sb.capacity();
sb.ensureCapacity(100); // extend capacity larger than requested
sb.trimToSize();
```

#### StringBuffer
different with stringBuilder, but few APIs are common.
refer to 'StringBuilder'

#### StringTokenizer
```java
import java.util.StringTokenizer;
// or
import java.util.*;
```

* default delimiter is blank

StringTokenizer stok = new StringTokenizer("apple peach banana");
str1 = stok.nextToken(); // apple
str2 = stok.nextToken(); // peach
str3 = stok.nextToken(); // banana
str4 = stok.nextToken(); <<-- raise NoSuchElementException

```java
StringTokenizer stok = new StringTokenizer("apple peach banana");

while(stok.hasMoreTokens()) {
  str = stok.nextToken();
  System.out.println(str);
}
```

* change delimiter to comma
StringTokenizer stok = new StringTokenizer("apple,peach,banana", ",");
StringTokenizer stok = new StringTokenizer("apple,peach|banana", ",|"); // both

* treat delimiter as token
```java
StringTokenizer stok = new StringTokenizer("apple,peach|banana", ",|", true);
while(stok.hasMoreTokens()) {
  String token = stok.nextToken();
  if(token.equals("="))
    System.out.print("\t");
  else if(token.equals("|"))
    System.out.print("\n");
  else
    System.out.print(token);
}
```


### Math
Math class is static
```java
int x = Math.round(42.2);
int y = min(56,12);
int z = Math.abs(-343);
double d = Math.random(); // [0.0~1.0)
```


Enjoy it!!!
