---
description: Microsoft Edge で web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 0cb135553b04cd0cf160755eacc0dbae245d13b7
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645316"
---
# WebDriver (Chromium)  

W3C [Webdriver][W3CWebdriver] API は、プラットフォームと言語に依存しないインターフェイスとワイヤプロトコルであり、Microsoft Edge \ (Chromium \) などの web ブラウザーの動作をプログラムまたはスクリプトで制御できます。  

WebDriver を使うと、開発者は、ユーザーの操作をシミュレートする自動テストを作成できます。  Webdriver のテストとシミュレーションは JavaScript 単体テストとは異なります。 WebDriver は、ブラウザーで実行されている JavaScript の機能と情報にアクセスすることはできないため、Webdriver ia ではユーザーイベントや OS レベルのイベントをより正確にシミュレートすることができます。  WebDriver は、1つのテストセッションで複数のウィンドウ、タブ、web ページにわたるテストを管理できます。  

ここでは、Microsoft Edge \ (Chromium) の WebDriver の使用を開始する方法について説明します。  

## Microsoft Edge をインストールする (Chromium)  

まだインストールしていない場合は、 [Microsoft Edge (Chromium) をインストール][MicrosoftEdge]してください。  コンピューターにプレインストールされているバージョンの Microsoft Edge を使用している場合は、microsoft edge \ (Chromium \) と Microsoft Edge \ (EdgeHTML \) がインストールされていることを確認してください。  簡単に確認するには、 `edge://settings/help` ブラウザーに読み込み、バージョン番号が v75 以降であることを確認します。  

## Microsoft Edge ドライバーをダウンロードする  

WebDriver では、ブラウザー固有のドライバーを各ブラウザーで自動化する必要があります。  Microsoft Edge \ (Chromium \) については、WebDriver には、テストまたは自動化する Microsoft Edge のビルド用の適切な[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]が必要です。  

適切なビルド番号を確認するには、次の手順を使用します。  

1.  Microsoft Edge を起動する 
1.  Microsoft Edge \ (Chromium \) バージョンを表示します。  
    *   次に移動します:  `edge://settings/help`  
    *   `...`  >  **Settings**  >   **Microsoft Edge に関する**設定を選択する  
1.  ビルドの適切なバージョンの WebDriver を確認して、適切に動作するようにします。  

:::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日の Microsoft Edge カナリアのビルド番号":::
   図 1.  2020年1月14日の Microsoft Edge カナリアのビルド番号  
:::image-end:::

<!--  
> ##### Figure 1  
> The build number for Microsoft Edge Canary on January 14, 2020
> ![The build number for Microsoft Edge Canary on January 14, 2020][ImageWebdriverChromiumEdgeVersion]  
-->  

次に、[対応するバージョンの Microsoft Edge ドライバーをダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]します。  

:::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge ドライバーページのダウンロードセクション":::
   図 2.   [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページのダウンロードセクション  
:::image-end:::

<!--  
> ##### Figure 2
> The Downloads section of the [Microsoft Edge Driver page][MicrosoftDeveloperEdgeToolsWebdriverDownloads]
> ![The Downloads section of the Microsoft Edge Driver page][ImageWebdriverChromiumEdgeDriverInstall]  
-->  

> [!NOTE]
> Microsoft edge \ (EdgeHTML \) は[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriverDownloads]では動作しません。  Microsoft Edge \ (EdgeHTML \) を自動化するには、microsoft [WebDriver For Microsoft edge \ (EdgeHTML \)][Webdriver]をダウンロードする必要があります。  

## WebDriver 言語バインドの選択  

ダウンロードする必要がある最後のコンポーネントは、言語固有のクライアントドライバーです。  言語バインディングは、Python、Java、C \ #、ルビ、JavaScript で記述したコードを、[前のセクション](#download-microsoft-edge-driver)でダウンロードした Microsoft edge ドライバーが microsoft edge \ (Chromium \) で実行できるように変換します。  

[選択した WebDriver 言語バインドをダウンロード][SeleniumDownloads]します。  Microsoft Edge チームでは、Microsoft Edge \ (Chromium \) の組み込みサポートが[4.00 Selenium][NugetPackagesSeleniumWebdriver400alpha05]れているため、alpha05 以降を強くお勧めします。  ただし、現在の厩舎 Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を使用することができます。  

> [!IMPORTANT]
> を使用して Microsoft Edge \ (Chromium \) を以前に自動化またはテストしている場合 `ChromeDriver` `ChromeOptions` 、webdriver コードは Microsoft Edge v80 以降で正常に動作しません。  この変更は中断されています。 Microsoft Edge \ (Chromium \) では、これらのコマンドは受け入れられなくなりました。  `EdgeOptions`クラスと[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]を使うようにテストを変更する必要があります。  

### Selenium 3 の使用  

[Selenium 3][|::ref1::|]は最新の安定した Selenium リリースです。  既定では、Selenium 3 は古い Microsoft Edge \ (EdgeHTML \) を駆動しており、Microsoft Edge \ (Chromium \) の組み込みサポートはありません。  Selenium 3 を Microsoft Edge \ (Chromium \) で使用するには、 [Microsoft edge パッケージ用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をインストールします。  Microsoft Edge 用 Selenium Tools は、更新されたドライバーを使用して Selenium 3 を拡張し、Microsoft Edge \ (EdgeHTML \) と新しい Microsoft Edge \ (Chromium \) のブラウザーの両方の自動テストを作成するのに役立ちます。  

Microsoft Edge 用 Selenium Tools は、Selenium 3 と、既存のブラウザーテストを行っていて、Selenium バージョンを変更せずに新しい Microsoft Edge \ (Chromium \) ブラウザーを追加する必要がある開発者向けのソリューションです。  `EdgeDriver` `EdgeDriverService` ツールに含まれているクラスとクラスは、Selenium の組み込みの同等の機能と完全に互換性があり、Microsoft Edge \ (EdgeHTML \) を既定で実行できます。このため、ツールは Selenium 内の既存の Edge クラスに対してシームレスなドロップイン置換として使うことができます。  

[Microsoft edge の Selenium ツールをインストール][GithubMicrosoftEdgeSeleniumTools]して、Selenium 3 プロジェクトで microsoft edge \ (Chromium) を使い始めることができます。  

## WebDriver で Microsoft Edge (Chromium) を使用する

次の例は、Selenium 3 または4のいずれかを使って実行できます。  Selenium 3 で使用するには、 [Microsoft Edge 用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]がインストールされている必要があります。  

### 基本的な使用方法  

Microsoft Edge \ (EdgeHTML \) で使用するには、クラスの既定のインスタンスを作成するだけです `EdgeDriver` 。

#### [C#](#tab/c-sharp/)  

<a id="basic-usage-code" />  

```csharp
var driver = new EdgeDriver();
```  

#### [Python](#tab/python/)  

<a id="basic-usage-code" />  

```python
driver = Edge()
```  

* * *  

### Microsoft Edge の推進 (Chromium)  

代わりに Microsoft Edge \ (Chromium \) で使用するには、新しいクラスを作成し、プロパティがに設定された `EdgeDriver` `EdgeOptions` オブジェクトを渡し `UseChromium` `true` ます。  

#### [C#](#tab/c-sharp/)  

<a id="diving-microsoft-edge-chromium-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="diving-microsoft-edge-chromium-code" />  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

* * *  

### 特定のブラウザーのバイナリを選択する (Chromium のみ)  

特定の `EdgeOptions` バイナリを選択するには、クラスを使います。  Microsoft edge ベータ版などの[Microsoft edge preview チャネル][MicrosoftedgeinsiderDownload]をテストする場合に便利です。  

#### [C#](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

* * *  

### Microsoft Edge Driver サービスをカスタマイズする  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

クラスを `EdgeDriver` 使ってクラスのインスタンスを作成すると `EdgeOptions` 、 `EdgeDriverService` microsoft Edge \ (EdgeHTML \) または microsoft Edge \ (Chromium \) の適切なクラスが自動的に作成され、起動されます。  

を作成する場合は `EdgeDriverService` 、メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成し `CreateChromiumService()` ます。  以下のコードでは、冗長ログ出力を有効にするなど、追加のカスタマイズに役立つ場合があります。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> クラスのインスタンスを渡すときに、オブジェクトを指定する必要はありません `EdgeOptions` `EdgeDriver` `EdgeDriverService` 。  この `EdgeDriver` クラスは、提供するサービスの種類に応じて、Microsoft edge \ (EdgeHTML \) または Microsoft edge \ (Chromium) のいずれかの既定のオプションを使用します。  
> 
> ただし、クラスとクラスの両方を提供する場合は、 `EdgeDriverService` `EdgeOptions` 両方が同じバージョンの Microsoft Edge で構成されていることを確認する必要があります。  たとえば、既定の Microsoft Edge \ (EdgeHTML \) `EdgeDriverService` クラスと Chromium プロパティをクラスで使うことはできません `EdgeOptions` 。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

Python を使っている場合、オブジェクトはを `Edge` 作成して管理し `EdgeService` ます。  を構成するには `EdgeService` 、オブジェクトに追加の引数を渡し `Edge` ます。

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

* * *  

### Chromium 固有のオプションを使用する  

プロパティとして設定されたクラスを使用 `EdgeOptions` `UseChromium` すると `true` 、Selenium の[ChromeOptions][SeleniumWebDriverChromeoptionsClass]クラスで利用できるものと同じすべてのメソッドとプロパティにアクセスすることができます。  たとえば、他の Chromium ブラウザーの場合と同様に、メソッドを使用して、 `EdgeOptions.AddArguments()` 次のコードの[ヘッドレスモード][WikiHeadlessBrowser]で Microsoft Edge \ (Chromium) を実行します。  

#### [C#](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="using-chromium-specific-options-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

* * *  

> [!NOTE]
> これらの[Chromium 固有のプロパティとメソッド][SeleniumWebDriverChromeoptionsClass]は常に使用できますが、 `UseChromium` プロパティがに設定されていない場合は効果がありません `true` 。  同様に、 `UseChromium` プロパティがに設定されている場合は、Microsoft Edge \ (EdgeHTML \) 用の既存のプロパティとメソッドは効果がありません `true` 。  

<!--  
### [C#](#tab/c-sharp/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```csharp
var driver = new EdgeDriver();
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

### [Python](#tab/python/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```python
driver = Edge()
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

* * *  

-->  

<!--  
### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

#### C\#  

```csharp
var driver = new EdgeDriver();
```  

#### Python  

```python
driver = Edge()
```  

### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

### Customizing the Edge Driver Service  

#### C\#  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Python  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  
-->  

## Web ドライバーを設定するその他の方法  

### Chocolatey  

パッケージマネージャーとして[Chocolatey][Chocolatey]を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。  

```console
choco install selenium-chromium-edge-driver
```  

詳細については、「 [Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。  

### Docker  

[Docker][DockerHub]を使用している場合は、次のコマンドを実行して、microsoft edge \ (Chromium \) および[microsoft edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]で事前に構成された画像をダウンロードしてください。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

詳細については、「 [Docker Hub のコンテナー][DockerHubMsedgedriver]」を参照してください。  

## Microsoft Edge DevTools チームと連絡を取り合う    

Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお寄せください。  Microsoft Edge DevTools またはツイート[@EdgeDevTools][TwitterTweetEdgeDevTools]の**フィードバック**アイコンを使用して、チームに自分の意見を伝えます。  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン":::
   Microsoft Edge DevTools の**フィードバック**アイコン  
:::image-end:::

<!--  
> ##### Figure 3  
> The **Feedback** icon in the Microsoft Edge DevTools  
> ![The example.png file produced by example.js][ImageDevtoolsGuideChromiumMediaDevtoolsFeedback])  
-->  

<!-- image links -->  

<!--[ImageWebdriverChromiumEdgeVersion]: ./media/webdriver-chromium/edge-version.png "Figure 1: The build number for Microsoft Edge Canary on January 14, 2020"  -->  
<!--[ImageWebdriverChromiumEdgeDriverInstall]: ./media/webdriver-chromium/edge-driver-install.png "Figure 2: The Downloads section of the Microsoft Edge Driver page"  -->
<!--[ImageDevtoolsGuideChromiumMediaDevtoolsFeedback]: ./devtools-guide-chromium/media/devtools-feedback.png "Figure 3: The example.png file produced by example.js"  -->  

<!-- links -->  

[Webdriver]: ./webdriver.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey ソフトウェア"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge Driver |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-ツール |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 開発者"
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "ダウンロード-WebDriver |Microsoft 開発者"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "SeleniumTools |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium ドライバー 3.141.0 |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium ドライバー 4.0.0-alpha05 |NuGet ギャラリー"  

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions Class-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"