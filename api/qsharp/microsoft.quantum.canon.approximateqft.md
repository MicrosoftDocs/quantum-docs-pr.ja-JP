---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850319"
---
# <a name="approximateqft-operation"></a>ApproximateQFT 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


クォンタムレジスタにおおよそのクォンタムフーリエ変換 (アク FT) を適用します。

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

QFT 回線で発生する制御された Z 回転を排除するレベルを決定する近似パラメーター。

近似パラメーター a は、Z 回転の排除レベルを決定します。つまり、∈ {0.. n} と Z 回転 2π/2k (k>a が QFT 回線から削除される) です。 K >= log ₂ (n) + log ₂ (1/ε) + 3 をバインドできることがわかっています。QFT-アク FT | |Εを<します。


### <a name="qs--bigendian"></a>qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

おおよそのクォンタムフーリエ変換が適用される n qubits のクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

アク FT には、2π/2k と Hadamard ゲートの形式の Z 回転ゲートが必要です。

入力と出力は、ビッグエンディアンエンコーディングでエンコードされると想定されます。

## <a name="references"></a>References

- [*M.、Beth*、Appl.exe、Commun のようになります。コンピューター.19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arxiv: quant-ph/0201067v1](https://arxiv.org/abs/quant-ph/0201067)