---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216576"
---
# <a name="cy-operation"></a>CY 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


コントロール-Y (CY) ゲートを qubits のペアに適用します。

$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -i 0 & 0 \\ \\ & i & 0 \end{align}、$ $。ここでは、行と列がクォンタムの概念ガイドに従って編成されています。

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="control--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

CY ゲートの制御 qubit。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

CY ゲートのターゲット qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

次と同じです。

```qsharp
Controlled Y([control], target);
```