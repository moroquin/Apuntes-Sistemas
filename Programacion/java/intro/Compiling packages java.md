## pre-requisites

To do this mini how-to you need:

* JDK installed on your machine. At least version 8. 
* Text editor
* Access to your terminal (bash)
* If you want to build the [example you can download the project from github](https://github.com/sierra-oe/TheLordOfTheRings-TerminalGame-Java)
	* If you want to clone the project with github you need to install de local client for your operative system. 

## Setup the project 

You can download the project from github as zip or you can clone the repo with the next command:

```bash
git clone https://github.com/sierra-oe/TheLordOfTheRings-TerminalGame-Java
```

Once you have the folder, the structure of the prejct that we aim to build is:

![root projecto tlofr](./compilingPackages1.png)
We are going to describe the packages and folders we have in the project:
* **src** we have these folder for have all our code, it is important to notice that *src* is not part of the packages. 
* **org/ipc1/tlotr** is the main folder, that has the main package **org.ipc1.tlotr**. In these folder whe have our entry point in the file *Main.java*. 
* **org/ipc1/tlotr/util** has a files that are utilery for the project
* **org/ipc1/tlotr/characters** has the class for the characters. 
* **org/ip1/tlotr/characters/heroes** has the classes for the heroes characters. 
* **org/ip1/tlotr/characters/beasts** has the classes for the heroes beasts. 

Defining the entry point, that is de file that we need to execute, it should be:

**org/ipc1/tlotr/Main.java**

We want to have a *build* folder to save the bytecode files (.class). For that, 
 we are going to create a folder. If you are using GNU/Linux you can do that with the next command.

```bash
mkdir build
```

Now we have the project structure like that:

![root projecto tlofr](./compilingPackages2.png)

## Compile the project
To compile the project, is important to pay attention to the next things

* To use the *javac* command you need to be in the source code folder, in these example we need to be inside the *src* folder because all the packages does not include the src in their definition. 
* You can not compile verifing recuersive all the folders, you need to compile each folders files. 

we can execute the Java compiler with the next command in bash.


```bash
cd src
javac -d ../build org/ipc1/tlotr/*.java
javac -d ../build org/ipc1/tlotr/util/*.java
javac -d ../build org/ipc1/tlotr/characters/*.java
javac -d ../build org/ipc1/tlotr/characters/beasts/*.java
javac -d ../build org/ipc1/tlotr/characters/heroes/*.java
```

Or we can execute all in the same line 

```bash
cd src
javac -d ../build org/ipc1/tlotr/*.java org/ipc1/tlotr/util/*.java org/ipc1/tlotr/characters/*.java org/ipc1/tlotr/characters/beasts/*.java org/ipc1/tlotr/characters/heroes/*.java
```

* **javac** is the java compiler
* **-d** argument tells the compiler where the compile files should be saved. In this case **./build** is the route.
* **src/HelloWorld.java src/Main.java** tells the compiler which files should compile

Another variant to the command before could be

```bash
javac -d ./build src/*.java
```

The only change is how we specify the files to compile 

* **src/\*.java**  specifies that we want to compile all the java files. For that we use the wild card **\***.  

## The output of the compile

Now we can see that the compiler creates files in the *src* folder with the *.class* extension.

![tree 3](./treeMultipleFiles3.png)

## Executing our project
To execute our project, we must type in our terminal the next command: 

```bash
java -cp ./build Main
```

* **java** basically starts an application by starting the Java virtual machine. 
* **-cp** specifies the directory where our compiled files are. In this case we have the *build* folder for that. Thats the reason for write **./build**
* **Main** in this case, Main is the name for the class that has the entry point. In java the entry point is the method *public static void main(String[] args)*

![tree 4](./treeMultipleFiles4.png)

