---
title: Microsoft Edge DevTools を使った Cookie の表示、編集、削除
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 084c4116cd4c9c5e70b2fe341257fa68ba2c8ae7
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612069"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# Microsoft Edge DevTools を使った Cookie の表示、編集、削除   

  

[HTTP cookie][MDNHTTPCookies]は主に、ユーザーセッションを管理するために使用され、ユーザーの個人設定の設定を保存し、ユーザーの動作を追跡するために使用されます。  また、これらのページは、web 上で表示される cookie の承認フォームを使用していることもあります。  このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]を使って、ページの HTTP cookie を表示、編集、削除する方法について説明します。  

## [Cookies] ウィンドウを開く   

1.  [DevTools を開き][DevToolsOpen]ます。  
1.  [**アプリケーション**] タブを選択して、[**アプリケーション**] パネルを開きます。  **マニフェスト**ウィンドウが開きます。  
    
    > ##### 図 1  
    > マニフェストウィンドウ  
    > ![マニフェストウィンドウ][ImageManifest]  

1.  [**記憶域**] で [ **cookie**] を展開し、[起点] を選択します。  
    
    > ##### 図 2  
    > [Cookie] ウィンドウ  
    > ![[Cookie] ウィンドウ][ImageCookies]  

## フィールド   

**Cookies**テーブルには、次のフィールドが含まれています。  

*   **[名前]**。  Cookie の名前。  
*   **値**。  Cookie の値。  
*   **ドメイン**。  Cookie の受信を許可されているホスト。  「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。  
*   **Path**。  ヘッダーを送信するために要求された URL 内に存在する必要がある URL `Cookie` 。  「 [Cookie のスコープ][MDNHTTPCookiesScope]」をご覧ください。  
*   **有効期限/最長年齢**。  Cookie の有効期限日または最大年齢。  「[永続的な cookie][MDNHTTPCookiesPermanent]」を参照してください。  [セッション cookie][MDNHTTPCookiesSession]の場合、この値は常に使用され `Session` ます。  
*   **サイズ**。  Cookie のサイズ (バイト単位) です。  
*   **HTTP**。  True の場合、このフィールドは、cookie が HTTP 経由でのみ使用され、JavaScript の変更が許可されていないことを示します。  「 [Httponly cookie][MDNHTTPCookiesSecure]」を参照してください。  
*   **セキュリティ保護さ**れます。  True の場合、このフィールドは、cookie がセキュリティで保護された HTTPS 接続を介してのみサーバーに送信される必要があることを示します。  「[安全な cookie][MDNHTTPCookiesSecure]」をご覧ください。  
*   **SameSite**。  `strict` `lax` Cookie が実験的な[Samesite][MDNHTTPCookiesSamesite]属性を使用しているかどうかを示します。  

## Cookie をフィルター処理する   

**名前**または**値**で cookie をフィルター処理するには、[**フィルター** ] テキストボックスを使用します。  他のフィールドによるフィルター処理はサポートされていません。  

> ##### 図 3  
> テキストが含まれていないすべての cookie をフィルターで除外する `ID`  
> ![テキスト ID が含まれていないすべての cookie をフィルターで除外する][ImageCookiesFilter]  

## Cookie を編集する   

[**名前**]、[**値**]、[**ドメイン**]、[**パス**]、[**有効期限**]、[最大有効期限] の各フィールドは編集できます。  
フィールドをダブルクリックして編集します。  

> ##### 図 4  
> クッキーの名前の設定 `DEVTOOLS!`  
> ![DEVTOOLS に cookie の名前を設定します。][ImageEditCookie]  

## Cookie を削除する   

Cookie を選択し、[**選択し**た削除の削除] をクリックし ![ て、 ][ImageDeleteIcon] 1 つの cookie を削除します。  

> ##### 図 5  
> 特定の cookie を削除する  
> ![特定の cookie を削除する][ImageDeleteCookie]  

すべて**Clear All**の ![ ][ImageClearIcon] cookie を削除するには、[すべてクリア] を選択します。  

> ##### 図 6  
> すべての cookie をクリアする  
> ![すべての cookie をクリアする][ImageClearAllCookies]  

<!--    -->  

  

<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "図 1: [マニフェスト] ウィンドウ"  
[ImageCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-selected.msft.png "図 2: [Cookie] ウィンドウ"  
[ImageCookiesFilter]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-filter-id.msft.png "図 3: テキスト ID が含まれていない cookie をフィルター処理する"  
[ImageEditCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-rename.msft.png "図 4: DEVTOOLS に cookie の名前を設定する"  
[ImageDeleteCookie]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-delete-selected.msft.png "図 5: 特定の cookie を削除する"  
[ImageClearAllCookies]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-cookies-clear-all.msft.png "図 6: すべての cookie をクリアする"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"  
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[MDNHTTPCookies]: https://developer.mozilla.org/docs/Web/HTTP/Cookies "HTTP クッキー |MDN"  
[MDNHTTPCookiesPermanent]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Permanent_cookies "HTTP クッキー-永続的な cookie |MDN"  
[MDNHTTPCookiesSamesite]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#SameSite_cookies "HTTP クッキー-SameSite クッキー |MDN"  
[MDNHTTPCookiesScope]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Scope_of_cookies "HTTP cookie-cookie のスコープ |MDN"  
[MDNHTTPCookiesSecure]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Secure_and_HttpOnly_cookies "HTTP クッキー-セキュアおよび HttpOnly クッキー |MDN"  
[MDNHTTPCookiesSession]: https://developer.mozilla.org/docs/Web/HTTP/Cookies#Session_cookies "HTTP クッキー-セッションクッキー |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cookies)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  