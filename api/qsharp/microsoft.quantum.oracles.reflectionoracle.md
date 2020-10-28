---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724212"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パック [](https://nuget.org/packages/)


リフレクション oracle を表します。

リフレクション oracle ($O $) には、次の入力があります。

- 反映されたサブ空間の回転に使用するフェーズ $/phi $。
- 指定されたリフレクションを実行する qubit レジスタ。

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>名前付き項目

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞と Ctl



## <a name="remarks"></a>解説

この oracle $O = \ bold 完了-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ は、単一の純粋な状態 $ \ket{\psi} $ について、フェーズ $ \ phi $ によって部分的なリフレクションを実行します。