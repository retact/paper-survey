
---
author: "retact"
title: "An Online SEMG Motion Classification Framework for Tele Operating the Robotic Hand"
date: 2021-07-29
draft: false
description: "An Online sEMG Motion Classification Framework for Tele-operating the Robotic Hand"
tags: [
    "EMG"
]

---

## 1. どんなもの？
ロボットハンドを動かすためのオンラインsEMG動作分類のフレームワークを提案している．オフライン学習とオンライン認識フェーズで構成されており，オフラインフェーズでは3つの分類器を比較し，オンラインフェーズでは2つの閾値を用いたデータセグメンテーションが設計されている．5つ分類において73.56%の総合精度を示した．  

<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● sEMGデコーディングにおいて深層学習による分類が行われてきたが，これらのアルゴリズムは時間的なコストがかかるのでオンラインロボットアプリケーションには適していない.  

## 3. 技術や手法の"キモ"はどこにある？
 ● システムのフレームワーク  
 オンラインとオフラインの2つのフェーズによって処理される．  
 オンラインフェーズでは、分類器がTCP/IPプロトコルで予測ラベルを送信し、ロボットハンドがROS端末でそのコマンドをデコードする仕組みになっている.  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng3-p6-zheng-small.gif)  
 ● オフラインフェーズ  
 特徴量抽出においてRMS,MAV,ZC,SCCの4つを選択し，その後ピアソン相関係数を出したのち，
 3つの時間的領域を選択する.その後分類ではKNN,SVM,ANNのアルゴリズムが検討された結果,RMSとMAVには強い相関があったためRMSを取り除き,最終的に一番精度の良いANNを選択している  

 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng5-p6-zheng-small.gif)  
   
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng.t1-p6-zheng-small.gif)  

 ● オンラインフェーズ  
 データセグメンテーションではRMSを追跡し，一定の値を超える時を開始点，下回った時を終了する点としている．また投票方式では計算速度の観点で多数決方を利用している．  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng7-p6-zheng-small.gif)  
   
 ![Figure 5](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng8-p6-zheng-small.gif)  

## 4. どうやって有効だと検証した？
 ● 3人の被験者に5種類の動作のうち8回ランダムにのモーションを1-3秒の間で行い，60秒間記録し，オンラインデータ取得をそれぞれの被験者で5回行なったところ平均総合精度73.56%,平均投票精度は91.67%を示した．  
 ![Figure 6](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9181388/9188342/9188795/zheng11-p6-zheng-small.gif)  

## 5. 議論はあるか？
 ● 転移学習を用いた被験者間の分類について  
 ● より高速なアルゴリズムを用いて他の動作をシステムに持ち込み特定の動作タスクを行えるようにする.  
 ● オフライン学習のデータを取得するのに10分かかる  
## 6. 次に読むべき論文はあるか？
 ● sEMGアプリケーションの分野における従来の手法と深層学習アルゴリズムについてまとめている論文  
[Deep Learning for Electromyographic Hand Gesture Signal Classification Using Transfer Learning](https://ieeexplore.ieee.org/document/8630679)  
 ● パターン認識のために必要なウィンドウサイズについて述べられている論文  
 [Determining the Optimal Window Length for Pattern Recognition-Based Myoelectric Control: Balancing the Competing Effects of Classification Error and Controller Delay](https://ieeexplore.ieee.org/document/5676233)  

### 論文情報・リンク

- [H. Zheng, H. Yokoi, Y. Jiang and F. Duan, "An Online sEMG Motion Classification Framework for Tele-operating the Robotic Hand," 2020 39th Chinese Control Conference (CCC), 2020, pp. 6491-6496, doi: 10.23919/CCC50068.2020.9188795.](https://ieeexplore.ieee.org/document/9188795)  
