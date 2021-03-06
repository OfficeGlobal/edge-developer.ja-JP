---
description: Microsoft Edge DevTools を使って、バックグラウンドでの取り出し、バックグラウンド同期、通知、プッシュメッセージをデバッグする方法について説明します。
title: Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fb5e408eb261ae3b2145780a1d7d5566c4501936
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124818"
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

# Microsoft Edge DevTools によるバックグラウンドサービスのデバッグ  

Microsoft Edge DevTools の [ **バックグラウンドサービス** ] セクションは、ユーザーが web サイトを開いていない場合でも web サイトが更新を送受信できるようにする JavaScript api 用のツールのコレクションです。  
バックグラウンドサービスは、機能的には [バックグラウンドプロセス] [WikiBackgroundProcess] と似ています。  
Microsoft Edge DevTools は、次の各 Api をバックグラウンドサービスと見なします。  

*   [バックグラウンドでの取得](#background-fetch)  
*   [バックグラウンド同期](#background-sync)  
*   [通知](#notifications)  
*   [メッセージをプッシュする](#push-messages)  
    
Microsoft Edge DevTools では、DevTools が開いていない場合でも、3日間はバックグラウンドサービスイベントをログに記録できます。  
これは、イベントが予期したとおりに送受信されるようにするのに役立ちます。  各イベントの詳細も調べることができます。  

:::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
   [ **プッシュメッセージング** ] ウィンドウ  
:::image-end:::  

## バックグラウンドでの取得  

**バックグラウンドフェッチ API**を使用すると、**サービスワーカー**は、ムービーやポッドキャストなどの大規模なリソースをバックグラウンドサービスとして確実にダウンロードできます。  DevTools が開いていない場合でも、3日間のバックグラウンドの取り出しイベントをログに記録するには、次の操作を行います。  

<!--Todo: add background fetch api section when available -->  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [バックグラウンドでの **取得** ] ウィンドウを開く。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-empty.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-fetch-empty.msft.png":::
       [ **バックグラウンド** での取り出し] ウィンドウ  
    :::image-end:::  
    
1.  [ **Record** ] ( ![ レコード ][ImageRecordIcon] \) を選びます。  
   一部のバックグラウンドフェッチアクティビティがトリガーされると、DevTools によってイベントがテーブルに記録されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-fetch.msft.png":::
       [バックグラウンドでの **取得** ] ウィンドウのイベントのログ  
    :::image-end:::  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-fetch-details.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-fetch-details.msft.png":::
       [バックグラウンドでの **取得** ] ウィンドウのイベントの詳細を表示する  
    :::image-end:::  
    
## バックグラウンド同期  

**バックグラウンド同期 API**では、信頼性の高いインターネット接続を再確立した後、オフライン**サービスワーカー**がサーバーにデータを送信できるようにします。  DevTools が開いていない場合でも、3日間のバックグラウンド同期イベントをログに記録するには、次の操作を行います。  

<!--Todo: add background sync api section when available -->  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [ **バックグラウンドの同期** ] ウィンドウを開く。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-empty.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-empty.msft.png":::
       [ **バックグラウンドの同期** ] ウィンドウ  
    :::image-end:::  
    
1.  [ **Record** ] ( ![ レコード ][ImageRecordIcon] \) を選びます。  
   一部のバックグラウンド同期アクティビティをトリガーした後、DevTools はイベントをテーブルに記録します。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync.msft.png":::
       [ **バックグラウンド同期** ] ウィンドウのイベントのログ  
    :::image-end:::  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-background-sync-details.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-background-sync-details.msft.png":::
       **バックグラウンドの同期**ウィンドウのイベントの詳細を表示する  
    :::image-end:::  
    
## 通知  

**サービスワーカー**がサーバーから[プッシュメッセージ][MDNPush]を受信した後、サービスワーカーは[通知 API][MDNNotifications]を使ってユーザーにデータを表示します。  DevTools が開いていない場合でも、3日間の通知をログに記録するには、次の操作を行います。  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [ **通知** ] ウィンドウを開く。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-empty.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-empty.msft.png":::
       [ **通知** ] ウィンドウ  
    :::image-end:::  
    
1.  [ **Record** ] ( ![ レコード ][ImageRecordIcon] \) を選びます。  
   一部の通知アクティビティをトリガーすると、DevTools によってイベントがテーブルに記録されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications.msft.png":::
       **通知**ウィンドウのイベントのログ  
    :::image-end:::  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-notifications-details.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-notifications-details.msft.png":::
       [ **通知** ] ウィンドウのイベントの詳細を表示する  
    :::image-end:::  
    
## メッセージをプッシュする  

ユーザーにプッシュ通知を表示するには、 **サービスワーカー** はまず、 [プッシュメッセージ API][MDNPush] を使ってサーバーからデータを受信する必要があります。  サービスワーカーが通知を表示する準備ができたら、 [通知 API][MDNNotifications]を使います。  DevTools が開いていない場合でも、3日間、プッシュメッセージをログに記録するには、次の操作を行います。  

1.  [DevTools を開き][OpenDevTools]ます。  
1.  **アプリケーション**パネルを開きます。  
1.  [ **プッシュメッセージング** ] ウィンドウを開きます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-empty.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging-empty.msft.png":::
       [ **プッシュメッセージング** ] ウィンドウを開く  
    :::image-end:::  
    
1.  [ **Record** ] ( ![ レコード ][ImageRecordIcon] \) を選びます。  
    一部のプッシュメッセージのアクティビティがトリガーされた後、DevTools ではイベントがテーブルに記録されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging.msft.png":::
       [ **プッシュメッセージング** ] ウィンドウのイベントのログ  
    :::image-end:::  
    
1.  イベントをクリックすると、テーブルの下の領域に詳細が表示されます。  
    
    :::image type="complex" source="../media/javascript-application-background-services-push-messaging-details.msft.png" alt-text="[プッシュメッセージング] ウィンドウ" lightbox="../media/javascript-application-background-services-push-messaging-details.msft.png":::
       **プッシュメッセージング**ウィンドウのイベントの詳細を表示する  
    :::image-end:::  
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRecordIcon]: ../media/record-icon.msft.png  

<!-- links -->  

<!--[BackgroundFetchAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2018/12/background-fetch.md "Background Fetch API"  -->  
<!--[BackgroundSyncAPI]: ../../../microsoft-edge/devtools-guide-chromium/whats-new/2015/12/background-sync.md  "Background Sync API"  -->

[OpenDevTools]: ../open.md "Microsoft Edge (Chromium) 開発者ツールを開く |Microsoft ドキュメント"  

[MDNNotifications]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPush]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
<!--[ServiceWorkerCacheStorage]: https://alphabet.dev/service-workers-cache-storage "Service workers and the Cache Storage API | alphabet.dev"  -->
[WikiBackgroundProcess]: https://en.wikipedia.org/wiki/Background_process "バックグラウンドプロセス-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/background-services) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
