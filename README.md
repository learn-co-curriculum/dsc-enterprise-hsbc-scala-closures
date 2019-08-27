
# Closures

## Closures close around the environment

In the below example:
* The `outer` value is inside of function `f` which closes around the environment and swallows the `outer`
* `x` is not a closure, it is the input to the function `f`


```scala
val outer = 99
val f = (x:Int) => outer + x
```


    Intitializing Scala interpreter ...



    Spark Web UI available at http://32c6e00c8fb3:4044
    SparkContext available as 'sc' (version = 2.4.3, master = local[*], app id = local-1562182232641)
    SparkSession available as 'spark'
    





    outer: Int = 99
    f: Int => Int = <function1>
    



When used, you can then call `f` in the above example and `outer` will "come along for the ride" since it is an enclosed value.


```scala
f(4) //103
```




    res0: Int = 103
    



## **Lab:** Closure by example

Given the following it seems that `MyFunctions.lessThan` is reusable

This returns a function that will receive a number and ask if it less than the previously defined value

**Step 1:** Implement what `MyFunctions.lessThan` look like?


```scala
val isFreezingCelcius = MyFunctions.lessThan(0)
val isFreezingFahrenheit = MyFunctions.lessThan(32)
isFreezingFahrenheit.apply(25) // true
isFreezingCelcius.apply(25) // false
```
