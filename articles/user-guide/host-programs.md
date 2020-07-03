---
title: Q# プログラムを実行する方法
description: 'Q # プログラムを実行するさまざまな方法の概要を説明します。 Python または .NET 言語のコマンドライン、Q # Jupyter Notebook、およびクラシックホストプログラム。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887740"
---
# <a name="ways-to-run-a-q-program"></a>Q# プログラムを実行する方法

Quantum Development Kit の最大の強みの1つは、プラットフォームと開発環境全体での柔軟性です。
ただし、これは、新しい Q # ユーザーが、[インストールガイド](xref:microsoft.quantum.install)に記載されている多くのオプションによって混乱を見たり、圧倒したりする可能性があることも意味します。
このページでは、Q # プログラムが実行されたときの動作について説明し、ユーザーが実行できるさまざまな方法を比較します。

主な違いは、Q # を実行できることです。
- スタンドアロンアプリケーションとして、Q # が関連する唯一の言語であり、プログラムが直接呼び出されます。 このカテゴリには、次の2つの方法があります。
  - コマンドラインインターフェイス
  - Q# Jupyter Notebook
- Python または .NET 言語 (C# や F # など) で記述された追加の*ホストプログラム*を使用して、プログラムを呼び出し、返された結果をさらに処理することができます。

これらのプロセスとその違いについてよく理解するために、簡単な Q # プログラムを考え、実行する方法を比較します。

## <a name="basic-q-program"></a>基本的な Q # プログラム

基本的な量子プログラムは、法則の状態が $ \ket $ および $ \ket $ の qubit を準備し、それを測定し、結果を返すことで構成される場合があり {0} {1} ます。これは、これら2つの状態のうち、確率が等しい場合に、ランダムに発生します。
実際には、このプロセスは、クォンタムの[乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng)のクイックスタートの中核になっています。

Q # では、これは次のコードで実行されます。

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

ただし、このコードだけを Q # で実行することはできません。
そのためには、操作の本体を構成する必要があります。この[操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)は、直接または別の操作によって---呼び出されたときに実行されます。 そのため、次の形式の操作を記述できます。
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
`MeasureSuperposition`入力を受け取らず、 [Result](xref:microsoft.quantum.guide.types)型の値を返す操作を定義しました。

このページの例は Q #*操作*のみで構成されていますが、ここで説明するすべての概念は、q #*関数*にも同様に関係しているので、*呼び出し*が許容できるものとしてまとめられています。 これらの違いについては、 [「Q # の基本: 操作と関数](xref:microsoft.quantum.guide.basics#q-operations-and-functions)」で説明されています。これらを定義する方法の詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。

### <a name="callable-defined-in-a-q-file"></a>Q # ファイルで定義された呼び出し可能

呼び出し可能なのは、Q # で呼び出されて実行されるものです。
ただし、完全な Q # ファイルを構成するには、さらにいくつかの追加機能が必要です `*.qs` 。

すべての Q # の型と呼び出し可能な (定義したものと言語に固有のものの両方) は、*名前空間*内で定義されています。これらの型は、参照可能な完全な名前を提供します。

たとえば、およびの [`H`](xref:microsoft.quantum.intrinsic.h) 各 [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 操作は、 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) 名前空間と名前空間 ( [Q # 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)の一部) にあります。
そのため、常に*完全な*名前を使用してを呼び出すことができます `Microsoft.Quantum.Intrinsic.H(<qubit>)` が、 `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 常にこの操作を実行すると、コードが乱雑になることがあります。

ステートメントを `open` 使用すると、上記の操作本体で行ったように、より簡潔な短縮形で呼び出し可能なを参照できます。
このため、操作を含む完全な Q # ファイルは、独自の名前空間を定義し、操作が使用する呼び出しの名前空間を開いて、次の操作を実行します。

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> 名前空間は、開いたときに*別名*を付けることもできます。これは、2つの名前空間の呼び出し可能な名前または型名が競合する場合に役立ちます。
> たとえば、代わりにを使用してから、を使用してを呼び出すこともでき `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` `H` `NamespaceWithH.H(<qubit>)` ます。

> [!NOTE]
> すべての例外の1つとして、 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 常に自動的に開かれる名前空間があります。
> そのため、のような呼び出し可能なは、 [`Length`](xref:microsoft.quantum.core.length) 常に直接使用できます。

### <a name="execution-on-target-machines"></a>ターゲットコンピューターでの実行

これで、Q # プログラムの一般的な実行モデルが明確になりました。

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

最初に、実行される特定の呼び出し可能なは、同じ名前空間で定義されている他の呼び出し可能な型と型にアクセスします。
また、いずれかの[Q # ライブラリ](xref:microsoft.quantum.libraries)からもアクセスできますが、これらのライブラリは、フルネームで参照するか、上記のステートメントを使用して参照する必要があり `open` ます。

その後、呼び出し可能なものが*[ターゲットコンピューター](xref:microsoft.quantum.machines)* 上で実行されます。
このようなターゲットマシンは、実際の quantum ハードウェア、または QDK の一部として提供されている複数のシミュレーターにすることができます。
ここでの目的のために、最も役に立つターゲットコンピューターは、[フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)のインスタンスです。これは `QuantumSimulator` 、ノイズフリーのクォンタムコンピューターで実行されているかのようにプログラムの動作を計算します。

ここまでは、特定の Q&a 呼び出しが実行された場合の動作について説明しました。
この一般的なプロセスは、スタンドアロンアプリケーションでもホストプログラムでも Q # が使用されているかどうかにかかわらず、同じ---になります。そのため、QDK の柔軟性が向上します。
クォンタム開発キットを呼び出すさまざまな方法の違いにより、Q # の呼び出し可能を呼び出す*方法*と、結果が返される方法を区別しています。
具体的には、 
1. 実行される Q # の呼び出しを示します。
2. 可能性のある呼び出し可能な引数の提供方法
3. 実行するターゲットコンピューターを指定します。
4. 結果が返される方法。

最初に、コマンドラインからの Q # スタンドアロンアプリケーションでこれがどのように行われるかについて説明した後、Python および C# ホストプログラムの使用に進みます。
最後に Q # Jupyter Notebook のスタンドアロンアプリケーションを予約しています。これは、最初の3つの機能とは異なり、ローカルの Q&a ファイルを中心にしていないためです。

> [!NOTE]
> これらの例では説明しませんが、実行メソッド間の1つの共通点として、Q # プログラムの内部から (またはなどによって) 出力されるすべてのメッセージは、 [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 通常、それぞれのコンソールに出力されます。

## <a name="q-from-the-command-line"></a>コマンドラインからの Q #
Q # プログラムの記述を開始する最も簡単な方法の1つは、個別のファイルと2番目の言語がまったく気にならないようにすることです。
QDK 拡張機能を使用して Visual Studio Code または Visual Studio を使用すると、1つの Q # ファイルからのみ Q # callables を実行できるシームレスなワークフローが可能になります。

この場合、最終的には、次のように入力して、プログラムの実行を呼び出します。
```dotnetcli
dotnet run
```
をコマンドラインで実行します。
最も単純なワークフローは、ターミナルのディレクトリの場所が Q # ファイルと同じ場合です。たとえば、VS Code の統合ターミナルを使用して、Q # のファイル編集と共に簡単に処理できます。
ただし、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は多くのオプションを受け入れます。プログラムは、 `--project <PATH>` Q # ファイルの場所を指定するだけで、別の場所から実行することもできます。


### <a name="add-entry-point-to-q-file"></a>Q # ファイルにエントリポイントを追加する

ほとんどの Q # ファイルには複数の呼び出し可能が含まれているため、当然ながら、コマンドを指定したときに実行さ*れる呼び出し元*をコンパイラに知らせる必要があり `dotnet run` ます。
これを行うには、Q # ファイル自体に単純な変更を加えます。 
    - 呼び出し可能なの直前に行を追加 `@EntryPoint()` します。

そのため、上記のファイルは
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

これで、コマンドラインからを呼び出すと、が `dotnet run` `MeasureSuperposition` 実行され、返された値がターミナルに直接出力されます。
そのため、またはのどちらかが表示され `One` `Zero` ます。 

より多くの呼び出し可能を定義しているかどうかは関係ありません `MeasureSuperposition` 。実行されるのはのみです。
また、呼び出し元が宣言の前に[ドキュメントコメント](xref:microsoft.quantum.guide.filestructure#documentation-comments)を含んでいる場合は問題ありません `@EntryPoint()` 。属性は、単純にその上に配置できます。

### <a name="callable-arguments"></a>呼び出し可能引数

ここまでは、入力を必要としない操作についてのみ検討しました。
同様の操作を実行するとしますが、複数の qubits---、引数として指定されている数を示しています。
このような操作は、
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
返される値は、測定結果の配列です。
[`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)と [`ForEach`](xref:microsoft.quantum.arrays.foreach) は名前空間にあり [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 、 `open` それぞれに対して追加のステートメントが必要であることに注意してください。

`@EntryPoint()`この新しい操作の前に属性を移動した場合 (ファイル内にはそのような行が1つだけ存在する場合があることに注意してください)、を使用して実行しようとすると、 `dotnet run` 必要な追加のコマンドラインオプションを示すエラーメッセージが表示されます。

コマンドラインの一般的な形式は実際にはであり、呼び出し可能な引数がそこに用意されてい `dotnet run [options]` ます。
この場合、引数 `n` が不足しているため、オプションを指定する必要があることが示されて `-n <n>` います。 Qubits でを実行するには、次のように `MeasureSuperpositionArray` `n=4` します。

```dotnetcli
dotnet run -n 4
```

のような出力を生成する

```output
[Zero,One,One,One]
```

これは、複数の引数にまで拡張されています。

> [!NOTE]
> で定義されている引数名 `camelCase` は、Q # 入力として受け入れられるように、コンパイラによって若干変更されています。 たとえば、の代わりに上記の名前を使用した場合、この入力はでは `n` `numQubits` なく、コマンドラインで指定され `--num-qubits 4` `-n 4` ます。

このエラーメッセージには、ターゲットコンピューターの変更方法など、使用できるその他のオプションも表示されます。

### <a name="different-target-machines"></a>異なるターゲットコンピューター

これまでの操作からの出力が実際の qubits でのアクションの予想される結果であるため、コマンドラインからの既定のターゲットコンピューターが完全な状態の quauntum シミュレーターであることは明らかです `QuantumSimulator` 。
ただし、オプション `--simulator` (または短縮形) を使用して、特定のターゲットコンピューターで実行するように指定することもでき `-s` ます。

たとえば、次のように実行でき [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ます。

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

印刷出力は次のようになります。

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

これらのメトリックが示す内容の詳細については、「[リソースの推定機能: 報告](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)されるメトリック」を参照してください。

### <a name="command-line-execution-summary"></a>コマンドライン実行の概要
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Q 以外の `dotnet run` オプション

前述のようにオプションを使用 `--project` すると、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は Q # の呼び出し可能な引数とは無関係のオプションも受け入れます。
両方の種類のオプションを指定する場合は、固有のオプションを指定し、その `dotnet` 後に区切り記号を指定してから、Q # 固有のオプションを指定する必要があり `--` ます。
たとえば、上記の操作に対してパスと数値 qubits を指定するした場合は、を使用して実行さ `dotnet run --project <PATH> -- -n <n>` れます。

## <a name="q-with-host-programs"></a>ホストプログラムを使用した Q #

Q # ファイルを手に置いて、操作または関数をコマンドラインから直接呼び出す代わりに、別のクラシック言語で*ホストプログラム*を使用することもできます。 具体的には、Python または C# や F # などの .NET 言語で行うことができます (簡潔にするために、ここでは C# についてのみ説明します)。
相互運用性を実現するにはもう少しセットアップが必要ですが、これらの詳細については、[インストールガイド](xref:microsoft.quantum.install)を参照してください。

簡単に言うと、この状況で `*.py` は、 `*.cs` Q # ファイルと同じ場所にホストプログラムファイル (やなど) が含まれるようになりました。
これは実行される*ホスト*プログラムであり、実行時には、q # ファイルから特定の q # 操作と関数を呼び出すことができます。
相互運用性の中核となるのは、q # コンパイラに基づいており、Q # ファイルの内容をホストプログラムからアクセスできるようにすることで、その内容を呼び出すことができるようにすることです。

ホストプログラムを使用する主な利点の1つは、Q # プログラムによって返される古典的なデータをホスト言語でさらに処理できることです。
これは、一部の高度なデータ処理 (Q # で内部的に実行できないものなど) で構成され、その結果に基づいてさらに Q # アクションを呼び出すことができます。また、Q # の結果をプロットするのと同じように簡単に処理することもできます。

一般的なスキームを次に示します。以下では、Python と C# の特定の実装について説明します。 F # ホストプログラムを使用するサンプルについては、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)を参照してください。

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Q # コマンドラインアプリケーションで使用される属性は、ホストプログラムでは使用できません。
> ホストによって呼び出されている Q # ファイルにエラーがある場合は、エラーが発生します。 

別のホストプログラムを使用する場合は、Q # ファイルに変更を加える必要はありません `*.qs` 。
次のホストプログラムの実装はすべて、同じ Q # ファイルで動作します。

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

目的のホスト言語に対応するタブを選択します。

### <a name="python"></a>[Python](#tab/tabid-python)
Python ホストプログラムは次のように構成されます。
1. モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが Q # の相互運用性のために登録されます。 
    これにより、Q # の名前空間を Python モジュールとして表示できるようになります。そこから、Q # の呼び出し可能なものを "インポート" できます。
    これは技術的には Q # の呼び出し可能なものではなく、Python スタブを呼び出すことができることに注意してください。
    これらは Python クラスのオブジェクトとして動作します。この場合、メソッドを使用して、操作を実行する対象のコンピューターを指定します。

2. そのような Q # callables インポートします。この場合は、とという---直接呼び出すことになり `MeasureSuperposition` `MeasureSuperpositionArray` ます。
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    モジュールが `qsharp` インポートされたら、直接 Q # ライブラリの名前空間から呼び出し可能ファイルをインポートすることもできます。

3. その他の Python コードでは、特定のターゲットコンピューターでそれらの呼び出しを呼び出すことができるようになりました。さらに使用するために、その戻り値を変数に代入します (値を返す場合)。

#### <a name="specifying-target-machines"></a>ターゲットコンピューターの指定
特定のターゲットコンピューターで実行される操作の呼び出しは、インポートされたオブジェクトのさまざまな Python メソッドを使用して行われます。
たとえば、は、を使用して `.simulate(<args>)` 操作を実行しますが、ではを使用 `QuantumSimulator` `.estimate_resources(<args>)` `ResourcesEstimator` します。

#### <a name="passing-inputs-to-q"></a>入力を Q に渡す\#
Q # の呼び出し可能な引数は、キーワード引数の形式で指定する必要があります。キーワードは、Q # 呼び出し可能な定義での引数名です。
つまり、は有効ですが、では `MeasureSuperpositionArray.simulate(n=4)` エラーがスローされ `MeasureSuperpositionArray.simulate(4)` ます。

そのため、Python ホストプログラム 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

次のような結果が出力されます。

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

C# ホストプログラムには複数のコンポーネントがあり、QDK の一部のコンポーネントと密接に連携しています。たとえば、シミュレーターは、それ自体が C# 上に構築されています。

Q # コンパイラは、q # ファイルの Q # 名前空間から同等の名前付き C# 名前空間を生成することによって、ここで動作します。
さらに、Q # の呼び出しが許容される型またはその中に定義された型ごとに、同等の名前付き C# クラスを生成します。

まず、ホストプログラムで使用されるすべてのクラスをステートメントで使用できるようにし `using` ます。これは、 `open` Q # ファイル内のステートメントに対してほぼ同じ単位です。

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

次に、C# の名前空間、他のいくつかのビットと部分 (以下の完全なコードブロックを参照) を宣言します。その後、必要なすべてのクラシックプログラミングを行います (たとえば、Q # の呼び出しが許容されるように引数を計算します)。
この場合、後者は必要ありませんが、このような使用例については、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)を参照してください。

#### <a name="target-machines"></a>ターゲット コンピューター

Q # に戻るには、操作を実行する対象コンピューターのインスタンスを作成する必要があります。

```csharp
            using var sim = new QuantumSimulator();
```

他のターゲットマシンの使用は、別のターゲットコンピューターをインスタンス化するのと同じように簡単ですが、それを行う方法と戻り値を処理する方法は若干異なります。
簡潔にするために、ここではについて説明 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) し、次のものを含め [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator)ます。

Q # 操作から生成された各 C# クラスには、メソッドがあり `Run` ます。このメソッドの最初の引数は、対象のコンピューターインスタンスである必要があります。
そのため、でを実行するには、を `MeasureSuperposition` `QuantumSimulator` 使用 `MeasureSuperposition.Run(sim)` します。
返された結果は、C# の変数に割り当てることができます。

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`このメソッドは、実際のクォンタムハードウェアの場合に発生するため、非同期的に実行されます。したがって、 `await` キーワードはタスクが完了するまでさらに実行をブロックします。

Q # が呼び出し可能なときに戻り値の型がない場合は、 `Unit` 変数に代入せずに同じ方法で実行を実行できます。
その場合、行全体は単に 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>引数

Q # の呼び出し可能な引数は、ターゲットコンピューターに追加の引数として渡されるだけです。
したがって、qubits での結果は、を使用してフェッチされます。 `MeasureSuperpositionArray` `n=4` 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

完全な C# ホストプログラムは、次のようになります。

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

C# ファイルの位置で、「」と入力すると、コマンドラインからホストプログラムを実行できます。
```dotnetcli
dotnet run
```
この場合、次のような出力がコンソールに書き込まれます。 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> コンパイラの名前空間との相互運用性により、ステートメントを使用せずに Q&a を利用できるように `using NamespaceName;` し、単純に C# の名前空間のタイトルをそれに一致させることができます。
> つまり、をに置き換え `namespace host` `namespace NamespaceName` ます。

#### <a name="including-the-resources-estimator"></a>リソースの推定機能を含む

では、 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) 出力を取得するために若干異なる実装が必要です。

まず、ステートメントを使用して変数としてインスタンス化する代わりに、を使用して `using` `QuantumSimulator` クラスのオブジェクトを直接インスタンス化します。

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

複数の Q # 操作で1つのターゲットシミュレーターが使用されるのではなく、それぞれに対して1つのターゲットシミュレーターがインスタンス化されていることに注意してください。 これは、ターゲットコンピューターとして使用されたときにオブジェクト自体が変更され、その結果をクラスメソッドで後から取得できるためです `.ToTSV()` 。

リソース estimators に対して操作を実行するには、次を使用します。

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
次に、とを使用して、結果をタブ区切り値 (TSV) としてフェッチし `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` ます。

したがって、との両方を使用する完全な C# ホストプログラムは、次のような `QuantumSimulator` `ResourcesEstimator` 形式になります。

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


これにより、のような出力が生成されます。

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a>Q# Jupyter Notebook
Q # Jupyter Notebook では、IQ # kernel を使用します。これにより、1つのノートブックで Q&a を定義、コンパイル、および実行して、命令、メモ、およびその他のコンテンツと共に---することができます。
つまり、Q # ファイルの内容をインポートして使用することはできますが、 `*.qs` 実行モデルでは必要ありません。

ここでは、上で定義した Q # 操作を実行する方法について詳しく説明しますが、q # Jupyter Notebook の使用方法の詳細については、「 [q # と Jupyter notebook の概要](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)」を参照してください。

### <a name="defining-operations"></a>定義 (操作を)

Q # Jupyter Notebook では、q # ファイルの名前空間内と同様に Q # コードを入力します。

そのため、それぞれの名前空間のステートメントを使用して、 [Q # 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)からの呼び出し可能なアクセスを有効にすることができ `open` ます。
このようなステートメントでセルを実行すると、その名前空間の定義がワークスペース全体で使用できるようになります。

> [!NOTE]
> [Microsoft の quantum](xref:microsoft.quantum.intrinsic)および[microsoft の quantum](xref:microsoft.quantum.canon) (やなど) からの呼び出し [`H`](xref:microsoft.quantum.intrinsic.h) は、 [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) Q # jupyter notebook のセル内で定義されている操作で自動的に使用できるようになります。
> ただし、外部の Q # ソースファイルからのコードには当てはまりません ( [q # と Jupyter notebook の概要](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)に記載されているプロセス)。 
> 

同様に、操作を定義するには、Q # コードを記述してセルを実行するだけです。

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

出力には、これらの操作が一覧表示されます。これらの操作は、今後のセルから呼び出すことができます。

### <a name="target-machines"></a>ターゲット コンピューター

特定のターゲットコンピューターで操作を実行する機能は、 [IQ # マジックコマンド](xref:microsoft.quantum.guide.quickref.iqsharp)を使用して提供されます。
たとえば、はを使用し、を使用し `%simulate` `QuantumSimulator` `%estimate` `ResourcesEstimator` ます。

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>関数および操作への入力の引き渡し

現在、実行マジックコマンドは、引数を受け取らない操作でのみ使用できます。 そのため、を実行するには、次に引数を指定し `MeasureSuperpositionArray` て操作を呼び出す "ラッパー" 操作を定義する必要があります。

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

この操作は `%estimate` 、やその他の実行コマンドと同様に使用できます。
