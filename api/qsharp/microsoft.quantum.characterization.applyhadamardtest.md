---
uid: Microsoft.Quantum.Characterization.ApplyHadamardTest
title: ApplyHadamardTest 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ApplyHadamardTest
qsharp.summary: ''
ms.openlocfilehash: c36a54bf907d41c9eaa1ece01b1bd446f6b8aaa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851943"
---
# <a name="applyhadamardtest-operation"></a>ApplyHadamardTest 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyHadamardTest (phaseShift : Bool, commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), control : Qubit, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="phaseshift--bool"></a>phaseShift: [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞




### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl




### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl




### <a name="control--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

