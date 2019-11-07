---
title: 量子乱数ジェネレーターの作成
description: 量子乱数ジェネレーターを作成することで、重ね合わせなど、基本的量子概念を実証する Q# プロジェクトを構築します。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462843"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>クイック スタート:Q# で量子乱数ジェネレーターを実装する
Q# で記述された量子アルゴリズムの単純な例が量子乱数ジェネレーターです。 このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。 

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。
- [Q# プロジェクトを作成する](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Q# 操作を記述する

### <a name="q-operation-code"></a>Q# 操作コード

1. Operation.qs ファイルの内容を次のコードに置き換えます。

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

「[量子コンピューティングとは](xref:microsoft.quantum.overview.what)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。 測定されるとき、キュービットは 0 か 1 だけになります。 ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。 この確率論的な状態が重ね合わせと呼ばれています。 この確率を使用し、乱数を生成できます。

今回の Q# 操作では、Q# ネイティブの `Qubit` データ型を導入します。 `Qubit` は `using` ステートメントでのみ割り当てることができます。 割り当て後、キュービットは常に `Zero` 状態になります。 

`H` 操作を使用することで、`Qubit` を重ね合わせに入れることができます。 キュービットを測定し、その値を読み取るには、`M` 組み込み操作を使用します。

重ね合わせに `Qubit` を入れ、測定することで、コードを呼び出すたびに結果は異なる値になります。 

`Qubit` の割り当てが解除されるとき、`Zero` 状態に明示的に戻す必要があります。戻さない場合、シミュレーターからランタイム エラーが報告されます。 これを実現する簡単な方法は `Reset` を呼び出すことです。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>ブロッホ球でコードを視覚化する

ブロッホ球では、北極は古典的理論値 **0** を表わし、南極は古典的理論値 **1** を表わします。 重ね合わせは球上の点で表わすことができます (矢印で表わされています)。 矢印の端が極に近づけば近づくほど、測定時、その極に割り当てられる古典的理論値にキュービットがなる確率が高くなります。 たとえば、下の赤い矢印で表わされているキュービットの状態では、測定したとき、値 **0** が与えられる可能性が高くなります。

<img src="./Bloch.svg" width="175">

この表現を利用し、コードの動作を視覚化できます。

* まず、状態 **0** で初期化されたキュービットから始め、`H` を適用し、**0** と **1** の確率が同じになる重ね合わせを作成します。

<img src="./H.svg" width="450">

* 次に、キュービットを測定し、出力を保存します。

<img src="./Measurement2.svg" width="450">

測定の結果は完全にランダムになるため、ランダム ビットが 1 つ取得されました。 この操作を複数回呼び出し、整数を作成できます。 たとえば、操作を 3 回呼び出してランダム ビットを 3 つ取得する場合、ランダムの 3 ビット数 (つまり、0 から 7 までの乱数) を構築できます。
