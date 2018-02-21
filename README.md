
# モチベーション
- pythonのGUIでゲーム作りたい
- 最初は簡単なものから
- 機械学習もやってみたい

# Gomoku_Tkinter
PythonのTkinterを使って五目並べを作りました．  
`Python Gomoku.py`でプレイヤー選択画面が表示される  
プレイヤーを選択してスタートボタンでゲーム開始

# 作成したプレイヤー
- 人間
	- ボタンが表示されるのでクリックして石を置く
	- コンピュータ同士の場合は描画追いつかないのでボタンは表示されない

- ランダム君(RandomPlayer)
	- 空いているマスをランダムに選択する
	- 負けたら恥  

- 強いランダム君(AlphaRandomPlayer)
	- 基本的にランダムに置く
	- 3つ並んでいたらその両端に置く（石の色関係なく）  

- モンテカルロ君(MonteCalroPlayer)
	- 空いているマス全てに置いて最後まで戦い，評価の高いマスに置く
	- 時間がかかるにもかかわらず弱いためプレイヤーとして選択できないようにしている  

- DQN
	- DeepLearningをした脳みそで戦う
	- 既に置いてあるマスに置く可能性あり（確率は低い）

# DeepLearning
少し勉強すればできるだろうと思っていたがそんなことなかった.  
ハイパーパラメータが多くて試行錯誤した.正解にたどり着いたとは思っていない  
最初は10✕10の盤面だったが，状態数が多すぎるので7✕7でやってみた．  
  

入力層 47個  
隠れ層（２つ）98個  
出力層 47個  

入力層と出力層は盤面の数，隠れ層はテキトーに盤面の２倍にしてみた.  
LeakyRelu？Adam？正直わかっていない  
  
最初は空いているマスを０で表現してたけど，なかなか学習しなかった．  
空いているマス＝置いてほしいマス＝情報を増やす？  
情報が伝達してないと思い，空いているマスを３と表現したらうまくいった．  
ここまできてやっとルールを覚えた感じ．




