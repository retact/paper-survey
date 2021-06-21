
---
author: "retact"
title: "Building the Ninapro Database: A Resource for the Biorobotics Community"
date: 2021-06-20
description: "Building the Ninapro Database: A Resource for the Biorobot Community"
tags: [
    "EMG"
]

---

## 1. どんなもの？
筋電図のデータセットで、ASCIIフォーマットで27人の健常者の52のジェスチャーの運動データのsEMGデータが含まれており、数年に渡って100人以上の健常者と50人以上の切断者のデータが追加されることが計画されているため、撮影設定，実験プロトコル,データの保存形式などが示されている。またこのデータベースに対してLeast-Squares SVMによる分類評価も行っている。


<!--more-->  

## 2. 先行研究と比べてどこがすごいの？
これまでのデータベースでは人間の手の器用さや患者が日常生活で必要とするものとはかなりかけ離れている他、少数の被験者からしかデータを取得していないため，性別，年齢，切断の特徴などを考慮して得られた結果のロバスト性をを評価することが難しい。そこで健常者、切断者含めた大量のデータとデータを収集するための広く受け入れられた標準的なプロトコルを提案することで今後の筋電義手開発に役に立つデータベースを提供する他に、これまでの対象となる被験者と動作の数を大幅に増やしたデータベース作成を試みている。  
## 3. 技術や手法の"キモ"はどこにある？
 ● 運動データを取得  
 運動データは22個のセンサを備えたCyberglove IIというグローブ型の歪みゲージを利用したセンサを使って取得している。22個の関節の角度を8ビットの値で表現しており、バーチャルリアリティ、臨床、学術の分野で標準的な手の姿勢収集装置となっているらしい....   
 ![Figure 1](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6275757/6290255/6290287/6290287-fig-1-source-small.gif)  
 ● データベース(sEMG,運動データなどの形式)
 今回のデータベース27名の健常者（20M/7F，25/2右/左利き，年齢28±3.4歳）のデータが含まれており、sEMGと傾斜計のデータ，運動データ，刺激のデータの3つのデータファイルが，前処理を行わずASCII形式で保存されている。また，各被験者について5枚の写真が保存されており，各ポーズの写真が3枚，前腕と手の写真が2枚ある。センサの取得場所は(fig1)を参照  

 ● データプロトコル  
 データを取得するにあたり、ヴァレー州（スイス）の倫理委員会の承認を得ており、WMA（世界医師会）のヘルシンキ宣言の遵守を徹底する。  
 また個人情報として年齢、性別、身長、体重、運動、側性、自己申告の健康状態などを記録し、切断者の場合は、年齢、種類、切断の理由、義肢の使用状況、その使用による利点と結果、幻肢の感覚と痛みの種類と程度など記録し、切断部分の写真を2枚撮影する。データは一定の期間匿名で保存され被験者の要求に応じて削除する。取得するデータは12種類の指の基本動作、8つの等尺性，等張性の手の構成、手首の9つの基本動作、23種類の把持および機能的動作の52種類の動作を取得する。(fig2)  
 またデータ取得の際に被験者は，調整可能な椅子に座りテーブルの前に座る。右手にはsEMG電極，データグローブ，傾斜計を装着する。被験者はスクリーンに表示される動画を見て、動画に描かれた動きをできるだけ正確に再現し、データを取得する。また手順に慣れるための訓練段階があり、本番は５秒の動作と3秒のインターバルで各クラスの動きを10回繰り返す連続したシリーズを被験者に提示し、一人あたり合計で約100分の実験となる。  
 ![Figure 2](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6275757/6290255/6290287/6290287-fig-2-source-small.gif)  
 
## 4. どうやって有効だと検証した？
 ● NinaProのデータベースにおける取得する動作数の増加が分類精度に悪影響を及ぼすかどうかを実験的に調べるために、前処理(100Hzに線形補完→2次バターワースフィルタ→1Hzローパス→３つにセグメントの真中のデータを各動作で平均し10のサンプル化)し(fig3)主成分分析したデータ(fig4)をLS-SVMを用いて分類し誤差を評価したところ、10%から20%の範囲であり、実験プロトコルとデータの正しさを示している。

  ![Figure 3](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6275757/6290255/6290287/6290287-fig-3-source-large.gif)  
  ![Figure 4](https://ieeexplore.ieee.org/mediastore_new/IEEE/content/media/6275757/6290255/6290287/6290287-fig-4-source-large.gif)  

## 5. 議論はあるか？
 ● 分類誤差の標準偏差が比較的大きいことから被験者ごとに分類性能に大きなばらつきがあり、分類タスクの確実性を高めるためには多数の被験者が必要  

## 6. 次に読むべき論文はあるか？
 
 AHPについてもっとも明確に述べている論文  
 [Control of Multifunctional Prosthetic Hands by Processing the Electromyographic Signal](https://www.dl.begellhouse.com/journals/4b27cbfc562e21b8,5b51f41866ab7f77,5d2cbc051cfa16a4.html)  
 -
### 論文情報・リンク

- [M. Atzori et al., "Building the Ninapro database: A resource for the biorobotics community," 2012 4th IEEE RAS & EMBS International Conference on Biomedical Robotics and Biomechatronics (BioRob), 2012, pp. 1258-1265, doi: 10.1109/BioRob.2012.6290287.](https://ieeexplore.ieee.org/document/6290287)
