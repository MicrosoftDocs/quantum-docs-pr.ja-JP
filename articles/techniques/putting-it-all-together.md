---
title: 'Q # の手法-すべてをまとめる |Microsoft Docs'
description: 'Q # の手法-まとめ'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183269"
---
# <a name="putting-it-all-together-teleportation"></a>すべてをまとめます。 #
「[クォンタム回線](xref:microsoft.quantum.concepts.circuits)」で定義されている例に戻りましょう。 これまでに学習した概念を説明するために、これを使用します。 ここでは、理論に習熟している方について説明し、その後に Q # でのコード実装のチュートリアルを示します。 

## <a name="quantum-teleportation-theory"></a>クォンタムの受付: 理論
Quantum の電話は、特定の場所の qubit から別の場所にある qubit に ('__message__' と呼ばれる) 不明なクォンタムの状態を送信する手法です (これらの qubit を '__ここ__'__と ' the ' と__呼びます)。それぞれ)。 Dirac 表記を使用して、__メッセージ__をベクトルとして表すことができます。 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

$ \ Alpha $ と $ \ ベータ $ の値がわからないため、__メッセージ__qubit の状態は不明です。

### <a name="step-1-create-an-entangled-state"></a>手順 1: ありの状態を作成する
__メッセージ__を送信するには、__ここ__に qubit を入力する必要が__あります。__ これを実現するには、Hadamard ゲートを適用し、その後に CNOT gate を適用します。 これらのゲート操作の背後にある数学を見てみましょう。

__ここ__では qubits から開始し、__両方とも $__ \ket{0}$ 状態にします。 これらの qubits を entangling した後、次のような状態になります。

$ $ \ket{\phi ^ +} = \ frac{1}{\ sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>手順 2: メッセージを送信する
__メッセージ__を送信するには、まず、__メッセージ__QUBIT を含む cnot gate を適用し、__次__に入力として qubit を適用します (この例では、__メッセージ__qubit がコントロールで、__ここ__ではターゲット qubit になります)。 この入力状態は、次のように記述できます。

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\ frac{1}{\ sqrt{2}} (\ket{00} + \ket{11})) $ $

次のように展開されます。

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

なお、コントロール qubit が1の場合、CNOT gate はターゲットの qubit を反転します。 たとえば、$ \ket{000}$ を入力すると、最初の qubit (コントロール) は0になり、変更は行われません。 ただし、最初の qubit が 1 (たとえば、$ \ket{100}$ の入力) である場合は、 このインスタンスでは、2番目の qubit (ターゲット) が CNOT gate によって反転されているため、出力は $ \ket{110}$ になります。

ここでは、CNOT gate が前述の入力を操作した後の出力について考えてみましょう。 結果は次のとおりです。

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

__メッセージ__を送信する次の手順では、Hadamard gate を__メッセージ__qubit (各用語の最初の qubit) に適用します。 

リマインダーとして、Hadamard ゲートは次のことを行います。

Input (入力) | 出力
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1}) $

上記の出力の各用語の最初の qubit に Hadamard ゲートを適用すると、次の結果が得られます。

$ $ \frac{\alpha}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\ sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

各用語には $2/frac{1}{/sqrt{2}} $ 要因があることに注意してください。 次の結果を返すことができます。

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

$ & Frac{1}{2}$ factor は各用語に共通であるため、角かっこの外側に移動できます。

$ $ \ frac{1}{2}\ big [\ alpha (\ket{0} + \ket{1}) \ket{00} +-alpha (\ket{0} + \ket{1}) \ket{11} +/beta (\ket{0}-\ket{1}) \ket{10} + \ ベータ (\ket{0}-\ket{1}) \ket{01}\ big] $ $

次に、各用語の角かっこを掛けて、次のようにします。

$ $ \ frac{1}{2}\ big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\ big] $ $

### <a name="step-3-measure-the-result"></a>手順 3: 結果を測定する

__ここ__ __では__、この__ような測定__値__があるため__、その状態に影響を与えます。 1番目と2番目の qubit (__メッセージ__と__ここで__) を測定する__場合は、__ このプロパティによってどのような状態になっているかを知ることができます。 

* 測定して結果00を取得すると、法則は折りたたまれ、この結果と一致する用語のみが残ります。 $ \Alpha\ket{000} + \beta\ket{001}$ です。 これは、$ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $ にリファクタリングできます。 したがって、1番目と2番目の qubit を00として測定した場合、3番目の qubit__が state__$ (\alpha\ket{0} + \beta\ket{1}) $ にあることがわかります。
* 結果01を測定して取得した場合、法則は折りたたまれ、この結果と一致する用語のみが残ります。 $ \Alpha\ket{011} + \beta\ket{010}$ です。 これは、$ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $ にリファクタリングできます。 したがって、1番目と2番目の qubit を01として測定した場合、3番目の qubit__が state__$ (\alpha\ket{1} + \beta\ket{0}) $ にあることがわかります。
* 評価して結果10を取得すると、法則は折りたたまれ、この結果との間には一致する語句だけが残ります。 これは $ \alpha\ket{100}-\beta\ket{101}$ です。 これは、$ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $ にリファクタリングできます。 したがって、1番目と2番目の qubit を10に測定した場合、3番目の qubit__が state__$ (\alpha\ket{0}-\beta\ket{1}) $ にあることがわかります。
* 結果11を測定して取得した場合、法則は折りたたまれ、この結果と一致する用語のみが残ります。 これは $ \alpha\ket{111}-\beta\ket{110}$ です。 これは、$ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $ にリファクタリングできます。 したがって、1番目と2番目の qubit を11に測定した場合、3番目の qubit__が state__$ (\alpha\ket{1}-\beta\ket{0}) $ にあることがわかります。

### <a name="step-4-interpret-the-result"></a>手順 4: 結果を解釈する

リマインダーとして、送信する元の__メッセージ__は次のようになりました。

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

受信状態が想定されているものであるように、この状態に__ある__qubit を取得する必要があります。 

* 測定して00の結果を得た場合、3番目の qubit は state $ (\alpha\ket{0} + \beta\ket{1}) $ に__あり__ます。 これは目的の__メッセージ__であるため、変更は必要ありません。
* を測定し、結果を01にした場合、3番目の qubit は state $ (\alpha\ket{1} + \beta\ket{0}) $ に__あり__ます。 これは目的の__メッセージ__とは異なりますが、NOT gate を適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ になります。
* 測定し、結果が10の場合、3番目の qubit は state $ (\alpha\ket{0}-\beta\ket{1}) $ に__あり__ます。 これは目的の__メッセージ__とは異なりますが、Z ゲートを適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ になります。
* 測定し、結果が11の場合、3番目の qubit は state $ (\alpha\ket{1}-\beta\ket{0}) $ に__あり__ます。 これは目的の__メッセージ__とは異なりますが、NOT ゲートの後に Z ゲートを適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ が適用されます。

まとめると、測定し、最初の qubit が1の場合、Z ゲートが適用されます。 測定し、2番目の qubit が1の場合、NOT gate が適用されます。

### <a name="summary"></a>Summary
次に示すのは、電話を実装するテキスト帳のクォンタム回線です。 左から右に移動すると、次のように表示されることがあります。
- 手順 1: Hadamard ゲートと CNOT gate を適用__して、__ __ここ__に Entangling します。
- 手順 2: CNOT ゲートと Hadamard gate を使用して__メッセージ__を送信する。
- 手順 3: 1 番目と2番目の qubits、__メッセージ__、__およびの__測定値を取得します。
- 手順 4: 手順 3. で測定の結果に応じて、NOT gate または Z ゲートを適用します。

![' テレポート (msg: Qubit、: Qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>クォンタム受付: コード

Quantum の回線を使用しています。

![' テレポート (msg: Qubit、: Qubit): Unit '](~/media/teleportation.svg)

これで、この量子回線の各ステップを Q # に変換できるようになりました。

### <a name="step-0-definition"></a>手順 0: 定義
電話をかけるときは、送信する__メッセージ__と送信する場所 (ここに__あり__ます) を把握しておく必要があります。 このため、最初に新しいテレポート操作を定義します。これには、引数として2つの qubits、`msg` と `there`を指定します。

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

また、`using` ブロックで実現する qubit `here` を割り当てる必要があります。

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>手順 1: ありの状態を作成する
次に、@"microsoft.quantum.primitive.h" と @"microsoft.quantum.primitive.cnot" の操作を使用して、`here` と `there` の間にありのペアを作成できます。

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>手順 2: メッセージを送信する
次に、$ & $H $ ゲートを使用して、メッセージ qubit を移動します。

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>手順 3 & 4: 結果の測定と解釈
最後に、`if` ステートメントで示されているように、@"microsoft.quantum.primitive.m" を使用して測定を実行し、必要なゲート操作を実行して目的の状態を取得します。

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

これにより、`here`の割り当てを解除し、本文を終了して、操作を終了できるようになります。

```qsharp
    }
}
```
