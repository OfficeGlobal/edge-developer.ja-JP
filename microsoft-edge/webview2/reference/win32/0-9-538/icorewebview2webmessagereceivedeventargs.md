---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c7d3d03fc1a0d53db403dab6c91dcdcf5ad6fd28
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699070"
---
# インターフェイス ICoreWebView2WebMessageReceivedEventArgs 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

WebMessageReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Source](#get_source) | この web メッセージを送信したドキュメントの URI です。
[get_WebMessageAsJson](#get_webmessageasjson) | このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

## Members

#### get_Source 

この web メッセージを送信したドキュメントの URI です。

> パブリック HRESULT [get_Source](#get_source)(LPWSTR * Source)

#### get_WebMessageAsJson 

このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。

> パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR * webMessageAsJson)

JavaScript オブジェクトを使って通信する場合に使用します。

たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

> パブリック HRESULT [Trygetwebmessageasstring](#trygetwebmessageasstring)(LPWSTR * webmessageasstring)

投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。 これは、単純な文字列を使って通信する場合に使用します。

たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
