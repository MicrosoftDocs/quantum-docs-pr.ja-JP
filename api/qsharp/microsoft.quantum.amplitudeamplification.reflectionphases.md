---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721818"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases ユーザー定義型

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


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