# Principles of Programming Languages - Lab 1
## David Bostany
## 9/5/17

1. Feedback. Complete the survey linked from the moodle after completing this assignment.
Any non-empty answer will receive full credit.

2. Scala Basics: Binding and Scope. For each the following uses of names, give the line where
that name is bound. Briefly explain your reasoning (in no more than 1–2 sentences).

    (a) Consider the following Scala code.

```Scala
    1   val pi = 3.14
    2   def circumference(r: Double): Double = {
    3     val pi = 3.14159
    4     2.0 * pi * r
    5   }
    6   def area(r: Double): Double =
    7     pi * r * r
```
##### The use of pi at line 4 is bound at which line?
    - The pi at line 4 is bound by the pi at line 3 because it is declared within the same scope. The pi on line 1 is out of scope.

##### The use of pi at line 7 is bound at which line?
    - The pi at line 7 is bound at line 1 because it is used and defined outside of the scope of circumference.

```Scala
1       val x = 3
2       def f(x: Int): Int =
3           x match {
4               case 0 => 0
5               case x => {
6                   val y = x + 1
7                   ({
8                       val x = y + 1
9                       y
10                  } * f(x - 1))
11              }
12          }
13      val y = x + f(x)
```

##### The use of x at line 3 is bound at which line?
- x at line 3 is bound on line 2 where x is passed into function f as a parameter.

##### The use of x at line 6 is bound at which line?
- x at line 6 is bound on line 5 because it can only be called on within 'case x'.

##### The use of x at line 10 is bound at which line?
- x at line 10 is also bound by line 5 because they're in the same scope. The closing bracket on line 10 closes off the higher level scope just before using x. 

##### The use of x at line 13 is bound at which line?
- x at line 13 is bound on line 1 because it's the only definition of x in the global scope.

##### 3. Scala Basics: Typing. In the following, I have left off the return type of function g. The body of is well-typed if we can come up with a valid return type. Is the body of g well-typed?

```Scala
1   def g(x: Int) = {
2       val (a, b) = (1, (x, 3))
3       if (x = 0) (b, 1) else (b, a + 2)
4   }
```
- The body of g is well typed if the function returns the same type consistently. g is well typed because no matter the value of x, g returns a value of type tuple: ((int, int) int). The name 'a' is of type int and 'b' is of type (int, int).

        (b, 1): ((int, int) int) because
            b: (int, int) because
                (x, 3): (int, int) because
                    x: int
                    3: int
            1: int

        (b, a + 2): ((int, int) int) because
            b: (int, int) because
                (x, 3): (int, int) because
                    x: int
                    3: int
            a + 2: int because
                a: int
                2: int
