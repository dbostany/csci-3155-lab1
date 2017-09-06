# Principles of Programming Languages - Lab 1
## David Bostany
## 9/5/17

1. Feedback. Complete the survey linked from the moodle after completing this assignment.
Any non-empty answer will receive full credit.

2. Scala Basics: Binding and Scope. For each the following uses of names, give the line where
that name is bound. Briefly explain your reasoning (in no more than 1–2 sentences).

⋅⋅⋅ (a) Consider the following Scala code.

```Scala
    1   val pi = 3.14
    2   def circumference(r: Double): Double = {
    3     val pi = 3.14159
    4     2.0 * pi * r
    5   }
    6   def area(r: Double): Double =
    7     pi * r * r
```

