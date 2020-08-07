---
title: 量子コンピューティングの概要
description: 量子コンピューティングとは何か、量子コンピューターで何ができるか、および量子コンピューティングを学習する方法について説明します。
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866980"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>量子コンピューティングと Quantum 開発キットの概要

Microsoft Quantum 開発キット (QDK) は、開発者が量子アルゴリズムを学び、量子プログラムを記述できるように設計されたオープン ソースのツール セットです。 量子コンピューティングは、地球上の環境、農業、健康、エネルギー、気候、材料工学などの分野に関わる最大の課題や、私たちがこれまで経験したことのないその他の問題を解決することを期待されています。  

こうした問題の中には、最も高性能なコンピューターでも問題が発生するものがあります。 量子テクノロジは、コンピューティングの世界に影響を与え始めたばかりですが、その範囲は広大であると考えられ、コンピューティングに関する私たちの考え方を変える可能性があります。

## <a name="what-is-quantum-computing"></a>量子コンピューティングとは

現代の用途では、量子という言葉は、物理特性の考えられる最小の不連続の単位を意味し、通常は、原子または亜原子粒子の特性を表します。 量子コンピューターは、実際の量子粒子、人工原子、または量子粒子の集合的特性を処理単位として使用し、大規模で複雑かつ高価な装置です。

量子コンピューターでは、量子物理学の固有の性質を利用し、それをコンピューティングに適用することで、従来のプログラミング方式に新しい概念をもたらし、重ね合わせ、もつれ、量子干渉などの量子物理学の性質を活用します。

## <a name="what-can-a-quantum-computer-do"></a>量子コンピューターでできること

量子コンピューターはすべてを高速に実行できるスーパーコンピューターではありませんが、量子コンピューターが優れた能力を発揮する分野があります。

- [量子シミュレーション](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [暗号化](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Search](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [最適化](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [機械学習](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>量子シミュレーション

量子コンピューターは、計算に量子現象が活用されるため、他の量子システムをモデル化するのに適しています。 光合成、超伝導、複雑な分子形成は、量子プログラムでシミュレートできる量子メカニズムの例です。

## <a name="cryptography-and-shors-algorithm"></a>暗号とショアのアルゴリズム

1994 年、ピーター・ショアは、スケーラブルな量子コンピューターによって RSA アルゴリズムなどの広く使用されている暗号化手法を解読できることを示しました。 従来の暗号化は、素因数分解や離散対数など、問題解決の難しさを利用していましたが、その多くは量子コンピューターを使用することで、より効率的に解決できます。

## <a name="search-and-grovers-algorithm"></a>検索とグローバーのアルゴリズム

1996 年、ロブ・グローバーは、非構造化データ検索の求解を大幅に高速化する量子アルゴリズムを開発し、従来のどのアルゴリズムよりも少ない手順で検索を実行できるようにしました。

## <a name="quantum-inspired-computing-and-optimization"></a>量子から着想を得たコンピューティングと最適化

量子から着想を得たアルゴリズムは、速度と精度の向上のために量子の原則を利用しますが、従来型コンピューター システムに実装されます。 このアプローチを使用すると、開発者は、いまだ新興の業界である量子ハードウェアを待たなくても、新しい量子手法の力を活用できます。

最適化は、所望の結果と制約をふまえて、問題に対する最適な解を見つけるプロセスです。 コスト、品質、生産時間などの要因はすべて、産業と科学で行われる重要な意思決定にかかわってきます。 量子から着想を得た最適化アルゴリズムを現在の従来型コンピューターで実行することで、これまで不可能だった解を見つけることができます。 渋滞を軽減するための交通量の最適化に加え、飛行機のゲート割り当て、小包配送、作業の日程計画などがあります。 材料工学で画期的な技術が開発されると、新しい形態のエネルギー、大容量のバッテリー、軽くて耐久性に優れた素材が現れます。

> [!NOTE]
> [材料工学](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[リスク管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)、[医薬](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)で、量子から着想を得た Microsoft のコンピューティングがどのように利用されているかをご覧ください。

## <a name="quantum-machine-learning"></a>量子機械学習

従来型コンピューターでの機械学習は、科学とビジネスの世界に大きな変革をもたらしています。 ただし、モデルのトレーニングのコンピューティング コストが高額なことが、この分野の発展と広がりの妨げになっています。 量子機械学習の分野では、従来型コンピューターより高速に動作する機械学習を可能にする、量子ソフトウェアを考案して実装する方法を探求します。

Quantum 開発キットには [Quantum Machine Learning Library](xref:microsoft.quantum.machine-learning.concepts.intro) が付属しています。これを使用すると、量子/従来型のハイブリッド機械学習の実験を行うことができます。 このライブラリには、サンプルとチュートリアルが含まれています。また、教師あり分類問題を解決するための新たな量子/従来型ハイブリッド アルゴリズムである回路中心量子分類器の実装に必要なツールが用意されています。

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# と Microsoft Quantum 開発キット (QDK)

Q# は、量子アルゴリズムを開発および実行するための Microsoft のオープンソース プログラミング言語です。 これは [QDK](https://docs.microsoft.com/quantum/) に含まれています。QDK は Q# 用のフル機能の開発キットであり、組み込みの全状態の量子シミュレーターなど、さまざまな環境で実行できる量子アプリケーションを開発するために、標準のツールと言語で使用できます。

Visual Studio と VS Code 用の拡張機能と、Python と Jupyter Notebook で使用するためのパッケージが用意されています。

QDK には、化学、機械学習、数値の特殊ライブラリとともに標準ライブラリが含まれています。

このドキュメントには、すぐに開始できるようにするための Q# 言語ガイド、チュートリアル、サンプル コードが含まれています。また、量子コンピューティングの概念を深く理解するのに役立つ豊富な記事が掲載されています。  

## <a name="microsoft-quantum-hardware-partners"></a>Microsoft の量子ハードウェアのパートナー

開発者がクラウドで量子ハードウェアにアクセスできるように、Microsoft は量子ハードウェア メーカーと提携しています。 開発者は、[Azure Quantum](https://azure.microsoft.com/services/quantum/) プラットフォームと Q# 言語 を利用して、さまざまな種類の量子ハードウェアで量子アルゴリズムを探求し、量子プログラムを実行できます。

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) と [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) は両方とも、**捕捉イオン ベース**のプロセッサを使用し、電子場に捕捉された個々のイオンを利用しています。それに対し、[QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) では、超伝導回路を使用しています。

## <a name="next-steps"></a>次のステップ

[量子コンピューティングの主要な概念](xref:microsoft.quantum.overview.understanding)
[クイックスタート](xref:microsoft.quantum.welcome)