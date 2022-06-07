# Scope Lab

## Learning Goals

- Fix scope issues

## Instruction

Modify the sample code in the previous section such that we can display the
integer value we have assigned based on the value of the `flag` variable.

```java
public class StudentGame {
    public static void main(String[] args) {
        boolean flag = false;
        if (flag) {
            // do something when flag is true
            int numberWhenFlagIsTrue = 12;
        } else {
            // do something else when flag is false
            int numberWhenFlagIsFalse = 5;
        }
        System.out.println(numberWhenFlagIsTrue); // <- this will not work because numberWhenFlagIsTrue is not in scope
    }
}
```

## Walkthrough

In order to make this work, we have to make two changes:

1. Separate the declaration and the assignment of the integer variable we use to
   track the number value we assign
2. Use a single variable for both the `true` case and the `false` case

```java
public class StudentGame {
    public static void main(String[] args) {
        boolean flag = false;
        int number;
        if (flag) {
            // do something when flag is true
            number = 12;
        } else {
            // do something else when flag is false
            number = 5;
        }
        System.out.println(number);
    }
}
```

Now that my `number` variable is declared inside the method scope, I can access
it from both the scope of the `if` statement and the scope of the `else`
statement, and I can display its value in the terminal when I'm done with the
conditional logic.
