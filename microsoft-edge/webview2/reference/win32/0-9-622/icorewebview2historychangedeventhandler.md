---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HistoryChangedEventHandler
ms.openlocfilehash: 909b055af0f9594bb3c85b215cb8e02f13606aa0
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012304"
---
# <span data-ttu-id="5b4fa-104">インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5b4fa-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="5b4fa-105">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5b4fa-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="5b4fa-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5b4fa-106">Summary</span></span>

 <span data-ttu-id="5b4fa-107">Members</span><span class="sxs-lookup"><span data-stu-id="5b4fa-107">Members</span></span>                        | <span data-ttu-id="5b4fa-108">説明</span><span class="sxs-lookup"><span data-stu-id="5b4fa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5b4fa-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="5b4fa-109">Invoke</span></span>](#invoke) | <span data-ttu-id="5b4fa-110">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="5b4fa-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="5b4fa-111">Members</span><span class="sxs-lookup"><span data-stu-id="5b4fa-111">Members</span></span>

#### <span data-ttu-id="5b4fa-112">Invoke</span><span class="sxs-lookup"><span data-stu-id="5b4fa-112">Invoke</span></span> 

<span data-ttu-id="5b4fa-113">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="5b4fa-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="5b4fa-114">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="5b4fa-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>
