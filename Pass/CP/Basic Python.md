---
date: 2025-06-30
aliases:
  - review python sheets
---
# Basic Languages
## Numbers
- integers(**int()**)
	- 十进制
		- int(7.5) =7
	- 二进制: 0Bn / 0bn
	- 八进制: 0On / 0on
	- 十六进制: 0Xn/0xn
- floating-point numbers (**float()**)
	- +-m.n
		- 3.0+4 =7.0
	- +-m.nE+-k
- complex numbers (**complex()**)
	- m+nj
		- complex(10.0,20.2) =10+20.2j
		- complex(3) =3+0j
> [!example]
> 	c=12.3+45.6j
> 	c ----#(12.3+45.6j)
> 	c.real ----#12.3
> 	c.imag ----#45.6
- boolean types (**bool()** =True/False)
	- 数值: 非0=True, 0=False; 数值计算时, True=1,False=0
		- x=3+True ---- x=4
	- 字符串: 非空=True, 空=False.
		- bool(23.4) =True
- String (**str()**)
	- str(23.4) ='23.4'
	- eval(str) 将字符串当成有效表达式并计算
		- eval('3+4') =7
> [!example]
> 	from math import *  # 调用时可省略模块名, 如无需math.pi
> 	x=eval(input("输入表达式: “))
> 	print("计算结果=“, x)


## Calculation

| 符号  | definition |       example       |
| :-: | :--------: | :-----------------: |
| **  |    幂次方     |   27**(1/3) =3.0    |
| //  |     整除     |      10//3 =3       |
|  %  |    取余数     |       10%3 =1       |
| +=  |    复合赋值    | a+=b/3 = a=a+(b/3)  |
| !=  |    不等于     | x!=20 ---True/False |
|     |    链式赋值    |     x=y=z=10.3      |
|     |   序列解包赋值   |     x,y,z=1,2,3     |

| 函数           | definition        | example             |
| ------------ | ----------------- | ------------------- |
| abs()        | 取绝对值              | abs(-3.5) =3.5      |
| divmod()     | 得到一元组结果(x//y,x%y) | divmod(10,3) =(3,1) |
| pow()        | x的y次幂             | pow(3,4) =81        |
| round(x[,n]) | 对x四舍五入保留n位小数      | round(10.4456) =10  |
| max/min()    | 取最大值/最小值          | max(1,2,3,4,5) =5   |
| exp()        | e^x               | exp(3) =20.085536…  |
| gcd(m,n)     | 取最大公约数            | gcd(12,8) =4        |
| log()        | 自然对数(以e为底)        | log(10)=2.302585…   |
| sqrt()       | 平方根               | sqrt(9) =3.0        |

### from random import *

| **random**    | definition          | example                            |
| ------------- | ------------------- | ---------------------------------- |
| random()      | 随机产生[0,1)区间内的一个浮点数  | random() =0.736485…                |
| randint(a,b)  | 随机产生[a,b]区间内的一个整数   | randint(67,90) =78                 |
| uniform(a,b)  | 随机产生[a,b]区间内的一个浮点数  | uniform(1,9)=5.78465…              |
| sample(seq,k) | 从序列seq中随机抽取k个元素组成列表 | sample(range(1,10),5) =[3,2,1,9,5] |
| choice(seq)   | 从非空序列seq中随机选取一个元素   | choice([34,67,89] =67)             |


## String
### Escape character

| character | definition | character | definition |
| :-------: | :--------: | :-------: | :--------: |
|    \\\    |     \      |    \n     |     换行     |
|    \\'    |     '      |    \r     |     回车     |
|    \\"    |     "      |    \t     |   横向制表符    |
\# 字符串前加“r"表示内容不转义:
	print(abc\t|123\r|) =abc     |123     |
	print(r"abc\t|123\r|") =abc\t|123\r|

### Operators&Functions
s1='abc', s2='defg'

| character              | definition                               | example                                                                            |
| :--------------------- | :--------------------------------------- | :--------------------------------------------------------------------------------- |
| +                      | 连接                                       | s1+s2 ='abcdefg'                                                                   |
| \*n / n*               | 复制n次                                     | s1\*3 ='abcabcabc'                                                                 |
| in                     | 子串测试                                     | s1 in s2 =False                                                                    |
| s\[i]                  | 索引<br>(正向从0开始,反向从-1开始)                   | s1\[2] ='c'<br>s2\[-4]= 'd'                                                        |
| s\[m:n:k]              | 切片, \[m,n), k为步长                         | s2\[:4:2] ='df'<br>s1\[:-2] ='a'                                                   |
| len(s)                 | 返回字符串长度                                  | len(s1) =3                                                                         |
| chr(n)                 | 返回字符编码n对应的单字符                            | chr(65) ='A"                                                                       |
| ord(s)                 | 返回单字符s对应的编码                              | ord('A') =65                                                                       |
| find(s)                | 字符串中第一个出现s子串的位置<br>找不到返回-1               | s1.find('bb') =-1                                                                  |
| index(s)               | 同上,找不到抛出异常                               | s1.index('bc') =1                                                                  |
| lower(s)               | 全部转换成小写字母                                | lower('ABC') ='abc'                                                                |
| upper(s)               | 全部转换成大写字母                                | upper(s1) ='ABC'                                                                   |
| isnumeric()            | 全部是数字返回True                              | s1.isnumeric() =False                                                              |
| isalpha()              | 全部是字母返回True                              | s1.isalpha() =True                                                                 |
| replace(old,new)       | 将字符串中old子串改为new子串                        | s1.replace('c','d') ='abd'                                                         |
| startwith(s,start,end) | 字符串在\[start,end)范围内<br>是否以字符串s开头         | s1.startwith('ab',0,2) =True                                                       |
| split(\[s])            | 将字符串按照s分隔符分离,返回结果是列表<br>缺省s按空格/制表符/换行符分隔 | s2=‘a   1 23'<br>s2.split() =\['a','1','23']<br>s2.split(" ") =\['a',' ','1','23'] |
| strip(s)               | 去掉字符串两旁的s子串<br>(一般用于去掉空格)                | ’ 123 ‘.strip() ='123'                                                             |
\# 字符串注意事项:
- 浮点数比较精度问题
	-因浮点数十进制与二进制互转因素,浮点数相等比较时结果会不正确,因采用差值小于给定精度来判断.

> [!example]
> 	3.5-2.7=0.8  ---- False
> 	3.5-2.7  ---- 0.7999999999998
> 	abs((3.5-2.7)-0.8)<0.00000001  ---- True

- 字符串比较大小问题
	-按字符的ASCII码的值从左到右逐一进行比较.
	\[例] 'ABCDE' > 'ABR'  ---- False; 'BC' < 'bc' ---- True


## Combined datas
组合数据类型通过类型转换函数进行互相转换 --- list() | tuple() | dic() | set()

### List \[]
mutable *-支持动态增删元素*
store a collection of elements ==(can contain different types)==

Loop through the list
- for item in *L*: 
	 -*can't change the value
- for i in range(len(L)): 
	 -**L\[i]** can change the value inside the list
- **enumerate(*L*)**
	 -get index and item at the same time
> [!example]
> 	fruits = ['apple', 'banana', 'cherry']
> 	for index, fruit in enumerate(fruits):
> 	print(index, fruit)
> 	----0 apple / 1 banana / 2 cherry


Delete the list
- del *L*


List slicing
- **L\[start:end:step]**
	 -get the copy of the sliced list (start inclusive, end exclusive)
- slice assignment
	 -replace, insert, or delete multiple elements
> [!example]
>	L=[1,2,3,4,5]     L[1:1]=[6,7]
>	print(L)   ----[1,6,7,2,3,4,5]


Calculation in list
- + /  \*   *\#首地址变更
- += / \*=   *、#首地址不变,对其他相关参数不影响*
- in     -*exist ---True


==List Methods==

| methods                           | definition                                                  | example                                                        |
| --------------------------------- | ----------------------------------------------------------- | -------------------------------------------------------------- |
| *L*.append(newitem)               | add new item to the list                                    | fib.append(fib\[-1]+fib\[-2])                                  |
| *L*.reverse()                     | reverse the list                                            |                                                                |
| *L*.sort(key=None, reverse=False) | Sorts the list in-place                                     | False-升序, True-降序<br>no reverse = False<br>key-sort by keyword |
| *L*.count(item)                   | Returns the number of times 'item' appears in the list      | L=\[1,2,3,1,4,5]<br>L.count(1)  ---2                           |
| *L*.index(item)                   | Returns the index of the first occurrence of 'item'         | L=\[1,2,3,1,4,5]  <br>L.index(3) ---2                          |
| *L*.pop(index=-1)                 | Removes and returns the item at index i (default is last)   | L=\[1,2,3,1,4,5]<br>L.pop() ---\[1,2,3,1,4]                    |
| *L*.extend(*iterable*)            | Adds all items from another iterable (like a list or tuple) |                                                                |
| *L*.insert(i,item)                | Inserts an item at position i                               |                                                                |
| *L*.clear()                       | Removes all items from the list                             |                                                                |
| *L*.remove(item)                  | Removes the first occurrence of 'item'                      |                                                                |
| len(*L*)                          | return the number of items in the list                      |                                                                |
| sum(*L*)                          | return the sum of the value of items                        |                                                                |
| max(*L*)/min(*L*)                 | return the maximum/minimum in the list                      |                                                                |
| map(function,*L*)                 | apply the function on every item in the list                | z=map(float,L)                                                 |
| zip(*L1,L2,L3*)                   | Combines multiple iterables **element-wise** into tuples    | *\#only be looped once*                                        |


### Tuple ()
- immutable *-创建后不能修改*
	 E.p. L\[0] += \[-55] ❌
- ordered *-elements have a defined order*
- can contain **mixed data types** *-numbers, strings, lists, etc.*
- single-element tuple must have a **comma**!
	 E.p.  t=(5, )
- faster with fixed structure, fixed data uses less memory


### Dictionary \{key:value}
- mutable
- unordered
- keys must be unique and immutable (e.g., string, number, tuple)
- {}--empty dictionary, empty set must use: set()
- dict() & zip()
>[!example]
>	data=\[\['China','Beijing'],\['German','Berlin],\['Dutch','Amsterdam']]
>	Dcountry=dict(data)
>	countries=\['China','German','Dutch']
>	cities=\['Beijing','Berlin','Amsterdam']
>	Dcountry=dict(zip(countries, cities))

==Dictionary Methods==

| methods                   | definition                                                        |
| ------------------------- | ----------------------------------------------------------------- |
| len(*D*)                  | return the number of key-value pairs                              |
| *D*.keys()                | return all keys                                                   |
| *D*.values()              | return all values                                                 |
| *D*.items()               | return all key-value pairs as tuples                              |
| *D*.get(key,default=None) | return value or None if missing                                   |
| *D*.pop(key\[,default])   | remove a key-value pair by key and return the corresponding value |
| *D*\[k]                   | return the value of k                                             |
| *D*\[k]=v                 | relate v on k                                                     |
| del *D*\[k]               | delete k                                                          |
| k in *D*                  | if k is a key in D, return True                                   |


### Set {}
- mutable  *except 'frozenset'*
- unordered
- unique items, no duplicates
	 -e.g. {1,1,2} ---{1,2}
- unindexed

==Set Methods==

| methods                               | definition                                                |
| ------------------------------------- | --------------------------------------------------------- |
| A - B /<br>*A*.difference(*B*)        | elements in A but not in B                                |
| A & B /<br>*A*.intersection(*B*)      | common elements in both sets                              |
| \|  / *A*.union(*B*)                  | combine all unique elements from both sets                |
| ^ / <br>*A*.symmetric_difference(*B*) | elements in A or B but not both                           |
| *S*.add(x)                            | add x in set *S*                                          |
| *S*.update(x)                         | add multiple items, x must be sequence types              |
| *S*.remove(x)                         | remove element x<br>*\#raises KeyError if x is not found* |
| *S*.discard(x)                        | remove element x<br>*\#does nothing if x is not found*    |
| *S*.clear()                           | delete the whole set                                      |
| *A*.issubset(*B*)                     | if A is a subset of B, return True                        |


## Input&Output
- input()
	-默认输入字符串, 可以用int()、float()、eval()等函数转换

- print(\[output]**\[,sep=分隔符]\[,end=结束符]**)
	-输出项由逗号分隔, sep缺省为空格, end缺省为换行

> [!example] 
> 	for i in range(1,3)
> 		print (i, i\*i)
> 	--- 1 1
> 	    2 4

- **format()**
	-格式字符串.format(字符项列表)
	-格式占位符: {\[序号:\[m.n]operators]}
		m: 输出最小宽度; n: 小数位数; operators: d|c|s|f|e
		\# format()方式默认数值类型右对齐左补空, 字符串类型左对齐右补空
> [!example]
>	1. print("My name is {} and I am {} years old.".format(name, age))
>	2. s=python n=1234
>	print("s={0:8s}n={1:6d}".format(s,n)) 
>	----s=python  n=  1234
>	3. print("Pi is {:.2f}".format(pi))
>	----3.14

| 符号  | 说明   | 示例                                 |
| --- | ---- | ---------------------------------- |
| `<` | 左对齐  | `"{:<10}".format("Hi")` → `"Hi "`  |
| `>` | 右对齐  | `"{:>10}".format("Hi")` → `" Hi"`  |
| `^` | 居中对齐 | `"{:^10}".format("Hi")` → `" Hi "` |

### %

|   operators    |    output     |                         example                         |
| :------------: | :-----------: | :-----------------------------------------------------: |
|       %d       |      int      |                    print("x1=%d"%x1)                    |
|       %c       | singel string |                                                         |
|       %s       |    string     |                                                         |
| %f<br>%\[m.n]f |     float     | print("x1=%8.3f\nx2=%8.3f"%(x1,x2))<br>浮点数输出宽度8位,小数位数3位 |
|       %e       |   exponent    |                                                         |
\# 格式化操作符%方式, 输出宽度大于实际输出位数时, 右对齐左补空  
	\[例] x=2.5  print("x=%6.3f"%x)  ----x=  2.500


# Structures
## If structure
- if
- if ... else
- if ... elif ... \[else]

## Loop structure
- for ... in
- range(start,end,step)
	 -no start=0, no step=1
- while
- break
	 -stop the loop
- continue
	 -skip the loop
- pass
	 -delay
- else
	 -after the loop


# Fuctions
## Define & Call
- def
- return
	 -return\[] or no return  ---- None
> [!example]
> 	import math
> 	def quadricEquation(a,b,c):
> 		delta=b\*b-4\*a\*c
> 		if delta>=0:
> 			root1=(-b+math.sqrt(delta)/(2\*a))
> 			root2=(-b-math.sqrt(delta)/(2\*a))
> 			return\[root1,root2]
> 		else:
> 			return\[]
> 	print("the roots of the Equation: 2x^2+7x-3=0")
> 	x,y,z=2,-7,3
> 	roots=quadricEquation(x,y,z)
> 	print(\'roots=',roots)
****

## Parameters
- positional arguments (required arguments)
	 -E.p. \"a b c" in def quadricEquation(a,b,c)
- default arguments (optional arguments)
	 -E.p. \"c" in def quadricEquation(a,b,c=1e-6)
	- Parameter Name Matching
	 -E.p. roots=quadricEquation(x,c=z,b=y)
- variable-length arguments
	- Single asterisk(\*) prefix - converts a group of arguments into a **tuple**
		 -E.p. def test(**\*arg**):     test(1,10,2.4) ---- (1,10,2.4)
	- Double asterisk(\*\*) prefix - converts "identifier=value" pairs into a dictionary
		 -E.p. def test(**\*\*arg**):     test(a=1,b=10,c=2.4) ----{\'a'=1,\'b'=10,\'c'=2.4}

- Parameter unpacking
	- asterisk(\*) prefix - convert list into a group of arguments
		 -E.p. print(quadricEquation(\*L))
- Parameter change
	- 如果你让形参“指向”一个新东西，实参不会变
	- 如果你改的是对象的“内容”，实参也会变
- Variable scope
	- global variable
		- Implicit use  - only read inside of a function
		- Explicit use with **global** keyword
		 -E.p. def fx(n):      global x     *\#modify a global variable inside a function*
	- local variable   - only use inside of the function

## lambda function
**lambda arguments: expression**
	-anonymous function for short, simple operations

> [!example]
> 	square=lambda x: x\*\*2
> 	print(square(5))    ----25

## Recursive function
-the function calls itself from within its own body
-2 key parts: base case & recursive case
>[!example]
>	def factorial(n):
>		if n == 1:
>			return 1
>		else:
>			return n\*factorial(n-1)
>	print(factorial(5))

### turtle
import turtle

| function              | definition                   |
| --------------------- | ---------------------------- |
| turtle.color(*color*) | color                        |
| turtle.penup()/pu()   | put up the pen               |
| turtle.pendown()/pd() | put down the pen             |
| turtle.right(x)       | turn right at the angle of x |
| turtle.left(x)        | turn left                    |
| turtle.forward(x)     | go forward for x pixel       |
| turtle.backward(x)    | go backward for x pixel      |
| turtle.toro(*(x,y)*)  | go to (x,y)                  |
