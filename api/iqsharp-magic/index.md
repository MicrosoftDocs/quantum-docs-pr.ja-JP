---
title: IQ# マジック コマンド
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: rmshaffer
ms.date: 08/25/2020
ms.topic: article
ms.openlocfilehash: d6bf8407e40be092689b38cf90514c88f798cc2f
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88862960"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="8a369-102">IQ# マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="8a369-102">IQ# Magic Commands</span></span>
| <span data-ttu-id="8a369-103">マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="8a369-103">Magic Command</span></span> | <span data-ttu-id="8a369-104">まとめ</span><span class="sxs-lookup"><span data-stu-id="8a369-104">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="8a369-105">Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-105">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="8a369-106">Azure Quantum ワークスペースでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a369-106">Executes a job in an Azure Quantum workspace.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="8a369-107">現在の Azure Quantum ワークスペースにジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-107">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="8a369-108">現在の Azure Quantum ワークスペースにジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-108">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="8a369-109">現在の Azure Quantum ワークスペースにジョブの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-109">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="8a369-110">Azure Quantum ワークスペースにジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="8a369-110">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="8a369-111">Azure Quantum ワークスペースでの Q# ジョブ送信のアクティブな実行ターゲットを設定または表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-111">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="8a369-112">1 つの kata のテストについて参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="8a369-112">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="8a369-113">指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="8a369-113">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="8a369-114">フェルミオン ハミルトニアンを Q# で利用できる形式にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8a369-114">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="8a369-115">フェルミオン ハミルトニアン条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a369-115">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="8a369-116">電子構造の問題に対して、フェルミオン ハミルトニアンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8a369-116">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="8a369-117">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="8a369-117">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="8a369-118">Broombridge の電子構造の問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="8a369-118">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="8a369-119">構成オプションの設定またはクエリを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a369-119">Allows setting or querying configuration options.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="8a369-120">指定された関数または操作を ResourcesEstimator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="8a369-120">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="8a369-121">1 つのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a369-121">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="8a369-122">現在使用可能なすべてのマジック コマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="8a369-122">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="8a369-123">現在開かれている名前空間とそのエイリアスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-123">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="8a369-124">NuGet パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a369-124">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="8a369-125">このカーネルの現在のパフォーマンス メトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="8a369-125">Reports current performance metrics for this kernel.</span></span> |
| [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project) | <span data-ttu-id="8a369-126">Q# プロジェクト参照を表示または追加する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a369-126">Provides the ability to view or add Q# project references.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="8a369-127">指定された関数または操作を QuantumSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="8a369-127">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="8a369-128">指定された関数または操作を ToffoliSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="8a369-128">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%trace`](xref:microsoft.quantum.iqsharp.magic-ref.trace) | <span data-ttu-id="8a369-129">指定された操作の実行パスを視覚化します。</span><span class="sxs-lookup"><span data-stu-id="8a369-129">Visualizes the execution path of the given operation.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="8a369-130">現在のセッションで使用できる Q# 操作を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8a369-130">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="8a369-131">現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a369-131">Provides actions related to the current workspace.</span></span> |
