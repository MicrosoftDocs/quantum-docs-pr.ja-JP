---
title: 'Q # 標準ライブラリの数値演算'
description: '組み込みデータ型で使用される Q # 標準ライブラリの典型的な数学関数について説明します。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275656"
---
# <a name="classical-mathematical-functions"></a>古典数学関数 #

これらの関数は、主に Q # の組み込みデータ型、、およびを操作するために使用され `Int` `Double` `Range` ます。

この <xref:microsoft.quantum.intrinsic.random> 操作には署名があり `(Double[] => Int)` ます。
このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスをとして配列に返し `Int` ます。
特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。 0に等しい n 個の配列要素は無視され、そのインデックスは返されません。
配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。
