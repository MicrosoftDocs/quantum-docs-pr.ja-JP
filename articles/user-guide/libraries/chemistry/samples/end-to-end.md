---
title: NWChem クォンタムプログラムのサンプル
description: NWChem 入力デッキを使用して、量子化学シミュレーションのゲート数を取得する例を紹介します。
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: e0ec7dcbdccbab5c81177a4223c71fd3f2ce57d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847778"
---
# <a name="end-to-end-with-nwchem"></a>NWChem を使用したエンド ツー エンド #

この記事では、Nw化学シミュレーションのゲート数を取得する例を、 [Nwchem](http://www.nwchem-sw.org/index.php/Main_Page) 入力デッキから順に見ていきます。
この例に進む前に、Docker がインストールされていることを確認してください。 [インストールと検証のガイド](xref:microsoft.quantum.chemistry.concepts.installation)に従ってください。

詳細:
- [NWChem 入力デッキの構造](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Quantum 開発キットで使用する入力デックコマンド](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [化学ライブラリと依存関係のインストール](xref:microsoft.quantum.chemistry.concepts.installation)
- [リソースカウント](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> この例では、Windows PowerShell Core を実行する必要があります。
> Windows、macOS、または Linux 用の PowerShell Core をでダウンロード https://github.com/PowerShell/PowerShell します。

## <a name="importing-required-powershell-modules"></a>必要な PowerShell モジュールのインポート ##

まだ実行していない場合は、 [Microsoft/Quantum リポジトリ](https://github.com/Microsoft/Quantum)を複製します。これには、Quantum 開発キットを操作するためのサンプルとユーティリティが含まれています。

```powershell
git clone https://github.com/Microsoft/Quantum
```

複製が完了したら `Microsoft/Quantum` 、 `cd` フォルダーに `utilities/` 対してを実行し、Docker と nwchem を操作するための PowerShell モジュールをインポートします。

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> 既定では、Windows によって、すべてのスクリプトまたはモジュールの実行がセキュリティ対策として禁止されます。
> などのモジュールを Windows で実行できるようにするには、 `Invoke-NWChem.psm1` ポリシーの変更が必要になることがあります。
> これを行うには、次のコマンドを実行し `Set-ExecutionPolicy` ます。
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> PowerShell を終了すると、ポリシーは元に戻ります。
> ポリシーを保存する場合は、次のように別の値を使用し `-Scope` ます。
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

これで、コマンドを使用できるようになりました `Convert-NWChemToBroombridge` 。

```powershell
Get-Command -Module InvokeNWChem
```

次に、 `Get-GateCount` **GetGateCount** サンプルで提供されているコマンドをインポートします。
詳細については、「」の [サンプルに記載されている手順](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount)を参照してください。
次に、 `<runtime>` `win10-x64` `osx-x64` `linux-x64` オペレーティングシステムに応じて、、、またはのいずれかを使用して、次のを実行します。

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

これで、コマンドを使用できるようになりました `Get-GateCount` 。

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>入力デッキ ##

NWChem パッケージは、メモリ割り当て設定などの他のパラメーターと共に、解決するクォンタムの化学問題を指定する _入力デッキ_ と呼ばれるテキストファイルを受け取ります。
この例では、NWChem に付属する事前に作成された入力デッキの1つを使用します。
まず、 [nwchemgit/nwchem リポジトリ](https://github.com/nwchemgit/nwchem)を複製します。

> [!NOTE]
> これは非常に大きなリポジトリであるため、簡易複製を実行して、引数を使用して帯域幅とディスク領域を節約することができ `--depth 1` ます。
> ただし、これは省略可能です。
> 複製は、なしで正常に動作 `--depth 1` します。

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

リポジトリには、 `nwchemgit/nwchem` Quantum 開発キットで使用するためのさまざまな入力デッキが用意されており、 [ `QA/chem_library_tests` フォルダー](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests)の下に一覧表示されています。
この例では、入力デッキを使用し `H4` ます。

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

分子は、4つの hydrogen アトムのシステムであり、1つの角度 ( `alpha` デッキの名前で示されているパラメーター) に依存する特定のジオメトリに配置されてい `h4_sto6g_alpha.nw` ます。 H4 は、1970年代以来の計算化学の既知の [分子ベンチマーク](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) です。 パラメーターは、 `sto6g` デッキが Slater の型の回転に対して表現を実装することを示しています。具体的には、6つのガウスベースの関数を使用した [設定](https://en.wikipedia.org/wiki/STO-nG_basis_sets) に関する表現です。 さらに、この入力デッキには、省略形 Engine (TCE) に対するいくつかの手順が含まれています。このエンジンは、NWChem を使用して、Quantum 開発キットとの相互運用に必要な情報を生成します。

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>NWChem からの Broombridge 出力の生成と使用 ##

これで、Broombridge ドキュメントを生成して使用するために必要なものがすべて揃いました。
NWChem を実行し、入力デッキの Broombridge ドキュメントを生成するには `h4_sto6g_0.000.nw` 、次のように実行し `Convert-NWChemToBroombridge` ます。

> [!NOTE]
> このコマンドを初めて実行すると、Docker によってイメージがダウンロードされ `nwchemorg/nwchem-qc` ます。
> 接続速度によっては、これには少し時間がかかることがあります。

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

これにより、という Broombridge ドキュメントが生成されます。これは、 `h4_sto6g_0.000.yaml` で使用でき `Get-GateCount` ます。

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

さまざまなクォンタムのシミュレーション方法について、T count、ローテーション数、CNOT count などのリソースの推定を含むコンソール出力が表示されるようになりました。

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

ここでは、さまざまなことを行います。 
- さまざまな定義済みの入力デッキを試してみてください。たとえば、でパラメーターを変えることによって、 `alpha` `h4_sto6g_alpha.nw` 
- `STO-nG`複数の選択を行うためのモデルの調査など、NWChem デッキを直接編集して、デッキを変更してみてください。 
- で利用可能なその他の定義済みの NWChem 入力デッキを試してみてください。 `nwchem/qa/chem_library_tests`
- NWChem から生成された定義済みの Broombridge YAML ベンチマークのスイートを試してみてください。 [Microsoft/Quantum リポジトリ](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)の一部として入手できます。 これらのベンチマークは次のとおりです。 
    - 分子 hydrogen (H2)、Beryllium (Be)、リチウム水素 (LiH) などの小さな分子
    - ozone (O3)、carotene、cytosine などのより大きな分子。 
- Microsoft Quantum Development Kit のインターフェイスを特徴とするグラフィカルフロントエンドの [Emsl 矢印](https://arrows.emsl.pnnl.gov/api/qsharp_chem) を試してみてください。 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>EMSL 方向から Broombridge 出力を生成しています ##

Web ベースのフロントエンドの EMSL 矢印の使用を開始するには、 [ここで](https://arrows.emsl.pnnl.gov/api/qsharp_chem)ブラウザーに移動します。 

> [!NOTE]
> Web ブラウザーで EMSL 矢印を実行するには、JavaScript を有効にする必要があります。 ブラウザーで JavaScript を有効にする方法については、こちらの [手順](https://www.enable-javascript.com/) を参照してください。 

最初に、[クエリ] ボックスに「分子」と入力します。 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

多くの分子は、"1, 3, Trimethylxanthine" ではなく "caffeine" のように、普通名で入力できます。 

次に、「」というボタンをクリックし ``theory{qsharp_chem}`` ます。 これにより、Broombridge YAML 形式で出力をエクスポートするよう実行に指示する命令が、クエリボックスに追加されます。 

ここで、時計をオンに ``Run Arrows`` します。 入力のサイズによっては、この処理に時間がかかることがあります。 また、特定のモデルが既に計算されている場合は、データベース内での検索にのみ使用されるため、非常に高速に実行できます。 どちらの場合も、入力によって指定されたデッキに対する NWChem の特定の実行に関する大量の情報を含む新しいページが表示されます。 

次のヘッダーから始まるセクションから、Broombridge YAML ファイルをダウンロードして保存することができます。 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

[オン] ``download`` をクリックすると、ローカルコピーがなどの一意のファイル名で保存され ``qsharp_chem48443.yaml`` ます (特定の名前は実行ごとに異なります)。 その後、次のようにしてこのファイルをさらに処理できます。 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
リソースの数を取得します。 

EMSL の矢印のスタートページにあるタブからアクセスできる3D 分子 builder を利用でき ``Arrows Entry - 3D Builder`` ます。 表示されている分子の [JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 画像をクリックすると、それを編集できるようになります。 原子を移動し、原子をドラッグして、分子間の距離が変化したり、原子を追加/削除したりすることができます。これらの選択のそれぞれに対して、 ``theory{qsharp_chem}`` [クエリ] ボックスに追加した後、Broombridge YAML スキーマのインスタンスを生成し、Quantum 化学ライブラリを使用してさらに詳細な調査を行うことができます。 
