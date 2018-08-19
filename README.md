# iris-study
IRIS classification with Nueral Network 

## 1. iris-study の目的
* iris-study は、Deep Learning における Nueral Network 作成に関するレポートである
* iris-study は、DL用のフレームワークやライブラリを使わずに作成
* sklearn の IRIS Dataset を用いて、iris の雄しべと雌しべの長さと幅から種類を予測する
* 事前データ
    入力データ ['sepal length (cm)', 'sepal width (cm)', 'petal length (cm)', 'petal width (cm)']
    訓練データ ['setosa', 'versicolor', 'virginica']

* Nueral Network の基本的な構成
    入力層
    隠れ層１ - 64 Nueron
    ドロップアウト層１
    活性化関数(ReLU)
    隠れ層２ - 128 Nueron
    ドロップアウト層２
    活性化関数(ReLU)
    隠れ層３ - 128 Nueron
    ドロップアウト層３
    活性化関数(ReLU)
    出力層（Softmax)
    
    学習データ 120
    テストデータ 30
    バッチサイズ 40
    
    誤差関数　クロスエントロピー
    重みの初期値設定  He
    学習率最適化手法 Adam
    学習率 0.001
    L2正則化
    ドロップアウト 0.3
    

## 2. 主な関数
* relu(x)
** ReLU関数
* softmax(x)
    * ソフトマックス関数
* d_relu(x)
    * ReLU関数の導関数
* d_softmax_with_loss
    * ソフトマックスとクロスエントロピーの複合導関数
* cross_entropy_error(d, y)
    * クロスエントロピー関数
* accuracy(d, y)
    * 精度計算
* init_network()
    * ネットワークの重みとバイアスの初期値設定 (He)
* Dropout
    * ドロップアウトのクラス
    * メソッド
        * forward(x, train_flg)
        * backward(dout)
* forward(network, x, train_fg)
    * ネットワークの順伝搬
* backward(x, d, z1, z2, z3, y, dropout)
    * ネットワークの誤差逆伝搬
    
