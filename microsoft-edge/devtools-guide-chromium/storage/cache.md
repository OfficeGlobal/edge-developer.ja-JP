---
description: Microsoft Edge DevTools のアプリケーションパネルからキャッシュデータを表示する方法について説明します。
title: Microsoft Edge DevTools を使ってキャッシュデータを表示する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5ab5fd0b3b504443e495f1d5108907a4551e6ac6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125441"
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

# Microsoft Edge DevTools を使ってキャッシュデータを表示する  

このガイドでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] を使って [キャッシュ][MDNCache] データを検査する方法について説明します。  

[HTTP キャッシュ][MDNHTTPCaching]データを検査しようとしている場合、これは目的のガイドではありません。  **ネットワークログ**の**Size**列で情報を探します。  「 [ネットワークアクティビティのログ記録][DevtoolsNetworkLogActivity]」を参照してください。  

## キャッシュデータを表示する  

1.  [ **アプリケーション** ] タブを選択して、[ **アプリケーション** ] パネルを開きます。  通常、 **マニフェスト** ウィンドウは既定で開かれます。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-manifest.msft.png":::
       **マニフェスト**ウィンドウ  
    :::image-end:::  
    
1.  [ **キャッシュ記憶域** ] セクションを展開して、利用可能なキャッシュを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage.msft.png":::
       利用可能なキャッシュ  
    :::image-end:::  
    
1.  コンテンツを表示するキャッシュを選択します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-root-headers.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-domain-root-headers.msft.png":::
       キャッシュの内容を表示する  
    :::image-end:::  
    
1.  リソースを選択して、表の下のセクションに HTTP ヘッダーを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-index-headers.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-index-headers.msft.png":::
       リソースの HTTP ヘッダーを表示する  
    :::image-end:::  
    
1.  [ **プレビュー** ] を選択して、リソースのコンテンツを表示します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-js-preview.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-domain-js-preview.msft.png":::
       リソースのコンテンツを表示する  
    :::image-end:::  
    
## リソースを更新する  

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  更新するリソースを選びます。  DevTools では、選択されていることを示すように強調表示されます。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-domain-refresh.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-domain-refresh.msft.png":::
       更新するリソースを選択する  
    :::image-end:::  
    
1.  [ **Refresh** ] ( ![ 更新 ][ImageRefreshIcon] \) を選びます。  
    
## リソースをフィルター処理する  

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  [ **パスを指定してフィルター** ] テキストボックスを使用して、指定したパスと一致しないリソースをフィルター処理します。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-filter.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-filter.msft.png":::
       指定したパスと一致しないリソースをフィルターで除外する  
    :::image-end:::  
    
## リソースの削除  

1.  [キャッシュのデータを表示](#view-cache-data)する。  
1.  削除するリソースを選びます。  DevTools では、選択されていることを示すように強調表示されます。  
    
    :::image type="complex" source="../media/storage-application-cache-storage-delete-selected.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-cache-storage-delete-selected.msft.png":::
       削除するリソースを選択する  
    :::image-end:::  
    
1.  [ **Delete selected** ] (選択し ![ た \ を削除) を選び ][ImageDeleteIcon] ます。  
    
## すべてのキャッシュデータを削除する  

1.  **アプリケーション**  >  の**クリアストレージ**を開きます。  
1.  [ **キャッシュストレージ** ] チェックボックスがオンになっていることを確認します。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox.msft.png":::
       [ **キャッシュストレージ** ] チェックボックス  
    :::image-end:::  
    
1.  [ **サイトデータのクリア**] を選びます。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png" alt-text="マニフェストウィンドウ" lightbox="../media/storage-application-clear-storage-cache-storage-checkbox-clear-site-data-button.msft.png":::
       [ **サイトデータのクリア** ] ボタン  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity  "ネットワークアクティビティのログ |Microsoft ドキュメント"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNHTTPCaching]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/storage/cache) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
