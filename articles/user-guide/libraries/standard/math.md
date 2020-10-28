---
title: 標準ライブラリの数値演算 Q#
description: 組み込みデータ型で使用される標準ライブラリの典型的な数学関数について説明 Q# します。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692057"
---
# <a name="classical-mathematical-functions"></a>古典数学関数 #

これらの関数は、主に、組み込みのデータ型、、およびを操作するために使用され Q# `Int` `Double` `Range` ます。

この <xref:Microsoft.Quantum.Intrinsic.Random> 操作には署名があり `(Double[] => Int)` ます。
このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスをとして配列に返し `Int` ます。
特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。 0に等しい n 個の配列要素は無視され、そのインデックスは返されません。
配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。
