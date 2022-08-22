# Write a program to print occurance of each character using java  

Source Code
```
package user.nagendra;
public class Main {
    public static void main(String[] args) {
        String exampleString = "This is just a sample string";
        long totalCharacters = exampleString.chars().filter(ch -> ch != ' ').count();
        System.out.println(exampleString);
        char[] x = exampleString.toCharArray();
        System.out.println("Total Characters :"+ totalCharacters);
        System.out.println("Chars "+ x);
        int iCharacter = 0;
        char temp;
        for(int characterIndex=0;characterIndex< x.length; characterIndex++){
            for(int i=0;i<exampleString.length();i++) {
                temp = exampleString.charAt(i);
                if (temp == x[characterIndex]) {
                    iCharacter++;
                }
            }
            System.out.println(x[characterIndex] + " appears  :" + iCharacter);
            iCharacter=0;
        }

    }
}
```

Output :

```
This is just a sample string
Total Characters :23
Chars [C@16b98e56
T appears  :1
h appears  :1
i appears  :3
s appears  :5
  appears  :5
i appears  :3
s appears  :5
  appears  :5
j appears  :1
u appears  :1
s appears  :5
t appears  :2
  appears  :5
a appears  :2
  appears  :5
s appears  :5
a appears  :2
m appears  :1
p appears  :1
l appears  :1
e appears  :1
  appears  :5
s appears  :5
t appears  :2
r appears  :1
i appears  :3
n appears  :1
g appears  :1
```
