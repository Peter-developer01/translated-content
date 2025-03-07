---
title: Push API
slug: Web/API/Push_API
tags:
  - API
  - Experimental
  - Landing
  - Notifications
  - Push
  - Reference
  - サービスワーカー
  - プッシュ通知
translation_of: Web/API/Push_API
---
{{ApiRef("Push API")}}

**Push API** は、ウェブアプリケーションがサーバーからメッセージ (プッシュ通知) を受信できるようにします。ウェブアプリケーションがフォアグランド状態かどうか、読み込まれているかどうかに関わらず利用できます。開発者は、オプトインしたユーザーへ非同期の通知と更新を届けることができ、タイムリーな新着コンテンツによってユーザーの関心を得られるでしょう。

## プッシュ通知の概念と使い方

> **Warning:** PushManager へのサブスクリプションを実装する場合、アプリで CSRF/XSRF 問題を起こさないように保護することが非常に重要です。詳しくは以下の記事を参照してください。
>
> - [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
> - [Preventing CSRF and XSRF Attacks](https://blog.codinghorror.com/preventing-csrf-and-xsrf-attacks/)

アプリがプッシュ通知メッセージを受信するために、アプリで[サービスワーカー](/ja/docs/Web/API/Service_Worker_API)が動作している必要があります。サービスワーカーが動作している時に、 {{domxref("PushManager.subscribe()")}} を利用してプッシュ通知に加入することができます。

返値の {{domxref("PushSubscription")}} には、プッシュ通知メッセージの配信に必要な情報であるエンドポイントとデータ送信用の暗号キーがすべて含まれています。

プッシュ通知メッセージを受信すると、そのメッセージを扱うためのサービスワーカーが起動します。これは、 {{domxref("ServiceWorkerGlobalScope.onpush")}} イベントハンドラーへ配信されます。これにより、例えば ({{domxref("ServiceWorkerRegistration.showNotification()")}} を使用して) 受信した通知を表示するなど、アプリケーションがプッシュ通知の受信に応じた動作ができます。

各サブスクリプションは、サービスワーカーに対して固有です。サブスクリプションのエンドポイントは、固有の [capability URL](https://www.w3.org/TR/capability-urls/) です。サブスクリプションのエンドポイント URL はアプリケーションにメッセージを送るために不可欠な情報です。エンドポイント URL は秘密にしておく必要があります。さもないと、他のアプリケーションがあなたのアプリケーションにプッシュ通知メッセージを送ることができてしまいます。

プッシュ通知メッセージの配信のためにサービスワーカーを動作させると、特にバッテリーなどのリソースを消費します。これを扱う方式はブラウザーごとに異なっており、現在標準となる仕組みはありません。 Firefox も Chrome も通知を生成するプッシュ通知メッセージの数に制限を設けていません。 Firefox は通知を表示しないアプリケーションに送信されるプッシュ通知メッセージの数に制限 (クォータ) を設けていますが、 Chrome には制限がありません。この制限数は、ウェブサイトを訪れるたびに更新されます。

## インターフェイス

- {{domxref("PushEvent")}}
  - : {{domxref("ServiceWorker")}} の[グローバルスコープ](/ja/docs/Web/API/ServiceWorkerGlobalScope) に送られるプッシュアクションを表します。これは、アプリケーションから {{domxref("PushSubscription")}} へ送られる情報を含んでいます。
- {{domxref("PushManager")}}
  - : プッシュ通知のリクエスト URL といった、サードパーティのサーバーからプッシュ通知を受け取るための手段を提供します。
- {{domxref("PushMessageData")}}
  - : サーバーから送られたプッシュ情報にアクセスする手段を提供し、受信したデータを操作するメソッドを含みます。
- {{domxref("PushSubscription")}}
  - : サブスクリプションのエンドポイント URL を提供し、プッシュサービスから購読を解除できるようにします。
- {{domxref("PushSubscriptionOptions")}}
  - : プッシュサブスクリプションに関連付けられたオプションを表します。

## サービスワーカーへの追加機能

以下の [Service Worker API](/ja/docs/Web/API/Service_Worker_API) への追加機能は、 Push API 仕様に含まれています。これらは、プッシュ通知メッセージを使用するためのエントリーポイントを提供するため、および、プッシュとサブスクリプション変更イベントの監視と応答のための追加です。

- {{domxref("ServiceWorkerRegistration.pushManager")}} {{readonlyinline}}
  - : 購読を含むサブスクリプションの管理、アクティブなサブスクリプションの取得、プッシュ権限状態の取得を行う {{domxref("PushManager")}} インターフェイスへの参照を返します。これは、プッシュ通知メッセージを使用するためのエントリーポイントです。
- {{domxref("ServiceWorkerGlobalScope.onpush")}}
  - : {{Event("push")}} イベントが発生する度に発動します。これは、サーバーがプッシュしたメッセージを受信する度に起こります。
- {{domxref("ServiceWorkerGlobalScope.onpushsubscriptionchange")}}
  - : {{Event("pushsubscriptionchange")}} イベントが発生する度に発動するイベントハンドラです。例えば、プッシュサブスクリプションが無効になったり、無効になりつつある時 (即ち、プッシュサーバーが有効期限を設定している場合) です。

## 例

Mozilla の [ServiceWorker Cookbook](https://serviceworke.rs/) は便利なプッシュ通知の例をたくさん揃えています。

## 仕様書

| 仕様書                           | 状態                         | 備考     |
| -------------------------------- | ---------------------------- | -------- |
| {{SpecName("Push API")}} | {{Spec2("Push API")}} | 初回定義 |

## ブラウザーの互換性

### `PushEvent`

{{Compat("api.PushEvent")}}

### `PushMessageData`

{{Compat("api.PushMessageData")}}

## 関連情報

- [Sending VAPID identified WebPush Notifications via Mozilla’s Push Service](https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service/)
- [Web Push Notifications: Timely, Relevant, and Precise](https://developers.google.com/web/fundamentals/engage-and-retain/push-notifications/), Joseph Medley
- [Service Worker API](/ja/docs/Web/API/Service_Worker_API)

{{DefaultAPISidebar("Push API")}}
