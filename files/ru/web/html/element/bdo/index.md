---
title: '<bdo>: The Bidirectional Text Override element'
slug: Web/HTML/Element/bdo
tags:
  - направление текста
translation_of: Web/HTML/Element/bdo
---
{{HTMLRef}}

**HTML-элемент переопределения двунаправленного текста** (**`<bdo>`**) переопределяет текущее направление текста так, что текст внутри отображается в другом направлении.

{{EmbedInteractiveExample("pages/tabbed/bdo.html", "tabbed-standard")}}

Текстовые символы рисуются от заданной точки в указанном направлении; индивидуальная ориентация символов не меняется (к примеру, символы не зеркалятся).

| [Категории контента](/ru/docs/HTML/Content_categories) | [Потоковый контент](/ru/docs/HTML/Content_categories#Flow_content), [фразовый контент](/ru/docs/HTML/Content_categories#Phrasing_content), palpable content.                           |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Допустимый контент                                     | [Фразовый контент](/ru/docs/HTML/Content_categories#Phrasing_content).                                                                                                                 |
| Закрывающий тег                                        | {{no_tag_omission}}                                                                                                                                                               |
| Допустимые родители                                    | Все элементы, принимающие [фразовый контент](/ru/docs/HTML/Content_categories#Phrasing_content),                                                                                       |
| Допустимые ARIA-роли                                   | Любый                                                                                                                                                                                  |
| DOM interface                                          | {{domxref("HTMLElement")}} до Gecko 1.9.2 (Firefox 4) включительно, Firefox реализует интерфейс [`HTMLSpanElement`](/en-US/docs/Web/API/HTMLSpanElement) для этого элемента. |

## Атрибуты

Этот элемент поддерживает [глобальные атрибуты](/ru/docs/HTML/Global_attributes).

- {{htmlattrdef("dir")}}
  - : Направление, в котором должен отображаться текст внутри элемента. Возможные значения:\* `ltr`: Указывает, что текст должен идти слева направо.
    - `rtl`: Указывает, что текст должен идти справа налево.

## Примеры

```html
<!-- Переключение направления текста -->
<p>This text will go left to right.</p>
<p><bdo dir="rtl">This text will go right
to left.</bdo></p>
```

### Результат

{{EmbedLiveSample('Примеры')}}

## Примечания

Спецификация HTML 4 не указывала события для этого элемента; они были добавлены в XHTML.

## Спецификации

{{Specifications}}

## Поддержка браузерами

{{Compat}}
