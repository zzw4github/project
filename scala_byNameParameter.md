scala By-name-parameter 和 Function type的区别

博客分类： scala
By-name-parameterFunction type函数类型scala
网上找的一篇关于 By-name-parameter 和 Function区别，虽然是2009年的文章了，但解释的非常好。 原来By-name-parameter和函数类型是不一样的概念，以前还以为By-name-paramete 就是函数类型的一个用法呢
 
By-name-parameter to Function

Today's topic is related to Defining Custom Control Structures. By name parameters are not function objects in the same way as other functions. Normally you need to invoke a function:
scala> def exec(func: () => Int) = func()
exec: (() => Int)Int
// exec invokes the function so 10 is the result
scala> exec (() => 10)  
res1: Int = 10
scala> def exec(func: () => Int) = func
exec: (() => Int)() => Int
// here exec returns the function:
scala> exec (() => 10)                 
res2: () => Int = <function>

Compare that to a by-name-parameter function:
scala> def exec(func: => Int) = func   
exec: (=> Int)Int
// by-name-parameters are executed when they are referenced
// so the result is 10
scala> exec {10}                    
res3: Int = 10
// This is not legal because by-name-parameters
// are not normal functions
scala> def exec(func: => Int) = func()
<console>:4: error: func of type Int does not take parameters
       def exec(func: => Int) = func()

So the issue is how can you pass a by-name-parameter to a method that takes a function as a parameter without having to do: 
scala> def takesFunc(func: () => Int) = println(func())
takesFunc: (() => Int)Unit
scala> def send(x: => Int) = takesFunc(() => x) 
send: (=> Int)Unit
scala> send{2}
2

the alternative syntax is:
scala> def send(x: => Int) = takesFunc (x _)   
send: (=> Int)Unit
scala> send {2}
2
 
参考:http://daily-scala.blogspot.sg/2009/12/by-name-parameter-to-function.html
