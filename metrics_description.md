# 指標解説
[公式](https://getcarv.com/blog/what-carv-can-measure)
設計者はTom Gellie
Designed by Tom Gellie.

# balance

正規化した
![パランスグラフ]({{site.baseurl}}/assets/images/fore_after_dynamic_balance.png)を見ていただきたい。
1ターンを時間軸で記録したグラフである。
縦軸上が前、下が後ろ
正規化はターンごとに行うのではなく、一番うしろのセンサーに加重中心がある場合を0として一番前に行ったところを100 としている。

This is the normalized place of center of pressure graph.
The X axis is time, Y axis is center of pressure(CoP).
I guess Y axis is normalized by the moment when the X axis is 0 and maximum Y is 100. Please ask it to official.
Y = 0 is after, Y = 100 is fore.
X is absolute time duration.

## topple

ターン前半　1/3　で外足の左右方向の加重中心がどれだけ内側にあるかどうか？
外側を0 内側を100として正規化したグラフを使っている。
ターン1/3を通した圧力の合計も算出に使っている。

looks at what percentage of the inside movement of the CoP was at the start of the turn, in one movement. Inside movement is the direction towards the centre of the turn. For the outside ski foot, this is from the little toe to the big toe.

in 0-33% of X how much outside normalized sideways CoP movement is achieved.

### Why topple is needed
膝関節中心から横方向のスキーセンターに対して1mm以下の誤差になるような精度で力を加える。なおかつエッジが立っていて支持基底点はエッジにあるとする。
その場合、ロール角を減少させてエッジを完全に寝かせる方向に引き起こす力が働く。それを打ち消す反力を膝関節からスキーセンターに対して押す力の方向を変えずに発生させるために、拇指球に加重中心を移動させるのがTopple である。

## start of turn

前後方向の加重中心がターン前半 ２０％ でどれだけ前に行っているか？

looks at what percentage of the forward movement of the CoP was at the start of the turn, in one movement.
In this graph is 100.

この数値はとても上げるのが難しいが、とても重要な指標である。

fore after balance モニターモードを使用した、バランス指標の改善方法。

ターン20%の時間めいいっぱい前を踏めるようにする。
インラインスケートにおいて
バランスモニターモードで60をターゲットに滑る
60-55が正常範囲として、間違えるなら60以上になるように滑る。
切り替え前に前に加重中心を置く。

５５以下になるということは、ターン切り替え時から前に加重ができていないので、ターン後端の踵加重を失っても前に加重する。

加重中心を素早く入れ替えるためには、ターン切り替え時にブーツが潰れていた方がすぐにブーツの反発を使って前に加重できる。なのでターン後半の踵加重をしている時にできるだけブーツを潰す練習をしてみる。それができないのであれば、ブーツを潰し続けて滑ってみて、そこからブーツの反発で元に戻っていい区間を増やしていく。

ターン後半には必ず一回は踵後端に加重中心を移動する。
数字が正常範囲内であれば踵加重指標をできるだけ高くする。
浅い20度ぐらいのエッジアングルで start of turn が80以上になるように練習する。指先まで使って加重中心を前にした時に、93を超えるようにする。
それができたらエッジアングルを高くしていき、40度付近で start of turn を80以上に保てるように努力する。

ターン切り替え時に地面と垂直方向の圧力があったほうが、素早く前に圧力が移動できるのでターン後半で足を曲げて切り替え時に立ち上がることで圧力を増して数値が変化することを実感すると良い。正常系はストレッチングターンなのでこのようなベンティングではなく、ターン後編でポンピングすることで、乗り物が前に推進されてわずかに加重中心が前に行くだけで、前のターンと逆方向の角加速度が発生しそれによって加重中心がより素早く前に移動するようにする。
ターン後半に踵をフォールラインと逆方向に移動させることでポンピングによる推進力をより得られるはず。

指を使って踏んだ方が加重中心が前に行くのでスコアが上がります。しかし、あまりやると疲れるので普段の練習では母指球まで前に加重中心を移動させて、踏んでいる時間を長くすることでスコアを上げましょう。ターン前半20%を超えたら踵加重にしないでスコアを上げても　end of turn スコアは下がります。


インラインでもエッジ角が60度付近でも継続して55以上を保てるようになれば合格。
## end of turn
ターン後半で外足踵に乗れているか？
前後方向の加重中心がターン後半 2/3 でどれだけ後ろに行っているか？

looks at what percentage of the backward movement of the CoP was at the end of the turn, in one movement.
In this graph is around 90 

ターン終端付近で、かかとの圧力マップが黒くなるぐらい踏み込むと高くなる。

# edging 
## early edging 
ターン前半でどれだけエッジ角が増えているか？　かなり正確
これが減るときは、ターンの切り替え時に重心が雪面に対して垂直よりもゴールと逆側に離れている量が大きいことが原因である。
ターン前半での角速度が大きいほどこの数値が増えるということは、角速度が大きくなってから切り替えれば良い。
倒す速度全体を大きくする必要はないのである。

How much the edge angle was increased at the start of the turn, in one movement. This metric has big noise endurance.

次の支持基底点と重心の位置をフォールライン上から見てできるだけ離す。
支持基底点は重心よりも山側にあるとする。

具体的な手順
ターン切り替え前に重心をめいいっぱい谷側に持っていく
ターン始動時のトップ加重が維持できる範囲で、スタンスを広げる。
次の内足が倒れるのを邪魔しないように内足の膝下をを思い切り内転させて足が浮くぐらいガニ股になる。

平地のインラインではこれだけで平均60まで持っていけるはず。より点数を上げたいならくの字になる操作を行うがそれは異常系なので積極的にやらない方がいい。遊びで少々倒して平地でも70以上は1ターン限りならいつでも出せるようにしておくと良い。
この指標は意外に正確である。斜度１２度あるなら９９以上で安定して巡航できるように練習するべき。

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

