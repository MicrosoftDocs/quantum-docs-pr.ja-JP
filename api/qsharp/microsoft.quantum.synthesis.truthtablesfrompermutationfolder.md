---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724455"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


単一の変数インデックスの分解ロジック

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>説明

これは、現在の状態を取得して、更新された順列を生成し、場合によっては制御ゲート用の新しい関数を追加します。

## <a name="input"></a>入力

### <a name="numvars--int"></a>numVars: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>状態: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>出力: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

