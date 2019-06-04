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

## クラスの中に処理を追加する

```python
class クラス名:
	def hello(self): #第一引数にselfを追加する
		print('こんにちは')
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
form モジュール名 import クラス名
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