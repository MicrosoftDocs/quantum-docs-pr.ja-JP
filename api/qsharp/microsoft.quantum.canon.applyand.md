---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718459"
---
# <a name="applyand-operation"></a>ApplyAnd 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


測定を使用して adjoint 演算を実行し、両方のコントロール qubit が1の状態である場合にのみ、指定されたターゲット qubit を反転します。

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>説明

`target`両方のコントロールが1で、 `target` が状態が0であると想定している場合にのみ、を反転させます。  この操作には、T カウント4、T 深度2があり、ヘルパー qubit は必要ないため、が0であることがわかっている場合は、CCNOT 操作に適している可能性があり `target` ます。  この操作の adjoint は測定ベースであり、T ゲートは必要ありません。

この操作の制御されたアプリケーションでは、ヘルパー qubit、ゲートは不要であり、 `2^c` `Rz` 深さに対して最適化されていません `c` 。は、操作の2つのコントロールを含むコントロールの全体の数です `ApplyAnd` 。  Adjoint の制御されたアプリケーションでは `2^c - 1` `Rz` 、ゲート (非 adjoint 操作のサイズの2倍の角度)、ヘルパー qubit、および深度に対して最適化されていないゲートが必要です。

## <a name="input"></a>入力

### <a name="control1--qubit"></a>control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初のコントロールの qubit


### <a name="control2--qubit"></a>control2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

2番目のコントロール qubit


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ターゲット補助 qubit;状態は0である必要があります



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

- Cody Jones: 「fault トレラントな Toffoli ゲートのための斬新構造」、「Phys 87、022328、2013 [Arxiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA
- Gidney: "半分に of クォンタムの追加", Quantum 2, ページ 74, 2018 [Arxiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "Quantum Oracle 回線とクリスマスツリーパターン"、 [2019 年12月19日のブログ記事](https://msoeken.github.io/blog_qac.html) (注: 複数の制御された構築について説明します)