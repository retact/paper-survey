
---
author: "retact"
title: "A Preliminary Analysis of Analysis Window Size and Voting Size With a Time Delay for a Robust Real Time SEMG Pattern Recognition"
date: 2021-07-28
draft: false
description: "description"
tags: [
    "EMG"
]

---

## 1. どんなもの？
動作の開始時と終了時の不安定なEMGにおいて，分類精度と速度はトレードオフの関係であり，信号処理の解析ウィンドウサイズと分類の投票サイズのパラメータから，パターン認識の精度の限界を調べたものである．またGoogleEarthを用いたパイロット試験を通じて解析ウィンドウサイズと投票サイズの有用なガイドラインを提案している．  


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
解析ウィンドウサイズの最適値や筋電義手の最適な制御遅延をリアルタイムで求める試みは行われているが，システムの速度を変化させるパラメータである信号の解析窓サイズと分類の時のvoting sizeを求め，パイロット試験から適切な遅延量とパラメータを求める研究は行われていない
## 3. 技術や手法の"キモ"はどこにある？
 ● 動作分類のシステム  
 分類する動作は10種類で以下の図のような信号処理を行い，分類器アルゴリズムには迅速に分類すること野できるELMを用いて分類する．  
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6991442/7057367/7057411/7057411-fig-3-source-small.gif)  
 ● 投票方式とその大きさの関係  
 投票するサイズに関しては以下のような処理を元に分類が行われるようになっている．  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6991442/7057367/7057411/7057411-fig-1-source-small.gif)  
 ● 解析ウィンドウサイズ  
 検証するウィンドウサイズは100ms-600msをけんしょうし，ShiftSizeを10msにしている．  
 ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6991442/7057367/7057411/7057411-fig-5-source-small.gif)  

## 4. どうやって有効だと検証した？
 ● データの取得は3秒間を行い3秒回のインターバルで10種類の動作を5回ずつ思考するセッションを3回行う.  
 ● システムの性能を表すために投票サイズと解析ウィンドウサイズと分類精度の関係をグラフ化した.  
 ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6991442/7057367/7057411/7057411-fig-8-source-small.gif)  
 ● GoogleEarthを用いたパイロットテストを行なった結果，高い分類精度であれば時間遅延が0.5〜0.6秒であってもユーザーは違和感を感じなかった．  

## 5. 議論はあるか？
 ● 異なる特徴量，分類器，アルゴリズムで検証する必要がある.  
 ● 過渡状態を減らす必要がある．  
 
## 6. 次に読むべき論文はあるか？
-速度と分類精度はトレードオフであることを示している論文  
[A robust, real-time control scheme for multifunction myoelectric control](https://ieeexplore.ieee.org/document/1206493)  

### 論文情報・リンク

- [M. Kim, J. Lee, H. Ko and K. Kim, "A preliminary analysis of analysis window size and voting size with a time delay for a robust real-time sEMG pattern recognition," 2014 11th International Conference on Ubiquitous Robots and Ambient Intelligence (URAI), 2014, pp. 121-126, doi: 10.1109/URAI.2014.7057411.](https://ieeexplore.ieee.org/document/7057411)
