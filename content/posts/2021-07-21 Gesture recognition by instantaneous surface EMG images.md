
---
author: "retact"
title: "Gesture Recognition by Instantaneous Surface EMG Images"
date: 2021-07-21
draft: false
description: "description"
tags: [
    "EMG"
]

---

## 1. どんなもの？
特定の瞬間のHD-sEMGによるジェスチャー認識法.高密度のsEMGから画像データを生成しDeepLearningによって識別する実験をおこなったところ，窓付き特徴量を用いず8つのジェスチャー識別において，89.3%の識別精度が得られ，52個のジェスチャー分類においても先行研究より優れた結果を得られた．



<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
● 今回使用する瞬間sEMG画像はこれまで利用されていたRojasらのsEMGマップと比べて，フレーム単位のジェスチャー認識に対応するために作られたものであり，ジェスチャー識別において優れた結果を示している． 　
## 3. 技術や手法の"キモ"はどこにある？
 ● 瞬間的なsEMG画像を用いたtest-bedの概略  
 HD-sEMG信号の各サンプリング・モーメントの瞬時値を，電極の位置関係に応じて2次元のグリッドに配置し，mVから線形変換を行うことで瞬間的なsEMG画像を生成している．  
 ![Figure 1](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fsrep36571/MediaObjects/41598_2016_Article_BFsrep36571_Fig2_HTML.jpg?as=webp)  
 Schematic illustration of gesture recognition by instantaneous sEMG images  
  
 ● 非侵襲的なウェアラブルデバイスを開発  
 7.5×10.05mmの電極間距離で2×8のマトリクス電極を用いて，128チャンネルで16bit1000Hzでサンプリングされる．  
   

## 4. どうやって有効だと検証した？
 ● CapgMyoデータベースを作成し，脳波画像と脳波差分画像において，それぞれ，1枚で89.3%，84.6% 150フレームと149枚の差分で99.5%,99.4%の精度を示した．  
 ● ConvNetを従来の識別法のMLP,KNN,SVM,RF,LDAに変えて，古典的なフレームワークでも実用的か検証した．  
 ● CSL-HDEMGデータセットを用いて27の指のジェスチャー分類を行なった結果，全てのセグメントの多数決による分類において96.8%の精度を示した．  
 ● Ninaproデータベース35において瞬間的な脳波画像の認識精度は，DB1で78.9％，DB2で76.1％の精度を示した．  
 
## 5. 議論はあるか？
 ● Convnetを利用した分類は計算リソースが高い．  
 ● 計測する人によってのパターン認識における生物的な理解は深まっていない．  
 ● 動的なジェスチャー認識の実用化  

### 論文情報・リンク

- [Geng, W., Du, Y., Jin, W. et al. Gesture recognition by instantaneous surface EMG images. Sci Rep 6, 36571 (2016). https://doi.org/10.1038/srep36571](https://www.nature.com/articles/srep36571)  
