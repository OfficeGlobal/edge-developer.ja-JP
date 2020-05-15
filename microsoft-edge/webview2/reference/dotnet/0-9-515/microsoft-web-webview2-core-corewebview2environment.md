---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: be8f475d4c1a886a92b46144f2bffde2d49dc9d4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654479"
---
# WebView2 クラス (CoreWebView2Environment クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

これは、WebView2 環境を表します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[この文字列](#browserversionstring) | CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。
[新機能をご利用いただけます](#newbrowserversionavailable) | 新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。
[CreateAsync](#createasync) | インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。
[CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) | 新しい WebView を非同期的に作成します。
[CreateWebResourceResponse](#createwebresourceresponse) | 新しい web リソース応答オブジェクトを作成します。

WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。 異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。

## Members

#### この文字列 

CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。

> パブリック文字列の[文字列](#browserversionstring)

これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。 チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。

#### 新機能をご利用いただけます 

新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。

> パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)

新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。 このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。 インストールされている Edge で実行されていない場合、イベントは発生しません。

ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。 または、単に、アプリを再起動するようにユーザーに求めます。

#### CreateAsync 

インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。

> パブリック async タスク< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [createasync](#createasync)(string browserexecutablefolder、文字列 userdatafolder、CoreWebView2EnvironmentOptions options)

##### パラメーター
* `browserExecutableFolder` 埋め込まれた端を含むフォルダーの相対パス。 

* `userDataFolder` userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。 

* `options` WebView2 環境の作成に使用するオプション。

#### CreateCoreWebView2ControllerAsync 

新しい WebView を非同期的に作成します。

> パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)

parentWindow は、WebView を表示して入力を受け取る HWND です。 WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。 兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。

アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。 何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。

#### CreateWebResourceResponse 

新しい web リソース応答オブジェクトを作成します。

> パブリック HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)

ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。 空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。 その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。
