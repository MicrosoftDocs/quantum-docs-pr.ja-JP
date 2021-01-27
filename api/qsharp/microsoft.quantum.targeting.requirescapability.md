---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855151"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability ユーザー定義型

名前空間: [Microsoft. Quantum. ターゲット](xref:Microsoft.Quantum.Targeting)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


コンパイラが必要とするランタイム機能で呼び出し可能をマークするために使用される、コンパイラが認識する属性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>名前付き項目

### <a name="level--string"></a>Level: [文字列](xref:microsoft.quantum.lang-ref.string)

呼び出し可能で必要なランタイム機能レベルの名前。
### <a name="reason--string"></a>理由: [文字列](xref:microsoft.quantum.lang-ref.string)

呼び出し可能にこのランタイム機能が必要な理由についての説明。

## <a name="remarks"></a>解説

この属性は、呼び出し可能なにこの属性のインスタンスが既に存在していない限り、コンパイラによって生成可能な呼び出しに自動的に追加されます。 使用しないでください。ただし、コンパイラが必要な機能を正しく推論できない場合があります。

機能レベル名の一覧を次に示します。機能が強化されるか、制限が減少します。

## `"BasicQuantumFunctionality"`

測定結果を等しいかどうかを比較することはできません。

## `"BasicMeasurementFeedback"`

演算では、if ステートメントの条件式でのみ等しいかどうかを比較できます。 結果に依存する if ステートメントのブロックには、ブロックの外側で宣言された変更可能な変数の set ステートメント、または return ステートメントを含めることはできません。

## `"FullComputation"`

実行時の制限はありません。 任意の Q # プログラムを実行できます。