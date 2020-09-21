---
title: Broombridge 量子化学スキーマ
description: Microsoft Quantum Development Kit で実際の化学の問題をモデル化するために使用される Broombridge quantum の化学スキーマの概要。
author: martinro
ms.author: martinro
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: e580fd8267cc7ba30533d557eceb486f8c205be6
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835776"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge 量子化学スキーマ # 

[Nwchem](http://www.nwchem-sw.org/)などの強力な計算化学ソフトウェアを使用すると、現実世界のさまざまな化学問題をモデル化できます。 Microsoft Quantum の化学ライブラリを使用して NWChem 分子モデルにアクセスするには、 **Broombridge**という名前の[yaml](https://en.wikipedia.org/wiki/YAML)ベースのスキーマを使用します。 この名前は、Hamiltonians の birthplace として celebrated されている一部の円の [ランドマーク](https://en.wikipedia.org/wiki/Broom_Bridge) の参照で選択されています。 

[Nwchem](https://github.com/nwchemgit/nwchem) は、許可されていない教育コミュニティライセンス (ECL) 2.0 ライセンスでライセンス供与されたオープンソースプロジェクトです。 [Broombridge Quantum の化学スキーマ](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) は、 [RFC 2119](https://tools.ietf.org/html/rfc2119)に続く[定義](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json)と MIT ライセンスでライセンスされた[検証スクリプト](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py)を含むオープンソーススキーマです。 

YAML ベースで、Broombridge は、電子的な構造の問題を表す、ユーザーが判読できる、ユーザーが編集できる、構造化されたユーザーが編集できる方法です。 特に、次のデータを表すことができます。
- Fermionic Hamiltonians は、1つと2つの電子積分を使用して表すことができます。
- 作成シーケンスを使用して、グラウンドと興奮の状態を表示できます。
- エネルギーレベルの上限と下限を指定できます。

複数のメソッドを使用して NWChem からデータを生成できます。たとえば、nwchem のフルインストールを使用して、実行の一部として Broombridge を出力する [nwchem ライブラリ](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) に用意されているような方法や、Broombridge を化学デッキから生成するために使用できる nwchem の docker イメージなどです。 化学ソフトウェアをインストールしなくても計算化学をすばやく開始するには、 [Emsl 矢印](https://arrows.emsl.pnnl.gov/api/qsharp_chem)によって提供される NWChem のビジュアルインターフェイスを使用できます。

大まかに言えば、NWChem と Microsoft Quantum Development Kit 間のクロスプレイは次のように視覚化できます。 ![ 化学 stack ](~/media/broombridge.png) 青い網掛けされたボックスは Broombridge スキーマを表し、灰色のさまざまなボックスは、実際の化学の問題に基づいて計算化学のクォンタムアルゴリズムを表すために選択された他の内部データ表現を表します。

クォンタム開発キットのサンプルリポジトリの [整数/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) フォルダーには、Broombridge スキーマを使用して定義された複数の化学表現が含まれています。
