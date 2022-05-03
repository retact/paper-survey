
---
author: "retact"
title: "Deep Learning for Electromyographic Hand Gesture Signal Classification Using Transfer Learning"
date: 2022-05-02T12:50:42+09:00
draft: true
description: "description"
tags: [
    "EMG",
    "Transfer Learning"
]

---

## 1. どんなもの？
Tlを用いて，複数のユーザー間から取得されたデータを用いて，簡易的にジェスチャー分類タスクの学習を行う手法を提示している．  
 タスクとしては2つのデータセットを取得し，Ninaproを合わせた3つのデータベースで,CWT,rawEMG,スペクトログラムのそれぞれ3つの異なる入力のネットワークを用い，その有用性を示している．  
 また，real-time feedbackをもちいたユースケースにおいて，精度劣化を軽減させることを示している．  


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● 深層学習  
 特徴工学から特養学習へのパラダイムシフト  
 
 ● 学習時間  
 一人のユーザーから何万ものデータを学習させることは現実的でないが，事前学習を行なったモデルを用いるTLによって，簡易的な学習で同精度の成果を出すことができる．  
  
 ● CWT  
 計算量はDWTとWPTの方が少ないもののConvNetを活用するための魅力的な画像的表現を提供することができ,組み込みシステムで効率的に実装することができる．
 

## 3. 技術や手法の"キモ"はどこにある？
 ● CNNアーキテクチャ   
 slow-fusion ConvNet architectureを用いている.  
  ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/8684927/8630679/cotea3-2896269-large.gif)  
  
 ●Transfer learning  
 もっともアクティブなチャンネルを特定し，アライメントを行う.  
 Fine-tuningにはcotastrophic fogettingが存在し，タスクにうまく適用しないネットワークに偏る可能性があるためPNNを用い重みを凍結することで解消する．
 Source NetworkとSecond Networkを組み合わせたTargetNetworkを構築する．  
  ![Figure](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/8684927/8630679/cotea4-2896269-large.gif)  
  

 ● Continuous Wavelet Transform (CWT)  
 入力はCWTの場合は時間×空間×スケールで構成することができる。このように、低速融合アーキテクチャに基づくConvNetを用いる動機は、動画データと提案するsEMG信号の特徴付けが類似した構造を持ち（動画の場合は時間×空間×空間）、非定常情報を記述できることに起因している．  
  

## 4. どうやって有効だと検証した？
 ● それぞれのデータセットに対し，TLとの比較，state of artとの比較，サンプル外のジェスチャーの比較をし，TLConvNetsは訓練サイクル数に関係なく、非拡張バージョンを有意に上回ったことを示している．
## 5. 議論はあるか？
 ● 提案するTL方式の限界は、新しいユーザーが事前トレーニングに使用したグループと同じ量の電極を装着できない場合、適応が難しい  

## 6. 次に読むべき論文はあるか？

### 論文情報・リンク

- [U. Côté-Allard et al., "Deep Learning for Electromyographic Hand Gesture Signal Classification Using Transfer Learning," in IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 27, no. 4, pp. 760-771, April 2019, doi: 10.1109/TNSRE.2019.2896269.](https://ieeexplore.ieee.org/document/8630679)
