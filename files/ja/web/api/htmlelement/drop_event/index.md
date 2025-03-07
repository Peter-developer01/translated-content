---
title: 'HTMLElement: drop イベント'
slug: Web/API/HTMLElement/drop_event
page-type: web-api-event
tags:
  - DOM
  - Drag Event
  - Drop
  - Event
  - HTML 5
  - Reference
  - drag and drop
browser-compat: api.HTMLElement.drop_event
translation_of: Web/API/HTMLElement/drop_event
---
{{APIRef}}

**`drop`** イベントは、要素または選択されたテキストが、妥当なドロップターゲットにドロップされたときに発生します。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">バブリング</th>
      <td>あり</td>
    </tr>
    <tr>
      <th scope="row">キャンセル</th>
      <td>可</td>
    </tr>
    <tr>
      <th scope="row">既定のアクション</th>
      <td>様々</td>
    </tr>
    <tr>
      <th scope="row">インターフェイス</th>
      <td>{{domxref("DragEvent")}}</td>
    </tr>
    <tr>
      <th scope="row">イベントハンドラープロパティ</th>
      <td>
        {{domxref("GlobalEventHandlers/ondrop", "ondrop")}}
      </td>
    </tr>
  </tbody>
</table>

## 例

### 最小限のドラッグ＆ドロップの例

この例では、コンテナーの中にドラッグ可能な要素を置いています。要素を掴んで、他のコンテナーの上にドラッグし、そして放してみましょう。

ここでは、 3 つのイベントハンドラーを使用しています。

- `dragstart` イベント ハンドラーでは、ユーザーがドラッグした要素へのリファレンスを取得します。
- ターゲットコンテナーの `dragover` イベントハンドラーでは、 `event.preventDefault()` を呼び出し、`drop` イベントを受信できるようにします。
- ドロップゾーンの `drop` イベントハンドラーでは、ドラッグ可能な要素を元のコンテナからドロップゾーンに移動する処理を行います。

ドラッグ＆ドロップのより完全な例については、[`drag`](/ja/docs/Web/API/HTMLElement/drag_event) イベントのページを参照してください。

#### HTML

```html
<div class="dropzone">
  <div id="draggable" draggable="true">
    この div はドラッグ可
  </div>
</div>
<div class="dropzone" id="droptarget"></div>
```

#### CSS

```css
body {
  /* 例でユーザーがテキストを選択するのを防ぐ */
  user-select: none;
}

#draggable {
  text-align: center;
  background: white;
}

.dropzone {
  width: 200px;
  height: 20px;
  background: blueviolet;
  margin: 10px;
  padding: 10px;
}
```

#### JavaScript

```js
let dragged = null;

const source = document.getElementById("draggable");
source.addEventListener("dragstart", event => {
  // ドラッグ中の要素の参照を保存
  dragged = event.target;
});

const target = document.getElementById("droptarget");
target.addEventListener("dragover", event => {
  // ドロップできるように既定の動作を停止
  event.preventDefault();
});

target.addEventListener("drop", event => {
  // 既定の動作（一部の要素でリンクとして開く）を行わないようにする。
  event.preventDefault();
  // ドラッグした要素を選択されたドロップターゲットに移動する
  if (event.target.className == "dropzone") {
    dragged.parentNode.removeChild(dragged);
    event.target.appendChild(dragged);
  }
});
```

#### 結果

{{EmbedLiveSample('A minimal drag and drop example')}}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- その他のドラッグ＆ドロップイベント:

  - {{domxref("HTMLElement/drag_event", "drag")}}
  - {{domxref("HTMLElement/dragstart_event", "dragstart")}}
  - {{domxref("HTMLElement/dragend_event", "dragend")}}
  - {{domxref("HTMLElement/dragover_event", "dragover")}}
  - {{domxref("HTMLElement/dragenter_event", "dragenter")}}
  - {{domxref("HTMLElement/dragleave_event", "dragleave")}}

- 他を対象としたこのイベント

  - {{domxref("Window")}}: {{domxref("Window/drop_event", "drop")}} イベント
  - {{domxref("Document")}}: {{domxref("Document/drop_event", "drop")}} イベント
  - {{domxref("SVGElement")}}: {{domxref("SVGElement/drop_event", "drop")}} イベント
