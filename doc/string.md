#### 1. 正则表达式：

    > r’[;,\s]\s*’ 表示分号、逗号、空格后面接0个以上的空格
    > r’(;,\s)\s*’ 表示同上，但是’()’意味着捕获组，即把出现的模式中的符号也捕获进来
    > 以‘$’结尾表示精确匹配
    > ‘.*?’表示最短匹配
    > ‘.*’表示贪婪匹配

#### 2. 字符串的拆分：

    > re.split( pattern, mystr )

#### 3. 匹配文本起始位置或结束位置

    str1=['abcd','bcde','fghhi']
    patt=(‘a’, ’b’) 
    str1[1].startswith(patt)  #匹配patt中任意一个
    str1[1].endswith(patt)

#### 4. 文本的匹配

    > str.find(sub_text)
    > re.match(patt, text)
    > re.compile(patt).findall(text)  #返回列表，如果想不区分大小写可以在findall中加入参数flags=re.IGNORECASE
    > re.compile(patt).finditer(text)  #返回生成器

#### 5. 文本的替换

    > str.replace(sub_text, string)
    > re.sub( sub_patt, patt, text)  #用后面的模式 替换 前面的模式

#### 6. 去掉文本中不需要的字符

    > str.strip()   #默认去掉开头和结尾的空格或换行符，可以输入参数
    > str.lstrip()
    > str.rstrip()

#### 7. 字符的索引

    > str.index(char, start, stop)






















