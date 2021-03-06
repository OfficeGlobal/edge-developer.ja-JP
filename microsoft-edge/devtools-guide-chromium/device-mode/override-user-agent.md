---
description: '[ネットワークの条件] タブを開き、[自動的に選択しない] を無効にして、一覧から選ぶか、カスタム文字列を入力します。'
title: Microsoft Edge DevTools からユーザーエージェント文字列を上書きする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: befbe186a5992c651f877a18f1c3232bf212394a
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124951"
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

# Microsoft Edge DevTools からユーザーエージェント文字列を上書きする  

Microsoft Edge DevTools から [ユーザーエージェント][MDNUserAgent] 文字列を上書きするには、次の操作を行います。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows, Linux \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を選択します。  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-console-command-menu.msft.png":::
       **コマンドメニュー**  
    :::image-end:::  
    
1.  「 `network conditions` **ネットワーク条件を表示**」を選択して、「 `Enter` **ネットワーク条件** 」タブを選択します。  
1.  [ **ユーザーエージェント** ] セクションで、 **[自動的に選択** する] チェックボックスをオフにします。  
    
    :::image type="complex" source="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png" alt-text="コマンドメニュー" lightbox="../media/device-mode-console-network-conditions-user-agent-select-automatically-deselected.msft.png":::
       **自動選択**を無効にする  
    :::image-end:::  
    
1.  リストからユーザーエージェント文字列を選択するか、独自のカスタム文字列を入力します。  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MDNUserAgent]: https://developer.mozilla.org/docs/Glossary/User_agent "ユーザーエージェント |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/override-user-agent) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
