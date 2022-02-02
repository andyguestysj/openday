---
title: Unit Testing In replit.com
permalink: /docs/unittesting-replit/
---

Video of this lecture.  

Unit testing in replit.com is the same as any other environment, it is just set up a little differently.  

## Setting Up A Repl For Unit Testing

1. Create your repl (project) as usual.
2. Click on the **Packages** icon at the left had of the screen. It looks like a little cube. 
![Package Icon](https://ysjged.netlify.app/assets/img/package.png)
3. In 'search for a pack' type **org.hamcrest**
4. Click on **org.hamcrest:hamcrest    2.2**
5. Click on the **+** symbol to install the package.
6. Wait for the package to install.
7. Set up your test file. Create a new file and call it something like `UnitTest.java`
Set up `UnitTest.java` as follows

```java
import org.junit.*;
import org.junit.runner.*;
import static org.junit.Assert.*;

public class UnitTest {

  // Insert a unit tests as normal here

  @Test
  public void testBasic() {

    

  }
}
```
8. Go to your `Main.java` file
Change it to 
```java
class Main {
  public static void main(String[] args) {
    System.out.println("Testing");
    org.junit.runner.JUnitCore.main("UnitTest");
  }
}
```
9. Your unit tests go in `UnitTest.java` as normal. You'll need to create objects and put your assertions in there.


Alternatively, before you start coding you can simply fork a copy of [https://replit.com/@andyguest/javaUnitTestTemplate](https://replit.com/@andyguest/javaUnitTestTemplate) which is already set up.