---
author: "retact"
title: "Hand Gesture Recognition Based on Semg Signal and Improved SVM Voting Method"
date: "2021-04-24"
description: "ジェスチャー推定を行うための少ない筋電図特徴量を用いたSVMアルゴリズム"
tags: [
    "EMG"
]
---


## 1. どんなもの？
  できるだけ少ない特徴量でできるだけ多くのジェスチャーパターンを認識するSVMアルゴリズムの提案。従来のvoting Methodとは異なり全てのサブセットトレーニングに対応している他分離可能性を高めた方法の提案がされている。これにより特徴ベクトル次元数は3元で12のジェスチャーを84%の認識精度で分類している。 
  <!--more-->

## 2. 先行研究と比べてどこがすごいの？
 ● これまではパターン認識アルゴリズムやNNによって特徴ベクトルの次元が数十から数百に及び、抽出されたアルゴリズムとジェスチャーの種類を分類させることが困難であったが、低次元化した特徴量を用いたジェスチャー分類を行うことができた。  
## 3. 技術や手法の"キモ"はどこにある？
 ● MyoBock 13E200-50電極によりsEMG信号を増幅、バンドパスフィルタリング、RMS整流している。  
 ● 物理的な意味が明らかであり計算コストの低い時間領域解析法と安定している周波数領域解析を用いている。  
 ● 計算量の低くセグメントごとに大きな特徴を示すMMAVを用いている。(sEMG波形をN分割し、MAV(平均絶対値)を左から抽出する。  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9236788/9236789/9236928/9236928-fig-2-source-small.gif)  
 ● 他の特徴量ではMMAVTPはMMAVのNの配列であり、MMAVを補完し、MPFというパワースペクトル密度関数を用いた周波数領域の特徴量を用いている。これらにより特徴ベクトル数は10,次元は3となる。  
 ● SVMをクラス距離に基づいて計算された分離可能性の基準によって異なるサブトレーニングセットに分散させる。  
 ● 分離可能性を強化する係数はSQPアルゴリズムを用いた非線形多変数関数の解を元に決められた制約条件に基づき産出する。  

## 4. どうやって有効だと検証した？
 ● Ninaproが定義した12のジェスチャ-を用いた。  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9236788/9236789/9236928/9236928-fig-1-source-small.gif)  
 ● 一般的ないくつかのニューラルネットワーク分類器と比較し，また従来の投票法とも比較した結果チャンネル数が同じ場合、改良型SVM投票法の認識効果は、他の分類器よりも著しく優れていることがわかった  
 ![Figure 5](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9236788/9236789/9236928/9236928-fig-5-source-small.gif)  

## 5. 議論はあるか？
 ● 加速度センサなどを用いて特徴量を増やすことにより、より多くのジェスチャーを取り込む。
## 6. 次に読むべき論文はあるか？
 -[M. Atzori, A. Gijsberts, C. Castellini et al., "Electromyography data for non-invasive naturally-controlled robotic hand prostheses", Sci Data, vol. 1, no. 140053, 2014.](https://www.nature.com/articles/sdata201453)  
 -[S. Park, W. K. Chung and K. Kim, "Training-Free Bayesian Self-Adaptive Classification for sEMG Pattern Recognition Including Motion Transition", IEEE Transactions on Biomedical Engineering, vol. 67, no. 6, pp. 1775-1786, June 2020.](https://ieeexplore.ieee.org/document/8867968)  
 -[W. Chen and Z. Zhang, "Hand Gesture Recognition using sEMG Signals Based on Support Vector Machine", 2019 IEEE 8th Joint International Information Technology and Artificial Intelligence Conference (ITAIC), pp. 230-234, 2019.](https://ieeexplore.ieee.org/document/8785542)  
 -[P. Xu, Y. Liu, G. Gu and X. Shen, "Research on the Method of EMG Pattern Recognition Based on Neural Networks", 2018 2nd IEEE Advanced Information Management Communicates Electronic and Automation Control Conference (IMCEC), pp. 1401-1405, 2018.](https://ieeexplore.ieee.org/document/8469432)  
 -[T. Ruan, K. Yin and S. Zhou, "Convolutional Neural Network Based Human Movement Recognition Using Surface Electromyography", 2018 IEEE 1st International Conference on MicrolNano Sensors for AI Healthcare and Robotics (NSENS), pp. 68-72, 2018.](https://ieeexplore.ieee.org/document/8713564)
 -[H. Liu, Z. Zhang, J. Qian, W. Wang and K. Kang, "Hand Gesture Recognition Based on Deep Neural Network and sEMG Signal", 2019 IEEE International Conference on Robotics and Biomimetics (ROBIO), pp. 3001-3006, 2019.](https://ieeexplore.ieee.org/document/8961445)  
 -sEMGデジタルセンサの設計スキーム  
 -[X. Chen, Y. Zhou, H. Wang, X. Lü and Z. Wang, "Design of sEMG-detecting circuit for EMG-Bridge", 2017 39th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 382-385, 2017.](https://ieeexplore.ieee.org/document/8036842)
### 論文情報・リンク

- [C. Liua, S. Zhou, S. Hu and M. Wu, "Hand Gesture Recognition Based on Semg Signal and Improved SVM Voting Method," 2020 IEEE 3rd International Conference on Information Systems and Computer Aided Education (ICISCAE), 2020, pp. 605-608, doi: 10.1109/ICISCAE51034.2020.9236928.](https://ieeexplore.ieee.org/document/9236928)
