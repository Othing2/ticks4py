#### 1. 序列分解单独变量：只需要一个赋值符号‘=’
	
	如 a, b = [1,2]

#### 2. 任意长度的可迭代对象的分解：通过使用 ‘*表达式’可以得到任意长度的对象片段

	如 first, *middle, last = (‘Dave’,  ‘example@mail.com’,  ‘123’,  ’86’,  ‘234’)

#### 3. 双端队列：插入元素和弹出元素复杂度为1，而列表的复杂度为n，可用于保存最后N个元素

	From collections import deque

#### 4. 堆队列：可用于找出最大或最小的N个元素(对于不可变数据(整数、字符串、元组等)是可哈希的，可以直接比较大小；列表、字典是不可哈希的)；也可用于构建优先级队列

	'''python
	import heapq
	heapq.nlargest(N, seq) 
	heapq.nsmallest(N, seq)
	'''

#### 5. 字典：通常的用法是d={}，但是如果想要是字典里有个默认值，可以使用defaultdict

	from collections import defaultdict
	D = defaultdict(list)  #表示这个字典存储的值是列表

	例如，如果开始想要判断字典D中的列表是否有’a’
	D={}     
	D[‘s’].append(‘a’)  #程序出错
	D=defaultdict(list)
	D[‘s’].append(‘a’)  #成功

#### 6. 有序字典OrderedDict：让存储的元素保持 其插入的顺序，内部维护一个双端列表。可用于类似在JOSN编码时需要精确控制各个字段的顺序；

	From collections import OrderedDict

#### 7. 字典有关的计算：常使用zip()函数，将字典的键、值翻转过来，构建元组，返回一个迭代器

	dict_iter = zip(dict.values(), dict.keys())
	min(dict_iter), max(dict_iter)

	字典的集合操作：

	> 键交集dict1.keys() & dict2.keys()

	> 项交集dict1.items() & dict2.items()

	> 键并集dict1.keys() | dict2.keys()

	> 项并集dict1.items() | dict2.items()

	> 键差集dict1.keys() - dict2.keys()

	> 项差集dict1.items() – dict2.items()

	字典的值不支持集合操作

	参考collection.ChainMap构建多个字典映射到单个字典

#### 8. 集合：可以用于去掉重复项，但是不保证元素的顺序不变

	set(seq)
	如果想去掉重复项，而保持顺序，需要自己构建一个新的方法
	'''python
	def deset(items, key=None):
		seen=set()
		for item in items:
			val = item if key is None else key(item)
			if val not in seen:
				yied item
				seen.add(val)
	'''
	这个函数模拟sort()、min()、max()、itertools.groupby()（字典或对象分组）对key的处理，可以不可哈希元素通过key函数变成可哈希的，可参考operator.itemgetter()和operator.attrgetter()；并且使用生成器，可以使得方法更通用，而不必绑定只对列表的处理

### 9. 命名元组：通过名称来访问元素，以减少对结构中位置的依赖性，比如在表单中新增一列数据，那么代码就可能崩溃。

	From collections import namedtuple
	row=[‘id’,‘name’,’addr’]  #构建表单访问列，如果表单列变化了，只需要改变这个列表
	Subscrib = namedtuple(‘Subscrib’, row) #构建一个名为’Subscrib’的命名元组类
	sub=Subscrib(*element) #用element填充列表row，并且element的列数也要相同
	sub.id
	sub.name
	sub.addr
	sub._replace(id=123)  #改变元素的值

#### 10. 对列表进行统计：统计相同元素的个数

	From collections import Counter
	Cnt1=Counter(dict1)  #返回一个类似字典的对象
	Cnt2=Counter(dict2)
	Cntp=Cnt1+Cnt2  #数学运算，类似字典的items()并集
	Cntd=Cnt1-Cnt2  #差集

#### 11. 过滤：字典推导式、列表推导式（容易消耗内存）、生成器表达式、filter()
	'''python
	values1=[1,2,3,-1,0]
	[ n for n in values if n >0 ]  #列表推导式
	( n for n in values if n>0 )  #生成器表达式
	gen=filter(fun, values)  #输入fun表示过滤函数，返回生成器
	mydict = {‘a’:1, ‘b’:2, ’c’:-1, ‘d’:0}
	{ key:value for key, value in mydict.items() if value>0 } #字典推导式
	'''













