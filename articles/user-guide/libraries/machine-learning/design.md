---
title: QDK を使用して独自の分類器を設計する
description: 量子回線中心の分類器のサーキットモデルを設計するための基本的な概念について説明します。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 60e694e9f7c2f01a6679ef960f5a7774c8bd6a62
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868944"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="7d85c-103">独自の分類器を設計する</span><span class="sxs-lookup"><span data-stu-id="7d85c-103">Design your own classifier</span></span>

<span data-ttu-id="7d85c-104">このガイドでは、量子回線中心の分類器のサーキットモデルの設計の背後にある基本的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="7d85c-105">従来のディープラーニングと同様に、特定のアーキテクチャを選択するための一般的な規則はありません。</span><span class="sxs-lookup"><span data-stu-id="7d85c-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="7d85c-106">問題によっては、アーキテクチャによっては、他よりもパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="7d85c-107">ただし、回線を設計する際に役立ついくつかの概念があります。</span><span class="sxs-lookup"><span data-stu-id="7d85c-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="7d85c-108">多数のパラメーターは、より柔軟なモデルを意味します。これは、複雑な分類境界の描画に適している場合もありますが、オーバーフィットの影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d85c-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="7d85c-109">Qubits 間の Entangling ゲートは、クォンタムの特徴間の相関関係を把握するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="7d85c-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="7d85c-110">Q で分類子を作成する方法\#</span><span class="sxs-lookup"><span data-stu-id="7d85c-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="7d85c-111">分類器を作成するには、サーキットモデルでパラメーター化制御循環を連結します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="7d85c-112">これを行うには、 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) クォンタム Machine Learning ライブラリで定義されている型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="7d85c-113">この型は、ターゲットの qubit のインデックス、制御 qubit のインデックスの配列、回転の軸、およびモデルを定義するパラメーターの配列内の関連付けられたパラメーターのインデックスを決定する4つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7d85c-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="7d85c-114">分類器の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="7d85c-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="7d85c-115">[ハーフ衛星サンプル](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)では、ファイルで定義されている次の分類子を見つけることができ `Training.qs` ます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="7d85c-116">ここで定義しているのは、要素の配列を返す関数であり `ControlledRotation` 、パラメーターの配列と共に、バイアスによってが定義され [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) ます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="7d85c-117">この型は、クォンタム Machine Learning ライブラリでは基本的なものであり、分類子を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="7d85c-118">上の関数で定義されている回線は、データセットの各サンプルに2つの特徴が含まれている分類子の一部です。</span><span class="sxs-lookup"><span data-stu-id="7d85c-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="7d85c-119">そのため、必要なのは2つの qubits だけです。</span><span class="sxs-lookup"><span data-stu-id="7d85c-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="7d85c-120">回路のグラフィカルな表現は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d85c-120">The graphical representation of the circuit is:</span></span>

 ![回路モデルの例](~/media/circuit_model_1.PNG)

<span data-ttu-id="7d85c-122">既定では、クォンタム Machine Learning ライブラリの操作によって、レジスタの最後の qubit が測定され、分類確率が算出されます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-122">Note that by default the operations of the Quantum Machine Learning library measure the last qubit of the register to estimate the classification probabilities.</span></span> <span data-ttu-id="7d85c-123">回線を設計するときは、この事実に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d85c-123">You should keep in mind this fact when designing your circuit.</span></span>

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="7d85c-124">ライブラリ関数を使用してゲートのレイヤーを作成する</span><span class="sxs-lookup"><span data-stu-id="7d85c-124">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="7d85c-125">たとえば、MNIST データセットのような28×28ピクセルの画像など、インスタンスごとに784の機能を持つデータセットがあるとします。</span><span class="sxs-lookup"><span data-stu-id="7d85c-125">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="7d85c-126">この場合、回線の幅が十分に大きくなり、個々のゲートが個別に作成される可能性がありますが、現実的ではないタスクになります。</span><span class="sxs-lookup"><span data-stu-id="7d85c-126">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="7d85c-127">このため、Quantum Machine Learning ライブラリには、パラメーター化回転のレイヤーを自動的に生成するための一連のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d85c-127">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="7d85c-128">たとえば、関数は、 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 指定された軸に沿って制御されないシングル qubit 回転の配列を返します。レジスタ内の qubit ごとに1つの回転があり、それぞれが異なるモデルパラメーターによってパラメーター化されます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-128">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="7d85c-129">たとえば、は `LocalRotationsLayer(4, X)` 次のゲートのセットを返します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-129">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![ローカルローテーションレイヤー](~/media/local_rotations_layer.PNG)

<span data-ttu-id="7d85c-131">サーキットの設計を効率化するために使用できるすべてのツールを検出するには、 [Quantum Machine Learning ライブラリの API リファレンスを参照](xref:microsoft.quantum.machinelearning)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d85c-131">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d85c-132">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7d85c-132">Next steps</span></span>

 <span data-ttu-id="7d85c-133">サンプルに用意されている例では、さまざまな構造体を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7d85c-133">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="7d85c-134">モデルのパフォーマンスに変更があるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7d85c-134">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="7d85c-135">次のチュートリアル「」で [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) は、データセットを読み込んで、分類子の新しいアーキテクチャを試してみる方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="7d85c-135">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
