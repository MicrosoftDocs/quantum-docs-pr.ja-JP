---
title: メディアの Readme
description: イメージのアップロードに関するヒント
author: geduardo
ms.author: v-edsanc
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: bf28f57820e95bbbf81f5ac7ade582d89b945a26
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834535"
---
# <a name="readme"></a>README
**重要**: ダークモードでイメージを正しく表示するには、ohp シートを使用しないようにする必要があります。
- .Jpg ファイルの場合、ファイル形式は透過的な要素をサポートしていないため、何もする必要はありません。
- .Png ファイルの場合は、白の背景を追加するか、アルファチャネルの値を100に変更する必要があります。 Windows でこれを行う最も簡単な方法は、ファイルをペイントで開いて、元のファイルを上書き保存することです。
- Svg ファイルの場合は、最も低いレイヤーに白い四角形を追加する必要があります。 これを行うには、Inkscape を使用します。
  - Svg ファイルを開きます。
  - 四角形メーカーツールを選択し、元の図の上に白い四角形を描画します。
  - [オブジェクトの選択と変換] ツールを選択するには、黒い矢印をクリックするか、F1 キーを押します。
  - 四角形が選択されている状態で、ツールバー要素内をクリックして [下まで選択] をクリックします。
  - マウスまたは方向キーを使用して四角形を調整します。
