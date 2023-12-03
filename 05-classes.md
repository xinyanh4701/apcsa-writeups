# Process Writeup
## Name: Xin Yan Huang
## Course: APCSA
## Period: 7
## Concept: Classes (UNIT 5)

### Concept
As I am typing right now, I have completed Unit 4 of APCSA which was loops. Unit 5 of APCSA is classes. A class is a "blueprint" for creating objects, an instance or copy of the class.

### Overview
#### Void Methods
Void methods do not return any value but, these methods can print outputs. Here's the format of a void method:
```java
public static void printOne(){
    System.out.println("1");
}
```

#### Parameters
Parameters are local variables inside a method or constructor header. They contain data that is going to be sent into the method or constructor. Parameters have different data types such as `int`, `double`, `String`, etc. To include multiple parameters inside the header, use a comma after each parameters but not the last parameter.

Format of a single parameter:
```java
public static void square(double x)
{
  System.out.println(x * x);
}
```
`double x` would be the parameter.

Format of multiple parameters:
```java
public static void pow(int x, int y)
{
  System.out.println(Math.pow(x, y));
}
```
`int x` and `int y` are the parameters.

#### Arguments
Arguments are the data that is sent to a method. Arguments occur when a method is being called if the method has parameters. Here's an example of what I am talking about:
```java
public static void squareIt(double x)
{
  System.out.println(x * x);
}

public static void main(String[] args){
    double val = scan.nextDouble();
    square(val);
}
```
`val` inside the parenthesis of the sqaure method is the argument. When the argument gets passed in, the data now becomes a parameter to help the `squareIt` method.

#### Primitive Parameters
If a void method mutates the value of a primitive, the changes are not permanent because primtives are stored inside their own memory.

#### Class Parameters
On the other hand, class data types do get changed when a void method makes changes to the class.

#### Return Methods
Return methods return a value back to the calling method.

#### Constructors
Constructors are methods that create an instance or copy of a class. What is different between constructors and methods is that constructors are named after the class name. Here's an example:
```java
public class Car(){
    private String carName;
    private String model;
    private int year;
    public Car(String cn, String md, int yr){ // constructor
        carName = cn;
        model = md;
        year = yr;
    }
    public getCarName(){ // method
        return carName;
    }
}
```
Constructors can either have no parameters, one parameter, or multiple parameters.

#### Javadoc
Javadoc are another type of comments different than the single-line and multi-line comments. Javadoc comments start with `/**` and end with `*/`. For each line that is a javadoc comment, you need an asterisk, `*` before writing any comments.

Format:
```java
/**
 *  This method calculates the difference between a circle and a rectangle area.
 *  @param circ a Circle object
 *  @param rect a Rectangle object
 *  @return a double representing the difference in area between the two shapes.
 */
```

### Challenges


### Takeaways
*
*
*