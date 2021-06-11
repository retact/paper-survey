

---
author: "retact"
title: "Navigating features: a topologically informed chart of electromyographic features space"
date: "2020-05-18"
description: "トポロジカルな手法を用いた特徴量選定の方法について"
tags: [
    "EMG",
    "FE"
]
---


## 1. どんなもの？
  EMGの特徴量58個を３つのデータセットにおいて、トポロジカルな手法を用いてサブグループを探索してこのグループに基づいたクラス分類可能性、ロバスト性、複雑性などについて分類しそれぞれの特徴量抽出の評価について紹介している。 
  <!--more-->

## 2. 先行研究と比べてどこがすごいの？  
 ● 特徴空間の探索を簡単にするMapper法という解析手法を用いて最適閾値を求めている.  
 ● 最適な特徴セットを自動的に選ぶのではなくトポロジカルデータ解析(TDA)を用いることで原理的でロバストな特徴空間マップを示している。  
 ● Mapperを用いて選択した手法には全ての特徴量を用いた場合と同程度の分類精度を達成できるという仮説に対して、SFSという手法と比較して検証をしている。  

## 2.1 なんとなくわからなかったこと,おもったこと
 ● Mapper法は古典的なクラスタリングや次元削減では検出できないサブグループを特定する。    
 ● この実験においてはデータセットの収集を行っていない。(そういう査読論文もある)  
 ● 特徴量抽出や分類におけるロバスト性を示すには色々なデータセットを使う必要がある(それはそう)  
 ● データのセグメンテーション，特徴抽出，分類，コントローラの処理、セグメンテーションあまり理解できていない。  
 ● 冗長性?の観点から特徴量比較はおこなわれていないらしい  
 ● 特徴量の標準化についてあまりよく知らない,  
 ● EMGの特徴機能は4つのグループに分けられていて、信号の振幅とパワーの特徴グループ（信号の大きさを示している）非線形の複雑さと周波数情報の機能グループ,時系列モデリング機能グループ,ユニークなグループ
## 3. 技術や手法の"キモ"はどこにある？
 ● 58種類、計81個の特徴量比較  
 [A list of EMG feature extraction techniques.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746577/table/RSIF20170734TB1/?report=objectonly)  
 ● 被験者のEMGチャンネルごとの特徴量スケーリングを行い、特徴量の標準化を行った。 またk-近傍法でのクラス分類ではユークリッド距離測定ですべての特徴の寄与を均等化を行っている  
 
 ● TDAは「形状」を抽出するアプローチによって、高次元，高変動性，低S/N比，時間依存性，非線形性を有する複雑なデータから，関連する洞察を抽出することを可能になる  
  1,生データを点群に変換  
  2,複数のフィルタ関数を用いでMOとMI区間に分割  
  3,クラスタリングアルゴリズムによってサブデータセットからクラスタリング  
  4,トポロジカルネットワークの構築  
 →これによってトポロジカルネットワークのノードがEMGグループの特徴のサブグループをみなし、機能グループなどに分けられる.  
 k-NN距離が低いと同じサブグループの相関が強く、このサブグループから1つだけ選択する必要があり、大きい場合はこれらのサブグループから複数の特徴を用いることができる。  
 ![Figure1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746577/bin/rsif20170734-g1.jpg)  
 (1)下の部分はは、信号の大きさやパワーを推定するMAVやRMSなどで構成されている。  
 (2)左腕は、周波数情報を含む特徴量のZC、MDFなどと、時系列の非線形性や複雑性を測定するための特徴量のエントロピー、フラクタル次元などで構成されている  
 (3)右部分と2つの切断されたノードは、時系列モデリング機能（ARなど）で構成されている  
 (4)中央のコアと1つの切断されたノードは、ユニークな情報を提供する特徴のセットを描いていてHISTやMAVSなど  
 ![Figure2](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746577/bin/rsif20170734-g2.jpg)  

 ●それぞれの特徴量の評価結果は表のようになっている。  
 [The classification performance of 81 features using different evaluation methods: DBI, FLDI, SVM and LDA for the three EMG datasets](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746577/table/RSIF20170734TB2/?report=objectonly)  

 ● 各機能グループから代表的な特徴を特定するために特徴評価法を使用している。  
   1,分離可能性尺度の使用  
   2,特徴空間の分類  
  

## 4. どうやって有効だと検証した？
 ● トポロジカルチャートが、効果的なSFSの設計と同等の精度を示すためにTDの特徴量セット MAV, WL, ZC, SSC, MAVS 　　AR+RMS 特徴量セット。AR および RMS 　　　　AR+CC+WL特徴セット AR, CC, WL　　の3つのデータセットを用いて再評価した。  
## 5. 議論はあるか？

## 6. 次に読むべき論文はあるか？
-引用していた筋電のデータセットが乗っている論文
[Toward improved control of prosthetic fingers using surface electromyogram (EMG) signals](https://www.sciencedirect.com/science/article/abs/pii/S0957417412004654)  
-筋電パターン認識のロバスト性を改善するためのEMG評価について
[EMG feature evaluation for improving myoelectric pattern recognition robustness](https://www.sciencedirect.com/science/article/abs/pii/S0957417413001395)  
-高次元データを単純複合体で抽出するMapperの手法について  
[Topological methods for the analysis of high dimensional data sets and 3D object recognition. In Proc. Eurographics Symposium on Point-Based Graphics ](http://diglib.eg.org/bitstream/handle/10.2312/SPBG.SPBG07.091-100/091-100.pdf?sequence=1&isAllowed=y)  
### 論文情報・リンク

- [Navigating features: a topologically informed chart of electromyographic features space
Angkoon Phinyomark, Rami N. Khushaba, Esther Ibáñez-Marcelo, Alice Patania, Erik Scheme, Giovanni Petri
J R Soc Interface. 2017 Dec; 14(137): 20170734. Published online 2017 Dec 6. doi: 10.1098/rsif.2017.0734](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5746577/)
