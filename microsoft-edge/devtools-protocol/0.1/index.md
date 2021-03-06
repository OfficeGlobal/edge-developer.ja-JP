---
description: Microsoft Edge DevTools プロトコルバージョン0.1 のリリースノート
title: DevTools プロトコルバージョン0.1 リリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 3c0648467c20572a525fe257788068966efd193c
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104736"
---
# DevTools プロトコルバージョン0.1 リリースノート

> [!NOTE]
> Microsoft Edge の DevTools プロトコルは、 [windows 10 年4月の2018更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降の [windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。

Microsoft **Edge Devtools プロトコル** のバージョン0.1 には、新しいスタンドアロンの [Microsoft Edge devtools プレビュー](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) アプリで EdgeHTML instrumentation と基本的なリモートデバッグをテストするための早期プレビューが用意されています。 そのため、 [windows 10 の2018年4月の更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) またはそれ以降の [windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドを実行している必要があります。

DevTools プロトコルの背後にあるゴールは、次の3つになります。

 - Microsoft Edge にアタッチするための DevTools アプリ用のパブリック API を提供する
 - DevTools 機能の access を外部ツールクライアントに拡張する
 - Microsoft Edge を実行している Windows 10 デバイスの範囲でリモートデバッグを有効にする 

この予備リリースでは、ブレークポイントの設定、コードのステップ実行、スタックトレースの表示などの基本的なデバッグ機能を提供します。 エッジ DevTools UI では、 [**デバッガー**](../../devtools-guide/debugger.md) パネルで使用可能な機能、マイナスキャッシュ検査 (Web ストレージ、Service Worker、cache API、IndexedDB) に変換されます。 

今後のリリースでは、さらにデバッガーの機能が追加されます。その後に、他の [Devtools](../../devtools-guide.md) パネルの電源計装が追加されます。
