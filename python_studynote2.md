```python
list.append(obj) 在列表末尾添加新的对象，只接受一个参数，参数可以是任何数据类型，被追加的元素在 list 中保持着原结构类型。
x = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']
x.append(['Thursday', 'Sunday'])
print(x)  
# ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', ['Thursday', 'Sunday']]
print(len(x))  # 6

list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
x = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']
x.extend(['Thursday', 'Sunday'])
print(x)  
# ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Thursday', 'Sunday']

print(len(x))  # 7
```


```python
.pop#指定标号删除，并返回该值
.del#指定标号删除，不返回
.remove#指定内容删除，并返回该值
```


```python
list1 = [123, 456, 789, 213]
list2 = list1
list3 = list1[:]
print(list2)  # [123, 456, 789, 213]
print(list3)  # [123, 456, 789, 213]
list1.sort()#将list1重新排序
print(list2)  # [123, 213, 456, 789] 
print(list3)  # [123, 456, 789, 213]

list1 = [[123, 456], [789, 213]]
list2 = list1
list3 = list1[:]
print(list2)  # [[123, 456], [789, 213]]
print(list3)  # [[123, 456], [789, 213]]
list1[0][0] = 111         #将list1重新赋值
print(list2)  # [[111, 456], [789, 213]]
print(list3)  # [[111, 456], [789, 213]]


两种不同的操作为什么对list3造成的影响不一样？
```


```python
字符串：
原始字符串：\不表示转义，在字符串中仅表示\      为了避免路径作为字符串时产生错误
原始字符串只需要在字符串前边加一个英文字母 r 即可。
print(r'C:\Program Files\Intel\Wifi\Help')  
# C:\Program Files\Intel\Wifi\Help
```


```python
format 格式化函数
【例子】

str8 = "{0} Love {1}".format('I', 'Lsgogroup')  # 位置参数
print(str8)  # I Love Lsgogroup

str8 = "{a} Love {b}".format(a='I', b='Lsgogroup')  # 关键字参数
print(str8)  # I Love Lsgogroup

str8 = "{0} Love {b}".format('I', b='Lsgogroup')  # 位置参数要在关键字参数之前
print(str8)  # I Love Lsgogroup

str8 = '{0:.2f}{1}'.format(27.658, 'GB')  # 保留小数点后两位
print(str8)  # 27.66GB

```


```python
Python 字符串格式化符号
符 号	描述
%c	格式化字符及其ASCII码
%s	格式化字符串，用str()方法处理对象
%r	格式化字符串，用rper()方法处理对象
%d	格式化整数
%o	格式化无符号八进制数
%x	格式化无符号十六进制数
%X	格式化无符号十六进制数（大写）
%f	格式化浮点数字，可指定小数点后的精度
%e	用科学计数法格式化浮点数
%E	作用同%e，用科学计数法格式化浮点数
%g	根据值的大小决定使用%f或%e
%G	作用同%g，根据值的大小决定使用%f或%E
```


```python
格式化操作符辅助指令
符号	功能
m.n	m 是显示的最小总宽度,n 是小数点后的位数（如果可用的话）
-	用作左对齐
+	在正数前面显示加号( + )
#	在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')
0	显示的数字前面填充'0'而不是默认的空格
print('%5.1f' % 27.658)  # ' 27.7'
print('%.2e' % 27.658)  # 2.77e+01
print('%10d' % 10)  # '        10'
print('%-10d' % 10)  # '10        '
print('%+d' % 10)  # +10
print('%#o' % 10)  # 0o12
print('%#x' % 108)  # 0x6c
print('%010d' % 5)  # 0000000005
```


```python
字典：
三种创建方式：
1.直接创建键值对
2.建立一个空字典，再添加
dic = dict()
dic['a'] = 1
dic['b'] = 2
dic['c'] = 3

3.用dict（）函数添加#dict（）一次只能输入一个参数，因此以list或者tuple的方式把键值对传进去

dic1 = dict([('apple', 4139), ('peach', 4127), ('cherry', 4098)])
print(dic1)  # {'cherry': 4098, 'apple': 4139, 'peach': 4127}

dic2 = dict((('apple', 4139), ('peach', 4127), ('cherry', 4098)))
print(dic2)  # {'peach': 4127, 'cherry': 4098, 'apple': 4139}

4.【例子】这种情况下，键只能为字符串类型，并且创建的时候字符串不能加引号，加上就会直接报语法错误。
dic = dict(name='Tom', age=10)
print(dic)  # {'name': 'Tom', 'age': 10}
print(type(dic))  # <class 'dict'>
```


```python
dic1 = {'user': 'lsgogroup', 'num': [1, 2, 3]}

# 引用对象
dic2 = dic1  
# 浅拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用
dic3 = dic1.copy()  

print(id(dic1))  # 148635574728
print(id(dic2))  # 148635574728
print(id(dic3))  # 148635574344

# 修改 data 数据
dic1['user'] = 'root'
dic1['num'].remove(1)

# 输出结果
print(dic1)  # {'user': 'root', 'num': [2, 3]}
print(dic2)  # {'user': 'root', 'num': [2, 3]}
print(dic3)  # {'user': 'lsgogroup', 'num': [2, 3]}




c是a进行浅拷贝生成的对象，可以看到a（或b）和c两个对象整体的id是不同的，
但是里面的第5个元素-列表的地址却是相同的（指向同一个地址），所以b在浅层次元素层面（不可变）增加一个元素时，c并没跟着增加，
但是b的第5个元素-列表在增加一个元素时，c的第5个元素也跟着增加了，这就是因为b和c的第5个元素-列表是指向同一个地址的，这个地址上的值变了，
在两个地方会同时改变；

结合下面的例子理解

```


```python
list1=[1,2,3,4,[1,2,3]]#前四个属于不可变类型（浅层次）扎扎实实复制过来了，最后一个list属于深层次，没有复制过来，地址还和原来的一样，所以随着原list的变化而变化
list2=list1.copy()
list1[4].append(5)
print(list1)
print(list2)
```

    [1, 2, 3, 4, [1, 2, 3, 5]]
    [1, 2, 3, 4, [1, 2, 3, 5]]
    


```python

```


```python

```


```python

```
