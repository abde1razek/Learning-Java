# Cheat Sheet

| What do you want?                  | Code                      |
| ---------------------------------- | ------------------------- |
| Print                              | System.out.print("");     |
| Print on one line                  | System.out.println("");   |
| Comment for one line               | //                        |
| Comment for multiple lines         | /* */                     |
| Concatenate strings with variables | ("bla bla" + var_name)    |
| Variables                          | [[#Variables]]            |
| User Input                         | [[#User Input]]           |
| Arithmetic Operators               | [[#Arithmetic Operators]] |
| If Statements                      | [[#If statements]]        |
| Random Numbers                     | [[#Random Numbers]]       |
|                                    |                           |
|                                    |                           |
# Tips & Tricks

* if you are lazy to write `System.out.println("");` you can type `sout` and then hit the `TAB` button.


# Main Course Notes

This section is for understanding the language
### Variables

It contains data and changeable.
There are two types of variables:
- Primitive = simple value directly in memory (stack) -> int, double, char, boolean
  // it is like giving you money cash
- Reference = memory address (stack) that points to the (heap) -> string, array, object
  // its like giving you a cheque

![[img/Pasted image 20251218205449.png|500]]

[What are Stack and Heap Memory? by Boot dev](https://www.youtube.com/watch?v=ep2xOW52mDY):
![[img/Pasted image 20251218210124.png]]

Declaration & Initialization & Assignment
![[img/Pasted image 20251218182803.png|500]]

you can declare and assign in the same line:
```java
String food = "Pizza";
```

You can't name your variables with this words
![[Pasted image 20251218194708.png|500]]

Ways to name a variable
![[Pasted image 20251218184007.png|500]]

variables examples
![[Pasted image 20251218183052.png|500]]

```java
int age = 22;
double price = 39.99;
char currency = '$'; // singe quote
boolean isStudent = true;
String name = "Abdelrazek"; // with capital S and double quotes
```

### User Input

First you need to import `Scanner` class from util
```java
import java.util.Scanner;
// then in the class
Scanner scanner = new Scanner(System.in);
// after you take the input close the scanner
scanner.close();
```

```java
String name = scanner.nextLine();
int age = scanner.nextInt();
double gpa = scanner.nextDouble();
boolean isStudent = scanner.nextBoolean();
```

If you want only get the first input like first name and discard the rest (everything comes after the first space will be thrown)
```java
String name = scanner.next();
```

For UX, there are two ways of asking the user for an input.
on new line or in the same line.
![[Pasted image 20251218191900.png]]
```java
System.out.println("What is your name?");  
String name = scanner.nextLine();  
  
System.out.print("What is your name: ");  
String name2 = scanner.nextLine();
```

There is a common issues;
When you ask for integer/double before a string then hit enter, this enter goes for the buffer as `\n` which is new line.
```java
Scanner scanner = new Scanner(System.in);  
  
System.out.print("Enter your age: ");  
int age = scanner.nextInt();  
  
System.out.print("Enter your name: ");  
String name = scanner.nextLine();  
  
System.out.println("Your age is " + age );  
System.out.println("Your name is " + name );

scanner.close();
```
![[Pasted image 20251218192829.png]]
To fix this; after taking int/double input add
```java
scanner.nextLine();
```

Example:
 ```java
// calculating the area of a rectangle
Scanner scanner = new Scanner(System.in);  
  
double width = 0;  
double height = 0;  
double area = 0;  
  
System.out.print("Enter the width: ");  
width = scanner.nextDouble();  
  
System.out.print("Enter the height: ");  
height = scanner.nextDouble();  
  
area = width * height;  
  
System.out.println("The area is " + area + "cm²");  
  
scanner.close();
 ```
![[Pasted image 20251218193641.png]]

### Arithmetic Operators

the `-=`, `+=`, etc. called augmented assignment operators.
![[Pasted image 20251218194848.png|500]]
Order of operations \[P-E-M-D-A-S]
![[Pasted image 20251218195649.png|500]]

  
### (task) Shopping Cart
```java
String item;  
double price;  
int quantity;  
  
Scanner scanner = new Scanner(System.in);  
System.out.print("What item would you like to buy?: ");  
item = scanner.nextLine();  
System.out.print("What is the price for each?: ");  
price = scanner.nextDouble();  
System.out.print("How many would you like?: ");  
quantity = scanner.nextInt();  
  
System.out.println("You have bought " + quantity + " " + item + "/s");  
System.out.println("Your total is $" + price * quantity);  
  
scanner.close();
```
![[Pasted image 20251218200637.png]]

### If statements
```java
Scanner scanner = new Scanner(System.in); 
 
System.out.print("What is your age?: ");  
int age = scanner.nextInt();  
  
if (age >= 123){  
    System.out.println("You are DEAD!");  
}  
else if (age >= 65){  
    System.out.println("You are a senior!");  
}  
else if (age >= 18) {  
    System.out.println("You are an adult!");  
}  
else if (age < 0) {  
    System.out.println("You are not born yet!");  
}  
else if (age == 0) {  
    System.out.println("You are about to be born!");  
}  
else {  
    System.out.println("You are a child!");  
}  

scanner.close();
```

Be careful, if two conditions met the program executes the first.

To check if variable is empty
```java
if(name.isEmpty()){
	System.out.println("You didn't enter your name!");
}
else if (){
	System.out.println("Hello " + name + "!");
}
```

### Random Numbers

You need to import `Random` class from util.
```java
import java.util.Random;
// then in class
Random random = new Random();
```

To get random integer or double or boolean
```java
int number = random.nextInt();
Double number = random.nextDouble(); // a number between 0 and 1 like 0.223
boolean isHeads = random.nextBoolean();
```

In nextInt`(bound)`/`(origin, bound)` you can add a range to get a random number from, but you won't get the value of bound.
```java
int number = random.nextInt(101); 
// [0,100]
int number = random.nextInt(50,100);
// [50,99]
```

### Math

![[Pasted image 20251218210547.png|500]]

```java
Math.round(3.14); // 3.0
Math.ceil(3.14); // 4.0
Math.floor(3.99); // 3.0
```

#### (Example) Hypotenuse
![[Pasted image 20251218211305.png|300]]

```java
Scanner scanner = new Scanner(System.in);  
  
System.out.print("Enter A: ");  
double A = scanner.nextDouble();  
System.out.print("Enter B: ");  
double B = scanner.nextDouble();  
  
double C = Math.sqrt(Math.pow(A, 2) + Math.pow(B, 2));  
System.out.println("C = " + C);  
  
scanner.close();
```
![[Pasted image 20251218211826.png]]

#### (Example) Some circle shit
![[Pasted image 20251218212132.png|300]]

```java
Scanner scanner = new Scanner(System.in);  
  
double PI = Math.PI;  
  
System.out.print("Enter the radius: ");  
double radius = scanner.nextDouble();  
  
double circumference = 2 * PI * radius;  
double area = PI * Math.pow(radius, 2);  
double volume = 4.0 / 3.0 * PI * Math.pow(radius, 3);  
  
System.out.println("The circumference is = " + circumference + "cm");  
System.out.println("The area is = " + area + "cm²");  
System.out.println("The volume is = " + volume + "cm³");  
  
scanner.close();
```

![[Pasted image 20251218213037.png|300]]
if you only wants one digit after the decimal use `printf`.
```java
System.out.printf("The circumference is = %.1fcm\n", circumference);  
System.out.printf("The area is = %.1fcm²\n",area);  
System.out.printf("The volume is = %.1fcm³\n",volume);

/*
Enter the radius: 5
The circumference is = 31.4cm
The area is = 78.5cm²
The volume is = 523.6cm³
*/
```

### printf()

Is a method used to format output
```java
// syntax
%[flags][width][.precision][specifier-character]
```

\[specifier-character]
%s -> string
%c -> char
%d -> int
%f -> double, float
%b -> boolean

```java
String name = "Sponge bob";  
char firstLetter = 'S';  
int age = 22;  
double height = 60.5;  
boolean isEmployed = true;  
  
System.out.printf("Hello %s\n", name);  
System.out.printf("Your name starts with a %c\n", firstLetter);  
System.out.printf("You are %d years old\n", age);  
System.out.printf("You are %f inches tall\n", height);  
System.out.printf("Employed status: %b\n", isEmployed);  
  
System.out.printf("%s is %d years old", name, age);

/*
Hello Sponge bob
Your name starts with a S
You are 22 years old
You are 60.500000 inches tall
Employed status: true
Sponge bob is 22 years old
*/
```

\[.precision]
limit the amount of digits that display after decimal
```java
double price1 = 9.987;  
double price2 = 100.324;  
double price3 = -45.6767;  
  
System.out.printf("%.1f\n", price1);  
System.out.printf("%.2f\n", price2);  
System.out.printf("%.3f\n", price3);

/*
10.0
100.32
-45.677
*/
```

\[flags]
\+ = output a plus
, = comma grouping separator
( = negative numbers are enclosed in ()
space = display a minus if negative, space if positive

```java
double price1 = 99.987;  
double price2 = 100600.324;  
double price3 = -454.6767;  
double price4 = -36.7841;  
  
System.out.println("++++++++++++++");  
System.out.printf("%+.2f\n", price1);  
System.out.printf("%+.2f\n", price2);  
System.out.printf("%+.2f\n", price3);  
System.out.printf("%+.2f\n", price4);  
  
System.out.println();  
System.out.println(",,,,,,,,,,,,,,");  
System.out.printf("%,.2f\n", price1);  
System.out.printf("%,.2f\n", price2);  
System.out.printf("%,.2f\n", price3);  
System.out.printf("%,.2f\n", price4);  
  
System.out.println();  
System.out.println("((((((((((((((");  
System.out.printf("%(.2f\n", price1);  
System.out.printf("%(.2f\n", price2);  
System.out.printf("%(.2f\n", price3);  
System.out.printf("%(.2f\n", price4);  
  
System.out.println();  
System.out.println("space space space");  
System.out.printf("% .2f\n", price1);  
System.out.printf("% .2f\n", price2);  
System.out.printf("% .2f\n", price3);  
System.out.printf("% .2f\n", price4);
```

![[Pasted image 20251218220253.png|100]]

\[width]
0 = zero padding
number = right justified padding
negative number = left justified padding

```java
int id1 = 1;  
int id2 = 23;  
int id3 = 456;  
int id4 = 7890;  
  
System.out.println("Zero Padding");  
System.out.printf("%04d\n", id1);  
System.out.printf("%04d\n", id2);  
System.out.printf("%04d\n", id3);  
System.out.printf("%04d\n", id4);  
System.out.println();  
  
System.out.println("Right Justified Padding");  
System.out.printf("%4d\n", id1);  
System.out.printf("%4d\n", id2);  
System.out.printf("%4d\n", id3);  
System.out.printf("%4d\n", id4);  
System.out.println();  
  
System.out.println("Left Justified Padding");  
System.out.printf("%-4d\n", id1);  
System.out.printf("%-4d\n", id2);  
System.out.printf("%-4d\n", id3);  
System.out.printf("%-4d\n", id4);  
System.out.println();
```
![[Pasted image 20251218220823.png|200]]


