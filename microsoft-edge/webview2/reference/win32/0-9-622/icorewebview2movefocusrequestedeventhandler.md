---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2MoveFocusRequestedEventHandler
ms.openlocfilehash: 89b1e7fada56bcf535ae07be109acbb340fdc9a8
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012269"
---
# <span data-ttu-id="3e23a-104">インターフェイス ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3e23a-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="3e23a-105">呼び出し元は、このメソッドを実装して MoveFocusRequested イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3e23a-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="3e23a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e23a-106">Summary</span></span>

 <span data-ttu-id="3e23a-107">Members</span><span class="sxs-lookup"><span data-stu-id="3e23a-107">Members</span></span>                        | <span data-ttu-id="3e23a-108">説明</span><span class="sxs-lookup"><span data-stu-id="3e23a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e23a-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="3e23a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3e23a-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e23a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3e23a-111">Members</span><span class="sxs-lookup"><span data-stu-id="3e23a-111">Members</span></span>

#### <span data-ttu-id="3e23a-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="3e23a-112">Invoke</span></span> 

<span data-ttu-id="3e23a-113">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e23a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3e23a-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="3e23a-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>
