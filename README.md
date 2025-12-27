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

#### Use of "this"
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

#### There are 4 OOPS concepts in Java. 
- Inheritance, Encapsulation, Polymorphism and Abstraction.
