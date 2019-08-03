# 視覚的顕著性に関する研究メモ

## これからやることリスト
### 実験の為の準備
- アイトラッカーから視線座標の取得をできるようにする
- Python SDK で視線座標の取得、CSVへの保存

### 実験
- 実験用ウェブページの収集・スクリーンショットの取得
 - ウェブページの最上部のみに限定するかどうか...
- ユーザー実験の規模、手法を考える
- ユーザー実験の実施

### 集計
- 視線座標から顕著性マップの生成
- スクリーンショットと顕著性マップの関係の学習方法を考える
- 深層学習についての知識・技術の学習

### その他
- アイトラッカーを使用した顕著性マップの生成に関する関連研究を調査

## 既存のウェブページ視線データセット
ほとんどウェブページに関するものはなく、これまでに知っているものは以下の一つのみ
- [FIWI(Fixation in Webpage Images) dataset](https://link.springer.com/chapter/10.1007/978-3-319-10584-0_3)
 > Chengyao Shen, Qi Zhao. Webpage Saliency [ECCV 2014]
 > 149webpages / 3categories(text, pictorial, mixed) / size: 1360x768px / ages: 21-25 / free viewing

![webpagesaliency.jpg](https://www-users.cs.umn.edu/~qzhao/images/proj_webpage_saliency/example_webpage1.PNG)

## 現在取り組んでいること
- 過去の研究でどのように視線データから顕著性マップを生成しているかを確認
- 実際にその方法が可能かどうか検証実験
