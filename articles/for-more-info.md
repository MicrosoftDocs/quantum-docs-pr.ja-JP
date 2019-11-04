---
title: クォンタムコンピューティングの学習リソース |Microsoft Docs
description: クォンタムコンピューターのプログラミングの詳細については、「クォンタムコンピューティングの詳細」トピックを参照してください。
author: QuantumWriter
uid: microsoft.quantum.more-information
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7302acddb37a30ad3d20cabd08ce31d90bd155dc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442522"
---
# <a name="more-quantum-computing-learning-resources"></a>その他の量子コンピューティング学習リソース

この概要では、この簡単な概要では、データを単位ベクトルとして指数関数的に大きなベクトル空間に格納するデバイスとしてクォンタムコンピューターを表示する方法について説明し、calcul を実行するためにクォンタムゲートを使用して情報をローテーションする方法について見てきました。招待.  また、クォンタム回線や Dirac 表記などのクォンタム操作を記述するために役立つ言語についても説明しました。これにより、複雑なクォンタムの状態やサブルーチンを開発者がすばやく理解できるようになります。

これらのツールは、quantum ソフトウェアの開発者にとって基本的なものですが、クォンタムコンピューターのプログラミングとアルゴリズムの設計に関してよく知られている内容の深さや幅には意味がありません。  クォンタムコンピューティングは迅速に開発できるフィールドであるため、問題を解決するためにこれらのツールを最大限に活用する方法を学ぶために必要なすべての情報が含まれたリソースは1つもありません。  このため、クォンタムコンピューターのプログラミングの最先端と美しさについて学習する必要がある参照リストをコンパイルしました。
このセクションには、クォンタムコンピューティングに関するトピックの詳細な説明が含まれています。

## <a name="basic-quantum-computing"></a>基本的なクォンタムコンピューティング ##

+ これは、M. A です。 & 語, I. L. (2010)、 クォンタムの計算とクォンタムの情報。 クォンタムの計算とクォンタムの情報、英国: ケンブリッジ大学プレス、2010。
+ Kitaev、A. Y.、Shen、A.、& Vyalyi、M. N。 (2002)。 古典およびクォンタム計算 (Vol. 47)。 Providence: アメリカの数学的社会。
+ Kaye、P.、Laflamme、R.、& Mosca、M. (2007)。 クォンタムコンピューティングの概要。 Oxford 大学のプレス。
+ Rieffel、、& Polak、W. H。 (2011)。 クォンタムコンピューティング: 簡単に紹介します。 MIT Press。

## <a name="elementary-techniques-for-building-controlled-gates"></a>制御ゲートを構築するための基本的な手法 ##

+ Barenco、A.、Bennett、Cleve、、R.、DiVincenzo、d.、Margolus、N.、Shor、P......& Weinfurter, H. (1995)。 クォンタム計算の基本ゲート。 物理的な確認 A、52 (5)、3457。
+ Jones、c. (2013)。 フォールトトレラントな Toffoli ゲートのオーバーヘッドの低い構造。 物理的なレビュー A、87 (2)、022328

## <a name="techniques-for-preparing-quantum-states"></a>クォンタムの状態を準備する方法 ##

+ Shende、V. V.、Markov、、& の、バルクロック、s. s. (2004)。 最小のユニバーサル2ビット制御の非ベース回線。 物理的な確認 A、69 (6)、062321。
+ Ozols、M.、Roetteler、M.、& ローランド、J. (2013)。 クォンタム拒否のサンプリング。 計算理論 (TOCT)、5 (3)、11での ACM トランザクション。
+ Grover、L.、& Rudolph、T. (2002)。 効率的に可能な確率分布に対応するスーパーポジションを作成する。 arXiv preprint quant-ph/0208112。
+ Farhi、E.、Goldstone、J.、Gutmann、S.、& Sipser、M. (2000)。 Adiabatic 進化によるクォンタムの計算。 arXiv preprint quant-ph/0001106。

## <a name="approaches-for-synthesizing-circuits-out-of-h-t-and-cnot-gates"></a>H、T、CNOT ゲートからから回線を使用する方法 ##

+ Kliuch氏、Maslov、D.、& Mosca、M. (2013)。 Asymptotically は、付加的な補助 qubit を使用して、Clifford と T サーキットによって1つの qubit unitaries 最適に近似します。 物理的なレビュー用レター、110 (19)、190502。
+ Ross、、& Selinger、P. (2014)。 Z 回転の ancilla を無料で Clifford + T 近似します。 arXiv preprint arXiv: 1403.2975。
+ Kliuch氏、V. (2013)。 Clifford + T 回線を使用した unitaries の合成。 arXiv preprint arXiv: 1306.3200。
+ Jones、N.n.n.n、McMahon、Yung chou、Yamamoto、Zメートル、R.、Asz u-Guzik、A.、&, Y. (2012) を入力します ()。このような場合は、、Y. () のようになります。 フォールトトレラントなクォンタムコンピューターでのより高速な量子化学シミュレーション。 物理、14 (11)、115023の新しい履歴。

## <a name="approaches-for-quantum-arithmetic"></a>クォンタムの算術演算の方法 ##

+ Takahashi, Y.、& Kunihiro, N. (2005)。 補助 qubits を追加するための、線形サイズのクォンタム回線。 クォンタム情報 & 計算、5 (6)、440-448。
+ Draper, T. G. (2000)。 クォンタムコンピューターへの追加。 arXiv preprint quant-ph/0008033。
+ Soeken, M.、Roetteler、M.、Wiebe、N.、& De Micheli、G. (2017 年3月)。 クォンタムコンピューターの設計の自動化とデザイン領域の探索。 2017設計では、Automation & 欧州カンファレンス & 上映 (DATE) (pp. 470-475) でテストします。 IEEE.

## <a name="methods-for-fast-quantum-sampling-amplitude-amplification-and-probability-estimation"></a>高速クォンタムサンプリング (振幅増幅) と確率推定のメソッド ##

+ Brassard Hoyer、P.、Mosca、M.、& Tapp、A. (2002)。 クォンタムの振幅増幅と推定。 最新の数学、305、53-74。
+ Grover、L. K. (2005)。 固定ポイントのクォンタム検索。 物理的なレビュー用レター、95 (15)、150501。
+ Berry、Childs &、、Kothari、R. (2015, 10 月)...。 すべてのパラメーターに最も最適化された依存関係を持つ Hamiltonian シミュレーション。 コンピューターサイエンス (FOC) の基礎として、2015 IEEE 56th 年間 Symposium on (pp. 792-809) をご活用ください。 IEEE.

## <a name="algorithms-for-quantum-simulation"></a>クォンタムシミュレーションのアルゴリズム ##

+ Lloyd, S. (1996)。 Universal Quantum シミュレーター。 [サイエンス (ニューヨーク、NY)、273 (5278)、1073](http://doi.org/10.1126/science.273.5278.1073)。
+ Berry、d.、Childs、Cleve、R.、Kothari、R.、& Somma、R. D. を行います。 (2015)。 Taylor シリーズを切り捨てて Hamiltonian dynamics をシミュレートする。 [物理的なレビュー用レター、114 (9)、090502](http://doi.org/10.1103/PhysRevLett.114.090502)。
+ 低、語、&、I. L。 (2017)。 [クォンタムシグナル処理による最適な Hamiltonian シミュレーション](https://arxiv.org/abs/1606.02685)。 [物理的な確認文字、118 (1)、010501](http://doi.org/10.1103/PhysRevLett.118.010501)。
+ 低、語、&、I. L。 (2016)。 Qubitization による Hamiltonian シミュレーション。 [Arxiv preprint: 1610.06546](https://arxiv.org/abs/1610.06546)。
+ Reiher、M.、Wiebe、N.、Svore、K. M.、、D.、& Troyer、M. (2017)。 クォンタムコンピューターの Elucidating 反力メカニズム。 [米国国立 Academy の201619152の手続き](http://doi.org/10.1073/pnas.1619152114)。
+ Wiebe、N.、Berry、d.、Høyer、P.、& サンダース、b. C。 (2011)。 クォンタムコンピューターでの quantum dynamics のシミュレーション。 [物理のジャーナル: 数学と理論的、44 (44)、445308](http://doi.org/10.1088/1751-8113/44/44/445308)。
+ Peruzzo、A.、McClean、J.、Shadbolt、P.、Yung chou、m.、Zhou、X. Q.、愛、p......& Obrien, J. L. (2014)。 Photonic クォンタムプロセッサ上の可変の eigenvalue ソルバー。 [自然通信、5](http://doi.org/10.1038/ncomms5213).

## <a name="procedures-for-quantum-optimization"></a>クォンタムの最適化の手順 ##

+ Durr、C.、& Høyer、P. (1996)。 最小値を検索するためのクォンタムアルゴリズム。 arXiv preprint quantph/9607014。
+ Farhi、E.、Goldstone、J.、& Gutmann、S. (2014)。 クォンタムのおおよその最適化アルゴリズム。 arXiv preprint arXiv: 1411.4028。
+ Brandao、f.、Svore K. M. (2017)。 Semidefinite プログラミングのクォンタム速度。 コンピューターサイエンス (FOC 2017) を基盤とする年間 Symposium。
