---
title: 標準ライブラリの数値演算 Q#
description: 組み込みデータ型で使用される標準ライブラリの典型的な数学関数について説明 Q# します。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868425"
---
# <a name="classical-mathematical-functions"></a>古典数学関数 #

これらの関数は、主に、組み込みのデータ型、、およびを操作するために使用され Q# `Int` `Double` `Range` ます。

この <xref:microsoft.quantum.intrinsic.random> 操作には署名があり `(Double[] => Int)` ます。
このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスをとして配列に返し `Int` ます。
特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。 0に等しい n 個の配列要素は無視され、そのインデックスは返されません。
配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。
