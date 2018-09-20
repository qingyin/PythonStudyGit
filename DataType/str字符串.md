# str字符串
在python中的字符串是一种对象类型，这种类型用str表示，通常单引号''或者双引号""包裹起来。

==**字符串对象是不可改变的，**==也就是说在python创建一个字符串后，
你不能把这个字符中的某一部分改变。任何函数改变了字符串后，
都会返回一个新的字符串，原字串并没有变。其实这也是有变通的办法的，
可以用S=list(S)这个函数把S变为由单个字符为成员的list，这样的话就
可以使用S[3]='a'的方式改变值，然后再使用S=" ".join(S)还原成字符串
## 下标和切片

下标和切片

**列表与元组支持下标索引好理解，字符串实际上就是字符的数组，所以也支持下标索引。**
下标
==如果想取出部分字符，那么可以通过下标的方法，（注意python中下标从 0 开始）==

```
name="abcde"
print(name[0])#注意python中下标从 0 开始
#a
print(name[4])
#e
```

切片
**切片是指对操作的对象截取其中一部分的操作。字符串、列表、元组都支持切片操作。
切片的语法：[起始:结束:步长]，注意分隔符号是”：”**

```
print(name[0:3])#取 下标0~2 的字符
#abc
print(name[0:4])
#abcd
print(name[0:5])#取 下标0~4 的字符
#abcde

print(name[2:]) #取下标2（包括2）以后所有的字符
#cde
print(name[:2])#取下标2（不包括2）以前所有的字符
#ab
print(name[::2])#正向隔1位取字符
#ace
print(name[::-2])#反向隔1位取字符
#eca
```
注意：选取的区间属于左闭右开型，即从”起始”位开始，到”结束”位的前一位结束（不包含结束位本身)。

```
# （面试题）给定一个字符串aStr, 请反转字符串
name="aStr"
print(name[::-1])
# rtSa
```

## string查找替换

```python
varStr = 'string test'
print(varStr.find('t'))          #查找字符串，返回查到的第一个匹配的索引，没有则返回-1
#1
print(varStr.rfind('t'))         #查找字符串，返回查到的最后一个匹配的索引，没有则返回-1
#10
print(varStr.index('t'))         #查找字符串，返回查到的第一个匹配的索引，没有则报错
#1
print(varStr.rindex('t'))        #查找字符串，返回查到的最后一个匹配的索引，没有则报错
#10
print(varStr.count('t'))         #从i到j字符串的个数，i和j类似切片，可倒数，超出字符串长度不会报错
#3
print(varStr.count('t',3))
#2
print(varStr.count('t',0,3))
#1
print(varStr.replace('st','ST',2)) #替换，'ST'替换'st'，从前往后替换2处，不加数字参数默认全部替换
#'STring teST'
varStr = varStr.center(20,'*')
print(varStr)
#'****string test*****'
print(varStr.strip('*'))           #删除字符串首尾匹配的字符，不加参数默认删除空格
#'string test'
print(varStr.lstrip('*'))          #删除字符串左匹配的字符，不加参数默认删除空格
#'string test*****'
print(varStr.rstrip('*'))          #删除字符串右匹配的字符，不加参数默认删除空格
#'****string test'
varStr = '\tTab'
print(varStr.count(' '))
#0
print(varStr.expandtabs().count(' ')) #把制表符转为空格，不加参数默认8个
#8
print(varStr.expandtabs(5).count(' '))
#5
```

## string分割/拼接

```python
Delimiter = '-'
print(Delimiter.join('string test'))   #join()将序列中的元素以指定的字符串(Delimiter)连接生成一个新的字符串
#'s-t-r-i-n-g- -t-e-s-t'
print(Delimiter.join(['string','test']))
#'string-test'
print(Delimiter.join(('string','test')))
#'string-test'
print('--'.join('string'))
#'s--t--r--i--n--g'

varStr = 'string test'
print(varStr.split('t',2))        #字符串分割，从左边开始2个't'进行分割，不填默认全部分割，
#['s', 'ring ', 'est']
print(varStr.rsplit('t',2))       #字符串分割，从右边开始2个't'进行分割，不填默认全部分割，
#['string ', 'es', '']
print(varStr.partition('t'))      #字符串分割保留分割字符串，从左边匹配的第一个
#('s', 't', 'ring test')
print(varStr.rpartition('t'))     #字符串分割保留分割字符串，从右边匹配的第一个
#('string tes', 't', '')
varStr = 'string\ntest'
print(varStr.splitlines())        #按照行('\r', '\r\n', \n')分隔，默认为false，几不保留分行符
#['string', 'test']
print(varStr.splitlines(True))    #同上，保留分行符
#['string\n', 'test']
```

用“+”能够拼接字符串，但不是什么情况下都能够如愿的。比如，将列表中的每个字符（串）元素拼接成一个字符串，并且用某个符号连接，如果用“+”，就比较麻烦了（是能够实现的，麻烦）。
用字符串的join就比较容易实现。

```python
b = 'www.itdiffer.com'
c = b.split(".")
print c
#['www', 'itdiffer', 'com']
print ".".join(c)
#'www.itdiffer.com'
print "*".join(c)
#'www*itdiffer*com'
```

## string大小写相关

```python
varStr = 'string tEst'
print(varStr.upper())      #转大写
#'STRING TEST'
print(varStr.lower())      #转小写
#'string test'
print(varStr.swapcase())   #大小写互换
#'STRING TeST'
print(varStr.capitalize()) #字符串首字母变大写，其余变小写
#'String test'
print(varStr.title())      #标题化字符串，本质:分隔符(非字母都视为分隔符)分开的字符串全部做capitalize操作
#'String Test'
strSpec = 'hI,?mY!nAme王is*jACK&how(are@you'
print(strSpec.title())
#'Hi,?My!Name王Is*Jack&How(Are@You'
import string
print(string.capwords(varStr,' ')) #这是模块中的方法，指定分隔符，分开后做capitalize操作
#'String Test'
print(string.capwords(varStr,'s'))
#'sTring tesT'
print(string.capwords(varStr,'i'))
#'StriNg test'
print(string.capwords(varStr,'trin'))
#'StrinG test'
```

## string格式输出、对齐
```python
varStr = 'string test'
print(varStr.center(20,'*')) #中对齐：输出20个字符，不足用*补足，str中间对齐
#'****string test*****'
print(varStr.center(20))     #第二个参数不填默认为空格
#'    string test     '
print(varStr.center(1))      #该方法至少要有一个参数，第一个参数小于str长度默认输出str
#'string test'
print(varStr.ljust(20,'^'))  #左对齐：str左对齐，其他同center
#'string test^^^^^^^^^'
print(varStr.rjust(20,'$'))  #右对齐：str右对齐，其他同center
#'$$$$$$$$$string test'
print(varStr.zfill(20))      #右对齐左边填充0：相当于rjust(int,'0')
#'000000000string test'
```

```python
a = "%d years" % 15
print a
#15 years
print "Today's temperature is %.2f" % 12.235
#Today's temperature is 12.23
print "Today's temperature is %+.2f" % 12.235
#'s temperature is +12.23
```

不同的占位符，会表示那个位置应该被不同类型的对象填充。下面列出许多，供参考。不过，不用记忆，常用的只有%s和%d，或者再加上%f，其它的如果需要了，到这里来查即可。

|占位符 |说明|
|----|----|
|%s | 	字符串(采用str()的显示)|
|%r | 	字符串(采用repr()的显示)|
|%c | 	单个字符|
|%b | 	二进制整数|
|%d | 	十进制整数|
|%i | 	十进制整数|
|%o | 	八进制整数|
|%x | 	十六进制整数|
|%e | 	指数 (基底写为e)|
|%E | 	指数 (基底写为E)|
|%f | 	浮点数|
|%F | 	浮点数，与上相同|
|%g | 	指数(e)或浮点数 (根据显示长度)|
|%G | 	指数(E)或浮点数 (根据显示长度)|

```python
s1 = "I like {0}".format("python")
print s1
#'I like python'
s2 = "Suzhou is more than {0} years. {1} lives in here.".format(2500, "qiwsir")
print s2
#'Suzhou is more than 2500 years. qiwsir lives in here.'
```

因为在python中还有新的格式化方法。
这就是python非常提倡的string.format()的格式化方法，其中{索引值}作为占位符，
这种方法真的是非常好，而且非常简单，只需要将对应的东西，按照顺序在format后面的括号中排列好，分别对应占位符{}即可。我喜欢的方法。

如果你觉得还不明确，还可以这样来做。

```python
print "Suzhou is more than {year} years. {name} lives in here.".format(year=2500, name="qiwsir")
#Suzhou is more than 2500 years. qiwsir lives in here.
```
真的很简洁，看成优雅。
其实，还有一种格式化的方法，被称为“字典格式化”。

## string判断
```python
varStr = 'string123'
strSpec = 'string***test'
print(varStr.isalnum())       #True,是否全是字母和数字
print(varStr.isdigit())       #False,是否全是数字
print(varStr.isalpha())       #False,是否全是字母
print(varStr.islower())       #True,是否全是小写，只对string中的字母进行判断
print(strSpec.islower())      #True,
print(varStr.isupper())       #False,是否全是大写，只对string中的字母进行判断
print(varStr.isspace())       #False,是否全是空白字符
print(varStr.istitle())       #False,是否所有单词字首都是大写，结合title()理解
print(varStr.startswith('str')) #True,判断字符串是否以'str'开头
print(varStr.endswith('123'))   #True,判断字符串是否以'123'结尾
```
##三引号

python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。

```python
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print (para_str)

para_str = '''这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
'''
print (para_str)

#输出
# 这是一个多行字符串的实例
# 多行字符串可以使用制表符
# TAB ( 	 )。
# 也可以使用换行符 [
#  ]。
#
# 这是一个多行字符串的实例
# 多行字符串可以使用制表符
# TAB ( 	 )。
# 也可以使用换行符 [
#  ]。
```


##字符串运算符
下表实例变量a值为字符串 "Hello"，b变量值为 "Python"：

|操作符	|描述	|实例|
|-----------|-----|-----|
|+	|字符串连接|	a + b 输出结果： HelloPython|
|*	|重复输出字符串|	a*2 输出结果：HelloHello|
|[]|	通过索引获取字符串中字符	|a[1] 输出结果 e|
|[ : ]	|截取字符串中的一部分，遵循左闭右开原则，str[0,2] 是不包含第 3 个字符的。|	a[1:4] 输出结果 ell|
|in	|成员运算符 - 如果字符串中包含给定的字符返回 True |	'H' in a 输出结果 True|
|not in| 	成员运算符 - 如果字符串中不包含给定的字符返回 True |	'M' not in a 输出结果 True|
|r/R|	原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母 r（可以大小写）以外，与普通字符串有着几乎完全相同的语法。| print (r'\n')输出\n print (R'\n')输出\n|





