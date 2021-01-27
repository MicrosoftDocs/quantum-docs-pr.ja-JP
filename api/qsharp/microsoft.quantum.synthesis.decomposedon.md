---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855525"
---
# <a name="decomposedon-function"></a>DecomposedOn 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


分解され変数の順列の並べ替え

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>説明

順列 $ \ pi $ ( `perm` ) とインデックス $i $ () に指定されてい `index` ます。このメソッドは3つの順列 $ ((\ pi_l, \ pi_r), \ pi ') $ を返します。 $ \ pi_l $ と $ \ pi_r $ のイメージでは、要素内の要素のビットを変更しないようにして、$-pi ' $ のイメージは、要素内でビット $i $ を変更しないようにします。

## <a name="input"></a>入力

### <a name="perm--int"></a>perm: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>出力: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>例

入力が perm = [0, 2, 3, 5, 7, 1, 4, 6] および index = 0 であると仮定します。この関数は、次の表に基づいて3つの順列を計算します。これにより、グループ `perm` A の要素とグループ D のイメージ内の要素を含むバイナリ表記の順列が示されます。 列には、ビットインデックスが一覧表示されます。

|  |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

インデックスのすべての値が 0 (= インデックス) と等しくない場合は、A から B、D から C にコピーされます。

|  |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

次に、ブロック B の列0に空のインデックスを持つ最初の要素に0が配置され、次に、プレフィックスが一致する B に1が配置されます (最初のケースでは、インデックスが 0 0 の他の行)。
その後、ブロック C の同じ行に1が追加され、ブロック C の対応するプレフィックスに対して0になります。 すべてのインデックスがブロック B および C の列0に配置されるまで、このプロセスが繰り返されます。

|  |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

次の3つの新しい順列をテーブルから読み取ることができます。

- $ \ pi_l $、内の要素、B (左)
- $ \ pi_r $、D の要素、C (right) のイメージ
- $ \ pi ' $ B 内の要素、C のイメージ (残り)

ただし、$ \ pi_l $ と $ \ pi_r $ では、インデックス1と2には変更されません。また、$ \ pi_ ' $ in index 0 のビット値も変更されません。  また、$ \ pi_l $ と $ \ pi_r $ は自己逆にする必要があることに注意してください。

派生した順列は次のとおりです: left = [0, 1, 2, 3, 4, 5, 6, 7] right = [0, 1, 3, 2, 4, 5, 7, 6] 剰余 = [0, 3, 2, 5, 6, 1, 4, 7]