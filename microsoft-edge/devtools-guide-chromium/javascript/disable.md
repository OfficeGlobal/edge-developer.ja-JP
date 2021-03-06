---
description: コマンドメニューを開き、[JavaScript を無効にする] コマンドを実行します。
title: Microsoft Edge DevTools で JavaScript を無効にする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4a200e2faa303a12d46fe2daf7ba89226a985b1f
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124720"
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

# Microsoft Edge DevTools で JavaScript を無効にする  

JavaScript が無効になっている場合に、web ページの外観と動作を確認するには、次の操作を実行します。  

1.  [Microsoft Edge DevTools を開き][DevToolsOpen]ます。  
1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-command.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  入力を開始し `javascript` 、[ **JavaScript を無効**にする] を選択して、 `Enter` コマンドを実行します。  JavaScript が無効になりました。  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-command-javascript.msft.png":::
       **コマンドメニュー**の [ **JavaScript を無効にする**] を選択します。  
    :::image-end:::  
    
    [ **ソース** ] の横にある黄色の警告アイコンは、JavaScript が無効になっていることを通知します。  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="コマンドメニュー" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       **ソース**の横にある警告アイコン  
    :::image-end:::  
    
DevTools が開いている限り、タブ内の JavaScript は無効のままです。  

読み込み中にページが JavaScript に依存するかどうかとその方法を確認するには、ページの再読み込みが必要になることがあります。  

JavaScript を再び有効にするには、次の操作を実行します。  

*   もう一度 **コマンドメニュー** を開き、コマンドを実行し `Enable JavaScript` ます。  
*   DevTools を閉じます。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/disable) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
