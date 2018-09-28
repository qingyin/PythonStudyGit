# Python函数

函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。

函数能提高应用的模块性，和代码的重复利用率。Python提供了许多==**内建函数，比如print()**==。但也可以自己创建函数，这被叫做用户自定义函数。

## 函数定义

1.     函数代码块以 def 关键词开头，后接函数标识符名称和圆括号()。
1.     任何传入参数和自变量必须放在圆括号中间。
1.     函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
1.     函数内容以冒号起始，并且缩进。
1.     pass 关键字，代表什么都不干
1.     exit(num)   强行退出(num:是一个数字，显示为退出码)
1.     return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。

```python
def add(x,y):
    print("{0} + {1} = {2}".format(x,y,x+y))
    return x+y
    print("finished")   #在return后不会执行这条语句

add(1,2)
add('a','b')
#输出
# 1 + 2 = 3
# a + b = ab
```


## 函数参数/变长参数/缺省参数（默认参数）

```python
#变长参数
# 经常出现def(*args, **kwargs)这样的表现形式：
# *args          指的是：tuple  (1, )
# **kwargs       指的是：dict   {“k”: “v”}

def fun(args1,args2,*args,**kwargs):
    print("args1={0},args2={1}".format(args1,args2))
    for i in args:
        print("non-keyword args:",i)
    for i in kwargs.keys():
        print("keyword args '%s': %s" % (i,kwargs[i]))

fun(10,20,30,40,foo = 50,bar = 60)
fun(10,20,*(30,40),**{"foo" : 50,'bar' : 60})
# 输出
# args1=10,args2=20
# ('non-keyword args:', 30)
# ('non-keyword args:', 40)
# keyword args 'foo': 50
# keyword args 'bar': 60
# args1=10,args2=20
# ('non-keyword args:', 30)
# ('non-keyword args:', 40)
# keyword args 'foo': 50
# keyword args 'bar': 60

#缺省参数（默认参数）
def fun(x=2,y=3):
    print x+y

print fun(23)
print fun(11,22)
# 输出
# 26
# 33
```


## 函数返回值

```
# 函数返回单个值：
def maximum(x, y):
    if x > y:
        return x
    else:
        return y

print maximum(2, 3) #3

#函数返回多个值：
def func1(a, b):
    return a,b
def func2(a, b):
    return(a,b)

(a,b) = func1(1,2)
print a,b
x,y = func2(10,20)
print x,y
# 输出
# 1 2
# 10 20
```
## 匿名函数

lambda函数也叫匿名函数，即函数没有具体的名称。
lambda函数的语法只包含一个语句:
lambda [arg1 [,arg2,.....argn]]:expression
冒号:之前的argsn表示它们是这个函数的参数。
匿名函数不需要return来返回值，expression表达式本身结果就是返回值。

```
def f(x):
    return x**2

#等价于
g = lambda x : x**2

print f(4) #16
print g(4) #16
```












