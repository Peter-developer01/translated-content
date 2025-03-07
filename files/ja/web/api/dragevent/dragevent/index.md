---
title: DragEvent()
slug: Web/API/DragEvent/DragEvent
page-type: web-api-constructor
tags:
  - API
  - Constructor
  - DOM
  - Reference
  - drag and drop
browser-compat: api.DragEvent.DragEvent
translation_of: Web/API/DragEvent/DragEvent
---
{{APIRef("HTML Drag and Drop API")}}

このコンストラクターは、合成した {{domxref("DragEvent")}} オブジェクトを作成するために使用します。

このインターフェイスにはコンストラクターがありますが、有用な {{domxref("DataTransfer")}} オブジェクトは、ドラッグ＆ドロップの際にブラウザーが調整する処理とセキュリティモデルを持っているので、スクリプトから作成することはできません。

このインターフェイスは、 {{domxref("MouseEvent")}} および {{domxref("Event")}} のプロパティを継承しています。

## 構文

```js
new DragEvent(type)
new DragEvent(type, dragEventInit)
```

### 引数

- `type`
  - : イベント名を表す文字列です（[DragEvent のイベントの種類](/ja/docs/Web/API/DragEvent#イベントの種類)を参照）。

- `dragEventInit` {{optional_inline}}

  - : `DragEventInit` 辞書で、以下のフィールドがあります。

    - `"dataTransfer"`: オプションで既定値は `"null"` です。型は {{domxref("DataTransfer")}} です。

`DragEventInit` 辞書は {{domxref("MouseEvent.MouseEvent","MouseEventInit 辞書", "", 1)}}から継承しています。

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}
