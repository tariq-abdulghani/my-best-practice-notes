# my-best-practice-notes
## Java

1. dont create static method 'of' instead name it with the name of the class
it gives more readability and enables static imports with less
collision in method names alot of methods named 'of' ??? why 

2. dont make constructors public create static method with class name
and import it statically and used it to create objects eliminate the need
for the ugly new operator


```java
public class Point {

    public int x;
    public int y;

    private Point(int x, int y) {
        this.x = x;
        this.y = y;
    }

    public static Point point(int x, int y){
        return new Point(x, y);
    }

    public static Point origin(){
        return new Point(0, 0);
    }


    @Override
    public String toString() {
        return "(" + x +
                "," + y +
                ')';
    }
}

```
and used as , no new operator and also its more clean
```java
public class Main {


    public static void main(String[] args) {
        Point p1 = point(10,0);
        Point zero = origin();

        System.out.println(p1);
        System.out.println(zero);
    }

}
```
