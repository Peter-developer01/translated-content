---
title: HTMLBodyElement
slug: Web/API/HTMLBodyElement
tags:
  - API
  - HTML DOM
  - Interface
  - Reference
translation_of: Web/API/HTMLBodyElement
---
{{APIRef("HTML DOM")}}

L'interface **`HTMLBodyElement`** des propriétés particulières (au-delà de celles de l'interface {{ domxref("HTMLElement") }} dont-elle hérite également) pour manipuler les éléments.

## Propriétés

_Propriétés hérite de son parent, {{domxref("HTMLElement")}} et de {{domxref("WindowEventHandlers")}}._

- {{domxref("HTMLBodyElement.aLink")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la couleur des liens hypertextes actifs.
- {{domxref("HTMLBodyElement.background")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la description de l'emplacement de la ressource d'image d'arrière-plan. Notez que ce n'est pas un URI, même si certaines anciennes versions de certains navigateurs s'y attendent.
- {{domxref("HTMLBodyElement.bgColor")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la couleur de fond du document.
- {{domxref("HTMLBodyElement.link")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la couleur des liens non visités.
- {{domxref("HTMLBodyElement.text")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la couleur de premier plan du texte.
- {{domxref("HTMLBodyElement.vLink")}} {{deprecated_inline}}
  - : Est un {{ domxref("DOMString") }} qui représente la couleur des liens visités.

## Méthodes

_Aucune méthode spécifique; méthodes hérite de ses parents, {{domxref("HTMLElement")}} et de {{domxref("WindowEventHandlers")}}._

## Les gestionnaires d'événements

_Pas de gestionnaire d'événement spécifique; gestionnaires d'événements hérite de ses parents, {{domxref("HTMLElement")}} et de {{domxref("WindowEventHandlers")}}._

- {{domxref("WindowEventHandlers.onafterprint")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("afterprint")}} est déclenché.
- {{domxref("WindowEventHandlers.onbeforeprint")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("beforeprint")}} est déclenché.
- {{domxref("WindowEventHandlers.onbeforeunload")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("beforeunload")}} est déclenché.
- {{domxref("WindowEventHandlers.onhashchange")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("hashchange")}} est déclenché.
- {{domxref("WindowEventHandlers.onlanguagechange")}} {{experimental_inline}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("languagechange")}} est déclenché.
- {{domxref("WindowEventHandlers.onmessage")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("message")}} est déclenché.
- {{domxref("WindowEventHandlers.onoffline")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("offline")}} est déclenché.
- {{domxref("WindowEventHandlers.ononline")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("online")}} est déclenché.
- {{domxref("WindowEventHandlers.onpagehide")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("pagehide")}} est déclenché.
- {{domxref("WindowEventHandlers.onpageshow")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("pageshow")}} est déclenché.
- {{domxref("WindowEventHandlers.onpopstate")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("popstate")}} est déclenché.
- {{domxref("WindowEventHandlers.onresize")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("resize")}} est déclenché.
- {{domxref("WindowEventHandlers.onstorage")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("storage")}} est déclenché.
- {{domxref("WindowEventHandlers.onunload")}}
  - : Est un {{event("Event_handlers", "event handler")}} représentant le code d'appel lorsque l'événement {{event("unload")}} est déclenché.

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- Élément HTML mise en œuvre par cette interface: {{ HTMLElement("body") }}
