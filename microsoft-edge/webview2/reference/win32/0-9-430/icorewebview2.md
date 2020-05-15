---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 77eb48773a963775e00d4dec50368564af5678b0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654587"
---
# インターフェイス ICoreWebView2 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2
  : public IUnknown
```

WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Settings](#get_settings) | ICoreWebView2Settings オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。
[get_Source](#get_source) | 現在の最上位レベルのドキュメントの URI。
[検索](#navigate) | 最上位レベルのドキュメントを指定した URI に移動します。
[NavigateToString](#navigatetostring) | 新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。
[add_NavigationStarting](#add_navigationstarting) | NavigationStarting イベントのイベントハンドラーを追加します。
[remove_NavigationStarting](#remove_navigationstarting) | Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。
[add_ContentLoading](#add_contentloading) | ContentLoading イベントのイベントハンドラーを追加します。
[remove_ContentLoading](#remove_contentloading) | Add_ContentLoading で以前に追加されたイベントハンドラーを削除します。
[add_SourceChanged](#add_sourcechanged) | SourceChanged Source プロパティが変更されたときに発生します。
[remove_SourceChanged](#remove_sourcechanged) | Add_SourceChanged で以前に追加されたイベントハンドラーを削除します。
[add_HistoryChanged](#add_historychanged) | 履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。
[remove_HistoryChanged](#remove_historychanged) | Add_HistoryChanged で以前に追加されたイベントハンドラーを削除します。
[add_NavigationCompleted](#add_navigationcompleted) | NavigationCompleted イベントのイベントハンドラーを追加します。
[remove_NavigationCompleted](#remove_navigationcompleted) | Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。
[add_FrameNavigationStarting](#add_framenavigationstarting) | FrameNavigationStarting イベントのイベントハンドラーを追加します。
[remove_FrameNavigationStarting](#remove_framenavigationstarting) | Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。
[add_ScriptDialogOpening](#add_scriptdialogopening) | Scriptの開始イベントのイベントハンドラーを追加します。
[remove_ScriptDialogOpening](#remove_scriptdialogopening) | Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。
[add_PermissionRequested](#add_permissionrequested) | PermissionRequested されたイベントのイベントハンドラーを追加します。
[remove_PermissionRequested](#remove_permissionrequested) | Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。
[add_ProcessFailed](#add_processfailed) | ProcessFailed イベントのイベントハンドラーを追加します。
[remove_ProcessFailed](#remove_processfailed) | Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。
[AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated) | グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。
[Execuスクリプト](#executescript) | WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。
[CapturePreview](#capturepreview) | WebView が表示されている画像をキャプチャします。
[再](#reload) | 現在のページを再読み込みします。
[PostWebMessageAsJson](#postwebmessageasjson) | 指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。
[PostWebMessageAsString](#postwebmessageasstring) | これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。
[add_WebMessageReceived](#add_webmessagereceived) | このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。
[remove_WebMessageReceived](#remove_webmessagereceived) | Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。
[Calldevon Protocolメソッド](#calldevtoolsprotocolmethod) | 非同期の Devて Protocol メソッドを呼び出します。
[get_BrowserProcessId](#get_browserprocessid) | WebView をホストしているブラウザープロセスのプロセス id。
[get_CanGoBack](#get_cangoback) | ナビゲーション履歴で前のページに移動できる場合は true を返します。
[get_CanGoForward](#get_cangoforward) | ナビゲーション履歴の次のページに移動できる場合は true を返します。
[GoBack](#goback) | ナビゲーション履歴で、WebView を前のページに移動します。
[GoForward](#goforward) | WebView をナビゲーション履歴の次のページに移動します。
[GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver) | DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。
[Stop](#stop) | すべてのナビゲーションと保留中のリソースフェッチを停止します。
[add_NewWindowRequested](#add_newwindowrequested) | NewWindowRequested イベントのイベントハンドラーを追加します。
[remove_NewWindowRequested](#remove_newwindowrequested) | Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。
[add_DocumentTitleChanged](#add_documenttitlechanged) | Documentechanged Lechanged イベントのイベントハンドラーを追加します。
[remove_DocumentTitleChanged](#remove_documenttitlechanged) | Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。
[get_DocumentTitle](#get_documenttitle) | 現在のトップレベルドキュメントのタイトル。
[AddRemoteObject](#addremoteobject) | 指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。
[RemoveRemoteObject](#removeremoteobject) | 名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。
[Opendevツールウィンドウ](#opendevtoolswindow) | WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。
[add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged) | "の場合、要素のプロパティが変更されたときに通知します。
[remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged) | 対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。
[get_ContainsFullScreenElement](#get_containsfullscreenelement) | WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。
[add_WebResourceRequested](#add_webresourcerequested) | WebResourceRequested イベントのイベントハンドラーを追加します。
[remove_WebResourceRequested](#remove_webresourcerequested) | Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。
[add_WindowCloseRequested](#add_windowcloserequested) | WindowCloseRequested イベントのイベントハンドラーを追加します。
[remove_WindowCloseRequested](#remove_windowcloserequested) | Add_WindowCloseRequested で以前に追加されたイベントハンドラーを削除します。
[CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format) | ICoreWebView2:: CapturePreview メソッドで使用されている画像形式。
[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND](#core_webview2_script_dialog_kind) | ICoreWebView2ScriptDialogOpeningEventHandler インターフェイスで使用される JavaScript ダイアログの種類。
[CORE_WEBVIEW2_PROCESS_FAILED_KIND](#core_webview2_process_failed_kind) | ICoreWebView2ProcessFailedEventHandler インターフェイスで使用されているプロセスエラーの種類。
[CORE_WEBVIEW2_PERMISSION_KIND](#core_webview2_permission_kind) | アクセス許可要求の種類。
[CORE_WEBVIEW2_PERMISSION_STATE](#core_webview2_permission_state) | アクセス許可要求に対する応答。
[CORE_WEBVIEW2_WEB_ERROR_STATUS](#core_webview2_web_error_status) | Web ナビゲーションのエラー状態の値。
[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) | Web リソース要求コンテキストの列挙。

## ナビゲーションイベント

ナビゲーションイベントの通常のシーケンスは、NavigationStarting、SourceChanged、ContentLoading、Navigationstarting です。

![dot-inline-dotgraph-1](media/dot-inline-dotgraph-1.png)

これは、同じ NavigationId イベント arg を持つナビゲーションイベント用であることに注意してください。 異なる NavigationId イベント引数を持つナビゲーションイベントは、重複する可能性があります。 たとえば、ナビゲーションを開始したときに NavigationStarting イベントが発生してから別のナビゲーションを開始した場合は、最初のナビで開始される navigationstarting 後に、2番目のナビゲーションのナビゲートが続いて、2番目のナビゲーションについて、該当するすべてのナビゲーションイベントが表示されます。 エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、ContentLoading イベントになることもあります。 HTTP リダイレクトの場合、1つの行に複数の NavigationStarting イベントが存在します。最初の列の後には、IsRedirect フラグが設定されています。

WebView でサブフレーム内のナビゲーションを監視またはキャンセルするには、FrameNavigationStarting を使用します。

## プロセスモデル

WebView2 は、Edge web ブラウザーと同じプロセスモデルを使用します。 ユーザーデータディレクトリを指定する WebView2 の呼び出しプロセスを提供するユーザーセッションの指定したユーザーデータディレクトリごとに、1つの Edge ブラウザープロセスが存在します。 つまり、1つの Edge ブラウザープロセスが複数の通話プロセスを処理している可能性があり、1つの呼び出しプロセスが複数の Edge ブラウザープロセスを使用している可能性があります。

![dot-inline-dotgraph-2](media/dot-inline-dotgraph-2.png)

ブラウザープロセスが表示されない場合は、いくつかのレンダラープロセスが存在します。 これらは、さまざまな WebViews で複数のフレームを処理するために必要に応じて作成されます。 レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebViews でレンダリングされた個別の切断元の数によって異なります。

![dot-inline-dotgraph-3](media/dot-inline-dotgraph-3.png)

クラッシュとハングに対処するには、これらのブラウザーと ProcessFailure イベントを使ってプロセスをレンダリングします。

Close メソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンできます。

## スレッドモデル

WebView2 は、UI スレッドで作成する必要があります。 特にメッセージポンプを持つスレッド。 すべてのコールバックがそのスレッドで発生し、WebView への呼び出しはそのスレッドで実行する必要があります。 他のスレッドから WebView を使うことは安全ではありません。

イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。 つまり、イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックによって reentrantly の実行が開始されません。

## セキュリティ

実行前に、必ず WebView の Source プロパティを確認してください。 Executesscript、PostWebMessageAsJson、Postwebmessageasjson などのメソッドを使って、WebView に情報を送信します。 ナビゲーションを引き起こしているページのページまたはスクリプトをエンドユーザーが操作している場合、WebView が別のページに移動している可能性があります。 同様に、AddScriptToExecuteOnDocumentCreated には細心の注意を払ってください。 今後のすべてのナビゲーションでは、このスクリプトが実行され、特定の元にのみ意図した情報へのアクセスを提供している場合、HTML ドキュメントはすべて、アクセス権を持つ可能性があります。

ExecuteScript の呼び出しの結果を調べるとき、WebMessageReceived イベントが発生した場合、または WebView の HTML ドキュメントから情報を受信するその他のメカニズムを確認する場合は、HTML ドキュメントの URI が予期したとおりであることを確認します。

WebView に送信するメッセージを構築する場合は、PostWebMessageAsJson の使用をお勧めし、JSON ライブラリを使って JSON 文字列パラメーターを構築します。 これにより、JSON 文字列またはスクリプトへのエンコード情報の発生を回避することができます。また、攻撃者によって制御される入力によって、残りの JSON メッセージを変更したり、任意のスクリプトを実行したりすることはできません。

## 文字列型

文字列 out パラメーターは、LPWSTR null で終了された文字列です。 呼び出し先は、、Cotaskmemalloc を使って文字列を割り当てます。 所有権は、呼び出し元に転送され、CoTaskMemFree を使ってメモリを解放することができます。

パラメーター内の文字列は、LPCWSTR null で終了する文字列です。 呼び出し元は、同期関数呼び出しの間、文字列が有効であることを保証します。 呼び出し先がその値を関数呼び出しが完了した後のある時点まで保持する必要がある場合、呼び出し元は、その値の文字列値のコピーを割り当てる必要があります。

## URI と JSON の解析

さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。 これらの文字列の解析と生成には、独自の好みのライブラリを使用してください。

アプリで WinRT が利用できる場合は `RuntimeClass_Windows_Data_Json_JsonObject` 、 `IJsonObjectStatics` JSON 文字列の解析または生成、 `RuntimeClass_Windows_Foundation_Uri` および uri の解析と生成を行うことができ `IUriRuntimeClassFactory` ます。 これらはどちらも Win32 アプリで動作します。

IUri と CreateUri を使って Uri を解析する場合は、次の URI の作成フラグを使って、WebView の URI 解析とより厳密に一致するようにします。 `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## デバッグ

標準のショートカット (または) で DevTools を開く。 `F12` `Ctrl+Shift+I` `--auto-open-devtools-for-tabs`コマンド引数スイッチを使うと、WebView を最初に作成したときに、DevTools ウィンドウをすぐに開くことができます。 ブラウザープロセスに追加のコマンドライン引数を指定する方法については、「CreateCoreWebView2Host のドキュメント」を参照してください。 WebView2 のさまざまなビルドを実行する方法については、CreateCoreWebView2Host のドキュメントの LoaderOverride を参照してください。

## バージョン

特定のバージョンの SDK を使ってアプリをビルドすると、アプリは、インストールされているブラウザーバイナリの以前のバージョンまたは新しいバージョンで終了する可能性があります。 WebView2 のバージョン1.0.0.0 以降では、更新中に、SDK がインストールされているブラウザーバイナリのさまざまなバージョンで動作しなくなる可能性があります。 バージョン1.0.0.0 以降の SDK では、次のベストプラクティスに従って、インストールされているブラウザーのさまざまなバージョンを使用できます。

API への変更を考慮するために、DLL エクスポート CreateCoreWebView2Environment を呼び出すときや、いずれかの CoreWebView2 オブジェクトで QueryInterface を呼び出す場合は、エラーかどうかを確認してください。 E_NOINTERFACE の戻り値は、SDK が Edge ブラウザーのバイナリと互換性がないことを示します。

QueryInterface からのエラーのチェックは、SDK が Edge ブラウザーのバージョンよりも新しい場合や、アプリが Edge ブラウザーに認識されないインターフェイスを使用しようとした場合にも考慮されます。

インターフェイスが利用できない場合は、可能であれば関連する機能を無効にするか、ブラウザーを更新する必要があることをエンドユーザーに知らせることができます。

## Members

#### get_Settings 

ICoreWebView2Settings オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。

> パブリック HRESULT [get_Settings](#get_settings)(ICoreWebView2Settings * * 設定)

#### get_Source 

現在の最上位レベルのドキュメントの URI。

> パブリック HRESULT [get_Source](#get_source)(LPWSTR * uri)

この値は、別のサイトやフラグメントナビゲーションへの移動などの場合に、SourceChanged イベント発生の一部として変更される可能性があります。 ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### 検索 

最上位レベルのドキュメントを指定した URI に移動します。

> パブリック HRESULT[移動](#navigate)(LPCWSTR uri)

詳細については、ナビゲーションイベントを参照してください。 これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。

```cpp
void ControlComponent::NavigateToAddressBar()
{
    int length = GetWindowTextLength(m_toolbar->addressBarWindow);
    std::wstring uri(length, 0);
    PWSTR buffer = const_cast<PWSTR>(uri.data());
    GetWindowText(m_toolbar->addressBarWindow, buffer, length + 1);

    HRESULT hr = m_webView->Navigate(uri.c_str());
    if (hr == E_INVALIDARG)
    {
        // An invalid URI was provided.
        if (uri.find(L' ') == std::wstring::npos
            && uri.find(L'.') != std::wstring::npos)
        {
            // If it contains a dot and no spaces, try tacking http:// on the front.
            hr = m_webView->Navigate((L"http://" + uri).c_str());
        }
        else
        {
            // Otherwise treat it as a web search. We aren't bothering to escape
            // URL syntax characters such as & and #
            hr = m_webView->Navigate((L"https://bing.com/search?q=" + uri).c_str());
        }
    }
    if (hr != E_INVALIDARG) {
        CHECK_FAILURE(hr);
    }
}
```

#### NavigateToString 

新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。

> パブリック HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlcontent)

HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。 新しいページの起点は "空白" になります。

```cpp
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### add_NavigationStarting 

NavigationStarting イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NavigationStarting](#add_navigationstarting)([ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) * eventHandler、EventRegistrationToken * token)

NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。 これは、リダイレクトの場合にも発生します。

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### remove_NavigationStarting 

Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)

#### add_ContentLoading 

ContentLoading イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ContentLoading](#add_contentloading)([ICoreWebView2ContentLoadingEventHandler](ICoreWebView2ContentLoadingEventHandler.md) * eventHandler、EventRegistrationToken * token)

ContentLoading は、コンテンツが読み込まれる前に発生します。 AddScriptToExecuteOnDocumentCreated ContentLoading によって追加されたスクリプトは、同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合には発生しません。 これは、NavigationStarting イベントと SourceChanged イベントの後で、履歴の変更イベントと Navigationstarting イベントの前に発生します。

#### remove_ContentLoading 

Add_ContentLoading で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ContentLoading](#remove_contentloading)(EventRegistrationToken token)

#### add_SourceChanged 

SourceChanged Source プロパティが変更されたときに発生します。

> パブリック HRESULT [add_SourceChanged](#add_sourcechanged)([ICoreWebView2SourceChangedEventHandler](ICoreWebView2SourceChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

SourceChanged のサイトまたはフラグメントナビゲーションに移動する場合に発生します。 ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションについては、このような操作は発生しません。 SourceChanged ドキュメントへのナビゲーションのためにコンテンツを読み込む前に、SourceChanged が呼び出されます。 SourceChanged イベントのイベントハンドラーを追加します。 

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### remove_SourceChanged 

Add_SourceChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_SourceChanged](#remove_sourcechanged)(EventRegistrationToken token)

#### add_HistoryChanged 

履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。

> パブリック HRESULT [add_HistoryChanged](#add_historychanged)([ICoreWebView2HistoryChangedEventHandler](ICoreWebView2HistoryChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

履歴の変更を使って get_CanGoBack/get_CanGoForward の値が変更されたかどうかを確認します。 GoBack/GoForward を使用する場合にも変更履歴が発生します。 変更履歴は、SourceChanged と ContentLoading の後に発生します。 履歴変更イベントのイベントハンドラーを追加します。 

```cpp
    // Register a handler for the HistoryChanged event.
    // Update the Back, Forward buttons.
    CHECK_FAILURE(m_webView->add_HistoryChanged(
        Callback<ICoreWebView2HistoryChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);

                return S_OK;
            })
            .Get(),
        &m_historyChangedToken));
```

#### remove_HistoryChanged 

Add_HistoryChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_HistoryChanged](#remove_historychanged)(EventRegistrationToken token)

#### add_NavigationCompleted 

NavigationCompleted イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NavigationCompleted](#add_navigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](ICoreWebView2NavigationCompletedEventHandler.md) * eventHandler、EventRegistrationToken * token)

NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    CORE_WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == CORE_WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### remove_NavigationCompleted 

Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)

#### add_FrameNavigationStarting 

FrameNavigationStarting イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) * eventHandler、EventRegistrationToken * token)

FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。 これは、リダイレクトの場合にも発生します。

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### remove_FrameNavigationStarting 

Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)

#### add_ScriptDialogOpening 

Scriptの開始イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([ICoreWebView2ScriptDialogOpeningEventHandler](ICoreWebView2ScriptDialogOpeningEventHandler.md) * eventHandler、EventRegistrationToken * token)

イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。 このイベントは、ICoreWebView2Settings:: Aredefaultscript プロパティが false に設定されている場合にのみ発生します。 Scriptdialogs 左中イベントを使うと、ダイアログを非表示にしたり、既定のダイアログをカスタムダイアログに置き換えたりすることができます。

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<ICoreWebView2ScriptDialogOpeningEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<ICoreWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            CORE_WEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<ICoreWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### remove_ScriptDialogOpening 

Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)

#### add_PermissionRequested 

PermissionRequested されたイベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_PermissionRequested](#add_permissionrequested)([ICoreWebView2PermissionRequestedEventHandler](ICoreWebView2PermissionRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<ICoreWebView2PermissionRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CORE_WEBVIEW2_PERMISSION_KIND kind = CORE_WEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionKind(&kind));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionKind(kind);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        CORE_WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? CORE_WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? CORE_WEBVIEW2_PERMISSION_STATE_DENY
            :                     CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### remove_PermissionRequested 

Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)

#### add_ProcessFailed 

ProcessFailed イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ProcessFailed](#add_processfailed)([ICoreWebView2ProcessFailedEventHandler](ICoreWebView2ProcessFailedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<ICoreWebView2ProcessFailedEventHandler>(
            [this](ICoreWebView2* sender,
                ICoreWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        CORE_WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == CORE_WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process has stopped responding.  Recreate webview?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### remove_ProcessFailed 

Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)

#### AddScriptToExecuteOnDocumentCreated 

グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。

> パブリック HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript、[ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) * handler)

挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。 これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。

[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。 たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### RemoveScriptToExecuteOnDocumentCreated 

AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。

> パブリック HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)

#### Execuスクリプト 

WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。

> パブリック HRESULT の[Executescript](#executescript)(LPCWSTR JavaScript、[ICoreWebView2ExecuteScriptCompletedHandler](ICoreWebView2ExecuteScriptCompletedHandler.md) * handler)

これは非同期的に実行されます。完了すると、ExecuteScriptCompletedHandler パラメーターでハンドラーが指定されると、指定された JavaScript を評価した結果を使って Invoke メソッドが呼び出されます。 結果値は、JSON でエンコードされた文字列です。 結果が定義されていない場合、参照循環が含まれている場合、または JSON にエンコードできない場合は、JSON null 値が文字列 ' null ' として返されます。 明示的な戻り値のない関数は undefined を返します。 実行されたスクリプトが未処理の例外をスローした場合、結果は ' null ' にもなります。 このメソッドは非同期的に適用されます。 1つのドキュメントに対して webview を実行しているときに、操作が行われたときに、その呼び出しが行われてから JavaScript が実行される前に、移動が行われると、スクリプトは実行されず、ハンドラーは errorCode パラメーターの E_FAIL で呼び出されます。 実行方法 IsScriptEnabled が FALSE に設定されている場合でも、スクリプトは機能します。

```cpp
// Prompt the user for some script and then execute it.
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```

#### CapturePreview 

WebView が表示されている画像をキャプチャします。

> パブリック HRESULT [CapturePreview](#capturepreview)([CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format) imageformat、IStream * imagestream、[ICoreWebView2CapturePreviewCompletedHandler](ICoreWebView2CapturePreviewCompletedHandler.md) * handler)

ImageFormat パラメーターを使用して、画像の形式を指定します。 結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。 CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<ICoreWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### 再 

現在のページを再読み込みします。

> パブリック HRESULT [Reload](#reload)()

これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。 ただし、戻る/forward 履歴は変更されません。

#### PostWebMessageAsJson 

指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。

> パブリック HRESULT [Postwebmessageasjson](#postwebmessageasjson)(LPCWSTR webmessageasjson)

最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。 このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 イベント引数は、のインスタンス `MessageEvent` です。 ICoreWebView2Settings:: IsWebMessageEnabled の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗します。 イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。 イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。 Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。 このメッセージは非同期的に送信されます。 メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### PostWebMessageAsString 

これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。

> パブリック HRESULT [Postwebmessageasstring](#postwebmessageasstring)(LPCWSTR webmessageasstring)

これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。 JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。

#### add_WebMessageReceived 

このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。

> パブリック HRESULT [add_WebMessageReceived](#add_webmessagereceived)([ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md) * handler、EventRegistrationToken * token)

PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。

```cpp
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```

 PostMessage が呼び出されると、この SetWebMessageReceivedEventHandler メソッドによって設定された[ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md)が、postMessage のオブジェクトパラメーターを JSON 文字列に変換して呼び出されます。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### remove_WebMessageReceived 

Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)

#### Calldevon Protocolメソッド 

非同期の Devて Protocol メソッドを呼び出します。

> パブリック HRESULT[呼び出し DevLPCWSTR Protocolmethod](#calldevtoolsprotocolmethod)(METHODNAME、LPCWSTR ParametersAsJson、[ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](ICoreWebView2CallDevToolsProtocolMethodCompletedHandler.md) * handler)

使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。 MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。 ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。 メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。 Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<ICoreWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### get_BrowserProcessId 

WebView をホストしているブラウザープロセスのプロセス id。

> パブリック HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 * 値)

#### get_CanGoBack 

ナビゲーション履歴で前のページに移動できる場合は true を返します。

> パブリック HRESULT [get_CanGoBack](#get_cangoback)(BOOL * CanGoBack)

履歴変更イベントは get_CanGoBack の値が変更された場合に発生します。

#### get_CanGoForward 

ナビゲーション履歴の次のページに移動できる場合は true を返します。

> パブリック HRESULT [get_CanGoForward](#get_cangoforward)(BOOL * CanGoForward)

履歴変更イベントは get_CanGoForward の値が変更された場合に発生します。

#### GoBack 

ナビゲーション履歴で、WebView を前のページに移動します。

> パブリック HRESULT [GoBack](#goback)()

#### GoForward 

WebView をナビゲーション履歴の次のページに移動します。

> パブリック HRESULT [Goforward](#goforward)()

#### GetDevToolsProtocolEventReceiver 

DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。

> パブリック HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(LPCWSTR EventName,[ICoreWebView2DevToolsProtocolEventReceiver](ICoreWebView2DevToolsProtocolEventReceiver.md) * * レシーバー)

EventName パラメーターは、形式におけるイベントの完全な名前です `{domain}.{event}` 。 Devtools プロトコル[ビューアー](https://aka.ms/DevToolsProtocolDocs)を参照して、devtools プロトコルイベントの説明とイベント引数の一覧を確認してください。

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### Stop 

すべてのナビゲーションと保留中のリソースフェッチを停止します。

> パブリック HRESULT [Stop](#stop)()

スクリプトは停止されません。

#### add_NewWindowRequested 

NewWindowRequested イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NewWindowRequested](#add_newwindowrequested)([ICoreWebView2NewWindowRequestedEventHandler](ICoreWebView2NewWindowRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。 アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<ICoreWebView2NewWindowRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<ICoreWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));

                auto newAppWindow = new AppWindow(L"");
                newAppWindow->m_isPopupWindow = true;
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_NewWindowRequested 

Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)

#### add_DocumentTitleChanged 

Documentechanged Lechanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([ICoreWebView2DocumentTitleChangedEventHandler](ICoreWebView2DocumentTitleChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<ICoreWebView2DocumentTitleChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### remove_DocumentTitleChanged 

Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)

#### get_DocumentTitle 

現在のトップレベルドキュメントのタイトル。

> パブリック HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR * title)

ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。

#### AddRemoteObject 

指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。

> パブリック HRESULT [Addremoteobject](#addremoteobject)(LPCWSTR NAME, VARIANT * object)

ホストオブジェクトは、を通じてリモートオブジェクトプロキシとして公開され `window.chrome.webview.remoteObjects.<name>` ます。 リモートオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。 アプリが名前付きのオブジェクトを追加していない場合、promise は拒否されます。 JavaScript コードがオブジェクトのプロパティまたはメソッドにアクセスする場合、promise が返されます。これは、ホストからプロパティやメソッドに対して返された値に解決されます。また、オブジェクトやパラメーターのプロパティやメソッドが無効であるなどのエラーが発生した場合には拒否されます。 たとえば、次のようなアプリケーションコードを実行するとします。 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。 コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。 JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。 入れ子になった配列は、最大3レベルまでサポートされます。 参照型での配列はサポートされていません。 VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。 JavaScript は null で、undefined は VT_EMPTY にマップされます。

さらに、すべてのリモートオブジェクトはとして公開され `window.chrome.webview.remoteObjects.sync.<name>` ます。 ここでは、ホストオブジェクトが同期リモートオブジェクトプロキシとして公開されています。 これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。 これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.remoteObjects.<name>` ます。

同期リモートオブジェクトプロキシと非同期リモートオブジェクトプロキシはどちらも、同じリモートオブジェクトをプロキシすることができます。 1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同一のリモートオブジェクトの他のプロキシにも反映されます。

JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。 これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。

リモートオブジェクトプロキシは JavaScript プロキシオブジェクトで、すべてのプロパティ get、プロパティセット、メソッドの呼び出しを受け取ります。 関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。 さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.remoteObjects.options.forceLocalProperties` もローカルで実行されます。 これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。 必要に応じて、この配列に追加することができます。

最適な手段と `chrome.webview.remoteObjects.cleanupSome` して、リモートオブジェクトプロキシを収集する方法があります。

リモートオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。

* applyRemote、getRemote、setRemote: リモートオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。 これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。 たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。 ただし `proxy.applyRemote('toString')` `toString` 、代わりにリモートプロキシオブジェクトで実行されます。

* getLocal、setLocal: プロパティ get、またはローカルにプロパティを設定します。 これらのメソッドを使って、リモートオブジェクトプロキシ自体のプロパティを、それが表すリモートオブジェクトではなく、強制的に取得または設定することができます。 たとえば、 `proxy.unknownProperty` は、リモートプロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。 ただし、この `proxy.getLocal('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。

* 同期: 非同期のリモートオブジェクトプロキシは、同一のリモートオブジェクトの同期リモートオブジェクトプロキシの promise を返す同期メソッドを公開します。 たとえば、 `chrome.webview.remoteObjects.sample.methodCall()` 非同期のリモートオブジェクトプロキシを返します。 代わりに、メソッドを使用して `sync` 同期リモートオブジェクトプロキシを取得できます。 `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* 非同期: 同期リモートオブジェクトプロキシは、同じリモートオブジェクトの非同期リモートオブジェクトプロキシをブロックして返す async メソッドを公開します。 たとえば、 `chrome.webview.remoteObjects.sync.sample.methodCall()` 同期リモートオブジェクトプロキシを返します。 このブロックに対してメソッドを呼び出す `async` と、同じリモートオブジェクトの非同期リモートオブジェクトプロキシが返されます。 `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* 次に、非同期リモートオブジェクトプロキシには then メソッドがあります。 これにより、awaitable を行うことができます。 `then` リモートオブジェクトの表現によって解決される promise を返します。 プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。 プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。 プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティと共にリモートオブジェクトプロキシとして返されます。

その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。 非同期のリモートオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。 この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。 同期リモートオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。

非同期リモートオブジェクトプロキシのプロパティの設定は、少し異なります。 Set はすぐに戻り値として設定されます。 これは JavaScript プロキシオブジェクトの要件です。 プロパティセットの完了を非同期的に待つ必要がある場合は、前述のように、setRemote メソッドを使って、promise を返します。 同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。

たとえば、次のインターフェイスを持つ COM オブジェクトがあるとします。

```IDL
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IRemoteObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);
    };
```

 このインターフェイスのインスタンスは、の JavaScript に追加することができ `AddRemoteObject` ます。 この場合は、次のように名前を指定し `sample` ます。

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_remoteObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddRemoteObject multiple times in a row without
            // calling RemoveRemoteObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(m_webView->AddRemoteObject(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```

 HTML 文書では、次の方法でこの COM オブジェクトを使うことができ `chrome.webview.remoteObjects.sample` ます。

```js
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = await chrome.webview.remoteObjects.sample.property;
            document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
            const propertyValue = chrome.webview.remoteObjects.sync.sample.property;
            document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyAsyncInput").value;
            // The following line will work but it will return immediately before the property value has actually been set.
            // If you need to set the property and wait for the property to change value, use the setRemote function.
            chrome.webview.remoteObjects.sample.property = propertyValue;
            document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
            // If you care about waiting until the property has actually changed value use the setRemote function.
            await chrome.webview.remoteObjects.sample.setRemote("property", propertyValue);
            document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
            const propertyValue = document.getElementById("setPropertySyncInput").value;
            chrome.webview.remoteObjects.sync.sample.property = propertyValue;
            document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
            const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
            const resultValue = await chrome.webview.remoteObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
            const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
            const resultValue = chrome.webview.remoteObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
            chrome.webview.remoteObjects.sample.CallCallbackAsynchronously(() => {
                document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
            });
        });
```

#### RemoveRemoteObject 

名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。

> パブリック HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)

新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。 既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。

#### Opendevツールウィンドウ 

WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。

> パブリック HRESULT [Opendevツールウィンドウ](#opendevtoolswindow)()

DevTools ウィンドウが既に開いているときに、何も呼び出されません。

#### add_ContainsFullScreenElementChanged 

"の場合、要素のプロパティが変更されたときに通知します。

> パブリック HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([ICoreWebView2ContainsFullScreenElementChangedEventHandler](ICoreWebView2ContainsFullScreenElementChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。 このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。 次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<ICoreWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(
                        sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_ContainsFullScreenElementChanged 

対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。

> パブリック HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)

#### get_ContainsFullScreenElement 

WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。

> パブリック HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL * Fullfullscreenelement)

#### add_WebResourceRequested 

WebResourceRequested イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_WebResourceRequested](#add_webresourcerequested)([ICoreWebView2WebResourceRequestedEventHandler](ICoreWebView2WebResourceRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。 イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### remove_WebResourceRequested 

Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)

#### AddWebResourceRequestedFilter 

URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。

> パブリック HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri、[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourcecontext)

URI パラメーターは、ワイルドカード文字列 (0 以上、"?": 完全に1つ) にすることができます。 nullptr は、L "" と同じです。 リソースコンテキストフィルターの説明については、「enum の CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT」を参照してください。

#### RemoveWebResourceRequestedFilter 

以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。

> パブリック HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri、[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourcecontext)

同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。 追加されていないフィルターの E_INVALIDARG を返します。

#### add_WindowCloseRequested 

WindowCloseRequested イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_WindowCloseRequested](#add_windowcloserequested)([ICoreWebView2WindowCloseRequestedEventHandler](ICoreWebView2WindowCloseRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

ウィンドウを閉じるために、WebView 内のコンテンツが要求されたときに発生します。たとえば、close の後に呼び出されます。 アプリが適切である場合は、アプリで WebView と関連するアプリのウィンドウを閉じる必要があります。

```cpp
    // Register a handler for the WindowCloseRequested event.
    // This handler will close the app window if it is not the main window.
    CHECK_FAILURE(m_webView->add_WindowCloseRequested(
        Callback<ICoreWebView2WindowCloseRequestedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) {
                if (m_isPopupWindow)
                {
                    CloseAppWindow();
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_WindowCloseRequested 

Add_WindowCloseRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)(EventRegistrationToken token)

#### CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT 

ICoreWebView2:: CapturePreview メソッドで使用されている画像形式。

> 列挙型[CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG            | PNG 画像形式。
CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG            | JPEG イメージ形式。

#### CORE_WEBVIEW2_SCRIPT_DIALOG_KIND 

ICoreWebView2ScriptDialogOpeningEventHandler インターフェイスで使用される JavaScript ダイアログの種類。

> 列挙型[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND](#core_webview2_script_dialog_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT            | ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。
CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM            | ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。
CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT            | Window というプロンプトで呼び出されるダイアログ。
CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD            | Beforeunload JavaScript イベントによって呼び出されるダイアログ。

#### CORE_WEBVIEW2_PROCESS_FAILED_KIND 

ICoreWebView2ProcessFailedEventHandler インターフェイスで使用されているプロセスエラーの種類。

> 列挙型[CORE_WEBVIEW2_PROCESS_FAILED_KIND](#core_webview2_process_failed_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED            | ブラウザープロセスが予期せず終了したことを示します。
CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED            | レンダープロセスが予期せず終了したことを示します。
CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE            | レンダープロセスが応答しなくなったことを示します。

#### CORE_WEBVIEW2_PERMISSION_KIND 

アクセス許可要求の種類。

> 列挙型[CORE_WEBVIEW2_PERMISSION_KIND](#core_webview2_permission_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION            | 不明な権限。
CORE_WEBVIEW2_PERMISSION_KIND_MICROPHONE            | オーディオをキャプチャするためのアクセス許可。
CORE_WEBVIEW2_PERMISSION_KIND_CAMERA            | ビデオをキャプチャするためのアクセス許可。
CORE_WEBVIEW2_PERMISSION_KIND_GEOLOCATION            | 位置情報へのアクセス許可。
CORE_WEBVIEW2_PERMISSION_KIND_NOTIFICATIONS            | Web 通知を送信するためのアクセス許可。
CORE_WEBVIEW2_PERMISSION_KIND_OTHER_SENSORS            | 汎用センサーへのアクセス許可。
CORE_WEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ            | ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。

#### CORE_WEBVIEW2_PERMISSION_STATE 

アクセス許可要求に対する応答。

> 列挙型[CORE_WEBVIEW2_PERMISSION_STATE](#core_webview2_permission_state)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT            | 既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。
CORE_WEBVIEW2_PERMISSION_STATE_ALLOW            | 権限の要求を許可します。
CORE_WEBVIEW2_PERMISSION_STATE_DENY            | 権限の要求を拒否します。

#### CORE_WEBVIEW2_WEB_ERROR_STATUS 

Web ナビゲーションのエラー状態の値。

> 列挙型[CORE_WEBVIEW2_WEB_ERROR_STATUS](#core_webview2_web_error_status)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN            | 不明なエラーが発生しました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT            | SSL 証明書の共通名が web アドレスと一致しません。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED            | SSL 証明書の有効期限が切れています。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS            | SSL クライアント証明書にエラーが含まれています。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED            | SSL 証明書が失効しています。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID            | SSL 証明書が無効になっている可能性があります。これは、 &ndash; 証明書がホスト名の公開キーピンと一致しなかったことを意味します。証明書が信頼されていない機関によって署名されている、または脆弱な署名アルゴリズムを使用している場合、証明書が名前の制限を超えている証明書、証明書の有効期間が長い、証明書の透過情報がない、証明書が[従来のシマンテックルート](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)にチェーンされている。
CORE_WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE            | ホストに到達できません。
CORE_WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT            | 接続がタイムアウトしました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE            | サーバーが無効または認識不能な応答を返しました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED            | 接続が中止されました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET            | 接続がリセットされました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED            | インターネット接続が切断されました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT            | 宛先に接続できません。
CORE_WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED            | 指定されたホスト名を解決できませんでした。
CORE_WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED            | 操作が取り消されました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED            | 要求のリダイレクトに失敗しました。
CORE_WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR            | 予期しないエラーが発生しました。

#### CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT 

Web リソース要求コンテキストの列挙。

> 列挙型[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL            | すべてのリソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT            | ドキュメントリソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET            | CSS リソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE            | 画像リソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA            | その他のメディアリソース (ビデオなど)。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT            | フォントリソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT            | スクリプトリソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST            | XML HTTP 要求。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH            | API 通信を取得します。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK            | TextTrack のリソース。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE            | EventSource API の通信。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET            | WebSocket API 通信。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST            | Web App マニフェスト。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE            | 署名された HTTP 交換。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_PING            | Ping 要求。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT            | CSP 違反レポート。
CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER            | その他のリソース。