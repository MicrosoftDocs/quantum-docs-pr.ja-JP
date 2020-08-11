---
title: Microsoft Quantum 開発キットに貢献する
description: Microsoft Quantum 開発キットと量子開発コミュニティに貢献する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0fbbe127b9f4c6b98bdc2cf0e46098bf40a816e3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866861"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Quantum Development Kit に貢献する

Quantum Development Kit は、量子プログラムを作成するための単なるツールの集まりではありません。
これは、量子コンピューティングの研究、量子アルゴリズムを使用した調査、量子デバイス向けの新しいアプリケーションの開発、および量子プログラミングを最大限に活用するためのその他の作業を行う人々の広範囲のコミュニティの一部です。
このコミュニティのメンバーとして、Quantum Development Kit は、さまざまな背景を持つ量子開発者に必要な機能を提供することを目的としています。
Quantum Development Kit へのコントリビューションは、他の量子開発者が使用するツールの改善、それらのツールの文書化、さらに量子プログラミング コミュニティでの発見や作成を改善するために役立つ新しい機能の作成などを通じて、このような目的を実現するために役立ちます。
Microsoft は、皆さんのコントリビューション、そして皆さんと協力してコミュニティを最大限に活用できる機会を非常にうれしく思います。 

このガイドでは、より広い量子プログラミング コミュニティへのコントリビューションを可能な限り有益なものにする方法に関するアドバイスを提供します。

## <a name="building-community"></a>コミュニティの構築

コントリビューションを行うときは、まず自分が貢献しているコミュニティを常に念頭に置く必要があります。
量子プログラミング コミュニティだけでなく、より広い範囲の仲間に対して礼儀正しく専門的に行動することで、皆さんの努力で最善の最も有効的なコミュニティを構築することができます。

この取り組みの一環として、すべての Quantum Development Kit プロジェクトは、[Microsoft オープンソースの倫理規定](https://opensource.microsoft.com/codeofconduct/)を採用しています。
詳しくは、[倫理規定についてよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)に関する記事を参照するか、[opencode@microsoft.com](mailto:opencode@microsoft.com) 宛てに質問またはコメントをお送りください。

## <a name="what-kinds-of-contributions-help-the-community"></a>どのようなコントリビューションがコミュニティに役立ちますか。

コントリビューションを通じて、量子プログラミング コミュニティを支援する方法はさまざまです。
このガイドでは、Quantum Development Kit に特に関連する 3 つの方法に焦点を当てます。
これらの方法はすべて、ユーザーを支援する量子コミュニティの構築に不可欠です。
ただし、これがすべてという訳ではありません。量子プログラミングの発展のため、コミュニティの構築に役立つその他の方法を調べることをお勧めします。

- **バグの報告** バグとその他の種類の問題を修正するための最初の手順は、それらを特定することです。 Quantum Development Kit でバグを発見した場合は、その問題を修正し、量子プログラミング コミュニティに向けたより優れたツール セットを作成できるよう、ぜひご報告ください。
- **ドキュメントの改善** ドキュメント セットは、常に改善し、より詳細な情報を記述し、アクセスしやすくすることができます。
- **コードの開発協力** 当然ながら、最も直接的に貢献する方法の 1 つは、新しいコードを Quantum Development Kit に追加することです。

このようなさまざまな種類のコントリビューションは、すべて非常に価値があり、高く評価されます。
このガイドの残りの部分では、各種コントリビューションを行う方法についてのアドバイスを提供します。

## <a name="where-do-contributions-go"></a>コントリビューションはどこで行いますか。

Quantum Development Kit には、量子プログラムを作成するためのプラットフォームを実現するために連携する多くの構成要素が含まれています。
これらの各構成要素は別々のリポジトリに存在しているため、最初に行うべきことの 1 つが各コントリビューションに最適な場所がどこかを整理することです。

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum):Quantum Development Kit の使用を開始するためのサンプルとツール。
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries):Quantum Development Kit 用の標準およびドメイン固有のライブラリ。
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas):量子コンピューティングと Q# プログラミング言語を学習するためのマイペースで進められるプログラミング演習。
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler):Q# コンパイラ、Visual Studio 拡張機能、および Visual Studio Code 拡張機能。
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime):Quantum Development Kit のシミュレーション フレームワーク、コード生成、シミュレーション ターゲット マシン。
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp):Jupyter カーネル、Q# の Python ホスト機能、およびクラウド環境で IQ# を使用するための Docker イメージ。
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): https://docs.microsoft.com/quantum で公開されているドキュメントのソース コード。

> [!NOTE]
> 現時点では、[**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) リポジトリに関するコードとドキュメントのコントリビューションは受け付けておりませんが、バグ報告については歓迎しています。

また、Quantum Development Kit に関連する補助機能に重点を置いた他の特化されたリポジトリもあります。

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty):Q# 構文の LaTeX 形式サポート。

## <a name="next-steps"></a>次のステップ

Quantum Development Kit コミュニティに参加していただき、ありがとうございます。ぜひご協力ください。
コントリビューションの詳細については、次のいずれかのガイドを参照してください。

> [!div class="nextstepaction"]
> [バグを報告する方法](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [ドキュメントの投稿方法](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [プル要求を開く方法](xref:microsoft.quantum.contributing.pulls)
