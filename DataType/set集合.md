# set（集合）
set是由唯一且无序的元素组成的集合。
python 的 set 和其他语言类似, 是一个无序不重复元素集, 基本功能包括关系测试和消除重复元素。set 和 dict 类似，但是 set 不存储 value 值的。

tuple算是list和str的杂合(杂交的都有自己的优势),那么set则可以堪称是list和dict的杂合.

set拥有类似dict的特点:可以用{}花括号来定义；其中的元素没有序列,也就是是非序列类型的数据;而且,set中的元素不可重复,这就类似dict的键.

set也有一点list的特点:有一种集合可以原处修改.

## 1、创建 set（集合）
set集合是唯一无序的集合

tuple (元组) 使用小括号，list (列表) 使用方括号, dict (字典) 使用的是大括号，dict 也是无序的，只不过 dict 保存的是 key-value 键值对值，而 set 可以理解为只保存 key 值。

```python
set1 = set((12,34,56))
set2 = set([123,456,789])
set3 = set({ 'city':'bj','age': 18})
set4 = set("bj4,8")
set5 = set(set3)
set6 = set()
print set1 #输出 set([56, 34, 12])
print set2 #输出 set([456, 123, 789])
print set3 #输出 set(['city', 'age'])
print set4 #输出 set(['8', ',', 'b', '4', 'j'])
print set5 #输出 set(['city', 'age'])
print set6 #输出 set([])

set1= set([123,456,789,123,123])
print set1 #输出 set([456, 123, 789])
```
set集合的定义如下，set集合是唯一无序的集合；需要关键字set来修饰，参数iterable可迭代的，则参数类型可以为元组，列表，字典，集合，字符串，不可以为数字类型。

```python
set() -> new empty set object
set(iterable) -> new set object
Build an unordered collection of unique elements. 
```

## 2、增加、删除 set（集合）
通过 add(key) 方法可以添加元素到 set 中，可以重复添加，但不会有效果
通过 remove(key) 方法可以删除 set 中的元素
pop() 从set中任意选一个删除,并返回该值
clear()清空

```python
set1 = set((12,34,56))
print set1 #输出 set([56, 34, 12])
set1.add(78)
print set1 #输出 set([56, 34, 12, 78])
set1.add(78)
print set1 #输出 set([56, 34, 12, 78])
set1.remove(78)
print set1 #输出 set([56, 34, 12])
```

## 3、set（集合）运算
元素与集合的关系

就一种关系，要么术语某个集合，要么不属于。

```
set1 = set("abc")
print("a" in set1) #输出 True
print(1 in set1) #输出 False
```
集合与集合的关系
因为 set 是一个无序不重复元素集，因此，两个 set 可以做数学意义上的 union(并集), intersection(交集), difference(差集) 等操作。
A是否等于B，即两个集合的元素完全一样, A == B 或 A != B
A是否是B的子集，或者反过来，B是否是A的超集。即A的元素也都是B的元素，但是B的元素比A的元素数量多。判断集合A是否是集合B的子集，可以使用A<B，返回true则是子集，否则不是。


```python
set1=set('hello')
set2=set(['p','y','y','h','o','n'])

# 交集 (求两个 set 集合中相同的元素)
print('交集 set1 & set2 = ',set1 & set2)
# 并集 （合并两个 set 集合的元素并去除重复的值）可使用函数A.union(B)
print('并集 set1 | set2 = ',set1 | set2)

# 差集
print('差集 set1 - set2 = ',set1 - set2)
print('差集 set2 - set1 = ',set2 - set1)

# 去除海量列表里重复元素，用 hash 来解决也行，只不过感觉在性能上不是很高，用 set 解决还是很不错的
list1 = [111,222,333,444,111,222,333,444,555,666]
print('去除列表里重复元素 set(list1) = ',set(list1))
# 输出
# ('交集 set1 & set2 = ', set(['h', 'o']))
# ('并集 set1 | set2 = ', set(['e', 'h', 'l', 'o', 'n', 'p', 'y']))
# ('差集 set1 - set2 = ', set(['e', 'l']))
# ('差集 set2 - set1 = ', set(['y', 'p', 'n']))
# ('去除列表里重复元素 set(list1) = ', set([555, 333, 111, 666, 444, 222]))
```
## 4、set（集合）函数&方法

```python
print dir(set)
#输出
# ['__and__', '__class__', '__cmp__',
#  '__contains__', '__delattr__', '__doc__',
#  '__eq__', '__format__', '__ge__',
# '__getattribute__', '__gt__', '__hash__',
# '__iand__', '__init__', '__ior__',
# '__isub__', '__iter__', '__ixor__',
# '__le__', '__len__', '__lt__',
# '__ne__', '__new__', '__or__',
# '__rand__', '__reduce__', '__reduce_ex__',
#  '__repr__', '__ror__', '__rsub__',
#  '__rxor__', '__setattr__', '__sizeof__',
# '__str__', '__sub__', '__subclasshook__',
# '__xor__', 'add', 'clear', 'copy',
# 'difference', 'difference_update', 'discard',
# 'intersection', 'intersection_update',
# 'isdisjoint', 'issubset', 'issuperset',
# 'pop', 'remove', 'symmetric_difference',
# 'symmetric_difference_update', 'union', 'update']
```


## 5、set（集合）总结


    能够索引的，如list/str，其中的元素可以重复
    可变的，如list/dict/set，即其中的元素/键值对可以原地修改
    不可变的，如str/int/tuple/frozenset，即不能进行原地修改
    无索引序列的，如dict，即其中的元素（键值对）没有排列顺序

set()来建立集合，这种方式所创立的集合都是可原处修改的集合，或者说是可变的，也可以说是unhashable

还有一种集合，不能在原处修改。这种集合的创建方法是用frozenset()，顾名思义，这是一个被冻结的集合，当然是不能修改了，那么这种集合就是hashable类型——可哈希。它没有add,clear等函数









