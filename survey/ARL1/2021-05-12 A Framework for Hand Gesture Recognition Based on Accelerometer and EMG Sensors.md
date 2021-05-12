---
title:  "A Framework for Hand Gesture Recognition Based on Accelerometer and EMG Sensors"
date:   2021-05-12
categories: EMG
---

## 1. どんなもの？
ACCとEMGセンサーの融合のために、決定木とマルチストリームHMMを用いたハンドジェスチャー認識のフレームワークの提案で様々な手首や指のジェスチャーの認識精度がこれまでの5〜10％向上した。

## 2. 先行研究と比べてどこがすごいの？
● ジェスチャーの開始点と終了点を自動的に指定することが重要であるがこれまでの研究は手動で達成していおり、ジェスチャーの開始点と終了点をEMG信号の強度によって自動的に検出し、ACCとEMGの両方のセグメントを取得し処理を行う。  
 ![Figure1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/3468/6034617/5735233/5735233-fig-1-source-small.gif)  

## 3. 技術や手法の"キモ"はどこにある？
 ● EMGを利用した移動平均データ分割し　EMG信号とACC信号の両方のアクティブなジェスチャセグメントは同じ境界によって区別される。  
 ● EMGの特徴抽出では平均絶対値(MAV)と4次のAR係数**(自己回帰係数)の組み合わせを特徴セットとして選択し，決定木の中の分類器によって使用する。またACC特徴抽出ではハンドジェスチャーを行ったときの3軸（x,y,z）方向の速度変化率を測定し、ファジーK-meansクラスタリングとLDCを用いて手のひらのむきの判定を行う。
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/3468/6034617/5735233/5735233-fig-2-source-small.gif)  
 ● 手の向き分類器で割り当てられた枝に沿って、未知のジェスチャー・サンプルは、ACCとEMGの特徴ベクトルはマルチストリームHMM分類器に入力される。ジェスチャーの判定はマルチストリームHMMノードの候補の中から決定する。  

 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/3468/6034617/5735233/5735233-fig-3-source-small.gif)  

## 4. どうやって有効だと検証した？
 ● 72個のCSL文を分類した実験結果から、ACCとEMGセンサーの相補的な機能と本フレームワークの有効性が示した。  
 ● 40のCSL文を認識することで、連続的な手話認識のためのフレームワークを評価した。  
 ●　ジェスチャーベースの制御については，18種類のハンドジェスチャーを制御コマンドとしたリアルタイムのインタラクティブシステムを10人の被験者にゲームをプレイしその性能をユーザ別に分類して評価した。  

## 5. 議論はあるか？

## 6. 次に読むべき論文はあるか？

### 論文情報・リンク

- [X. Zhang, X. Chen, Y. Li, V. Lantz, K. Wang and J. Yang, "A Framework for Hand Gesture Recognition Based on Accelerometer and EMG Sensors," in IEEE Transactions on Systems, Man, and Cybernetics - Part A: Systems and Humans, vol. 41, no. 6, pp. 1064-1076, Nov. 2011, doi: 10.1109/TSMCA.2011.2116004.](https://ieeexplore.ieee.org/document/5735233)  
 
