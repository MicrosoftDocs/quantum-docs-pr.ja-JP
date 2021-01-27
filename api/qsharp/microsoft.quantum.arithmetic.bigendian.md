---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian ディアンユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843389"
---
# <a name="bigendian-user-defined-type"></a>BigEndian ディアンユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ビッグエンディアンの順序で符号なし整数をエンコードするレジスタ。 Qubit with index は、 `0` 符号なし整数の最上位ビットをエンコードします。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>解説

`BigEndian` `BE` ドキュメントでは、のように省略します。