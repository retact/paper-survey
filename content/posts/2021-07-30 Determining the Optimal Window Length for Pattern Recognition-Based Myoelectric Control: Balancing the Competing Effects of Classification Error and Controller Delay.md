
---
author: "retact"
title: "Determining the Optimal Window Length for Pattern Recognition Based Myoelectric Control: Balancing the Competing Effects of Classification Error and Controller Delay"
date: 2021-07-30T14:55:35+09:00
draft: false
description: "Determining the Optimal Window Length for Pattern Recognition-Based Myoelectric Control: Balancing the Competing Effects of Classification Error and Controller Delay"
tags: [
    "EMG",
    "Windowsize"
]

---

## 1. どんなもの？
筋電図のパターン認識において，分類誤差とコントローラの遅延とリアルタイムの制御性から解析ウィンドウの長さを50ms-550msの中でどの値が最適かを調べている．実験はTarget Achievement Controlによって評価され，ユーザーのパフォーマンスは分類誤差が小さいほど，向上し，遅延量が大きくなるほど低下するトレードオフの関係であることがわかっている．その上でこの研究で用いたシステムでの最適な解析ウィンドウの長さは150-250msであることがわかった．


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
● 先行研究では臨床環境でのパラーン認識が最適化されていない． 
● パターン認識を用いた筋電制御について，分類誤差，制御器の遅延，リアルタイム制御性の関係を調べた先行研究はなかった  
## 3. 技術や手法の"キモ"はどこにある？
 ● 2個と4個のEMGチャンネル(バイポーラEMG電極)をもちいて，7種類の動作を分類する試験を13人の被験者を対象に行なった.  
 各収縮は3秒間行い，学習に利用した特徴はZCとSSCとMAVとWLを用いてLDAの7の部分空間に分割し，パターン認識を行なっている.(処理遅延は2.5GHzのIntel Core 2 Duoプロセッサで計算され、約500μs)また仮想環境の更新情報を表示するのにかかる時間が20ms以下だったため25msのスライドウィンドウにしている．    
 ● 統計解析  
 SPSS Statistical Modeling Softwareを用いて線形混合効果モデルを元にウィンドウの長さと分類誤差との関係を調べている.   
  

## 4. どうやって有効だと検証した？
 ● Target Achievement Control  
 50，150，250，350，450，550msに設定した解析ウィンドウ長さを利用したパターン分類器を用いた6つの目標動作に対して12秒間のうち2秒間の維持を動作を成功とする2セットのパイロットテストを行い，分類精度と解析ウィンドウの最適な長さは150ms-250msであることがわかった.  
 ![Figure1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/5745718/5676233/5676233-fig-2-source-small.gif)  
 分類誤差と解析ウィンドウの関係(ウィンドウが長ければ分類精度は向上するが4つのチャンネルで検証した結果150ms，250ms，350ms，450ms，550msでは有意な差はみられていない)  
   
 ![Figure2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/5745718/5676233/5676233-fig-3-source-small.gif)  
 それぞれのウィンドウにおける増加したタスク完了率(分類誤差とは関係ない)  
   
 ![Figure3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/7333/5745718/5676233/5676233-fig-4-source-small.gif)  
 分類誤差が小さい（ウィンドウ長が長い）と完了率にプラスの効果があり，分析ウィンドウが長いと（分類誤差とは無関係に考えた場合）完了率にマイナスの効果がある.  

 
## 5. 議論はあるか？
 ● チャンネル数によって最適な解析ウィンドウ長さは変わる.  
 ● 実機を用いたテストをおこなっていない.  

### 論文情報・リンク

- [L. H. Smith, L. J. Hargrove, B. A. Lock and T. A. Kuiken, "Determining the Optimal Window Length for Pattern Recognition-Based Myoelectric Control: Balancing the Competing Effects of Classification Error and Controller Delay," in IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 19, no. 2, pp. 186-192, April 2011, doi: 10.1109/TNSRE.2010.2100828.](https://ieeexplore.ieee.org/document/5676233)
