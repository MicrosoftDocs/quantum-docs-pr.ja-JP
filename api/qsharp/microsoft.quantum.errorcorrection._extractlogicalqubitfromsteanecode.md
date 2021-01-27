---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853209"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


より隣人の測定値と埋め込みの逆関数。

$X $-と $Z $-stabilizers は、エンコーディング回線の特定の選択によって処理されません。
この asymmetry は、別のより隣人抽出ルーチンにつながります。
より隣人を測定する方法としては、コードの状態を直接測定する方法がありますが、取り組みの目的では、論理 qubit が1つの qubit に返されます。これは、より隣人の測定値をさらに ancillas なしで実行できることです。

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>入力

### <a name="code--logicalregister"></a>コード: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

$X $-より隣人と $Z $-より隣人の論理 qubit と整数のペア。
これは、1つの $X $-または $Z $ error が測定されたより隣人の原因となったコード qubit のインデックスを表します。

## <a name="remarks"></a>解説

`internal`単体テストがこの操作に直接依存しているため、この操作はとマークされていないことに注意してください。 今後の改善のために、単体テストはパブリック呼び出し可能なものにのみ依存するようにリファクタリングする必要があります。

> [!WARNING]
> このルーチンは、Steane の 7 qubit コードの特定のエンコーディング回線に合わせて調整されています。エンコーディング回線を変更する場合は、より隣人の結果を異なる方法で解釈することが必要になる場合があります。