# COMP26020

## Part 2  Functional Programming  Haskell

### 1.1 Treat Functions like any other data 

- define  without naming
- functions as inputs/outputs of other functions 

### 1.2 Reason about them like mathematic functions 

-  if f(x)=g(x) for all x then f = g
- let x = f(10) in x+x+x = f(10)+f(10)+f(10)

### 1.3 Basic definition in Haskell

```haskell
b = False || (False && True)
n = 1+7
b2 = n/=8
main = print(b2)
```

​      **" /= " 代表不等于** 

​      

```haskell
b = False || (False && True)
n = 1
 +7
b2 = n/=8
b3 = (0,0) == (0,0)
v = 7* (if b then 5 else 6)
main = print(v)
```

  这里的 if 和 else 只是  definition 对于 cases ， 然后这个 cases 是 true 或者 false ， 因此 Haskell 是  functional language 

```haskell
b = False || (False && True)
n = 1
 +7
b2 = n/=8
b3 = (0,0) == (0,0)
v = 7* (if b then 5 else 6)

add7 n = n+ 7 
main = print(add7 8)
```

 define function add 7 ，add7 是  function name ， n 是他的 argument

```haskell
small 0 = True 
small 1 = True 
small n = False 
main = print(small 8)
```

 define  function  small    

这里的 order 很重要 ，放在前面的会先execute 

```haskell
small 0 = True 
small n = False 
small 1 = True 

main = print(small 8)
```

这里 small n 在 前面 所以执行的结果为  False 

```haskell
addUp (0,n) = n
addUp (m,0) = m
addUp (m,n) = m+n
main = print(addUp(5,6))
```

   pair 作为 argument  

​      

```haskell
first(e,_) = e 
main = print(first(5,6))
```

  

```haskell
fib 0=0
fib 1= 1
fib n = fib(n-2) + fib(n-1)
main = print(fib 6)
```

​        在 Haskell 中 使用 recursion 

### 1.4 Higher order Function

  使用 function 去 output 另一个 function

```haskell
addConst n m = n + m 
addThree = addConst 3
main = print(addThree 7)
```

这里用 addConst 输入一个数字 n 然后 return 了一个 function,也可以 看作addConst 有两个输入 m ，n



```haskell
addConstB n = \m -> n + m 
main = print(addConstB 3 8)
```

​          

```haskell
addConstC = \n ->(\m ->n +m)
main = print(addConstC 3 9)
```

​     



```haskell
addConstC = \n ->(\m ->n +m)
thriceFromZero f = f(f(f(0)))
main = print(thriceFromZero(addConst 3))
```

​       

```
thriceFromZero f = f(f(f(0)))
main = print(thriceFromZero(\n -> 2*n +1))
```

​      这里 0 作为 input 将 \n -> 2*n +1 执行了3 次

​       

```haskell
h n = (\m -> n)
main = print(h 1 2)
```

```haskell
h n = (\n -> n)
main = print(h 1 2)
```

这里上面的 m ，n会输出 1 ， 而下面的代码会输出 2  ， 

最后输入的这个n才会matter ，这个现象被称作 shadowing

```haskell
h n = (\n -> n)

repFromZero 0 f  = 0 
repFromZero n f = f(repFromZero (n-1) f)
main=print(repFromZero 3 (\x -> x+1))
```

###         1.5 Useful forms of definition 

```haskell
small 0 = True  
small 1 = True 
small n = False 

smallB n = case n + 1 of 
 0 -> True 
 1 -> True 
 n ->False 
  
main =  print(smallB 1)
```

```haskell
sideOfFive n 
 |  d > 0 = 1 
 |  d < 0 = -1 
 |  otherwise = 0 
 where d = n -5 
  
main =  print(sideOfFive 5)
```

```haskell
y = let x = 10 + 10 in x+ x
  
main =  print(y)
```

​        let 有 shadowing 的 作用  let 让我们能够 创建 loacl  definition

```haskell
z = let x = 10 in 
 let x = 20 in x
main = print (z)
```

​       

```haskell
w = let x = 5 in 
 let f = \n -> x in
 let x = 6 in 
 f 0
main = print (w)
```

```haskell
w = let x = 5 in 
 let f = \n -> x in
 let x = 6 in 
 x
main = print (w)
```

​       将 f 0 换成 x 的话 output 就变成了 6 因为 x 最近一次的定义 为6 

而 f 0 最近的一次 define 是 5

### 1.6 Stuff that goes wrong  

```haskell
oops True = True 
main = print (oops False)
```

​         上述代码会报错 我们忘记去define opps 在 oops False , oops 是由 pattern matching 定义的 ，oops 作为 input   与 pattern  False  不匹配所以会报错

```haskell
epp 0 = 0 
epp n = 1 + epp n 
main = print (epp 1)
```

​      上述代码会 stackoverflow ， 因为会一直递归增加

```haskell
yikes = let x = x in x 

main = print (yikes False )
```

​      (Bottom represents a "hole" in a haskell program, an infinite loop or `undefined` are examples of bottom)

### 1.7 Type and Type Inferrence 

​       Int 数据类型

```haskell
f :: Int -> Int 
f x = x + 1
main = print(f 10)
```

​        `::` + `Type` 代表数据类型

```haskell
f :: Int -> Int 
f x = x + 1
main = print(f (10:: Double))
```

​         代码会报错， 因为  `Double`  与 `Int` 不匹配

​          haskell 的 数据类型必须是相匹配的

​       Boolean 数据类型 

```haskell
big :: Int -> Bool 
big x = x > 10
main = print(big 10 )
```

​       

```haskell
j x = True
main = print (j 10)
```

​         这里看似打破了之前所说的haskell的 strong typed ，实际上这里如果我们不provide type ， haskell的编译器 会推断这里所应该用的type

```haskell
j :: Bool -> Bool
j x = True
main = print (j 10)
```

​         这里我们将 `j`  的 input 定义为了 `Bool`，所有当我们输入 `10` 的时候会报错

```haskell
j x = True
main = print (j 10 && j False )
```

​        haskell 会 infer 一个 general 的 type 

### 1.8 Type Constructor 

```haskell
sumPair :: (Int,Int) -> Int
sumPair (x,y) = x + y
atTen :: (Int -> Bool) -> Bool 
atTen f = f(10)
main = print (atTen(\x -> True))
```

​          `函数名` + `::` + `(输入数据类型)` `-> 输出数据类型`

```haskell
myApp :: (Int -> Bool) -> Int -> Bool
myApp f x = f x
main = print(myApp(\x -> True) 10)

```

​          这里函数 myapp 的 input 是  一个 `concrete type`     `Int -> Bool` 输出也是 `f x`  所以只能也是 `Int -> Bool`

### 1.9 Algebraic Datatypes 

```haskell
data SwitchState = On | Off

isOn On = True
isOn Off = False 

toggle On = Off
toggle Off = On 

main = print(isOn(toggle On))
```

​        这里我们不能直接用 `main=print(toggle On)` ,因为 `On` 和 `Off` 都是我们自己定义的数据类型

```haskell
data MyIntPair = IntPair Int Int
mySumPair (IntPair x y) = x + y
main = print (mySumPair(IntPair 10 11)
```

```haskell
data MyIntPair = IntPair Int Int
myFirst (IntPair x _) = x 
main = print (myFirst(IntPair 10 11) 
```

```haskell
data BoolOrInt = Abool  Bool | Anint Int
intval :: BoolOrInt -> Int
intval(Abool True) = 1
intval(Abool False) = 0 
intval(Anint x) = x 
main = print (intval(Abool False))
```

​         errorhandling 里可以用到 algebraic datatype 

​         例如 

​                

```haskell
data Maybeint = Noint | Isint Int
```

​       当我们不确定数据类型的时候可以用

​       

```haskell
data Mypair a b = Pair a b 
myFirst (Pair a b) = a 
main = print (myFirst(Pair "yes" "no"))
```

​      Maybe type Constructor   

​      `Maybe a = Nothing | Just a`

​       

```haskell
data MyList a = Empty | Append a (MyList a)

myHead :: MyList Int -> Maybe Int
myHead Empty = Nothing
myHead (Append x xs ) = Just x 

main = print(myHead(Append 11 (Append 10 Empty)))
```

###        1.10 List sytnax

​          

```HASKELL
myIntHead :: [Int] -> Maybe Int
myIntHead [] = Nothing 
myIntHead  (x:xs) = Just x 

main = print(myIntHead(1:2:3:[]))
```

​       

```haskell
myHead :: [a] -> Maybe a
myHead [] = Nothing 
myHead  (x:xs) = Just x 

main = print(myHead("Hi"::String))
```

​      

```haskell
main = print([1..5])
```

​          [1,2,3,4,5]

```haskell
main = print([1,3..10])
```

​        [1,3,5,7,9]

```haskell
   l = [(w,n)| w<- "Hi", n <- [1..3]]
   main = print(l)
```

​           [('H',1),('H',2),('H',3),('i',1),('i',2),('i',3)]

​    

```haskell
l = [(w,n)| w<- "Hi", n <- [1..3],w /= 'i']
main = print(l)
```

​         [('H',1),('H',2),('H',3)]