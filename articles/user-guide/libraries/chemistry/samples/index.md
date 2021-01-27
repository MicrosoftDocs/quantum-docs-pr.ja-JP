---
title: 量子化学のサンプル アプリケーション
description: Microsoft Quantum Chemistry Library のサンプル アプリケーションについて確認します。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a8740f9c94ca733e24012aaf5c80b15b731c2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858919"
---
# <a name="quantum-chemistry-examples"></a>量子化学の例

量子化学の概念では、フェルミオン ハミルトニアンの例を手動で構築しました。 [ハミルトニアン ダイナミクスのシミュレーション](xref:microsoft.quantum.libraries.standard.algorithms)で説明した化学シミュレーション アルゴリズムは、規範ライブラリの[量子位相推定](xref:microsoft.quantum.libraries.characterization)に統合されています。 この組み合わせにより、分子で表されるエネルギー レベルを推定することができます。量子コンピューターの量子化学が主に応用されているのが、分子です。 

ハミルトニアンの用語を 1 つずつ指定する代わりに、大規模な量子化学実験の実行を可能にするいくつかの例についても説明します。 最初に、[Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)でエンコードされた化学ハミルトニアンを読み込む例から始めます。

[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でシミュレートするには大きすぎる分子でも、興味深い科学を実行できます。 たとえば、大規模な化学シミュレーションを実行するリソース コストは、[トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を対象にすることで評価できます。

提供された例のいくつかを使用して、化学シミュレーション ライブラリの興味深い応用例を説明します。
