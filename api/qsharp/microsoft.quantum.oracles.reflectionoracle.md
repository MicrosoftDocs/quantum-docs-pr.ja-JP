---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854482"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle ユーザー定義型

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


リフレクション oracle を表します。

リフレクション oracle ($O $) には、次の入力があります。

- 反映されたサブ空間の回転に使用するフェーズ $/phi $。
- 指定されたリフレクションを実行する qubit レジスタ。

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>名前付き項目

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です



## <a name="remarks"></a>解説

この oracle $O = \ bold 完了-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ は、単一の純粋な状態 $ \ket{\psi} $ について、フェーズ $ \ phi $ によって部分的なリフレクションを実行します。