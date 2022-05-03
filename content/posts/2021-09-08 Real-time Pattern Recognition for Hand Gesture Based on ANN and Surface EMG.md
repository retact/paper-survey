
---
author: "retact"
title: "Real Time Pattern Recognition for Hand Gesture Based on ANN and Surface EMG"
date: 2021-09-08
draft: false
description: "description"
tags: [
    "EMG",
    "Real-Time"
]

---

## 1. どんなもの？
 フィードフォワードの3層ANNを用いた5クラスのジェスチャーのリアルタイム分類について記述されている．手法として，スライドウィンドウ法をもちいて，4つの時間的特徴とHjorthParametersを元に特徴量ベクトルを作成し，平均応答速度を300msに押さえ分類精度は96％を示している．またそれぞれの特徴の筋電的な意味についても述べられている．  


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● 先行研究と比べて，300msのレスポンスをANNを用いて行っている点，さらにクラスは5であるもののMyoをつかった分類精度は96%を示している点.


## 3. 技術や手法の"キモ"はどこにある？
 ● スライドウィンドウ法  
 ウィンドウサイズやスライドサイズについては明記されていなかったがスライドウィンドウ法を用いている．おそらくウィンドウサイズは移動平均で使うデータに合わせてあると考える．またこのスライドウィンドウで算出した特徴量ベクトルを構築し入力している．  
 ● Hjorth Parameters  
 特徴量として，HjorthParametersも時間的特徴と共に利用しており，ActivityとMObilityとComplexityの統計的特性の指標として明記されている．  
 ● 学習時間が短いこと  
 今回の分類を行うためにおこなったトレーニングデータの取得は30回のみ出会ったために実用的な義手を考える上では重要な点であると考える．    

## 4. どうやって有効だと検証した？
 ● Restも含めた6のジェスチャーを各5回計測し合計30のデータを用いて学習し，テストデータではそのセットを5つ取得し，150のデータサンプルを用いて，過去の研究の分類精度を比較している．  
なおデータ取得のプロセスと人数などについては明記されていない．  
![Confusion matrix of the results](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8770353/8785424/8785894/yang4-p4-yang-small.gif)  
![Hand Getures activity time and response time](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8770353/8785424/8785894/yang.t1-p4-yang-small.gif)
## 5. 議論はあるか？
● 他のメソッドについて明記されていない．  
● 識別精度と応答速度の向上  
## 6. 次に読むべき論文はあるか？
ANNを利用した分類について  
-[Electromygraphy (EMG) signal based hand gesture recognition using artificial neural network (ANN)](https://ieeexplore.ieee.org/document/5937135)

### 論文情報・リンク

- [K. Yang and Z. Zhang, "Real-time Pattern Recognition for Hand Gesture Based on ANN and Surface EMG," 2019 IEEE 8th Joint International Information Technology and Artificial Intelligence Conference (ITAIC), 2019, pp. 799-802, doi: 10.1109/ITAIC.2019.8785894.](https://ieeexplore.ieee.org/document/8785894)
