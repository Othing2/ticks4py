#### 1. 构建迭代器：
    python的迭代协议要求：
    > 对象的__iter__()方法返回一个可迭代对象，并且要实现__next__()方法，并使用StopIteration异常来通知迭代完成。
#### 2.构建__iter__()方法：
    两种简单的方法： 使用内建的iter()函数； 使用yield生成器
#### 3. 反向迭代
    对象需要构建__reversed__()方法，这个方法是一个生成器函数，配合内建的reversed()函数
#### 4. 迭代切片
    普通的切片操作符不管用，需要itertools.islice()方法
From itertools import islice
#### 5. 丢弃前几个元素
    itertools.dropwhile(func, iterable_seq)
#### 6. 迭代所有组合
    itertools.permutations(seq)
    itertools.combinations(seq)
#### 7. 迭代元素值和索引
    enumerate()
#### 8. 迭代多个序列
    zip(seq1, seq2)
    itertools.chain(seq1, seq2)
#### 9. yield from
    从一个可迭代对象中返回其所有的元素
    for it in iterable_seq:
        if isinstance(it iterable):
            yield from it














