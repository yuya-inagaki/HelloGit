# Pythonの覚書き

## 外部ファイルの読み込み

```
import 外部ファイル名
外部ファイル名.関数名(引数)
```

## for文

```
for 変数 in データの集まり:
    処理
```

実行１
```python
for i in range(5):
    print(i)
```

結果１
```python
0
1
2
3
4
```

実行２
```python
for i in range(1, 6):
    print(i)
```

結果２
```python
1
2
3
4
5
```

## 乱数生成

```python
import random (ランダム)
random.randint(0,2) #0~2の整数をランダムで生成
```

## クラス

```python
class クラス名:
	pass (何も処理がない)
```

## インスタンスメソッド

```python
class クラス名:
    def hello(self): #第一引数にselfを追加する
	print('こんにちは')
```


## クラスメソッド

```python
class クラス名:
    count = 0  #クラス変数
    def __init__(self):
        print('インスタンスが生成されました！')
	self.count += 1

    @classmethod
    def show_info(cls): #第一引数にclsを追加する
	print('{0} instances'.format(cls.count))
```


## __init__ メソッド
__init__メソッドは、インスタンスを生成した直後に処理を実行することができる。

```python
class MenuItem:
    def __init__(self):
        print('インスタンスが生成されました！')

menu_item1 = MenuItem()
```

## クラスを直接外部ファイルから読み込む（そのままクラス名を使用可能）

```python
form モジュール名 import クラス名1, クラス名2
```

## 四捨五入

```python
round(四捨五入したい数)
```

## 継承

```python
from モジュール名 import 親クラス名
class 子クラス名(親クラス名):
    pass
```

## super()
親クラスに定義されたインスタンスメソッドを利用する

```python
super().メソッド名()
```

## アクセス制限
Pythonには厳密なアクセス制限は存在しない。慣習的にはアンダーバーを使用しておくことになっている。

```python
class User:
    count = 0  #クラス変数
    def __init__(self, name):
	self.__name = name

tom = User("tom")
print(tom.__name) #エラーが発生する
print(tom._User__name) #これならアクセスできてしまう
```

## 多重継承

```python
class 子クラス名(親クラス名１, 親クラス名２):
```

## 例外

```python
class MyException(Exception): #独自の例外を作成
    pass

def div(a, b):
    try:
	if(b < 0):
	    raise MyException('not minus') #独自の例外を発火
	print(a/b)
    except ZeroDivisionError:
	print('not by zero!')
    except MyException as e: #MyExceptionを捕捉
	print(e)
    else:
	print('no exception!')
    finally:
	print('-end-')

div(10,0)
```

## データ型
### リスト型

```python 
scores = [40, 50]
print(scores[0])    # 40
scores[0] = 45
print(len(scores))  # 2
scores.append(100)
print(scores)       # [45, 50, 100]

for score in scores:
    print(score)

for i, score in enumerate(scores):
    print("{0}: {1}".format(i, score))
```

enumerate部分の結果
```python 
0: 40
1: 50
```

### タプル
リストとは異なり値の変更ができない
```python
items = (50, "apple", 32.5)
print(items[1]) 
items[1] = "pen" #これはエラーになる

print(list((1, 3, 5))) #タプルからリストへの変換: [1, 3, 5]
print(tuple([1, 3, 5])) #リストからタプルへの変換: (1, 3, 5)
```

### スライス
```python
scores = [40, 50, 70, 90, 60]
print(scores[1:4])  # 50, 70, 90
print(scores[:2])   # 40, 50
print(scores[3:])   # 90, 60
print(scores[-3:])  # 70, 90, 60

s = "hello"
print(s[1:4])  # ell
```

### セット
セットは順序がなく、重複を許さないデータ構造
```python
a = {5, 3, 8, 5}
print(a)       # {8, 3, 5}
print(5 in a)  # True
a.add(2)
a.remove(3)
print(a)       # {8, 2, 5}
print(len(a))  # 3

a = {1, 3, 5, 8}
b = {3, 5, 8, 9}
print(a | b)   # 和集合 {1, 3, 5, 8, 9}
print(a & b)   # 積集合 {8, 3, 5}
print(a - b)   # 差集合 {1}
```

### 辞書型
```python
sales = {"taguchi": 200, "fkoji": 400}
print(sales["taguchi"])    # 200
sales["taguchi"] = 300
sales["sasaki"] = 500
del(sales["fkoji"])
print(sales)               # {'taguchi': 300, 'sasaki': 500}

for key, value in sales.items():
    print("{0}: {1}".format(key, value))
```

## イテレータ
```python
scores = [40, 50, 70, 90, 60]
it = iter(scores)
print(next(it))  # 40
print(next(it))  # 50
print("hello")   # hello
print(next(it))  # 70

def get_infinite(): #ジェネレータ
    i = 0
    while True:
        yield i * 2 #yieldを使用することでそこで処理が一度止まる
        i += 1

g = get_infinite()
print(next(g))   # 0
print(next(g))   # 2
print(next(g))   # 4
```

### map関数
map(関数, イテレータ)

```python
def triple(n):
    Return n * 3

print(list(map(triple, [1, 2, 3])))
```

### lamda関数
lamda 引数: 処理

```python
print(list(map(lamda n: n*3, [1, 2, 3])))
```

### filter
filter(関数, イテレータ)

```python
def is_even(n):
    Return n % 2 == 0

print(list(filter(is_even, range(10))))  # [0, 2, 4, 6, 8]

# ラムダでも実装可能
print(list(filter(lamda n: n%2 == 0, range(10))))  # [0, 2, 4, 6, 8]
```

### 内包表記

```python
# 0-9
print([i for i range(10)])     # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print([i * 3 for i range(10)]) # [0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
print([i * 3 for i range(10) if i % 2 == 0]) # [0, 6, 12, 18, 24]
```