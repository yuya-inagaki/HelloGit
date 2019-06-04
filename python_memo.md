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
class クラス名:
	pass (何も処理がない)
```

## クラスの中に処理を追加する

```python
class クラス名:
	def hello(self): #第一引数にselfを追加する
		print('こんにちは')
```
