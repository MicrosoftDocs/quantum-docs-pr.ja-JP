---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829228"
---
# <a name="dumpregister-function"></a><span data-ttu-id="f7b78-102">DumpRegister 関数</span><span class="sxs-lookup"><span data-stu-id="f7b78-102">DumpRegister function</span></span>

<span data-ttu-id="f7b78-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f7b78-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f7b78-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="f7b78-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f7b78-105">指定した qubits に関連付けられている現在のターゲットコンピューターの状態をダンプします。</span><span class="sxs-lookup"><span data-stu-id="f7b78-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f7b78-106">入力</span><span class="sxs-lookup"><span data-stu-id="f7b78-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="f7b78-107">場所: \</span><span class="sxs-lookup"><span data-stu-id="f7b78-107">location : 'T</span></span>

<span data-ttu-id="f7b78-108">状態のダンプを生成する場所に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7b78-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f7b78-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f7b78-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f7b78-110">報告する qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="f7b78-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7b78-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7b78-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="f7b78-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="f7b78-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7b78-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7b78-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7b78-114">&</span><span class="sxs-lookup"><span data-stu-id="f7b78-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f7b78-115">解説</span><span class="sxs-lookup"><span data-stu-id="f7b78-115">Remarks</span></span>

<span data-ttu-id="f7b78-116">このメソッドを使用すると、指定した qubits の状態に関連付けられた情報をファイルまたはその他の場所にダンプできます。</span><span class="sxs-lookup"><span data-stu-id="f7b78-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="f7b78-117">生成される実際の情報とのセマンティクス `location` は、各ターゲットコンピューターに固有です。</span><span class="sxs-lookup"><span data-stu-id="f7b78-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="f7b78-118">ただし、空のタプルを位置 () として指定 `()` することは、通常、出力をコンソールに生成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f7b78-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="f7b78-119">Quantum 開発キットの一部として配布されるローカルの完全な状態シミュレーターでは、このメソッドは、指定された qubits の状態 (つまり、対応するサブシステムの wave 関数) を1次元の複素数の配列として書き込むファイルのパスを持つ文字列を受け取ります。各要素は、対応する状態を測定する確率の振幅を表します</span><span class="sxs-lookup"><span data-stu-id="f7b78-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="f7b78-120">指定した qubits が他の qubits と区別され、その状態を分離できない場合は、qubits がありであることを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="f7b78-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>