#### 1. 类的私有属性：通常以’_’或’__’来表示
#### 2. 类的可管理属性
    在对属性获取(getter)和设置(setter)上，需要增加额外的处理过程（类型检查、验证等），可以将其定义为property，即把类中定义的方法当属性来使用。然后根据访问属性的不同方式会触发getter、setter、deleter方法
    @property
    def first_name(self):  #getter方法
        return _first_name
    @first_name.setter
    def first_name(self, value):  #setter方法
        checking…
        self._first_name = value
    @first_name.deleter     #deleter方法
    def first_name(self):
        checking…
#### 3. 调用父类方法
    通常使用super()函数，在继承中，尽量在初始化时使用一次该函数
		