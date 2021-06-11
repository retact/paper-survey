---
author: "retact"
title: "A versatile embedded platform for EMG acquisition and gesture recognition"
date: "2021-05-09"
description: "安価でオンライン制御のできるアームバンドの開発"
tags: [
    "EMG",
    "AB"
]
---

## 1. どんなもの？
ハイエンドなアクティブ筋電精度と同等の精度を示すリアルタイムジェスチャー認識のためのEMG信号の取得と処理が可能で安価なウェアラブルデバイスを開発.　デバイスはCerebroとCoretexが統合されており、SVM認識アルゴリズムを実装し，オフラインでの最先端の結果と同等の90%の精度で29.7 mWの消費電力性能を示している。
<!--more-->

## 2. 先行研究と比べてどこがすごいの？
筋電にはクロストークなどのいくつかの干渉やユーザーによって筋肉の構造が異なり、装着する場所を標準化できないといった問題に対して、高度な機械学習アルゴリズムによってオフライン制御によって認識精度をあげる試みが行われており、HMIでは行えない計算であったが、ARM Cortex M4を用いたEMG収集、及ジェスチャー認識システムHMIで高度な計算を実現している。またEMGジェスチャ認識システムにおいてチップレベルで多くのソリューションは開発されているが信号取得と処理の完全なシステムアプローチは行われていない。
　　
## 3. 技術や手法の"キモ"はどこにある？
 ● Signal Acquisition Front-End (cerebro ASIC)  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/4156126/7337496/7303979/7303979-fig-2-source-large.gif)  


 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/4156126/7337496/7303979/7303979-fig-1-source-large.gif)  
 
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/4156126/7337496/7303979/7303979-fig-3-source-large.gif)  

## 4. どうやって有効だと検証した？
 ● MYOアームバンドと比較  

## 5. 議論はあるか？
 ● 臨床試験での検証  
## 6. 次に読むべき論文はあるか？
 著者の前作アーキテクチャ  
 -[S. Benatti, B. Milosevic, F. Casamassima, P. Schonle, P. Bunjaku, S. Fateh, et al., "Emg-based hand gesture recognition with flexible analog front end", Proc. IEEE Biomedical Circuits and Systems Conf., pp. 57-60, 2014-Oct.](https://ieeexplore.ieee.org/document/6981644)  
 ARM Corex-A8 DSPを使用したハンドジェスチャ認識の先行研究  
 -[J. Liu, F. Zhang and H. Huang, "An open and configurable embedded system for emg pattern recognition implementation for artificial arms", Proc. 36th IEEE Annu. Int. Conf. Engineering in Medicine and Biology Soc., pp. 4095-4098, 2014-Aug.](https://pubmed.ncbi.nlm.nih.gov/25570892/)  
 AFEとADCおよびマイクロプロセッサを同一チップ上に統合した唯一の効率的なソリューション  
 -[N. Van Helleputte, M. Konijnenburg, J. Pettine, D.-W. Jee, H. Kim, A. Morgado, et al., " A 345- \$mu\$ W multi-sensor biomedical SoC with bio-impedance 3-channel ECG motion artifact reduction and integrated DSP "](https://ieeexplore.ieee.org/document/6923499)
### 論文情報・リンク

- [S. Benatti et al., "A versatile embedded platform for EMG acquisition and gesture recognition", IEEE Trans. Biomed. Circuits Syst., vol. 9, no. 5, pp. 620-630, Oct. 2015.](https://ieeexplore.ieee.org/document/7303979)
