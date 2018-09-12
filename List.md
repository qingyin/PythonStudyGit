# 一、List（列表）

列表是Python中最基本的数据结构。列表中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

Python有6个序列的内置类型，但最常见的是列表和元组。

Python 内置的一种数据类型是列表：list。 list是一种有序的集合，可以随时添加和删除其中的元素。索引号是从0开始的。
## 1、创建 List（列表）

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可,且列表的数据项不需要具有相同的类型

```python
list1=['两点水','twowter','liangdianshui',123]
```
## 2、访问List（列表）中的值
使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取列表

```python
list1=['两点水','twowter','liangdianshui',123]
#通过索引来访问列表
print(list1[2])#输出： liangdianshui
#通过方括号的形式来截取列表中的数据
print(list1[0:2])#输出： ['两点水','twowter']
print(list1[:2])#输出： ['两点水','twowter']

print(list1[1:])#输出： ['twowter','liangdianshui',123]
print(list1[1:-1])#输出： ['twowter','liangdianshui']
```

## 3、更新List（列表）
可以通过索引对列表的数据项进行修改或更新，也可以通过append()方法来添加列表项。

```python
list1=['两滴水','twowter','liangdianshui',123]
print(list1)#输出 ['两滴水', 'twowter', 'liangdianshui', 123]
list1[2] = 456
print(list1)#输出 ['两滴水', 'twowter', 456, 123]
list1.append('hello')
print(list1)#输出 ['两滴水', 'twowter', 456, 123, 'hello']
```

## 4、删除List（列表）
使用del语句来删除列表的元素

```python
list1=['两滴水','twowter','liangdianshui',123]
print(list1)#输出 ['两滴水', 'twowter', 'liangdianshui', 123]
del list1[2]
print(list1)#输出 ['两滴水', 'twowter', 123]
```

## 5、List（列表）运算符

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

|Python 表达式|结果|描述|
|-----------|-----|-----|
|len([1, 2, 3])|3|计算元素个数|
|[1, 2, 3] + [4, 5]|	[1, 2, 3, 4, 5]|	组合|
|['Hi!'] * 4|['Hi!', 'Hi!', 'Hi!', 'Hi!']|复制|
|3 in [1, 2, 3]|True|元素是否存在于列表中|
|for x in [1, 2, 3]: print x,|1 2 3|迭代|

## 6、List （列表）函数&方法 ##

|函数&方法|描述|
|----|----|
|cmp(list1, list2)|比较两个列表的元素|
|len(list)|列表元素个数|
|max(list)|返回列表元素最大值|
|min(list)|返回列表元素最小值|

|函数&方法|描述|
|----|----|
|list(seq)|将元组转换为列表|
|list.append(obj)|在列表末尾添加新的对象|
|list.count(obj)|统计某个元素在列表中出现的次数|
|list.extend(seq)|在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）|
|list.index(obj)|从列表中找出某个值第一个匹配项的索引位置|
|list.insert(index, obj)|将对象插入列表|
|list.pop(obj=list[-1])|移除列表中的一个元素（默认最后一个元素），并且返回该元素的值|
|list.remove(obj)|删除第一次出现的数据|
|list.reverse()|反向列表中元素|
|list.sort([func])|对原列表进行排序|


## 7、List（列表）总结

**list是一种有序的集合，可以随时添加和删除其中的元素。与字符串的索引一样，列表索引从0开始,以-1为结束。索引号是非常重要的，大部分操作(增删查改)都需要通过索引号来完成。
列表的数据项不需要具有相同的类型。列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。**

1. 增：insert在列表指定位置上插入数据，效率方面要后退后面的数据；append在列表末尾附加上数据。
2. 删：remove删除在列表中出现的第一次要删除的数据，效率方面，后面的数据要前进。del全局方法；pop删除指定索引号上的数据
3. 查：通过key或索引来进行查询，索引号是从0开始的，最后一个元素可以通过索引号-1来访问。index函数。可以使用方括号的形式如[0:2]截取列表
4. 改：通过指定的索引号来修改数据；

其他：
count：统计某个元素在列表中出现的次数；

list既然是集合，就会有集合方面的操作运算，+ 号用于组合列表，* 号用于重复列表。








