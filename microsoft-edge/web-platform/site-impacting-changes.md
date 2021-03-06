---
description: サイトの互換性に影響を与える可能性の高い変更の概要を示します。
title: Microsoft Edge 向けのサイトの互換性に影響する変更点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム
ms.openlocfilehash: bb4d67bf1ab6274a10a83ee750fa9db52ab85464
ms.sourcegitcommit: 4497b399a6ddfa34163b7d3db4f76423d4da3c12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "11156349"
---
# Microsoft Edge 向けのサイトの互換性に影響する変更点  

Web は、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させ、常に進化しています。  場合によっては、既存のページの機能に影響を与えるために変更が重要になることがあります。  次の表は、Microsoft Edge チームが現在追跡している、特に大きな影響を与える変更をまとめたものです。  この記事をよく確認してください。Microsoft Edge チームでは、次のページが、考え方の変化、タイムラインの定着、および新しい変更が発表されたときに更新されます。  

| 変更点 | Stable チャネル | Experimentation | 追加情報 |  
|:--- |:--- |:--- |:--- |
| Cookie の既定値 `SameSite=Lax` と `SameSite=None-requires-Secure` | [Chrome + 1](#release-comments) \ (Edge v86 \)  | カナリア v82、Dev v82 | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome プラットフォームの状態エントリ][ChromePlatformStatus5088147346030592]に移動します。  |  
| 参照元ポリシー: 既定値 `strict-origin-when-cross-origin` | [Chrome + 1](#release-comments) \ (Edge v86 \)  | カナリア v79、Dev v79 | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome プラットフォームの状態エントリ][ChromePlatformStatus6251880185331712]に移動します。  |  
| `XmlHttpRequest`ページ強制的の同期を無効にする | [Chrome + 1](#release-comments) \ (Edge v83 \) |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  Chrome では、Microsoft Edge はグループポリシーを提供して、Edge v88 までこの変更をオフにします。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome プラットフォームの状態エントリ][ChromePlatformStatus4664843055398912]に移動します。  |  
| 通知のアクセス許可要求に関する微妙なプロンプトを表示する | Edge v84 |  | Quiet 通知要求は、または API を使って要求されたサイト通知のアクセス許可のアドレスバーに微妙な要求のアイコンを表示し `Notifications` `Push` ます。フルまたは標準のアクセス許可ポップアッププロンプト UI を置き換えます。  この機能は、現在すべてのユーザーに対して有効になっています。  Quiet 通知要求を無効にするには、に移動 `edge://settings/content/notifications` します。  今後、Microsoft Edge チームは、いくつかのシナリオで、完全なポップアップ通知のプロンプトを再び有効にすることができます。  |  
| 既定で TLS/1.0 と TLS/1.1 をオフにする | Edge v84 |  | [Sslminversion][DeployedEdgePoliciesSSLMinVersion]グループポリシーでは、tls/1.0 および tls/1.1 の再有効化が許可されています。ポリシーは、Edge v90 まで利用できます。  |  
| 混在したコンテンツのダウンロードをブロックする | [Chrome + 1](#release-comments) \ (Edge v86 \)  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [google セキュリティのブログエントリ][GoogleBlogSecurity20200206]を参照してください。  注意またはブロックするファイルの種類に関する Microsoft ロールアウトのスケジュールは、Chrome 後の1回のリリースで計画されています。  |  
| AppCache の廃止 | [Chrome + 1](#release-comments) \ (Edge v86 \)  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  詳細については、 [Webdev のドキュメント][WebDevAppCacheRemoval]を参照してください。  廃止の Microsoft ロールアウトスケジュールは、Chrome 以降のリリース1回で計画されています。  [Appcache OriginTrial Token][AppCacheOriginTrial]を要求すると、サイトはエッジ v90 まで廃止された API を引き続き使うことができます。  |  
| Adobe Flash の削除 | Edge v88  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  詳細については、「 [Adobe Flash Chromium のロードマップ][ChromiumFlashRoadmapSupportRemoved]」を参照してください。  | 
| FTP をオフにして削除する | Edge v88  | Edge ベータ版 v87 | Edge ベータ v87 では、FTP のサポートは既定で無効になっています。エッジの厩舎 v87 の場合は、有効のままになります。  Edge v88 では、FTP のサポートは完全に削除されます。  この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  詳細については、 [Chrome プラットフォームの状態エントリ][ChromePlatformStatus6246151319715840]に移動します。  依然として FTP サポートが必要なサイトがある企業は、 [IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を使うようにサイトを構成することによって、引き続き ftp を使用できます。  |   

##### リリースコメント  

:::row:::
   :::column span="1":::
      Chrome + 1
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、指示された機能や変更が Chrome の後に1回リリースされます。
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome または Chrome + 1
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、指定された機能を同時に、または Chrome の後に1つずつ解放します。
   :::column-end:::
:::row-end:::

<!-- links -->  

[DeployedEdgePoliciesSSLMinVersion]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[ChromePlatformStatus4664843055398912]: https://www.chromestatus.com/feature/4664843055398912 "ページ強制的 JavaScript の同期 XHR を許可しない |Chrome プラットフォームの状態"  
[ChromePlatformStatus5088147346030592]: https://www.chromestatus.com/feature/5088147346030592 "Cookie の既定値は SameSite = 甘い |Chrome プラットフォームの状態"  
[ChromePlatformStatus6251880185331712]: https://www.chromestatus.com/feature/6251880185331712 "参照元のポリシー: 既定では、"元の値に戻す" (cross-origin) |Chrome プラットフォームの状態"  
[ChromePlatformStatus6246151319715840]: https://chromestatus.com/feature/6246151319715840 "FTP サポートの廃止 |Chrome プラットフォームの状態"

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "フラッシュのサポートが Chromium から削除されました (Target: Chrome 88 +-Jan 2021)-フラッシュロードマップ |Chromium プロジェクト"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "Google Chrome での安全でないダウンロードからのユーザーの保護-Google Online セキュリティブログ" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal/ "AppCache の削除"
[AppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial token"

<!--todo:  cleanup links  -->  
