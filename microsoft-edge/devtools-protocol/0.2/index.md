---
description: Microsoft Edge DevTools プロトコルバージョン0.2 のリリースノート
title: Microsoft Edge DevTools プロトコルバージョン0.2 リリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: c4959d2905f95c2bcf98cb78ad67bb88ecfec959
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104743"
---
# DevTools プロトコルバージョン0.2 リリースノート

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763) 以降の [windows Insider Preview](https://insider.windows.com/getting-started/) ビルドでのみ動作します。

Microsoft **Edge Devtools プロトコル** のバージョン0.2 には、EdgeHTML インストルメンテーションと基本的なリモートデバッグをテストするためのプレビューが用意されています。新しいスタンドアロンの [Microsoft Edge devtools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリ。 そのため、 [windows 10 年 2018 10 月の更新プログラム](/windows/uwp/whats-new/windows-10-build-17763) またはそれ以降の [windows Insider Preview](https://insider.windows.com/getting-started/) ビルドを実行している必要があります。

DevTools プロトコルの背後にあるゴールは、次の3つになります。

 - Microsoft Edge にアタッチするための DevTools アプリ用のパブリック API を提供する
 - DevTools 機能の access を外部ツールクライアントに拡張する
 - Microsoft Edge を実行している Windows 10 デバイスの範囲でリモートデバッグを有効にする 

DevTools プロトコルのバージョン0.2 には、スタイルとレイアウトのための新しいドメインが含まれています (読み取り専用) デバッグと本体の Api に加えて、バージョン0.1 で導入されたコアスクリプトのデバッグ機能も含まれています。 Edge の DevTools UI では、これは [**要素**](../../devtools-guide/elements.md)、 [**コンソール**](../../devtools-guide/console.md) 、 [**デバッガー**](../../devtools-guide/debugger.md)  パネルで利用できる機能に変換されます。
