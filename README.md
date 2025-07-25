
<style>

    .success {
        padding:5px;
        display:inline;
        color:#1B5E20;
        background-color:#C8E6C9;
    }
    .warning {
        padding:5px;
        display:inline;
        color:#E65100;
        background-color:#FFE0B2;
        width:100%;
    }
    .danger {
        padding:5px;
        display:inline;
        color:#B71C1C;
        background-color:#FFCDD2;
    }
    .info {
        padding:5px;
        display:inline;
        color:#006064;
        background-color:#B2EBF2;
    }
    .doubt {
        padding:5px;
        display:inline;
        color:#AAA;
        background-color:#DDDDDD;
    }
    .asso {
        padding:5px;
        display:inline;
        color:#555;
        background-color:#FFCC00;        
    }
    
    .alert {
        display:inline-block;
        width:100%;
        padding:5px;
        line-height:30px;
        margin-top:10px;
    }
</style>


# Learn-Python
Learn-Python
#### python缺点
相对于编译型语言（c,c++），python和javascript一样属于解释型语言，速度慢。python的运行效率低，但开发效率高。


## 基本数据类型
### 1. Number
数字类型(大的分类，下面还有整数int，浮点数float, 布尔类型bool（python中**bool类型属于Number类型的子类**），复数类型（数字j）等子分类.
<span class="danger"><b>python不区分单精度和双精度浮点数，默认双精度，int也不细分short,long整型</b></span>
```python
>>> type(1*1) // class 'int'
>>> type(1*1.0) // class 'float'
>>> type(1/1) // class 'float' 两个整型相除结果类型为浮点数
>>> type(1//1) //class 'int' 两个整型用双斜杠//相除结果类型为整型
```
<b class="danger">单斜杠</b> 除法自动转换结果为<b class="danger">浮点数</b>，<b class="danger">双斜杠</b>除法是整除<b class="danger">不考虑余数</b>

<span class="asso"><b>ES: Math.floor()  ,Math.ceil()   ,Math.round()   ,ParsrInt()</b></span>
<b class="asso">ES: typeof(134) </b>


### 2. 进制转换 10，2，8，16进制

2进制（满2进1）：0,1, 10
8进制（满8进1）：0,1,2,3,4,5,6,7, 10
10进制（满10进1）：0,1,2,3,4,5,6,7,8,9, 10
16进制（满16进1）0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F, 10
**进制类型，数据的记录方式**
2进制：0，1，0，1，0，1 1+1= 10
8进制：0，1，2，3，4，5，6，7，10，11
10进制：0，1，2，3，4，5，6，7，8，9，10
16进制：0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F,10
**python进制表示方法及转换**
2进制(binary)：0b10, 2进制转10进制，2进制的10，在IDLE中会自动转换成10进制数，结果为2
8进制(octal)：0o10, 8进制转10进制，8进制的10，在IDLE中会自动转换成10进制数，8
16进制(hex)：0x10, 16进制转10进制，16进制的10，在IDLE中会自动转换成10进制数，16
bin() 转换成2进制数方法
bin(10), bin(0x12), bin(0o10)
int() 转换成10进制数方法
int('123') //123
int(123) // 123
<b class="danger"> int(123.01) //返回错误 </b>
hex() 转换成16进制方法
oct() 转换成8进制方法
float() 转成浮点数
<b class="asso">ES:parseInt('123'), parseFloat('123.2')</b> 


### 3. bool 布尔类型
<b class="asso">
ES: Boolean()
</b>

```python
type(True) #class 'bool'
type(False) #class 'bool'
int(True) # 1
int(False) # 0
bool(1) #True
bool(0) #False
bool(2) #True
bool(0b01) #Ture
bool(0b0) #False
bool('abc') #True
bool('') #False
bool([1,2,3]) #True 列表
bool([]) #False 这里不同于JS的空数组,JS空数组Boolean([])为true
bool({1,2,3}) #True 元组
bool({}) #False
bool(None) #False
```

<b class="asso">
ES:Boolean('123') python: bool('123')

ES:true,flase python:True,False
ES数组，python列表
ES:对象，python元组
</b>

### 4. str 字符串类型
单引号 'this is a apple'
双引号 " it's a apple "
**三引号表示多行字符串，单或双都可以**

```python
"""
hello world
hello world
"""
```

`print('hello world\nhello world') `
print函数加转义字符实际也会显示成两行 hello world<b class="danger">\n</b> hello world

`print(r'c:\na1\na2') `
字符串前面加r print(<b class="danger">r</b>'String')表示的是原始字符串（所见即所得）

转义字符：换行\n, 单引号\', 制表符\t


#### 4.1 字符串运算
`'hello world'[0] ` 取字符串第0个字符
`'hello world'[0:4]`  取字符串0到4个字符串，不包含第4个
`'hello world'[6: ]`   <b class="danger"> [6: ]</b> 从第6位截取到末尾，返回world。省略即开始或末尾
`'hello world'[:-4]`  <b class="danger"> [:-4]</b> 从0位开始**往后截取**到负4位，返回'hello w'。省略即开始或末尾
`'hello world'[-4:]`  从倒数第4位开始**往后截取**，返回'orld'
<b class="asso">ES:substring(0,4)</b>
**python中字符串也是有序数据类型**
**string是不可变的序列，常用操作方法:**

```python
'a' in str
'a' not in str

str.replace('a','b',2) #将a替换成b，并指定替换次数
str.startswith('a')
str.endswith('a')

.translate()#将字符串中的每个字符根据指定的映射表进行转换。比replace方法更灵活。
.split(',') #将字符串以','分割转换成list
js:'abcde'.split('')
.join(str1) #将List转换成字符串 '-'.join(list)
js:['a','b','c','d'].join('-')
.splitlines() #将字符串按行分割，并返回一个包含每行作为元素的列表
.center(),.ljust(),.rjust() #使用指定的字符填充出指定长度的字符串，原字符串居中或左对齐或右
对齐
.zfill() #用0左填充出指定长度的字符串
.startwith('a') #是否以a开头
.endwith('a') #是否以a结尾
.upper() #全大写
.lower() #全小写
.capitalize() #首字母大写
.title() #每个单词首字母大写
.swapcase() #大小写互换
.isnumberic() #是否全为数字字符串
.isalpha() #字符是否全为字母字符串
.strip() #删除字符串头尾指定字符（默认为空格），返回新字符串
.rstrip() #删除字符串右侧空格
.lstrip() #删除字符串左侧空格
str.tstrip() #移除末尾字符，如果不指定参数则移除空白字符，如果指定参数，则移除指定参数对应的字符，如果指定多个参数字符串，则移除参数字符串中所有组合能匹配上的字符
str.strip() #移除首位字符
.find() #查找指定内容在字符串中出现的索引号，找不到返回-1
.expandtabs() #将字符串中的制表符\t转换城指定数量的空格字符
\ 转义字符，\n 换行, \\ 斜线
```

#### 4.2 格式化字符串
<b class="danger">
.format()方法格式化字符串，{n}中可以指定传入参数的索引号，可以指定变量名称
</b>

```python
1 print("{}{}{}".format('a','b','c')) #abc
2 print("{0}{0}{2}{2}".format('a','b','c')) #aacc {}指定索引号占位符
3 print("hello {}".format("world")) #hello world
4 print("hello {var}".format(var="hello")) #hello hello {}中指定变量名var
5 print("number is {:d}".format(2)) #number is 2 指定整型数值占位符
6 print("string is {:s}".format('str1')) #string is str1 指定字符串占位符
7 print("float number is {:.2f}".format(12.50)) #float number is 12.50 指定两位小数浮点数占位
8 print("float number is {:.0f}".format(12.50)) #float number is 12 指定小数四舍五入占位符
9 print("secince number is {:.4E}".format(121234123123)) #secince number is 1.2123E+11 指定
10 print("number is {:.2f}%".format(45.23)) #number is 45.23% 加%自动转换成百分比
```

<b class="danger">
f-string() 模板字符串
</b>

```python
1 >>> num = 2
2 >>> f"I have {num} apples"
3 >>> f"They have {2+5*2} apples"
4 'They have 12 apples'
5 >>> import math
6 >>> f"Π的值为{math.pi}"
7 'Π的值为3.141592653589793'
```





#### 4.3 字符编码
计算机以统一的方式存储和处理字符，无论是字母、数字、符号还是特殊字符。**字符编码通常是将字符集中每个字符映射为一个或多个字节(binary digits)**

常见的字符编码包括：
**ASCII 美国信息交换标准代码**，包含**128**个字符，英文大写小写，数字，标点，控制字符。每个字符对应**一个字节**长度**8bit**

**unicode 统一字符编码**，将世界各种语言的**每个字符定义一个唯一的编码**，以满足跨语言、跨平台的文本信息转换。unicode通常**使用一个特定**的编码方案来实现，最常见的unicode编码方案就是**UTF-8**。常见的\u是unicode转义序列。

**UTF-8** 可变长度编码方式，UTF-8 就是在互联网上使用最广的一种 Unicode 的实现方式，占用**1-4**个字节

**UTF-16**占用**2-4**个字节

**UTF-32**始终占用**4**个字节

**GBK**

```python
1 text='你好，123abcde'
2 encode_text = text.encode('utf-8') #将字符串用utf-8格式编码
3 decode_text = encode_text.decode('utf-8') #用utf-8格式解码字符串
4 text2 = text1.encode('ascii', error='ignore') #忽略无法处理的字符
5 text3 = text1.encode('ascii', error='replace') #用?代替无法处理的字符
6 with codecs.open('./text.txt', encoding='utf-8') as file #codecs包读取text.txt文件，用utf-8编码方式打开
```

unicode字符串，Unicode字符串通常用于表示包含非ASCII字符的字符串，比如中文或者特殊符号。Unicode字符串表示的是字符串本身，而不是它们的编码形式
unicode字符串 `print(u'你好，python')`

二进制字符串 `print(b'hello,python')`  *这里不能有中文*

### 5. list列表类型  python中的有序数据类型
<b class="asso">
ES: Array
</b>

List:`[1,2,2,1,'hello','abc',12.5, [2,3,22]]`
list是有序的，而且可以嵌套list, List可以通过赋值改变成员的值

#### 访问列表
List[0] 返回列表的第0个元素
如果索引号是单个数字则返回结果是List成员的字符串
如果索引号是一个区间值List<b class="danger">[0:4]</b>返回列表的第0到第4个元素(不含第4个)组成的<b class="danger">新列表</b>

#### 连接两个列表 <b class="asso">ES: concat方法</b>
`[1,2,3,4] + ['a','a1','aa'] #返回 [1,2,3,4,'a','a1','aa'] `
 

#### 重复列表
`[1,2] * 3 #返回 [1,2,1,2,1,2]`

#### 列表list的常用方法
```python
.append() #添加元素，改变原列表(如果参数是列表则会将参数当成一个元素插入)
.extend() #添加元素，改变原列表(如果参数是列表则会挨个插入)
+ #不改变原列表但生成一个新的列表

max(list)
min(list)
sum(list)

list.count(x) #找出list中匹配项出现的次数
list.index(x) #找出第一个匹配项x的索引
list.insert(3,x) #在指定位置插入x
list.pop(3) #移除指定位置上的元素
list.remove(x)  #移除list中的第一个匹配项
.remove(2) #删除指定的元素，第一个匹配的元素被删除
.clear() #清空列表
list.clear() #删除list所有值
list.copy() #浅拷贝等价于a[:]
del list[0] #del是语句，删除列表list指定索引号的元素，参数可以指定区间，可以指定步长
del list[1:6:3] #del是语句，删除列表list从第1个开始到第6个，间隔3个删除
.insert(2,'hello') #在指定位置插入元素
list.join('-') #将list根据指定字符转成str
tuple(list1) #tuple函数，转换list为tuple
tuple(range(10)) #tuple函数，转换range为tuple
list(tuple1) #list函数，转换tuple为list
list(range(10)) #list函数，转换range为list

.sort() #列表的排序，默认升序，不会生成新列表仅修改原列表
.sorted(x) #排序并复制，对x做排序生成新的经过排序后的列表
1 x1=[2,3,4,5,6]
2 x2=['d','c','a','b']
3 x1.sort(reverse=True) #reverse反向排列，[6,5,4,3,2]
4 x2.sort() #默认升序排列 ['a','b','c','d']
5
6 x1=[6,7,8,9]
7 x2=sorted(x1, reverse=True) # sorted(x1) 会生成一个经过排序后的新列表
8 x3=x1.sort(reverse=True) # .sort()方法排序修改原列表，不会生成新列表，所以x3是none
9 print(x1,x2,x3) # [9, 8, 7, 6] [9, 8, 7, 6] None
```


**使用zip()并行迭代**
```python
a=['a','b','c']
b=[1,2,3]

for x,y in zip(a,b):
    print(x,y)

```

.sort() #列表的排序，默认升序，**不会生成新列表**仅修改原列表
.sorted(x) #排序并复制，对x做排序**生成新的**经过排序后的列表


### 6. tuple元组类型  python中的有序数据类型
Tuple: `(1,2,3,4,'hello')` 元组是<b class="danger">不可变的List</b>,即元组的<b class="danger">元素不可以赋值</b>。<b class="danger">列表有的方法元组也有</b>

【1】定义只有一个元素的元组`type((1, ))`返回**tuple**。如果不加逗号是(1)则python编译器默认(1)是求值运算。
【2】定义空的元组`type(tuple())` 返回tuple，定义空的元组 type(())
`del tup #删除整个tuple`


<b class="danger">序列包含可变序列List, 和不可变序列Tuple，字符串String</b>，序列的特点类似JS中复杂类型的变量在内存中的特点，属于值地址引用。栈内存中存放的是堆内存中的内存地址。

#### 字符串、列表、元组共有的方法
【1】切片[0:10:2] 切片方法的 <b class="danger">第三个参数是步长</b>
【2】连接[1]+[2]
【3】判断元素是否**在序列内** 
2 **in** [1,2,3] 返回True 
<b class="asso">ES: [1,2,3].includes(2)</b>

判断是否**不在序列内** 
2 **not in** [1,2,3] 返回False
【4】序列的长度 **len(**[1,2,3]**)**，len('hello world')，len((2,))
【5】序列的最大值,最小值 **max(**[1,2,3]**)**，**min(**(1,2)**)** ,
**max(**'hello world'**)** 字符串最大值、最小值是字符串ASCII编码的最大值，最小值。ord('param') 转换参数为ASCII编码，参数必须为**单个字符**
【6】序列的 **方法** 使用 **.()** 调用
```python
1 x=[1,2,3,2,8,2,7,5,2]
2 print(x.index(5)) #序列的方法，指定元素，第一个匹配上的，在序列中的序号
3 print(x.count(2)) #序列的方法，指定元素，第一个匹配上的在序列中出现的次数
```
#### 序列的切片和步长 <b class="danger">适用list, tuple, string</b>
```python
1 x=[1,2,3,4,5,6,7,8,9]
2 print(x[2:5]) #返回索引2-5的值，不包含第5个值
3 print(x[:5]) #从第0个值截至到第5位，不包含第5个值
4 print(x[2:]) #从第2个开始到最后一个值
5 print(x[:-1]) #从第0个值到最后一个值
7 [3, 4, 5]
8 [1, 2, 3, 4, 5]
9 [3, 4, 5, 6, 7, 8, 9]
10 [1, 2, 3, 4, 5, 6, 7, 8]
11
12 x=[1,2,3,4,5,6,7,8,9,'hello','world']
13 print(x[2:9:2]) #第2个到第9个不包含9之间的，每两个间隔取值
14 print(x[1:10:3]) #第1个到第10个不包含10之间的，每3个间隔取值
16 [3, 5, 7, 9]
17 [2, 5, 8]

```

<b class="danger">列表切片通常会返回一个新的列表，但当使用切片赋值时，可以直接修改原列表</b>
```python
my_list = [1, 2, 3, 4, 5, 6]
my_list[2:5] = [111, 222, 333]
print(my_list) # [1, 2, 111, 222, 333, 6]
```


#### 使用<b class="danger">.copy()</b>方法可<b class="danger">浅拷贝</b>成两个独立的序列




### 7. set集合类型 python中的无序数据类型
![集合](./img/set_python.jpg)
集合是<b class="danger">无序的</b>数据类型，无法通过下标序列号获取元素。集合的元素是<b class="danger">没有重复的</b>set适用于需要**存储一组唯一元素**并进行**集合**运算的场景
<b class="asso">ES:js中的set()无重复，但js中的set是有序的。</b>
set: {1,2,3,4,'123',True}，定义空的集合 type(**set()**)
获取集合的长度 **len(**{1,2,3}**)**
判断是否在集合内 1 **in** {1,2,3}
判断是否不在集合内 1 **not in** {1,2,3}
求两个集合的**差集**，用**减法-**，{1,2,3,4,5,6} **-** {3,4} 返回{1,2,5,6}
求两个集合的**交集∩**，共有的元素，**用&** ，{1,2,3,4,5,6} & {3,4} 返回{3,4}
求两个集合的**并集∪**，**用 |**，{1,2,3,4,5,6} **|** {5,6,7} //返回{1,2,3,4,5,6,7}









### 8. dict字典类型 python中的无序数据类型
dict: { 'a':100, 'b':'hello' } dict是**无序列表** dict适用于需要通过**唯一的键**来查找、存储和操作值的场景，例如存储联系人的姓名和电话号码。
<b class="asso">ES:js中的Object对象</b>
字典中不能有重复的key，存在重复的key时，后添加的key会替代先添加的key。
字典的键key可以是字符串也可以是数值,{**1**:'a',**'1'**:'b'} ，这里**两个key1是不同的key**
字典的**key 必须是不可变的类型**，比如int, str,tuple，list可变所以不能作为key
获取key对应的value值 {'a':1,'b':2}**['a']**
获取key对应的value值 {'a':1,'b':2}**.get('a',default)**
 <b class="danger">get方法没有获取到对应的key时默认返回None,如果指定了default值则返回指定的值</b> 
定义空的字典type(**dict()**)

```python 
#获取字典的方法 get和[]

abc =  {'a':1,'b':2}
# print(abc['a']) #正常输出
# print(abc['c']) #触发KeyError错误

print(abc.get('a')) #正常输出
print(abc.get('c')) #没有获取到值时返回None
print(abc.get('c','没有获取到值时返回的默认值')) #没有获取到值时返回默认值
```

#### 字典的常用方法
len(dict1) #查看字典的元素个数
'a' in dict1 #判断dict1中是否有key为a的元素
1 not in dict1 #判断dict1中的key
dic1 **.update** (dic2) #合并字典，**会改变dic1**
dic3 = dic1 **.copy()** #浅复制一个字典
a1 = **len(** dic3 **)** #返回字典长度
'a' **in** dic1 #判断key是否在某个字典中
`lst1 = [['a',1],['b',2]]` `dict1 = dict(lst1)` #将嵌套数组lst1转成key,value格式
`dict([('a',1),('b',2)])` #将数组嵌套的元组转成key,value格式
`keys1=['a','b','c']` `dic1 = dict.fromkeys(keys1,0)` #生成**值为0**只有键名的字典，fromkeys方法的第二个参数是，填充生成字典的值
`dict(x=1,b=2)`  #返回{'x':1,'b':2}

dict['key']='aa' #修改一个键值对
dict['x']='a1' #添加一个键值对
del dict['key'] #删除指定键值对，当key不存在时，会触发KeyError错误
dict **.pop('key',default)** #删除指定键值对，当key不存在时，返回指定的值 
dic1 **.get('key',default)** #获取字典key对应的value, 当key不存在时，返回指定的值
dic1 **.keys()** #获取dic1的所有的key
dic1 **.values()** #获取dic1的所有的value
dic1 **.items()** #获取dic1的所有的key,value构成的成员，返回结果的格式是 **[(** 'key','value' **)]**
del dict #删除整个dict
dict.clear() #清空dict

`dict1.update(dict2) ` #将dict2合并到dict1

dict1.keys() #返回的是class dict_keys类，即dict的一个视图对象（不可变性，但可动态更新），用list()转化为列表
dict1.values() #返回的是class dict_values类，即dict的一个视图对象（不可变性，但可动态更新），用list()转化为列表
dict1.items() #返回的是class dict_items类，即dict的一个视图对象（不可变性，但可动态更新），用list()转化为列表

**使用zip()生成字典**
```python
keys = ["a", "b", "c"]
values = [1, 2, 3]
#zip(keys,values) 返回迭代器
dict(zip(keys, values)) #将迭代器转成字典
```



#### 遍历字典
```python
1 for keys in dic1: #遍历dic1的keys
2 print(keys)
3
4 for values in dic1.values(): #遍历dic1的values
5 print(values)
6 
7 for (k,v) in dic1.items(): #遍历dic1的key,value 键值对
8 print(k,v)
```

#### 访问字典和对象的不同
1. 字典的值只能通过键（my_dict['key'] 或 my_dict.get('key')）来访问，不能通过点号（.）操作符访问。
2. 点号操作符通常用于访问类或对象的属性设计的，字典的键并不自动成为对象属性。
3. **字典的键可以是任何不可变类型（如字符串、数字、元组等）**，而对象的**属性**名通常是符合 Python 标识**符命名规则的字符串**。字典的键可以是 'my-key' 或 123，但这些名称不符合对象属性的命名规则，因此无法通过点号访问。
4. 字典的键是动态的，可以在运行时添加或删除；而对象的属性通常是固定的，或者是通过类定义明确指定的。


## python变量
值类型 **(不可变)：int，str，tuple，** 即便是str[0]='aa' 这种对字符串的操作也不能改变字符串str原来的值。
<b class="asso">ES:'string'[0]=1 无效</b>

引用类型 **（可变）：list，set，dict** 引用类型的成员的值可以改变。`[1,2][0]='a'`
<b class="danger">id(var) 可以显示一个变量在内存中的地址</b>


tuple类型不能修改成员，也不能追加成员。tuple的使用场景主要是描述保持不变的数组类型的数据。
但在**tuple**类型中，**嵌入了可变数据类型**的成员，则这个**可变类型的成员是可以被修改的**
```python
1 a = (1,2,3,[1,2,4])
2 a[3][2]='4'
3 #返回(1,2,3,[1,2,'4'])
4 a[3].append('d')
5 #返回(1,2,3,[1,2,'4','d'])
```
user_account = <b class="danger">input()</b> 命令行输入时，使用input()函数

python中没有常量概念，**只有形式上的常量，变量名使用大写**，python文件的顶部，一般有一段注,用来说明该文件模块的内容。


## 运算符
算术运算符： `+， - ，*，/，**， //, %`
赋值运算符： `+=，-=， *=， /=， %=， **=，//=`
比较运算符：`==，!=， >=， <=， >， <`
逻辑运算符：`and， or，not  `<b class="asso"> ES: &&, ||, !</b>
成员运算符： `in，not in `<b class="asso"> ES: 没有not in 只有in</b>
身份运算符：`is，is not` <b class="asso"> ES: Object.is(param1, param2) 判断两个值是否完全相等即==) </b>
位运算符：&， |， ^，>>，<<，~ （<b class="danger">按位</b> &,|,^,>>,<<,~）
python中没有a ++, a-- 这种自增自减运算符


<b class="danger">比较运算符</b>在比较<b class="danger">字符串</b>的时候会调用<b class="danger">ord()</b>函数，将两个待比较的字符串各自分拆后逐个字符转成ASCII编码来比较。比如判断abc<abe比较时，会先比较a,a，在比较b,b，最后比较c,e

<b class="danger">比较运算符</b>在比较<b class="danger">列表</b>的时候会将两个列表的成员逐一比较，比如判断[1,2,3]<[2,3,4]比较时，会先比较1<2，再比较2<3，最后比较3<4。元组的比较也是类似



逻辑运算符可以比较bool型，数值型，字符串。在python中做逻辑运算时会自动转换数据类型：int、float类型中的0会被转换为False，大于0或小于0的会被转换为True

str类型中，**空字符串**''会被转换成False，注意不是' '(**里面有空格不是空字符串**)

list,tuple,set,dict 类型中，空的列表[],空的元祖(),空的集合{},空的字典{'a':1} 会被转换成False. <b class="asso">ES:这里不同于js中的空数组，js空数据会被转换成true</b>


身份运算符:**is, is not**, 判断的是两个变量的<b class="danger">值和值的值内存地址</b>是否相同
a=1 b=1.0
判断a <b class="danger">==</b> b时返回True，比较运算符判断的是两个值是否相等，不看值的内存地址。
判断a <b class="danger">is</b> b 的时候返回False，身份运算符判断值和值的内存地址是否相等

python中判断一个变量是否是某个类型的实例，使用
<b class="danger">isinstance： isinstance('a', str) #判断'a'是否是str类型</b>
<b class="danger">isinstance: isinstance(param1,(str, tuple, set)) #判断param1是否是str,tuple,set中的任意一种</b>

<span class="asso"><b>ES:判断对象是否是某个构造函数（类）的实例，str instanceof String // 这里str 必须是str = new String('a')的结果，这样才是String函数生成的实例。
</b></span>


#### 运算符优先级
赋值运算是右结合，从等号右边往左执行。如果表达式优先级顺序不太清晰，使用括号显式的标记运算优先级。
**算术运算符>比较运算符>逻辑运算符**
![python运算符](./img/operator_python.jpg)

##### 算术运算符
a+b, a-b, a*b, a/b
a%b #取模，求除法余数
a//b #除法取整数
a**b #幂运算，a的b次方

##### 比较运算符

a **==** b
a **>=** b
a **!=** b
a **>** b
a **<** b

##### 逻辑运算符
True **and** False, True **or** False, **not** True

##### 成员运算符
lst = [2,3,4]
dis = {'a':1,'b':2}
print(2 **in** lst) #返回true
print('c' **in** dis) #返回false

##### 身份运算符
a=[1,2,3,4,5]
b=a
c=[1,2,3,4,5]
a is b # True
a is c # False
a is not c # True



## python流程控制语句
python编码规范：
行末尾不强制加分号结尾。不需要用{}包裹代码块，python使用缩进表示代码块
### 1. 条件控制语句 if-else
<b class="danger">pass</b> 语句在python中用来作占位，使语句能顺利执行下去不出错
```python
1 if condition_test:
2   pass
3 elif condition_test2:
4   pass
5 else:
6   pass
```
<b class="asso">ES:if () {} else if () {} else {}</b>

### 2. match 条件判断
```python 
match status_code:
    case 400:
        print("Bad Request")
    case 404:
        print("Not Found")
    case 500 | 503: #使用| 或运算符，表示匹配多个值
        print("Server Error")
    case _: #默认情况
        # 执行默认情况的代码，即所有其他未被明确匹配的情况
```
```python
# point是一个元组(x,y)
    match point:
        case (0,0):
            print("Origin")
        case (0,y):
            print(f"On the Y axis at {y}")
        case (x,0):
            print(f"On the X axis at {x}")
        case (x,y):
            print(f"On the ({x},{y})")
```

<b class="asso">ES:switch case</b>

### 3. 循环while else
```python
1 while condition:
2   pass1
3 else:
4   pass2 #else是condition条件为false时执行的代码块

1 count =1
2 while count <=10:
3   count +=1
4   print(count)
5 else:
6   print('EOF')
```
while循环的使用场景是，设定condition为条件判断，condition条件为true时就一直执行语句块，条件判断为<b class="danger">false</b>时就执行<b class="danger">else</b>后面的语句块。while多用在递归的场景中。

<b class="asso">ES: while(){}, do{} while</b>

### 4. 循环for else
for 循环用来遍历/循环 序列、集合、字典

for **target_list in expression_list**:
    pass1
else:
    pass2
<b class="danger">else</b> 语句块在for循环<b class="danger">正常结束</b>（**非break终止**）后执行
```python
1 a = [['a','b','c'],(1,2,3)]
2 for i in a:
3   print(i,end='--')
4   for y in i:
5       print(y,end="|")
6 else:
7   print('EOF iterate done')
```
print(a,<b class="danger">end = '|'</b>)
print函数使用<b class="danger">end参数</b>可以将需要打印的元素横向间隔排列。

### 5. 循环-列表推导式

new_list = **[** expression for item in iterable **if** condition **]**
```python 
list1 = [1,2,-3,5,6,9,-10]
new_list = [item * 2 for item in list1 if item>0]
print(new_list)
```

### 6. 循环控制 终止循环 使用break, continue
break 终止循环跳出整个循环，continue 跳过本次循环但会继续执行下一次循环。<b class="danger">break</b>会<b class="danger">中断</b>for循环遍历，使for循环结束后的else不执行，但<b class="danger">在循环嵌套的场景下，break只会中断所在层级的循环</b>，<b class="danger">对外层循环不会中断</b>
```python
1 a = [1,2,3]
2 for x in a:
3   if (x == 2):
4       break
5   print(x, end='|')
6 else:
7   print('EOF')
8 # x==2时终止循环，整个过程只会打印出1|, break语句终止循环后
```

```python
1 a = [1,2,3]
2 for x in a:
3   if (x == 2):
4       continue
5   print(x, end='|')
6 else:
7   print('EOF')
# x==2时跳过本次循环，整个过程会打印出1|3|EOF
```

#### for循环的范围限定使用range()函数
<b class="asso">ES for 循环：</b>
```js
1 // js文件
2 let a = [1,2,3,4,5,6,7,8,9,10]
3   for (let i =0;i <= a.length; i ++) {
4       console.log(i+'|')
5 }
```

```python
# python文件
1 for i in (range(0,10)):
2   print(i)
3 # 打印出0,1,2,3,4,5,6,7,8,9 共10个数字

1 for i in (range(0,10,2)):
2   print(i)
3 #打印出0，2，4，6，8 共5个数字，range()函数的第三个参数表示步长
```

#### range列表和生成器
**range(num1, num2, length)**
range范围num1是起始数值，num2是终止数值但不包含num2，length是步长，步长可以为负数表示递减。
<b class="danger">range生成一个整数区间,不包含末尾一位，</b>类型为`<class range>`， <b class="danger">range不是一个列表但可以使用索引访问值，使用括号表示range，逗号表示范围,</b> **第三个参数代表步长**。使用 **list()** 函数可以生成由 **range** 指定区间范围的 **列表** ，使用 **tuple()** 可以生成指定范围**元组**，使用 **set()** 可以生成指定范围 **集合**
```python
1 for x in range(10,2,-2):
2   print(x)
3 #结果打印出10，8，6，4

x = range(0,5)
y = tuple(x) #转成元组
y
(0, 1, 2, 3, 4)

y1 = list(x) #转成列表
y1
[0, 1, 2, 3, 4]

y2 = set(x) #转成集合
y2
{0, 1, 2, 3, 4}

sum(range(4)) #返回6，即0+1+2+3
```

#### all()函数，检查可迭代对象（list,tuple,set,dict）中的所有元素是否都为True,返回bool值
**检测字典dict时，判断的是键key**
all(iterable)

```python
# 列表
print(all([True, 1, 'non-empty string']))  # 输出: True
# 有一个元素为 False
print(all([True, 0, 'non-empty string']))  # 输出: False
print(all([])) #输出true

#元组
# 所有元素都为 True
print(all((True, 1, 'non-empty string')))  # 输出: True
# 有一个元素为 False
print(all((True, 0, 'non-empty string')))  # 输出: False


#集合
# 所有元素都为 True
print(all({True, 1, 'non-empty string'}))  # 输出: True
# 有一个元素为 False
print(all({True, 0, 'non-empty string'}))  # 输出: False

#字典
# 所有键都为 True
print(all({True: 1, 1: 'non-empty string', 'key': 'value'}))  # 输出: True
# 有一个键为 False
print(all({True: 1, 0: 'non-empty string', 'key': 'value'}))  # 输出: False

```

验证列表中的所有元素是否满足某个条件
```python
numbers = [1, 2, 3, 4, 5]
print(all(x > 0 for x in numbers))  # 输出: True
```

检查多个条件是否都为真
```python
conditions = [True, True, True]
print(all(conditions))  # 输出: True

my_dict = {'a': 1, 'b': 2, 'c': 3}
print(all(isinstance(key, str) for key in my_dict.keys()))  # 输出: True
```

#### any() 判断可迭代对象（如列表、元组等）中是否有任意一个元素为 True
```python
print(any([False, False, False])) # 输出: False
print(any([False, True, False]))  # 输出: True
```


## python 工程组织结构
### 包、模块、类
python项目的组织结构，最顶级的层级<b class="danger">包</b>层级（类似文件夹），然后是<b class="danger">模块</b>层级（类似文件）、最后是写在模块文件中的<b class="danger">类</b>。**包的文件夹结构是可以嵌套的** 

<b class="danger">  \_\_init__.py 是一个包被导入的时候自动执行的文件，当导入包，或者导入包下面某个模块的某个变量时 \_\_init__.py 文件也会自动执行。</b> 包和包中**某个模块中的某个变量**被导入时都会自动执行\_\_init__.py

文件夹下如果有 <b class="danger">\_\_init__.py</b> 文件，则代表该 <b class="danger">文件夹是一个包</b> ,如果一个文件夹下**没有\_\_init__.py**则python认为该文件夹是**普通文件夹**。

**\_\_init__.py**本质上就是一个模块文件，\_\_init__.py文件可以写代码，<b class="danger">也可以不写只是用来标注一个包。</b>

<b class="danger">\_\_init__.py模块的名称就是包的名称，</b>比如**seven**目录下有__init__.py，则__init__.py**模块的名称就是seven**。

一个 .py 文件可以称为模块，包含了 \_\_init__.py 文件的称为包。

**\_\_init__.py 常用来执行模块导入时的初始化动作，比如用来收敛包（文件夹）下各模块公用的类库/模块**


不同包下同名的模块，使用**命名空间**来区分
```python
1 seven.c4
2 six.c4 
3 #seven,six 是包名称，c4是模块名称
```

#### 导入模块的方法
##### import
```python
1 import module_name # 导入同级目录下的某个模块
2 import a1.module_name #导入同级目录下a1目录下面的module_name模块
3 import t.b.c7 as m #导入t/b下的c7模块，并使用m表示，调用c7模块时使用m.a调用
```


```js
1 // js文件
2 // require
3 const module = require('module')

// exports 
5 export.fs = fs 
6 module.exports = fs

8 // import
9 import fs from 'fs';
10 import {  fs as newFs } from 'fs'; // ES6语法, 将fs重命名为newFs, 命名冲突时常用import { a as b}
11 import fs, { part } from fs; //表示从文件系统模块中导入默认导出和名为part的具名导出。

12 // export 
13 export default fs;
14 export const fs;
15 export function part;
16 export { part1, part2 };
17 export * from 'fs'; //将模块 'fs' 中的所有导出内容重新导出到当前模块

```

#### from import 
导入某个包/模块下的局部变量或局部函数
from t.c7 import a  导入**t.c7**模块下的**a**变量，调用a变量时可直接使用 **.方法** 调用
from t import c7# 导入t模块下的c7模块，调用a变量时使用**c7.a**调用
from t.c7 import a, b, c #导入t.c7模块下的a,b,c三个变量
from t.c7 import (a, b
c) 导入t.c7模块下的a,b,c三个变量,c变量可以在括号内换行,需要导入多个变量（换行）时，使用**括号**包裹
from t.c7 import * 导入t模块下c7模块下的所有变量

<b class="danger">import方法导入的是模块，from import 导入的可以是某个变量也可以是某个模块</b>

#### \_\_init__.py 文件定义导入文件
导入一个包时,\_\_init__.py文件会自动执行，使用\_\_init__.py文件导入变量使用场景
在**包t**下的\_\_init__.py模块文件中编写需要多次重复导入的模块，比如
```python
1 #__init__.py文件
2 import sys
3 import datetime
4 import io
```

在其他目标文件中直接导入包t即可导入包t下\_\_init__.py模块文件中所导入的变量/库
```python
1 import t
2 print(t.sys)
```
#### 导入模块注意事项
1. 包和模块**不会被重复导入**，**多次**引用同一个包或模块，但其导入过程**只会执行一次**。
2. 当导入某个模块时，该模块文件中的代码会**自动执行一次**。
3. 避免循环导入
4. **如果一个.py文件被当作python执行的入口文件，这个.py文件的顶级不会有package包，即便当前.py文件同级路径存在\_\_init__.py也不会打印出\_\_package__**，即如果python直接执行这个.py文件时，这个.py文件中的\_\_package__为NoneType。**如果一个.py文件被当作模块导入后，这个.py文件中的\_\_package__会指向其命名空间路径**。
5. **如果需要将某个c15.py入口文件当作模块调用可以使用`python -m seven.c15` 明确c15.py的顶级包seven，并使用-m的方式调用，此时c15.py文件的\_\_package__就不为NoneType**
6. 指定源码文件的执行编码环境，在源码文件的头部加入注释指定源码文件运行的字符集
`# -*- coding: cp1252 -*-`

#### 相对导入、绝对导入
import package2.package4.m2 #绝对路径导入，根据文件路径导入某个模块

from .m3 import m #相对路径导入，导入相对于当前路径下的m3模块

from ..m4 import m #相对路径导入，导入相对于当前路径，上一级目录下的m4模块

注意，<b class="danger">使用相对路径导入时，不能超过当前模块的顶级包路径，否则出现以下错误</b>
**attempted relative import beyond top-level package**

<b class="danger">在python项目的入口文件中，不建议使用相对路径导入模块，优先使用绝对路径导入。或者使用相对路径导入，但将入口文件当成模块调用(加-m参数)</b> 
无论入口文件如何运行，优先使用绝对导入，避免因运行方式不同而导致的导入问题。如果入口文件是通过 python script.py 的方式直接运行，那么它会被视为一个顶层脚本（top-level script），而不是包的一部分。此时，无法使用相对导入（如 from . import module 或 from .. import module），因为 Python 无法确定它的父包。
`python -m pkgName.moduleName` *明确入口文件的顶级包*

<b class="danger">绝对引入，要从顶级包开始写 top.ab.cd</b>, **顶级包的位置是相对于python执行入口.py文件的位置来确定的**


*添加绝对路径后再导入包*
```python
1 import sys
2 sys.path.append('c:\\users\\desktop') #添加一个绝对路径
3 import packageName1 #添加绝对路径后可以直接导入绝对路径下的包
4 packageName.fn1('hello world')

```

### 模块的内置变量
python c15.py #python 将c15.py <b class="danger">当作程序入口</b> 文件直接执行 
python <b class="danger">-m</b> seven.c15 #python 将seven目录下的c15.py文件 <b class="danger">当作模块调用</b> （.py文件当作模块调用时必须有包的环境(加<b class="danger">.</b> )，**seven**目录这时候就是包），这种方式不同于python seven\c15.py#仍然是当入口文件调用

**main.py入口文件不是顶级包，只是入口文件**

`info=dir()`
`print(info)`
<b class="danger">dir()函数</b> 
如果没有**提供参数**，dir()函数将返回**当前作用域内的有效属性列表**。如果**提供了参数**，dir()函数将返回该**参数对象的有效属性列表**。dir()函数通常用于查看对象的属性，以便在编程时了解可以对对象进行哪些操作。

**带双下划线的是python的内置变量**
\_\_annotations__
\_\_builtins__
\_\_cached__
<b class="danger">\_\_doc__</b> 当前模块的注释信息
<b class="danger">\_\_file__</b>当前模块文件相对于**执行入口文件所在目录的**文件路径
\_\_loader__ 引用了本模块的加载器对象，即该模块的上下文是由这个加载器加载到内存中的
<b class="danger">\_\_name__</b> 当前模块的完整名称，包含了命名空间，比如t.c9
<b class="danger">\_\_package__</b>  当前模块 <b class="danger">所在的包</b> 名称比如t，**相对于执行入口文件所在的目录**
\_\_spec__
**\_\_init__.py** python检测到一个目录下存在\_\_init__.py文件时，python就会把它当成一个模块
**\_\_all__** 在某个模块文件中指定可以被导出的变量，或在\_\_init__中指定可以被导出的模块。如果不定义 __all__，所有不以单下划线 **_** 开头的名称都会被 * 导入，这可能导致不必要的名称污染，或者导入一些你不希望暴露给用户的内部实现细节。<b class="danger">但显式的导入方式，比如import module或者from module import name 这种方法，不受__all__的限制</b>
**\_\_closure__[0].cell_contents #查看对象的闭包变量**

当一个模块是程序的**入口文件**时即执行**python abc.py**时，该模块文件的 **\_\_name__** 会显示为 <b class="danger">\_\_main__</b>  ，**\_\_file__**文件路径会显示为**当前模块的文件名**（没有路径）

<b class="danger">\_\_name__的经典应用</b>
`make a script both importable and executable` 让一个脚本既可被当作模块导入，也可被解析执行
```python
1 #t1.py文件
2 if __name__ == '__main__':
3   pass1
4 pass2
```
当t1.py作为 <b class="danger">程序入口</b> 直接 <b class="danger">执行</b> 的时候会执行**pass1**, 当t1.py <b class="danger">被其他模块导入时</b> t1.py只会执行**pass2**，不执行pass1



## 函数
定义函数
```python 
def fn(param1, param2 = 'abc'):  #param2是函数参数默认值
    pass
    return val1
```

#### 函数的多个返回值
```python 
def damage(sk1,sk2):
    val1 = sk1 * 2
    val2 = sk2 * 2
    return val1,val2 

resule1, resule2 = damage(2,3)
```
**返回多个值**，使用**逗号分隔开**，逗号分隔开的返回值其**类型是元组tuple**
**获取**函数的**多个返回值**的时候，用逗号分隔声明变量**解构赋值**方法，**接收结果**的变量和函数内部**返回值的先后顺序**有关

#### 声明多个变量
```python 
a,b,c=1,2,3 #a=1, b=2, c=3
a,b,c=[1,2,3] #a=1, b=2, c=3
a,b,c=(1,2,3) #a=1, b=2, c=3
a = 1,2,3 #a=(1,2,3)
```
`a,b,c=1,2,3` 
`a,b,c = d` d是序列类型时（**tuple,list**），此时a,b,c会序列解包
`a = 1, 2, 3` #a赋值后是tuple类型
<b class="asso">ES: let a=1,b=2,c=3 或者 let {a,b,c} = {a:1,b:2,c:3}</b>

#### 使用 namedtuple 进行更优雅的解构
如果你希望将字典解构成对象的形式，可以使用 collections.namedtuple 或 dataclasses.dataclass。
```python
from collections import namedtuple

data = {'name': 'Alice', 'age': 25, 'city': 'New York'}
Person = namedtuple('Person', ['name', 'age', 'city'])

person = Person(**data)

print(person.name, person.age, person.city)
```

#### 使用 dataclass 进行更优雅的解构
```python
from dataclasses import dataclass
@dataclass
class Person:
    name: str
    age: int
    city: str
data = {'name': 'Alice', 'age': 25, 'city': 'New York'}
person = Person(**data)
```


##### 链式赋值
`a=b=c=1` a=1,b=1,c=1
<b class="asso"> let a=b=c=1</b>

#### 函数参数
##### 1. 必须参数
```python 
def fn(x,y):
    return x+y
```
调用时传入的实际参数必须和形式参数个数一致且顺序一致

##### 2. 关键字参数
```python 
def fn(x,y):
    return x+y
```
调用时传入的参数不用考虑顺序，只需要参数名和形式参数一致即可`fn(x=1,y=2)`
<b class="asso">ES:通过解构赋值实现调用函数时不考虑参数传入顺序</b>
```js
function fn({x,y}){
    return x+y
}
fn({y:2,x:1}) //不考虑参数传入的顺序
```

##### 3. 默认参数
```python 
def fn(x,y=2):
    print(f"x is {x},y is {y}")
```
调用时`fn(1) #x1,y2`
调用时`fn(3,4) #x3,y4`
python语法要求，python中有 <b class="danger">默认值的参数</b>要放<b class="danger">末尾</b> ，声明函数时，**必须参数靠前**，有默认值的**默认参数尽量放后面**。


##### 4. 可变参数
```python 
def fn(*param):
    print(param)
```
调用时 fn(1,2,3,4,5), 打印param时(1,2,3,4,5)会自动将参数列表转换成**tuple**，函数内部定义的可变参数param会 <b class="danger">自动收敛传入参数，并转成tuple</b> 
```python 
def fn(x,y,z):
    print(f"x is {x},y is {y}, z is {z}")
```
<b class="danger">fn(\*(1,2,3))</b>
调用时 fn(*(1,2,3))使用\*调用将传入的参数tuple平铺**逐一匹配**到函数内部的**形式参数**位置

<b class="asso">ES: 参数收敛</b>
```js
function fn1(...param){
    console.log(param)
    // 调用fn1(1,2,3,4)时，param被收敛为[1,2,3,4]
}

function fn2(x,y,z) {
    console.log(x, y, z)
}
//调用fn2(...[3,4,5])时，...[3,4,5]被平铺到函数中的形式参数位置
```

##### 5. 关键字可变参数
收敛传入的关键字参数，基于字典的可变参数，传入参数转成dict格式
```python 
def fn(**param):
    print(param)
```
<b class="danger">将传入的参数收敛为dict</b> 
调用时`fn(x=1,y=2,z=3)`,param为{'x':1,'y':2,'z':3}

```python 
def fn(x,y,z):
    print(f'x is {x},y is {y},z is {z}')
```
调用时`fn(**{'y':3,'z':2,'x':4})` 不用强调传入参数的顺序x4,y3,z2

```python
prompt_template = "Hello, my name is {name}, I am {age} years old, and I live in {city}."
inputs = {
    'name': 'Alice',
    'age': 30,
    'city': 'New York'
}
result = prompt_template.format(**inputs)
```
实际**inputs 将 inputs 字典解包为 name='Alice', age=30, city='New York'
`prompt_template.format(name='Alice', age=30, city='New York') ` 
将这些值替换到模板中的相应占位符位置。



## 变量作用域
#### 函数的局部变量和全局变量
局部变量只能在其被声明的函数内部访问，而全局变量可以在整个全局上下文环境访问。
**某个模块中函数内部global关键字定义的全局变量也是可以被其他模块导入使用的**
<b class="danger">函数内声明全局变量</b> 
```python 
def fn():
    global a
    a  = 'default'

fn() #fn函数执行后创建了一个全局变量a
```
#### 作用域
函数内部定义的变量（局部变量）作用域在函数内部，函数外部无法引用函数内部变量（闭包除外，还可以使用global关键字变量在函数内部定义全局变量）。但函数内部可以引用全局变量即函数外部定义的变量，或者嵌套函数，其内部变量可以引用外层变量。
```python 
c=10
def fn():
    print(c) #打印出10
```
注意：python只有**全局作用域**、**函数作用域**的概念，python**没有代码块级的块作用域**。在python中，**for循环，while循环，if..else等非函数不能形成独立的块作用域**。所以python for循环中声明的变量，**在for循环外部**是**可以访问**的。<b class="danger">不同于JS，有块级作用域。</b> 



## 面向对象
类：用class定义，类变量 <b class="danger">首字母大写，驼峰命名法</b>，类的最基本作用是用来封装代码。类中定义的函数即方法。类就是对现实世界的抽象定义。
```python 
class Student():
    sum = 0
    age = 0
    #构造函数，初始化实例，self指向实例对象
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def fn(self):
        print(self.name,self.age)

# 实例化stu1
stu1 = Student('json',18)
# 调用实例的方法
stu1.fn()
```
在定义类class的实例的**构造函数**和**方法**时， <b class="danger">必须显式的传入第一个参数self</b>

#### 导入类
```python 
from c1 import Student
stu2 = Student('penny',18)
stu2.fn()
```
#### 类和对象的关系
**类**是现实世界或思维世界中的实体在**计算机中的一种抽象反映**，将抽象出的实体，其 <b class="danger">属性</b>和对属性的操作即<b class="danger">方法</b> 封装在一起。简单理解，类抽象出**实体的特征与行为**，类基本可以理解为模板对象，即通过类**实例化**出的一个**实例**。
```python 
class Studen():
    name= 'default value'
    age= 0
    def __init__(self, name, age): #python类的构造函数
        self.name=name #通过构造函数的执行来初始化对象的属性
        self.age=age #通过构造函数的执行来初始化对象的属性
```
**实例化**一个实例时，类的**构造函数会自动执行**。构造函数或实例方法内的**self**始终**指向实例**。
<b class="asso">ES:类的定义方法
</b>
```js
class Student{
    constuctor(name,age) { //构造函数
        this.name=name
        this.age=age
    }
    fn() { //实例方法
        console.log(this.name) //this指向实例对象
    }
    static fnStatic() { //类class的静态方法
        console.log(this) //静态方法中this指向的是类而不是实例
    }
    static valStatic = 'default' //类的静态属性
}
```

#### 类变量、实例变量
类变量即类自身的**静态属性**，类变量要**和类关联在一起**，**体现出类的意义**。
实例变量即类**实例化后的属性**，实例化后生成对象的属性。实例变量和对象关联在一起
```python 
 class Student():
    sum=0 #类的变量，与类相关联，JS类的变量用static静态属性表示
    def __init__(self, name, age): #self只是占位符，可以用this替代
        self.name=name #实例变量
        self.age=age #实例变量
        self.__class__.sum += 1 #构造函数中访问类的属性
    def fn1(self): # 定义函数的时候参数传入self，表示该函数是实例的方法
        print(self.name) #访问实例的属性
        print(self.__class__.sum) #访问类的属性
        print(Student.sum) #访问类的属性
```

#### 类与对象的变量查找顺序
`stu1 = Student()`

stu1<b class="danger">.\_\_dict\_\_ </b> **对象（包含类或者实例）的__dict__对象中保存了当前对象的所有变量**
注意：类的静态属性（类变量）和实例属性（实例变量）的查找顺序，如果查找一个实例的变量，首先在实例属性中查找，如果找不到就去类的静态属性中查找，如果类中找不到就会去类的父类中中查找。
<b class="asso">ES:JS的原型对象</b>

##### 在实例方法中访问实例变量与类变量
实例方法中访问实例变量，<b class="danger">self.val</b> 
实例方法中访问类变量：<b class="danger">ClassName.val</b>  或者 <b class="danger">self.\_\_class\_\_.val</b> 


#### 类方法 @classmethod
```python 
class Student():
    name=''
    sum=0
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def fn(self):
        print(self.name)
        print(Student.name)
        print(self.__class__.name)

    @classmethod #装饰器，定义类的方法
    def fn2(cls):
        cls.sum += 1 #访问类的属性
```

`@classmethod` 定义类的方法时增加 **@classmethod装饰器** 
显式的传入第一个参数cls,传入的参数 **cls** 表示 **class** ，可以使用其他变量代替。
类的方法中访问类的属性，访问类的属性cls.val，和实例方法中 <b class="danger">self.\_\_class\_\_.val</b> 等价，等价于 <b class="danger">ClassName.val</b>。
调用类的方法：ClassName.fn2()
通过类的实例调用类的方法(不建议这么调用没意义):
`ins1 = ClassName()`
`ins1.__class__.fn2()`
<b class="danger">如果方法需要操作类本身（如修改类属性或创建类的实例），使用 @classmethod 在方法函数中显式传入cls</b>

#### 静态方法 @staticmethod
当一个方法与类相关，但不需要访问类或实例的状态时，可以将其定义为静态方法。不需要传递隐式的 self 或 cls 参数
```python 
class MyClass:
    @staticmethod
    def my_static_method(x, y):
        return x + y

# 调用静态方法
result = MyClass.my_static_method(5, 3)  # 输出：8
```
<b class="danger">类的方法不需要访问类或实例的状态，使用 @staticmethod</b>

#### 私有方法 __
Python 并没有真正的“私有”方法，单下划线 _ 只是一种约定，提醒开发者这些方法不应该被外部直接调用。


#### 成员可见性
对类的变量即类的静态属性的操作，放到类的静态方法中，或者实例方法中去操作。不建议在外部直接操作类的属性比如 `ClassName.val = 1`  这种操作不建议。**成员的可见性即设置私有方法或私有属性，不允许从外部访问或修改，体现封装性**。

**类的私有方法** 在一个类中定义的方法(类方法或者实例方法)名称前面加<b class="danger">\_\_</b>表示该方法为类的私有方法，私有方法在类的外部无法调用，比如`ClassName.__fn()`

**私有变量** 在变量名前加<b class="danger">\_\_</b>该变量就成为私有变量，私有变量只能在对象内部访问，无法在外部访问，比如`obj.a`
```python 
class Student():
    __abc = '这是类的私有变量' #声明类的私有变量
    def __init__(self,name,age):
        self.name=name
        self.age=age
        self.__instval = '这是实例的私有变量' #声明实例的私有变量
    def fn(self):
        print(self.name) 
        print(self.__instval) #内部访问实例的私有变量
        print(Student.__abc) #内部访问类的私有变量
        print(self.__class__._Student__abc) #内部访问类的私有变量
        self.__privateMethod() #Student类的内部访问私有方法
    def __privateMethod(self): #声明实例的私有方法
        self.__abc = 'modify private val 1' #操作类的私有变量
        self.__instval = 'modify private val 2' #操作实例的私有变量
        print(self.__abc)
        print(self.__instval)
    def __fn2(): # 这里不传入self参数
        print(Student.__abc) # 操作类的私有变量

stu1 = Student('a',18) #实例化stu1
```
#### Name Mangling
类的私有变量会被Name Mangling,例如类的私有变量__privateVal会被重命名为_ClassName__privateVal，实际访问时用ClassName._ClassName__privateVal访问。

实例的私有变量会被Name Mangling，例如实例的私有变量__instval会被重名名为_ClassName__instval，实际访问时用obj._ClassName__instval访问。 实例的私有变量是绑定到具体实例上的，而不是直接挂载到类上。

无论是类的私有变量还是实例的私有变量，只要是以双下划线 __ 开头，都会被改写为 _类名__变量名 的形式。

**注意：**
以上代码中直接访问`Student.__abc` 或者 `Student.__privateMethod`会提示错误，无法直接通过类访问类的私有属性和方法。但可以通过hack方法变通访问`Student._Student__abc`或者`Student._Student__privateMethod`

以上代码中访问直接访问`stu1.__abc` 或者 `stu1.__privateMethod`会提示错误，无法直接通过实例访问**父类的**私有属性和方法。但可以通过hack方法变通访问`stu1.__class__._Student__abc`或`stu1.__class__._Student__privateMethod`
或`stu1._Student__abc`或`stu1._Student__privateMethod`

以上代码中直接访问`stu1.__instval` 会提示错误，无法直接通过实例访问实例的私有属性，可以hack方法变通访问`stu1._Student__instval`访问。由此看出构造函数中声明的实例私有属性，也被挂载到类的私有属性上。

python中类的构造函数中定义私有属性后，可通过 **\_\_dict\_\_** 查看实例的所有变量，可以发现私有属性被改名为 **\_ClassName\_\_privateVar** ,即在 **\_类** 名后面加私有属性.

python中虽然有私有变量概念，但私有变量还是可以通过hack方法访问的，通过__dict__可以知道python的私有变量只不过通过改名实现的，所以通过instance._ClassName__privateVar 可以访问到私有变量

`obj._val = 1` 这种看似在外部修改了名称为_val的私有变量，实则是由于**python有动态语言**的特性，在obj对象上增加了一个名称为_val的变量并设置值为1。所以，python中不能动态的添加一个私有属性。python中的私有属性和方法都被自动添加了 **\_ClassName** 前缀。


示例2
```python 
class Humman():
    sum = 0
    __hmval = 'humman class private val' #声明类的私有变量
    def __init__(self,country):
        self.country=country
        self.__huminst = 'humman instance private val' #声明实例的私有变量
    def getCountry(self):
        print(self.__huminst) #内部访问私有变量
        print(Humman.__hmval) #内部访问类的私有变量
        print(self.__class__._Humman__hmval) #内部访问类的私有变量

print(Humman._Humman__hmval)
#类，访问私有变量，返回humman class private val

hum1 = Humman('中国')
print(hum1.country)
#访问实例的属性，返回中国

#print(hum1.__huminst)
#直接访问实例的私有变量，返回错误信息

print(hum1._Humman__huminst)
#在实例上访问实例的私有变量，返回humman instance private val

hum1.getCountry()
#返回 humman instance private val
#返回 humman class private val
#返回 humman class private val
```


## 面向对象 继承
继承，避免重复定义方法和变量。`Student(Human)`此时Student子类生成的实例，可以访问父类Human上定义的类属性、类方法和父类的实例属性、实例方法。
```python 
class Humman():
    sum = 0
    __hmval = 'humman class private val' #声明类的私有变量
    def __init__(self,country,name,age):
        self.country=country
        self.name=name
        self.age=age
        self.__huminst = 'humman instance private val' #声明实例的私有变量
    def getCountry(self):
        print(self.__huminst) #内部访问私有变量
        print(Humman.__hmval) #内部访问类的私有变量
        print(self.__class__._Humman__hmval) #内部访问类的私有变量

#声明子类，传入Humman父类继承父类
class Student(Humman):
    def __init__(self,country,score,name,age):
        super().__init__(country,name,age) #执行父类的构造函数，继承父类的实例化属性
        self.score=score #子类实例属性
    def get_score(self):
        print(self.__dict__)
        super().getCountry() #执行父类的方法


stu1 = Student('英国',60,'abc',20)
stu1.get_score()
#返回 {'country': '英国', 'name': 'abc', 'age': 20, '_Humman__huminst': 'humman instance private val', 'score': 60}
```


## oop思想
**封装、继承和多态** 是面向对象的三大特征。这三大特征与语言本身无关，这是一种面向对象的编程思想。

**封装** 是为了提高程序的安全性；将数据（属性）和行为（方法）包装到类对象中。而**在方法内部对属性进行操作**，**在类对象的外部调用方法**。这样我们只需要用合适的方式去用它，而不用关心方法是如何具体实现的。

**继承** 承是为了提高代码的复用性；继承就是定义子类，子类继承父类的属性和方法。一个类没有继承任何类，**默认继承object**；Python支持多继承。

**多态** 多态是为了提高程序的可扩展性和可维护性。Python中的多态指的是，在运行过程中根据变量所引用对象的类型，动态的决定调用哪个类对象中的方法。

**Object类是所有类的父类，一个类没有继承任何类，默认继承object**。

类的浅拷贝,Python拷贝一般都是浅拷贝，拷贝时，对象包含的子对象内容不拷贝，因此，源对象与拷贝对象会引用同一个子对象。浅拷贝是指创建一个新的对象，但**只复制了原对象的第一层内容（即引用类型的数据仅复制其引用地址）**
```python 
import copy
a2 = copy.copy(a1)
```
类的深拷贝,使用copy模块的deepcopy函数，递归拷贝对象中包含的子对象，源对象和拷贝对象所有的子对象也不相同。深拷贝是指创建一个新的对象，并递归地复制原对象的所有嵌套对象。
```python 
import copy
a3 = copy.deepcopy(a1)
```

## 异常处理
<b class="danger">try...except...finally</b>
出现异常后捕获异常，加以处理，不让程序终止并退出。常见的异常类型有：
Exception, Error, warning, error类型继承自Exception
```python 
try:
    pass #可能会出现错误的代码
except 异常类型 as e #e是异常变量
    pass #出现异常后的处理代码
finally:
    pass # try excpet代码块执行完之后，最终都会执行的代码块
```
except语句可指定异常类型，**如果不指定，则except语句捕获try语句中的所有异常，** 当指定具体异常时则except只捕获try中特定的异常。**多个异常类型的捕获可以放在一起。**

finally代码块中常用来释放资源，比如打开的文件、网络连接、打开数据库的连接、及数据结果集都会占用计算机资源，在finally中释放资源。

```python 
try:
    pass #可能会出现错误的代码
except 异常类型1 as e:
    pass
except 异常类型2 as e:
    pass
except (异常类型3,异常类型4) as e #多个异常类型相似可以合并
except Exception as e: #没有指定异常类型，默认捕获上面未捕获到的异常
    pass
finally:
    pass #正常流程或捕获错误的流程执行完之后，最终都会执行的代码
```
try...except 可以嵌套，但实际开发中尽量不要嵌套，应梳理好程序执行流程再考虑是否需要try...except嵌套

**traceback.print_exc()** 输出异常信息,查看堆栈跟踪信息
print(**str(e)**) 输出异常信息
**避免使用裸 except: 因为它会捕获包括 SystemExit 和 KeyboardInterrupt 在内的所有异常，可能导致程序无法正常退出。**

#### 自定义异常类，继承Exception类
```python 
class customException(Exception):
    def __init__(self,message):
        super().__init__(message)
```

#### 手动触发异常 raise
raise 触发自定义异常
```python 
raise customException('这是一个自定义的异常信息')
```






## 正则表达式 re模块
```python 
import re
```
#### 1. findall函数
re.findall('正则规则'，目标字符串) #查找出与匹配规则的结果，返回结果是list列表

##### 2. 元字符
re.findall(' <b class="danger">\d</b> ', a) #查找0-9的数字
\d、[0-9] #匹配0-9数字
‘\D’ 、[^0-9] #匹配0-9非数字
'\w'、'[A-Za-z0-9_]' #匹配单词字符，即数字和字母和下划线
''\W' #匹配非单词字符符号，包含空白字符符号比如空格，回车，制表符等
'\s' #匹配空白字符符号比如空格，回车，制表符
'\S' #匹配非空白字符
'[\s\S]*?' #匹配除所有字符
'.' #匹配除换行符\n之外的其他所有字符
‘a[**cf**]c’ #查找a开头，c结尾，中间是**c或f**的结果
‘a[**^cf**]c’ #查找a开头，c结尾，中间不是**c或f**的结果
‘a[**c-f**]c’ #查找a开头，c结尾，中间是**c到f**之间的结果

##### 3. 数量词
'[a-z]{3,6}' #匹配a-z之间的字符，最少匹配3位，最多匹配6位，贪婪模式匹配
'[a-z]{3,6}**?**' #匹配a-z之间的字符，最少匹配3位，最多匹配6位，**非贪婪模式**匹配3位即可
'pytho **\***' #匹配pytho**0次或无限多次**
'pytho **+**' #匹配pytho**1次或无限多次**
'pytho **?**' #匹配pytho**0次或1次**

##### 4. 边界匹配
'\^\d{3,8}\$' ^即字符串开始位置，$即字符串结束位置。数字开头，数字结尾，且长度在3-8位之间

##### 5. 组
r = re.findall('(Python){3}', s)
(Python){3} #将Python作为完整的一个分组，判断python是否重复3次
Python{3} #只判断Python中的单一字符n是否重复3次
小括号 **(abc)** 分组后，括号中的字符是且关系，中括号 **[abc]** 中的字符是或关系

##### 6. 匹配模式参数，findall的第三个参数
r = re.findall('正则规则', 目标字符串, re.I | re.S) # re.I即不区分大小写，re.S改变元字符 <b class="danger">.</b> 的匹配规则。多个模式用管道符连接，是且关系
r = re.findall('c#', 'PythonC#JavaPHP', re.I)
r = re.findall('c#<b class="danger">.{1}</b>', 'PythonC#<b class="danger">\n</b>JavaPHP', re.I | re.S) 
目标字符串里面有换行，元字符.是匹配除换行外所有字符，模式参数加上了re.S 就是改变元字符.的匹配特性，匹配包括换行符在内的所有字符。

##### 7. 正则替换，返回结果是字符串
r = re.sub('C#', 'GO', 'PythonC#JavaPHP',0) #第二个参数是要替换成的字符串，第4个参数count设置为0是不限制替换次数
第2个参数可以定义成函数，实现更复杂的需求，**比如第一个参数定义的匹配规则匹配出的是变量的时候**
```python 
def convert(value):
    mached = value.group() #value是匹配到正则结果的match对象
    return 'AA' + mached + 'AA'
r = re.sub('C#', convert, 'PythonC#JavaPHP', 0)
```
第1个参数匹配到之后会传入到convert函数中（convert函数中定义的value参数就是匹配上规则的一组match对象），返回函数执行的内容
示例
```python 
def fn(value):
    matched = value.group()
    if(int(matched)>=6):
    return '9' #这里必须返回字符串，因为正则只能操作字符串
    else:
    return '0'
re.sub('\d', fn, 'A8C3721D86', 0)
```
函数作为参数传入另一个函数，就是高阶函数

##### 7. re模块中的search,match函数
re模块中除了findall之外的其他两个函数search, match，，只匹配一次，**返回结果是match对象** r = re.match('\d', 'A83C7') #返回结果为None，因为match函数会从目标字符串的**首字母**开始匹配，如果首字母没匹配到就返回None

r = re.search('\d', 'A83C7') #search函数会搜索整个字符串，直到找到第一个匹配的结果就会**返回match对象**

##### 8. group()方法
match对象需要使用group()方法来获取具体的结果
r=re.search('life<b class="danger">(.\*)</b>python<b class="danger">(.\*)</b>python', 'life is short, i use python, i love python')
r.group(0) #获取所有分组匹配内容，即返回完整的匹配结果 'life is short, i use pyhon, i love python'
r.group(1) #获取第一个分组(.\*)匹配的内容，即'is short, i use '
r.group(2) #获取第二个分组(.\*)匹配的内容，即', i love'
r.group(0,1,2) #获取指定分组已元组形式返回  ('life is short, i use pyhon, i love python', 'is short, i use ',', i love')

##### 9. groups()方法
m = re.match(r"(\d+)\\.(\d+)", "24.1632")
m.groups() #返回('24','1632')




## JSON
JSON是轻量级的数据交换格式。JSON是数据格式，常见的数据格式还有XML数据格式。字符串是JSON的表现形式，符合JSON格式的字符串就是JSON。

python中JSON和 **字典** 格式一样，在 **JS中JSON和对象格式**一样，在每种语言中都有特定的数据格式与JSON对应从而实现转换。

#### JSON反序列化 
转换json格式字符串为JSON，必须是标准格式的JSON字符串`'{"name":"abc"}'`
python JSON 转字典
```python 
import json
ditc1 = json.loads(jsonStr) #将str格式的json字符串转成dict
```
<b class="asso">ES: JSON.parse(jsonString)</b>

数组JSON对象也能被反序列化为python中的list
`list1 = json.loads('[{"name":"a1"},{"name2":"a2"}]') `
<b class="danger">这里一定得是字符串格式的list，且list内的每个成员是字符串的JSON格式</b> 

```python 
import json
list1 = json.loads('[{"name":"a1"},{"name2":"a2"}]') #字符串格式list转成list
print(list1) #返回list格式
print(type(list1)) #list

list1Str = json.dumps(list1) #将list格式转成字符串格式list
print(list1Str) #返回字符串格式list
print(type(list1Str)) #字符串

abc = json.loads('[{"a":1,"b":2},{"c":3}]')
print(abc) #返回list [{'a': 1, 'b': 2}, {'c': 3}]
```

<b class="asso">ES: JS中也能将字符串格式数组对象转成数组对象，JSON.parse(jsonString)</b>

JSON数据类型与python数据类型
![json_python](./img/json_python.jpg)

#### JSON序列化
将JSON数据格式转成JSON格式字符串
```python 
import json
jsonStr = json.dumps(jsonObject)
```
<b class="asso">ES: JSON.stringify(jsonObject)</b>
JSON：一种通用的数据交换格式，支持各种语言。在每种编程语言中都有特定的数据类型和JSON格式可以转换。
JSON字符串：符合标准JSON语法格式的字符串
JSON对象：只在JS语言中存在JSON对象，在python中是dict，或list dict


## 枚举
枚举（enum）是一种特殊的类，通过enum模块提供，主要用于定义**一组命名的常量集合**，每个枚举成员都有一个**唯一**的**名称**和**关联值**

<b class="danger">Enum 强制输入值必须是预定义的成员，避免非法值的使用。Enum 还可以集中定义了所有值，便于后期统一管理和修改。</b>


枚举其实是一个类，枚举不可实例化。**枚举就是列举出有穷集合的所有元素，枚举的成员** <b class="danger">不可修改</b> ，且枚举类型中 <b class="danger">没有重复成员名称name</b>，**但成员名称对应的值可以相同，后面相同值对应成员名称name相当**<b class="danger">于是别名</b>

常规的class类、dict类型中定义的属性或变量可以被修改，且类中定义的属性存在相同值的可能，无法确认属性的唯一性。
```python 
class TypeDiamond():
    yellow = 1 # 无法确认属性的唯一性
    red = 2
    green = 1 # 无法确认属性的唯一性
```
`abc = {'yellow':1,'red':2, 'green':1}`
以上方法定义的属性或变量可被修改，且存在值相同的变量，无法区分唯一性。

```python 
from enum import Enum
class VIP(Enum):
    YELLOW=1
    GREEN=2
    abc=2 #因为枚举值相等，所以后面的abc相当于是前面GREEN的别名
```
`VIP.YELLOW =2` 会提示报错，因为枚举类型不能修改
`VIP.YELLOW` VIP.YELLOW 获取的是一个枚举类型即`<enum 'VIP'>`，不是具体的值
`VIP.YELLOW.value` 取枚举类型中标签对应的枚举
`VIP.YELLOW.name` 获取枚举类型中枚举名称
**abc相当于是GREEN的别名，abc的值与GREEN的值相同**

#### 遍历枚举
```python 
for v in VIP:
    print(v) #返回VIP类中的所有的枚举类型
```
**枚举的运算比较**，**枚举类型之间**只能判断**是否相等**(===)，**是否同一身份**(is)
`VIP.YELLOW == VIP.YELLOW` 返回True
`VIP.YELLOW == VIP.GREEN` 返回False
`VIP.YELLOW == 1` 会返回False，不是枚举类型之间比较
`VIP.YELLOW is VIP.GREEN` 返回True

#### 枚举转换
当已知某个值，要根据该值匹配出某个枚举类型中的成员
```python 
a=1
VPI(a) #返回VIP.YELLOW枚举类型
```


#### 使用枚举代替数字来进行分类
如果项目中需要通过不同的数字来判断不同的类别，可以使用枚举类型来表示这些数字，可以将数字转换成相应的枚举成员来处理。例如邮箱，手机，微信小程序，微信公众号这几类注册方式，用户请求传过来的数字在后端处理的时候，总不能直接使用100，101这样的数字来区分不同的注册方式。
```python 
from enum import Enum
class ClientTypeEnum(Enum): #继承枚举类型
    USER_EMAIL=100
    USER_PHONE=101
    USER_MINA=200
    USER_WX=201
```


## 闭包
<b class="danger">函数及函数声明时所在的环境变量的集合叫闭包。</b>
**可在函数外部调用函数内部的局部变量。闭包可以保存函数的环境变量，避免函数执行后环境变量被垃圾回收。**
查看某个函数的闭包使用 <b class="danger">.\_\_closure\_\_[0].cell_contents</b>
```python 
def curve_pre():
    a = 25
    def fn():
        return a + 5
    return fn

f = curve_pre()
f.__closure__[0].cell_contents
```

```python 
def save_steps(x):
    origin = x
    def walk_step(step):
        nonlocal origin #nonlocal 声明引用的是外层函数的局部变量
        origin += step #如果不使用nonlocal显示声明，此行修改变量会提示变量不存在的错误

        print(origin)
        return origin
    return walk_step

fn = save_steps(0)
fn(2)
print(fn.__closure__[0].cell_contents)
fn(6)
print(fn.__closure__[0].cell_contents)
fn(12)
print(fn.__closure__[0].cell_contents)
```
**需要修改闭包局部变量时，首先要使用nonlocal显示声明变量不是内层函数的局部变量**，否则会提示变量不存在错误

## Lambda 表达式 匿名函数 
lambda表达式定义匿名函数 ``lambda parament_list: expression``,**lambda表达式后面只能是 <b class="danger">一个简单的表达式</b> ，不能是复杂的代码块，lambda表达式不需要使用return**。通常lambda表达式是一行的匿名函数，但也可以通过反斜杠和括号来实现换行。
```python 
#定义普通函数
def add(x,y):
    return x+y

#lambda表达式定义匿名函数
lambda x,y: x + y
#匿名函数的调用
f = lambda x,y: x+ y
f(1,2)

(lambda x,y:x+y)(1,2)
```

<b class="asso">ES: JS匿名函数</b>
```js
(function(x,y){
    return x+ y 
})(1,2)

(x,y)=> x+ y
```

## 三元表达式
**条件为真时返回的结果x  if 条件判断 else条件为假时返回的结果y**
`resunt = x if(expression) else y` 返回x时必须满足expression中的条件，否则返回y
`value_true if condition else value_false`

<b class="asso">ES: JS三元表达式</b>
`(expression)?x:y`


## 函数式编程
函数式编程 属于声明式编程中的一种，它的主要思想是**将计算机运算看作为函数的计算**，也就是**把程序问题抽象成数学问题**去解决。函数式编程中，我们可以充分利用数学公式来解决问题。也就是说，任何问题都可以通过函数（加减乘除）和数学定律（交换律、结合律等），一步一步计算，最终得到答案

#### map函数
**map函数返回的是map类**，结果使用 <b class="danger">list(</b>map_x<b class="danger">)</b>  转成列表
**map函数把要遍历的目标对象逐一传入前面的函数中进行处理**,返回一个map类
```python 
list_x = [1,2,3,4,5,6,7,8]
list_y = [1,2,3,4,5,6]

def square(x):
    return x * x

#方法一 for...in循环
for x in list_x:
    square(x)

#方法二 map函数遍历
r = map(square,list_x)
#返回结果[1，4，9，16，25，36，49，64]

#使用lambda表达式定义匿名函数,简化代码
r1 = map(lambda x: x*x, list_x)
print(list(r1))
#返回 [1, 4, 9, 16, 25, 36, 49, 64]

#使用lambda表达式定义匿名函数，简化代码
r2 = map(lambda x,y:x*x +y, list_x,list_y) #这里传入的是两个list参数
#返回 [2, 6, 12, 20, 30, 42]
```

#### filter函数
**返回一个过滤后的集合**，结果使用 <b class="danger">list(</b>fliter_x<b class="danger">)</b>  转成列表
```python 
list_x = [1,0,1,1,0,1,0]
r = filter(lambda x: True if x > 0 else False, list_x)
print(list(r))
#返回[1,1,1,1]
```
<b class="danger">filter函数中的lambda表达式的返回值必须为布尔值或者0，1类布尔值，</b>即必须是能表示真假的值


#### reduce函数
**每次的计算结果作为下一次计算的参数**
```python 
from functools import reduce
list_x = [1,2,3,4,5,6,7,8]
r = reduce(lambda x,y:x+y, list_x, 10)
```
**reduce函数的第三个参数10是初始值**



## 装饰器
当需求变更之后，不可避免要修改代码，修改代码尽量遵循原则（对修改是封闭的，对扩展是开放的），不要修改函数和对象的定义，**应该通过扩展一个函数，或者扩展一个类来解决需求变更的问题**。 为一个函数增加功能，而不修改原有函数的代码,不改变原有函数的基础上，增加新的功能。

开闭原则 <b class="success">对修改是封闭的，对扩展是开放的</b>

装饰器的使用场景
1. 当需要对某一个封装的单元比如某个函数做出修改，可以在不修改原有函数的基础上使用装饰器的形式扩展原有函数的功能进而达到间接修改原有函数
2. 需要复用某个函数的功能

```python 
import time

def decorator(func):
    def wrapper(): #定义扩展原函数的代码
        print(time.time())
        func()
    return wrapper #返回扩展函数

def f1():
    print('This is a function')

f = decorator(f1)
f()

#使用装饰器语法糖简化以上调用
@decorator
def f1():
    print('This is a function')
f1() #直接执行f1()函数，不用像上面代码一样改变调用函数的调用方式 f = decorator(f1) f()
```

<b class="danger">python装饰器的语法糖 @符号</b> 
@符号语法糖，不改变原有函数，增加新功能，代码没有改变f1的内容，调用时直接调用f1()

**使用装饰器语法糖后可以直接执行f1()函数，不用像上面代码一样改变函数的调用方式** 
`f = decorator(f1)` 
`f()`


#### 单函数参数场景的装饰器函数
```python 
import time

def decorator(fn):
    def wrapper(fn_name):
        print(time.time())
        fn(fn_name)
    return wrapper

@decorator
def f1(fn_name):
    print(f'this is a function named {fn_name}')

f1('test_name') #调用经过装饰的函数
#返回以下内容
# 1709539265.6746893
# this is a function named test_name
```


#### 多个函数参数场景的装饰器函数
```python 
import time

def decorator(fn):
    def wrapper(*args):
        print(time.time())
        fn(*args)
    return wrapper

@decorator
def f2(fn_name1,fn_name2):
    print(f'this is a function named {fn_name1}')
    print(f'this is a function named {fn_name2}')
f2('test1','test2')

#返回以下内容
# 1709539505.1007066
#this is a function named test1
# this is a function named test2
```

#### 多个函数参数，可变关键字参数的装饰器函数
```python 
import time

def decorator(fn):
    def wrapper(*args,**kw):
        print(time.time())
        fn(*args,**kw)
    return wrapper

@decorator
def f3(*args,**kw):
    print(f'this is a function named {args[0]}')
    print(f'this is a function named {args[1]}')
    print(kw)

f3('test1','test2',a=1,b=2,c=3)

#返回如下
# 1709541640.6559663
# this is a function named test1
# this is a function named test2
# {'a': 1, 'b': 2, 'c': 3}
```
**\*args 收敛可变参数, \*\*kw收敛关键字参数**

#### 装饰器的副作用
使用装饰器后原有**函数的名称会改变为wrapper**，**函数**内的 \_\_doc\_\_ **说明文档会改变**。
解决增加装饰器后函数名称改变的方法：
```python 
import time
from functools import wraps
def my_decorator(func):
    @wraps(func) #包裹原函数，其他不变
    def wrapper(*args, **kw):
        print(time.time())
        func(*args, **kw)
    return wrapper

@my_decorator
def f4():
    """this is f4 doc"""
    print("is f4")

f4() #返回内容如下
# 1709543999.348059
# is f4

print(f4.__name__) #返回f4
help(f4) #返回f4函数的说明文档 this is f4 doc
```
f4.\_\_name\_\_ 函数的名称仍然是f4,
f4.\_\_doc\_\_ 函数的注释还是原函数的注释


## with as 语法
with...as 语句是上下文管理器的语法糖，用于资源管理。主要目的是确保资源在使用后被正确释放，即使代码块发生了异常也能被关闭，**避免忘记释放资源的问题。**
```python
with expression as variable:
    # 代码块
```

expression 返回一个**上下文管理器对象**，调用上下文管理器的__enter__()方法，将__enter__()的返回值赋值给as后面的变量。执行代码块，无论代码块是否发生异常，都会调用__exit__()方法。
常见的使用场景
1. 文件操作（自动关闭文件）
```python
with open('file.txt','r') as f:
    content = f.read()
```
2. 数据库链接（自动关闭连接）
```python
with psycopg2.connect(database='test') as conn:
    with conn.cursor() as cursor:
        cursor.execute('select * from users')
```


## python编程技巧
#### 1. 使用<b class="danger">表驱动编程</b>，替代match
```python 
def get_sunday:
    return 'Sunday'
def get_monday:
    return 'Monday'
def get_tuesday:
    return 'Tuesday'
def get_default:
    return 'Unknow'
dicts = {
    0:get_sunday,
    1:get_monday,
    2:get_tuesday
}
day_num = 2
dicts.get(day_num,get_default)()
# 当获取不到指定day_num所对应的值时，默认返回get_default方法
```

#### 2. 列表推导式
根据已经存在的列表创建一个新的列表。
```python 
a = [1, 3, 5, 7, 9]
b = [i for i in a] #返回一个新的列表
b1 = [i**2 for i in a] #返回a列表每个元素的平方，生成新的列表

# 条件筛选列表推导式
c = [i**2 for i in a if i>=5] #筛选出原列表中大于等于5的元素的平方，生成新的列表

# 在列表推导式中调用函数
def to_upper(s):
    return s.upper()
strings = ['hello', 'world', 'python']
upper_strings = [to_upper(s) for s in strings]

# 在列表推导式中使用lambda函数，需显式地赋值给变量
a2 = [(lambda x=i:x.upper())() for i in ['hello', 'world', 'python']] # x=i 表示将列表中的元素依次赋值给x，然后对x进行操作


# 多重迭代，从多个可迭代对象生成列表
list1 = [1, 2, 3]
list2 = ['a', 'b']
combinations = [(x, y) for x in list1 for y in list2]
print(combinations)  # 输出: [(1, 'a'), (1, 'b'), (2, 'a'), (2, 'b'), (3, 'a'), (3, 'b')]

# 嵌套列表推导式
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
new_matrix = [[x + 1 for x in row] for row in matrix]
print(new_matrix)  # 输出: [[2, 3, 4], [5, 6, 7], [8, 9, 10]]

# 带条件的多重迭代
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
combinations = [(x, y) for x in list1 for y in list2 if x != 2 or y != 'b']
print(combinations)  # 输出: [(1, 'a'), (1, 'b'), (1, 'c'), (2, 'a'), (2, 'c'), (3, 'a'), (3, 'b'), (3, 'c')]


```
**列表、元组、集合都可以被推导**
```python 
a = {1,2,3,4,5,6,7,8} #集合
bb = (1,2,3,4,5,6,7,8) #元组
cc = [1,2,3,4,5,6,7,8] #列表

a1 = [i**2 for i in a] #集合推导出列表
a2 = {i**2 for i in a} #集合推导出集合
a3 = [i**2 for i in bb] #元组推导出列表
a4 = {i**2 for i in cc} #列表推导出集合
```

**字典推导出列表**
```python 
students = {
    'name1': 18,
    'name2': 22,
    'name3': 24
}
#将原字典的key提取推导出新的列表
b = [key for key,value in students.items()]
print(b)
#返回 ['name1', 'name2', 'name3']

#将原字典的key,value提取推导出新的字典
c = {key:value for key,value in students.items()}
print(c)
#返回 {'name1': 18, 'name2': 22, 'name3': 24}
```


#### 3. None 判空操作 
None的类型是 **NoneType** ,表示此处有值但为空
<b class="asso">ES: null</b>
<b class="danger">判空操作</b> `if a:`, `if not a:`
```python 
a = None
a = ''
a = []
a = False
#以上几种类型 都可以使用 if a, if not a 来判断控制
```

<b class="danger">对象存在，但并不一定是True</b>
class类在做**真假值判断**的时候，会调用 **bool()** 方法将类转换成bool类型，class类其内部定义的`__bool__(self)`,`__len__(self)`方法会作为判断的依据。当__bool__和__len__同时存在时，优先调用__bool__

```python 
class Test():
    def __bool__(self):
        return False  #只能 return True/False
    def __len__(self):
        return 0 #能return False/True/0/1

#基于以上代码
bool(test()) #返回False  因为有内部定义的__bool__(self)方法

if Test():
    print('T')
else:
    print('F')
#这里打印F，因为Test()返回的是False，所以执行的是else:语句
```

#### 4. 海象运算符 :=
对一个表达式求值，或对一个函数的调用求值，求值后在一行代码中对一个变量赋值。<b class="danger">顺便声明一个由表达式计算结果（或函数求值结果）赋值的变量</b>
`(variable_name := expression or value)`
**海象运算符，避免表达式多次求值， 提高了性能**
`b = len('abc')` 如果要多次引用`len('abc')`表达式计算的结果，可以使用海象表达式简化代码

```python 
b := len('abc')
```
```python 
a = 1 + 2
if a>0:
    print('Y')

#使用海象运算符改写
if (a:= 1+2)>0:
    print('Y')
# 打印Y
```

```python 
def abc():
    return 1

if (a := abc()) > 0:
    print('Y')
# 打印Y
```

#### 5. @dataclass 装饰器简化构造函数
```python 
from dataclasses import dataclass

@dataclass
class Student():
    #以下为语法糖
    name:str 
    age:int
    school_name:str

    # def __init__(self,name,age,school_name):
    #     self.name=name
    #     self.age=age
    #     self.school_name=school_name

    def fn(self):
        print(self.name)

stu1 = Student('tiger',18,'sanxia')
stu1.fn()
#返回 tiger

print(stu1.__repr__())
#返回 Student(name='tiger', age=18, school_name='sanxia')
```
**当使用@dataclass装饰器，会自动生成以上代码中注释掉的构造函数这部分代码,所以可以不写构造函数执行过程**

`@dataclass(init=True,repr=True)` init参数默认True,repr默认参数True

`__repr__()`是一个内置函数，用于获取对象的“官方”字符串表示形式。这个“官方”表示形式通常可以通过  eval()  函数重新创建对象
因此  repr()  返回的字符串应该是有效的 Python 表达式。

```python 
@dataclass(init=False, repr=False) #关闭构造函数, 关闭repr
class Student(): 
    name:str
    age:int
    school_name:str

stu1 = Student('tiger',18,'sanxia') #这里会报错，因为上面已经关闭了构造函数
```


#### 6. 迭代器 iterator
**可迭代对象iterable** 凡是可以被for...in循环遍历的对象就是可迭代对象。比如列表、元组、集合都具有可迭代接口。

**迭代器iterator即迭代接口**,是一个可迭代的对象。<b class="danger">但可迭代对象(列表、元组、集合)不一定是迭代器。</b>

自定义部署迭代器需要自定义两个方法`__iter__` `__next__` 迭代器**可以使用next**函数控制**迭代过程**。<b class="danger">迭代器是一次性的</b>,第一次遍历完毕后就无法再遍历了。**可迭代对象是可以多次遍历的，而且没有next()方法控制迭代过程**
使用自定义部署迭代器，实现一个可迭代的class类
```python 
class BookCollection:
    def __init__(self):
        self.data = ['往事','只能','回味']
        self.curs = 0 #定义游标，控制next()方法进度
    def __iter__(self):
        return self
    def __next__(self):
        if self.curs >= len(self.data): #迭代完成
            raise StopIteration() #迭代完成，如果游标值超过data列表长度即数据已全部遍历则抛出终止迭代的异常
        result = self.data[self.curs]
        self.curs += 1
        return result

book = BookCollection()

#遍历迭代器使用for in 循环
for i in book:
    print(i)
# 返回如下内容
# 往事
# 只能
# 回味

#使用next()方法控制迭代过程
print(book.next())
print(book.next())
print(book.next())
```
<b class="danger">raise StopIteration()</b>遍历结束，手动终止迭代遍历


#### 7. 生成器 generator
生成器是一种特殊的函数，它使用**yield**语句来产生值，可以按需生成值，而不是一次性生成所有值。生成器适用的场景：
1. **处理大量数据**：当需要处理大量数据或无限序列时，生成器可以逐个生成值，而不需要一次性将所有数据加载到内存中。 
 
2. **节省内存**：生成器是惰性计算的，只在需要时生成值，可以节省内存空间。 
 
3. **迭代操作**：在需要对序列进行迭代操作时，使用生成器可以简化代码并提高效率。 
 
4. **处理无限序列**：生成器可以用于表示无限序列，如斐波那契数列等。 
5. **异步编程**: 生成器可以与协程一起使用，用于异步编程，处理并发任务。
```python 
n = [i for i in range(0,10001)]

#一次性将长列表写入内存中然后遍历，效率不高
# for i in n:
#     print(i)

# 使用生成器处理大量数据
def gen(max):
    n = 0
    while n<=max:
        n+=1
        yield n #不是return一个值，而是yield一个值

g = gen(10000)

print(next(g))
print(next(g))
print(next(g))
# 以上代码返回 1,2,3

print(g)
# 打印出生成器


#生成器可以迭代
for i in g:
    print(i) #打印出所有数字
    # print(next(g))
```

**yield**关键字，不同于return，函数执行到return返回函数运行结果后就终止了，函数执行到yield返回yield后的值，但函数不会终止，可以通过next(generator)方法继续执行生成器函数


## python异步编程
1. 同步(synchronous) 代码按顺序逐行执行,前一个操作完之后才能执行下一个，会阻塞后续代码执行。
2. 异步(Asynchronous)操作发起后立即继续执行后续代码，不等待当前操作完成，通过回调，promise，async/await处理结果。
3. 串行(serial)任务按顺序一个接一个执行，前一个任务完成才开始下一个，总执行时间是各任务时间之和。
4. 并行(parallel)多个任务同事在不同cpu核心/线程执行，需要多核/多线程支持，显著减少执行时间。
5. 并发(concurrent)，多个任务**交替执行**（单核上），通过时间片轮转实现“同时”执行的假象，不需要多核心硬件。

**并行是真正的物理同时执行**
**并发是逻辑上的同时执行**
**异步是一种编程模式，可用语实现高并发**

<b class="success">异步函数即协程</b> 
协程**coroutine**是一种比线程更轻量的**用户态**并发执行单元，可以理解为协作式多任务处理的基本单位。它允许在函数执行过程中，在任意位置暂停（suspend）执行，并在之后恢复（resume）执行，保持其状态不变。<b class="info">协程是协作式多任务的基本单位。任务是事件循环调度的最小单位。</b> 
<b class="danger">暂停当前协程的执行，交出控制权给事件循环.</b>

- async语法将fn函数由普通函数变成异步函数**coroutine function**，当调用这个协程function时，不会执行函数内定义的代码和返回定义的返回值，而是返回一个**coroutine对象**（协程对象）
```python
async def fn():
    await print('test')
``` 


<b class="success">1. 正确执行协程即异步函数coroutine function的方法</b>
- 方法1：**使用await** 在另一个coroutine function 中
```python
async def fn1():
    print('fn1 function')

async def main():
    await fn1() # 正确地等待协程执行，直接await一个协程对象
    await asyncio.create_task(my_coroutine()) # 等待任务执行完毕

import asyncio
asyncio.run(main())
```

- 方法2： **使用asyncio.run()**
```python
async def fn1():
    print('fn1 function')

import asyncio
asyncio.run(fn1())
```


<b class="success">2. asyncio的常用方法</b>

asyncio 是 Python 官方提供的异步 I/O 标准库，用于编写并发程序（如网络请求、并发任务、异步 IO 等）。
```python
asyncio.run(coro, *, debug=False) #启动并运行一个协程，自动管理事件循环
asyncio.get_event_loop() #获取当前事件循环（不推荐在 3.7+ 中直接使用）

asyncio.create_task(coro) #创建一个任务并调度执行（推荐方式）
await asyncio.gather(*tasks) #并发执行多个协程或任务，并等待全部完成
asyncio.wait_for(coro, timeout) #设置协程的超时时间
asyncio.shield(coro) #防止协程被取消（取消操作会等待其完成）

await asyncio.sleep(delay) #异步睡眠（不会阻塞事件循环）
asyncio.as_completed(coros, timeout=None) #按实际的完成顺序返回结果，而不是gather中的启动顺序
asyncio.wait(coros, return_when=ALL_COMPLETED) #控制等待条件（如任一完成、全部完成等）

```



<b class="success">3. asyncio 中的 协程，任务，事件循环的概念</b>

协程**coroutine**
协程是一种可暂停执行的函数，它可以在执行过程中**暂停（yield）**，稍后再**恢复（resume）**，并且在**暂停期间不会阻塞整个程序**。使用 async def 定义的函数就是一个协程函数，调用它会返回一个协程对象（coroutine object）

任务**task**
任务是**对协程的封装**，它是一个 asyncio.Task 实例，用于**调度协程的执行**。将协程提交给事件循环进行调度。
<b class="info">协程是协作式多任务的基本单位。任务是事件循环调度的最小单位。</b> 

使用 **await coro** 协程对象更加直接，适用于简单的等待操作。
**await task 这种方式更灵活，能利用任务提供更多的控制选项，如取消任务或添加回调。**
task的常用方法：
```python
task.done() # 判断任务是否已完成
task.result() # 获取任务的结果
task.cancel() # 取消任务
task.cancelled() # 检查任务是否已被取消
task.exception() # 获取任务抛出的异常
task.add_done_callback(callback) # 添加一个回调函数，在任务完成时调用。回调函数会被传递一个任务实例作为参数。
task.remove_done_callback(callback) 移除任务的指定回调函数
```


事件循环**event loop**
事件循环是异步程序的核心**调度器**，调度协程/任务的执行。协调所有异步操作的执行顺序。



<b class="success">4. 创建异步任务列表的示例</b>

- 创建单个异步任务（协程对象），将协程对象封装成列表。 **asyncio.creat_task(asy_fn)**
`works = [asyncio.creat_task(fn(1)), asyncio.creat_task(fn(2))]`
- 对异步任务指定回调函数
`works[0].add_done_callback(task1_callbackfn)`
- main函数封装，将异步任务整合到代码逻辑里面  
   **await asyncio.gather(\*works) 获取返回值列表(gather即收集的意思)**
   **await asyncio.create_task(asyn_fn_name())** 获取单个异步函数（协程函数）返回值
```python
async def main():
    response = await asyncio.gather(*works) # 获取异步函数（协程）的返回值，参数序列传入
```
- 执行异步任务（协程） **asyncio.run()**
`asyncio.run(main())`


模拟io事件`await asyncio.sleep(1)` 在**async函数中，不能使用time.sleep() 方法**




#### python中await的理解
**await是一个显式的，强制性的挂起点**，它直接告诉事件循环：“我现在要等这个异步操作完成，你可以去干别的活了”。协程的执行流在 await 处清晰可见地被中断，并在操作完成后恢复。



协程对象是协作式多任务的基本单位，async def函数被调用后返回协程对象，但它不会自动运行。 必须通过以下方式之一驱动：

- 在另一个协程内 await 它（会等待它完成）。
- 作为主入口点传递给 asyncio.run()。
- 包装成 Task (asyncio.create_task()) 并发执行。create_task 是并发启动协程的关键。




## 深入理解python协程和事件循环
在 Python 的异步编程中，“暂停当前协程的执行，交出控制权给事件循环” 是一个非常核心的概念。当一个协程执行到 await 某个 coroutine（比如 await asyncio.sleep(1)）时，这个 await 会暂停当前协程的执行，然后把控制权交还给事件循环，让事件循环去执行其他协程或任务。有点像，<b class="info">我现在要等一会儿，你（事件循环）先去干别的事，等我准备好了再叫我。</b>

```python
async def my_coroutine():
    print("Start")
    await fn()     # <-- 这里暂停当前协程，直到 fn() 完成
    print("End")
```
代码执行过程分析
1. 当 my_coroutine() 执行到 await fn() 时，它会暂停自己，把控制权交还给事件循环。
2. 事件循环就可以去执行其他协程、任务等。
3. 等 fn() 完成后，事件循环会唤醒 my_coroutine()，继续执行后面的代码。

**await 的作用是：**
1. 等待某个异步操作完成（比如 IO、网络请求、定时器等）。
2. 在等待期间，当前协程不占用 CPU，不阻塞主线程，而是让事件循环去调度其他任务。

### python和javascript中await的对比
JavaScript 的 await 等待的是 Promise，Python 的 await 等待的是 coroutine、Task、Future。
Python 的 await 是基于协程和事件循环的协作式异步模型，强调任务调度；而 JavaScript 的 await 是基于 Promise 的异步语法糖，强调链式调用和回调处理。

|对比项|Python 中的 await|JavaScript 中的 await|
|--|--|--|
|底层机制|	基于 协程（coroutine） 和 事件循环（event loop）。|	基于 Promise 和 事件循环（event loop）。|
|执行模型|	协作式多任务（cooperative multitasking）：只有遇到 await 时才会让出控制权。|	基于 Promise 的链式调用，await 只是语法糖，底层还是 Promise。|
|await 的对象|	必须是 awaitable：coroutine、Task、Future。	|必须是 Promise（也可以是普通值，会自动包装成 resolved Promise）。|
|事件循环管理|	Python 需要显式启动事件循环（如 asyncio.run()）。	|JS 的事件循环由运行时（如 Node.js、浏览器）自动管理。|
|并发性|	使用 asyncio.create_task() 可以并发运行多个协程。	|使用 Promise.all()、Promise.race() 等实现并发。|
|线程支持|	asyncio 默认是单线程的，但可以通过 loop.run_in_executor() 调用线程/进程。|	JS 是单线程的，但可以通过 Web Worker 实现多线程（浏览器端）。|
|错误处理|	使用 try/except 捕获异常。	|使用 try/catch 捕获异常。|
|返回值|	await 表达式的返回值就是协程的返回值。	|await 表达式的返回值是 Promise 的 resolve 值。|
|是否可以脱离 async 函数使用|	❌ 不可以。await 只能在 async def 函数中使用。	|❌ 不可以。await 只能在 async function 中使用（但可以在 top-level module 中使用）。|
|核心思想|更偏向 协程模型，强调协程之间的协作调度。强调显式控制事件循环（如 asyncio.run()）。更适合系统级并发（如网络服务器、爬虫等）。|更偏向 Promise 模型，强调链式调用和回调机制。事件循环由运行时自动管理，开发者几乎不接触。更适合前端异步交互（如 API 请求、DOM 操作等）。|

### javascript中的async await 
async/await 是语法糖： async 函数本质上返回一个 Promise。await 表达式会暂停 async 函数的执行，等待其后的 Promise 解决。当 Promise 解决后，其回调（即 await 之后的代码）被放入微任务队列，等待当前宏任务执行完后被调度执行。其回调机制，无论是早期的回调函数还是现代的 Promise/async/await，底层都依赖于将回调函数放入队列等待事件循环调度。

await 主要用来等待 Promise 解决。控制权转移和回调入队是引擎在解析 Promise 链时隐式处理的。开发者主要关注 Promise 的状态流转。

### python 中的async await 
协程 (Coroutine)： 这是 Python 异步编程的核心抽象，比 JS 的回调更高级。 一种特殊的可挂起 (suspendable) 和 可恢复 (resumable) 的函数。它不是进程或线程，是用户态轻量级“线程”。await： 关键操作符，显式地 在协程内部标记一个“挂起点”，当协程执行到 await 表达式时，它会挂起自身的执行，事件循环就会接管控制权，去执行其他就绪的任务。当 await 等待的操作完成（如 I/O 就绪、定时器到期、其他协程返回结果），事件循环会在合适的时机（通常是下次轮询时）恢复该协程的执行，从 await 之后继续运行，并传入结果。

await 是一个显式的、强制性的挂起点。它直接告诉事件循环：“我现在要等这个异步操作完成，你可以去干别的活了”。协程的执行流在 await 处清晰可见地被中断，并在操作完成后恢复。这使异步代码的逻辑更接近同步代码的线性思维，可读性通常更高。理解协程的关键就是理解 await 如何标记挂起点。


## asyncio 库的使用
Python 3.5及以上版本引入了asyncio库，支持异步编程和async/await语法。Python 示例假设我们有一个类似的场景，包括两个异步操作：从网络获取数据和写入文件。我们将使用asyncio库来实现这两个操作，并观察它们是如何并发执行的。
```python
import asyncio
import time

# 模拟网络请求的异步函数
async def fetch_data(url):
    print(f"开始从 {url} 获取数据")
    await asyncio.sleep(2)  # 模拟2秒的网络延迟
    print(f"数据获取完成: 来自 {url}")
    return f"数据来自 {url}"

# 模拟写入文件的异步函数
async def write_file(data):
    print("开始写入文件")
    await asyncio.sleep(1)  # 模拟1秒的文件写入时间
    print(f"文件已写入: {data}")

# 定义一个异步函数来处理这两个操作
async def process_tasks():
    print("开始处理任务")

    # 任务1：从网络获取数据
    data = await fetch_data('https://api.example.com/data')

    # 任务2：写入文件
    await write_file(data)

# 在主程序中模拟其他任务
async def main():
    task = asyncio.create_task(process_tasks())  # 创建一个任务

    print("主程序继续运行")
    await asyncio.sleep(0.5)  # 模拟其他任务
    print("其他任务1完成")
    await asyncio.sleep(1)  # 模拟其他任务
    print("其他任务2完成")

    await task  # 等待process_tasks任务完成

# 运行主程序
asyncio.run(main())
```

输出结果运行上述代码，你将看到以下输出顺序：开始处理任务
主程序继续运行
开始从 https://api.example.com/data 获取数据
其他任务1完成
其他任务2完成
数据获取完成: 来自 https://api.example.com/data
开始写入文件
文件已写入: 数据来自 https://api.example.com/data

**解释:**
1. 开始处理任务：首先，process_tasks协程被创建并开始执行，输出“开始处理任务”。
2. 主程序继续运行：由于await fetch_data('https://api.example.com/data')会暂停process_tasks协程的执行，但不会阻塞事件循环，因此主程序中的print("主程序继续运行")会立即执行。
3. 其他任务1完成：0.5秒后，输出“其他任务1完成”。
4. 其他任务2完成：1秒后，输出“其他任务2完成”。
5. 数据获取完成：2秒后，fetch_data的await asyncio.sleep(2)完成，process_tasks协程继续执行，输出“数据获取完成: 来自 https://api.example.com/data”。
6. 开始写入文件：紧接着，write_file协程开始执行，输出“开始写入文件”。
7. 文件已写入：1秒后，write_file的await asyncio.sleep(1)完成，输出“文件已写入: 数据来自 https://api.example.com/data”。

**关键点:**
•暂停执行：在await fetch_data('https://api.example.com/data')处，process_tasks协程会暂停执行，等待fetch_data的异步操作完成。在这段时间内，事件循环可以继续处理其他任务。
•并发执行：由于await表达式不会阻塞事件循环，其他任务（如asyncio.sleep回调）可以继续运行，从而实现并发执行。
通过这种方式，async/await使得异步代码更加简洁和高效，同时保持了良好的并发性能。希望这个解释和示例能帮助你更好地理解“当前的async函数会暂停执行，允许其他任务继续运行”的含义。如果有更多问题，欢迎继续提问。内容由AI生成
已记录

#### asyncio函数的使用举例
asyncio 是 Python 的一个标准库，用于编写异步程序。它允许你编写并发代码，使用协程、任务和事件循环来处理 I/O 操作和其他阻塞操作，而不会阻塞主线程。
1. 协程 (Coroutine)：
- 协程是一种特殊的函数，可以暂停和恢复执行。在 Python 中，协程使用 async def 定义。
- 协程对象不能直接运行，需要通过事件循环或 await 表达式来执行。
2. 事件循环 (Event Loop)：
- 事件循环是 asyncio 的核心，负责管理和调度协程的执行。
- 你可以使用 asyncio.run() 或 loop.run_until_complete() 来启动事件循环。
3. 任务 (Task)：
- 任务是协程的一个封装，用于在事件循环中调度和执行。
- 你可以使用 asyncio.create_task() 创建任务。
4. Future：
- Future 是一个特殊的低层级可等待对象，表示一个异步操作的最终结果。
- 任务实际上是 Future 的子类。
5. Awaitable：
- 可等待对象是可以用在 await 表达式中的对象，包括协程、任务和 Future。
```python
import asyncio

# 定义一个协程
async def say_after(delay, what):
    await asyncio.sleep(delay)  # 模拟异步I/O操作
    print(what)

# 定义一个主协程
async def main():
    print(f"started at {time.strftime('%X')}")

    # 创建两个任务
    task1 = asyncio.create_task(say_after(1, 'hello')) #将任务1推入任务队列
    task2 = asyncio.create_task(say_after(2, 'world')) #将任务2推入任务队列

    # 等待两个任务完成
    await task1 #等待任务1完成
    await task2 #等待任务2完成

    print(f"finished at {time.strftime('%X')}")

# 启动事件循环
import time
start_time = time.time()
asyncio.run(main()) # asyncio.run(main()) 启动事件循环并执行 main 协程。
end_time = time.time()
print(f"Total time: {end_time - start_time} seconds")
```

### create_task()的作用
asyncio.create_task() 是 asyncio 库中的一个重要函数，用于**将一个协程包装成一个任务task** <b class="danger">并调度它在事件循环中运行。</b> 
<b class="info">create_task()</b>  是将协程包装为 Task，提交给事件循环统一调度，<b class="info">真正实现了“并发”。</b> 
- create_task() 不会立即运行协程，而是将其加入事件循环中排队。
- create_task() 创建任务后，需要通过 await task 来等待其结果或完成。await task 会阻塞当前协程直到任务完成。

主要作用有以下三个：

1. 创建任务：
- create_task() 将一个协程对象（由 async def 定义的函数返回的对象）包装成一个 Task 对象。
- Task 是 Future 的子类，表示一个异步操作的最终结果。
2. 调度执行：
- 创建的任务会被立即排入事件循环中，等待事件循环调度执行。
- 任务的执行是异步的，不会阻塞当前的执行流程。
3. 返回任务对象：
- create_task() 返回一个 Task 对象，你可以使用这个对象来检查任务的状态、获取任务的结果或取消任务。


### asyncio.gather()的作用
gather() 用于 <b class="success">并发运行多个协程或任务</b> ，并**收集**它们的**结果**。asyncio.gather(*coros_or_tasks) 接受**多个协程**或**任务对象**，传入协程时内部会**自动将协程包装成任务**（类似 create_task()），返回值是**按顺序**排列的协程返回值的**列表**。
- asyncio.gather(*coros_or_tasks) 接受多个协程或任务对象，会并发执行它们。
- asyncio.gather() 返回一个协程对象，必须用 await 来等待它完成。
- 使用 await asyncio.gather(...) 会阻塞当前协程，直到所有传入的协程或任务完成。

<b class="danger">asyncio.gather()方法的参数</b> 
asyncio.gather()方法的参数，**是传入task还是传入一个异步函数？**
- asyncio.gather() 的参数既可以是 异步函数调用（即协程对象），也可以是 已经创建好的 Task 对象，可以在 gather() 中混用协程和任务。
- asyncio.gather(coroutine_obj) 内部会自动将这些协程对象封装成 Task 并发执行，asyncio.gather(task)的优势是可以提前控制任务的创建过程（对任务的某些操作）。

<b class="info">等待多个任务中的某一个任务执行完即可的方法</b>

`asyncio.wait()` 会自动将协程对象包装成 Task 对象
```python
async def main():
    # 创建任务列表
    tasks = [task1(), task2()]
    
    # 等待第一个完成的任务
    done, pending = await asyncio.wait(
        tasks,
        return_when=asyncio.FIRST_COMPLETED
    )
```

### asyncio.run()的作用
asyncio.run() 会自动创建一个事件循环（event loop），运行传入的协程（即run方法中的参数），并在完成后清理事件循环。一次只能运行一个主协程。

### await的作用
await 用于**等待**一个 **协程、任务或 Future** 完成。它只能在 async def 定义的协程函数中使用。await 会挂起当前协程，**让事件循环去执行其他任务**，直到被等待的对象完成。
await task 会阻塞当前协程直到任务完成。

### 运行协程的几种方式
- 如果你只需要运行一个主协程，使用 asyncio.run(main())。
- 如果你想**并发运行**多个协程并等待它们完成，使用 asyncio.gather()。
- 如果你需要更细粒度地控制任务（比如取消、查询状态等），使用 asyncio.create_task() 并手动 await 每个任务。



### await async_fn 和 await task的本质区别
- **await async_fn()** 表示当前协程会 按顺序同步地 执行这个协程的代码，直到它完成。**它不会被调度到事件循环中并发运行**，而是由当前协程“亲自”一步步推进它的执行流程。同步执行（顺序执行），不支持并发。
- **await task** asyncio.create_task(fn()) 把协程封装成一个 Task 对象，并立即加入事件循环排队执行。await task 表示会挂起当前任务，让事件循环去运行其他任务，等这个任务完成后才继续。并发执行（多个任务可以同时在事件循环中跑），支持取消，查询等高级操作。
```python
import asyncio
import time

async def count(name, n):
    for i in range(1, n+1):
        print(f"{name}: {i}")
        await asyncio.sleep(0.5)

async def main():
    await count("A", 3)
    await count("B", 3)

asyncio.run(main())
# 同步执行，耗时3s，返回
A 1
A 2
A 3
B 1
B 2
B 3

## 使用封装task的方式
async def main():
    task1 = asyncio.create_task(count("A", 3))
    task2 = asyncio.create_task(count("B", 3))

    await task1
    await task2

asyncio.run(main())
# 并发执行，耗时1.5s，返回
A 1
B 1
A 2
B 2
A 3
B 3

## 更简洁的写法,task方式的语法糖
async def main():
    await asyncio.gather(count("A", 3), count("B", 3))
```
- **await async_fn** 当不需要并发执行时，或想严格执行顺序，或协程之间有严格依赖关系，使用await async_fn()
- **await task** 当需要并发执行多个独立的任务，或任务之间无依赖，需要提升CPU或IO效率时，使用await task


```python
import asyncio

# 定义一个协程
async def say_after(delay, what):
    await asyncio.sleep(delay)  # 模拟异步I/O操作
    print(what)

# 定义一个主协程
async def main():
    print(f"started at {time.strftime('%X')}")

    # 创建两个任务
    task1 = asyncio.create_task(say_after(1, 'hello'))
    task2 = asyncio.create_task(say_after(2, 'world'))

    # 等待两个任务完成
    await task1
    await task2

    print(f"finished at {time.strftime('%X')}")

# 启动事件循环
import time
start_time = time.time()
asyncio.run(main())
end_time = time.time()
print(f"Total time: {end_time - start_time} seconds")
```

如果**直接使用 asyncio.run() 执行一个协程**，而不是通过 asyncio.create_task() 创建任务，那么 asyncio.run() 会启动事件循环并运行指定的协程，直到该协程完成。这种方式**只适用于单个协程的简单场景**

##### 调用asyncio.run()提示runtimeError错误
在某些环境中，例如 Jupyter Notebook 或某些框架中，事件循环可能已经在运行。当尝试在已经运行的事件循环中调用 asyncio.run() 时，Python 会抛出 RuntimeError，因为 asyncio.run() 试图创建一个新的事件循环，而这是不允许的。
解决方案：
- 检查事件循环是否已经运行：可以使用 <b class="danger">asyncio.get_event_loop()</b>  来检查当前是否有事件循环在运行。
- 使用 <b class="danger">asyncio.create_task()</b> ：如果事件循环已经在运行，你可以使用 asyncio.create_task() 来创建并运行新的任务。
```python
if asyncio.get_event_loop().is_running():
    # 如果事件循环已经在运行，使用 asyncio.create_task()
    task = asyncio.create_task(say_after(1, 'hello'))
    # 确保任务被等待完成
    asyncio.get_event_loop().run_until_complete(task)
else:
    # 如果没有事件循环在运行，使用 asyncio.run()
    asyncio.run(say_after(1, 'hello'))
```

<b class="info">python中await 的本质</b> 
python中，理解 await 的本质： 把 await 看作一个检查点或让出点。每次遇到 await，当前协程就主动暂停，把执行权**交还给事件循环**。事件循环利用这段时间去做其他事情（运行其他就绪协程、检查I/O、处理定时器）。等 await 的东西准备好了，事件循环再把执行权还给这个协程，从 await 后面继续执行。

<b class="info">python中 task 的本质</b> 
掌握 Task 的创建： 明白 asyncio.create_task() 是并发执行多个协程的核心手段。它把一个协程对象调度到事件循环上，使其能与其他协程并发运行（在遇到 await 挂起时切换）。




## python文档化
文档化是在python代码中添加注释，提供代码的详细说明，包括参数和返回值的说明，以及代码示
例。
注解不同于注释，注解有更广泛的作用，注解在python中是一种元数据机制，用于在代码中添加额外信息，可用于类型检查、函数参数、返回值等。注解在python中通常与类型提示一起使用，提供关于变量，参数，返回值的预期类型信息。python的元数据机制是用于组织、管理、存储元数据的模型，即描述数据的信息，包含数据的类型，值的范围，来源以及其他属性。在python中，注解通常使用冒号来分隔表达式和类型。注解用于提供关于变量类型等元数据的信息，而注释则是为了在代码中添加人类可读的解释和说明。注解是Python 3引入的新特性，主要用于类型提示和类型检查。
 ```python 
def greet(name: str) -> str:
    return "Hello, " + name
 ```
在这个例子中，**name: str** 和 **\-> str** 就是注解，它们告诉开发者greet函数接受一个字符串类型的参数，并返回一个字符串类型的值。
**注解** 是Python 3引入的新特性，**主要用于类型提示和类型检查**。使用 **mypy** 这样的静态类型检查工具可以在开发时提供更早的反馈
```python 
pip install mypy

# mypy_example.py
 def greet(name: str, age: int) -> str:
 return f"Hello, {name} ({age} years old)"
```
在命令行中运行 mypy，mypy 将会检查并报告潜在的类型错误。
```
mypy mypy_example.py
```


## I/O操作
python中文件I/O可以通过内置的open()函数实现，该函数打开一个文件并返回一个对象，通过使用文件对象可以对文件进行读，写操作。
```python 
#打开，并读取操作
with open('./text.txt','r') as f:
   content = f.read()
   print(content)
#打开，并读取操作, 按行打印，逐行读取
with open('./text.txt', 'r') as f:
   for line in f:
       print(line)
```



## dotenv 环境变量
dotenv库用来读取项目中的 <b class="danger">.env文件</b> ，将.env文件中**定义的环境变量导入到当前程序运行的环境中供程序使用**。将<b class="danger">敏感信息（API密钥，数据库密码等）存储在环境变量中</b>而不是硬编码到代码中<b class="danger">提高程序运行的安全性，</b> 因为这些敏感信息不会存储在代码库中，**只存在于程序运行的环境中**。git版本控制信息中可通过 **\.gitignore文件忽略\.env** 配置文件，避免敏感信息上传到远程仓库。

dotenv 是一个 Python 库，它可以从 .env 文件中读取环境变量，并将它们添加到运行 Python 代码的环境中。这对于管理敏感数据（如 API 密钥）或配置信息非常有用，因为你可以将这些信息存储在 .env 文件中，而不是硬编码在你的 Python 代码中。



1. 安装python-dotenv库
```python 
pip install python-dotenv
```
2. 创建.env文件，并将环境变量写入到.env文件中，每组key=value对应一行
3. 将.env文件中的环境变量挂在到系统环境中。通过使用load_dotenv函数读取.env配置文件中的环境变量挂载到系统环境中。
```python 
from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv())
```


`find_dotenv` 函数会在你的项目目录及其父目录中查找 .env 文件。如果找到了 .env 文件，它会返回该文件的路径。

`load_dotenv `函数接受一个文件路径作为参数，并从该文件中加载环境变量。在这段代码中，它加载了 find_dotenv 找到的 .env 文件。

`_ = load_dotenv(find_dotenv()) `这行代码的意思是，找到 .env 文件并从中加载环境变量，但是忽略 load_dotenv 的返回值（它返回一个布尔值，表示环境变量是否成功加载）。_ 是一个常用的变量名，用于表示我们不关心这个值。

在使用 load_dotenv(find_dotenv()) 加载环境变量后，可以使用 Python 的 **os 模块**来获取这些环境变量。` os.environ` 对象，它是一个字典，其键是环境变量的名称，值是环境变量的值。
`os.environ.get("model3")`



## 多线程、多进程
进程(process)和线程(thread)是操作系统的基本概念，是操作系统程序运行的基本单元。
**进程是执行中的程序，是资源分配的最小单位**：操作系统以进程为单位分配存储空间，进程拥有独立地址空间、内存、数据栈等。操作系统管理所有进程的执行，分配资源。可以通过fork或 spawn的方式派生新进程，新进程也有自己独立的内存空间。**多进程<b class="danger">并行</b>执行**。

**线程是CPU调度的的最小单位：** 一个进程可以有多个线程，同进程下执行，并共享相同的上下文。线程间的信息共享和通信更加容易。**多线程<b class="danger">并发</b>执行**
![并发并行](./img/concurrent_parallel.jpg)

**并发**通常应用于 **I/O 操作频繁**的场景，**并行**则更多应用于 **CPU heavy** 的场景。
**并发(concurrency)**，指同一时刻只能有一条指令执行，多个线程的对应的指令被快速轮换地执行，线程/任务之间会互相切换。
a. 处理器先执行线程 A 的指令一段时间，再执行线程 B 的指令一段时间，再切回到线程 A，快速轮换地执行。
b. 处理器切换过程中会进行上下文的切换操作，进行多个线程之间切换和执行，这个切换过程非常快，使得在宏观上看起来多个线程在同时运行。
c. 每个线程的执行会占用这个处理器一个时间片段，同一时刻，其实只有一个线程在执行。

**并行（parallel）** ,指同一时刻，有多条指令在多个处理器上同时执行
a. 不论是从宏观上还是微观上，多个线程都是在同一时刻一起执行的。
b. 并行只能在多处理器系统中存在，如果只有一个核就不可能实现并行。并发在单处理器和多处理器系统中都是可以存在的，一个核就可以实现并发。注意：具体是并发还是并行取决于操作系统的调度。

**多线程使用场景**
多线程/多进程是解决并发问题的经典模型之一。
<b class="danger">在一个程序进程中，有一些操作是比较耗时或者需要等待的，比如等待数据库的查询结果的返回，等待网页结果的响应。这个线程在等待的过程中，处理器是可以执行其他的操作的，从而从整体上提高执行效率。</b>

比如网络爬虫，在向服务器发起请求之后，有一段时间必须要等待服务器的响应返回，这种任务属于IO 密集型任务。对于这种任务，启用多线程可以在某个线程等待的过程中去处理其他的任务，从而提高整体的爬取效率。

还有一种任务叫作计算密集型任务，或者称为CPU 密集型任务。任务的运行一直需要处理器的参与。如果使用多线程，一个处理器从一个计算密集型任务切换到另一个计算密集型任务，处理器依然不会停下来，并不会节省总体的时间，如果线程数目过多，进程上下文切换会占用大量的资源，整体效率会变低。

所以，如果**任务不全是计算密集型任务，我们可以使用多线程来提高程序整体的执行效率**。尤其对于网络爬虫这种 IO 密集型任务来说，使用多线程会大大提高程序整体的爬取效率，多线程只适合IO 密集型任务。


**程序在运行时一次只能执行一个任务（单线程）**，让程序同时执行多个任务就要使用多线程技术。
1. 程序进入执行状态后就是一个进程，每个进程有自己的独立的内存空间、系统资源，每一个进程的内部数据和状态都是完全独立的。windows中的进程局势exe或者dll程序，进程之间相互独立也可以通信。
2. 一个进程中可以包含多个线程，多个线程共享一块内存空间和一组系统资源，所以系统在各线程之间切换时，系统开销比进程小得多，因此线程称为轻量级进程。
3. python程序至少有一个线程即主线程，python程序启动后由python解释器负责创建主线程，程序结束后由python解释器停止主线程。多线程中，主线程负责其他子线程的调度，启动、挂起、停止等。多线程编程时，需要给每个子线程执行分配机会，通过让当前子线程休眠暂停 <b class="danger">（延迟当前子线程的后续执行）执行</b> ，让其他线程有机会执行。如果当前子线程没有休眠，只能等待当前线程执行后再执行第二个线程。

多线程可以把空闲时间利用起来，比如有两个进程函数 func1、func2，func1函数里使用sleep休眠一定时间，如果使用单线程调用这两个函数，那么会顺序执行这两个函数，也就是直到第一个函数执行完后，才会执行第二个函数，这样需要很长时间；如果使用多线程，会发现这两个函数是同时执行的，这是因为多线程会把空闲的时间利用起来，在第一个函数休眠的函数就开始执行第二个函数

python多线程使用场景：如果程序时cpu密集型的，使用python的多线程是无法提升效率的，如果程序时IO密集型的，使用python多线程可以提高程序的整体效率。

CPU密集型（CPU-bound）：CPU密集型也叫计算密集型，指的是系统的硬盘、内存性能相对CPU要好很多，此时，系统运作大部分的状况是CPU Loading 100%，CPU要读/写I/O(硬盘/内存)，I/O在很短的时间就可以完成，而CPU还有许多运算要处理，CPU Loading很高

IO密集型（I/O bound）：IO密集型指的是系统的CPU性能相对硬盘、内存要好很多，此时，系统运作，大部分的状况是CPU在等I/O (硬盘/内存) 的读/写操作，此时CPU Loading并不高，I/O bound的程序一般在达到性能极限时，CPU占用率仍然较低。这可能是因为任务本身需要大量I/O操作，而pipeline做得不是很好，没有充分利用处理器能力

多线程的应用有很多，一些阻塞主线程的操作应该被放到子线程中处理，比如打开文件，网络爬虫。多线程会产生并发问题，多个线程如果同时读取某个变量导致相互干扰产生并发问题，所以实际开发中尽量避免多个线程读取或写入相同的变量。
```python 
import _thread as thread
from time import sleep, ctime

def fun1():
    print('开始运行func1', ctime())
    # 休眠4秒
    sleep(4)
    print('func1运行结束', ctime())
def fun2():
    print('开始运行func2', ctime())
    # 休眠4秒
    sleep(2)
    print('func2运行结束', ctime())
def main():
    print('开始运行时间', ctime())
    # 启动一个线程运行func1函数
    thread.start_new_thread(fun1, ())
    thread.start_new_thread(fun2, ())
    # 休眠6秒
    sleep(6)
    print('运行结束时间', ctime())

if __name__ == '__main__':
    main()

E:\python\python.exe E:/progect/untitled1/untitled1/urls.py
开始运行时间 Sat Feb 16 09:34:00 2019
开始运行func1 Sat Feb 16 09:34:00 2019
开始运行func2 Sat Feb 16 09:34:00 2019
func2运行结束 Sat Feb 16 09:34:02 2019
func1运行结束 Sat Feb 16 09:34:04 2019
运行结束时间 Sat Feb 16 09:34:06 2019
```



#### 线程模块 threading ，线程类Thread
线程模块相关函数：
```python 
avtive_count() #返回当前处于活动状态的线程个数
current_thread() #返回当前的Thread对象
main_thread() #返回主线程对象，主线程是python解释器启动的线程

import threading
threading.current_thread()
threading.active_count()
threading.main_thread()
```

创建子线程
1. 线程对象，由threading模块的Thread类或Thread的子类构建的对象
2. 线程体，即子线程要执行的代码，通常封装到一个函数中。子线程启动后会执行线程提。
实现线程体有以下两种方式

a. 自定义函数中实现线程体
`Thread(target=fnName, name='threadname', args=[x1,x2])`
target参数指向自定义的线程体函数
name参数可自定义线程名称
args为线程体函数提供的参数，列表类型
示例
```python 
import threading
t1 = threading.Thread(target=Fn1, name ='myThread')
t1.start()
```
b. 自定义线程类实现线程体，run()方法就是线程体函数
![thread](./img/thead.jpg)

## 线程管理
1. 等待线程结束，某些场景可以控制主线程等待另一个子线程t1执行结束后才能继续执行
![thread2](./img/thread2.jpg)
join(timeout= None) #设置超时时间单位秒，不设置默认一直等待，调用join()方法让主进程阻塞，等待t1子进程执行完毕后再继续执行。

![thread3](./img/thread3.jpg)

![thread4](./img/thread4.jpg)

![thread_result](./img//thread_result.jpg)


## python GIL
由于 Python 中 GIL 的限制，导致**不论是在单核还是多核条件下，在同一时刻只能运行一个线程，导致Python 多线程无法发挥多核并行的优势**。GIL 全称为 Global Interpreter Lock（全局解释器锁)，是Python 解释器 CPython 中的一个技术术语，是Python之父为了数据安全而设计的。

在 Python 多线程下，每个线程轮流执行:
获取 GIL-->执行对应线程的代码-->释放GIL
**某个线程想要执行，必须先拿到 GIL**，并且在一个 Python 进程中，GIL 只有一个，导致即使在多核的条件下，同一时刻也只能执行一个线程。每一个线程执行完一段后，会释放 GIL，以允许别的线程开始利用资源。
![GIL](./img/GIL.jpg)
Python 由于GIL锁的存在，无法利用多进程的优势，要真正利用多核，可以重写一个不带GIL的解释器， 比如JPython（Java 实现的 Python 解释器）。某些Python 库使用C语言实现，例如 NumPy 库不受 GIL 的影响。在实际工作中，如果对性能要求很高，可以使用C++ 实现，然后再提供 Python 的调用接口。另外Java语言也没有GIL限制。








## python常见命令
```shell
cls #清屏幕
pip install packageName
pip uninstall packageName
pip #查看帮助
help(round) #查看某个函数的使用方法
import this #查看python之禅
```

## python常用全局函数
`id(var1)` 显示变量在内存中的位置
`dir(obj)` **列表形式**返回当前模块下的**所有变量**，包含内置变量，dir(sys)返回sys包的所有变量组成的数组
1. 操作相关函数
```python 
print(obj,end='|')
a=input()
exec('print(''Python'')') #执行python语句
eval('1+1') #执行一个表达式
type(obj)
id(obj) #返回某个obj对象的唯一标识
globals() #返回全局变量的字典
help()
isinstance('a', str) #判断一个对象是否为某个类的实例
issubclass(class1,class2) #判断一个类是否为另一个类的子类
```

2. 数学函数
```python 
len(a)
max(a)
min(a)
round(1.123, 2)
abs()
sum()
sorted(lis) #排序，返回被排序后的list
reverse(iterate) #返回可迭代对象的反转
divmod(a,b) #获取a除以b的商和余数
pow(a，b) #a的b次方
range(num1,num2, step)
```

3. 类型转换
```python 
str('a') #等同于 js toString(var)
int(1.0)
float(a)
bool(1)
tuple(iterate) #可迭代对象转换成tuple
list(iterate) #可迭代对象转换成list
dict(iterate) #可迭代对象转换成dict
set(iterate) #可迭代对象转换成set
iter(iterable) #返回一个可迭代的对象
enumerate(iterable) #返回一个枚举对象
hex(int) 转16进制
oct(int) 转8进制
bin(int) 转2进制
chr(int) 转数字为ASCII字符
ord(str) 转字符为ASCII编码
```

 ## python对象的方法
 1. random
```python 
import random
random.random() #生成0--1之间的随机浮点数
random.randint(a,b) #生成a,b之间的随机整数
random.choice(list) #对有序数列随机取样（list, tuple,str）
random.sample(list, 5) # 对有序数列随机取片段（对list,随机取5个元素）
random.shuffle(list) #随机打乱有序数列
```

2. time
```python 
import time
time.sleep(1) #间隔1秒休息一次
time.ctime() #生成本地时区时间
time.localtime() #生成本地时间的时间结构
time.strftime('%Y-%m-%d %H:%M:%S', time.localtime()) #格式化时间
```

3.string
```python 
str.format()
f'str{}'
str.isnumeric() #判断是否为可计数类型,一二三也会返回True
str.isdigit() #判断是否为数值类型，一二三会返回Fals
str.split(',') #以什么分割字符串为列表
str.strip() #去除空格
```
4. list
```python 
list1.copy()
list1.deepcopy()
```

5. dict
```python 
dic.get('key')
dic.keys()
dic.values()
dic.items()
dict.fromkeys(lis, val) #根据lis生成一个dict,key为lis成员，用val填充
dict(data) # 转data为字典格式，data的数据是列表[key, value]格式才行
```

## 模块的导入
import customModel
import customModel as abc #导入模块文件，并指定别名
from customModel import fn1 #导入模块文件的部分方法

## 系统模块
```python
import sys
sys.path.append('c:\\user\\directoryName') #手动添加一个路径

import os
os.name #当前系统名称
os.getcwd() #当前执行脚本的文件路径
os.listdir() #返回指定目录下的所有文件和目录，包括目录
os.chdir('c:\\users\\desktop') #更改路径
os.remove('abc.txt') #删除指定文件
os.path.split('c:/user/desktop/abc.txt') #返回文件路径目录和文件名的元组tuple('c:\\user\\desktop', 'abc.txt')
os.path.exists('c:/user/desktop/abc.txt') #判断文件或目录是否存在 返回True,False
```

## python数据读写
csv是有分隔符的text文件
路径的书写三种方式
`path1 =C:\\Users\\Administrator\\Downloads\\text.txt`
`path2 = C:/Users/Administrator/Downloads\\text.txt`
`path = r'C:\\Users\\Administrator\\Downloads\\text.txt'`






##### 1. 读取文件
```python 
open(路径, 模式, 编码格式),
模式r读取，w写入，rw读写，a追加，w+打开并清空，wb 二进制模式写入，
file = open(path1, 'r', encoding='utf8')
file.read(10) #读取10个字符，读取指定字符个数，读取完成后光标位于读取结束的位置，继续执行read()方法，会继续向后读取
file.readline() #读取行,按行读取
file.readline(5) #读取行的前5个字符
file.readlines() #读取所有行，并转成列表list
file.seek(0) #上一次读取完后将光标移动到开始位置，便于下次读取
file.close()
```
`f.seek(0) `光标移动到指定位置，f.seek(offset,whence)，第2个参数whence **1**表示光标当前所处位置为参考点，**0**表示文件开头位置为参考点，**2**表示文件结尾位置为参考点，第一个参数表示偏移多少个字节，正数表示向后偏移，负数表示向前偏移。

##### 2. 写入文件
```python 
file = open('text.txt', 'w', encoding='utf8') #创建一个待写入文件
file.write('abcd') #写入单个字符串
file.close()

file.writelines(list) #写入多个字符串组成的列表，列表list的成员依次传入writelines方法，水平书写，如果希望换行书写则遍历list在每个成员后 + '\n'，list中的元素必须是字符串

```

##### 3. pickle存储
可将数据处理过程中的任何类型数据格式保存为系统中的dump快照文件，**不像写入txt文件时会将原来数据格式转换为字符串**，pickle模块保存的dump快照文件保留的原有的数据类型。
```python 
#将数据保存为快照文件
import pickle
data = {'a':1,'b':[1,2,3], 'c':'hello world'}
dump_file = open('data.pkl', 'wb') #创建文件名为data.pkl的快照文件，写入模式
pickle.dump(data, dump_file)
dump_file.close()

#读取快照文件，还原数据
dump_file = open('c:\\user\\data.pkl', 'rb')
dt1 = pickle.load(dump_file)
print(dt1)
```






## 常用python标准库

伪随机数模块
```python
import random
x=random.random() #生成0-1的随机数
x=random.ranint(0,10) #生成0-10的随机整数
s=random.choice(list) #对list列表随机取样，取一个
s=random.sample(list,5) #对list列表随机取样，指定取样长度
s=random.shuffle(list) #将列表顺序随机排列
```

时间模块
```python
import time
time.sleep(1) #休息1秒
time.ctime() #生成本地时间的字符串
time.localtime() #生成本地时间的视图
time.strftime('%Y-%m-%d %H:%M:%S',time.time.localtime()) #格式化时间视图
```

## 常用python第三方库
### 1. Numpy 科学计算工具包
高级的数值编程工具，支持N维数组，对二维数组结构进行矩阵运算（无需遍历），包含随机数，线性代数，傅里叶变化等功能。

```python 
import numpy as np
ar = np.array([[1,2,3],[2,3,4]])
np.ndim #数组维度
```
一维数组：单行
二维数组：多行多列
三维数组：多个二维数组构成一个三维数组
四维数组：多个三维数组构成一个四维数组
创建数组时指定的行列个数不一样时，会自动转换成一维数组

#### numpy常用方法
##### 创建数组，及数组的属性
```python 
ar = numpy.array([1,2,3])  #生成数组
ar.ndim #数组维度的个数，轴数，或者说秧，维度的数量也称rank
ar.shape #数组的行列个数
ar.size #数组元素的总个数，n行m列元素个数是n*m
ar.dtype 查看数组中元素的类型，python中的type()函数查看的是数组变量的类型
ar.itemsize 数组中每个元素的字节长度，int32 类型是4字节，float类型是8字节
ar 查看数组详情

#创建数组
ar0 = numpy.array([1,2,3,4,5,6,7,8,9])
ar1 = numpy.array(range(10))
ar2 = numpy.arange(10)  numpy自带生成数组的方法
ar3 = numpy.random.rand(10) #创建10个随机数的数组
ar3.reshape(2,5)  #将一维数组ar3改为2行5列的二维数组
ar3 = numpy.random.randint(0, 10, size=(2, 3)) # 生成2*3的随机数组，元素在0-9之间
ar4 = numpy.linspace(10, 21, num=20, endpoint= True, retstep=True) #生成10-21之间的数据，均分成20个，endpoint参数指定是否包含最后一个边界数，retstep是否显示步长
ar5 = numpy.zeros(10) 创建长度为10的数组，用0填充，ones(10)方法类似
ar6=numpy.zeros((2*5), dtype=numpy.float) 创建2行5列，用0填充的数组，元素为浮点数，ones((2*5), dtype=numpy.int)方法类似
ar7 = numpy.zeros_like(ar3) 创建一个数组ar7 复制ar3的数组结构，ones_like(ar3)方法类似
ar8 = numpy.eye(5) #创建一个正方形n*n的单位矩阵，对角线值为1，其余数为0
```

##### 修改数组
```python
ar=np.arange(10,dtype=float)

ar.resize(2,5) #实例的方法，修改原数组，修改后数组的元素可以和原数组的元素个数不一致，修改的是原数组返回None
np.resize(ar,(3,3)) #类方法，传入ar参数后生成新的数组，返回操作后的数组

ar.reshape(2,5) #修改数组，修改后数组的元素必须和原数组的元素个数一致，返回一个新数组
np.reshape(ar, (2, 3)) #返回一个新数组

ar2 = ar.T #行列转换,返回一个新的数组

ar2 = ar.astype(np.int64) #改变元素类型，生成新的数组
ar3 = ar.astype("float32")

# 数组的堆叠
np.hstack(a,b) #将一系列数组在水平方向堆叠（列方向）
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
result = np.hstack((a,b))
[[1 2 5 6]
 [3 4 7 8]
]

np.vstack(a,b) #将一系列数组在垂直方向堆叠，（行方向）
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
result = np.vstack((a, b))
[[1 2]
 [3 4]
 [5 6]
 [7 8]]

np.stack((ar1,ar2),axis=0) # 将一系列数组沿着新轴进行堆叠，生成一个新的高维数组。
#当你有两个或多个相同形状的数组，并且希望将它们沿一个新的维度拼接在一起时。
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
result = np.stack((a, b), axis=0)

[[[1 2]
  [3 4]]

 [[5 6]
  [7 8]]]
如果将axis=1，那么就是按列进行堆叠，如果axis=2，那么就是按深度进行堆叠。
[[[1 2]
  [5 6]]

 [[3 4]
  [7 8]]]



# 数组的拆分
ar = np.arange(16).reshape(4,4)
np.hsplit(ar,2) #横向拆分，拆分成2个，返回list
a = np.array([[1, 2, 3, 4],
              [5, 6, 7, 8],
              [9, 10, 11, 12],
              [13, 14, 15, 16]])
result = np.hsplit(a, 2)
#返回
[array([
    [1, 2]
    [5, 6]
    [9, 10]
    [13, 14]
]),
array([
    [3, 4]
    [7, 8]
    [11, 12]
    [15, 16]
])]

ar = np.arange(16).reshape(4,4)
np.vsplit(ar,2) #纵向拆分，拆分成2个，返回list

a = np.array([[1, 2, 3, 4],
              [5, 6, 7, 8],
              [9, 10, 11, 12],
              [13, 14, 15, 16]])
result = np.vsplit(a, 2)
#返回
[array([[1, 2, 3, 4],
        [5, 6, 7, 8]]),
array([[9, 10, 11, 12],
      [13, 14, 51, 16]])]
```

##### 数组的切片
```python
# 索引切片
ar = np.arange(16).reshape(4,4)
ar[2][3] #第三行的第四个元素，索引从0开始
ar[1:3] #第二行到第四行，不包含第四行，索引从0开始
ar[2,3] #第三行的第四列的元素，索引从0开始，与ar[2][3]类似
ar[:1,2:] #第二行的第三列及以后的元素，索引从0开始

# 布尔型索引切片
ar=np.arange(12).reshape(3,4)
i = np.array([True, False, True])
print(ar[i,:]) #将ar的行按i即[True, False, True]来切片，即保留第0行和第2行，列为:即保留所有列
print(ar[:,i]) #将ar的列按i即[True, False, True]来切片，即保留第0列和第2列，行为:即保留所有行
print(ar>5) #会返回一个元素为True或者False的二维数组，可以利用这个二维数组来筛选原数组的元素
ar[ar>5] #将布尔数组套到原数组上，筛选原数组
[[False False False False]
 [False False  True  True]
 [ True  True  True  True]]
```

##### numpy中的随机数
```python
np.random.normal(size=(4,4)) #用随机数生成4*4的数组，正态分布，元素为-1到1之间的浮点数
np.random.randn(4,4) #用随机数生成4*4的数组，正态分布，元素为浮点数-1到1之间
np.random.randn(100) #生成100个-1到1之间正态分布的随机数

np.random.rand(4,4) #用随机数生成4*4的数组，均匀分布，元素为浮点数0-1
np.random.rand(4,4)*100 #生成4*4的数组， 0-100的随机数，均匀分布
np.random.rand(100) #生成100个在0-1之间的均匀分布的随机数

np.random.randint(2,9) #取一个区间内的随机整数，均匀分布
np.random.randint(10,size=10) #在0-9之间取10个随机整数，组成一维数组
np.random.randint(10,size=(2,5)) #在0-9之间取10个随机整数，组成二维数组
np.random.randint(10,20,size=(3,3)) #在10-19之间取 3*3的二维数组
```

##### numpy 数据输出
```python
import os
os.chdir('C:\\users\\desktop\\')
np.load('')
np.save('test.npy',ar) #存为npy数组文件
np.load('test.npy') #读取npy的数组文件

np.savetxt('test.txt',ar,delimiter=",") #存成逗号分割的txt文件

# 数据读取时也要指定分隔符
np.loadtxt('test.txt',ar,delimiter=",") #读取逗号分隔符的txt文件
```
---

### 2.pandas
基于numpy构建，在pandas中一维数组**Series**, 二维数组**dataframe**
```python
import pandas as pd
import numpy as np

ar = np.random.rand(5) #生成5个随机浮点数组成的一维数组
s=pd.Series(ar) #将一维数组转换成Series，series是一个自带索引index的数组，即一维数组+索引

# 查看索引信息， 索引是生成器类型。索引可以不是数字，可以是字母。索引可以是不同类型数值混合使用。
# RangeIndex(start=0, stop=5, step=1)
print(s.index) 

# 查看series的所有值，是narray数组类型
# [0.56305847 0.98721076 0.02718032 0.15178964 0.23487075]
s.values 
```
##### 创建Series
```python
# 1. 通过字典创建序列
dic={'a':1,'b':2,'c':3,5:10}
s = pd.Series(dic) #返回索引是a,b,c,5 对应值是1,2,3,10的序列

# 2. 通过一维数组创建序列
ar =np.random.rand(10)
s = pd.Series(ar)

# 3. 通过标量（静态的值）创建序列
s=pd.Series(100,index=range(4)) #索引0-3，由100构成的4个值的序列
```

##### Series的参数
- index #指定索引，**索引的数量必须和值的数量一致**
- dtype #指定值的类型
- name #指定Series的名称，可以通过s.rename('test') 来修改

##### Series的索引
```python
s=pd.Series(np.random.rand(10))
1. 位置索引
s[5] #根据位置索引查找第6个值，索引从0开始
s[[6,3]] #根据多个索引查找多个值，索引可以不按原顺序，索引是数组类型
s[-1] #位置索引不支持-1这种相对位置

2.标签索引
s=pd.Series(np.random.rand(5),index=['a','b','c','d','e'])
s['a'] #通过名称为a的标签索引找到对应的值
s[['b','a']] #通过多个标签名称索引查找多个对应的值，可以不不按原顺序。索引是数组类型

3.切片索引
s1=pd.Series(np.random.rand(5)) #不指定索引信息时，默认为位置索引
s2=pd.Series(np.random.rand(5),index=['a','b','c','d','e']) #指定标签索引
s1[1:4] # 取位置索引为1-4，不含位置索引为4的3个元素
s1[:-1] # 切片可以用相对位置
s1[-1] # 通过位置索引查找元素，不能用相对位置
s1[1:5:2] #位置索引切片，可指定步长
s2['a':'c'] #取标签索引a-c的三个元素，包含c，必须按标签索引顺序
s2[0:3] #不指定标签索引时，也可以通过位置索引查找，取位置索引0-3，不包含3的3个元素
s2['a':'d':2] #标签索引切片，可指定步长

4.布尔型索引
s=pd.Series(np.random.rand(3)*100)
s[4]=None #设置第五个元素为None
s[4]=np.nan #设置第四个元素为NaN，注意NaN和None不一样
bs1=s>50 #生成一个值为布尔类型序列
0     True
1    False
2    False
4    False
bs2=s.isnull() #判断序列中的每个值是否为null，生成一个值为布尔类型序列
0    False
1    False
2    False
4     True
bs3=s.notnull() #判断序列中的每个值是否不为null，生成一个值为布尔类型的序列
0     True
1     True
2     True
4    False
s[bs3] #用生成的布尔序列来取s序列，返回第1,2,3三个元素

```

##### Series的数据查看，重新索引，索引对齐，添加修改删除值
```python
# 查看数据
s = pd.Series(np.random.rand(15))
s.head() #查看前5个元素
s.head(2) #查看前2个元素
s.tail() #查看后5个元素

# 重新索引，按新的索引重新排序
reindex(['a','b','g','h']) #重新索引，按新的索引重新排序，如果新的索引不存在，则索引对应的值为NaN，如果新的索引存在，则索引对应原来的值
reindex(['a','b','g','h'],fill_value=0) # 重新索引，如果索引对应的值不存在，则用0填充
s=pd.Series(np.random.rand(5),index=['a','b','c','d','e'])
s.reindex(['c','d','f','a'],fill_value=0) #重新索引，索引f不存在，用0填充

# 索引对齐
s1=pd.Series(np.random.rand(4),index=['jack','jack','tom','kitty'])
s2=pd.Series(np.random.rand(3),index=['jack','tom','kitty'])
print(s1)
print(s2)
print(s1+s2) # 索引对齐，如果索引对齐（相等），则相加，否则返回NaN

# 索引删除
s=pd.Series(np.random.rand(5),index=list('abcde'))
s1=s.drop('a') #返回删除后的新序列
s2 = s.drop(['c','d']) #返回删除后的新序列
s.drop(['c','d'],inplace=True) #删除原序列中的索引

# 添加索引
s1[5]=100 # 通过索引标签添加元素
s1['f']=200

s1.append(s2) #添加一个Series，返回一个新序列

# 修改索引
s1.index=['a','b','c','d','e','f']
s1.rename(index={'a':'jack','b':'tom'}) # 通过关键字映射的方式修改索引

```






---

### 3. Pydantic
Pydantic是一个Python库，用于数据验证和序列化。它的作用是定义数据模型并对数据进行验证，以确保数据的类型和结构符合预期。Pydantic还提供了将数据模型转换为字典或JSON字符串的功能，以便于数据的导出和交互。

BaseModel 是 Pydantic 库中的一个核心类，用于定义数据模型。Pydantic 是一个用于数据验证和解析的库，它允许你 <b class="danger">使用 Python 类型注解来定义数据模型</b> ，并自动进行数据验证和转换。




#### model_dump_json()
`model_jump_json` 是 Pydantic 模型的一个方法，用于将Pydantic模型的数据实例序列化（转换）为 JSON 字符串，不会递归调用嵌套模型的 .json() 方法。返回的是一个 JSON 字符串。适用场景，只需要序列化模型的字段值而不关心嵌套结构。

```python
# 美化json输出
import json
#传入的obj对象是继承自pydantic.BaseModel的类的实例，实例上有model_dump_json()方法
def show_json(obj):
    str = json.dump(
        json.load(obj.model_dump_json()),
        indent=4,
        ensure_ascii=False
    )
    print(str)
```

#### pydantic_instance.json()方法
将整个pydantic模型（包括嵌套模型）以 JSON 格式序列化，自动递归处理嵌套模型。返回的是一个 JSON 字符串。适用场景，需要完整地序列化模型及其所有嵌套结构。

#### pydantic_class.parse_raw(data)方法
解析原始数据（如 JSON 字符串）并将其转换为pydantic模型实例的方法。将原始数据（如 JSON 字符串、字节流等）解析为 Pydantic 模型实例。自动验证数据是否符合模型定义的结构和类型,返回的是一个经过验证的 Pydantic 模型实例。



**升级到最新版pydantic**，部分conda环境安装的pydantic库是老版本，没有model_dump_json()方法
`conda install -c conda-forge pydantic`


#### 定义数据模型
使用 BaseModel 定义数据模型
```python 
from pydantic import BaseModel

#定义一个pydantic类型
class User(BaseModel):
    id: int
    name: str
    email: str
    is_active: bool = True
    age: int = None

# 创建模型实例
# 创建模型实例时，必须显式传入模型的字段名称
user_data = {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com",
    "is_active": False,
    "age": 30
}
# 创建 User 实例
user = User(**user_data)

# 访问字段
print(user.id)        # 输出: 1
print(user.name)      # 输出: John Doe
print(user.email)     # 输出: john.doe@example.com
print(user.is_active) # 输出: False
print(user.age)       # 输出: 30


#使用model_dump_json方法讲模型序列化为JSON数据
print(user.model_dump_json())
#打印出JSON格式数据
```

#### Field字段和v1.0版本的Pydantic
Pydantic 在 v2 版本中进行了一些重大更改和改进，这可能导致一些旧的代码或依赖项不再兼容。应该明确地使用 pydantic.v1 来确保代码的稳定性和一致性。防止由于安装了最新版本的 Pydantic（可能是 v2 或更高版本）而导致的潜在问题，确保代码继续使用期望的 API 和行为。
`from pydantic.v1 import BaseModel, Field`

**Field** 是 Pydantic 中用于**定义模型字段**的**类**。用于为字段添加更多的**元数据和校验规则**。
```python

from pydantic.v1 import BaseModel, Field

# ... 表示该字段是必填项。
# description 提供字段的描述信息，有助于生成文档或调试。
# gt, ge, lt, le 分别表示大于、大于等于、小于、小于等于，用于数值类型的范围限制。
# min_length, max_length 用于字符串类型的长度限制。
# default 设置默认值（可选字段）

class Product(BaseModel):
    id: int = Field(..., description="Product ID", gt=0)
    name: str = Field(..., min_length=1, max_length=100, description="Product Name")
    price: float = Field(..., ge=0, description="Price of the product in USD")
    # is_available 默认值为 True
    is_available: bool = Field(True, description="Whether the product is available")

# 创建实例
product = Product(id=1, name="Laptop", price=999.99, is_available=True)

print(product)


```

#### 校验数据类型
Pydantic 会自动进行数据验证。如果传入的数据不符合定义的类型或约束，会抛出 ValidationError。
```python 
from pydantic import BaseModel

#定义一个pydantic类型
class User(BaseModel):
    id: int
    name: str
    email: str
    is_active: bool = True
    age: int = None

#创建一个待验证的数据实例
invalid_user_data = {
    "id": "not an integer",  # 错误：id 应该是整数
    "name": "Jane Doe",
    "email": "jane.doe@example.com",
    "is_active": True,
    "age": 25
}

try:
    # 使用定义的数据模型进行数据验证
    user = User(**invalid_user_data)
except ValueError as e:
    print(e)

# 输出错误信息
1 validation error for User
id
  value is not a valid integer (type=type_error.integer)
```
#### 自定义验证器
```python
from pydantic import BaseModel, validator

class User(BaseModel):
    id: int
    name: str
    email: str
    is_active: bool = True
    age: int = None

    @validator('email')
    def validate_email(cls, v):
        if '@' not in v:
            raise ValueError('Invalid email address')
        return v

user_data = {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com",
    "is_active": False,
    "age": 30
}

user = User(**user_data)
print(user.email)  # 输出: john.doe@example.com
```

### python中的typing模块
typing模块可以实现**类型标注（Type Annotations）**或称为**类型提示（Type Hints）**。允许在函数定义中**指定参数和返回值的预期类型。** 类型标注不是强制性的：Python 是动态类型语言，类型标注不会影响代码的运行时行为。它们主要用于开发和调试阶段。

类型标注的作用
- 提高代码**可读性**，类型标注可以帮助其他开发者（包括未来的你自己）更容易理解函数的意图和用法。通过明确指出参数和返回值的类型，减少了阅读代码时的猜测。
- **静态类型检查**。**使用工具如 mypy**，可以在不运行代码的情况下检查类型错误，从而捕获潜在的bug。有助于在开发早期发现类型不匹配的问题，减少调试时间。
- **文档生成**。类型标注可以用于生成文档，帮助其他开发者了解函数的参数和返回值类型。

<b class="danger">Optional 通常用于表示一个变量可以是某种类型或者为 None,Optional 实际上是 Union[T, None] 的简写形式，其中 T 是任意类型。这意味着 Optional[T] 表示该值要么是类型 T 的实例，要么是 None。</b> 
`self.session: Optional[ClientSession] = None` ,定义并初始化一个可选类型的实例属性 self.session，类型为 ClientSession 或 None,将 self.session 的初始值设置为 None，表示在对象初始化时，该属性还没有被赋值为具体的 ClientSession 实例。

```python
# List[T] 表示一个包含类型为 T 的元素的列表。返回值为 None 表示没有返回值。
from typing import List
def process_items(items: List[str]) -> None:

# 希望一个参数或返回值可以是某种类型或者 None 时，使用 Optional。这里定义的是期望返回一个字符串或者 None。
from typing import Optional
def get_user_name(user_id: int) -> Optional[str]:

# Tuple[T1, T2, ...] 表示一个包含特定类型元素的元组。这里定义的是期望返回一个包含两个整数的元组。
from typing import Tuple
def get_coordinates() -> Tuple[int, int]:

# Dict[K, V] 表示一个键为类型 K、值为类型 V 的字典。这里定义的是期望返回一个键为字符串、值为整数的字典。
from typing import Dict
def get_user_info() -> Dict[str, str]:

# Set[T] 表示一个包含类型为 T 的元素的集合。这里定义的是期望返回一个包含整数的集合。
from typing import Set
def get_unique_values() -> Set[int]:

# Union[T1, T2, ...] 表示值可以是类型 T1、T2 等中的任意一种。这里定义的是期望参数可以是整数、浮点数或字符串。返回值为 None 表示没有返回值。
from typing import Union
def process_input(value: Union[int, float, str]) -> None:


# Callable[[Arg1Type, Arg2Type, ...], ReturnType] 表示一个接受特定类型参数并返回特定类型结果的可调用对象。这里定义的是期望参数是两个整数，Callable的返回值是整数的函数。apply_function函数的返回值是整数。
from typing import Callable
def apply_function(func: Callable[[int, int], int], a: int, b: int) -> int:
    return func(a, b)

# Any 表示值可以是任何类型，通常用于不确定类型的情况下。
from typing import Any
def process_anything(value: Any) -> Any:

# 表示一个具有固定键和对应类型的字典。定义一个子类来指定键及其对应的类型。这里定义的是期望参数是一个键为title值为string,键为year值为int的字典类型。
from typing import TypedDict
class Movie(TypedDict):
    title: str
    year: int
```



### 4. PDF处理工具
![alt text](./img/pdf-extract.png)

- 1.文档解析工具，pdf处理库
    - PyPDF
    - PyMUPDF

    - PDFMiner.six 是一个 Python 库，用于从 PDF 文件中提取文本和布局信息。它是 PDFMiner 库的更新版本。
    PDFMiner.six 可以用来：
        - 提取 PDF 文件中的文本
        - 分析 PDF 文件的布局和结构
        - 提取 PDF 文件中的图像和其他媒体
        - 支持多种语言，包括中文

- 2.OCR工具解析PDF文件
    - pytesseract OCR库

- 3.智能文档解析工具（IDP）
    - 基于LlamaCloud 提供的解析工具 llamaParse，将文档解析为PDF格式，每天1000页免费额度。
    - e2m



- 4.其他PDF转markdown工具
    - docling
    - markitdown
    - marker

### 5.elasticSearch
Elasticsearch 是一个开源的分布式全文搜索引擎，它提供了快速、可扩展的文本搜索和数据分析功能。它主要用于处理大量结构化和非结构化数据，并支持各种数据分析和可视化工具。

倒排索引是一种搜索引擎的数据结构，它将文档中的每个词映射到一组文档中，并记录每个词在文档中出现的次数。即关键字对应文档的索引id,通过关键字查找文档。这有别于传统sql数据库，用id号查找文档的方式。

elasticSearch中的核心概念
  - 索引index类似于mysql中的**表table**，document类似mysql中的**一行记录**，mapping类似于mysql中的schema表结构描述
  - 索引的操作
    - 将不同业务类型的数据存放到不同的索引中，比如微博信息存入weibo_index,新闻业务存入new_index,博客内容存入blog_index
    - 按日期切分存储日志索引，比如7月的日志存入logs_202407
    - 创建索引 PUT/index_name
    {
        obj
    }
        - obj 常见参数：
        - number_of_shards: 分片数，默认为5，一个分片对应一个索引文件，一个索引文件对应一个磁盘文件，分片越多，查询越快，但是越占磁盘空间
        - number_of_replicas: 备份数，默认为1，如果设置为0，则表示不备份，如果设置为2，则表示备份2个副本，如果设置为3，则表示备份3个副本，如果设置为4，则表示备份4个副本，以此类推，备份越多，查询越慢，但是越安全，但是越占磁盘空间
        - mappings: 字段定义，指定索引包含哪些字段。比如id是整型，username是字符串，email是字符串，对应mysql表中的字段
        
    - 删除索引 DELETE/index_name
    - 查询索引 GET/index_name
    - 查询索引对应的数据 GET/index_name/_search
    {
        "query":{ 查询条件 }
    }
    - 修改索引， 修改索引的setting设置 PUT/index_name/_settings, 修改索引的mapping PUT/index_name/_mapping
  - 索引的别名。针对PB级别增量数据需要提供按日期切分的索引，此时需要为索引定义别名，方便按日期查询索引即对多个索引进行分组。或者某个索引起初设计不合理，比如某个字段定义不准确，如何保证不停止服务的前提即不修改业务代码的前提下更换索引。
    - 当没有索引别名时，查询索引时POST index_1,index_2,index_3/_search
    - 有别名时，直接查询原始索引对应的别名（将原索引名称分组后定义的名称，比如将原索引index_202401,index_202402 分组归纳定义别名为index_2024）
  - 文档的操作
    - 新增单个文档 POST/index_name/_doc/doc_id
    {
        "field1":"value1"
        "field2":"value2"
    }
    - 新增多个文档 POST/index_name/_bulk
    - 根据id查询文档 GET/index_name/_doc/doc_id
    - 根据关键字查文档 
        - 匹配所有文档 GET/index_name/_search
        {
            "query":{
                "match_all":{}
            }
        }
        - 匹配文本字段 GET/index_name/_search
        {
            "query":{
                "match":{
                    "field1":"query_string"
                }
            }
        }
    - 删除文档 DELETE/index_name/_doc/doc_id
    - 更新文档
      - 更新单个文档 POST/index_name/_update/doc_id
      {
        "doc":{
            "field1":"value1"
        }
      }
      - 更新多个文档 POST/index_name/_bulk
      {
        "update":{"_index":"index_name1","_id":"doc_id"}
        "doc":{"age":22}
        "update":{"_index":"index_name2","_id":"doc_id"}
        "doc":{"age":23}
      }

#### elasticSearch 文档的建模最佳实践
- 文档类型选择
    - 单一对象类型，比如博客，作者，选择反范式Denormalization    Object类型
    - 当数据中包含多数值对象，比如某字段包含数组内容，比如电影包含的演员信息，选择Nested类型
    - 父子文档更新较为频繁的场景，选择Child/Parent
- 一个文档中，避免大量字段，默认最大字段数1000
- 避免通配符，正则，模糊查询

### 6.NLP 相关库和工具
nltk: 自然语言处理，分词，识别命名实体，词性标注，词汇规范化（提取词干，词形还原）。
jieba: 中文分词


### 7.处理excel文件的库
openpyxl: 读写excel文件，支持xlsx格式


### 8.处理http请求的库
httpx: 快速、支持异步、可扩展的HTTP库,支持http1.1和http2
```python
try:
    response = httpx.get("https://www.example.com/")
    response.raise_for_status()
except httpx.HTTPError as exc:
    print(f"Error while requesting {exc.request.url!r}.")


# 显式的处理发起请求和接收响应时的两种情况的错误
try:
    response = httpx.get("https://www.example.com/")
    response.raise_for_status()
except httpx.RequestError as exc:
    print(f"An error occurred while requesting {exc.request.url!r}.")
except httpx.HTTPStatusError as exc:
    print(f"Error response {exc.response.status_code} while requesting {exc.request.url!r}.")

```

创建一个客户端实例并复用它来发送多个请求 **async with httpx.AsyncClient() as client:** ,这样做的好处是可以保持连接（持久连接），提高性能，并且可以共享配置（如 headers、cookies、认证信息等）。相比之下，使用 **httpx.post() 会发送多次请求**会导致每次都新建连接（三次握手），这会增加延迟。
```python
## 并发方式一、使用asyncio.gather()
async def fetch():
    async with httpx.AsyncClient() as client:
        resp1, resp2 = await asyncio.gather(
            client.get("https://httpbin.org/get"),
            client.get("https://abcde/get")
        )
        print(resp1.status_code, resp2.status_code)

## 并发方式二、使用create_task()+await
async def fetch():
    async with httpx.AsyncClient() as client:
        task1 = asyncio.create_task(client.get("https://httpbin.org/get"))
        task2 = asyncio.create_task(client.get("https://abcde/get"))

        resp1 = await task1
        resp2 = await task2

        print(resp1.status_code, resp2.status_code)
```

```python
## 这种方式是串行执行的，非并发。
async def fetch():
    async with httpx.AsyncClient() as client:
        response1 = await client.get("https://httpbin.org/get")
        response2 = await client.get("https://abcde/get")

```




### 9.mcp开发工具
`uv add "mcp[cli]"`

## 安装pip
1. 在Python官网上下载Windows版本pip安装包
https://pypi.org/project/pip/#downloads
![install_pip](./img/install_pip.jpg)
下载完成后，将得到一个压缩包，将压缩包进行解压。

2. 打开控制台，使用cd命令进入解压后的文件夹至可执行目录，如下图所示
![install_pip2](./img/install_pip_2.jpg)

3. 在控制台输入如下命令：
`python setup.py install`
回车，控制台将自动安装pip，安装完成后，在控制台输入
`python -m pip --version`命令
如果显示‘pip’不是内部命令，也不是可运行的程序，说明，缺少环境变量。
![install_pip3](./img/install_pip_3.jpg)
在此，需要在系统环境变量PATH中添加环境变量：C:\Python27\Scripts（本次安装的是Python2.7.10版本，所以需要添加环境变量C:\Python27\Scripts）;添加完成后，再次执行
`python -m pip --version`  命令，如果控制台输出pip的版本号，说明安装成功。

## pip python包管理工具
在cmd命令行环境下安装包
```shell 
 pip install packName
 pip install packName[numpy,scipy] #安装包，同时安装包的依赖项
 pip install packName ==1.2 #指定安装版本
 pip install --upgrade packName #升级已安装的包
 pip install --no-dependencies packName #安装包，忽略包的依赖
 pip install /path/to/packName #安装本地指定目录的包
 pip uninstall packName
 pip list #列出当前python环境已安装的所有包或库
 pip show packName #列出指定包的详细信息
 pip search packName #在python package index 上查找包的信息
 pip #查看帮助
 pip freeze > requirements.txt #导出依赖库，生成依赖包列表文件
 pip install -r requirements.txt #根据导出的依赖包列表文件，安装依赖包
 pip install pipreqs #依赖包管理模块
 pipreqs ./ #导出当前项目目录下所依赖的包
 pip cache purge
```

## conda命令
- 创建新环境，指定python版本
  `conda create --name envName python=3.11.15`
- 列出所有环境
  `conda info --envs`
  `conda env list`
- 激活环境
  `conda activate envName`
- 验证python版本
  `python --version`
- 切换回系统默认环境
  `conda deactivate`
- 删除环境
  `conda env remove -n envName`
- 安装指定版本python
  `conda install python=3.9.5`
- 在环境envName中安装指定python版本
  `conda install -n envName python=3.8.0`

- 安装指定版本包
`conda install numpy=1.19.2`

- 在 Conda 环境中结合使用 pip 来安装不在 Conda 仓库中的包
`pip install some-package`

- 在Conda环境中安装软件包，并指定软件包的来源。模型情况下，conda会从default频道查找软件包，conda-forge频道是一个社区驱动的频道，提供了大量的第三方软件包。
`conda install -c conda-forge some-package`

- 导出当前环境配置
`conda env export > environment.yml`

- 从 environment.yml 文件创建环境
`conda env create -f environment.yml`

- 从已有的一个环境进行更新，可以使用 conda env update
`conda env update -f /path/to/your/environment.yml

- environment.yml 配置示例：
```yaml
name: myenv
channels:
  - defaults
dependencies:
    - python=3.8
    - numpy=1.19.2
    - pandas=1.1.5
    - scikit-learn=0.24.2
    - pip:
        - some-package==1.0.0
```




pip 安装的包通常存放在 Python 的 site-packages 目录中。
`C:\Python3x\Lib\site-packages`

conda 在不同环境中安装的包存放在其对应的环境目录下。
`C:\Users\<username>\Anaconda3\envs\<env_name>\pkgs`


## uv工具链
uv 是一个新兴的工具，用于管理 Python 项目依赖、构建虚拟环境和运行测试等任务。
```shell
uv init weather # 在当前目录初始化一个weather的项目
cd weather # 进入项目目录
uv venv # 创建虚拟环境
source .venv/bin/activate # 激活虚拟环境
uv add "numpy" # uv add 不仅安装依赖，还会同步更新
```
uv add package_name 命令会自动更新项目的 pyproject.toml 文件，记录新添加的依赖及其版本信息

<b class="danger">参数 --active 表示将命令在当前已激活的虚拟环境下执行</b>，如果不加该参数则在当前默认的环境下执行

## WSL2
1. 开启CPU虚拟化，进入BIOS设置，intel vmx virtualization technology 开启，amd AMD-V 开启
2. 开启windows功能，勾选“适用于Linux的Windows子系统”、“虚拟机平台”
3. cmd管理员身份运行，输入wsl --install --web-download 
4. 安装其他版本 wsl --install Ubuntu-22.04 --web-download
5. 输入账号密码
6. 常用命令
    - wsl --update #更新wls
    - wsl --set-default-version 2 #设置wsl2为默认版本
    - wsl --version #查看wls版本
    - wsl #开机启动wsl
    - wsl -d Ubuntu #启动指定的子系统
    - wsl--shutdown #重启虚拟机，等待8秒后再打开
    - wsl --list --online #可安装的发行版
    - wsl --list -v #当前子系统列表
    - wsl --set-default openSUSE-Leap-15.5 #指定模型的发行版本
    - wsl --unregister openSUSE-Leap-15.5 #卸载指定的子系统
    - wsl --export openSUSE-Leap-15.5 d:\wslopensuse\opensuse-bak.tar #备份指定子系统到指定目录
    - wsl --import Ubuntu2 d:/wsl c:\users\abc\desktop\opensuse-bak.tar #加载备份文件到指定目录d:/wsl(提前先创建)，并启动名称为Ubuntu2的wsl
    - windows PowerShell中可以混用linux命令和windows cmd命令
    - nvidia-smi #查看显卡直通
    - 修改.wslconfig文件（对wls1,wls2都生效），让wsl的ip地址和windows的ip地址直通。在C:\User\username\ 创建.wslconfig文件。用记事本打开添加以下内容并保存。然后执行wsl--shutdown关闭虚拟机，<b class="danger">等待8秒后启动</b> 
        ```shell
        [wsl2]
        networkingMode=mirrored
        ```
    - 在linux终端命令行中，输入 **code . 即可打开默认编辑器**



----
## Docker
1. windows主机上安装时，需要在启用或关闭windows功能中，开启hyper-v虚拟化技术,开启WSL2子系统功能
2. docker镜像加速，在docker desktop中点击设置，在docker engine中添加
```json
"registry-mirrors": [
    "https://2a6bf1988cb6428c877f723ec7530dbc.mirror.swr.myhuaweicloud.com",
    "https://docker.m.daocloud.io",
    "https://hub-mirror.c.163.com",
    "https://mirror.baidubce.com",
    "https://your_preferred_mirror",
    "https://dockerhub.icu",
    "https://docker.registry.cyou",
    "https://docker-cf.registry.cyou",
    "https://dockercf.jsdelivr.fyi",
    "https://docker.jsdelivr.fyi",
    "https://dockertest.jsdelivr.fyi",
    "https://mirror.aliyuncs.com",
    "https://dockerproxy.com",
    "https://mirror.baidubce.com",
    "https://docker.m.daocloud.io",
    "https://docker.nju.edu.cn",
    "https://docker.mirrors.sjtug.sjtu.edu.cn",
    "https://docker.mirrors.ustc.edu.cn",
    "https://mirror.iscas.ac.cn",
    "https://docker.rainbond.cc"
  ]
```

```shell
docker run -d nginx:latest #-d 后台运行，避免终止命令行后容器也终止
docker ps #查看正在运行的容器,包括容器id（短id）
docker ps -a #查看所有容器，包括已经终止的容器
docker inspect container_id #查看容器详细信息
docker -h # 查看帮助
docker run --h #查看run命令帮助，加双横线



# docker 容器镜像的基本操作
docker images #查看所有镜像，或者docker image list
docker pull nginx:latest #拉取镜像
docker rmi image_id #删除镜像
docker rmi $(docker images -q) #删除所有镜像

# 从docker hub上拉搜索镜像
docker search image_name




#启动一个ubuntu容器，容器名称c1，-i即交互式, -t即提供终端模式，/bin/bash即进入容器后启动bash shell以便可以在容器中执行命令和操作，
docker run -i -t --name:c1 ubuntu:latest /bin/bash 
**在容器启动时，如果不给/bin/bash这类执行命令，比如像nginx就会卡住。建议都加上/bin/bash**
如果在容器中退出/bin/bash 命令行，则容器会终止，但容器还在。

# 列出所有容器
docker ps -a #查看所有容器，包括已经终止的容器

# 查看容器详细信息
docker inspect container_id

# 删除指定名称的容器，注意要先stop停止再删除
docker rm container_name
# 批量删除容器
docker rm $(docker ps -a -q)

# 退出交互式容器，让容器仍然处于后台运行的方式
按住ctrl+p+q
# 退出交互式容器后，不进入容器而继续执行容器的命令
docker exec -it container_name ls /root


# 进入到容器中(类似于ssh登录到远程服务器)
docker attach container_name

# 停止容器
docker stop container_name
# 批量停止容器
docker stop $(docker ps -a -q)

# 启动容器
docker start container_name
# 批量启动容器
docker start $(docker ps -a -q)

# 查看容器内的进程信息
docker top container_name

# 查看容器占用资源情况，--no-stream参数指取的是某个时间点的情况，不是连续动态的
docker stats --no-stream container_name


# docker prune命令，用来清理docker中的资源，包括未使用的容器、镜像、卷和网络
# 删除未使用的容器镜像
docker image prune

# 删除所有未使用的容器镜像
docker image prune -a

# 删除所有停止的容器
docker container prune

# 删除所有未被挂载的卷
docker volume prune

# 删除所有未被使用的网络
docker network prune

# 删除docker所有资源
docker system prune




# 容器镜像的操作
# 将当前运行容器的一些改变提交一个新的镜像
docker commit 
1. 使用ctrl+p+q退出容器，保持容器在后台运行
2. 执行docker commit container_id tage_name

# 保存镜像到本地
docker save
docker save -o centosv1.tar centos:v1

# 加载镜像，不支持使用docker export 导出的镜像
docker load
docker load -i centosv1.tar

# 导出正在运行的容器
docker export
docker export -o centosv1.tar centos:v1

# 导入容器
docker import
docker import centosv1.tar centos:v1
```

### docker容器镜像仓库
```shell
# 将镜像标记为 Docker Hub 上的仓库路径，方便后续推送
docker tag my_image:v1.0 my_dockerhub_username/my_image:v1.0

docker login #登录docker hub
docker push my_dockerhub_username/my_image:v1.0

# 从 Docker Hub 拉取镜像
docker pull my_dockerhub_username/my_image:v1.0
```

----
## Jupyter Notebook
#### 在vscode中启用jupyter进度条
1. 安装必要的扩展和库
安装ipywidgets和jupyter_contrib_nbextensions
首先，确保你已经安装了ipywidgets和jupyter_contrib_nbextensions。这些包提供了Jupyter Notebook中的交互式小部件支持。
`pip install ipywidgets jupyter_contrib_nbextensions`
或者conda安装 `conda install ipywidgets jupyter_contrib_nbextensions`

    安装VSCode的Jupyter扩展
    确保你已经在VSCode中安装了Jupyter扩展。你可以通过以下步骤安装：
    - 打开VSCode。
    - 点击左侧活动栏中的扩展图标（四个方块组成的图标）。
    - 搜索“Jupyter”并安装由Microsoft提供的Jupyter扩展。
2. 启用ipywidgets扩展
安装完ipywidgets后，需要启用它以便在Jupyter Notebook中使用：
在命令行中执行
`jupyter nbextension enable --py widgetsnbextension`

3. 使用tqdm的Jupyter兼容模式
在代码中使用tqdm时，确保导入的是Jupyter兼容的版本。你可以使用tqdm.notebook模块来确保进度条能够在Jupyter环境中正确显示。
```python
from tqdm.notebook import tqdm
for i in tqdm(range(100)):
    # 你的代码逻辑
    pass
```
4. 配置VSCode的Jupyter设置
有时VSCode的Jupyter设置可能会影响进度条的显示。你可以尝试调整以下设置：
    - 打开VSCode的设置（可以通过点击左下角的齿轮图标，然后选择“设置”）。
    - 搜索jupyter.runStartupCommands，添加如下配置以确保ipywidgets被正确加载：
```json
"jupyter.runStartupCommands": ["%matplotlib inline", "import ipywidgets as widgets"]
```

5. 确保内核重启并重新运行所有单元格
6. 结合pandas使用的示例
```python
from tqdm.notebook import tqdm

# 按证件地址中包含的村镇名称匹配支局名称
def find_support_office(pspt_address, data_project):
    for index, row in data_project.iterrows():
        if row['township_clear'] in pspt_address:
            return row['支局名称']
    return None

# 使用 tqdm 包装 apply 调用, 使用progress_apply调用
tqdm.pandas(desc="匹配支局名称")
data_pspt['村镇名称关联支局名称'] = data_pspt['PSPT_ADDRESS_CLEARN'].progress_apply(lambda x: find_support_office(x, data_project))

```

























----
<span class="success">
    test asdfds adasf dfas 
</span>

<span class="alert danger">
    test asdfds adasf dfas 
</span>

<span class="alert info">
    test asdfds adasf dfas 
</span>


<span class="alert success">
    test asdfds adasf dfas 
</span>

<div class="alert warning">python不区分单精度和双精度浮点
数，默认双精度，int也不细分short,long整型)
</div>

<div class="alert asso">python不区分单精度和双精度浮点
数，默认双精度，int也不细分short,long整型)
</div>

<div class="alert doubt">python不区分单精度和双精度浮点
数，默认双精度，int也不细分short,long整型)
</div>


