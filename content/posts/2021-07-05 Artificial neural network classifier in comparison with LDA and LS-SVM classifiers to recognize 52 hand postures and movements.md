
---
author: "retact"
title: "Artificial Neural Network Classifier in Comparison With LDA and LS SVM Classifiers to Recognize 52 Hand Postures and Movements"
date: 2021-07-05
draft: false
description: "Artificial neural network classifier in comparison with LDA and LS-SVM classifiers to recognize 52 hand postures and movements"
tags: [
    "EMG"
]

---

## 1. どんなもの？
NINAPRO5のデータを使って，MLPとLDAとLS-SVMの分類器に対してMAV, IAV, RMS, WL, E, ER1, ER2, CCなどと言った時間的特徴を入力し，それぞれの組み合わせの52種類のジェスチャ分類を比較している．全ての特徴を用いてMLPでは96.34%の平均精度，LDAに対してMAVとCCを用いた分類で平均精度84.23%，LS-SVMに対してIAV+MAV+RMS+WLで85.19%の平均精度が算出された．  
 またE，ER1，ER2のような単一の特徴量を用いた場合，MLPは他の2つの分類器と比較して性能が低下すると言った結果も示している．  
<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
● 実用的な観点から価値のある52の動きの分類であること.  
● 分類精度に有効なパラメータの一部が異なるものの、より良い性能を示している.  

## 3. 技術や手法の"キモ"はどこにある？
 ● NINAPRODB5のデータを加工  
 NINAPRO5のデータのうち一人に対するデータを学習させ，10回の動きの繰り返しのうち、9回の繰り返しをトレーニングに、1回の繰り返しをテストに使用した
 また前処理として5Hzのローパスゼロ位相2次バターワースフィルタでフィルタリングをし，2つのウィンドウウィング法によって学習させる信号を選択する.  
 ・1つ目のウィンドウウィング法  
 動きを3つの等しいセグメントに分割し、中央の1.6秒のセグメントを選択する．
 ・2つ目のウィンドウウィング法  
 局所的な最大値の10%を閾値として設定し、この閾値以上の信号を選択する.  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6974753/6993332/6993343/6993343-fig-1-source-small.gif)  
 電極番号3と7のフィルタリングされた信号にこれらの方法を適用した例  
 ● 多層パーセプトロン  
 今回のMLPで使用した活性化関数は双曲線シグモイド関数を利用しており．スケール共役勾配法を利用しており，出力層には52個のニューロンを設定している.．  

## 4. どうやって有効だと検証した？
 ● MLP，LDA，LS-SVM分類器の分類精度をそれぞれの特徴量の組み合わせで比較して評価した結果，，MLPではIAV+RMSと第1ウィンドウ法で92.69%の精度，IAVと第1ウィンドウ法で88.46%の精度，全ての特徴量と第1ウィンドウ法で96.34%の最良の平均分類精度を示した．またLDAではRMSと第1ウィンドウ法で78.84%，IAVとCCと第1ウィンドウ法で84.23%，すべての特徴の組み合わせと第1ウィンドウ法で84.03%の分類精度を示した．LS-SVMではIAVと第1ウィンドウ法で83.57%，IAVとRMSと第1ウィンドウ法で84.82%，MAV+IAV+RMS+WLと第2ウィンドウ法で85.19%の精度を示した．      
 ・MLP classifier  
 ![Figure2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6974753/6993332/6993343/6993343-fig-2-source-small.gif)  
 ・LDA classifier  
 ![Figure3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6974753/6993332/6993343/6993343-fig-3-source-small.gif)  
 ・LS-SVM classifier  
 ![Figure4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6974753/6993332/6993343/6993343-fig-4-source-small.gif)  
## 5. 議論はあるか？
 ● 今回使用したウィンドウウィング法や特徴抽出法は、オンラインアプリケーションでは使用できない  
 ● RMS、E、ER1、ER2は同じ種類のもののため、これらの特徴は組み合わせとしてテストしなかった.  
 ● 第2ウィンドウ法よりも第1ウィンドウ法の方が安定した結果を得られることができる.  

## 6. 次に読むべき論文はあるか？
 ● データベースを用いた先行研究  
 [I. Kuzborskij, A. Gijsberts, B. Caputo, "On the Challenge of Classifying 52 Hand Movements from Surface Electromyography", Proceedings of Annual International Conference on IEEE-EMBS, pp. 4931-4937, 2012.](https://ieeexplore.ieee.org/document/6347099)  


### 論文情報・リンク

- [A. Nazemi and A. Maleki, "Artificial neural network classifier in comparison with LDA and LS-SVM classifiers to recognize 52 hand postures and movements," 2014 4th International Conference on Computer and Knowledge Engineering (ICCKE), 2014, pp. 18-22, doi: 10.1109/ICCKE.2014.6993343.](https://ieeexplore.ieee.org/document/6993343)
