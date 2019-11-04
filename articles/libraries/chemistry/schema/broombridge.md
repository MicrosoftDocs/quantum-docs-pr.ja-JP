---
title: Broombridge-量子化学スキーマ
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: c2a7636d0b3f07419e3312e04da5d811229ad854
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185326"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化学スキーマ # 

[Nwchem](http://www.nwchem-sw.org/)などの強力な計算化学ソフトウェアを使用すると、さまざまな現実世界の化学問題をモデル化できます。 Microsoft Quantum の化学ライブラリを使用して NWChem 分子モデルにアクセスするには、 **Broombridge**を呼び出す[yaml](https://en.wikipedia.org/wiki/YAML)ベースのスキーマを使用します。 この名前は、Hamiltonians の birthplace として celebrated されている一部の円の[ランドマーク](https://en.wikipedia.org/wiki/Broom_Bridge)の参照で選択されています。 

[Nwchem](https://github.com/nwchemgit/nwchem)は、許可されていない教育コミュニティライセンス (ECL) 2.0 ライセンスでライセンス供与されたオープンソースプロジェクトです。 Broombridge は、[ここで](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)指定するオープンソーススキーマであり、MIT ライセンスの下でライセンスされている[RFC 2119](https://tools.ietf.org/html/rfc2119)および[検証ツールスクリプト](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)に続く[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)が付属しています。 

YAML ベースで、Broombridge は、電子的な構造の問題を表す、ユーザーが判読できる、ユーザーが編集できる、構造化されたユーザーが編集できる方法です。 特に、次のデータを表すことができます。 
- Fermionic Hamiltonians は、1つと2つの電子積分を使用して表すことができます。 
- 作成シーケンスを使用して、グラウンドと興奮の状態を表示できます。
- エネルギーレベルの上限と下限を指定できます。

データ形式は、NWChem から簡単に生成することができます。たとえば、NWChem のフルインストールから、[ここで](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)提供されているような化学デッキを実行したり、実行の一環として docker 経由で Broombridge を出力したりするさまざまな方法が用意されています。Broombridge を化学デッキから生成するために使用することもできる NWchem の画像。 最後に、化学ソフトウェアをインストールしなくても、計算化学をすばやく開始するための視覚的な方法は、NWChem への[Emsl 矢印](https://arrows.emsl.pnnl.gov/api/qsharp_chem)インターフェイスによって提供されます。 

大まかに言えば、nwchem と Microsoft Quantum Development Kit 間の相互作用は次のように視覚化できます。 ![化学スタック](~/media/broombridge.png) 青色で網掛けされたボックスは Broombridge スキーマを表し、灰色の影が付いたさまざまなボックスは他の内部を表します。現実世界の化学の問題に基づいて計算化学のクォンタムアルゴリズムを表現し、処理するために選択されたデータ表現。 

Broombridge スキーマを使用して定義されている複数の化学表現が[ここ](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)に記載されています。

