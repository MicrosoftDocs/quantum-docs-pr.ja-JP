---
title: 'Q # 標準ライブラリ-math |Microsoft Docs'
description: 'Q # 標準ライブラリ-数値演算'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184459"
---
# <a name="classical-mathematical-functions"></a>古典数学関数 #

これらの関数は、主に Q # の組み込みデータ型 `Int`、`Double`、および `Range`を操作するために使用されます。

<xref:microsoft.quantum.intrinsic.random> 操作にはシグネチャ `(Double[] => Int)`があります。
このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスを `Int`として配列に返します。
特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。 0に等しい n 個の配列要素は無視され、そのインデックスは返されません。
配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。