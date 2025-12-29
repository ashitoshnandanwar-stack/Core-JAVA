# Core-JAVA
Code and Notes of java
### Precedence
| Priority | Operators      | Description                       |   |            |
| -------- | -------------- | --------------------------------- | - | ---------- |
| 1        | `()`           | Parentheses                       |   |            |
| 2        | `++  --`       | Increment / Decrement             |   |            |
| 3        | `*  /  %`      | Multiplication, Division, Modulus |   |            |
| 4        | `+  -`         | Addition, Subtraction             |   |            |
| 5        | `<  <=  >  >=` | Relational                        |   |            |
| 6        | `==  !=`       | Equality                          |   |            |
| 7        | `&&`           | Logical AND                       |   |            |
| 8        | `||`           | Logical OR                        | ` |            |
| 9        | `=` `+=` `-=`  | Assignment                        |   |            |

```
 class operators 
    {
        public static void main(String args[])
        {
            int var1 = 5; 
            int var2 = 6;
            int var3;
            var3 = ++ var2 * var1 / var2 + var2;
            System.out.print(var3);
        } 
    }
Output : 12
Explanation: Operator ++ has the highest precedence than / , * and +.
var2 is incremented to 7 and then used in expression, var3 = 7 * 5 / 7 + 7, gives 12.
```
```
class operators 
    {
        public static void main(String args[]) 
        {    
             int x = 8;
             System.out.println(++x * 3 + " " + x);
        } 
    }
Output : 27 9
Explaination : Operator ++ has higher precedence than multiplication operator, *, x is incremented to 9 than multiplied with 3 giving 27.
				9*3+_+9 gives 27 9
```
### Control Statements
- Switch statements checks for equality between the controlling variable and its constant cases.
- The do-while loop is also known as exit control loops, because it executes the code of the block before checking the conditional statement.
- The continue statement skips the remaining code in the loop body for the current iteration and moves to the next one. It doesn’t exit the loop, just skips that specific pass.
- While loop repeats a set of code only until the condition is met to be false.
- Break halts the execution and forces the control out of the loop
```
Which of the following is not a decision making statement?
a) if
b) if-else
c) switch
d) do-while
View Answer

Answer: d
Explanation: do-while is an iteration statement. Others are decision making statements.
```
### Data type and variable
| Data Type   | Category  | Size             | Range                                                   |
| ----------- | --------- | ---------------- | ------------------------------------------------------- |
| **byte**    | Integer   | 1 byte (8 bit)   | -128 to 127                                             |
| **short**   | Integer   | 2 bytes (16 bit) | -32,768 to 32,767                                       |
| **int**     | Integer   | 4 bytes (32 bit) | -2,147,483,648 to 2,147,483,647                         |
| **long**    | Integer   | 8 bytes (64 bit) | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| **float**   | Floating  | 4 bytes (32 bit) | ±3.40282347E38                                          |
| **double**  | Floating  | 8 bytes (64 bit) | ±1.79769313486231570E308                                |
| **char**    | Character | 2 bytes (16 bit) | 0 to 65,535 (Unicode)                                   |
| **boolean** | Logical   | JVM dependent*   | true / false                                            |

- Boolean variable can contain only one of two possible values, true and false. Everything in lowercase. Capitalized True and False are not boolean values in Java.

 ```
 class mainclass {
        public static void main(String args[]) 
        {
            boolean var1 = true;
	           boolean var2 = false;
	    if (var1)
	        System.out.println(var1);
	    else
	        System.out.println(var2);
       } 
    }
output : true
```
```
class booloperators {
        public static void main(String args[]) 
        {
            boolean var1 = true;
	    boolean var2 = false;
	    System.out.println((var1 & var2));
        } 
    }
Output : false
Explaination : boolean ‘&’ operator always returns true or false. It returns true when both the values are true and false otherwise.
Since, var1 is defined true and var2 is defined false hence their ‘&’ operator result is false.

class booloperators {
        public static void main(String args[]) 
        {
            boolean var1 = true;
	    boolean var2 = false;
	    System.out.println((var1 || var2));
        } 
    }
output : true
Explanation : In this one condition are true, because result is true.
```
##### Enum
- An enum (enumeration) in Java is a special data type used to define a fixed set of constants.
- Introduced in Java 5 <br>
eg. enum Day { MON, TUE, WED, THU, FRI, SAT, SUN } <br>
-  order of appearance of variables in Enum is their natural order (the natural order means the order in which they are declared inside Enum type). However, the compareTo() method is implemented to order the variable in ascending order.
-  No, instances of Enum cannot be created outside of Enum boundary, because Enum does not have a public constructor.
-  The ordinal() method retrieves the ordinal value of an enum constant, which represents its position within the enum declaration, starting from 0.
-  Enum cannot have any modifiers. They are public, static and final by default.
-  Enum types cannot extend class.

| Method      | Use                      |
| ----------- | ------------------------ |
| `values()`  | Returns all constants    |
| `valueOf()` | Converts String → enum   |
| `ordinal()` | Position (starts from 0) |
| `name()`    | Returns constant name    |

```
class TestEnum {
    enum Color { RED, GREEN, BLUE }

    public static void main(String[] args) {
        Color c = Color.RED;
        System.out.println(c);
    }
}
Output : RED
```
```
enum Enums
{
    A, B, C;
 
    private Enums()
    {
        System.out.println(10);
    }
}
 
public class MainClass
{
    public static void main(String[] args)
    {
        Enum en = Enums.B;
    }
}
Output : 10
         10
         10
```
#### Big Decimal
- BigDecimal has unnatural syntax, needs more memory and creates a great amount of garbage. But it has a high precision which is useful for some calculations like money.
- int, float, double provide overloaded methods for +,-,* and /.  But BigDecimal does not provide these overloaded methods.
- BigDecimal.ONE is a static variable of BigDecimal class with value 1 on scale 0.
- MathContext class is a library of functions to perform arithmetic operations of BigInteger and BigDecimal.
```
import java.math.*;
class Main
{
    public static void main(String args[])
    {
        double a = 0.02;
        double b = 0.03;
        double c = b - a;
        System.out.println(c);
 
        BigDecimal _a = new BigDecimal("0.02");
        BigDecimal _b = new BigDecimal("0.03");
        BigDecimal _c = _b.subtract(_a);
        System.out.println(_c);
    }
}
Output :  0.009999999999999998
          0.01
Explaination : BigDecimal provides more precision as compared to double. Double is faster in terms of performance as compared to BigDecimal.
```
##### DATE and Time
- SimpleDateFormat takes a string containing pattern. sdf.format converts the Date object to String.
- SimpleDateFormat takes a string containing pattern. sdf.parse converts the String to Date object.
##### Literals and variable
- A literal is a fixed value written directly in the program.
 ```
int a = 10;      // 10 is a literal
char c = 'A';   // 'A' is a literal
String s = "Hi"; // "Hi" is a literal
```
| Type                  | Example    |
| --------------------- | ---------- |
| Decimal (base 10)     | `10`, `25` |
| Octal (base 8)        | `010`      |
| Hexadecimal (base 16) | `0x1A`     |
| Binary (base 2)       | `0b1010`   |

- A variable is a named memory location used to store data.
- Data type long literals are appended by an L(uppercase) or l(lowercase).
  
- In Java, all arithmetic operations (+ - * /) promote operands smaller than int (byte, short, char) to int.
- The extension of a compiled Java class is .class.
##### Type casting
```
class conversion 
    {
        public static void main(String args[]) 
        {
            double a = 295.04;
            int  b = 300;
            byte c = (byte) a;
            byte d = (byte) b;
            System.out.println(c + " "  + d);
        } 
    }
Output : 39 44
Explaination : Type casting a larger variable into a smaller variable results in modulo of larger variable by range of smaller variable. b contains 300 which is larger than byte’s range i:e -128 to 127 hence d contains 300 modulo 256 i:e 44.
 byte store upto 128 max, because 300 = 128 + 128 + 44, hence for 300 show 44 answer
 for 295.04 = show 39 (in byte not show decimal value)
```

```
class A 
    {
        final public int calculate(int a, int b) { return 1; } 
    } 
    class B extends A 
    { 
        public int calculate(int a, int b) { return 2; } 
    } 
     public class output 
     {
        public static void main(String args[]) 
        { 
            B object = new B(); 
            System.out.print("b is " + b.calculate(0, 1));  
        } 
    }
Output : Compilation error
Explaination : The code does not compile because the method calculate() in class A is final and so cannot be overridden by method of class b.
```
##### Array
```
class main_arguments 
    {
        public static void main(String [] args) 
        {
           int arr[] = new int [5];
    System.out.print(arr);              
        }
    }
Output : classname@hashcode in hexadecimal form
Explaination : If we trying to print any reference variable internally, toString() will be called which is implemented to return the String in following form.
```

```
matrix sum calculate
eg.
1  2  3
4  5  6
1+2+3+4+5+6 = 21

eg.
 int array_variable[][] = {{ 1, 2, 3}, { 4 , 5, 6}, { 7, 8, 9}};
1+2+3+4+5+6+7+8+9 = 45

eg.
int[][] arr = {
    {1},
    {1, 2},
    {1, 2, 3}
};
sum = 10
```
```
int a[], b;
int []c, d;
ans :  ‘b’ is int variable; ‘d’ is int array
Explaination : If [] is declared after variable it is applicable only to one variable. If [] is declared before variable it is applicable to all the variables.
```
- Generics gives the flexibility to strongly typecast collections. Generics is applicable to Set, List and Tree. It is not applicable to Array.
-  Array is stored in heap space. Whenever an object is created, it’s always stored in the Heap space and stack memory contains the reference to it.
-  Array elements are stored in contiguous memory. Linked List is stored in random memory locations.

### Operands and Control Statements
- The operand of arithmetic operators can be any of numeric or character type, But not boolean.
- Modulus operator can be applied to both integers and floating point numbers.
  ```
  int x = 10;
	x =+ 1;
	System.out.println(x);
  output : 1
  Explaination : assign +1 to the x.
  ```
  ```
   class Output 
    {
        public static void main(String args[]) 
        {    
             int a = 1;
             int b = 2;
             int c;
             int d;
             c = ++b;
             d = a++;
             c++;
             b++;
             ++a;
             System.out.println(a + " " + b + " " + c + " " + d);
        } 
    }
Output : 3 4 4 1
Explainaion :   a = 1 , b = 2 
	c = ++b , means b = 3, c = 3;
	d = a++, means d = 1(first assign then increment), a = 2 ;
	c++ = 4 ;
	b++ = 3 ;
	++a = 3 ;
```
  ```
##### Bitwise operand
- Invert bits → add 1 → make negative
```
 class bitwise_operator 
    {
        public static void main(String args[])
        {
            int var1 = 42;
            int var2 = ~var1;
            System.out.print(var1 + " " + var2);     	
        } 
    }
    Output : 42 -43
	~x = -(x + 1)
```
```
class bitwise_operator 
    {
        public static void main(String args[]) 
        {    
             int a = 3;
             int b = 6;
 	    	 int c = a | b;
             int d = a & b;             
             System.out.println(c + " "  + d);
        } 
    }
Output : 7 2
Explaination :
Convert to bitwise
a = 3  → 0011
b = 6  → 0110

Bitwise OR (|)
Rule:
If any bit = 1 → result = 1
  0011
| 0110    (OR operand any one is 1 output is 1)
------
  0111
0111 (binary) = 7 (decimal)

Bitwise AND (&)
Rule:
If both bits = 1 → result = 1
  0011
& 0110    (AND operand both are 1 then output is 1 otherwise 0)
------
  0010
0010 (binary) = 2 (decimal)
```
- Left shift operator(<<) <br>
 Shifts bits to the left <br>
 Equivalent to multiplication by 2ⁿ
```
int a = 5;
System.out.println(a << 1);
5  = 00000101
<<1 = 00001010
value of a = 10

int x = 8;
System.out.println(x << 2);
8 × 2² = 32
32
```
- Right Shift operator(>>) <br>
Shifts bits to the right <br>
Equivalent to division by 2ⁿ
```
int a = 20;
System.out.println(a >> 2);  
20 ÷ 4 = 5
value 5
```
- What is " ?: " ? <br> 
?: is called the ternary operator or conditional operator.<br>
It is a short form of if–else. <br>
condition ? value_if_true : value_if_false;



### Use of "this"
- this points to the object that is calling the method or constructor.<br>
- 1️⃣ Differentiate instance variables from local variables
 When variable names are the same.
```
class Student {
    int id;
    Student(int id) {
        this.id = id;   // instance variable = local variable
    }
}
```
👉 Without this, Java gets confused.
<br>
- 2️⃣ Call current class instance variables.
```
class Test {
    void display() {
        System.out.println("Hello");
    }

    void show() {
        this.display(); // same as display()
    }
}
```

- 3️⃣ Call current class methods
```
class Test {
    void display() {
        System.out.println("Hello");
    }

    void show() {
        this.display(); // same as display()
    }
}
```

- 4️⃣ Invoke current class constructor (Constructor Chaining)
```
class Example {
    Example() {
        this(10);   // calls parameterized constructor
    }

    Example(int x) {
        System.out.println(x);
    }
}
```
📌 this() must be the first statement in constructor.

- 5️⃣ Pass current object as method parameter
```
class A {
    void print(A obj) {
        System.out.println("Object passed");
    }

    void call() {
        print(this);
    }
}
```

- 6️⃣ Return current object
```
class Demo {
    Demo getObject() {
        return this;
    }
}
```
### Polymorphism
- One thing, many forms
- One method but different behaviour
```
Real-Life Example
Think about a person 👇
At home → Father
At school → Teacher
At bank → Customer
👉 Same person, different roles
This is polymorphism.
```
- Why Do We Need Polymorphism?<br>
✔ Code reusability <br>
✔ Flexibility <br>
✔ Less code, more functionality <br>
✔ Supports dynamic behavior <br>

- Their two types of polymorphism 
1. Compile time polymorphism(method overloading) <br>
2. Runtime polymorphism (method overiding)

##### Compile time polymorphism (method overloading)
- same method name
- different parameters
- decide at compile time
```
class Main {
    static int add(int a, int b) {
        return a + b;
    }
    static double add(double a, double b) {
        return a + b;
    }
    public static void main(String[] args) {
        
    double a = 5.85;
    double b = 5.15;
    System.out.println(add(a, b));

    }
}
```
##### Run-time polymorphism (method overriding)
- Parent class reference
- Child class object
- Method call decided at runtime
```
class Animal {
    void sound() {
        System.out.println("Animal makes sound");}
}
class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
class Main {
    public static void main(String[] args) {  
       Animal a = new Dog();
       a.sound();
    }
}

output : Dog barks
```

- Example: Static Method (Important MCQ)
```
  class A {
    static void show() {
        System.out.println("A");
    }
}

class B extends A {
    static void show() {
        System.out.println("B");
    }
}
class Main {
    public static void main(String[] args) {  
      A a = new B();
      a.show();
}

Output : A 
*Reason = Static methods are not polymorphic
```
- Compile time is faster
- Constructor can not be overridden
- final method can not be overridden
- Polymorphism works only with methods, not with variables

##### Truncation
- Truncation refers to the removal of digits after the decimal point.
- When a floating-point value (float, double, etc.) is assigned to an integer type (int, long, etc.), the fractional part after the decimal point is discarded.
Note: This operation requires explicit type casting.

##### Selection Statement
- Selection statements decide which block of code will execute.
```
Their are 4 types of selection statment
1. if
if Statement
🔹 Meaning
Executes a block only if condition is true

2. if else
if-else Statement
🔹 Meaning
Executes one block if condition is true
Executes another block if condition is false

3. else-if Ladder
🔹 Meaning
Used when multiple conditions are checked

4. switch Statement
🔹 Meaning
Selects execution based on fixed values
Better than long if-else ladders
```
| Statement | Use Case            |
| --------- | ------------------- |
| `if`      | Single condition    |
| `if-else` | Two conditions      |
| `else-if` | Multiple conditions |
| `switch`  | Fixed values        |

```
class output 
    {
        public static void main(String args[])
        { 
           String c = "Hello i love java";
           boolean var;
           var = c.startsWith("Hello");
           System.out.println(var);
        }
    }
 Output : true
"But"
class output 
    {
        public static void main(String args[])
        { 
           String c = "Hello i love java";
           boolean var;
           var = c.startsWith("hello");
           System.out.println(var);
        }
    }
Output : false (because java is case sensitive.
```
#### point
String → immutable
StringBuffer → mutable (slow but safe)
StringBuilder → mutable (fast but not safe)

```
 class Output 
    {
        public static void main(String args[]) 
        {
            Integer i = new Integer(257);  
            byte x = i.byteValue();
            System.out.print(x);
        }
    }
Output : 1
Explanation: i.byteValue() method returns the value of wrapper i as a byte value. i is 257, range of byte is 256 therefore i value exceeds byte range by 1 hence 1 is returned and stored in x.
```

-  Object class is superclass of every class in Java.

```
import java.util.*;
   class Arraylists
   {
       public static void main(String args[])
       {
           ArrayList obj = new ArrayList();
           obj.add("A");
           obj.add("B");
           obj.add("C");
           obj.add(1, "D");
           System.out.println(obj);
       }
   }
Output : [A, D, B, C]
```
#### Important Thread Methods
| Method          | Purpose         |
| --------------- | --------------- |
| `start()`       | Start thread    |
| `run()`         | Code execution  |
| `sleep(ms)`     | Pause thread    |
| `join()`        | Wait for thread |
| `getName()`     | Thread name     |
| `setPriority()` | Priority        |

- ServerSocket is a java.net class which provides system independent implementation of server side socket connection.
- Servlets execute within the address space of a web server. Since it is written in java it is platform independent. The full functionality is available through libraries.

### There are 4 OOPS concepts in Java. 
- Inheritance, Encapsulation, Polymorphism and Abstraction.
- Abstraction is the concept of defining real world objects in terms of classes or interfaces.
- Encapsulation is implemented by combining methods and attribute into a class. The class acts like a container of encapsulating properties.
- Association is a general “uses-a” relationship between two independent objects. Both can have their own lifecycles with no dependency on each other.<br>
Example: A teacher and a department can be associated but exist independently.
- Composition occurs when child object gets killed if parent object gets killed. Aggregation is also known as strong Aggregation.
- Aggregation occurs when objects have their own life cycle and child object can associate with only one parent object.
##### JDK, JRE, JVM
- JDK is a core component of Java Environment and provides all the tools, executables and binaries required to compile, debug and execute a Java Program.
- JRE is the implementation of JVM, it provides platform to execute java programs.
- JVM (Java Virtual Machine) is responsible for interpreting bytecode into machine-specific code. It executes the bytecode and manages memory, security, and platform independence.
- JIT is responsible to optimize bytecode to machine code
##### class and objects
```
class main_class 
    {
        public static void main(String args[])
        {
            int x = 9;
            if (x == 9) 
            { 
                int x = 8;
                System.out.println(x);
            }
        } 
    }
Output: Compilation error
Explanation: Two variables with the same name can’t be created in a class.
But
class main_class 
    {
        static int x = 9;
        public static void main(String args[])
        {
           
            if (x == 9) 
            { 
                int x = 8;
                System.out.println(x);
            }
        } 
    }
Output : 8
```
- The finalize() method in Java is a method of the Object class used to perform cleanup activity before an object is destroyed. It can be call by garbage collector or manually.
```
 class box 
    {
        int width;
        int height;
        int length;
        int volume;
        void finalize() 
        {
            volume = width*height*length;
            System.out.println(volume);
        }
        protected void volume() 
       {
            volume = width*height*length;
            System.out.println(volume);
       } 
    }    
    class Output 
    { 
        public static void main(String args[])
        {
            box obj = new box();
            obj.width=5;
            obj.height=5;
            obj.length=6;
            obj.volume();
        } 
    }
Output : Compilation error
Explaination : The code results in a compilation error because the class box contains both a field named volume and a method named volume().
In Java, having a method and a variable with the exact same name in the same class causes a naming conflict, which is not allowed.
```
-  finalize() method is called just prior to garbage collection. it is not called when object goes out of scope.
-  The method getInstance() can be used to create an object if the class doesn’t have any constructor.
-   Protected constructor can only be called using super().<br> Protected access modifier means that constructor can be accessed by child classes of the parent class and classes in the same package.
-   A mark and sweep garbage collection consists of two phases, the mark phase and the sweep phase.
  	I mark phase all the objects reachable by java threads, native handles and other root sources are marked alive and others are garbage.
	In sweep phase, the heap is traversed to find gaps between live objects and the gaps are marked free list used for allocating memory to new objects.
- 	Overloading is a very powerful feature of java, which allows the developer to declare multiple methods or constructors with the same name but different functionality, which improves readability and flexibility of the program.
- 	Encapsulation is the process of wrapping data (variables) and methods that operate on the data into a single unit (class), and controlling access to the class members using access specifiers like private, public, and protected. This helps protect the internal state and hides implementation details.
- 	For a class to be inherited by another subclass (even in a different package), it must be declared public.<br> If a class has default (no modifier) access, it can only be inherited within the same package. Private classes cannot be inherited.
- 	The variables should be private in the class and should be accessed with get and set methods.
- 	The protected access modifier is accessible within package and outside the package but only through inheritance. <br> The protected access modifier can be used with data member, method and constructor. It cannot be applied in the class.
- 	In Java, arrays are implemented as objects. Even arrays of primitive types (like int[], char[]) are considered objects, and they inherit methods from the Object class.
- 	charAt() is a predefined method of string class which returns the character of specified index passed to it. Java does not support traditional [ ] to access the character at specified index.
- 	Strings in Java are immutable that is they can not be modified.ava defines a peer class of String, called StringBuffer, which allows string to be altered.
- 	When parameterised constructor not created, then default constructor are automatically created in class.
- 	Only main() method can be given parameters via using command line arguments.
```
Static blocks execute before main(), not static methods.
class Test {
    static {
        System.out.println("Static block");
    }

    public static void main(String[] args) {
        System.out.println("Main method");
    }
}
Output: Static block
		Main method
```
-  In Java, command-line arguments are stored in a String array passed to the main method as String[] args.<br>
Each argument entered on the command line becomes an element in this array.<br>
Therefore, the data type used to store command-line arguments is an array of string.
- All command Line arguments are passed as a string. We must convert numerical value to their internal forms manually.
- Recursions are always managed by using stack.
  
| Reason          | Loop              	| Recursion                   |
| --------------- | -----------------   | --------------------------- |
| Function calls  |  No extra calls     | Multiple function calls     |
| Stack usage     | Less                | More (call stack)           |
| Memory overhead | Low                 | High                        |
| Execution speed | Faster              | Slower                      |
| Risk            | No stack overflow   | StackOverflowError possible |

### Overidding
-  The method overriding is the process of redeclaration of a parent’s method in the child class with the same name and method signature.
-  To disallow a method from being overridden, specify final as a modifier at the start of its declaration. Methods declared as final cannot be overridden.
-   An abstract class is incomplete by itself and relies upon its subclasses to provide a complete implementation. The object of abstract classes are not created, we have to inherit it and then create the object of its subclass.
