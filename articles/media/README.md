---
title: メディアの Readme
description: イメージのアップロードに関するヒント
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: a4922e28a8fc5ddfb4cbc80302e23869154234d8
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024187"
---
# <a name="readme"></a><span data-ttu-id="c5505-103">README</span><span class="sxs-lookup"><span data-stu-id="c5505-103">README</span></span>
<span data-ttu-id="c5505-104">**重要**: ダークモードでイメージを正しく表示するには、ohp シートを使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5505-104">**IMPORTANT**: to have the images rendering properly in dark mode you must avoid transparencies.</span></span>
- <span data-ttu-id="c5505-105">.Jpg ファイルの場合、ファイル形式は透過的な要素をサポートしていないため、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5505-105">For .jpg files you don't need to do anything since the file format doesn't support transparent elements.</span></span>
- <span data-ttu-id="c5505-106">.Png ファイルの場合は、白の背景を追加するか、アルファチャネルの値を100に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5505-106">For .png files you must add a white background or change the value of the alpha channel to 100.</span></span> <span data-ttu-id="c5505-107">Windows でこれを行う最も簡単な方法は、ファイルをペイントで開いて、元のファイルを上書き保存することです。</span><span class="sxs-lookup"><span data-stu-id="c5505-107">The easiest way to do this in Windows is by opening the file in Paint and saving, overwritting the original file.</span></span>
- <span data-ttu-id="c5505-108">Svg ファイルの場合は、最も低いレイヤーに白い四角形を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5505-108">For .svg files you must add a white rectangle in the lowest layer.</span></span> <span data-ttu-id="c5505-109">これを行うには、Inkscape を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5505-109">You can do this with Inkscape:</span></span>
  - <span data-ttu-id="c5505-110">Svg ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5505-110">Open the .svg file.</span></span>
  - <span data-ttu-id="c5505-111">四角形メーカーツールを選択し、元の図の上に白い四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="c5505-111">Select the square maker tool and draw a white rectangle on top of the original figure.</span></span>
  - <span data-ttu-id="c5505-112">[オブジェクトの選択と変換] ツールを選択するには、黒い矢印をクリックするか、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c5505-112">Select the tool "Select and transform objects" by clicking in the dark arrow or pressing F1.</span></span>
  - <span data-ttu-id="c5505-113">四角形が選択されている状態で、ツールバー要素内をクリックして [下まで選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5505-113">While having the rectangle selected, click in the toolbar element "Lower selection to bottom (End)".</span></span>
  - <span data-ttu-id="c5505-114">マウスまたは方向キーを使用して四角形を調整します。</span><span class="sxs-lookup"><span data-stu-id="c5505-114">Adjust the rectangle with the mouse or the arrow keys.</span></span>
