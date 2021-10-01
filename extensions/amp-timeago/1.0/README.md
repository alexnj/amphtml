# Bento Timeago

## Usage

The Bento Timeago component provides fuzzy timestamps by formatting dates as time ago (for example, 3 hours ago). It can be used as a web component [`<bento-timeago>`](#web-component), or as a Preact/React functional component [`<BentoTimeago>`](#preactreact-component).

### Web Component

You must include each Bento component's required CSS library before adding custom styles in order to guarantee proper loading. Or use the lightweight pre-uprgrade styles available inline. See [Layout and Style](#layout-and-style).

The examples below demonstrate use of the `<bento-timeago>` web component.

#### Example: Import via npm

[example preview="top-frame" playground="false"]

Install via npm:

```sh
npm install @ampproject/bento-timeago
```

```javascript
import '@ampproject/bento-timeago';
```

[/example]

#### Example: Include via `<script>`

[example preview="top-frame" playground="false"]

```html
<head>
  <script async custom-element="bento-timeago" src="https://cdn.ampproject.org/v0/bento-timeago-1.0.js"></script>
  <style data-bento-boilerplate>
    bento-timeago {
      display: block;
      overflow: hidden;
      position: relative;
    }
  </style>
</head>
<bento-timeago
  id="my-timeago"
  datetime="2017-04-11T00:37:33.809Z"
  locale="en">
  Saturday 11 April 2017 00.37
</bento-timeago>
<div class="buttons" style="margin-top: 8px;">
  <button id='ar-button'>Change locale to Arabic</button>
  <button id='en-button'>Change locale to English</button>
  <button id='now-button'>Change time to now</button>
</div>

<script>
  (async () => {
    const timeago = document.querySelector('#my-timeago');
    await customElements.whenDefined('amp-timeago');

    // set up button actions
    document.querySelector('#ar-button').onclick = () => timeago.setAttribute('locale', 'ar');
    document.querySelector('#en-button').onclick = () => timeago.setAttribute('locale', 'en');
    document.querySelector('#now-button').onclick = () => timeago.setAttribute('datetime', 'now');
  })();
</script>
```

[/example]

#### Layout and style

Each Bento component has a small CSS library you must include to guarantee proper loading without [content shifts](https://web.dev/cls/). Because of order-based specificity, you must manually ensure that stylesheets are included before any custom styles.

```html
<link rel="stylesheet" type="text/css" href="https://cdn.ampproject.org/v0/bento-timeago-1.0.css">
```

Alternatively, you may also make the light-weight pre-upgrade styles available inline:

```html
<style data-bento-boilerplate>
  bento-timeago {
    display: block;
    overflow: hidden;
    position: relative;
  }
</style>
```

**Container type**

The `bento-timeago` component has a defined layout size type. To ensure the component renders correctly, be sure to apply a size to the component and its immediate children (slides) via a desired CSS layout (such as one defined with `height`, `width`, `aspect-ratio`, or other such properties):

```css
bento-timeago {
  height: 500px;
  width: 100px;
}
```

#### Attributes

##### `datetime`

The required `datetime` attribute sets the date and time. The value must be an [ISO datetime](https://www.w3.org/QA/Tips/iso-date).

-   Express time in UTC (Coordinated Universal Time): `2017-03-10T01:00:00Z`
-   Express in local time with a time zone offset: `2017-03-09T20:00:00-05:00`

##### `locale` (optional)

The local default is `en`. Add the `locale` attribute and specify one of the following values to chance the local.

-   `ar` (Arabic)
-   `be` (Belarusian)
-   `bg` (Bulgarian)
-   `bn-IN` (Bangla)
-   `ca` (Catalan)
-   `cs` (Czech)
-   `da` (Danish)
-   `de` (German)
-   `el` (Greek)
-   `en` (English)
-   `en-short` (English - short)
-   `es` (Spanish)
-   `eu` (Basque)
-   `fa` (Persian - Farsi)
-   `fi` (Finnish)
-   `fr` (French)
-   `gl` (Galician)
-   `he` (Hebrew)
-   `hi-IN` (Hindi)
-   `hu` (Hungarian)
-   `id-ID` (Malay)
-   `it` (Italian)
-   `ja` (Japanese)
-   `ka` (Georgian)
-   `ko` (Korean)
-   `ml` (Malayalam)
-   `my` (Burmese - Myanmar)
-   `nb-NO` (Norwegian Bokmål)
-   `nl` (Dutch)
-   `nn-NO` (Norwegian Nynorsk)
-   `pl` (Polish)
-   `pt-BR` (Portuguese)
-   `ro` (Romanian)
-   `ru` (Russian)
-   `sq` (Albanian)
-   `sr` (Serbian)
-   `sv` (Swedish)
-   `ta` (Tamil)
-   `th` (Thai)
-   `tr` (Turkish)
-   `uk` (Ukrainian)
-   `vi` (Vietnamese)
-   `zh-CN` (Chinese)
-   `zh-TW` (Taiwanese)

##### `cutoff`

Add the `cutoff` attribute to display the date specified in the `datatime` attribute after passing the specified date in seconds.

#### Styling

You may use the `bento-timeago` element selector to style the component.

### Preact/React Component

The examples below demonstrates use of the `<BentoTimeago>` as a functional component usable with the Preact or React libraries.

#### Example: Import via npm

[example preview="top-frame" playground="false"]

Install via npm:

```sh
npm install @ampproject/bento-timeago
```

```javascript
import React from 'react';
import { BentoTimeago } from '@ampproject/bento-timeago/react';
import '@ampproject/bento-timeago/styles.css';
function App() {
  return (
    <BentoTimeago
      datetime="2017-04-11T00:37:33.809Z"
      locale="en"
    >
      Saturday 11 April 2017 00.37
    </BentoTimeago>
  );
}
```

[/example]

#### Props

##### `datetime`

The required `datetime` prop sets the date and time. The value must be an [ISO datetime](https://www.w3.org/QA/Tips/iso-date).

-   Express time in UTC (Coordinated Universal Time): `2017-03-10T01:00:00Z`
-   Express in local time with a time zone offset: `2017-03-09T20:00:00-05:00`

##### `locale` (optional)

The local default is `en`. Add the `locale` attribute and specify one of the following values to chance the local.

-   `ar` (Arabic)
-   `be` (Belarusian)
-   `bg` (Bulgarian)
-   `bn-IN` (Bangla)
-   `ca` (Catalan)
-   `cs` (Czech)
-   `da` (Danish)
-   `de` (German)
-   `el` (Greek)
-   `en` (English)
-   `en-short` (English - short)
-   `es` (Spanish)
-   `eu` (Basque)
-   `fa` (Persian - Farsi)
-   `fi` (Finnish)
-   `fr` (French)
-   `gl` (Galician)
-   `he` (Hebrew)
-   `hi-IN` (Hindi)
-   `hu` (Hungarian)
-   `id-ID` (Malay)
-   `it` (Italian)
-   `ja` (Japanese)
-   `ka` (Georgian)
-   `ko` (Korean)
-   `ml` (Malayalam)
-   `my` (Burmese - Myanmar)
-   `nb-NO` (Norwegian Bokmål)
-   `nl` (Dutch)
-   `nn-NO` (Norwegian Nynorsk)
-   `pl` (Polish)
-   `pt-BR` (Portuguese)
-   `ro` (Romanian)
-   `ru` (Russian)
-   `sq` (Albanian)
-   `sr` (Serbian)
-   `sv` (Swedish)
-   `ta` (Tamil)
-   `th` (Thai)
-   `tr` (Turkish)
-   `uk` (Ukrainian)
-   `vi` (Vietnamese)
-   `zh-CN` (Chinese)
-   `zh-TW` (Taiwanese)

##### `cutoff`

Add the `cutoff` prop to display the date specified in the `datatime` attribute after passing the specified date in seconds.
