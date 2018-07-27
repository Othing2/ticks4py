#### 1. 函数接收任意个参数：
    以*开头表示任意个位置参数
    > def func(first, *args)
    以**开头表示任意个关键字参数
    > def func(first, *args, **argv)
#### 2. 函数参数元信息说明：
    以参数注解的形式，可以为参数附加上元信息，以提示程序员该函数如何使用
    def func(x:int, y:int) -> int:
        return x+y
#### 3. 函数参数指定默认值：
    一种方法是在函数定义时用’=’赋默认值，通常默认值是一个不可变量，且这个参数只绑定一次
    > def func(x, y=0)
    一种方法是调用functools.partial()为函数赋默认值，并返回一个新的可调用对象，通常在一些需要回调函数的库(如mutilprocessing)中发挥重要作用
	> new_func = functoos.partial(func, y=0)
#### 4. 函数返回多个值
只需要把要返回的变量构成一个元组返回即可
#### 5. lamda表达式
#### 6. 回调函数运行时携带一些信息
    回调函数携带的信息可以比如像调用次数等，可以用几种方法来达到这一目的：
    1) 使用functools.partial()，在给默认参数指定日志变量或全局变量
    def Handler(result, log):
            processing…
    functools.partial(Handler, log=state)
    2) 把需要携带的信息和回调函数打包成类C，在需要用回调函数的时候传递一个实例class CHander():
    def __init__(self):
        self.state=0
    def Handler(self, result):
        processing…
    3) 使用闭包来捕获状态，类似第二种方法，用一个函数打包状态变量和处理函数
    def make_handler()
            dtate =0
            def handler(result):
                Processing…
            Return hannder
    4) 使用协程
#### 7. 闭包函数