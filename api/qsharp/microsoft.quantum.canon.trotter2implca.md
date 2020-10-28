---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715309"
---
# <a name="trotter2implca-operation"></a>Trotter2ImplCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


2番目の順序の Trotter – Suzuki インテグレーターの実装。

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>入力

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

時間ステップに分解される操作の数。


### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

シミュレーションの各ステップのサイズに対する乗数。


### <a name="target--t"></a>ターゲット: \

操作が動作するクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。