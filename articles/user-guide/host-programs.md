---
title: プログラムを実行する方法 Q#
description: プログラムを実行するさまざまな方法の概要を説明し Q# ます。 Q#Python または .net 言語のコマンドプロンプト、jupyter notebook、およびクラシックホストプログラム。
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691693"
---
# <a name="ways-to-run-a-no-locq-program"></a>プログラムを実行する方法 Q#

Quantum Development Kit の最大の強みの1つは、プラットフォームと開発環境全体での柔軟性です。
ただし、これは、新しい Q# ユーザーが、 [インストールガイド](xref:microsoft.quantum.install)に記載されている多くのオプションによって混乱を招き、圧倒される可能性があることも意味します。
このページでは、プログラムの実行時の動作につい Q# て説明し、ユーザーが実行できるさまざまな方法を比較します。

主な違いは、を Q# 実行できることです。
- スタンドアロンアプリケーションとして、 Q# は関連する唯一の言語であり、プログラムは直接呼び出されます。 このカテゴリには、次の2つの方法があります。
  - コマンドラインインターフェイス
  - Q# Jupyter Notebook
- Python または .NET 言語 (C#、F # など) で記述された追加の *ホストプログラム* を使用して、プログラムを呼び出し、返された結果をさらに処理できます。

これらのプロセスとその違いについて理解を深めるために、単純なプログラムを考えて、 Q# 実行する方法を比較します。

## <a name="basic-no-locq-program"></a>基本 Q# プログラム

基本的な量子プログラムは、法則の状態が $ \ket $ および $ \ket $ の qubit を準備し、それを測定し、結果を返すことで構成される場合があり {0} {1} ます。これは、これら2つの状態のうち、確率が等しい場合に、ランダムに発生します。
実際には、このプロセスは、クォンタムの [乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng) のクイックスタートの中核になっています。

では Q# 、これは次のコードによって実行されます。

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

ただし、このコードだけをで実行することはできません Q# 。
そのためには、操作の本体を構成する必要があります。この [操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)は、直接または別の操作によって---呼び出されたときに実行されます。 そのため、次の形式の操作を記述できます。
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
`MeasureSuperposition`入力を受け取らず、 [Result](xref:microsoft.quantum.guide.types)型の値を返す操作を定義しました。

このページの例は操作のみで構成 Q# *operations* されていますが、ここで説明するすべての概念は、関数にも同様に関係 Q# *functions* します。そのため、これらのすべての概念を *呼び出し* が許容できるものとして参照します。 これらの違いについては、 [ Q# 「基本: 操作と関数](xref:microsoft.quantum.guide.basics#q-operations-and-functions)」で説明されています。これらの定義の詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。

### <a name="callable-defined-in-a-no-locq-file"></a>ファイルで定義された呼び出し可能 Q#

呼び出し可能なは、によって呼び出され、実行され Q# ます。
ただし、完全なファイルを構成するには、さらにいくつかの追加機能が必要です `*.qs` Q# 。

すべての Q# 型と呼び出し可能 (定義したものと言語に固有の型の両方) は、 *名前空間* 内で定義されます。これらの名前は、参照可能な完全な名前を提供します。

たとえば、およびの [`H`](xref:Microsoft.Quantum.Intrinsic.H) 各 [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) 操作は、 [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) 名前空間と名前空間 ( [ Q# 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)の一部) にあります。
そのため、常に *完全な* 名前を使用してを呼び出すことができます `Microsoft.Quantum.Intrinsic.H(<qubit>)` が、 `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 常にこの操作を実行すると、コードが乱雑になることがあります。

ステートメントを `open` 使用すると、上記の操作本体で行ったように、より簡潔な短縮形で呼び出し可能なを参照できます。
Q#このため、操作を含む完全なファイルは、独自の名前空間を定義し、操作が使用する呼び出しの名前空間を開いて、次の操作を行うことで構成されます。

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
> 名前空間は、開いたときに *別名* を付けることもできます。これは、2つの名前空間の呼び出し可能な名前または型名が競合する場合に役立ちます。
> たとえば、代わりにを使用してから、を使用してを呼び出すこともでき `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` `H` `NamespaceWithH.H(<qubit>)` ます。

> [!NOTE]
> すべての例外の1つとして、 [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) 常に自動的に開かれる名前空間があります。
> そのため、のような呼び出し可能なは、 [`Length`](xref:Microsoft.Quantum.Core.Length) 常に直接使用できます。

### <a name="running-on-target-machines"></a>ターゲットコンピューターでの実行

これで、プログラムの一般的な実行モデルが明確になりました Q# 。

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

最初に、実行される特定の呼び出し可能なが、同じ名前空間で定義されている他の呼び出し可能な型と型にアクセスできるようにします。
また、 [ Q# ライブラリ](xref:microsoft.quantum.libraries)からアクセスすることもできますが、フルネームを使用するか、上記のステートメントを使用して参照する必要があり `open` ます。

その後、呼び出し可能なものが *[ターゲットコンピューター](xref:microsoft.quantum.machines)* 上で実行されます。
このようなターゲットマシンは、実際の quantum ハードウェア、または QDK の一部として提供されている複数のシミュレーターにすることができます。
ここでの目的のために、最も役に立つターゲットコンピューターは、 [フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)のインスタンスです。これは `QuantumSimulator` 、ノイズフリーのクォンタムコンピューターで実行されているかのようにプログラムの動作を計算します。

ここまでは、特定の Q# 呼び出し可能が実行されたときの動作について説明しました。
がスタンドアロンアプリケーションとホストプログラムのどちらで使用されているかにかかわらず Q# 、この一般的なプロセスは同じ---であるため、QDK の柔軟性があります。
クォンタム開発キットを呼び出す方法の違いにより、呼び出し可能な呼び出しの *how* 実行方法 Q# と結果が返される方法が異なります。
具体的には、次のような違いがあります。

- Q#実行する呼び出し元を示す
- 可能性のある呼び出し可能な引数の提供方法
- 実行するターゲットコンピューターの指定
- 結果が返される方法

まず、コマンドプロンプトからスタンドアロンアプリケーションを使用してこれがどのように行われるかについて説明 Q# し、次に Python および C# ホストプログラムの使用に進みます。
Jupyter Notebook のスタンドアロンアプリケーションは、 Q# 最初の3つとは異なり、プライマリ機能はローカルファイルを中心にしていません Q# 。

> [!NOTE]
> これらの例では説明しませんが、run メソッド間の1つの共通点として、プログラム内から Q# (またはなどによって) 出力されるすべてのメッセージは、 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 通常、それぞれのコンソールに出力されます。

## <a name="no-locq-from-the-command-prompt"></a>Q# コマンドプロンプトから
プログラムの記述を開始する最も簡単な方法の1つ Q# は、個別のファイルと2番目の言語をまったく気にすることがないようにすることです。
QDK 拡張機能を使用して Visual Studio Code または Visual Studio を使用すると、 Q# 1 つのファイルから呼び出し可能なものだけを実行するシームレスな作業フローを実現でき Q# ます。

この場合、最終的には、次のように入力してプログラムを実行します。

```dotnetcli
dotnet run
```

」と入力します。
最も単純なワークフローは、ターミナルのディレクトリの場所がファイルと同じ場合です Q# Q# 。たとえば、VS Code の統合ターミナルを使用して、ファイルの編集と共に簡単に処理できます。
ただし、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は多くのオプションを受け入れます。プログラムは、 `--project <PATH>` ファイルの場所を指定するだけで別の場所から実行することもできます Q# 。


### <a name="add-entry-point-to-no-locq-file"></a>ファイルへのエントリポイントの追加 Q#

ほとんど Q# のファイルには複数の呼び出し可能が含まれているため、当然ながら、コマンドを指定したときに実行さ *れる呼び出し元* をコンパイラに知らせる必要があり `dotnet run` ます。
これは、ファイル自体を単純に変更することで行われ Q# ます。 
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

これで、コマンドプロンプトからを呼び出すと、が `dotnet run` `MeasureSuperposition` 実行され、返された値がターミナルに直接出力されます。
そのため、またはのどちらかが表示され `One` `Zero` ます。 

より多くの呼び出し可能を定義しているかどうかは関係ありません `MeasureSuperposition` 。実行されるのはのみです。
また、呼び出し元が宣言の前に [ドキュメントコメント](xref:microsoft.quantum.guide.filestructure#documentation-comments) を含んでいる場合は問題ありません `@EntryPoint()` 。属性は、単純にその上に配置できます。

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
[`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)と [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) は名前空間にあり [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 、 `open` それぞれに対して追加のステートメントが必要であることに注意してください。

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
> で定義されている引数名 `camelCase` は、入力として受け入れられるように、コンパイラによって若干変更されてい Q# ます。 たとえば、の代わりに上記の名前を使用した場合、この入力はでは `n` `numQubits` なく、コマンドラインで指定され `--num-qubits 4` `-n 4` ます。

このエラーメッセージには、ターゲットコンピューターの変更方法など、使用できるその他のオプションも表示されます。

### <a name="different-target-machines"></a>異なるターゲットコンピューター

これまでの操作からの出力が実際の qubits でのアクションの予想される結果であるため、コマンドラインからの既定のターゲットコンピューターが完全な状態のクォンタムシミュレーターであることは明らかです `QuantumSimulator` 。
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

これらのメトリックが示す内容の詳細については、「 [リソースの推定機能: 報告](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)されるメトリック」を参照してください。

### <a name="command-line-run-summary"></a>コマンドラインの実行の概要
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>オプション以外 Q# `dotnet run`

前述のようにオプションを使用 `--project` すると、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は呼び出し可能な引数とは無関係のオプションも受け入れ Q# ます。
両方の種類のオプションを指定する場合は、固有のオプションを指定し、その後に区切り記号を指定してから、固有のオプションを `dotnet` 指定する必要があり `--` Q# ます。
たとえば、上記の操作に対して、数値 qubits と共にパスを指定すると、を使用して実行さ `dotnet run --project <PATH> -- -n <n>` れます。

## <a name="no-locq-with-host-programs"></a>Q# ホストプログラムを使用する

ファイルを Q# 手に置いて、コマンドプロンプトから直接操作または関数を呼び出す代わりに、別のクラシック言語で *ホストプログラム* を使用する方法があります。 具体的には、Python または C# や F # などの .NET 言語で行うことができます (簡潔にするために、ここでは C# についてのみ説明します)。
相互運用性を実現するにはもう少しセットアップが必要ですが、これらの詳細については、 [インストールガイド](xref:microsoft.quantum.install)を参照してください。

簡単に言うと、この状況で `*.py` は、 `*.cs` ファイルと同じ場所にホストプログラムファイル (やなど) が含まれるようになりました Q# 。
これで実行される *ホスト* プログラムになり、実行中に、ファイルから特定の操作と関数を呼び出すことができ Q# Q# ます。
相互運用性の中核となるのは、コンパイラを使用して、 Q# ファイルの内容を Q# ホストプログラムからアクセスできるようにし、それらを呼び出すことができるようにすることです。

ホストプログラムを使用する主な利点の1つは、プログラムによって返される古典的なデータを Q# ホスト言語でさらに処理できることです。
これは、いくつかの高度なデータ処理 (で内部で実行できないものなど Q# ) と、その結果に基づいて他のアクションを呼び出すことができ Q# ます。また、結果をプロットするのと同じように簡単です Q# 。

一般的なスキームを次に示します。以下では、Python と C# の特定の実装について説明します。 F # ホストプログラムを使用するサンプルについては、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)を参照してください。

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`アプリケーションに使用される属性は、 Q# ホストプログラムでは使用できません。
> Q#ホストによって呼び出されているファイルにエラーがある場合は、エラーが発生します。 

別のホストプログラムを使用する場合は、ファイルに対する変更は必要ありません `*.qs` Q# 。
次のホストプログラムの実装はすべて、同じファイルで動作し Q# ます。

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
1. モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが相互運用性のために登録され Q# ます。 
    これ Q# により、名前空間を Python モジュールとして表示できるようになります。そこから、"インポート" 呼び出しを実行でき Q# ます。
    これは技術的には呼び出し可能なものではなく Q# 、インポートされる Python スタブであり、それを呼び出すことができることに注意してください。
    これらは Python クラスのオブジェクトとして動作します。 これらのオブジェクトに対してメソッドを使用して、プログラムの実行時に操作を送信するターゲットコンピューターを指定します。

2. そのような呼び出しをインポート Q# します。ここでは、を直接呼び出します。この場合、 `MeasureSuperposition` と--- `MeasureSuperpositionArray` ます。
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    モジュールをインポートした場合は、 `qsharp` ライブラリの名前空間から直接 callables 実行可能ファイルをインポートすることもでき Q# ます。

3. その他の Python コードでは、特定のターゲットコンピューターでそれらの呼び出しを呼び出すことができるようになりました。さらに使用するために、その戻り値を変数に代入します (値を返す場合)。

#### <a name="specifying-target-machines"></a>ターゲットコンピューターの指定
特定のターゲットコンピューターで実行される操作の呼び出しは、インポートされたオブジェクトのさまざまな Python メソッドを使用して行われます。
たとえば、は、を使用して `.simulate(<args>)` 操作を実行しますが、ではを使用 `QuantumSimulator` `.estimate_resources(<args>)` `ResourcesEstimator` します。

#### <a name="passing-inputs-to-q"></a>入力を Q に渡す\#
呼び出し可能な引数は、キーワード Q# 引数の形式で指定する必要があります。キーワードは呼び出し可能な定義の引数名です Q# 。
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

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#他のプロジェクトまたはパッケージからのコードの使用

既定では、 `import qsharp` コマンドは、現在のフォルダー内のすべてのファイルを読み込み、 `.qs` その Q# 操作と関数を Python スクリプト内から使用できるようにします。

別のフォルダーからコードを読み込むには、 Q# [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects)を使用して、 `.csproj` プロジェクトのファイル (つまり Q# 、を参照するプロジェクト) への参照を追加し `Microsoft.Quantum.Sdk` ます。
このコマンドは `.qs` 、とそのサブフォルダーを含むフォルダー内のすべてのファイルをコンパイル `.csproj` します。 また、またはから参照されるプロジェクトを通じて参照されるパッケージも、そのファイルで再帰的に読み込まれ `PackageReference` Q# `ProjectReference` `.csproj` ます。

たとえば、次の Python コードは、現在のフォルダーに対する相対パスを参照して外部プロジェクトをインポートし、その操作の1つを呼び出し Q# ます。

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

この結果、次のような出力が生成されます。

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

コードを含む外部パッケージを読み込むに Q# は、 [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)を使用します。

現在の Q# フォルダー内のコードが外部のプロジェクトまたはパッケージに依存している場合は、 `import qsharp` 依存関係がまだ読み込まれていないため、の実行時にエラーが発生することがあります。
コマンドの実行中に必要な外部パッケージまたはプロジェクトを読み込むには、Python スクリプトが格納されているフォルダーに、を Q# `import qsharp` 参照するファイルが含まれていることを確認し `.csproj` `Microsoft.Quantum.Sdk` ます。 その中で、 `.csproj` プロパティを `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` に追加し `<PropertyGroup>` ます。 これにより Q# `ProjectReference` `PackageReference` `.csproj` 、コマンドの実行中に、で見つかった項目または項目を再帰的に読み込むように指示され `import qsharp` ます。

たとえば、 `.csproj` パッケージを自動的に読み込む単純なファイルを次に示し Q# `Microsoft.Quantum.Chemistry` ます。

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> 現在、このカスタム `<IQSharpLoadAutomatically>` プロパティは python ホストで要求されていますが、将来は `.csproj` python スクリプトと同じフォルダーにあるファイルの既定の動作になる可能性があります。

> [!NOTE]
> 現在 `<QsharpCompile>` 、の設定は `.csproj` Python ホストによって無視され、 `.qs` のフォルダー (サブフォルダーを含む) 内のすべてのファイルが `.csproj` 読み込まれ、コンパイルされます。 設定のサポートは `.csproj` 今後改善される予定です (詳細については、「 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 」を参照してください)。


### <a name="c"></a>[C#](#tab/tabid-csharp)

C# ホストプログラムには複数のコンポーネントがあり、QDK の一部のコンポーネントと密接に連携しています。たとえば、シミュレーターは、それ自体が C# 上に構築されています。

ここでは、 Q# ファイルの名前空間から同等の名前付き C# 名前空間を生成することによって、コンパイラが動作し Q# Q# ます。
さらに、呼び出しが許容される型またはその中に定義された型ごとに、同等の名前付き C# クラスを生成 Q# します。

まず、ホストプログラムで使用されるすべてのクラスをステートメントで使用できるようにし `using` ます。これは、 `open` ファイル内のステートメントに対しておおよその順序で実行され Q# ます。

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

次に、C# の名前空間、他のいくつかのビットと部分 (以下の完全なコードブロックを参照) と、必要なすべての古典的なプログラミング (呼び出しを行うための引数の計算など) を宣言し Q# ます。
この場合、後者は必要ありませんが、このような使用例については、  [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)を参照してください。

#### <a name="target-machines"></a>ターゲット コンピューター

に戻るには Q# 、操作を実行する対象コンピューターのインスタンスを作成する必要があります。

```csharp
            using var sim = new QuantumSimulator();
```

他のターゲットマシンの使用は、別のターゲットコンピューターをインスタンス化するのと同じように簡単ですが、それを行う方法と戻り値を処理する方法は若干異なります。
簡潔にするために、ここではについて説明 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) し、次のものを含め [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator)ます。

操作から生成された各 C# クラスには Q# メソッドがあり `Run` 、その最初の引数はターゲットコンピューターインスタンスである必要があります。
そのため、でを実行するには、を `MeasureSuperposition` `QuantumSimulator` 使用 `MeasureSuperposition.Run(sim)` します。
返された結果は、C# の変数に割り当てることができます。

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`このメソッドは、実際のクォンタムハードウェアの場合に使用されるため、非同期的に実行されます。したがって、キーワードは、 `await` タスクが完了するまでさらに処理をブロックします。

Q#呼び出し可能なが返されない場合 (戻り値の型がある場合など `Unit` )、変数に代入せずに、実行を同じ方法で実行できます。
その場合、行全体は単に 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>引数

呼び出し可能な引数 Q# は、ターゲットコンピューターの後に追加の引数として渡されるだけです。
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

C# ファイルの場所では、「」と入力して、コマンドプロンプトからホストプログラムを実行できます。
```dotnetcli
dotnet run
```
この場合、次のような出力がコンソールに書き込まれます。 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> コンパイラの名前空間との相互運用性により、 Q# ステートメントを使用せずに呼び出し可能にすることができ `using NamespaceName;` ます。また、C# の名前空間のタイトルと単純に一致させることもできます。
> つまり、をに置き換え `namespace host` `namespace NamespaceName` ます。

#### <a name="including-the-resources-estimator"></a>リソースの推定機能を含む

では、 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) 出力を取得するために若干異なる実装が必要です。

まず、ステートメントを使用して変数としてインスタンス化する代わりに、を使用して `using` `QuantumSimulator` クラスのオブジェクトを直接インスタンス化します。

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

複数の操作で1つのターゲットシミュレーターが使用されるのではなく Q# 、それぞれに対して1つのターゲットシミュレーターがインスタンス化されていることに注意してください。 これは、ターゲットコンピューターとして使用されたときにオブジェクト自体が変更され、その結果をクラスメソッドで後から取得できるためです `.ToTSV()` 。

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

## <a name="no-locq-jupyter-notebooks"></a>Q# Jupyter Notebook
Q# Jupyter Notebook では、I カーネルを使用します Q# 。これにより、 Q# すべての命令、メモ、およびその他のコンテンツと共に、呼び出し可能なを1つのノートブックで定義、コンパイル、および実行することが---ます。
つまり、ファイルの内容をインポートして使用することはできますが、 `*.qs` Q# 実行モデルでは必要ありません。

ここでは、上で定義した操作を実行する方法について詳しく説明します Q# が、jupyter notebook の使用方法の概要については、「 Q# 概要」と「 [ Q# jupyter notebook](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)」を参照してください。

### <a name="defining-operations"></a>定義 (操作を)

Jupyter Notebook では Q# 、 Q# ファイルの名前空間内と同様にコードを入力し Q# ます。

そのため、 [ Q# 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)から、 `open` それぞれの名前空間のステートメントを使用して、呼び出し可能なアクセスを有効にすることができます。
このようなステートメントでセルを実行すると、その名前空間の定義がワークスペース全体で使用できるようになります。

> [!NOTE]
> [Microsoft の quantum](xref:Microsoft.Quantum.Intrinsic)および[microsoft の quantum](xref:Microsoft.Quantum.Canon) (たとえば、や) からの呼び出し [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) 可能範囲は、jupyter notebook のセル内に定義されている操作で自動的に使用できるようになります。 Q#
> ただし、外部ソースファイルからのコードには当てはまりません Q# ( [概要 Q# と Jupyter notebook](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)に示されているプロセス)。 
> 

同様に、操作を定義するには、コードの記述 Q# とセルの実行のみが必要です。

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

出力には、これらの操作が一覧表示されます。これらの操作は、今後のセルから呼び出すことができます。

### <a name="target-machines"></a>ターゲット コンピューター

特定の対象コンピューターで操作を実行する機能は、 [I Q# マジックコマンド](xref:microsoft.quantum.guide.quickref.iqsharp)を使用して提供されます。
たとえば、はを使用し、を使用し `%simulate` `QuantumSimulator` `%estimate` `ResourcesEstimator` ます。

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>関数および操作への入力の引き渡し

操作に入力を渡すために、 Q# 引数をペアとして `key=value` 実行マジックコマンドに渡すことができます。
そのため、 `MeasureSuperpositionArray` 4 つの qubits を使用してを実行するには、次のように実行し `%simulate MeasureSuperpositionArray n=4` ます。

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

このパターンは `%estimate` 、およびその他の実行コマンドと同様に使用できます。

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#他のプロジェクトまたはパッケージからのコードの使用

既定では、 Q# Jupyter Notebook は現在のフォルダーにあるすべてのファイルを読み込み、その `.qs` Q# 操作と機能を Notebook 内から使用できるようにします。 [ `%who` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.who)では、現在使用可能なすべての操作と関数が一覧表示され Q# ます。

別のフォルダーからコードを読み込むには、 Q# [ `%project` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.project)を使用して、 `.csproj` プロジェクトのファイル (つまり Q# 、を参照するプロジェクト) への参照を追加し `Microsoft.Quantum.Sdk` ます。 このコマンドを実行する `.qs` `.csproj` と、(およびサブフォルダー) を含むフォルダー内のすべてのファイルがコンパイルされます。 また、またはから参照されるプロジェクトを通じて参照されるパッケージも、そのファイルで再帰的に読み込まれ `PackageReference` Q# `ProjectReference` `.csproj` ます。 

たとえば、次のセルは、現在の Q# フォルダーを基準としてプロジェクトパスが参照される外部プロジェクトからの操作をシミュレートします。

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

コードを含む外部パッケージを読み込むには Q# 、 [ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用します。
パッケージを読み込むと、パッケージの一部であるすべてのアセンブリに含まれている任意のカスタムマジックコマンドまたは表示エンコーダーも使用できるようになります。

ノートブックの初期化時に外部パッケージまたはプロジェクトを読み込むには Q# 、notebook フォルダーにを参照するファイルが含まれていることを確認し `.csproj` `Microsoft.Quantum.Sdk` ます。 その中で、 `.csproj` プロパティを `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` に追加し `<PropertyGroup>` ます。 これにより、 Q# `ProjectReference` notebook の読み込み時に、 `PackageReference` で見つかった項目または項目を再帰的に読み込むように指示され `.csproj` ます。

たとえば、 `.csproj` パッケージを自動的に読み込む単純なファイルを次に示し Q# `Microsoft.Quantum.Chemistry` ます。

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> 現在、このカスタム `<IQSharpLoadAutomatically>` プロパティは Jupyter Notebook ホストで要求されてい Q# ますが、今後、 `.csproj` Notebook ファイルと同じフォルダーにあるファイルの既定の動作になる可能性があります。

> [!NOTE]
> 現在 `<QsharpCompile>` 、の設定は `.csproj` Jupyter Notebook ホストによって無視され、 Q# `.qs` のフォルダー (サブフォルダーを含む) 内のすべてのファイルが `.csproj` 読み込まれ、コンパイルされます。 設定のサポートは `.csproj` 今後改善される予定です (詳細については、「 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 」を参照してください)。
