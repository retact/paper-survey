
---
author: "retact"
title: "A 3D Printed, Adjustable Armband for Electromyography Based Finger Movement Classification With Haptic Feedback"
date: 2021-06-21
draft: false
description: "description"
tags: [
    "EMG",
]

---

## 1. どんなもの？
1本の指のタッピング動作を検出するために，電極の配置を完全に調整できる3Dプリントされた低コストのアームバンドの提案。9本の指の動きを検出するために，8チャンネルのSEMG信号から抽出した特徴量を用いて機械学習を行い、500msウィンドウの特徴量を用いたKNNでは71%、200msのきれいなデータのサブセットから抽出した特徴量を用いたKNNでは93%の精度を記録した。  
 


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
指の動きを分類する研究では市販の8チャンネルsEMGアームバンドを使用し，5本の指の分類問題で72%の精度を得ているが特定の筋肉にセンサを配置することができないため器用な動きを伴う分類問題には適していないのに対し、今回紹介するのは任意の場所に電極を配置できるアームバンドのデザインであること、
## 3. 技術や手法の"キモ"はどこにある？
 ● アームバンドのデザイン  
 ユーザーの日常生活に支障が出ないように極薄のデザインで、電極の位置を自由に調整できる他巻き付けて調節可能なベルトを3タイプ作成している。  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9282733/9282811/9283117/wang1-p6-wang-small.gif)  
 (Computer-aided designs of the armband pieces. A: Hand piece. B: Wrist piece. C: Forearm piece)  

 ● Haptic Feedback Mechanism  
 ユーザーエクスペリエンスの向上のため、感覚フィードバック機能を実装している。携帯電話で使用されている振動モーターを5つ搭載され、80ミリ秒のフィードバックが行われる。  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9282733/9282811/9283117/wang2-p6-wang-small.gif)  

 ● データ収集とデバイス  
 13人の健常者に対して8チャンネルのOpenBCI Cytonバイオセンシングボードを用いて，平板状のAg/AgCl（銀/塩化銀）スナップ電極にて250Hzのサンプリングレートでデータを取得している。また取得されるデータは画面上でキーボードを使って文字を入力するよう指示されるmode1と空中でタッピングの動作を行うmode2と自分のペースでキーボードを入力してもらうmode2がある。  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9282733/9282811/9283117/wang3-p6-wang-small.gif)  
 ● 動きの検出  
 動きの検出は、ウィンドウを100ミリ秒ごとのサブウィンドウに分割し、各チャンネルの10〜50Hzの平均パワースペクトル密度（PSD）を計算され、一定の閾値を超えなければ動きなしと判定される  
 ● 分類では11種類の時間領域の特徴量と4種類の周波数領域の特徴量をもちいてScikit-learnのK-Nearest Neighbours（KNN），ロジスティック回帰（LR），決定木分類法（CART）を用いてデータセットの80%のトレーニングセット、20%のテストセットに分けらて行う。  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9282733/9282811/9283117/wang.t1-p6-wang-small.gif)  
 
## 4. どうやって有効だと検証した？
 ● ウィンドウサイズを200ms，500ms，1000msに設定し，28回のすべての試行で学習を行い、KNNではそれぞれ 60.5±0.6%，66.8±0.3%，70.3±0.4% の精度が得られている。  
 ![Figure4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9282733/9282811/9283117/wang.t2-p6-wang-small.gif)  
## 5. 議論はあるか？
 ● データの収集には被験者の偏りがあるため、厳密なデータ収集プロトコルを用いた実験を行う必要  
 ● ロバストなモデルの作成  

## 6. 次に読むべき論文はあるか？
[C. Castellini and P. van der Smagt, "Surface EMG in advanced hand prosthetics", Biol. Cybern., vol. 100, no. 1, pp. 35-47, Jan. 2009.](https://link.springer.com/article/10.1007/s00422-008-0278-1)
### 論文情報・リンク

- [M. Wang et al., "A 3D-Printed, Adjustable Armband for Electromyography-Based Finger Movement Classification With Haptic Feedback," 2020 IEEE International Conference on Systems, Man, and Cybernetics (SMC), 2020, pp. 3460-3465, doi: 10.1109/SMC42975.2020.9283117.](https://ieeexplore.ieee.org/document/9283117)  
