---
title: IQ# マジック コマンド
description: 'Q # Jupyter Notebook を使用した IQ # マジックコマンドのクイックリファレンスページ'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870543"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="23fd1-103">IQ# マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="23fd1-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="23fd1-104">全般</span><span class="sxs-lookup"><span data-stu-id="23fd1-104">General</span></span>

- <span data-ttu-id="23fd1-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): 構成オプションを設定または照会できます。</span><span class="sxs-lookup"><span data-stu-id="23fd1-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="23fd1-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="23fd1-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): 現在使用可能なすべてのマジックコマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="23fd1-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): NuGet パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="23fd1-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): このカーネルの現在のパフォーマンスメトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="23fd1-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): QuantumSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="23fd1-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): ToffoliSimulator ターゲットコンピューターで指定された関数または操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="23fd1-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): 現在のセッションで使用できる Q # 操作を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="23fd1-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): 現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="23fd1-114">Azure クォンタムの統合</span><span class="sxs-lookup"><span data-stu-id="23fd1-114">Azure Quantum integration</span></span>

- <span data-ttu-id="23fd1-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="23fd1-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Azure Quantum ワークスペースでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Executes a job in an Azure Quantum workspace.</span></span>
- <span data-ttu-id="23fd1-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): 現在の Azure クォンタムワークスペースのジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="23fd1-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): 現在の Azure クォンタムワークスペースにジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="23fd1-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): 現在の Azure クォンタムワークスペースのジョブの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="23fd1-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Azure Quantum ワークスペースにジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="23fd1-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Azure Quantum ワークスペースでの Q # ジョブの送信のアクティブな実行ターゲットを設定または表示します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="23fd1-122">化学 (Microsoft の Quantum パッケージから)</span><span class="sxs-lookup"><span data-stu-id="23fd1-122">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="23fd1-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): 指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="23fd1-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Hamiltonian on にあるは、Q # で利用できる形式にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="23fd1-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="23fd1-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Hamiltonian 上の対象に用語を追加します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="23fd1-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): 電子構造の問題のために、Hamiltonian 上にあるので、このデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="23fd1-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="23fd1-127">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="23fd1-127">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="23fd1-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Broombridge の電子構造問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="23fd1-129">Katas (Katas パッケージから)</span><span class="sxs-lookup"><span data-stu-id="23fd1-129">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="23fd1-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): 1 つのテストを実行し、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="23fd1-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): 1 つの kata のテストの参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="23fd1-132">具体的には、1つのタスクの参照実装をセルに置き換え、テストが成功したかどうかを報告します。</span><span class="sxs-lookup"><span data-stu-id="23fd1-132">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
