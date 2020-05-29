---
title: Microsoft Edge DevTools のデバッグ JavaScript の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 06df1fd4d6457a3f02be85b95959bdc353865495
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581825"
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







# Microsoft Edge DevTools のデバッグ JavaScript の概要   



このチュートリアルでは、DevTools で JavaScript の問題をデバッグするための基本的なワークフローについて説明します。  

## 手順 1: バグを再現する   

常にバグを再現する一連のアクションを見つけることは、常にデバッグの最初の手順です。  

1.  [**デモを開く**] をクリックします。  `Control`\ (Windows \) または `Command` \ (macOS \) を保持し、新しいタブでデモを開きます。  

    [デモを開く][OpenDebugJSDemo]  

1.  [ `5` **数値 1** ] テキストボックスに入力します。  
1.  [ `1` **数値 2** ] テキストボックスに入力します。  
1.  [**番号 1] と [番号2の追加] を**クリックします。  ボタンの下にラベルが表示され `5 + 1 = 51` ます。  結果はになり `6` ます。  これは、修正する予定のバグです。  
    
    > ##### 図 1  
    > の結果 `5 + 1` はですが `51` 、 `6`  
    > ![5 + 1 の結果は51ですが、6にする必要があります。][ImageJSBugs]  

## 手順 2: ソースパネルの UI について理解する   

DevTools には、CSS の変更、ページの読み込みパフォーマンスのプロファイリング、ネットワーク要求の監視など、さまざまなタスクに対応するさまざまなツールが用意されています。  [**ソース**] パネルでは、JavaScript をデバッグします。  

1.  `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押して、devtools を開きます。  このショートカットは**コンソール**パネルを開きます。  
    
    > ##### 図 2  
    > **コンソール**パネル  
    > ![コンソールパネル][ImageJSConsole]  

1.  [**ソース**] タブをクリックします。  
    
    > ##### 図 3  
    > [**ソース**] パネル  
    > ![[ソース] パネル][ImageJSSources]  

**ソース**パネルの UI には3つの部分があります。  

> ##### 図 4  
> **ソース**パネルの UI の3つの部分  
> ![ソースパネルの UI の3つの部分][ImageJSSourcesAnnotated]  

1.  **ファイルナビゲーター**ウィンドウ \ ([図 4](#figure-4)のセクション 1)  ページが要求するすべてのファイルがここに表示されます。  
1.  **コードエディター**ウィンドウ \ ([図 4](#figure-4)のセクション 2)  [**ファイルナビゲーター** ] ウィンドウでファイルを選択すると、そのファイルの内容がここに表示されます。  
1.  **JavaScript のデバッグ**ウィンドウ ([図 4](#figure-4)のセクション 3)  ページの JavaScript を調べるためのさまざまなツール。  DevTools ウィンドウが広くなっている場合、このウィンドウは [**コードエディター** ] ウィンドウの右側に表示されます。  

## 手順 3: ブレークポイントでコードを一時停止する   

このような問題をデバッグする一般的な方法は、スクリプトの実行時に値を検査するために、コードに大量のステートメントを挿入することです `console.log()` 。  次に、例を示します。  

```javascript
function updateLabel() {
    var addend1 = getNumber1();
    console.log('addend1:', addend1);
    var addend2 = getNumber2();
    console.log('addend2:', addend2);
    var sum = addend1 + addend2;
    console.log('sum:', sum);
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
}
```  

このメソッドではジョブが完了して `console.log()` いる可能性がありますが、**ブレークポイント**を使うと作業を高速化できます。  ブレークポイントを使用すると、実行時にコードを一時停止し、その時点ですべての値を検証することができます。  ブレークポイントには、この方法に関するいくつかの利点があり `console.log()` ます。  

*   では `console.log()` 、ソースコードを手動で開いて、関連するコードを見つけ、ステートメントを挿入して `console.log()` から、コンソールにメッセージを表示するためにページを再読み込みする必要があります。  ブレークポイントを使用すると、コードがどのように構成されているかわからなくても、関連するコードを一時停止することができます。  
*   ステートメントで、 `console.log()` 検査する各値を明示的に指定する必要があります。  ブレークポイントを使用すると、DevTools によって、その時点でのすべての変数の値が表示されます。  場合によっては、認識していないコードに影響を与える変数が存在することもあります。  

つまり、ブレークポイントは、メソッドよりも短時間でバグを見つけて修正するのに役立ち `console.log()` ます。  

手順を実行して、アプリの動作について考えている場合は、 `5 + 1 = 51` `click` [ **1 と番号2を追加**] ボタンに関連付けられているイベントリスナーで、誤った sum () が計算されることを推測できます。  そのため、おそらくリスナーが実行されている時間の前後にコードを一時停止する必要があり `click` ます。  **イベントリスナーのブレークポイント**を使用すると、次の操作を行うことができます。  

1.  JavaScript の**デバッグ**ウィンドウで、[**イベントリスナーブレークポイント**] をクリックしてセクションを展開します。  DevTools は、**アニメーション**や**クリップボード**などの拡張可能なイベントカテゴリの一覧を表示します。  
1.  **マウス**イベントカテゴリの横にある [展開アイコン**の展開] をクリックし** ![ ][ImageExpandIcon] ます。  DevTools は、 **click** 、 **mousedown**などのマウスイベントの一覧を表示します。  各イベントの横にチェックボックスがあります。  
1.  **[クリック**時] チェックボックスをオンにします。  DevTools は *、* イベントリスナーが実行されると自動的に一時停止するように設定されました `click` 。  
    
    > ##### 図 5  
    > **[クリック**] チェックボックスが有効になっている  
    > ![[クリック] チェックボックスが有効になっている][ImageJSClickCheckbox]  
    
1.  デモに戻り、[**番号 1] と [番号 2**をもう一度追加する] をクリックします。  DevTools はデモを一時停止し、[**ソース**] パネルでコードの行を強調表示します。  DevTools は、16行目で一時停止する必要があり `get-started.js` ます。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    別のコード行を使用して一時停止した場合は、[**スクリプト実行の再開**] をクリックして、正しい行をポイントし ![ ][ImageResumeIcon] ます。  
    
    > [!NOTE]
    > 別の行に一時停止している場合は、アクセスした `click` すべてのページにイベントリスナーが登録されているブラウザー拡張機能があります。  内線番号のリスナーで一時停止してい `click` ます。  InPrivate モードを使って**プライベートで参照**している場合は、すべての拡張機能が無効になります。その場合は、必要なコード行を毎回一時停止することになります。  

<!--todo: add inprivate section when available -->  

**イベントリスナーのブレークポイント**は、devtools で利用できる多くの種類のブレークポイントのうちの1つにすぎません。  各型は最終的に、できるだけ簡単にさまざまなシナリオをデバッグするのに役立ちますので、すべての種類を memorizing することをお勧めします。  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## 手順 4: コードをステップ実行する   

バグの一般的な原因の1つとして、スクリプトが誤った順序で実行されることがあります。  コードをステップ実行することで、コードの実行を1行ずつ実行し、予期していた順序で実行されている位置を正確に把握することができます。  今すぐお試しください:  

1.  [次の関数のステップ**オーバー** ] をクリックして ![ ][ImageOverIcon] 、次の関数の呼び出しを実行します。  DevTools では、次のコードをステップ実行せずに実行します。  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  

    > [!NOTE]
    > DevTools では、数行のコードをスキップします。  これは、 `inputsAreEmpty()` false として評価されるため、このステートメントのコードブロックは `if` 実行されません。  

1.  DevTools の**ソース**パネルで **、[次**の関数の呼び出し] をクリックし ![ て、 ][ImageIntoIcon] 関数の実行時に1行ずつ手順を実行し `updateLabel()` ます。  

これは、コードをステップ実行するための基本的な考え方です。  コードを見ると `get-started.js` 、バグが関数のどこかにあると考えられ `updateLabel()` ます。  すべてのコード行をステップ実行するのではなく、別の種類のブレークポイントを使って、バグの可能性がある場所に近いコードを一時停止することができます。  

## 手順 5: コード行のブレークポイントを設定する   

行コードのブレークポイントは、最も一般的なブレークポイントの種類です。  一時停止する特定のコード行を取得したら、コード行のブレークポイントを使用します。  

1.  のコードの最後の行を確認し `updateLabel()` ます。  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  コードの左側に、この特定のコード行の行番号 ( **33**) が表示されています。  [ **33**] をクリックします。  DevTools は、 **33**の左側に赤いアイコンを配置します。  これは、この行に行コードのブレークポイントがあることを意味します。  DevTools は、このコード行が実行される前に常に一時停止されるようになりました。  
1.  [**スクリプト実行の再開**] ![ スクリプト実行をクリックし ][ImageResumeIcon] ます。  スクリプトは、33行目に到達するまで実行され続けます。  [DevTools] は、30、31、および32の行で、 `addend1` `addend2` `sum` 各行のセミコロンの右にある、、、の値を出力します。  
    
    > ##### 図 6  
    > DevTools は、32行目のコードの行のブレークポイントで一時停止します  
    > ![DevTools は、32行目のコードの行のブレークポイントで一時停止します][ImageJSLineOfCodeBreakpoint]  

## 手順 6: 変数の値を確認する   

[] の値、[ `addend1` `addend2` 疑わしい] と表示さ `sum` れます。  引用符で囲まれています。これは文字列であることを意味します。  これは、バグの原因を説明するための優れた仮説です。  次に、詳細情報を収集します。  DevTools には、可変値を検査するための多くのツールが用意されています。  

### 方法 1: 範囲ウィンドウ   

コード行を一時停止すると、**スコープ**ウィンドウに、現在定義されているローカルとグローバル変数、および各変数の値が表示されます。  また、必要に応じて休業変数も表示されます。  変数値をダブルクリックして編集します。  コード行で一時停止していない場合、**スコープ**ウィンドウは空です。  

> ##### 図 7  
> **スコープ**ウィンドウ  
> ![スコープウィンドウ][ImageJSScope]  

### 方法 2: 式をウォッチする   

[**式のウォッチ**] タブでは、時間の経過に伴う変数の値を監視できます。  名前が示すように、ウォッチ式は変数だけに限定されているわけではありません。  ウォッチ式には有効な JavaScript 式を格納することができます。  今すぐお試しください:  

1.  [**ウォッチ**] タブをクリックします。  
1.  [**式** ![ の追加] ][ImageAddIcon] をクリックします。  
1.  「`typeof sum`」と入力します。  
1.  キーを押し `Enter` ます。  DevTools が表示さ `typeof sum: "string"` れます。  コロンの右側の値は、ウォッチ式の結果です。  

> [!NOTE]
> [式のウォッチ] ウィンドウ ([図 8](#figure-8)の右下) で、 `typeof sum` ウォッチ式が表示されます。  DevTools ウィンドウが大きい場合は、[ウォッチ式] ウィンドウは、**イベントリスナーの [ブレークポイント**] ウィンドウの右側にあります。  

> ##### 図 8  
> ウォッチ式ウィンドウ  
> ![ウォッチ式ウィンドウ][ImageJSWatchExpression]  

疑わしいとして、 `sum` 数値の場合は文字列として評価されます。  これがバグの原因であることが確認されました。  

### 方法 3: 本体   

メッセージを表示するだけで `console.log()` なく、コンソールを使って任意の JavaScript ステートメントを評価することもできます。  デバッグの観点から、本体を使ってバグの潜在的な解決をテストすることができます。  今すぐお試しください:  

1.  コンソールの引き出しを開いていない場合は、を押して `Escape` 開きます。  これは、DevTools ウィンドウの下部に表示されます。  
1.  コンソールで、と入力 `parseInt(addend1) + parseInt(addend2)` します。  このステートメントは `addend1` 、および範囲内のコード行で一時停止しているために動作し `addend2` ます。  
1.  キーを押し `Enter` ます。  DevTools は、ステートメントを評価して出力し `6` ます。これは、デモで生成される結果です。  

> ##### 図 9  
> 評価後の本体の引き出し `parseInt(addend1) + parseInt(addend2)`  
> ![ParseInt (addend1) + parseInt (addend2) を評価した後の本体の引き出し][ImageJSConsoleEvaluated]  

## 手順 7: 修正プログラムを適用する   

バグの修正プログラムが見つかった場合は、コードを編集してデモを再実行して、修正を試してください。  この修正プログラムを適用するには、DevTools を終了する必要はありません。  DevTools UI では、JavaScript コードを直接編集できます。  今すぐお試しください:  

1.  [**スクリプト実行の再開**] ![ スクリプト実行をクリックし ][ImageResumeIcon] ます。  
1.  **コードエディター**で、行32、 `var sum = addend1 + addend2` をに置き換え `var sum = parseInt(addend1) + parseInt(addend2)` ます。  
1.  `Control` + `S` \ (Windows \) または `Command` + `S` \ (macOS \) を押して、変更内容を保存します。  
1.  [**ブレークポイントの非**アクティブ化] をクリックし ![ ][ImageDeactivateIcon] ます。  これは青色に変わり、アクティブであることを示します。  この設定を行うと、設定したブレークポイントはすべて、DevTools によって無視されます。  
1.  さまざまな値を持つデモを試してみてください。  デモが正しく計算されるようになりました。  

> [!CAUTION]
> このワークフローは、ブラウザーで実行されているコードにのみ修正プログラムを適用します。  ページにアクセスするすべてのユーザーのコードは修正されません。  そのためには、サーバー上のコードを修正する必要があります。  

## 次のステップ   

お疲れさまでした。  これで、JavaScript のデバッグ時に Microsoft Edge DevTools を最大限に活用する方法がわかりました。  このチュートリアルで学んだツールと方法を使用すると、時間を節約できます。  

このチュートリアルでは、2つの方法でブレークポイントを設定する方法について説明しました。  DevTools には、次のようなさまざまな方法があります。  

*   指定した条件が true の場合にのみトリガーされる条件付きブレークポイント。  
*   キャッチまたはキャッチされない例外のブレークポイント。  
*   指定した URL が指定した部分文字列と一致した場合にトリガーされる XHR ブレークポイント。  

<!-- See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

<!--There are a couple of code stepping controls that were not explained in this tutorial.  See [Step over line of code][JSReferenceStepping] to learn more.  -->  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: /microsoft-edge/devtools-guide-chromium/media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageIntoIcon]: /microsoft-edge/devtools-guide-chromium/media/step-into-icon.msft.png  
[ImageOverIcon]: /microsoft-edge/devtools-guide-chromium/media/step-over-icon.msft.png  
[ImageResumeIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-run-icon.msft.png  

[ImageJSBugs]: /microsoft-edge/devtools-guide-chromium/media/javascript-js-demo-bad.msft.png "図 1: 5 + 1 の結果は51ですが、6でなければなりません。"  
[ImageJSConsole]: /microsoft-edge/devtools-guide-chromium/media/javascript-console-empty.msft.png "図 2: コンソールパネル"  
[ImageJSSources]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections.msft.png "図 3: [ソース] パネル"  
[ImageJSSourcesAnnotated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-sections-annotated.msft.png "図 4: [ソース] パネル UI の3つの部分"  
[ImageJSClickCheckbox]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png "図 5: [クリック] チェックボックスが有効になっている"  
[ImageJSLineOfCodeBreakpoint]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused.msft.png "図 6: DevTools が行32のコードの行のブレークポイントで一時停止する"  
[ImageJSScope]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-scope.msft.png "図 7: スコープウィンドウ"  
[ImageJSWatchExpression]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-watch.msft.png "図 8: [ウォッチ式] ウィンドウ"  
[ImageJSConsoleEvaluated]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-breakpoint-paused-console.msft.png "ParseInt (addend1) + parseInt (addend2) を評価した後の本体の引き出し"  

<!-- links -->  

<!--[JSBreakpoints]: breakpoints.md "JavaScript Breakpoints"  -->  
<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->
[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "デモを開く"  
<!--[JSReferenceStepping]: reference.md#stepping "Reference Stepping"  -->

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  