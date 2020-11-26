---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205968"
---
# <a name="noop-operation"></a>NoOp 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


引数に対して identity 操作 (no op) を実行します。

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、任意の型の値を取得し、それに対して何も実行しません。
これは、操作の種類の入力が必要な場合には常に役立ちますが、アクションを実行する必要はありません。
たとえば、特定のエラー修正より隣人によってエラーが発生していないことが示された場合は、 `NoOp<Qubit[]>` 適切な回復手順である可能性があります。
同様に、操作で状態の準備手順を入力と想定している場合は、を使用して、 `NoOp<Qubit[]>` 状態 $ \ket{0 \ cドット 0} $ を準備できます。

## <a name="input"></a>入力

### <a name="input--t"></a>入力: ' t

無視する値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

ほとんどの場合、の型パラメーターは `NoOp` 明示的に指定する必要があります。 たとえば、 `NoOp<Qubit>` はと同じです <xref:microsoft.quantum.intrinsic.i> 。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. I](xref:Microsoft.Quantum.Intrinsic.I)