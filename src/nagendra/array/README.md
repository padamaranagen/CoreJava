# Array

>An ordered collection of primitives or objects. When you declare an array, you specify the element type,  and the resulting array can contain only elements of that type.

### What is an array element?
>Each item stored in an array is considered an element of the array. Each array element must be the same type as the array itself. For example, an int array contains some number of int array elements.

Note:

-	All arrays are immutable. If you have an array with six elements in it and you want it to hold seven, you must create a new array. An array is not meant to be a dynamically sized collection type, so don’t try to use it that way.
-	Think about the main method that you have been working with so far:
```
public static void main(String[] args)
```
- Earlier, you learned that the parameter to this method is in fact an array of String objects. Each element in this array is one argument passed on the command line to the class that holds this main method. What is the length of that array? You have no way to answer that right now, do you? Until you actually pass the command-line arguments, there is no way of telling. If you pass two arguments, the length of args will be two. If you pass zero arguments, the length will be zero. This demonstrates an array’s length being determined at runtime. Once the array length is determined, however, it cannot change.

What really happens when you pass command-line arguments is that the JVM creates a new array and populates it with each of the arguments that you passed (if any).

-	Arrays contain multiple items.
-	Each item in an array is called an element.
-	All the elements in an array must be the same type.
-	The length of an array is determined at runtime.
	The length of an array can never change.
-	The contents of an array can be changed dynamically.
-	All arrays are objects, regardless of their content type.
-	Array indexes start at zero and go to (length – 1).

So far you have been using System.out.printn() to output messages to the command line. When you output error messages, you should normally use System.err.println() instead. This outputs the message to the standard error of your system. This is normally just the command line, but using System.err ensures that all error messages go to the right place.


### Array Initializer
>A special variation to creating an array that does not require you to explicitly set the length. Instead, the contents of the array are put right inside a pair of braces ({}), and a comma separates each element. The resulting array’s length equals the number of elements listed between the braces.

```
String [] names={"nagendra","Lakshmi","Ram","Pandu","Krishna"};

System.out.println("There are "+names.length+ " names in the address book.");     

```

### Java Array Default Values
-	byte – default value is zero
-	short – default value is zero
-	int – default value is zero
-	long – default value is zero, 0L.
-	float – default value is zero, 0.0f.
-	double – default value is zero, 0.0d.
-	char – default value is null, ‘\u0000′.
-	boolean – default value is false.
-	reference types – default value is null.

#### Examples
- Single Dimensional  
- Double Dimensional
- Three Dimensional
- Jagged 

 

Author
----

Nagendra Prasad

