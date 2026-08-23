# basic-ui
Simple JavaScript and CSS inspired by Google's Material Design.

**<span style="color:red">Not quite ready!</span> I recommend to use the links below now instead of copying the files.** This is how I currently use basic-UI in [Clean Link](https://lborgman.github.io/text-and-link/).

    <script src="https://lborgman.github.io/basic-ui/js/basic-ui.js" 
      type="module"></script>

    const modBasicUI =
      await import("https://lborgman.github.io/basic-ui/js/basic-ui.js");

    <!-- Asynchronous non-blocking CSS load -->
    <link href="https://lborgman.github.io/basic-ui/css/basic-ui.css" 
        rel="stylesheet" media="print"
        onload="this.media='all'" />


*I am planning to implement some more functions. If there is something you think would be in a library like this, then please till me!*

-----
Below are the currently exported JavaScript functions.
(The table is created with [jsdoc to markdown for web](https://lborgman.github.io/jsdoc2md-web/jsdoc2md-7.html).)

## Table of Contents

- [Helpers](#helpers)
  - [colorNameToHex(colorName) ⇒ <code>string|null</code>](#colornametohexcolorname-stringnull)
  - [getRootCssVarMs(cssVar) ⇒ <code>number</code>](#getrootcssvarmscssvar-number)
  - [isCssVariableDefined(variableName, className) ⇒ <code>boolean</code>](#iscssvariabledefinedvariablename-classname-boolean)
  - [nextPaint(fun) ⇒ <code>Promise<undefined></code>](#nextpaintfun-promise)
  - [waitForLayoutSilence(elements) ⇒ <code>Promise<WeakMap<HTMLElement, ResizeObserverEntry>></code>](#waitforlayoutsilenceelements-promise)
- [Visual elements](#visual-elements)
  - [addMenuAlt(dialogMenu, txt, fun)](#addmenualtdialogmenu-txt-fun)
  - [addMenuDivider(dialogMenu)](#addmenudividerdialogmenu)
  - [addXclose(dialog) ⇒ <code>HTMLButtonElement</code>](#addxclosedialog-htmlbuttonelement)
  - [mkDialogMenu() ⇒ <code>HTMLDialogElement</code>](#mkdialogmenu-htmldialogelement)
  - [mkFabButton(icon, title, small) ⇒ <code>HTMLButtonElement</code>](#mkfabbuttonicon-title-small-htmlbuttonelement)
  - [mkIconButton(icon, title) ⇒ <code>HTMLButtonElement</code>](#mkiconbuttonicon-title-htmlbuttonelement)
  - [mkXclose([funClose]) ⇒ <code>HTMLButtonElement</code>](#mkxclosefunclose-htmlbuttonelement)
  - [snackbar(message, duration)](#snackbarmessage-duration)
- [Visual helpers](#visual-helpers)
  - [applyMaterialTheme(baseColor, [isDark], [targetElement])](#applymaterialthemebasecolor-isdark-targetelement)
  - [closeMyDialog(elt)](#closemydialogelt)
  - [displayMenu(dialogMenu, objDialogPosition)](#displaymenudialogmenu-objdialogposition)
  - [showDialog(bdy, [retValFun], [buttons], [dialogClass]) ⇒ <code>Promise<any></code>](#showdialogbdy-retvalfun-buttons-dialogclass-promise)
  - [showDialogConfirm(bdy, [ok], [cancel])](#showdialogconfirmbdy-ok-cancel)

* * *

<a id="helpers"></a>
## Helpers

<a id="colornametohexcolorname-stringnull"></a>
### colorNameToHex(colorName) ⇒ <code>string|null</code>

Converts any valid CSS color string (name, rgb, hsl) to a hex string.

**Kind**: exported function

**Returns**: <code>string|null</code> - Hex color string (e.g., "#f97316") or null if invalid

| Param | Type | Description |
| --- | --- | --- |
| colorName | <code>string</code> | e.g., "orange", "deepskyblue", "papayawhip" |

* * *

<a id="getrootcssvarmscssvar-number"></a>
### getRootCssVarMs(cssVar) ⇒ <code>number</code>

**Kind**: exported function

**Returns**: <code>number</code>

| Param | Type | Description |
| --- | --- | --- |
| cssVar | <code>string</code> | - 500ms, 0.5s |

* * *

<a id="iscssvariabledefinedvariablename-classname-boolean"></a>
### isCssVariableDefined(variableName, className) ⇒ <code>boolean</code>

**Kind**: exported function

**Returns**: <code>boolean</code>

| Param | Type | Description |
| --- | --- | --- |
| variableName | <code>string</code> |  |
| className | <code>string</code> |  |

* * *

<a id="nextpaintfun-promise"></a>
### nextPaint(fun) ⇒ <code>Promise<undefined></code>

Resolves after the browser completes its next layout and paint cycle.

**Kind**: exported function

**Returns**: <code>Promise<undefined></code>

| Param | Type | Description |
| --- | --- | --- |
| fun | <code>function</code> |  |

* * *

<a id="waitforlayoutsilenceelements-promise"></a>
### waitForLayoutSilence(elements) ⇒ <code>Promise<WeakMap<HTMLElement, ResizeObserverEntry>></code>

Waits for a list of elements to settle their layouts.

**Kind**: exported function

**Returns**: <code>Promise<WeakMap<HTMLElement, ResizeObserverEntry>></code> - Resolves with a WeakMap mapping elements to their final entries.

| Param | Type | Description |
| --- | --- | --- |
| elements | <code>HTMLElement\|HTMLElement[]\|NodeList</code> | Single element or list of elements. |

* * *

<a id="visual-elements"></a>
## Visual elements

<a id="addmenualtdialogmenu-txt-fun"></a>
### addMenuAlt(dialogMenu, txt, fun)

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| dialogMenu | <code>HTMLDialogElement</code> |  |
| txt | <code>string</code> |  |
| fun | <code>function():void</code> |  |

* * *

<a id="addmenudividerdialogmenu"></a>
### addMenuDivider(dialogMenu)

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| dialogMenu | <code>HTMLDialogElement</code> |  |

* * *

<a id="addxclosedialog-htmlbuttonelement"></a>
### addXclose(dialog) ⇒ <code>HTMLButtonElement</code>

**Kind**: exported function

**Returns**: <code>HTMLButtonElement</code>

| Param | Type | Description |
| --- | --- | --- |
| dialog | <code>HTMLDialogElement</code> |  |

* * *

<a id="mkdialogmenu-htmldialogelement"></a>
### mkDialogMenu() ⇒ <code>HTMLDialogElement</code>

**Kind**: exported function

**Returns**: <code>HTMLDialogElement</code>

* * *

<a id="mkfabbuttonicon-title-small-htmlbuttonelement"></a>
### mkFabButton(icon, title, small) ⇒ <code>HTMLButtonElement</code>

**Kind**: exported function

**Returns**: <code>HTMLButtonElement</code>

| Param | Type | Description |
| --- | --- | --- |
| icon | <code>any</code> |  |
| title | <code>string</code> |  |
| small | <code>boolean</code> |  |

* * *

<a id="mkiconbuttonicon-title-htmlbuttonelement"></a>
### mkIconButton(icon, title) ⇒ <code>HTMLButtonElement</code>

**Kind**: exported function

**Returns**: <code>HTMLButtonElement</code>

| Param | Type | Description |
| --- | --- | --- |
| icon | <code>any</code> |  |
| title | <code>string</code> |  |

* * *

<a id="mkxclosefunclose-htmlbuttonelement"></a>
### mkXclose([funClose]) ⇒ <code>HTMLButtonElement</code>

**Kind**: exported function

**Returns**: <code>HTMLButtonElement</code>

| Param | Type | Description |
| --- | --- | --- |
| [funClose] | <code>function</code> |  |

* * *

<a id="snackbarmessage-duration"></a>
### snackbar(message, duration)

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string\|HTMLDivElement</code> |  |
| duration | <code>number</code> |  |

**Example**
```js
  snackbar('Microphone enabled');
```

* * *

<a id="visual-helpers"></a>
## Visual helpers

<a id="applymaterialthemebasecolor-isdark-targetelement"></a>
### applyMaterialTheme(baseColor, [isDark], [targetElement])

Applies the generated palette directly to an element.

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| baseColor | <code>string</code> | Color hex or name (e.g. "#4f46e5" or "indigo") |
| [isDark=false] | <code>boolean</code> | Set to true for dark mode tokens |
| [targetElement=document.documentElement] | <code>HTMLElement</code> | Optional target container element |

* * *

<a id="closemydialogelt"></a>
### closeMyDialog(elt)

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| elt | <code>HTMLElement</code> |  |

* * *

<a id="displaymenudialogmenu-objdialogposition"></a>
### displayMenu(dialogMenu, objDialogPosition)

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| dialogMenu | <code>HTMLDialogElement</code> |  |
| objDialogPosition | <code>Object</code> |  |

* * *

<a id="showdialogbdy-retvalfun-buttons-dialogclass-promise"></a>
### showDialog(bdy, [retValFun], [buttons], [dialogClass]) ⇒ <code>Promise<any></code>

Show a dialog.
To remove the upper right X close button
add CSS class "no-x-close-button" to bdy.

**Kind**: exported function

**Returns**: <code>Promise<any></code>

| Param | Type | Description |
| --- | --- | --- |
| bdy | <code>HTMLDivElement</code> |  |
| [retValFun] | <code>function\|undefined</code> |  |
| [buttons] | <code>undefined\|HTMLButtonElement[]</code> |  |
| [dialogClass] | <code>string</code> |  |

* * *

<a id="showdialogconfirmbdy-ok-cancel"></a>
### showDialogConfirm(bdy, [ok], [cancel])

**Kind**: exported function

| Param | Type | Description |
| --- | --- | --- |
| bdy | <code>HTMLDivElement</code> |  |
| [ok] | <code>string</code> |  |
| [cancel] | <code>string</code> |  |