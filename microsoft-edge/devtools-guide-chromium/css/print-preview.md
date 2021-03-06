---
description: '[レンダリング] タブを開き、"print" > "CSS メディアのエミュレート" を選択します。'
title: Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d4e8e06d60461ac4cdcab8686a18a0698d52f6e3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125119"
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

# Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する  

[印刷メディアクエリ][MDNUsingMediaQueries]は、ページがどのように印刷されるかを制御します。  ページを印刷プレビューモードにするには、次の操作を行います。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  「」と入力し `rendering` 、[レンダリングの **表示**] を選択して、を選択し `Enter` ます。  
1.  [ **CSS メディアのエミュレート** ] で [ **印刷**] を選びます。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       印刷プレビューモード  
    :::image-end:::  
    
ここでは、他の web ページと同じように、CSS を表示したり変更したりできます。  「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCSSGetStarted]参照してください。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCSSGetStarted]: ./index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/print-preview) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
