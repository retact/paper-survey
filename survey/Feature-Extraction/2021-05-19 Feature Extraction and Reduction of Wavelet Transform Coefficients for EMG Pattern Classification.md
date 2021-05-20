---
title:  "Feature Extraction and Reduction of Wavelet Transform Coefficients for EMG Pattern Classification"
date:   2021-05-19
categories: FE EMG
---

## 1. どんなもの？
適切なウェーブレットベースの関数を用いて複数のレベルのウェーブレット分解と再構成からsEMGの特徴を抽出し有用性を検討し、ほとんどのsEMGの特徴において、クラス分離性を向上させる結果となり、可能な限り分類精度を確保しつつ、計算時間を可能な限り短縮することができた。  
 
## 2. 先行研究と比べてどこがすごいの？
先行研究ではDWTによって非定常信号の分析に成功はしているが、高次元の特徴ベクトルを生成し、パラメータの増加を引き起こしてしまうため、分類精度を意地したたまま特徴ベクトルの次元を削減するひつようがある。一般的な手法としては特徴投影法と特徴選択法があるが、本研究では元のウェーブレット係数と元の特徴とは異なる削減された特徴と最適な組み合わせを決定使用とし種成分分析を用いた特徴投影法によって行い,EMG特徴量の特徴空間におけるクラス分離性の向上が示された。
## 2.1 特徴抽出や筋電義手においてなんとなくわかったこと,おもったこと
● 時間領域、周波数領域、時間-周波数領域、時間-スケール領域などの領域で分類されている。  
● ウェーブレット解析に基づく特陵は有用なものであると言われている。  
● 筋電図は非定常信号  
● この研究では2つの前腕筋から6つの手の動きのデータセットを用いておこなった  
● DWTは次元スケールアプローチ  
● SOFM（自己組織化特徴マップ）などがあるらしい  
● 線形判別分析(LDA)などの投影法もあるらしい。  
● wrist flexion (WF), wrist extension (WE), hand close (HC), hand open (HO), forearm pronation (FP) and forearm supination (FS)  
● ウェーブレット変換法は離散型と連続型に分けることができる。
## 3. 技術や手法の"キモ"はどこにある？
 ● 
 ![Figure 1]()  
 ● 
 ![Figure 2]()  
 ● 
 ![Figure 3]()  

## 4. どうやって有効だと検証した？
 ● 
## 5. 議論はあるか？

## 6. 次に読むべき論文はあるか？

### 論文情報・リンク

- [https://www.researchgate.net/publication/262011091_Feature_Extraction_and_Reduction_of_Wavelet_Transform_Coefficients_for_EMG_Pattern_Classification](https://www.researchgate.net/publication/262011091_Feature_Extraction_and_Reduction_of_Wavelet_Transform_Coefficients_for_EMG_Pattern_Classification)
