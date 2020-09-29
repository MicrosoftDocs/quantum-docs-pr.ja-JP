---
title: Q# と Binder を使用した開発
description: Binder を使用して Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836559"
---
# <a name="develop-with-no-locq-and-binder"></a>Q# と Binder を使用した開発

Binder を使用して、Jupyter Notebook をオンラインで実行し、共有することができます。

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Microsoft QDK サンプルでの Binder の使用

Microsoft QDK サンプルを使用するように Binder を自動的に構成するには、次のようにします。

1. ブラウザーを開いて､ https://aka.ms/try-qsharp を実行します。
1. **Quantum Development Kit Samples** ランディング ページで、 **[Q# notebook]** をクリックして、IQ# を使用して独自の量子アプリケーション ノートブックを記述する方法を学習します。

![QDK ランディング ページ](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>独自のノートブックとリポジトリで Binder を使用する

GitHub リポジトリに既にノートブックがある場合は、リポジトリと連携するように Binder を構成できます。

1. リポジトリのルートに *Dockerfile* という名前のファイルがあることを確認します。 このファイルには、少なくとも次の行が含まれている必要があります。

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > IQ# の最新バージョンは、[リリース ノート](xref:microsoft.quantum.relnotes)で確認できます。

    Dockerfile 作成の詳細については、[Dockerfile リファレンス](https://docs.docker.com/engine/reference/builder/)をご覧ください。

2. ブラウザーを開いて、[mybinder.org](https://mybinder.org) を表示します。
3. **GitHub URL** としてリポジトリ名 (たとえば *MyName/MyRepo*) を入力し、 **[launch]** をクリックします。

![MyBinder フォーム](~/media/mybinder.png)
    
## <a name="next-steps"></a>次のステップ

これで、Binder 環境の設定が完了したので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。
