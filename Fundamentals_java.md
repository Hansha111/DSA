# 🧪Methods & Functions

Difference between method and function :
1. method
		--> inside class 
		-->can be called using object of class only

2. function --> outside class

# 🧠Method

writing a function inside a class is a method.

***Method statements***
1. declaration
2. definition
3. calling

declaration & definition should be outside main class.
calling should be inside main class and main method.

```
//outside Main class
function_type functionName (parameters or placeholders) {  //declaration
	//definition
	
}

inside Main class & main method
functionName (arguments); //calling
```

### 🔍 Who’s Who Here?

|Code Part|It's a...|Why?|
|---|---|---|
|`String name, int age` in method|**Parameter**|Declared in the method definition – the "placeholder"|
|`"Gippy", 5` in method call|**Argument**|Actual values passed in when calling the method|

----------------------------------------------------------------------------------------------------------

**Function Types
------------------
except void , for remaining types we have to return the data.
for void , print the data.

except void , remaining all are datatypes , those having some default value, that's why we've to return and void is not a datatype , and no return values.


# i/p & o/p

in java , everything should be written in class only . 
it will take the data in strings and stores in array.

static acts as an object for the main method.
for static methods , no need to create an object.

for non-static methods , we must create an object to call them.


### 🔍 Common Related Stuff:

|Concept|What it means|
|---|---|
|`static` variable|Shared by **all objects** of a class (like a class-level counter)|
|`static` block|Executes **once** when class loads|
|`this` keyword|Refers to **current object** (can’t use it in static methods!)|
|Object creation|`ClassName obj = new ClassName();`|
|Accessing non-static from static|❌ Not allowed directly — needs object|
|Accessing static from anywhere|✅ Allowed (if in same class)|


### 🔐 Access Modifiers in Java (The VIP List):

|Modifier|Access Level 👀|
|---|---|
|`public`|Accessible from **anywhere**|
|`private`|Accessible **only within the same class**|
|`protected`|Accessible in **same package + subclasses**|
|_default_ (no keyword)|Accessible in **same package only**|



### 🎭 Where Can You Use `public`?

|You can write `public` in front of...|Why?|
|---|---|
|Classes|To make them accessible from any package|
|Methods|So they can be called from other classes|
|Variables|So they can be accessed directly (though usually not recommended)|
|Constructors|So you can create objects from other classes|



Scanner is a class from util package.
before scanner class , we had string buffer that only took strings as an input thus we needed to convert to the targeted datatypes . we can't convert for multiple inputs . that's why scanner class comes in .

In Scanner class , we've multiple pre-defined methods. just creating an obj for scanner class , we can access those pre-defined methods.

create a class using class keyword , name of the class - Starting letter of the class should be capital (optional).

for all the methods , name of the method should start from small letter.


# Constructor

Constructors are used to initialize the objects.
For every class there will be a default constructor.
Whenever we create an object , constructor will be called ,then object will be created.
Constructor having class name and method properties.
Constructor is called whenever we make an object of that class.


### 🧠 Bonus: Constructor vs Method

|Feature|Constructor|Method|
|---|---|---|
|Name|Same as class|Any name|
|Return type|None|Must have (even void)|
|Called by|`new` keyword|Called manually|
|Purpose|Initializes object|Defines behavior|


### 🎯 What is a Static Block?

A `static` block is a **code block** that runs **once** when the class is **loaded into memory** — **before** any object is created and **before** `main()` is called.

Static block will be created with the static keyword. 
it will be called automatically, no need to call with either object or class.


Static block will be prioritized over Constructor .

```
class Demo{
    static {
        System.out.println("Static block");
    }
    Demo(){
        System.out.println("Constructor");
    }
}

public class Day2 {
    public static void main(String[] args){
    //created two objects , hence two times constructor will be called
        Demo d1 = new Demo();
        Demo d2 = new Demo();
    }
}

//OUTPUT:

Static block
Constructor
Constructor

```

# Static Method

For static method ,no need to call with object , we can directly call with class name.
here , static will act as instance or object.

### ✨ Static Method vs Non-static Method

| Feature              | Static Method              | Non-static Method          |
| -------------------- | -------------------------- | -------------------------- |
| Belongs to           | Class                      | Object                     |
| Call with            | `ClassName.method()`       | `new Object().method()`    |
| Access instance vars | ❌ Can't use `this`         | ✅ Can use `this`           |
| Memory efficiency    | ✅ One copy for all objects | ❌ Separate copy per object |



## 🌱 1. **Local Variable**

- **Lives inside methods**, constructors, or blocks.
    
- Exists **only while the method is running**.
    
- **No default value** – must be **initialized**!


## 🧍 2. **Instance Variable**

- Declared **inside a class** but **outside methods**.
    
- Every **object gets its own copy**.
    
- Stored in **heap memory**.


## 🏛️ 3. **Static Variable** (a.k.a class-level variable – maybe _standard_)

- Declared with `static`.
    
- Belongs to the **class**, not the object.
    
- **Shared** among all objects.
    
- Initialized **only once** when class loads.



## 🪞 4. **`this` Keyword**

- Refers to the **current object**.
    
- Helps **distinguish** between instance and local variables if they have the **same name**.



## 🎯 Summary Table:

| Type              | Where it's declared                    | Scope                     | Default Value | Accessed via         |
| ----------------- | -------------------------------------- | ------------------------- | ------------- | -------------------- |
| Local Variable    | Inside methods                         | Only within method/block  | ❌ No default  | Direct in method     |
| Instance Variable | Inside class                           | Per object (non-static)   | ✅ Yes         | `this.variable`      |
| Static Variable   | Inside class w/ `static`               | Shared across all objects | ✅ Yes         | `ClassName.variable` |
| `this`            | Inside non-static methods/constructors | Refers to current object  | N/A           | `this.variable`      |



```
class Student{
    int age;
    String name;
    boolean passedout;
    float marks;
    long ERP;

    void setAge(int age1){
        this.age = age1;  // this.age is instance var, age1 is local
    }

    void setName(String name1){
        this.name = name1;   // this.name is instance var, name1 is local
    }

    void setPassedout(boolean passedout1){
        this.passedout = passedout1;    // this.passedout is instance var, passedout1 is local
    }

    void setmarks(float marks1){
        this.marks = marks1;    // this.marks is instance var, marks1 is local
    }

    void setERP(long ERP1){
        this.ERP=ERP1;  // this.ERP is instance var, ERP1 is local
    }

  
  

    int getAge(){
        return age;
    }

    String getName(){
        return name;
    }

  
    boolean getPassedout(){
        return passedout;
    }

    float getMarks(){
        return marks;
    }

    long getERP(){
        return ERP;
    }

}

  

class Day2{

    public static void main(String[] args) {
        Student obj1 = new Student();
        
        obj1.setAge(21);
        System.out.println(obj1.getAge());

	obj1.setName("Maya");
        System.out.println(obj1.getName());


        obj1.setMarks(9.2f);
        System.out.println(obj1.getMarks());

  
        obj1.setPassedout(false);
        System.out.println(obj1.getPassedout());
    }

	obj1.setERP(2203031050220L);
        System.out.println(obj1.getERP());

}


//OUTPUT:
21
Maya
9.2
2203031050220

```


# Recursion

***example:***

```
import java.util.Scanner;

public class Day1 {

    int fact(int a){
        if (a==0 || a==1){
            return 1;
        }

        int f = a * fact (a-1);
        return f;
    }

  

    int fib(int n){
    
        if (n==0 || n==1) return n;

        int f= fib(n-1) + fib(n-2);
        return f;

    }


    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        Day1 d = new Day1(); // Create object to call non-static method
        int result = d.fact(n);

        System.out.println("Factorial : "+result);
        System.out.println(Fibonacci:"+ d.fib(n));

    }
}


//OUTPUT:
4
Factorial : 24
Fibonacci:3
```





# 💡Conditional Statements

Types:
if-else , else-if ladder , switch case

conditional statements are used to check the condition and to print that relevant block , in constant time. 

Pseudo code:
```
if (condition) {
    // block if condition is true
} else if (anotherCondition) {
    // block if the first is false but this is true
} else {
    // block if nothing above was true
}

```


Switch case example:

```
switch (expression) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // default code
}

```



# 💡Control Statements

***Two Types:***
1. Entry control loop  --> for , while 
2. Exit control loop  --> do-while


1.**Entry Control Loops
---------------------------
example:

```

//For Loop
for(initialization ; condition ; updation){
	//code
}


//While Loop
initializing
while(condition){
	//code

	updation
}
```




when we know the range , we'll use for loop .
when we don't know the range , prefer to use while loop.

```
int[] arr = {1,2,3,4,5};
for(int i = 0 ; i<n ; i++){
	return arr[i];
}
```










2.**Exit Control Loops
--------------------------

🧪 Sample: Do-While Loop in Java
```
public class DoWhileExample {
    public static void main(String[] args) {
        int counter = 1;

        do {
            System.out.println("Count is: " + counter);
            counter++;
        } while (counter <= 5);
    }
}

```


