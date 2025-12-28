# Core-JAVA
Code and Notes of java

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

- In Java, all arithmetic operations (+ - * /) promote operands smaller than int (byte, short, char) to int.
- The extension of a compiled Java class is .class.
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
