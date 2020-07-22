---
title: IQ# マジック コマンド
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: rmshaffer
ms.date: 07/21/2020
ms.topic: article
ms.openlocfilehash: 971787adae03af35d2e5b408fb88356a8b7df90a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870704"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="e16b7-102">IQ# マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="e16b7-102">IQ# Magic Commands</span></span>
| <span data-ttu-id="e16b7-103">マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="e16b7-103">Magic Command</span></span> | <span data-ttu-id="e16b7-104">まとめ</span><span class="sxs-lookup"><span data-stu-id="e16b7-104">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="e16b7-105">Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-105">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="e16b7-106">Azure Quantum ワークスペースでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-106">Executes a job in an Azure Quantum workspace.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="e16b7-107">現在の Azure Quantum ワークスペースにジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-107">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="e16b7-108">現在の Azure Quantum ワークスペースにジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-108">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="e16b7-109">現在の Azure Quantum ワークスペースにジョブの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-109">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="e16b7-110">Azure Quantum ワークスペースにジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-110">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="e16b7-111">Azure Quantum ワークスペースでの Q# ジョブ送信のアクティブな実行ターゲットを設定または表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-111">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="e16b7-112">1 つの kata のテストについて参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-112">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="e16b7-113">指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-113">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="e16b7-114">フェルミオン ハミルトニアンを Q# で利用できる形式にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e16b7-114">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="e16b7-115">フェルミオン ハミルトニアン条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-115">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="e16b7-116">電子構造の問題に対して、フェルミオン ハミルトニアンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e16b7-116">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="e16b7-117">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="e16b7-117">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="e16b7-118">Broombridge の電子構造の問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-118">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="e16b7-119">構成オプションの設定またはクエリを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e16b7-119">Allows setting or querying configuration options.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="e16b7-120">指定された関数または操作を ResourcesEstimator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-120">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="e16b7-121">1 つのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-121">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="e16b7-122">現在使用可能なすべてのマジック コマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-122">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="e16b7-123">現在開かれている名前空間とそのエイリアスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-123">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="e16b7-124">NuGet パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-124">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="e16b7-125">このカーネルの現在のパフォーマンス メトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-125">Reports current performance metrics for this kernel.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="e16b7-126">指定された関数または操作を QuantumSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-126">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="e16b7-127">指定された関数または操作を ToffoliSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-127">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="e16b7-128">現在のセッションで使用できる Q# 操作を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-128">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="e16b7-129">現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e16b7-129">Provides actions related to the current workspace.</span></span> |
