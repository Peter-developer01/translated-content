---
title: Firefox 71 for Developers
slug: Mozilla/Firefox/Releases/71
tags:
  - '71'
  - Firefox
  - Mozilla
  - Release
translation_of: Mozilla/Firefox/Releases/71
---
{{FirefoxSidebar}}

Firefox 71 は、米国時間 2019 年 12 月 3 日 にリリースされました。このページでは、開発者に影響する Firefox 71 の変更点をまとめています。

## ウェブ開発者向けの変更点一覧

### 開発者ツール

[コンソール](/ja/docs/Tools/Web_Console):

- コンソールの [マルチラインモード](/ja/docs/Tools/Web_Console/The_command_line_interpreter#Multi-line_mode) をデフォルトで有効にしました。
- コンソールの設定項目が、新しい [ツールバーの設定メニュー](/ja/docs/Tools/Web_Console/Opening_the_Web_Console#Toolbar) に統合されました ({{bug(1523868)}})。

[JavaScript デバッガー](/ja/docs/Tools/Debugger):

- [インラインの変数プレビュー](/ja/docs/Tools/Debugger/How_to/Set_a_breakpoint#Inline_variable_preview) を有効にしました ({{bug(1576679)}})。
- as is the ability to [イベントのタイプによるフィルタリング](/ja/docs/Tools/Debugger/Set_event_listener_breakpoints#Filter_by_event_type) と同様に、[イベントのログ記録](/ja/docs/Tools/Debugger/Set_event_listener_breakpoints#Logging_on_events) が可能になりました ({{bug(1110276)}})。
- デバッガーの新しい [一時停止のオーバーレイ](/ja/docs/Tools/Debugger/How_to/Step_through_code#Pause_on_breakpoints_overlay) を、設定項目 `devtools.debugger.features.overlay` を使用して無効化できるようになりました ({{bug(1579768)}})。
- デバッガーを開く新しい [キーボードショートカット](/ja/docs/Tools/Keyboard_shortcuts) が使用可能になりました: Linux/Windows では&#x20;

  <kbd>Ctrl</kbd>

  &#x20;\+&#x20;

  <kbd>Shift</kbd>

  &#x20;\+&#x20;

  <kbd>Z</kbd>

  、macOS では&#x20;

  <kbd>Cmd</kbd>

  &#x20;\+&#x20;

  <kbd>Opt</kbd>

  &#x20;\+&#x20;

  <kbd>Z</kbd>

  &#x20;です ({{bug(1583042)}})。

- [DOM Mutation のブレークポイント](/ja/docs/Tools/Debugger/Break_on_DOM_mutation) で一時停止すると、ブレークポイントを持つ DOM ノードや (存在すれば) 追加/削除された子ノードを表示するようになりました ({{bug(1576145)}})。
- [整形されたソース](/ja/docs/Tools/Debugger/How_to/Pretty-print_a_minified_file) 内の位置が、整形した後やインスペクターの [イベントリスナーのツールチップ](/ja/docs/Tools/Page_Inspector/How_to/Examine_event_listeners) からジャンプしたときも正確になりました ({{bug(1500222)}})。

[ネットワークモニター](/ja/docs/Tools/Network_Monitor):

- [Web sockets インスペクター](/ja/docs/Tools/Network_Monitor/Inspecting_web_sockets) をデフォルトで有効化しました ({{bug(1573805)}})。
- 要求/応答のボディ、ヘッダー、Cookie の [全文検索](/ja/docs/Tools/Network_Monitor/request_list#Search_in_requests) が可能になりました。
- 読み込み時に [特定の URL をブロックする](/ja/docs/Tools/Network_Monitor/request_list#Blocking_specific_URLs) パターンを入力できるようになりました。
- [タイミングタブ](/ja/docs/Tools/Network_Monitor/request_details#Timings) で、{{httpheader("Server-Timing")}} ヘッダーで送信したタイミングデータを表示するようになりました ({{bug(1403051)}})。

[インスペクター](/ja/docs/Tools/Page_Inspector):

- 色の値を持つ CSS 変数の定義の隣に、色見本を表示するようになりました ({{bug(1456167)}})。
- {{cssxref(":visited")}} のスタイルを CSS ルールビューで表示するようになりました ({{bug(713106)}})。

### CSS

- CSS Grid Level 2 から値 [subgrid](/ja/docs/Web/CSS/CSS_Grid_Layout/Subgrid) を、{{cssxref("grid-template-columns")}} および {{cssxref("grid-template-rows")}} に追加しました ({{bug(1580894)}})。
- [段組みレイアウト](/ja/docs/Web/CSS/CSS_Columns) で {{cssxref("column-span")}} をサポートしました ({{bug(1426010)}})。
- {{cssxref("clip-path")}} で `path()` の値をサポートしました ({{bug(1488530)}})。
- {{htmlelement("img")}} 要素の `height` および `width` HTML 属性を、内部の {{cssxref("aspect-ratio")}} プロパティにマッピングしました ({{bug(1585637)}})。[この機能について、MDN のガイドをご覧ください](/ja/docs/Web/Media/images/aspect_ratio_mapping)。

#### 廃止

- CSS Radial Gradients が、負の値の半径を受け入れないようになりました ({{bug(1583736)}})。[サイト互換性情報の記事](https://www.fxsitecompat.dev/docs/2019/css-radial-gradients-no-longer-accept-negative-radii/) をご覧ください。

### JavaScript

- {{jsxref("Promise.allSettled()")}} メソッドをサポートしました ({{bug(1549176)}})。このメソッドは、先のコードを実行する前に promise のセットに含まれるすべての promise が解決または拒否されるまで待つことを容易にします。

#### 廃止

- Array の非標準のジェネリックメソッドを、Firefox 71 で削除しました ({{bug(1222547)}})。これらは始めに Firefox 1.5 ([JavaScript 1.6](/ja/docs/Web/JavaScript/New_in_JavaScript/1.6)) で導入されて、Firefox 68 から非推奨になりました。配列状のオブジェクトで Array のジェネリックメソッドを使用している場合は、[`Array.from()`](/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/from) を使用してオブジェクトを適切な配列に変換して、標準のメソッドを使用するようにしてください。

### MathML

- [MathML 要素](/ja/docs/Web/MathML/Element) が MathML DOM を実装しました。クラスは {{domxref("MathMLElement")}} です。例えば適切な MathML DOM と、`mathmlEl.style`、グローバルイベントハンドラーを使用できます。従来は MathML 要素が {{domxref("Element")}} クラスのみ実装していました ({{bug(1571487)}})。

### API

#### 新規 API

[Media Session API](/ja/docs/Web/API/Media_Session_API) を部分的に実装しました。この API は、メディアの再生状態に関するオペレーティングシステムの情報をコンテンツと共有するための標準的な仕組みを提供します。これはアーティスト、アルバム、トラック名、あるいはアルバムのアートワークといったメタデータを含みます ({{bug(1580602)}})。

またこの API は、デバイスのメディア操作 (再生、停止、シークボタンなど) がユーザーによって行われたときに通知を受ける手段も提供します。このために {{domxref("MediaSession")}} インターフェイスを部分的に実装して、現在再生しているメディアのメタデータを設定および取得する機能や {{domxref("MediaSession.setActionHandler", "setActionHandler()")}} メソッドをサポートしました。`MediaSession` API へアクセスするには、{{domxref("navigator.mediaSession")}} プロパティを使用してください。

#### DOM

- {{domxref("StaticRange.StaticRange()", "StaticRange()")}} コンストラクターをサポートしました ({{bug(1575980)}})。
- MathML の {{domxref("MathMLElement")}} インターフェイスを実装しました ({{bug(1571487)}})。

#### メディア、Web Audio、WebRTC

- {{domxref("MediaRecorder")}} インターフェイスに {{domxref("MediaRecorder.audioBitsPerSecond", "audioBitsPerSecond")}} および {{domxref("MediaRecorder.videoBitsPerSecond", "videoBitsPerSecond")}} プロパティを実装しました ({{bug(1514158)}})。

#### Canvas と WebGL

- {{domxref("OVR_multiview2")}} および {{domxref("OES_fbo_render_mipmap")}} WebGL 拡張をデフォルトで公開しました ({{bug(1584277)}}, {{bug(1583878)}})。

#### 廃止

{{domxref("DataTransfer")}} の、非標準のメンバーを削除しました ({{bug(1345192)}}):

- {{domxref("DataTransfer.mozItemCount")}}
- {{domxref("DataTransfer.mozClearDataAt()")}}
- {{domxref("DataTransfer.mozGetDataAt()")}}
- {{domxref("DataTransfer.mozSetDataAt()")}}
- {{domxref("DataTransfer.mozTypesAt()")}}

### WebDriver conformance (Marionette)

- `WebDriver:TakeScreenshot` および `WebDriver:TakeElementScreenshot` コマンドを、未処理のプロンプトの動作設定を尊重するように更新しました ({{bug(1584927)}})。
- `Marionette:Quit` コマンドを、Firefox 以外の Gecko 駆動アプリケーションも終了または再起動できるように更新しました ({{bug(1298921)}})。
- Android の GeckoView ベースブラウザーで、セッション機能で返される `browserName` が常に `firefox` になります ({{bug(1587364)}})。

## アドオン開発者向けの変更点

### API の変更点

- {{WebExtAPIRef("downloads.download")}} が、以下の HTTP レスポンスコードをエラーとして識別および報告するようになりました:

  - 404 で `SERVER_BAD_CONTENT` を返します
  - 403 で `SERVER_FORBIDDEN` を返します
  - 402 および Proxy 407 で `SERVER_UNAUTHORIZED` を返します
  - 上記以外の 400 で `SERVER_FAILED` を返します ({{bug(1576333)}})。

- {{WebExtAPIRef("downloads.download")}} の省略可能な `options` 引数に、`allowHttpErrors` プロパティを含むようになりました。この `boolean` フラグを `true` に設定すると、HTTP エラーが発生した後もダウンロードを続けることができます。`false` に設定すると HTTP エラーが発生した際にダウンロードをキャンセルします。既定値は `false` です ({{bug(1578955)}})。

#### 廃止

- [`proxy.register()`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/proxy/register "This method has been deprecated in Firefox 68 and will be removed from Firefox 71. In Firefox 68 or later, calling this method logs an error message to the console:") および [`proxy.unregister()`](/ja/docs/Mozilla/Add-ons/WebExtensions/API/proxy/unregister "This method has been deprecated in Firefox 68 and will be removed from Firefox 71. In Firefox 68 or later, calling this method logs an error message to the console:") 関数を削除しました ({{bug(1443259)}})。要求のプロキシ使用を制御するには {{WebExtAPIRef("proxy.onRequest")}} を使用してください。

## 関連情報

- Hacks ブログのリリース記事: [Firefox 71: A year-end arrival](https://hacks.mozilla.org/2019/12/firefox-71-a-year-end-arrival/)

## 過去のバージョン

{{Firefox_for_developers(70)}}
