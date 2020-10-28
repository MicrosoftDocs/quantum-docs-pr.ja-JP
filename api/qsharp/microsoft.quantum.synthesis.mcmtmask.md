---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725500"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask ユーザー定義型

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


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

