#### 1. 魔法方法：
    > 迭代
    __iter__(): 构建迭代器
    __next__(): 获取迭代器下一个值
    __reversed__(): 构建反向迭代，配合内建的reversed()函数

    > 终端显示
    __repr__(): 构建可用于直接显示实例信息的类
    __str__():构建可用于print()的类
    __format__():勾践剑类的格式化输出信息，配合内建的format()函数使用

    > 长度
    __len__(): 计算对象长度

    > 上下文管理器
    __enter__():构建上下文管理的进入 with语句刚开始执行的状态，并把结果赋as
    __exit__():构建上下文管理的退出 with语句执行完之后的状态

    > 描述器
    __getattr__():获取类中的一个属性，搭配getattr()函数
    __setattr__():为类中的属性赋值， 搭配setarrt()函数
    __getitem__():通过类似字典的形式获取类中属性的值
    __setitem__():通过类似字典的形式设置类中属性的值
    __get__():
    __set__():
    __delete__()

#### 2. 魔法属性：
    __slot__: 这个作为类的属性，可以在创建大量对象是减少内存的使用
    __dict__:获取类中的属性字典




