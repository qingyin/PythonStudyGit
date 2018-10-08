# 高阶函数

list 和 tuple 可以用来表示有序集合


## map(f, list)函数
返回每个元素通过f计算完的value的list

map()函数接收两个参数，一个是函数，一个是序列，map将传入的函数依次作用到序列的每个元素，并把结果作为新的list返回。
```python
def fun(x):#一个参数
    return x*x

print map(fun,[1,2,3,4]) #[1, 4, 9, 16]
print map(fun,(1,2,3,4)) #[1, 4, 9, 16]
print map(fun,{1,2,3,4}) #[1, 4, 9, 16]
```

## reduce(f,list)函数
reduce把一个函数作用在一个序列[x1, x2, x3...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算

```python
#计算列表中所有数的和
def fun(x,y):
    return x+x

print map(reduce,[1,2,3,4]) #10
```
## filter(f,list)函数（过滤）
filter函数接收一个函数f和一个list，函数f的作用是对每个元素进行判断，返回True或者False，filter()根据判断结果自动过滤掉不符合条件的元素，返回符合要求的元素组成的list

```python
print filter(lambda x:x<3,[1,2,3,4]) #[1, 2]
```
## sorted()函数（排序）
python的排序有两个方法，一个是list对象的sort方法，另外一个是builtin函数里面sorted，主要区别：

1. sort仅针对于list对象排序，无返回值, 会改变原来队列顺序
1. sorted是一个单独函数，可以对可迭代（iteration）对象排序，不局限于list，它不改变原生数据，重新生成一个新的队列
    
sorted(...)
    sorted(iterable, cmp=None, key=None, reverse=False) --> new sorted list

1.  sorted(iterable, key, reverse)
1.  iterable  一个可迭代的对象
1.  key 对什么进行排序
1.  reverse  bool类型，如果为true为反序， 默认为false
1.  返回值是一个list

```python
help(list.sort)
# sort(...)
#     L.sort(cmp=None, key=None, reverse=False) -- stable sort *IN PLACE*;
#     cmp(x, y) -> -1, 0, 1
# key 用列表元素的某个属性或函数进行作为关键字（此函数只能有一个参数）
# reverse 排序规则.reverse = True降序或者reverse = False升序，默认升序
# return 无返回值

a = [-9, 2, 3, -4, 5, 6, 6, 1]
# 按从小到大排序
a.sort()
print(a)  # 结果：[-9, -4, 1, 2, 3, 5, 6, 6]

# 按从大到小排序
a.sort(reverse=True)
print(a)  # 结果：[6, 6, 5, 3, 2, 1, -4, -9]

# key参数接受的是函数对象，并且函数只能有一个参数，可以自己定义一个函数，也可以写个匿名函数（lambda）
# 按绝对值排序
def f(x):
    return abs(x)
a.sort(key=f)
print(a)   # 结果：[1, 2, 3, -4, 5, 6, 6, -9]

# 1、list对象是字符串
b = ["hello", "helloworld", "he", "hao", "good"]
# 按list里面单词长度倒叙
b.sort(key=lambda x: len(x), reverse=True)
print(b)   # 结果：['helloworld', 'hello', 'good', 'hao', 'he']

# 2、list对象是元组
c = [("a", 9), ("b", 2), ("d", 5)]

# 按元组里面第二个数排序
c.sort(key=lambda x: x[1])
print(c)  # 结果：[('b', 2), ('d', 5), ('a', 9)]

# 3、list对象是字典
d = [{"a": 9}, {"b": 2}, {"d":5}]

d.sort(key=lambda x: list(x.values())[0])
print(d)  # 结果：[{'b': 2}, {'d': 5}, {'a': 9}]


help(sorted)
# sorted(...)
#     sorted(iterable, cmp=None, key=None, reverse=False) --> new sorted list
# iterable可迭代对象，如：str、list、tuple、dict都是可迭代对象（这里就不局限于list了）
# key用列表元素的某个属性或函数进行作为关键字（此函数只能有一个参数）
# reverse排序规则.reverse = True降序或者reverse = False升序，默认升序
# return 有返回值值，返回新的队列
```











