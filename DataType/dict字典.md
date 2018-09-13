# 字典(Dictionary)

list 和 tuple 可以用来表示有序集合


## 1、创建dict（字典）

字典的每个键值 key=>value 对用冒号 : 分割，每个键值对之间用逗号 , 分割，整个字典包括在花括号 {} 中 ,格式如下所示： 

d = {key1 : value1, key2 : value2 }

注意：键必须是唯一的，但值则不必。**值可以取任何数据类型，但键必须是不可变的,可以为字符串，数字，元组，不可以为列表、字典、集合。**

## 2、访问dict（字典）

```python
tuple1 = (45,'abc')
dict2 = { tuple1:"tuple1",12:78 }
print dict2 #输出 {12: 78, (45, 'abc'): 'tuple1'}
print dict2[12] #输出 78
print dict2[tuple1] #输出 tuple1
print dict2[(45,'abc')] #输出 tuple1
```
**注意的一点是：如果字典中没有这个键，是会报错的。
**
## 3、修改dict（字典）
向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对
```python
dict2 = { 'city':'beijing',12:78 }
dict2["city"] = 'shanghai' # 修改键值对
dict2["age"] = 18 # 新增一个键值对
print dict2 #输出 {'city': 'shanghai', 'age': 18, 12: 78}
```

## 4、删除dict（字典）
通过 del 可以删除 dict （字典）中的某个元素，也能删除 dict （字典）
通过调用 clear() 方法可以清除字典中的所有元素

```python
dict2 = { 'city':'beijing','age': 18,"name" : "lili"}
print dict2.pop("age") #输出 18
print dict2 #输出 {'city':'beijing','age': 18}
del dict2["city"] # 通过 key 值，删除对应的元素
print dict2 #输出 {'age': 18}
dict2.clear() # 删除字典中的所有元素
print dict2 #输出 {}
del dict2 # 删除字典
```

## 5、dict（字典）函数&方法

|函数&方法|描述|
|----|----|
|cmp(dict1, dict2)|比较两个字典的元素|
|len(dict)|字典元素个数|
|str(dict)|输出字典可打印的字符串表示|
|type(variable)|返回输入的变量类型，如果变量是字典就返回字典类型|

|函数&方法|描述|
|----|----|
|dict.keys()    | 以列表返回一个字典所有的键|
|dict.values() 	|以列表返回字典中的所有值|
|dict.copy() |	返回一个字典的浅复制|
|dict.clear() 	|删除字典内所有元素|
|dict.get(key, default=None) |返回指定键的值，如果值不在字典中返回default值|
|dict.has_key(key) |如果键在字典dict里返回true，否则返回false|


## 6、dict（字典）总结

dict（字典）是不允许一个键创建两次的，但是在创建 dict （字典）的时候如果出现了一个键值赋予了两次，会以最后一次赋予的值为准

```python
dict2 = { 'city':'beijing','age': 18 ,"city":456}
print dict2 #输出 {'city': 456, 'age': 18}
print dict2["city"] #输出 456
```

dict 内部存放的顺序和 key 放入的顺序是没有任何关系
和 list 比较，dict 有以下几个特点：

*  查找和插入的速度极快，不会随着key的增加而变慢
*  需要占用大量的内存，内存浪费多

而list相反：

*     查找和插入的时间随着元素的增加而增加
*     占用空间小，浪费内存很少












