---
title:  "An Efficient PointLSTM for Point Clouds Based Gesture Recognition"
date:   2021-05-12
categories: EMG
---

## 1. どんなもの？
 ジェスチャー認識を不規則なシーケンス認識問題として定式化して長期的な空間相関を捉えることを目的として重み共有されたLSTM層によって現在の状態を更新するpointLSTMを用いた手法  
## 2. 先行研究と比べてどこがすごいの？
 画像データの生の点群から構造情報を直接抽出するPointNetアーキテクチャなどは単に短期的なモデル化に焦点を当てており、長期的な関係を捉える能力は不十分である他、長短期記憶のLSTMにおいても時間とともに変化する動きと外観の両方を捉えることが可能になるが、点群データは無秩序なので最適化が難しいため時間的な情報をどのように活用するかが課題となっていたが、PointLSTMによって長期的かつ、不規則な配列に対して空間構造を保持しつつ、時間的特徴を取り入れた。またPointLSTM-PSSでは計算量を削減した。
 ![Figure1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/9142308/9156271/9157795/716800f760-fig-1-source-small.gif)  
## 3. 技術や手法の"キモ"はどこにある？
 

## 4. どうやって有効だと検証した？
 ● NVIDIA Dynamic Hand Gesture DatasetやSHREC'17 Track Datasetを用いて3Dジェスチャー認識とアクション認識という2つのシーケンス認識タスクで評価したところ、実時間アプリケーションへの大きな可能性が示された。  
 ● MSR Action3D Datasetで行動認識に対する提案手法を検証したところスケルトンベースの手法と競合する結果を示した。   

## 5. 議論はあるか？

## 6. 次に読むべき論文はあるか？

### 論文情報・リンク

- [Y. Min, Y. Zhang, X. Chai and X. Chen, "An Efficient PointLSTM for Point Clouds Based Gesture Recognition," 2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2020, pp. 5760-5769, doi: 10.1109/CVPR42600.2020.00580.](https://ieeexplore.ieee.org/document/9157795)
  
