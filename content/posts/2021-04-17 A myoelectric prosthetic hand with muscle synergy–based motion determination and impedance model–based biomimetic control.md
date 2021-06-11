
---
author: "retact"
title: "A myoelectric prosthetic hand with muscle synergy–based motion determination and impedance model–based biomimetic control"
date: "2021-04-17"
description: "3Dプリンタ義手におけるキンシナジーに基づく動作決定法と生体模倣インピーダンス制御について"
tags: [
    "AH",
    "EMG"
]
---

## 1. どんなもの？
3Dプリンタによって生成可能な義手において、筋シナジーに基づく動作決定法と生体模倣インピーダンス制御を導入することで，
学習されていない複合動作の分類や，スムーズで直感的な義手の指の動きを実現した筋電義手
オープンソースの義手を改造して比較的簡単に設計されている。
また義手の制御自体にはPID制御を用いている。
<!--more-->

## 2. 先行研究と比べてどこがすごいの？
 ● これまでの筋電義手では大量のデータを学習させ、正確に分類できるEMG分類法を用いているのに対し、この研究では
 筋シナジーをEMGから抽出し、その偏移と組み合わせに注目した筋力の推定とRNNを用いて学習コストを減らしたほか
 未学習の複合動作の推測に成功した。またインピーダンスモデルに基づく生体模倣制御を用いて義手のなめらかな動きを再現した。

## 3. 技術や手法の"キモ"はどこにある？
 ● 制御システムは、EMG測定、EMG信号処理、義手制御、筋電義手という4つの部分で構成されバイオミメティック制御により，アクチュエータのコマンドを決定する  
![Figure 1](https://robotics.sciencemag.org/content/robotics/4/31/eaaw6339/F1.medium.gif)
 ● EMG信号を測定するために5つの電極を使用  
 ● R-LLGMNを用いて単一のEMG時系列EMGパターンを学習し筋シナジーを推定するモデルを作る  
 ● ペトリネットを用いて記述されたイベントドリブンモデルをベースに動作生成モデルを構築
 

## 4. どうやって有効だと検証した？
 ● 被験者には，10回の動作（M1からM5までは単一動作，M6からM10までは複合動作）を行い、それぞれの動作を記録、
 　次に学習していない複合動作を含む10種類の動作をすべて行い、分類精度を算出した結果．
 　すべての動作において，平均分類精度は，フィードバックなしで91.7%，フィードバックありで97.3%であった。  
   ![Figure 3](https://robotics.sciencemag.org/content/robotics/4/31/eaaw6339/F3.medium.gif)  
   ((A) Classified motion and corresponding normalized EMG signals for each channel, force information, and muscle contraction level. (B) Classified motion and corresponding motor output angle for each finger. In this experiment, the motions conducted by the participant were no motion (NoM), thumb flexion (M1), index finger flexion (M2), middle finger flexion (M3), ring and little finger flexion (M4), and grasp (M5).)  
    
   ![Figure 4](https://robotics.sciencemag.org/content/robotics/4/31/eaaw6339/F4.medium.gif)  
   ((A) Results for the single motions (M1 to M5). (B) Results for the combination motions (M6 to M10). These time-series results are arbitrary 2-s cuts from data of a participant.)  
   
 ● 切断者には5つの動作（M1〜M5）をさせ,学習した単一動作で89.9%、学習していない複合動作で100.0%、全動作で91.9%であった  
  
## 5. 議論はあるか？
 ● 筋電義手の握力向上や、軽量化について述べていく余地がある。  
 ● この研究で実施した最長の実験の時間は60秒であった。筋電義手のデータ精度の向上  
 ● EMGのサンプリングが200Hz  
 　
## 6. 次に読むべき論文はあるか？
[T. Tsuji, K. Shima, N. Bu, O. Fukuda, Biomimetic impedance control of an EMG-based robotic hand, in Robot Manipulators (InTech, 2010), chap. 9, pp. 213–231.](https://www.researchgate.net/publication/221908124_Biomimetic_Impedance_Control_of_an_EMG-Based_Robotic_Hand)  

### 論文情報・リンク

- [Akira Furui, Shintaro Eto, Kosuke Nakagaki, Kyohei Shimada, Go Nakamura, Akito Masuda, Takaaki Chin, Toshio Tsuji, "A myoelectric prosthetic hand with muscle synergy–based motion determination and impedance model–based biomimetic control", Science Robotics, vol. 4, pp. eaaw6339, 2019.](https://robotics.sciencemag.org/content/4/31/eaaw6339)
