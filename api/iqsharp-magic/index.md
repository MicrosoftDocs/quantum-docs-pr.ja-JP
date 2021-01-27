---
title: IQ# マジック コマンド
description: IQ# Jupyter カーネルで使用できるマジック コマンドをリストします。
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: ryansha
ms.date: 01/24/2021
ms.topic: article
ms.openlocfilehash: 00b0e0b806c0034d222d286bac5388bd14326a60
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844097"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="06903-103">IQ# マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="06903-103">IQ# Magic Commands</span></span>
| <span data-ttu-id="06903-104">マジック コマンド</span><span class="sxs-lookup"><span data-stu-id="06903-104">Magic Command</span></span> | <span data-ttu-id="06903-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="06903-105">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="06903-106">Azure Quantum ワークスペースに接続するか、現在の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-106">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="06903-107">Azure Quantum ワークスペースにジョブを送信し、完了するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="06903-107">Submits a job to an Azure Quantum workspace and waits for completion.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="06903-108">現在の Azure Quantum ワークスペースにジョブの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-108">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="06903-109">現在の Azure Quantum ワークスペースにジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-109">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="06903-110">現在の Azure Quantum ワークスペースにジョブの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-110">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="06903-111">Azure Quantum ワークスペースにジョブを送信します。</span><span class="sxs-lookup"><span data-stu-id="06903-111">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="06903-112">Azure Quantum ワークスペースでの Q# ジョブ送信のアクティブな実行ターゲットを設定または表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-112">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="06903-113">1 つの kata のテストについて参照の実装を確認します。</span><span class="sxs-lookup"><span data-stu-id="06903-113">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="06903-114">指定された yaml ファイルから Broombridge の電子構造の問題表現を読み込んで返します。</span><span class="sxs-lookup"><span data-stu-id="06903-114">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="06903-115">フェルミオン ハミルトニアンを Q# で利用できる形式にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="06903-115">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="06903-116">フェルミオン ハミルトニアン条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="06903-116">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="06903-117">電子構造の問題に対して、フェルミオン ハミルトニアンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="06903-117">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="06903-118">問題はファイルから読み込まれるか、引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="06903-118">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="06903-119">Broombridge の電子構造の問題を読み込み、選択した入力状態を返します。</span><span class="sxs-lookup"><span data-stu-id="06903-119">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="06903-120">構成オプションの設定またはクエリを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="06903-120">Allows setting or querying configuration options.</span></span> |
| [`%debug`](xref:microsoft.quantum.iqsharp.magic-ref.debug) | <span data-ttu-id="06903-121">指定された Q# 操作または関数の実行をステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="06903-121">Steps through the execution of a given Q# operation or function.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="06903-122">指定された関数または操作を ResourcesEstimator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="06903-122">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="06903-123">1 つのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="06903-123">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="06903-124">現在使用可能なすべてのマジック コマンドの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="06903-124">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="06903-125">現在開かれている名前空間とそのエイリアスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-125">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="06903-126">NuGet パッケージを読み込む機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="06903-126">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="06903-127">このカーネルの現在のパフォーマンス メトリックを報告します。</span><span class="sxs-lookup"><span data-stu-id="06903-127">Reports current performance metrics for this kernel.</span></span> |
| [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project) | <span data-ttu-id="06903-128">Q# プロジェクト参照を表示または追加する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="06903-128">Provides the ability to view or add Q# project references.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="06903-129">指定された関数または操作を QuantumSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="06903-129">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="06903-130">指定された関数または操作を ToffoliSimulator ターゲット マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="06903-130">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%trace`](xref:microsoft.quantum.iqsharp.magic-ref.trace) | <span data-ttu-id="06903-131">指定された操作の実行パスを視覚化します。</span><span class="sxs-lookup"><span data-stu-id="06903-131">Visualizes the execution path of the given operation.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="06903-132">現在のセッションで使用できる Q# 操作を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="06903-132">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="06903-133">現在のワークスペースに関連するアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="06903-133">Provides actions related to the current workspace.</span></span> |
