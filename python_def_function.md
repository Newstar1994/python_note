# python_def_function

## def 函数

Python 使用`def`定义函数，`def`后空格跟着函数名，括号内为函数的参数

```python
def function_name([parmeter1],...):
	expressions
```
- Python中`def`是可执行的代码，直到Python运行了`def`后，定义的函数才存在。Python运行到def语句时，将会生成一个新的函数对象并将其赋值给这个函数名。函数名将成为该对象的引用。
- ***lambda*** 创建一个对象但将其作为结果返回
- ***return*** 将一个结果对象发送给调用者
- ***yield*** 向调用者发回一个结果对象，但记住它离开的地方
- ***global*** 声明一个模块级的变量并被赋值
### 本地变量
所有在函数内部进行赋值的变量名都默认为本地变量。

参数通过赋值被传入，也是本地变量。

## python的作用域
- 变量在def内赋值，则其作用域在这个函数内
- 变量在一个嵌套的def中赋值，它对于嵌套函数来说是非本地的
- 在def之外赋值的变量属于整个文件全局
###作用域规则
LEGB
### 内置作用域
通过 \_\_builtin\_\_导入
### global
global语句声明全局变量。全局变量在函数内被赋值时，必须声明，引用可以不声明。

## python函数中的参数
- 不可变对象赋值传递
- 可变对象相当于指针传递，在函数内部可以进行原处的改变
### 参数匹配
- 位置：从左至右匹配
- 关键字：通过参数名匹配
- 默认参数：为没有传入的参数定义默认值
- 可变参数： 收集任意多的基于位置或者关键字的参数
- 可变参数解包：传递任意多的基于位置或者关键字的参数
- keyword-only参数：参数必须按照名称传递
#### 参数顺序
- 调用：任何位置参数(value)、关键字参数(name=value)和\*sequence的组合、\*\*dict
- 定义：name、name=value、 \*name、Keyword-only、\*\*name

> 任意函数可以用一下方式定义：`universal_func(*args, **kw)`

#### 解包参数
```python
def func(a,b,c,d):print(a,b,c,d)
args = (1,2)
args += (3,4)
func(*args)
args = {'a':1,'b':2,'c':3}
args['d'] = 4
func(**args)
```
使用 `*`语法，能够通过一个元组向函数传递多个参数  
使用`**`语法，能够以键/值得形式解包一个字典

---
```python
def tracer(func, *pargs, **kargs):
	print('calling:', func.__name__)
	return func(*pargs, **kargs)
```
#### Keyword-only参数
Keyword-only参数出现在\*args之后，\*\*args之前。调用时必须以关键字传入。  
一个单独的\*\*不能出现在参数列表中。  

## lambda匿名函数
lambda表达式：
```
lambda argument1, argument2,... argumentN : expersion using arguments
```
lambda表达式返回函数对象。
- lambda是一个表达式，而非语句
- lambda的主体是一个单个的表达式，而不是一个代码块
## 其他
map， filter， reduce




