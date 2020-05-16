---
title: IQ# マジック コマンド
description: 'Q # Jupyter Notebook を使用した IQ # マジックコマンドのクイックリファレンスページ'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431021"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="b5624-103">IQ# マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="b5624-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="b5624-104">全般</span><span class="sxs-lookup"><span data-stu-id="b5624-104">General</span></span>

- <span data-ttu-id="b5624-105">`%config`: 構成設定を設定または取得します。</span><span class="sxs-lookup"><span data-stu-id="b5624-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="b5624-106">`%estimate`: QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5624-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="b5624-107">`%lsmagic`: 現在使用可能なすべてのマジックコマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b5624-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="b5624-108">`%package`: Nuget パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5624-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="b5624-109">`%performance`: このカーネルの現在のパフォーマンスメトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="b5624-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="b5624-110">`%simulate`: QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5624-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="b5624-111">`%toffoli`: ToffoliSimulator シミュレーターターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5624-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="b5624-112">`%who`: 現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5624-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="b5624-113">`%workspace`: 現在のセッションで定義されているすべての操作と関数の一覧を、対話的に、または現在のワークスペースから読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="b5624-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="b5624-114">科学</span><span class="sxs-lookup"><span data-stu-id="b5624-114">Chemistry</span></span>

- <span data-ttu-id="b5624-115">`%chemistry.broombridge`: 指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="b5624-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="b5624-116">`%chemistry.encode`: Hamiltonian on にあるは、Q # で利用できる形式にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="b5624-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="b5624-117">`%chemistry.fh.add_terms`: Hamiltonian 上の対象に用語を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5624-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="b5624-118">`%chemistry.fh.load`: 電子構造の問題のために、Hamiltonian 上にあるので、このデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b5624-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="b5624-119">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="b5624-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="b5624-120">`%chemistry.inputstate.load`: Broombridge の電子構造問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="b5624-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="b5624-121">Katas パッケージから</span><span class="sxs-lookup"><span data-stu-id="b5624-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="b5624-122">`%kata`: 1 つのテストを実行し、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="b5624-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="b5624-123">`%check_kata`: 1 つの kata のテストの参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5624-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="b5624-124">具体的には、1つのタスクの参照実装をセルに置き換え、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="b5624-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
