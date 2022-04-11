# 指標解説
[公式](https://getcarv.com/blog/what-carv-can-measure)
設計者はTom Gellie

# balance

正規化した![パランスグラフ]({{site.baseurl}}/assets/images/fore_after_dynamic_balance.png)を見ていただきたい。
1ターンを時間軸で記録したグラフである。
縦軸上が前、下が後ろ
正規化はおそらくヨーイング角度が変わった瞬間を0として一番前に行ったところを100 としている。

## topple

ターン前半　1/3　で外足の左右方向の加重中心がどれだけ内側に動いているかどうか？
外側を0 内側を100として正規化したグラフを使っていると考えられる。
looks at what percentage of the inside movement of the CoP was at the start of the turn, in one movement. Inside movement is the direction towards the centre of the turn. For the outside ski foot, this is from the little toe to the big toe.



## start of turn

前後方向の加重中心がターン前半 1/3 でどれだけ前に行っているか？
looks at what percentage of the forward movement of the CoP was at the start of the turn, in one movement.

## end of turn
ターン後半で外足踵に乗れているか？
前後方向の加重中心がターン後半 1/3 でどれだけ後ろに行っているか？

# edging 
## early edging 
ターン前半でどれだけエッジ角が増えているか？　かなり正確

## edge smoothness
エッジ角の変化がどれだけスムーズか　足がガタガタして振られるだけですぐに低下します。
アスファルトの上をインラインですべると、100に簡単になります。

## similarity
右エッジ角 / 左エッジ角　がどれぐらい1に近いか？
大きいエッジ角では大きい角度差でもスコアの低下は小さい。小さいエッジ角度では逆。
ぼこぼこだとすぐに60ぐらいに低下する。
朝一の圧雪ならエッジ角度40で平均85は出せる。

# pressure
## pressure smoothness
加重がどれだけなめらかか？　ガタガタな場所でも低下する。
ターン前半が軽く　終盤に向かって最大 pressure をかけるようにするとハイスコアになる
一時直線での増加が一番スコアが高いはず。

## outside ski pressure
1ターンで外足加重が多い時間の割合
2021-22から氷の上でかなり踏んでもボコボコしていると70まで低下するようになった。ロシアの Thomas でもまともに滑って67の日もある。
瞬間的な圧力の大きさを考慮していた、2020-21 シーズンから指標の改定あり。
大きければ大きいほどよい。指標の設計者は80以上を理想としている。
ターン後半で内足に乗るとスコアがとても低下する。

## turn comparison
左右差

# rotary
## turn shape
ターン形状が理想的かどうか？どんなターンが理想的かは正確にわかっていない。
おそらく角速度がターン後半で増していかないターンが理想だと考えている模様。


## parallel ski
yawing と edge similarity も考慮した スキーの平行度　ヨーイングは振動で不正確になるのだが、何で補正しているのか不明。
ボコボコしていると信頼性が下がる。

## 20-21

- foot roll 導入
- turn shape 導入

## 21-22

- forward stance -> start of turn 改名
- end of turn 導入
- toppling 導入
- foot roll 消去
- rotary 削除　高速時に磁気センサーのノイズが大きすぎたため開発を放棄