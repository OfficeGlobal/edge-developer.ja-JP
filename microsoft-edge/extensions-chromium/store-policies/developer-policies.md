---
description: Microsoft Edge のアドオンカタログ開発者ポリシー。
title: Microsoft Edge のアドオンカタログ開発者ポリシー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/21/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: be159491d892c176a8439393573dc23680fac377
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607434"
---
# Microsoft Edge のアドオンカタログ開発者ポリシー  

## このドキュメントの概要と目的  

Microsoft Edge のアドオンカタログ用の拡張機能の開発に興味をお持ちいただき、ありがとうございました。  Microsoft Edge のアドオンカタログ開発者ポリシー \ (アドオンカタログ開発者ポリシー) は、お客様の内線番号に適用されます。これには、[パートナーセンター][MicrosoftPartnerCenter]からの内線番号の申請や、microsoft Edge のアドオンによる拡張機能の提供が含まれます。  

## 指針  

使用を開始するためのいくつかの原則を次に示します。  

*   Microsoft Edge の内線番号には、一意の値を提供する必要があります。  Microsoft Edge のアドオンカタログから拡張機能をダウンロードするための説得力のある理由を提供します (Microsoft Edge アドオン \)。  
*   お客様は、お客さまの内線番号、ユーザを提供していること、その他の機能について、誤解しないようにする必要があります。  
*   ユーザー、システム、またはエコシステムを表示しないようにする必要があります。  Microsoft Edge のアドオンには、いかなる種類の詐欺にも対応する場所がありません。評価を行い、操作、クレジットカード不正行為、またはその他の不正行為活動をレビューします。  

これらのアドオンカタログ開発者ポリシーを遵守することで、内線の魅力と対象ユーザーを強化することができます。  

拡張機能は、数百名のユーザーにとって非常に重要です。  お客様が作成した内容が問題となり、世界中のお客様の内線番号を thrilled ことができます。  

## 1. 製品ポリシー  

### 1.1 Distinct 関数 & 値正確な表現  

拡張機能と関連付けられたメタデータは、記述したソース、機能、機能を正確かつ明確に反映する必要があります。  

#### 1.1.1 拡張機能には1つの目的が必要  

拡張機能には、機能が限定された1つの目的がある必要があります。  

#### 1.1.2 の説明  

拡張機能については、必須またはサポートされている入力デバイスを含む、機能、機能、および拡張に関する重要な制限事項について正確に説明する必要があります。  拡張機能のバリュープロポジションは、初回の実行時に明確である必要があります。  内線番号には、他の拡張機能と同じような名前やアイコンは使用できません。また、その表現に対する権限がない場合は、会社や行政機関の団体を表す必要はありません。  

#### 1.1.3 機能  

内線番号が完全に機能している必要があります。  

#### 1.1.4 検索と検出  

検索用語は、7つの固有の用語を超えてはならず、お客さまの内線番号に関連している必要があります。  

#### 1.1.5 が適切な詳細情報を提供する  

内線番号の詳細と情報を提供する必要があります。詳細については、お客様の内線番号のリスト \ (metadata) をご覧ください。  お客さまの内線番号には、お客さまのお客様のご利用にはお客さまの  拡張機能には、Microsoft Edge のアドオンでのアクティブなプレゼンスも含まれている必要があります。  

#### 1.1.6 の安定性とパフォーマンス  

拡張は、Microsoft Edge のパフォーマンスまたは安定性に悪影響を与えないようにする必要があります。  

#### 1.1.7 の難読化  

難読化されたコードを含む拡張機能は使用できません。  これには、拡張パッケージ内のコードに加えて、web から取得した外部コードまたはリソースも含まれます。  再表示されていない場合は、コードの一部をリファクターするように求められる場合があります。  

#### 1.1.8 Browser の設定の変更  

お客様の内線番号は、**適切なユーザーの同意**を必要としたり、変更したり、変更したりすることはできません。たとえば、アドレスバーの検索プロバイダーと候補、スタート画面またはホームページ、新しいタブページ、お気に入りの追加または削除に限定されません。  

ブラウザーの設定に変更を加えた場合は、拡張機能の説明に明示的に記述する必要があります。  

この拡張機能には、Microsoft web ページまたはサードパーティのサービス (サードパーティの検索エンジンの使用を義務付ける、またはサードパーティの web プロパティにホームページを設定するなど) を使用している場合にのみ、これらのサードパーティによって利用されているかどうかに関係なく、重要な設定のみを変更できます。  

### 1.2 セキュリティ  

内線番号には、ユーザーのセキュリティ、またはデバイス、システム、または関連するシステムのセキュリティまたは機能を危険または侵害させないようにする必要があります。  

#### 1.2.1 コンテンツセキュリティポリシー  

> [!NOTE]
> 記述されている機能を超えて拡張機能に変更を加えた場合は、コードに対するすべての変更が[Microsoft Edge のコンテンツセキュリティポリシー][MicrosoftEdgeContentSecurityPolicyRemoteScript]に準拠している必要があります。  例: 拡張機能では、リモートスクリプトをダウンロードせずに、説明した機能と一貫性がない方法でスクリプトを実行する必要があります。  

#### 望ましくない悪意のあるソフトウェアを1.2.2  

お客様の内線番号には、[望ましくない悪意][MicrosoftIdentifiesMalwareUnwantedApplications]のあるソフトウェアに関する Microsoft の条件で定義されたマルウェアを含めたり有効にしたりすることはできません  

#### 他のソフトウェアへの1.2.3 の依存関係  

お客さまの内線番号は、この機能を実現するために、統合されていないソフトウェア (別の製品、モジュール、サービス \ など) に依存することがあります。  

#### 1.2.4 拡張機能の更新  

Microsoft によって許可されていない限り、microsoft Edge のアドオンを介してのみ拡張機能を更新する必要があります。  

### 1.3 製品がテスト可能である  
拡張機能はテスト可能である必要があります。  以下の項目を含む、何らかの理由で拡張機能をテストできない場合は、この要件を満たすことができない可能性があります。  

#### 1.3.1 ユーザーの資格情報  
内線番号にログイン資格情報が必要な場合は、[**証明書のメモ**] フィールドを使って、デモ用のデモアカウントを提供してください。  

#### 1.3.2 サービスの可用性  

拡張機能でサーバーへのアクセスが必要な場合は、サーバーが正常に動作することを確認するためにサーバーが機能している必要があります。  

### 1.4 のユーザビリティ  

拡張機能には、以下のサブセクションに記載されているように、ユーザビリティのために拡張ストア標準を満たしている必要があります。  

#### プラットフォーム間の1.4.1 の互換性  

ダウンロード可能なすべてのデバイスとプラットフォームで、拡張機能に Microsoft Edge との互換性を持たせる必要があります。  互換性のないデバイスに拡張機能がダウンロードされた場合、その拡張機能と互換性があるために、デバイスが満たす必要のある要件の詳細をユーザーに示すメッセージが、起動時に検出されます。  

#### 1.4.2 のユーザーエクスペリエンス  

拡張機能はすぐに起動する必要があり、ユーザー入力に対する応答性を維持する必要があります。  拡張機能は、引き続き実行され、ユーザー入力に対する応答性を維持する必要があります。  延長は、予期せずに正常に終了する必要があります。  拡張機能は例外を処理し、例外が処理された後でもユーザー入力の応答性を維持する必要があります。  

### 1.5 個人情報  

個人情報にアクセスする拡張機能には、次の要件が適用されます。  個人情報には、ユーザーを識別するために使用する、またはその情報やデータに関連付けられている情報やデータがすべて含まれます。  

#### 1.5.1 は必要な場合にのみ個人情報を収集する  

拡張機能は、(web 閲覧アクティビティを含む) 個人情報の収集、アクセス、使用、または送信を行うことができます。必要なのは、目立つように公開されたユーザー向けの機能です。  

#### 1.5.2 プライバシーポリシーの管理  

拡張機能によって個人情報がアクセス、収集、または送信するかどうかに関係なく、法律で義務付けられている場合は、プライバシーポリシーを目立つように通知して、そのポリシーに準拠する必要があります。  お客様のプライバシーポリシーでは、お客様の内線番号にアクセス、収集、または送信された個人情報、その情報の使用方法、保存方法、セキュリティを保護する方法、および公開されている相手の種類を示す必要があります。  お客様のプライバシーポリシーには、ユーザーが情報を使用して共有し、情報にアクセスする方法、適用法および規制に準拠する必要があるコントロールについて説明する必要があります。  お客さまのプライバシーポリシーは、拡張機能に新機能を追加したときに最新の状態に維持する必要があります。  

Microsoft にプライバシーポリシーを提供している場合、お客様は、お客様の内線番号のユーザとプライバシーポリシーの共有を許可することに同意するものとします。  

#### サードパーティとのデータ共有1.5.3  

内線番号を使用しているユーザーの個人情報は、拡張機能または関連付けられたメタデータを使って、ユーザーからオプトインの同意を得た後で、外部のサービスまたはサードパーティに公開することができます。  オプトインの同意は、次のようにして、ユーザーが要求されたアクティビティのために、拡張機能のユーザーインターフェイスで明示的な権限を付与することを意味します。  

*   情報のアクセス方法、使用方法、共有方法、および公開されているユーザーの種類を示す方法について説明します。  
*   ユーザーに拡張機能のユーザーインターフェイスのメカニズムを提供します。このインターフェイスでは、後でアクセス許可とオプトインを取り消すオプションがあります。  

#### ユーザー以外の情報を共有する1.5.4  

内線番号またはメタデータを使用して、ユーザーの個人情報を外部のサービスまたはサードパーティに公開する場合、その情報が共有されているユーザーは内線番号のユーザーではありません。  

1.  個人情報を公開するには、書面による同意を得る必要があります。  
1.  情報が共有されているユーザーには、いつでも承諾の取り消しを許可する必要があります。  
1.  お客様のプライバシーポリシーは、この方法で個人情報を収集できることを明確に伝える必要があります。  
1.  適用法によって必要な場合は、この方法で情報を収集した個人を含め、個々のユーザーの個人情報を削除する必要があります。  
1.  拡張機能により、他のユーザーの個人情報へのアクセス権がユーザーに提供される場合は、この要件も適用されます。  

#### 1.5.5 で情報を安全に送信する  

拡張機能によって個人情報が収集、保存、または送信される場合最新の暗号化方法を使用して安全に行う必要があります。  

#### 機密性の高い情報を1.5.6  

内線番号の機能に関連していない場合、拡張機能は、健康や財務データなどの機密性の高い個人情報を収集、保存、または送信することはできません。  また、このような情報を収集、保存、または送信する前に、拡張機能によってエクスプレスユーザの同意を得る必要があります。  

### 1.6 のアクセス許可  

拡張機能には、機能するために必要なアクセス許可のみを要求する必要があります。  拡張機能のしくみについての説明を入力する必要があります。  拡張機能は、説明どおりに実行する必要があります。  拡張機能には、宣言されたとおりに実行して機能する必要がある機能以外にも、機能へのアクセス許可を要求することはできません。  

### 1.7 のローカライズ  

拡張機能がサポートするすべての言語の拡張機能をローカライズする必要があります。  拡張機能の記述のテキストは、宣言した各言語にローカライズする必要があります。  
拡張機能がローカライズされたバージョンで利用できない機能がある場合は、その拡張機能の説明にあるローカライズの制限を明確に記述するか、表示する必要があります。 拡張機能によって提供されるエクスペリエンスは、サポートされているすべての言語で同じである必要があります。  

### 1.8 財務取引  

製品に製品購入、月額プラン、仮想通貨、請求機能、または財務情報のキャプチャが含まれている場合以下のセクションの要件が適用されます。  

#### 1.8.1 有料機能  

拡張機能により、ユーザーはサードパーティの購入メカニズムまたは API を通じて購入したデジタルコンテンツまたはサービスを利用できる場合があります。  

物理的な商品またはサービスを購入するには、セキュリティで保護されたサードパーティの購入 API を使用する必要があります。  現実世界のギャンブルまたは慈善団体を含む、その他のサービスに関連した支払いには、セキュリティで保護されたサードパーティの購入 API を使用する必要があります。  

*   お客様の内線番号を使用して、慈善団体への協力、またはプロモーションの懸賞またはコンテストの実施に使用する場合は、適用法に準拠する必要があります。  
*   また、Microsoft がプロモーションの会またはスポンサーではないことを明確に示す必要があります。  
*   内線番号で販売されている製品サービスは、合法的な有効な通貨 (米ドル、ユーロなど)、あるいは任意の物理的な商品やサービスに換算することはできません。  

セキュリティで保護されたサードパーティ購入 API の使用には、次の要件が適用されます。  

*   トランザクションの時点で、またはユーザーから支払いや財務情報を収集する場合拡張機能では、commerce トランザクションプロバイダーを特定し、ユーザーを認証し、トランザクションの確認をユーザーに求める必要があります。  Commerce トランザクションプロバイダーは、財務交換のためのセキュリティで保護されたプラットフォームを維持します。  
*   拡張機能により、ユーザーにこの認証を保存する機能が提供されますが、ユーザーはすべてのトランザクションに対して認証を要求するか、または製品内のトランザクションを無効にすることができる必要があります。  
*   拡張機能でクレジットカード情報を収集する場合、またはクレジットカード情報を収集するサードパーティの支払いプロセッサを使用する場合、支払い処理は現在の PCI データセキュリティ規格 \ (PCI DSS \) に準拠している必要があります。  

#### 1.8.2 の有料機能の公開  

拡張機能と関連メタデータには、提供されている製品の購入の種類と価格の範囲に関する情報を提供する必要があります。  お客様には、ユーザーを誤解しないようにする必要があります。また、試用版の利用規約など、製品内のプロモーションやサービスの性質を明確にする必要があります。  ユーザーが作成したコンテンツへのアクセスが試用期間中に制限されている場合は、事前にユーザーに通知する必要があります。  さらに、拡張機能を使用すると、拡張機能で購入オプションを開始していることがユーザーにわかりやすくなります。  

### 1.9 通知  

内線番号は、通知のシステム設定を尊重する必要があります。  つまり、通知が Microsoft プッシュ通知サービス \ (MPNS \)、Windows プッシュ通知サービス \ (WNS \)、またはその他のいずれかのサービスによって提供されているかどうかに関係なく、ユーザーの広告と通知のプレゼンテーションは、ユーザーの設定と一貫している必要があります。  ユーザーが通知を無効にした場合、製品固有またはシステム全体のどちらでも、拡張機能は機能したままにしておく必要があります。  

製品で MPNS または WNS を使って通知を送信する場合は、次の要件に従う必要があります。  

#### 1.9.1 の一般的なガイダンス  

WNS または MPNS 経由で提供される通知は製品コンテンツと見なされ、すべてのアドオンカタログ開発者ポリシーの適用対象となります。  

#### 通知の所有権の1.9.2  

内線番号から開始された通知のソースを不明瞭にしたり、偽装したりする必要はありません。  

#### 機密情報や機密情報が1.9.3 ない  

ユーザーが機密または機密情報を検討している可能性がある場合は、通知に含めることはできません。  

#### 1.9.4 の用途 (通知の目的)  

内線番号から送信される通知は、その拡張機能、または Microsoft Edge のアドオンカタログで公開する他の拡張機能に関連付けられている必要があります。また、内線番号に関連していない種類のプロモーションメッセージを含めることはできません。  

### 1.10 広告の実施とコンテンツ  

広告に関連するすべてのアクティビティについて、次の要件が適用されます。  

#### 1.10.1 目的  

拡張機能のプライマリコンテンツはアドバタイズされていない必要があります。また、アドバタイズは内線の他のコンテンツと明確に区別する必要があります。  

#### 1.10.2 のポリシーと契約  

内線番号が表示される広告コンテンツは、 [Microsoft クリエイティブの検収ポリシー][MicrosoftAdvertisingCreativeAcceptancePolicies]に準拠している必要があります。  
拡張機能に広告が表示されている場合、表示されるすべてのコンテンツは、[アプリ開発者契約][MicrosoftAppDeveloperAgreement]とこのポリシーの広告要件に準拠している必要があります。  

#### 広告の1.10.3 品質  

*   拡張機能の主な目的は、ユーザーが広告をクリックしないようにすることです。  
*   お客様の内線番号は、表示される広告の表示、値、または品質に影響を与えるものではありません。  

#### 1.10.4 プロモーション  

[パートナーセンター][MicrosoftPartnerCenter]の広告キャンペーン機能を使用して、お客様の内線番号を購入または作成する場合は、関連するすべてのランディングページを含む、microsoft に提供するすべての広告マテリアルは、 [Microsoft のクリエイティブ仕様ポリシー][MicrosoftAdvertisingCreativeSpecifications]および[microsoft のクリエイティブ検収ポリシー][MicrosoftAdvertisingCreativeAcceptancePolicies]に準拠している必要があります。  

#### 関心を持った広告のオプトインをユーザーに通知する1.10.5  

お客様のプライバシーに関する声明または利用規約では、ユーザーが個人情報を広告サービスプロバイダに送信することをユーザーに知らせることができます。また、ユーザーが関心をお持ちの広告をオプトアウトする方法について説明する必要があります。  

#### 1.10.6 その他のガイドライン  

内線番号が13歳未満の子供に向けている場合は、[子供のオンラインプライバシー保護法][FTCChildrensPrivacy]で定義されています。この事実については[パートナーセンター][MicrosoftPartnerCenter]で通知する必要があります。また、内線に記載されているすべての広告コンテンツが13歳未満のお子様に適していることを確認してください。  

## 2コンテンツポリシー  

次のポリシーは、Microsoft Edge のアドオンで配布するために提供されているコンテンツとメタデータに適用されます (発行者名、内線名、内線番号アイコン、拡張説明、拡張スクリーンショット、拡張トレーラーとトレーラーのサムネイル、およびその他の拡張メタデータ)。  コンテンツは、拡張機能に含まれている画像、サウンド、ビデオ、テキスト、拡張機能を通じて公開されたエラーメッセージまたは広告、サーバーから配信されたもの、または拡張機能が接続するものを指します。  拡張機能と Microsoft Edge のアドオンは世界中で使用されるため、これらの要件は、地域および文化の基準に基づいて解釈および適用されます。  

### Microsoft Edge アドオンカタログの2.1 コンテンツ要件  

拡張子に付随して提出したメタデータおよびその他のコンテンツには、完成したコンテンツが含まれていない可能性があります。  
拡張ストア登録情報の要件を満たしていない申請は拒否または即座に削除されます。  

### 2.2 コンテンツ (名前、ロゴ、オリジナル、サードパーティなど)  

内線番号と関連付けられているメタデータ内のすべてのコンテンツは、お客様が最初に作成するか、またはサードパーティの権限所有者によって適切にライセンスを付与されているか、または法律で許可されている場合にのみ使用される必要があります。  

### 2.3 による被害のリスク  

#### 2.3.1 要件  

内線番号には、次の現実世界の活動を促進または glamorizes するコンテンツは含まれません。 \ (a) エクストリームまたはお客さまの暴力。\ (b) 人的権利違反。\ (c \) 違法な武器の作成または \ (d \) 個人、動物、または個人のプロパティに対して武器を使用します。  

#### 2.3.2 責任  

お客さまの内線番号は、次のようなものではありません。 \ (a \) は、discomfort、けがなど、エンドユーザーや他の人や動物に対する安全リスクをもたらすものではありません。または \ (b \) は、real または personal プロパティの損害または被害の原因となる可能性があります。  お客様は、すべての拡張機能の安全性テスト、証明書の取得、および適切な機能保護の実装に対してのみ責任を負います。  プラットフォームの安全性または安全な機能を無効にする必要があります。また、お客様は、お客様の内線番号に適用されている法的必須および業界標準の警告、通知、免責事項をすべて含める必要があります。  

### 2.4 中傷、Liベル、Slanderous、脅迫  

内線番号には、中傷、liベル、slanderous、脅迫などのコンテンツを含めることはできません。  

### 2.5 不快感を持つコンテンツ  

拡張機能と関連付けられたメタデータに、機密情報や不快感を与える可能性のあるコンテンツが含まれていない。  地域の法律または文化によっては、コンテンツは、特定の国/地域の機密または不快と見なされる場合があります。  さらに、お客様の内線番号と関連メタデータには、レース、ethnicity、国内の原産国、言語、性別、年齢、障碍、宗教、hatred の状態、その他のソーシャルグループのメンバーシップなど、差別、、または暴力の考慮事項に基づいたコンテンツを含めることはできません。  

### 2.6 アルコール、タバコ、薬物  

お客様の内線番号には、アルコールまたはタバコ製品または薬物の過大または glamorizes の使用に役立つコンテンツが含まれている必要があります。  

### 2.7 成人向けコンテンツ  

お客様の内線番号には、わいせつまたはアダルト向けのコンテンツを含めたり、表示したりすることはできません。  

### 2.8 で禁止されているコンテンツ、サービス、アクティビティ  

内線番号は、次の条件に従っている必要があります。  

*   内線番号には、コンテンツが含まれていたり、オンラインのギャンブルを促進するサービスが提供されている必要があります  オンラインギャンブルには、オンライン casinos、スポーツの賭け、lotteries、または、現金の賞品やその他の価値をもたらす技能が含まれています。  
*   内線番号やログイン制限を回避するなど、web サイトのコンテンツへの不正アクセスを提供することは禁じられています。  
*   内線番号は、著作権のあるコンテンツまたはメディアの不正アクセス、ダウンロード、ストリーミングを許可、許可、または有効にすることはできません。  
*   内線番号は、暗号化されていない必要があります。  

### 2.9 不正行為  

お客様の内線番号には、現実世界での違法行為を助長する、または glamorizes するコンテンツや機能を含めることはできません。  

### 不適切な不適切なコンテンツを2.10  

*   内線番号には、過大な言葉やお持ちの言葉は使用できません。  
*   拡張子には、"性的" と見なされるコンテンツを含めたり表示したりすることはできません。  

### 2.11 の国/地域固有の要件  

内線番号が対象としている国または地域に不快感を与えているコンテンツは許可されません。  地域の法律または文化によっては、コンテンツが特定の国/地域によって不快になっていると見なされることがあります。  一部の国/地域で不快感を与える可能性のあるコンテンツの例には、次のようなものがあります。  

**中国**  

*   禁止された性的コンテンツ  
*   紛争地域参照  
*   該当する地方法律で違法なコンテンツまたはサービスへのアクセスを提供または有効化する  

### 2.12 年齢区分  

#### 2.12.1 の成熟したコンテンツ  

拡張機能を[パートナーセンター][MicrosoftPartnerCenter]に提出するときに、"成熟" とマークする必要があるコンテンツが拡張機能に表示されるかどうかを指定する必要があります。  内線番号の評価を決定する際には、ユーザーが生成したコンテンツや広告など、アプリ内のすべてのコンテンツと、拡張機能にリンクされているコンテンツを考慮してください。  内線番号に "成熟していない" コンテンツが含まれていないことを示す場合は、この評価の正確さを維持する責任を負います。  お客様の内線番号に応じて、Microsoft Edge のアドオン開発者ポリシーのすべてのコンテンツ要件に従う必要があります。  

#### 2.12.2 の評価の変更  

割り当てられた評価よりも年齢評価に適している可能性があるコンテンツ (ユーザーが作成、販売、またはその他の web ベースコンテンツなど) を提供する場合は、コンテンツフィルターを使用するか、既存のアカウントでサインインして、ユーザーにそのコンテンツの受信をオプトインする必要があります。  

### 2.13 ビデオ  

記載されたプロモーション用ビデオを提出する場合は、このポリシーに記載されているすべてのコンテンツガイドラインに従う必要があります。  YouTube リンクを指定する場合は、埋め込む特定のビデオについてアドバタイズが無効になっていることを確認する必要があります。  YouTube で広告を有効または無効にする方法の詳細については、「 [support.google.com/youtube/answer/2531367?ref_topic=7072227][GoogleYoutubeAnswer2531367Topic7072227]と[support.google.com/youtube/answer/132596][GoogleYoutubeAnswer132596]」を参照してください。  

<!-- image links -->  

<!-- links -->  

[MicrosoftEdgeContentSecurityPolicyRemoteScript]: ./csp.md#relaxing-the-default-policy "既定のポリシーの緩和-コンテンツセキュリティポリシー \ (CSP \) |Microsoft ドキュメント"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "アプリ開発者契約 |Microsoft ドキュメント"  
[MicrosoftIdentifiesMalwareUnwantedApplications]: /windows/security/threat-protection/intelligence/criteria "Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを特定する方法を教えてください。Microsoft ドキュメント"  

[GoogleYoutubeAnswer2531367Topic7072227]: https://support.google.com/youtube/answer/2531367?ref_topic=7072227 "既定の広告の形式を設定する-YouTube のヘルプ"  
[GoogleYoutubeAnswer132596]: https://support.google.com/youtube/answer/132596 "埋め込みビデオに関する広告-YouTube のヘルプ"  
[FTCChildrensPrivacy]: https://www.ftc.gov/tips-advice/business-center/privacy-and-security/children%27s-privacy "子供のプライバシー-連邦取引委員会"  

[MicrosoftAdvertisingCreativeAcceptancePolicies]: https://about.ads.microsoft.com/solutions/ad-products/display-advertising/creative-acceptance-policies "クリエイティブな検収ポリシー-Microsoft 広告"  
[MicrosoftAdvertisingCreativeSpecifications]: https://about.ads.microsoft.com/solutions/ad-products/display-advertising/creative-specs "クリエイティブな仕様-Microsoft 広告"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  