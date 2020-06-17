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
ms.openlocfilehash: c715a195a52d95e91095e006c71e50de46dc05e4
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699039"
---
# インターフェイス ICoreWebView2WebResourceRequest 

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

WebResourceRequested イベントと共に使用される HTTP 要求。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Content](#get_content) | HTTP 要求メッセージ本文をストリームとして送信します。
[get_Headers](#get_headers) | 変更可能な HTTP 要求ヘッダー。
[get_Method](#get_method) | HTTP 要求メソッド。
[get_Uri](#get_uri) | 要求 URI。
[put_Content](#put_content) | Content プロパティを設定します。
[put_Method](#put_method) | Method プロパティを設定します。
[put_Uri](#put_uri) | Uri プロパティを設定します。

## Members

#### get_Content 

HTTP 要求メッセージ本文をストリームとして送信します。

> パブリック HRESULT [get_Content](#get_content)(IStream * * コンテンツ)

データの投稿はここにあります。 ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。 UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)

#### get_Headers 

変更可能な HTTP 要求ヘッダー。

> パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) * * ヘッダー)

#### get_Method 

HTTP 要求メソッド。

> パブリック HRESULT [get_Method](#get_method)(LPWSTR * メソッド)

#### get_Uri 

要求 URI。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### put_Content 

Content プロパティを設定します。

> パブリック HRESULT [put_Content](#put_content)(IStream * コンテンツ)

#### put_Method 

Method プロパティを設定します。

> パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)

#### put_Uri 

Uri プロパティを設定します。

> パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)
