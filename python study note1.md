```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
将对象以字符串表示的方式格式化输出到流文件对象file里。其中所有非关键字参数都按str()方式进行转换为字符串输出；
关键字参数sep是实现分隔符，比如多个参数输出时想要输出中间的分隔字符；
关键字参数end是输出结束时的字符，默认是换行符\n；
关键字参数file是定义流输出的文件，可以是标准的系统输出sys.stdout，也可以重定义为别的文件；
关键字参数flush是立即把内容输出到流文件，不作缓存。
```


      File "<ipython-input-7-f29b284ee5cd>", line 2
        将对象以字符串表示的方式格式化输出到流文件对象file里。其中所有非关键字参数都按str()方式进行转换为字符串输出；
                                                   ^
    SyntaxError: invalid character in identifier
    



```python
is, is not 对比的是两个变量的内存地址
==, != 对比的是两个变量的值
比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的。
对比的两个变量，指向的是地址可变的类型（list，dict，tuple等），则两者是有区别的。

a = "hello"
b = "hello" #地址不可变
print(a is b, a == b)  # True True
print(a is not b, a != b)  # False False

a = ["hello"]
b = ["hello"]#地址可变
print(a is b, a == b)  # False True
print(a is not b, a != b)  # True False
```

    1 6
    


```python
3. 利用位运算实现快速计算
通过 <<，>> 快速计算2的倍数问题。

n << 1 -> 计算 n*2
n >> 1 -> 计算 n/2，负奇数的运算不可用
n << m -> 计算 n*(2^m)，即乘以 2 的 m 次方
n >> m -> 计算 n/(2^m)，即除以 2 的 m 次方
1 << n -> 2^n
通过 ^ 快速交换两个整数。 通过 ^ 快速交换两个整数。

a ^= b
b ^= a
a ^= b
通过 a & (-a) 快速获取a的最后为 1 位置的整数。

00 00 01 01 -> 5
&
11 11 10 11 -> -5
---
00 00 00 01 -> 1

00 00 11 10 -> 14
&
11 11 00 10 -> -14
---
00 00 00 10 -> 2
```


```python
一个数的二进制表示可以看作是一个集合（0 表示不在集合中，1 表示在集合中）。

比如集合 {1, 3, 4, 8}，可以表示成 01 00 01 10 10 而对应的位运算也就可以看作是对集合进行的操作。
#从右到左是0-9，对应位置为1即在集合中

Python中bin一个负数（十进制表示），输出的是它的原码的二进制表示加上个负号，巨坑。
Python中的整型是补码形式存储的。
Python中整型是不限制长度的不会超范围溢出。
所以为了获得负数（十进制表示）的补码，需要手动将其和十六进制数0xffffffff进行按位与操作，再交给bin()进行输出，得到的才是负数的补码表示。
```


```python
assert 关键词#相当于程序内部打个断点
assert这个关键词我们称之为“断言”，当这个关键词后边的条件为 False 时，程序自动崩溃并抛出AssertionError的异常。
【例子】

1
my_list = ['lsgogroup']
2
my_list.pop(0)
3
assert len(my_list) > 0
4
​
5
# AssertionError
【例子】在进行单元测试时，可以用来在程序中置入检查点，只有条件为 True 才能让程序正常工作。

1
assert 3 > 7
2
​
3
# AssertionError
```


```python
enumerate()函数
enumerate(sequence, [start=0])
sequence：一个序列、迭代器或其他支持迭代对象。
start：下标起始位置。
返回 enumerate(枚举) 对象

e.g.1
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
lst = list(enumerate(seasons))
print(lst)
# [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

e.g.2:
for i, language in enumerate(languages, 2):
    print(i, 'I love', language)
print('Done!')
# 2 I love Python
# 3 I love R
# 4 I love Matlab
# 5 I love C++
# Done!
```


```python
pass 语句
pass 语句的意思是“不做任何事”，如果你在需要有语句的地方不写任何语句，那么解释器会提示出错，而 pass 语句就是用来解决这些问题的。

【例子】

1
def a_func():
2
​
3
# SyntaxError: unexpected EOF while parsing
【例子】

def a_func():
    pass
pass是空语句，不做任何操作，只起到占位的作用，其作用是为了保持程序结构的完整性。尽管pass语句不做任何操作，但如果暂时不确定要在一个位置放上什么样的代码，可以先放置一个pass语句，让代码可以正常运行。
```


```python

```
