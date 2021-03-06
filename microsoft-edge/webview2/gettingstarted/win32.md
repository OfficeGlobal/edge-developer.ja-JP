---
description: Win32 アプリ用 WebView2 の概要ガイド
title: Win32 アプリの WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 20d830e2c8b95213b223da46f9afd9f69a137946
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120383"
---
# WebView2 の概要  

次のコンテンツでは、 [WebView2][Webview2Index] の一般的に使われる機能について説明し、最初の WebView2 アプリを作成するための開始点を提供します。  個々の WebView2 Api について詳しくは、 [api リファレンス][Webview2ReferenceWin32]をご覧ください。  

## 前提条件  

*   サポートされている OS \ (現在 Windows 10、Windows 8.1、Windows 7 \) にインストールされている[WebView2 Runtime][Webview2Installer]または[Microsoft Edge (Chromium) 非永続的なチャネル][MicrosoftedgeinsiderDownload]。  
    
    > [!NOTE]
    > WebView チームは、カナリアチャネルの使用を推奨し、最低限必要なバージョンは82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2015 以降、C++ サポートがインストールされています。  

## 手順 1-単一ウィンドウの win32 アプリを作成する  

1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。  チュートリアルに焦点を合わせるために、サンプルアプリ用の [従来の Windows デスクトップアプリケーション (C++) を作成][CppWindowsWalkthroughCreatingDesktopApplication] して、チュートリアルから変更されたサンプルコードを使用しています。  更新されたサンプルをダウンロードして始めるには、 [WebView2 サンプル][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]に移動します。  

Visual Studio で、を開き `WebView2GettingStarted.sln` ます。  以前のバージョンの Visual Studio を使っている場合は、 **WebView2GettingStarted** プロジェクトにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **プロパティ**] を選びます。  [**構成プロパティ**の  >  **全般**] で、 **Windows sdk のバージョン**と**プラットフォームのツールセット**を変更して、Win10 SDK と Visual Studio のツールセット (VS ツールセット \) を使用できるようにします。  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールバージョン" lightbox="../media/tool-version.png":::
   ツールバージョン  
:::image-end:::  

WebView2 ヘッダーファイルが存在しないため、Visual Studio でいくつかのエラーが表示されることがあります。これは、手順2が完了した後に移動する必要があります。  

## 手順 2-WebView2 SDK をインストールする  

プロジェクトに WebView2 SDK を追加します。  NuGet を使って Win32 SDK をインストールすることができます。  

1.  プロジェクトにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **NuGet パッケージの管理**] を選択します。  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="ツールバージョン" lightbox="../media/manage-nuget-packages.png":::
       NuGet パッケージの管理  
    :::image-end:::  
    
1.  Windows 実装ライブラリをインストールします。  
    1.  `Microsoft.Windows.ImplementationLibrary`検索バーに入力し、結果から [ **ImplementationLibrary** ] を選択して、右側のウィンドウで [**インストール**] を選択します。  NuGet によって SDK がコンピューターにダウンロードされます。  
        
        > [!NOTE] 
        > [Windows 実装ライブラリ][GithubMicrosoftWilMain]と[Windows ランタイム C++ テンプレートライブラリ][CppCxWrlTemplateLibraryVS2019]は省略可能であり、この例で COM を簡単に操作できるように追加されています。  
        
        :::image type="complex" source="../media/wil.png" alt-text="ツールバージョン" lightbox="../media/wil.png":::
           Windows 実装ライブラリ  
        :::image-end:::  
        
1.  WebView2 SDK をインストールします。  
    1.  `Microsoft.Web.WebView2`検索バーに入力し、結果から [ **WebView2** ] を選択して、右側のウィンドウで [**インストール**] を選択します。  NuGet によって SDK がコンピューターにダウンロードされます。  
        
        :::image type="complex" source="../media/nuget.png" alt-text="ツールバージョン" lightbox="../media/nuget.png":::
           Nuget パッケージマネージャー
        :::image-end:::  
        
1.  プロジェクトに WebView2 ヘッダーを追加します。  
    :::row:::
       :::column span="1":::
          `HelloWebView.cpp`を開き、次のコードスニペットをコピーして、最後の行の後ろに貼り付け `HelloWebView.cpp` `#include` ます。  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          Include セクションは、次のコードスニペットのようになります。  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
WebView2 API に対して使用およびビルドするように設定されています。  

### 空のサンプルアプリを作成する  

`F5`サンプルアプリをビルドして実行することを選択します。  空のウィンドウを表示するアプリが表示されます。  

:::image type="complex" source="../media/empty-app.png" alt-text="ツールバージョン" lightbox="../media/empty-app.png":::
   空のアプリ  
:::image-end:::  

## 手順 3-親ウィンドウ内に1つの WebView を作成する  

メインウィンドウに WebView を追加します。  メソッドを使用して `CreateCoreWebView2Environment` 環境を設定し、コントロールの電源を入れて Microsoft Edge \ (Chromium) ブラウザーを見つけます。  また、 `CreateCoreWebView2EnvironmentWithOptions` 既定の設定を使用する代わりに、ブラウザーの場所、ユーザーフォルダー、ブラウザーのフラグなどを指定する場合にも、このメソッドを使うことができます。  メソッドが完了する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` と、コールバック内でメソッドを実行 `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` し、メソッドを実行して、 `ICoreWebView2Controller::get_CoreWebView2` 関連付けられている WebView を取得できます。  

コールバックでいくつかの追加設定を行い、WebView のサイズを変更して親ウィンドウの100% を取得し、Bing に移動します。  

次のコードスニペットをコピーし、 `HelloWebView.cpp` メモの後 `// <-- WebView2 sample code starts here -->` とメモの前に貼り付け `// <-- WebView2 sample code ends here -->` ます。  

```cpp
// Step 3 - Create a single WebView within the parent window
// Locate the browser and set up the environment for WebView
CreateCoreWebView2EnvironmentWithOptions(nullptr, nullptr, nullptr,
    Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
        [hWnd](HRESULT result, ICoreWebView2Environment* env) -> HRESULT {
        
            // Create a CoreWebView2Controller and get the associated CoreWebView2 whose parent is the main window hWnd
            env->CreateCoreWebView2Controller(hWnd, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                [hWnd](HRESULT result, ICoreWebView2Controller* controller) -> HRESULT {
                if (controller != nullptr) {
                    webviewController = controller;
                    webviewController->get_CoreWebView2(&webviewWindow);
                }
                
                // Add a few settings for the webview
                // The demo step is redundant since the values are the default settings
                ICoreWebView2Settings* Settings;
                webviewWindow->get_Settings(&Settings);
                Settings->put_IsScriptEnabled(TRUE);
                Settings->put_AreDefaultScriptDialogsEnabled(TRUE);
                Settings->put_IsWebMessageEnabled(TRUE);
                
                // Resize WebView to fit the bounds of the parent window
                RECT bounds;
                GetClientRect(hWnd, &bounds);
                webviewController->put_Bounds(bounds);
                
                // Schedule an async task to navigate to Bing
                webviewWindow->Navigate(L"https://www.bing.com/");
                
                // Step 4 - Navigation events
                
                // Step 5 - Scripting
                
                // Step 6 - Communication between host and web content
                
                return S_OK;
            }).Get());
        return S_OK;
    }).Get());
```  

### Bing サンプルアプリを構築する  

`F5`アプリをビルドして実行することを選択します。  これで、[WebView] ウィンドウに Bing ページが表示されます。  

:::image type="complex" source="../media/bing-window.png" alt-text="ツールバージョン" lightbox="../media/bing-window.png":::
   Bing ウィンドウ  
:::image-end:::  

## ステップ 4-ナビゲーションイベント  

既に紹介している WebView チームについては、最後の手順のメソッドを使用して URL に移動し `ICoreWebView2::Navigate` ます。  ナビゲーション中に、WebView は、ホストがリッスンできる一連のイベントを発生させます。  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

詳細については、「 [ナビゲーションイベント][Webview2ConceptsNavigationEvents]」を参照してください。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ツールバージョン" lightbox="../media/navigation-events.png":::
   ナビゲーションイベント  
:::image-end:::  

エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、次のいずれかのイベントが発生することがあります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

HTTP リダイレクトが発生する場合は、 `NavigationStarting` 1 つの行に複数のイベントがあります。  

イベントを使用する例として、イベントのハンドラーを登録して `NavigationStarting` https 以外の要求をキャンセルします。  次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。  

```cpp
// register an ICoreWebView2NavigationStartingEventHandler to cancel any non-https navigation
EventRegistrationToken token;
webviewWindow->add_NavigationStarting(Callback<ICoreWebView2NavigationStartingEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2NavigationStartingEventArgs * args) -> HRESULT {
        PWSTR uri;
        args->get_Uri(&uri);
        std::wstring source(uri);
        if (source.substr(0, 5) != L"https") {
            args->put_Cancel(true);
        }
        CoTaskMemFree(uri);
        return S_OK;
    }).Get(), &token);
```  

これで、アプリは https 以外のサイトに移動しません。  同様のメカニズムを使って、独自のドメイン内でのナビゲーションの制限など、他のタスクを実行することができます。  

## 手順 5-スクリプト  

ホストアプリでは、JavaScript を WebView に挿入することもできます。  タスク WebView で任意の JavaScript を実行したり、初期化スクリプトを追加したりすることができます。  追加された初期化スクリプトは、削除されるまで、今後のすべてのトップレベルのドキュメントと子フレームのナビゲーションに適用されます。  初期化スクリプトは、グローバルオブジェクトを作成した後、および HTML ドキュメントに含まれている他のスクリプトを実行する前に実行されます。  

次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。  

```cpp
// Schedule an async task to add initialization script that freezes the Object object
webviewWindow->AddScriptToExecuteOnDocumentCreated(L"Object.freeze(Object);", nullptr);
// Schedule an async task to get the document URL
webviewWindow->ExecuteScript(L"window.document.URL;", Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
    [](HRESULT errorCode, LPCWSTR resultObjectAsJson) -> HRESULT {
        LPCWSTR URL = resultObjectAsJson;
        //doSomethingWithURL(URL);
        return S_OK;
    }).Get());
```  

この時点で、WebView は常にオブジェクトを固定 `Object` し、ページドキュメントを1回返す必要があります。  

> [!NOTE] 
> スクリプトインジェクション Api \ (および他のいくつかの WebView2 Api \) は非同期です。特定の順序でコードを実行する必要がある場合は、コールバックを使う必要があります。  

## ステップ 6-ホストと web コンテンツ間の通信  

この方法では、ホストと web コンテンツもメソッドを通じて相互に通信することができ `postMessage` ます。  WebView 内で実行されている web コンテンツは、メソッドによってホストに投稿される可能性があり `window.chrome.webview.postMessage` ます。メッセージは、 `ICoreWebView2WebMessageReceivedEventHandler` ホスト上のイベントハンドラーによって処理されます。  同様に、ホストで `ICoreWebView2::PostWebMessageAsString` は、 `ICoreWebView2::PostWebMessageAsJSON` リスナーから追加されたハンドラーによって検出された web コンテンツを経由して、またはメソッドでメッセージを送信することがあり `window.chrome.webview.addEventListener` ます。  通信メカニズムにより、web コンテンツは、ネイティブ Api を実行するようにホストにメッセージを送信することによってネイティブ機能を使うことができます。  

このメカニズムを理解するための例として、WebView でドキュメントの URL を印刷しようとすると、次の手順が発生します。  

1.  ホストは、受信したメッセージを web コンテンツに戻すためのハンドラーを登録します。  
1.  ホストは、ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツにスクリプトを挿入します。  
1.  ホストは、URL をホストにポストする web コンテンツにスクリプトを挿入します。  
1.  ホストのハンドラーがトリガーされ、web コンテンツへのメッセージ \ (URL) が返されます。  
1.  Web コンテンツのハンドラーがトリガーされ、ホスト \ (URL \) からメッセージが出力されます。  

次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。    

```cpp
// Set an event handler for the host to return received message back to the web content
webviewWindow->add_WebMessageReceived(Callback<ICoreWebView2WebMessageReceivedEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2WebMessageReceivedEventArgs * args) -> HRESULT {
        PWSTR message;
        args->TryGetWebMessageAsString(&message);
        // processMessage(&message);
        webview->PostWebMessageAsString(message);
        CoTaskMemFree(message);
        return S_OK;
    }).Get(), &token);

// Schedule an async task to add initialization script that
// 1) Add an listener to print message from the host
// 2) Post document URL to the host
webviewWindow->AddScriptToExecuteOnDocumentCreated(
    L"window.chrome.webview.addEventListener(\'message\', event => alert(event.data));" \
    L"window.chrome.webview.postMessage(window.document.URL);",
nullptr);
```  

### Show URL サンプルアプリを作成する  

`F5`アプリをビルドして実行することを選択します。  URL は、ページに移動する前にポップアップウィンドウに表示されます。  

:::image type="complex" source="../media/show-url.png" alt-text="ツールバージョン" lightbox="../media/show-url.png":::
   Url の表示  
:::image-end:::  

おめでとうございます。最初の WebView2 アプリを作成しました。  

## 次のステップ  

このページで取り上げていない WebView2 の機能の多くは、次のセクションで追加のリソースを提供しています。  

### 関連項目  

*   WebView2 機能の包括的な例については、「 [WEBVIEW2 API のサンプル][GithubMicrosoftedgeWebview2samplesApisample]」を参照してください。  
*   WebView2 を使って構築されたサンプルアプリケーションの場合は、 [WebView2Browser][GithubMicrosoftedgeWebview2browser]に移動します。  
*   WebView2 API の詳細については、 [api リファレンス][Webview2ReferenceWin32]に移動してください。  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーションイベント |Microsoft ドキュメント"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows ランタイム C++ テンプレートライブラリ (WRL) |Microsoft ドキュメント"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "チュートリアル: 従来の Windows デスクトップアプリケーションの作成 (C++) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser-MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 実装ライブラリ (WIL)-microsoft/WIL |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  
