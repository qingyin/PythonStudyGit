# tuple（元组）

tuple 和 list 非常类似，但是 tuple 一旦初始化就不能修改。那么不能修改是指什么意思呢？

tuple 不可变是指当你创建了 tuple 时候，它就不能改变了，也就是说它也没有 append()，insert(),remove(),pop()这样的方法，但它也有获取某个索引值的方法，但是不能赋值。那么为什么要有 tuple 呢？那是因为 tuple 是不可变的，所以代码更安全。所以建议能用 tuple 代替 list 就尽量用 tuple 。
## 1、创建 tuple（元组）

元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。
元组中只包含一个元素时，需要在元素后面添加逗号,tuple4=(123,)
如果不加逗号，创建出来的就不是 tuple （元组），而是指 123 这个数了，这是因为括号 ()既可以表示 tuple，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python 规定，这种情况下，按小括号进行计算，计算结果自然是 123 。

![](https://github.com/qingyin/PythonStudyGit/blob/master/DataType/image/tuple-init.png)

## 2、访问 tuple （元组）
tuple（元组）可以使用下标索引来访问元组中的值,元组下标索引从0开始，可以进行截取，组合等。

![](https://github.com/qingyin/PythonStudyGit/blob/master/DataType/image/tuple-index.png)

## 3、删除 tuple （元组）
tuple 元组中的元素值是不允许删除的，但我们可以使用 del 语句来删除整个元组

```python
tuple1 = ('hello',"world",12.34,66)
del tuple1 #是整个元组奥，删除元组中的一个元素是回出问题了
```

## 4、tuple （元组）运算符

与字符串一样，元组之间可以使用 + 号和 * 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。

|Python 表达式|结果|描述|
|-----------|-----|-----|
|len((1, 2, 3))|3|计算元素个数|
|(1, 2, 3) + (4, 5)|	(1, 2, 3, 4, 5)|	组合|
|('Hi!') * 4|('Hi!', 'Hi!', 'Hi!', 'Hi!')|复制|
|3 in (1, 2, 3)|True|元素是否存在|
|for x in (1, 2, 3): print x,|1 2 3|迭代|

## 5、tuple （元组）函数&方法

|函数&方法|描述|
|----|----|
|cmp(tuple1, tuple)|比较两个元组的元素|
|len(tuple)|元组元素个数|
|max(tuple)|返回元组元素最大值|
|min(tuple)|返回元组元素最小值|

|函数&方法|描述|
|----|----|
|tuple(seq)|将列表转换为元组|
|tuple.count(obj)|统计某个元素在元组中出现的次数|


## 6、tuple （元组）总结

**tuple元组一旦初始化就不能修改。**









