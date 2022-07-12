# 指標解説
[公式](https://getcarv.com/blog/what-carv-can-measure)
設計者はTom Gellie
Designed by Tom Gellie.

# balance

正規化した
![パランスグラフ]({{site.baseurl}}/assets/images/fore_after_dynamic_balance.png)を見ていただきたい。
1ターンを時間軸で記録したグラフである。
縦軸上が前、下が後ろ
正規化はおそらくヨーイング角度が変わった瞬間を0として一番前に行ったところを100 としている。

This is the normalized place of center of pressure graph.
The X axis is time, Y axis is center of pressure(CoP).
I guess Y axis is normalized by the moment when the X axis is 0 and maximum Y is 100. Please ask it to official.
Y = 0 is after, Y = 100 is fore.
X is absolute time duration.

## topple

ターン前半　1/3　で外足の左右方向の加重中心がどれだけ内側に動いているかどうか？
外側を0 内側を100として正規化したグラフを使っていると考えられる。

looks at what percentage of the inside movement of the CoP was at the start of the turn, in one movement. Inside movement is the direction towards the centre of the turn. For the outside ski foot, this is from the little toe to the big toe.

in 0-33% of X how much outside normalized sideways CoP movement is achieved.

## start of turn

前後方向の加重中心がターン前半 1/3 でどれだけ前に行っているか？

looks at what percentage of the forward movement of the CoP was at the start of the turn, in one movement.
In this graph is 100.

## end of turn
ターン後半で外足踵に乗れているか？
前後方向の加重中心がターン後半 1/3 でどれだけ後ろに行っているか？

looks at what percentage of the backward movement of the CoP was at the end of the turn, in one movement.
In this graph is around 90 - 100.

# edging 
## early edging 
ターン前半でどれだけエッジ角が増えているか？　かなり正確
これが減るときは、ターンの切り替え時に重心が雪面に対して垂直よりもゴールと逆側に離れている量が大きいことが原因である。
ターン前半での角速度が大きいほどこの数値が増えるということは、角速度が大きくなってから切り替えれば良い。
倒す速度全体を大きくする必要はないのである。

How much the edge angle was increased at the start of the turn, in one movement. This metric has big noise endurance.

## edge smoothness
エッジ角の変化がどれだけスムーズか　足がガタガタして振られるだけですぐに低下します。
アスファルトの上をインラインですべると、100に簡単になります。

How the roll angle changing was smooth. This metric has little noise endurance.
Easily reaches 100 when you on inline skate.

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
このスコアが低い場合、踏む強さよりも踏み終わるタイミングが早いことが原因の場合が多い。
ターン後半まで踏み続けて次のターンまで圧力が突き抜けているグラフが表示される段階になってから、ターン前半からの踏み込みを意識すると良い。


Sum of time duration in one turn when the outside ski pressure was higher than 8:2.
That is easily get low score when you were raising your body by inside ski pressure in turn end.
Officially 80 is the ideal value. but I think 100 is the best.
Because raise and push center of mass to next turn by inside ski pressure, that is obstacle of speed.
I can push my body to next turn only by outside ski pressure before intermediate of turn.


## turn comparison
左右差 これは outside ski pressure の数値の左右差である。
balance of average of outside ski pressure score, not considering balance of pressure smoothness.

# rotary
## turn shape
ターン形状が理想的かどうか？どんなターンが理想的かは正確にわかっていない。
おそらく角速度がターン後半で増していかないターンが理想だと考えている模様。

Turn shape is round or not.
I guess, constant yawing rotation rate turn is the best. Carv team don't answer it.


## parallel ski
yawing と edge similarity も考慮した スキーの平行度　ヨーイングは振動で不正確になるのだが、何で補正しているのか不明。
ボコボコしていると信頼性が下がる。

It is considered yawing and rolling angle similarity. yawing has low endurance to noise,
but this feature has big noise endurance than only yawing.

## changing history
### 20-21

- 導入　foot roll is in
- 導入　turn shape is in

### 21-22

- forward stance -> start of turn renamed
- 導入　end of turn is in
- 導入　toppling is in
- 削除　foot roll is out
- 削除　rotary is out　高速時に磁気センサーのノイズが大きすぎたため開発を放棄

# ベンディングとストレッチングの使い分けの基準
ターン後半で体をスキーの進行方向に対してロールする力が足りないときに、雪面と重心の距離を近くすることで、ターン切替時に雪面に対して垂直に重心を持っていくことがベンディング。
ストレッチングだと、ロールするために重心を次のターンの内側に運ぶ筋力がより大きく要求される。

