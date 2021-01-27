---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847177"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases ユーザー定義型

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


振幅増幅での部分的な反射のシーケンスのフェーズ。

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>名前付き項目

### <a name="aboutstart--double"></a>先頭: [Double](xref:microsoft.quantum.lang-ref.double)[]

開始状態に関するリフレクションのフェーズの配列。
### <a name="abouttarget--double"></a>対象: [Double](xref:microsoft.quantum.lang-ref.double)[]

対象の状態に関するリフレクションのフェーズの配列。

## <a name="remarks"></a>解説

両方の配列の長さは同じである必要があります。 多くの場合、開始状態とターゲット状態に関する最後のフェーズに関する最初のフェーズでは、グローバルフェーズシフトが導入され、$0 $ に設定できます。