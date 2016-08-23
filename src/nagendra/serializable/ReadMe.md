# What is the use of serialVersionUID
Employee.java
```
package nagendra.serializable;
import java.io.Serializable;
public class Employee implements Serializable
{
   public String firstName;
   public String lastName;
   private static final long serialVersionUID = 8106990931l;
}
```
SerializaitonClass.java
```
package nagendra.serializable;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
public class SerializaitonClass {
	public static void main(String[] args) {
		Employee emp = new Employee();
		emp.firstName = "Nagendra";
		emp.lastName = "Prasad";
		try {
			FileOutputStream fileOut = new FileOutputStream("./employee.txt");
			ObjectOutputStream out = new ObjectOutputStream(fileOut);
			out.writeObject(emp);
			out.close();
			fileOut.close();
			System.out.printf("Serialized data is saved in ./employee.txt file");
		} catch (IOException i) {
			i.printStackTrace();
		}
	}
}
```


DeserializationClass.java
```
package nagendra.serializable;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
public class DeserializationClass {
	public static void main(String[] args) {
		Employee emp = null;
		try {
			FileInputStream fileIn = new FileInputStream("./employee.txt");
			ObjectInputStream in = new ObjectInputStream(fileIn);
			emp = (Employee) in.readObject();
			in.close();
			fileIn.close();
		} catch (IOException i) {
			i.printStackTrace();
			return;
		} catch (ClassNotFoundException c) {
			System.out.println("Employee class not found");
			c.printStackTrace();
			return;
		}
		System.out.println("Deserializing Employee...");
		System.out.println("First Name of Employee: " + emp.firstName);
		System.out.println("Last Name of Employee: " + emp.lastName);
	}
}
```
Run Serialization.java 

Serialized data is saved in ./employee.txt file

It will first create a file with Employee object’s state and then while de-serialization it creates object from the same file.  Output will be something like below.

Run Deserialization.java
```
Deserializing Employee...
First Name of Employee: Nagendra
Last Name of Employee: Prasad
```
Employee.java
```
package nagendra.serializable;
import java.io.Serializable;
public class Employee implements Serializable
{
   public String firstName;
   public String lastName;
   public String address;
   //private static final long serialVersionUID = 8106990931l;
}
```
Now run “DeserializationClass.java” and see the output.
```
java.io.InvalidClassException: nagendra.serializable.Employee; local class incompatible: stream classdesc serialVersionUID = 8106990931, local class serialVersionUID = -3332965514060056883
	at java.io.ObjectStreamClass.initNonProxy(Unknown Source)
	at java.io.ObjectInputStream.readNonProxyDesc(Unknown Source)
	at java.io.ObjectInputStream.readClassDesc(Unknown Source)
	at java.io.ObjectInputStream.readOrdinaryObject(Unknown Source)
	at java.io.ObjectInputStream.readObject0(Unknown Source)
	at java.io.ObjectInputStream.readObject(Unknown Source)
	at nagendra.serializable.DeserializationClass.main(DeserializationClass.java:17)
```

It will throw an incompatible exception. Because the given class Employee.java was changed in between serialization and de-serialization process. Hence the system failed to identify that it is still the same class. To make our system understand that it is the same class you have to make use of serialVersionUID  variable inside class.

### Important Points about Serialization


- Defining a serialVersionUID field in serializable class is not mandatory.
- If a serializable class has an explicit serialVersionUID then this field should be of type long and must be static and final.
- If there is no serialVersionUID field defined explicitly then serialization runtime will calculate default value for that class. The value can vary based on compiler implementation. Hence it is advisable to define serialVersionUID.
- It is advised to use private access modifier for serialVersionUID.
    Different class can have same serialVersionUID.
- Array classes cannot declare an explicit serialVersionUID, so they always have the default computed value, but the requirement for matching serialVersionUID values is waived for array classes.
- If there is a difference between serialVersionUID of loaded reciever class and corresponding sender class then InvalidClassException will be thrown.
- You should use different serialVersionUID for different version of  same class if you want to forbid serialization of new class with old version of same class.


Author
----

Nagendra Prasad

