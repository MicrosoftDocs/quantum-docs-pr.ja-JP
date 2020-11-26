---
uid: Microsoft.Quantum.AmplitudeAmplification
title: AmplitudeAmplification 名前空間
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: f265f1f8b41513f9201a758f85451e768b7564e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191416"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>AmplitudeAmplification 名前空間

この名前空間には、振幅増幅を実行するための関数と操作が含まれています。



## <a name="description"></a>説明

無関係の部分反射を使用した振幅増幅は、ここで実装されている振幅増幅の最も一般的な形式です。

これは、操作 AmpAmpObliviousByReflectionPhases を通じて呼び出されます。

これには、との2つのレジスタがあり `ancillaRegister` `systemRegister` ます。

これは `ReflectionOracle` 、レジスタにのみ作用する型の反射に対して、2つの oracles を受け入れ `ancillaRegister` ます。

これは、 `ObliviousOracle` 両方のレジスタに共同で動作する、型の無関係の特殊な振幅増幅を許可します。

への入力状態は、 `ancillaRegister` 最初のリフレクション演算子 $I-2 \ k {s} \ bra {s} $ という一意の $-$1 eigenstate と想定されます。

ターゲットクォンタムの状態に関する反射は、多くの場合、計算ベース $ \ket{0\cdots 0} $ からその状態を準備する oracle へのアクセスを前提として実装されます。

これらの oracles の規則では、2つのレジスタが必要です。1つはシングル qubit レジスタ、もう1つはフロントシャー `flagQubit` ドレジスタレジスタに登録します。

型の oracle は、 `StateOracle` 両方のレジスタに共同で動作し、レジスタ内の $ \ket $ によってフラグが設定されたターゲット状態を、 {1} `flagQubit` いくつかの実際の振幅で作成します。

`ReflectionOracle`このフラグの状態に関するリフレクションは、操作によって生成され `TargetStateReflectionOracle` ます。

への `ReflectionOracle` 入力状態に関するリフレクション `ancillaRegister` は、を反転することによって生成され、$ \ket{0\cdots 0} $ と ReflectionStart () を反映します。

型の oracle は、 `DeterministicStateOracle` レジスタに対して動作し、 `qubitState` フラグなしでターゲットの状態を正確に作成します。

`AmpAmpObliviousByOraclePhases` は、反射ではなく oracles とを受け入れる無関係の振幅増幅のバージョンです `StateOracle` `ObliviousOracle` 。

振幅増幅は特殊なケースで、無関係の振幅増幅であることに注意してください。 `ObliviousOracle` は id 演算子で、システム qubits は存在しません。つまり、 `systemRegister` は空です。

これは、操作とを通じて呼び出され `AmpAmByReflectionPhases` `AmpAmpByOraclePhases` ます。

Grover search の標準的なケースでの部分的な反射のフェーズは、AmpAmpPhasesStandard 関数によって提供されます。

たとえば、AmpAmpByOracle >-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases という依存関係があります。