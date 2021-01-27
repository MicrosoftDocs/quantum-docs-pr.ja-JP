---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855372"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask ユーザー定義型

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


複数制御されたマルチターゲット Toffoli ゲートを表す型。

最初の整数は、制御線のビットマスクです。  設定されるビットインデックスは、制御行インデックスに対応します。

2番目の整数は、ターゲット行のビットマスクです。  設定されているビットインデックスは、ターゲットの行インデックスに対応します。

両方の整数のビットインデックスは、不整合である必要があります。

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="controlmask--int"></a>ControlMask: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [Int](xref:microsoft.quantum.lang-ref.int)

