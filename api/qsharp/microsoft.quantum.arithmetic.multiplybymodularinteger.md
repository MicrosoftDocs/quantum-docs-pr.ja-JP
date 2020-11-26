---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222577"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit レジスタで整数定数を使ってモジュール乗算を実行します。

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

$ `modulus` と $a $ を $N し `constMultiplier` てください。
次に、この操作では、計算基準に基づいて、次のマップによって定義される、"$ $ \begin{align} \ket{y} \ket{(a-cdot y)" $1 $N & \end{align}} N} $ $ $0 $y を実装します。

## <a name="input"></a>入力

### <a name="constmultiplier--int"></a>[型の型: Int](xref:microsoft.quantum.lang-ref.int)

乗数を乗算する定数。 係数は連にする必要があります。


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

乗算演算が実行され `modulus` ます。


### <a name="multiplier--littleendian"></a>乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

定数を乗算した数値。
これは、リトルエンディアン形式で整数をエンコードする qubits の配列です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

- 回路図と説明については、arXiv のページ8の図7を参照してください [: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- この操作は Arxiv の U ₐに対応し [ます: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)