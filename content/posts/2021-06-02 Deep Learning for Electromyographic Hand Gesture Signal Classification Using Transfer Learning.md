

---
author: "retact"
title: "Deep Learning for Electromyographic Hand Gesture Signal Classification Using Transfer Learning"
date: "2021-06-02"
description: "CWTネットワークを用いた転移学習を利用したジェスチャー分類について"
tags: [
    "EMG",
    "GR"
]
---

## 1. どんなもの？
転移学習を利用し、推定精度を向上させる手法の提案。深層学習に用いる2つのデータセットは19人,17人の健常者から取得し、NinaProDB5
を活用しており、それぞれに対してraw EMG, spectrograms,continuous wavelet transform (CWT)を用いたネットワークを構築し推定精度を比較したところ、
CWTベースのConvNetでは17人の参加者の7つのジェスチャーに対して98.31％、生のEMGベースのConvNetでは10人の参加者の18のジェスチャーに対して68.98％のオフライン精度を達成している。
またこの論文ではConvNetの性能を体系的かつ大幅に向上させる新しい転移学習スキームを紹介している。   

<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● これまでの一般的な深層学習では一人のユーザーが一度に何万もの例を生成する必要があり、これは現実的ではない  
 ● CWTは筋電信号の分析のために提案されているがsEMGに基づく手のジェスチャー認識の分類のための特徴として採用されたのは初めてらしい  
## 2.1 わからないこと  
 ● ウィンドウサイズ、ウィンドウオーバーラップについて  
 ● 時間的特徴におけるSkewnessについて  
 ● ファインチューリング  


## 3. 技術や手法の"キモ"はどこにある？
 ● Myoの2つの新しいデータセット 
 デバイスはMyoを使い,260msのウィンドウサイズの2つのデータセットのうち、一つは事前学習用のデータセットで、もう一つは評価用のデータセット  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/8684927/8630679/cotea1-2896269-small.gif)  
 ● NinaPro DB5  
 合計53種類の動作  

 ● クラシックなsEMG分類  
本実験で用いられる分類器はSVM,ANN,RF,KNN,LDAで、ハイパーパラメータはランダム検索と並行して3回のクロスバリデーションを行い，各参加者のデータセットについて，各分類器のハイパーパラメータの50種類の組み合わせをテストすることで選択している。また、使用されている特徴量は
MAV,ZC,SSC,WLのTDと、RMS,IEMG,AR,SkewnessのETDと、ninaproにおいて、RMS,mDWT,HISTと時間的特徴,SampEn Pipelineのパラメータを用いている。  
  
 ● Deep Learning Classifiers Overview  
 slow-fusionモデルのCNNでオーバーフィッティングの問題に対処するため、MC Dropout,バッチの正規化および早期停止をする。  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/8684927/8630679/cotea3-2896269-small.gif)  
 ● Transfer Learning  
 PNNをもちいて、ファインチューリングにおけるcatastrophic forgettingを防いでいる。
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/8684927/8630679/cotea4-2896269-small.gif)  

## 4. どうやって有効だと検証した？
 ● 

## 5. 議論はあるか？
 ● 上肢切断者に適用してテストすること  
 ● オンライン制御  

## 6. 次に読むべき論文はあるか？
 ● 筋電義手における非深層学習のTLハイパーパラメータなど  
 [V. Gregori, A. Gijsberts and B. Caputo, "Adaptive learning to speed-up control of prosthetic hands: A few things everybody should know," 2017 International Conference on Rehabilitation Robotics (ICORR), 2017, pp. 1130-1135, doi: 10.1109/ICORR.2017.8009401.](https://ieeexplore.ieee.org/document/8009401)  
 ● ビッグデータと深層学習を用いた筋電図パターン認識について
 [Phinyomark, A.; Scheme, E. EMG Pattern Recognition in the Era of Big Data and Deep Learning. Big Data Cogn. Comput. 2018, 2, 21. https://doi.org/10.3390/bdcc2030021](https://www.mdpi.com/2504-2289/2/3/21/htm)  
 ● ウェアラブル筋電センサの特徴抽出の選択  
 [A. Phinyomark, R. N. Khushaba and E. Scheme, "Feature extraction and selection for myoelectric control based on wearable EMG sensors", Sensors, vol. 18, no. 5, pp. 1615, 2018.](https://pubmed.ncbi.nlm.nih.gov/29783659/)  

### 論文情報・リンク

- [U. Côté-Allard et al., "Deep Learning for Electromyographic Hand Gesture Signal Classification Using Transfer Learning," in IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 27, no. 4, pp. 760-771, April 2019, doi: 10.1109/TNSRE.2019.2896269.](https://ieeexplore.ieee.org/document/8630679)

