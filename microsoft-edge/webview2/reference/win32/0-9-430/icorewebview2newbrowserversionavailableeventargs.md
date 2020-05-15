---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 3ac37f7d90fc03214381b991c8becae602bac738
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654403"
---
# インターフェイス ICoreWebView2NewBrowserVersionAvailableEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

新しい参照サーバーの available イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_NewVersion](#get_newversion) | 現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。

## Members

#### get_NewVersion 

現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。

> パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR * NewVersion)
