# HelloWorld Example

```
/*
* The traditional HelloWorld example
*/

public class HelloWorld
{
    public static void main(String args[])
    {
        System.out.println("Hello World!");
    }
}

```



### The public Keyword
>The public keyword is the access modifier. The main() method must be public so that the interpreter can invoke the method for you. If you forget to use the public modifier, the interpreter will not be able to run the code.

### The static Keyword
>The static keyword is needed so that the interpreter can access the method right from the class instead of requiring an object. A nonstatic method can be called only if an object has been created from a class. A static method can be called without any objects being created.

>Because the main() method is providing the bootstrap entry point into your code, no objects are present yet. That is why you must always include the static keyword in this method.

### The void Return Type
>The main() method always returns void and can never return anything else. If you try to return something other than void from the main() method, your code will not run at all.

### The main() Method
>All Java programs include a special method called main(). This is the only method defined in the HelloWorld class, and it is the method that makes a Java program go. To execute this code, you typed the following line at your command prompt:

```
java HelloWorld
```

>Whenever you invoke a program using java, the main() method is automatically executed. Whatever you instructed the main() method to do is carried out at that time. For that reason, the main() method can be called the bootstrap method of all Java applications. It is the method that makes everything else execute.

### Compile & Execute
```
javac HelloWorld.java
java HelloWorld
Hello World!
```

>The interpreter (java) automatically appends the .class extension, so do not include it on the command line. If you do, you will receive an error message telling you that the interpreter cannot find the specified class file. The interpreter reads in the class file and follows the bytecode instructions that the class contains.


# Working with Multiple Arguments

```
public class HelloWorldMultipleArgs
{
    public static void main(String args[])
    {
        System.out.println("Hello World!");
        System.out.println("Hello:"+args[0]);
        System.out.println("Hello:"+args[1]);
        System.out.println("Hello:"+args[2]);
    }
}
```

### Compile & Execute:
```
javac HelloWorldMultipleArgs.java
java HelloWorldMultipleArgs nag raj manju
Hello World!
Hello:nag
Hello:raj
Hello:manju
```

Author
----

Nagendra Prasad

