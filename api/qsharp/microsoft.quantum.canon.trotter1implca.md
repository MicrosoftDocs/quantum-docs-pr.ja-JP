---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840099"
---
# <a name="trotter1implca-operation"></a>Trotter1ImplCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


最初の順序の Trotter – Suzuki インテグレーターの実装。

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

時間ステップに分解される操作の数。


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

シミュレーションの各ステップのサイズに対する乗数。


### <a name="target--t"></a>ターゲット: \

操作が動作するクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。

## <a name="example"></a>例

同等のものを次に示します。

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

and

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```