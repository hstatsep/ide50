# Java Setup

## Make sure future java classwork is organized
```
cd ~
mkdir java
cd java
mkdir java-apcsa
cd java-apcsa
mkdir u00-other u01-primitives u02-objects u03-booleans-ifs u04-iteration u05-classes u06-arrays u07-arraylist u08-2d-arrays u09-inheritance u10-recursion u11-ap-prep
```

## Make a template file
* `touch Template.java`
* Open it, then paste the following code:
```java
import java.util.Scanner;
import java.lang.Math;

class Template {
    public static void main(String[] args) {

        Scanner scan = new Scanner(System.in);

        System.out.println("Hello World");

    }
}
```
_Note: your filename MUST match the class name._
_Naming convention: FirstLetterOfEveryWordCapitalized.java_

## Hello World
```
cd u00-other
mkdir HelloWorld
cd HelloWorld
touch Hello.java
```
* Open `Hello.java` and paste in the same code from your template (but update the class name!)
* `javac Hello.java`
* `java Hello`
* You should see `Hello World` in your terminal

* As a general rule of thumb, use this same format when making new programs (`cd` into the correct directory, make a folder with the appropriate name, `cd` into it, then name your file `WhateverYouWant.java` which will then get compiled to `WhateverYouWant.class`)
  * As a shortcut, you can copy with the `cp source destination` command. I.e. once you make your `HelloWorld` directory and `cd` into it, you could do `cp ~/java/java-apcsa/template.java ./WhateverYouWant.java`

## Java compile and run
#### Setting this up allows you to compile and run in the same command
`nano ~/.bash_profile`  
Paste the following:  
`jcar() { javac $1.java && java $1 ; }`  
Do <kbd>control</kbd>+<kbd>X</kbd> to quit, <kbd>Y</kbd> to save, then press <kbd>ENTER</kbd>
#### To use, type `jcar Program` (using your own Java program file, but with no `.java`)
* Try this out by adding `!` to your **Hello World** program so that it outputs `Hello World!`
* Run the shortcut by doing `jcar Hello`
