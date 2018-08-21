# iris-study
IRIS classification with Nueral Network

ソースコード: iris.ipynb

## 1. iris-study の目的
* iris-study は、Deep Learning における Nueral Network 作成に関するレポートである
* iris-study は、DL用のフレームワークやライブラリを使わずに作成
* sklearn の IRIS Dataset を用いて、iris の雄しべと雌しべの長さと幅から種類を予測する
* 使用データ
    * 入力データ: ['sepal length (cm)', 'sepal width (cm)', 'petal length (cm)', 'petal width (cm)']
    * 出力データ:  ['setosa', 'versicolor', 'virginica']

## 2. Nueral Network の構成
### 2.1 トポロジー
+ 入力層
+ 隠れ層１
    + 64 Nodes
    + ドロップアウト１
    + 活性化関数(ReLU)    
+ 隠れ層２
    + 128 Ndoes
    + ドロップアウト２
    + 活性化関数(ReLU)    
+ 隠れ層３
    + 128 Nodese
    + ドロップアウト３
    + 活性化関数(ReLU)
+ 出力層
    + 活性化関数(Softmax)

### 2.2 パラメーター
* 学習データ: 120
* テストデータ: 30
* バッチサイズ: 40
* 繰り返し: 1,000 iteration x 10 データセット
* 誤差関数:　クロスエントロピー
* 重みの初期値設定:  He
* 学習率最適化手法: Adam
* 学習率: 0.001
* L2正則化
* ドロップアウト: 0.4

## 3. ニューラルネットワークの構造図


[事前に用意する情報]

入力: <img src="https://latex.codecogs.com/gif.latex?x_n&space;=&space;[x_{n1}&space;..&space;x_{nl}]"/>

訓練データ: <img src="https://latex.codecogs.com/gif.latex?d_n&space;=&space;[d_{n1}&space;..&space;d_{nk}]"/>

[多層ネットワークのパラメータ]

重み: <img src="https://latex.codecogs.com/gif.latex?w^l&space;=&space;\left[&space;\begin{array}{rrr}&space;w^l_{11}&space;&&space;..&space;&&space;w^l_{1l}&space;\\&space;:&space;&&space;..&space;&&space;:&space;\\&space;w^l_{j1}&space;&&space;..&space;&&space;w^1_{jl}&space;\end{array}\right]"/>  

バイアス:
<img src="https://latex.codecogs.com/gif.latex?b^l&space;=&space;\left[\begin{array}{rrr}&space;b^l_1&space;..&space;b^l_j\end{array}\right]"/>

活性化関数: <img src="https://latex.codecogs.com/gif.latex?f^l(u^l)&space;=&space;[f^l(u^l_1)&space;..&space;f^l(u^l_j)]"/>

中間層出力: <img src="https://latex.codecogs.com/gif.latex?z^l&space;=&space;[z^l&space;..&space;z^k]&space;=&space;f^l(u^l)"/>

総入力: <img src="https://latex.codecogs.com/gif.latex?u^l&space;=&space;W^l&space;z^{l-1}&space;&plus;&space;b^l"/>

出力: <img src="https://latex.codecogs.com/gif.latex?y^l_n&space;=&space;[y^l_{n1}&space;..&space;y^l_{n4}]&space;=&space;z^L"/>

誤差関数: <img src="https://latex.codecogs.com/gif.latex?E^n(w)"/>

![NN Structure](nn_structure.jpg)

<img src="https://latex.codecogs.com/gif.latex?w^{l-1}&space;=&space;w^l&space;-\epsilon&space;\nabla&space;E_n(w)&space;\longleftarrow&space;\nabla&space;E_n(w)&space;=&space;\frac{\partial&space;E}{\partial&space;w}"/>



## 4. 結果

![Output](output.jpg)

## 5. 主な関数

<dl>
    <dt>relu(x)</dt>
    <dd>ReLU関数</dd>
    <dt>softmax(x)</dt>
    <dd>ソフトマックス関数</dd>
    <dt>d_relu(x)</dt>
    <dd>ReLU関数の導関数</dd>
    <dt>d_softmax_with_loss(x)</dt>
    <dd>ソフトマックスとクロスエントロピーの複合導関数</dd>
    <dt>cross_entropy_error(d, y)</dt>
    <dd>クロスエントロピー関数</dd>
    <dt>accuracy(d, y)</dt>
    <dd>精度計算</dd>
    <dt>init_network()</dt>
    <dd>ネットワークの重みとバイアスの初期値設定 (He)</dd>
    <dt>Dropout</dt>
    <dd>ドロップアウトのクラス</dd>
    <dd>メソッド<br>
        &nbsp;&nbsp;&nbsp;&nbsp;forward(x, train_flg)<br>
        &nbsp;&nbsp;&nbsp;&nbsp;backward(dout)
    </dd>
    <dt>forward(network, x, train_flg)</dt>
    <dd>ネットワークの順伝搬</dd>
    <dt>backward(x, d, z1, z2, z3, y, dropout)</dt>
    <dd>ネットワークの誤差逆伝搬</dd>
</dl>
