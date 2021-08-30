
---
author: "retact"
title: "Investigation of Different Approaches to Real Time Control of Prosthetic Hands With Electromyography Signals"
date: 2021-08-30
draft: false
description: "description"
tags: [
    "EMG",
    "Real-Time"
]

---

## 1. どんなもの？
ACCを用いたマルチモーダルによる筋電パターン認識システムの評価と感覚フィードバックの考案をしている．筋電パターン認識では300msで応答するソフトウェアハードウェアシステムを開発しており，従来の分類精度と同等の結果を得られている，またフィードバックシステムにおいても把持する物体の質量が変わっても把持し続けられる結果を得ている．

<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
 ● 筋電パターン認識においては，CNNを用いた分類精度には及ばないものの，MLP,RFを用いた手法において，従来と同等以上の分類精度を示している．  
 ● フィードバックシステムにおいてはスリップ検出システムによって，質量が変わるという外乱においても把持し続けられるようなシステムを考案している，  

## 3. 技術や手法の"キモ"はどこにある？
 ● マルチモーダル処理  
 ACCと組み合わせることによって12クラスの分類を向上させている.
またPCAとLDAの時限削減を行い比較したところ，PCAを用いた手法の分類精度が低下したことからPCAでは有用な情報が失われることがわかった.  
  
 ● フィードバックシステム  
 圧力センサと滑りセンサを用いて，物体を把持しているか，また滑っていないかを検出流フィードバックシステムを考案している.  

 ● 時間的特徴の抽出  
 分類において15個の時間的特徴から，Pearson's Correlation Coefficientsを用いて，7つの特徴を選択ている.  
 

## 4. どうやって有効だと検証した？
 ● 筋電パターン認識においては，従来の分類と比較するために，NinaProDB2,とDB3を用いて，50分類との比較と，独自のkudaProを用いて12分類の性能評価を行い従来手法と同等の精度であることを示している．  
 ● フィードバックシステムにおいては，trackerを用いたビデオ分析によって．3つの物体，計30回の試行を元に把持する精度を従来精度と同等であることを示している．またカップに水を注ぐことで，フィードバックによる把持力の変化についても示している．  
## 5. 議論はあるか？
 ● モータのトルクによる義手そのものの把持力がないこと．  
 ● CNNなどを用いたリアルタイム分類を行うこと．  
 ● 切断者の分類においては精度が低いこと.  

## 6. 次に読むべき論文はあるか？
 ● 筋電パターン認識におけるマルチモーダルアプローチ  
 -[A. Fougner, E. Scheme, A. D. C. Chan, K. Englehart and Ø. Stavdahl, "A multi-modal approach for hand motion classification using surface EMG and accelerometers," 2011 Annual International Conference of the IEEE Engineering in Medicine and Biology Society, 2011, pp. 4247-4250, doi: 10.1109/IEMBS.2011.6091054](https://ieeexplore.ieee.org/document/6091054)
### 論文情報・リンク

- [J. O. d. O. De Souza, M. D. Bloedow, F. Rubo, R. M. De Figueiredo, G. Pessin and S. J. Rigo, "Investigation of Different Approaches to Real-Time Control of Prosthetic Hands with Electromyography Signals," in IEEE Sensors Journal, doi: 10.1109/JSEN.2021.3099744.](https://ieeexplore.ieee.org/document/9494435)
