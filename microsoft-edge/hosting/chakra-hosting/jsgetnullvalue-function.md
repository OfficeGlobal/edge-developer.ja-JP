---
description: 現在のスクリプトコンテキスト内の値を取得し `null` ます。
title: JsGetNullValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84164aa9ce5d522b0933d928d85b26c652be066f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570456"
---
# JsGetNullValue 関数
現在のスクリプトコンテキスト内の値を取得し `null` ます。  
  
## 構文  
  
```cpp  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### パラメーター  
 `nullValue`  
 `null`値。  
  
## 戻り値  
 `JsNoError`操作が正常に完了した場合は、エラーコードは返されません。  
  
## 注釈  
 アクティブなスクリプトコンテキストが必要です。  
  
## 要件  
 **ヘッダー:** jsrt  
  
## 関連項目  
 [リファレンス (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)