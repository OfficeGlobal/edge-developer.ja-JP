---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: c3ba6ac3a2478861abb7b26e726a9cbd606b0eb9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654337"
---
# インターフェイス ICoreWebView2ContentLoadingEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

ContentLoading イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsErrorPage](#get_iserrorpage) | 読み込まれたコンテンツがエラーページの場合は True です。
[get_NavigationId](#get_navigationid) | ナビゲーションの ID です。

## Members

#### get_IsErrorPage 

読み込まれたコンテンツがエラーページの場合は True です。

> パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL * IsErrorPage)

#### get_NavigationId 

ナビゲーションの ID です。

> パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 * navigation_id)
