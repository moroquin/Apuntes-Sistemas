If you are starting with java you can create a new text file name "HelloWorld.java", the content of the file should be

```java
public class HelloWorld{
	public static void main(String[] args){
		System.out.println("Hello World");
	}
}
```

To execute the first class you can run in your terminal
```bash 
java HelloWorld.java
```
Make sure that the terminal is located in the directory where you created the file. We execute our first program in java. Since java 11 if you have code in one file you can run it this way. It is important to mention that if you use this way to run java files you only can use the classes that came with the jdk. 

Other way to execute the program is to compile the java file first

```bash
javac HelloWorld.java
```
 The result of the compilation should be a HelloWorld.class. This file must be executed 
 ```java
 java HelloWorld
 ```
It is important to not include the *.class* in the command. 