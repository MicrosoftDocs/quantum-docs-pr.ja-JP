---
title: クォンタムコンピューティング用語集 |Microsoft Docs
description: クォンタム用語の用語集
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ce15fee2be68d41f0b806be50320b562a749c3b7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442539"
---
# <a name="quantum-computing-glossary"></a>クォンタムコンピューティング用語集

|期間|定義|
|-------------|----------|
|Adjoint|操作の複雑な共役の転置。 ユニタリ演算子を実装する操作の場合、adjoint は演算の逆になります。|
|呼び出し可能|操作と関数は、総称して*呼び出し*を実行できるものとして知られています。|
|標準|準備で定義されているロジックに基づいて、Q # で定義された操作と関数。 標準ライブラリの実装は、ターゲットコンピューターに対しては依存しません。|
|Clifford グループ|Bloch 球の octants を占有する操作のセット。 これには、`X`、`Y`、`Z`、`H`、および `S`|
|た|ターゲット操作のイネーブラーとして1つ以上の qubits を受け取るクォンタム操作。|
|Dirac 表記|クォンタム状態の短縮形。 詳細については、「 [Dirac 表記](xref:microsoft.quantum.concepts.dirac)」を参照してください。|
|Eigenvalues と固有ベクトル|詳細については、[詳細マトリックス](xref:microsoft.quantum.concepts.matrix-advanced)に関するセクションを参照してください。|
|EPR ペア|[ベルの状態](https://en.wikipedia.org/wiki/Bell_state)とも呼ばれます。|
|発展|時間の経過と共に状態がどのように変化するか。 例については、<xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> に関するセクションを参照してください。 |
|Function|Q # 言語での純粋にクラシックルーチン|
| <a id="global-phase"></a>グローバルフェーズ | 1つの複素数の倍数に等しい2つの状態 $e ^ {i\ phi} $ は、グローバルフェーズによって異なります。 ローカルフェーズとは異なり、グローバルフェーズはどのような測定でも監視できません。 詳細については、「 [P# li 測定](xref:microsoft.quantum.concepts.pauli)」を参照してください。 |
|Measurement|Qubit (または qubit のセット) から古典ビットを取得します。 詳細については、「 [Qubit の概念](xref:microsoft.quantum.concepts.qubit)」を参照してください。|
|変更可能|値が作成後に変更される可能性がある変数。|
|名前空間|関連する名前 (通常は操作、関数、型) のコレクションのラベル。 たとえば、名前空間[`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation)は、初期状態の準備に役立つ標準ライブラリで定義されているすべてのシンボルをラベル付けします。|
|Operation|Q # でのクォンタム実行の基本単位。 これは、C や C++、Python の関数、または C# や Java の静的メソッドとほぼ同じものです。|
|オペレーターアプリケーション|クォンタム操作を実行しています。 通常、これは、現在の状態ベクトルに対して、通常は、ユニタリ行列を適用します。 詳細については、「[クォンタムの概念の概要」を](xref:microsoft.quantum.concepts.intro)参照してください。|
|Oracle|実行時にクォンタムアルゴリズムにデータ依存の情報を提供するサブルーチン。 通常、目標は、法則内の入力に対応する出力の法則を提供することです。   |
|部分アプリケーション|すべての必須パラメーターを指定せずに、関数または操作を呼び出します。 は、今後のアプリケーション中に指定された不足パラメーターのみを必要とする新しい呼び出し可能を返します。|
|P# li 演算子|`X`、`Y`、および `Z` クォンタムゲートです。|
|準備|Q # レベルではなく、個々のターゲットコンピューターによって定義されたプリミティブおよび従来の操作と関数のセット。|
|クォンタム回線|クォンタムコンピューターのプログラムの表現。 詳細については、<xref:microsoft.quantum.concepts.circuits> に関するセクションを参照してください。|
|クォンタムの状態|システム内の qubits の表現。 これは、通常、複合列ベクターとして表されます。 詳細については、<xref:microsoft.quantum.concepts.vectors> を参照してください。 |
|qubit|クォンタムストレージの単位。 詳細については、<xref:microsoft.quantum.concepts.qubit> に関するセクションを参照してください。|
|繰り返し-成功まで|見込みが成功するクォンタムアルゴリズム。 エラーが発生すると、ルーチンは成功するまで (または制限に達した時点で) 再試行します。 |
|ソフトウェアスタック|全古典および quantum ソフトウェアの完全なセットに加えて、quantum コンピューターを運用するために必要なコンパイラ、シミュレーター、およびランタイムがあります。 詳細については、<xref:microsoft.quantum.concepts.software-stack> に関するセクションを参照してください。 |
|ターゲットコンピューター|ハードウェアまたはシミュレーションの抽象的なクォンタムプログラムを下げるコンパイルターゲット。 これには通常、ゲートの置換、エラー修正のためのエンコード、ジオメトリレイアウトなど、さまざまな目的のための再書き込みが含まれます。|
|タプル|コンマで区切られた型は、かっこを使用してグループ化されます。 |
|ユーザー定義型|1つの単位として参照される組み込みまたは以前に定義された型のコレクション。|

