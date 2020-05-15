---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8ca8de3c430eda3bde089ca53501d880f4d8e35e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654389"
---
# インターフェイス ICoreWebView2MoveFocusRequestedEventArgs 

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

MoveFocusRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | イベントがアプリによって処理されたかどうかを示します。
[get_Reason](#get_reason) | MoveFocus 要求されたイベントを WebView が発生させる理由。
[put_Handled](#put_handled) | Handled プロパティを設定します。

## Members

#### get_Handled 

イベントがアプリによって処理されたかどうかを示します。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * 値)

アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。 イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。 既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。 フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。

#### get_Reason 

MoveFocus 要求されたイベントを WebView が発生させる理由。

> パブリック HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON * 値)

#### put_Handled 

Handled プロパティを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)
