
---
author: "retact"
title: "Forearm Motion Discrimination Technique Using Real Time EMG Signals"
date: 2021-09-08
draft: false
description: "description"
tags: [
    "EMG",
    "Real-Time"
]

---

## 1. どんなもの？
300m/s以下のレスポンス速度について[Real-time Pattern Recognition for Hand Gesture Based on ANN and Surface EMG](https://ieeexplore.ieee.org/document/8785894)で明記されていた理由として紹介されていたが，本文ではその理由に対するエビデンスは示されていない．  
本文ではhyper - spheremodel といったみたことのない特徴を用いており，異常値をrestとみなすアプローチがされている.  
また移動平均フィルタのデータ数が増えると遅延量が多くなりレスポンス速度が遅くなるという結果明記がされている．　　


<!--more-->  

 ![Motion Discrimination](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6067544/6089866/6091100/6091100-fig-1-source-small.gif)  
 ![Filtering Delay](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6067544/6089866/6091100/6091100-fig-2-source-small.gif)  
 ![Examples of Decision Regions using Conic Models](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6067544/6089866/6091100/6091100-fig-3-source-small.gif)  



### 論文情報・リンク

- [H. Mizuno, N. Tsujiuchi and T. Koizumi, "Forearm motion discrimination technique using real-time EMG signals," 2011 Annual International Conference of the IEEE Engineering in Medicine and Biology Society, 2011, pp. 4435-4438, doi: 10.1109/IEMBS.2011.6091100.](https://ieeexplore.ieee.org/document/6091100)
