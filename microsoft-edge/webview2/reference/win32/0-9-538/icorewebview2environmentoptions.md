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
ms.openlocfilehash: 3de9cd454f693179a0d1dc63e6ccb1332f80c875
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698996"
---
# インターフェイス ICoreWebView2EnvironmentOptions 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

WebView2 環境の作成に使用するオプション。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_AdditionalBrowserArguments](#get_additionalbrowserarguments) | WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。
[get_Language](#get_language) | WebView が実行される既定の言語。
[get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion) | Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。
[put_AdditionalBrowserArguments](#put_additionalbrowserarguments) | AdditionalBrowserArguments プロパティを設定します。
[put_Language](#put_language) | Language プロパティを設定します。
[put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion) | Target互換の Sion を設定します。

WebView2EnvironmentOptions には既定の実装が用意されています。

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## Members

#### get_AdditionalBrowserArguments 

WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。

> パブリック HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR * 値)

これらは、コマンドラインの一部としてブラウザープロセスに渡されます。 ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。 コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。 次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。 これらのスイッチは、指定した場合でも無視されます。 同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。 無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。 およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。 アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。 一部の機能は内部で無効にされているため、有効にすることはできません。 指定したスイッチの解析に失敗した場合、それらは無視されます。 既定では、追加のフラグなしでブラウザープロセスを実行します。

#### get_Language 

WebView が実行される既定の言語。

> パブリック HRESULT [get_Language](#get_language)(LPWSTR * 値)

これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。 また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。 この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。

#### get_TargetCompatibleBrowserVersion 

Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。

> パブリック HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR * 値)

これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。 この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。 対象となるのは、のバージョン部分だけです。 チャネルのサフィックス (存在する場合) は無視されます。 実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。 互換性が保証されるだけであることが保証されます。 ICoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。

#### put_AdditionalBrowserArguments 

AdditionalBrowserArguments プロパティを設定します。

> パブリック HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR 値)

#### put_Language 

Language プロパティを設定します。

> パブリック HRESULT [put_Language](#put_language)(LPCWSTR 値)

#### put_TargetCompatibleBrowserVersion 

Target互換の Sion を設定します。

> パブリック HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR 値)
