---
uid: Microsoft.Quantum.Synthesis.Extended
title: 拡張関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855469"
---
# <a name="extended-function"></a>拡張関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


反転係数でスペクトルを拡張します

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>入力

### <a name="spectrum--int"></a>スペクトラム: [Int](xref:microsoft.quantum.lang-ref.int)[]

スペクトル係数



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

係数の後に逆コピーが続く

## <a name="example"></a>例

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```