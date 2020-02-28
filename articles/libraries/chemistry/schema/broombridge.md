---
title: Broombridge-量子化学スキーマ
description: Microsoft Quantum Development Kit で実際の化学の問題をモデル化するために使用される Broombridge quantum の化学スキーマの概要。
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907819"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化学スキーマ # 

[Nwchem](http://www.nwchem-sw.org/)などの強力な計算化学ソフトウェアを使用すると、さまざまな現実世界の化学問題をモデル化できます。 Microsoft Quantum の化学ライブラリを使用して NWChem 分子モデルにアクセスするには、 **Broombridge**を呼び出す[yaml](https://en.wikipedia.org/wiki/YAML)ベースのスキーマを使用します。 この名前は、Hamiltonians の birthplace として celebrated されている一部の円の[ランドマーク](https://en.wikipedia.org/wiki/Broom_Bridge)の参照で選択されています。 

[Nwchem](https://github.com/nwchemgit/nwchem)は、許可されていない教育コミュニティライセンス (ECL) 2.0 ライセンスでライセンス供与されたオープンソースプロジェクトです。 Broombridge は、[ここで](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)指定するオープンソーススキーマであり、MIT ライセンスの下でライセンスされている[RFC 2119](https://tools.ietf.org/html/rfc2119)および[検証ツールスクリプト](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)に続く[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)が付属しています。 

YAML ベースで、Broombridge は、電子的な構造の問題を表す、ユーザーが判読できる、ユーザーが編集できる、構造化されたユーザーが編集できる方法です。 特に、次のデータを表すことができます。 
- Fermionic Hamiltonians は、1つと2つの電子積分を使用して表すことができます。 
- 作成シーケンスを使用して、グラウンドと興奮の状態を表示できます。
- エネルギーレベルの上限と下限を指定できます。

データ形式は、NWChem から簡単に生成できます。たとえば、NWChem のフルインストールから、[この例](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)のようなさまざまな方法を使用できます。また、Broombridge の一部として実行の一部として出力されます。これは、Broombridge を化学デッキから生成するためにも使用できます。 最後に、化学ソフトウェアをインストールしなくても、計算化学をすばやく開始するための視覚的な方法は、NWChem への[Emsl 矢印](https://arrows.emsl.pnnl.gov/api/qsharp_chem)インターフェイスによって提供されます。 

大まかに言えば、NWChem と Microsoft Quantum Development Kit 間のクロスプレイは次のように視覚化できます。 ![化学スタック](~/media/broombridge.png) 青い網掛けされたボックスは Broombridge スキーマを表し、灰色のさまざまなボックスは、実際の化学の問題に基づいて計算化学のクォンタムアルゴリズムを表すために選択されたその他の内部データ表現を表します。 

Broombridge スキーマを使用して定義されている複数の化学表現が[ここ](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)に記載されています。
