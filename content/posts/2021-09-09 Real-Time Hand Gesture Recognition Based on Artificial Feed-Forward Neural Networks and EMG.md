
---
author: "retact"
title: "2021 09 09 Real Time Hand Gesture Recognition Based on Artificial Feed Forward Neural Networks and EMG"
date: 2021-09-09
draft: false
description: "description"
tags: [
    "EMG",
    "Real-Time"
]

---

## 1. どんなもの？
3層ニューラルネットワークで5つのジェスチャーを90.1%の精度でresponse速度11msで分類している．  
また，ウィンドウサイズ500点でスライドウィンドウが10点であり，整流化のち5次のバターワースフィルタを用いてエンベロープで平滑化したあとに，筋収縮に対応する点をセグメント化している．特徴量抽出はDTWを利用しており，分類では条件付き確立で0.5の閾値を取らなければrestと判断する手法が取られている．  
またこの手法の利点として,トレーニングデータが30個であるため，学習コストが非常に少ないといったことがあげられる．
今後の手法としてRNNを用いた分類モジュールを提案している．  

<!--more-->  
 ![EMG signal (red line) and its envelope (black line).](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8537458/8552938/8553126/1570439350-fig-1-source-small.gif)  
 ![Confusuion matrix of the proposed model](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8537458/8552938/8553126/1570439350-table-1-source-small.gif)  
 ![Results of different recognition models](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/8537458/8552938/8553126/1570439350-table-2-source-small.gif)  

## 次に読むべき論文はあるか？
筋収縮に対応する領域をセグメント化した手法を用いている論文  
[Real-time hand gesture recognition using the Myo armband and muscle activity detection](https://ieeexplore.ieee.org/abstract/document/8247458)  

### 論文情報・リンク

- [M. E. Benalcázar, C. E. Anchundia, J. A. Zea, P. Zambrano, A. G. Jaramillo and M. Segura, "Real-Time Hand Gesture Recognition Based on Artificial Feed-Forward Neural Networks and EMG," 2018 26th European Signal Processing Conference (EUSIPCO), 2018, pp. 1492-1496, doi: 10.23919/EUSIPCO.2018.8553126.](https://ieeexplore.ieee.org/document/8553126)
