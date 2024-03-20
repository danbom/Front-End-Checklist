<h1 align="center">
<br>
  <img src="https://raw.githubusercontent.com/thedaviddias/Front-End-Checklist/master/data/images/logo-front-end-checklist.jpg" alt="Front-End Checklist" width="130">
  <br>
    <br>
  프론트엔드 체크리스트
  <br>
</h1>

---
<h3 align="center">🚨 Currently working on new version of frontendchecklist.io,<br>feel free to <a href="https://github.com/thedaviddias/Front-End-Checklist/discussions/513">discuss</a> any feature you would like to see. Thanks for your support!</h3>

---

<h4 align="center">The Front-End Checklist is an exhaustive list of all elements you need to have / to test before launching your website / HTML page to production.</h4>

<p align="center">
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome">
  </a>
    <a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg?style=flat-square" alt="Contributors">
  </a>
  <a href="https://github.com/thedaviddias/Front-End-Checklist/">
    <img src="https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg?style=flat-square" alt="Front‑End_Checklist followed">
  </a>
    <a href="https://creativecommons.org/publicdomain/zero/1.0/">
    <img src="https://img.shields.io/badge/license-CC0-green.svg?style=flat-square" alt="CC0">
  </a>
</p>

<p align="center">
  <a href="#how-to-use">How To Use</a> • <a href="#contributing">Contributing</a> • <a href="https://frontendchecklist.io">Website</a> • <a href="https://www.producthunt.com/posts/front-end-checklist">Product Hunt</a>
</p>
<p align="center">
    <span>Other Checklists:</span>
    <br>
  <a href="https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-">🎮 Front-End Performance Checklist</a> • <a href="https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist">💎 Front-End Design Checklist</a>
</p>


It is based on Front-End developers' years of experience, with the additions coming from some other open-source checklists.

---

## How to use?

All items in the **Front-End Checklist** are required for the majority of the projects, but some elements can be omitted or are not essential (in the case of an administration web app, you may not need RSS feed for example). We choose to use 3 levels of flexibility:

All items in the Front-End Checklist are necessary for the majority of projects, but some elements can be omitted or are not essential. For example, in an administration web app, you may not need an RSS feed. We have categorized the flexibility into three levels:

![Low][low_img] indicates that the item is recommended but can be omitted in certain situations.
![Medium][medium_img] indicates that the item is highly recommended but can potentially be omitted in very specific cases. However, omitting these elements can negatively impact performance or SEO.
![High][high_img] indicates that the item cannot be omitted under any circumstances. Removing these elements may result in page malfunctions or cause accessibility and SEO issues. Testing should prioritize these elements first.



Some resources possess an emoticon to help you understand which type of content / help you may find on the checklist:

* 📖: documentation or article
* 🛠: online tool / testing tool
* 📹: media or video content

> You can contribute to the ***Front-End Checklist App*** reading the [CONTRIBUTING.md file](https://github.com/thedaviddias/Front-End-Checklist/blob/master/CONTRIBUTING.md) which explains everything about the project.

---

## Head

> **참고:** HTML 문서의 <head>에서 찾을 수 있는 모든 것에 대한 목록을 [여기](https://github.com/joshbuchea/HEAD)에서 찾을 수 있습니다.

### 메타 태그

* [ ] **Doctype:** ![High][high_img] Doctype은 HTML5이며 모든 HTML 페이지의 맨 위에 있습니다.

```html
<!doctype html> <!-- HTML5 -->
```

> * 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*다음 2개의 메타 태그(Charset 및 Viewport)는 head 태그 내에서 가장 먼저 와야 합니다.*

* [ ] **Charset:** ![High][high_img] 문자 인코딩(UTF-8)이 올바르게 선언되었습니다.

```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```

* [ ] **Viewport:** ![High][high_img] 뷰포트가 올바르게 선언되었습니다.

```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

* [ ] **Title:** ![High][high_img] 모든 페이지에는 타이틀이 사용됩니다 (SEO: Google은 제목에 사용된 문자의 픽셀 너비를 계산하고 472에서 482 픽셀 사이에서 자릅니다. 평균 문자 제한은 약 55자입니다).

```html
<!-- Document Title -->
<title>Page Title less than 55 characters</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** ![High][high_img] 메타 설명이 제공되었으며, 이는 고유하며 150자를 초과하지 않습니다.

```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```

> * 📖 [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** ![Medium][medium_img] 각 파비콘이 만들어졌으며 올바르게 표시됩니다. 만약 `favicon.ico`만 가지고 있다면, 이를 사이트의 루트에 둡니다. 보통은 아무런 마크업을 사용하지 않아도 됩니다. 그러나 아래의 예시처럼 링크를 걸어두는 것이 좋습니다. `.ico` 형식 대신 **PNG 형식이 권장됩니다**. (크기: 32x32px).

```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Web App Meta:** ![Low][low_img] Apple 메타 태그가 존재합니다.

```html
<!-- Apple Touch Icon (at least 200x200px) -->
<link rel="apple-touch-icon" href="/custom-icon.png">

<!-- To run the web application in full-screen -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- Status Bar Style (see Supported Meta Tags below for available values) -->
<!-- Has no effect unless you have the previous meta tag -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```

> * 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)
> * 📖 [Supported Meta Tags](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

* [ ] **Windows Tiles:** ![Low][low_img] Windows 타일이 존재하고 링크되어 있습니다.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

`browserconfig.xml` 파일에 필요한 최소한의 XML 마크업은 다음과 같습니다:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] 중복 콘텐츠를 피하기 위해 `rel="canonical"`을 사용하세요.

```html
<!-- Helps prevent duplicate content issues -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-read.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML 태그

* [ ] **Language attribute:** ![High][high_img] 웹사이트의 `lang` 속성이 지정되어 있고 현재 페이지의 언어와 관련이 있습니다.

```html
<html lang="en">
```

* [ ] **Direction attribute:** ![Medium][medium_img] 텍스트 방향이 HTML 태그에 지정되어 있습니다 (다른 HTML 태그에서도 사용할 수 있습니다).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] 웹사이트의 언어 태그는 현재 페이지의 언어와 관련이 있습니다.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **x-default:** ![Low][low_img] 국제 랜딩 페이지용 웹사이트 언어 태그입니다.

```html
<link rel="alternate" href="https://example.com/" hreflang="x-default" />
```

> * 📖 [x-default - Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html)


* [ ] **Conditional comments:** ![Low][low_img] IE를 위해 필요한 경우 조건부 주석이 있습니다.

> * 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] 프로젝트가 블로그이거나 기사가 있는 경우, RSS 링크가 제공되었습니다.

* [ ] **CSS Critical:** ![Medium][medium_img] CSS 크리티컬(또는 "above the fold: 아무런 행동을 하지 않은 기본 화면")은 페이지의 가시적인 부분을 렌더링하는 데 사용되는 모든 CSS를 수집합니다. 이는 기본 CSS 호출 전에 `<style></style>` 사이의 한 줄로 포함됩니다(최소화됨).

> * 🛠 [Critical by Addy Osmani on GitHub](https://github.com/addyosmani/critical) automates this.

* [ ] **CSS order:** ![High][high_img] 모든 CSS 파일은 `<head>` 안에서 어떤 JavaScript 파일보다 먼저 로드됩니다. (페이지의 맨 위에서 가끔씩 JS 파일이 비동기적으로 로드되는 경우를 제외하고)

### 소셜 메타

[메타 태그](https://metatags.io/)를 사용하여 소셜 메타 태그를 자동으로 시각화하고 생성하세요.

***Facebook OG*** 및 ***Twitter Cards***는 모든 웹사이트에 대해 강력히 권장됩니다. 그 밖의 다른 소셜 미디어 태그는 해당 소셜 유저를 대상으로 할 경우에만 고려합니다. 이를 통해 화면 표시를 보장할 수 있습니다.

* [ ] **Facebook Open Graph:** ![Low][low_img] 모든 Facebook Open Graph (OG)가 테스트되었고 누락되거나 잘못된 정보가 없습니다. 이미지는 최소한 600 x 315 픽셀이어야 하지만, 1200 x 630 픽셀을 권장합니다.

> **참고:** `og:image:width`와 `og:image:height`를 사용하면 크롤러에게 이미지의 크기를 지정하여 이미지를 비동기적으로 다운로드하고 처리하지 않고 즉시 렌더링할 수 있습니다.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<!-- Next tags are optional but recommended -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 📖 [Best Practices - Sharing](https://developers.facebook.com/docs/sharing/best-practices/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ back to top](#table-of-contents)**

---

## HTML

### 모범 사례

* [ ] **HTML5 Semantic Elements:** ![High][high_img] HTML5 의미 있는(Semantic) 요소들이 적절하게 사용됩니다 (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![High][high_img] 404 페이지와 5xx 에러 페이지가 존재합니다. 5xx 에러 페이지는 해당 CSS가 통합되어 있어야 합니다 (현재 서버에서 외부 호출 없이).

* [ ] **Noopener:** ![Medium][medium_img] 만약 `target="_blank"`로 외부 링크를 사용한다면, 링크에는 탭내빙을 방지하기 위해 `rel="noopener"` 속성이 있어야 합니다. 오래된 버전의 Firefox를 지원해야 한다면, `rel="noopener noreferrer"`를 사용합니다.

<img src="https://yozm.wishket.com/media/news/1586/image004.png" width="300" height="300"  alt="탭내빙"/>

> * 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Low][low_img] 페이지를 프로덕션으로 보내기 전에 불필요한 코드를 제거해야 합니다.

### HTML testing

* [ ] **W3C compliant:** ![High][high_img] 모든 페이지는 W3C 검증기를 사용하여 HTML 코드의 가능한 문제를 식별해야 합니다.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] HTML 코드에서 발생할 수 있는 문제를 분석하는 데 도움이 되는 도구를 사용합니다.

> * 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)

> * 🛠 [webhint](https://webhint.io/)

* [ ] **Link checker:** ![High][high_img] 페이지에 유효하지 않은 링크가 없고, 404 오류가 없습니다.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium][medium_img] 광고 차단기를 사용해도 콘텐츠를 올바르게 표시합니다. 광고 차단기를 해제하도록 사람들에게 메시지를 제공할 수 있습니다.

> * 📖 [Use AdBlocking in your Dev Environment](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)


**[⬆ back to top](#table-of-contents)**

---

## 웹폰트

> **참고:** 웹 폰트 사용으로 스타일이 적용되지 않은 텍스트의 순간적인 나타남 현상(Flash Of Unstyled Text) 또는 텍스트가 보이지 않는 순간적인 현상(Flash Of Invisible Text)이 발생할 수 있습니다. 이를 방지하기 위해 대체 폰트를 설정하거나 웹 폰트 로더를 활용하여 동작을 제어하는 것이 좋습니다.
> * 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Webfont format:** ![High][high_img] 모든 최신 브라우저에서 WOFF, WOFF2 및 TTF 형식을 지원합니다.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High][high_img] 웹폰트 크기가 모든 변형을 포함하여 2 MB를 초과하지 않습니다.

* [ ] **Webfont loader:** ![Low][low_img] 웹폰트 로더를 사용하여 로딩 동작을 제어합니다.

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ back to top](#table-of-contents)**

---

## CSS

> **참고:** 많은 프론트엔드 개발자가 따르는 [CSS 가이드라인](https://cssguidelin.es/)과 [Sass 가이드라인](https://sass-guidelin.es/)을 살펴보세요. CSS 속성에 대한 의문이 있다면 [CSS 레퍼런스](http://cssreference.io/)를 방문하세요. 일관성을 위한 간단한 [코드 가이드](http://codeguide.co/)도 있습니다.

* [ ] **Responsive Web Design:** ![High][high_img] 반응형 웹 디자인을 사용합니다.
* [ ] **CSS Print:** ![Medium][medium_img] 인쇄 스타일 시트가 각 페이지에서 제공되며 올바르게 설정되어 있습니다.
* [ ] **Preprocessors:** ![Low][low_img] CSS 전처리기를 사용합니다. (예: [Sass](http://sass-lang.com/), [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/))
* [ ] **Unique ID:** ![High][high_img] ID를 사용하는 경우, 각각 페이지의 ID가 고유합니다.
* [ ] **Reset CSS:** ![High][high_img] CSS 리셋(reset), 정규화(normalize), 또는 재부팅(reboot)이 사용되고 최신 상태입니다. *(부트스트랩이나 파운데이션 같은 CSS 프레임워크를 사용하는 경우, 정규화가 이미 포함되어 있습니다.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Low][low_img] JavaScript 파일에서 사용되는 모든 클래스(또는 id)는 **js-** 로 시작하며 CSS 파일에 스타일이 지정되지 않습니다.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **embedded or inline CSS:** ![High][high_img] `<style>` 태그에 CSS를 포함하거나 인라인 CSS를 사용하는 것을 지양합니다. 유효한 이유(예: 슬라이더의 배경 이미지, 중요한 CSS)만을 위해 사용합니다.
* [ ] **Vendor prefixes:** ![High][high_img] CSS 벤더 프리픽스를 사용하고 브라우저 지원 호환성에 따라 적절하게 생성합니다.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### 성능

* [ ] **Concatenation:** ![High][high_img] CSS 파일이 하나의 파일로 병합됩니다. (HTTP/2의 경우에는 해당하지 않음)
* [ ] **Minification:** ![High][high_img] 모든 CSS 파일이 최소화되었습니다.
* [ ] **Non-blocking:** ![Medium][medium_img] CSS 파일은 DOM이 로드되는 데 시간이 걸리지 않도록 Non-Blocking(다른 주체의 작업에 관련없이 자신의 작업을 하는 것)되어야 합니다.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

* [ ] **Unused CSS:** ![Low][low_img] 사용되지 않는 CSS를 제거합니다.

> * 🛠 [UnCSS Online](https://uncss-online.com/)
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
> * 🛠 [Chrome DevTools Coverage](https://developer.chrome.com/docs/devtools/coverage/)


### CSS 테스트

* [ ] **Stylelint:** ![High][high_img] 모든 CSS 또는 SCSS 파일에 오류가 없어야 합니다.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] 모든 페이지는 다음의 중단점에서 테스트되었습니다: 320px, 768px, 1024px (분석에 따라 더 많거나 다를 수 있음).
**Responsive Checker -**
> * 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
> * 🛠 [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
> * 🛠 [Responsive Website Design Tester](https://responsivedesignchecker.com/)
> * 🛠 [Responsinator](https://www.responsinator.com/)
> * 🛠 [XRespond](https://xrespond.com/)


* [ ] **CSS Validator:** ![Medium][medium_img] CSS가 테스트되고 관련된 오류가 수정되었습니다.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** ![High][high_img] 모든 데스크톱 브라우저(Safari, Firefox, Chrome, Internet Explorer, EDGE 등)에서 모든 페이지가 테스트되었습니다.
* [ ] **Mobile Browsers:**  ![High][high_img] 모바일 브라우저(Native browser, Chrome, Safari 등)에서 모든 페이지가 테스트되었습니다.
* [ ] **OS:**  ![High][high_img] 모든 페이지가 모든 운영 체제(Windows, Android, iOS, Mac 등)에서 테스트되었습니다.

* [ ] **Design fidelity:** ![Low][low_img] 프로젝트 및 디자인의 품질에 따라 디자인과의 일관성을 유지해야 합니다. 코드 구현과 크리에이티브를 비교하고 일관성을 보장하기 위해 몇 가지 도구를 사용할 수 있습니다.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** ![High][high_img] 모든 페이지는 LTR 및 RTL 언어에 대해 지원해야하는 경우를 위해 테스트되어야 합니다.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## 이미지

> **참고:** 이미지 최적화에 대한 이해를 위해 Addy Osmani의 무료 eBook인 **[Essential Image Optimization](https://images.guide/)** 를 확인하세요.

### 모범 사례

* [ ] **Optimization:** ![High][high_img] All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.
> * 🛠 Use [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) for image optimization in real time.
> * 🛠 Use [Kraken.io](https://kraken.io/web-interface) awesome alternative for both png and jpg optimization. Up to 1mb per files on free plan.
> * 🛠 [TinyPNG](https://tinypng.com/) optimises png, apng (animated png) and jpg images with very small loss in quality. Free and paid version available.
> * 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) jpg-like compression for transparent images using svg masking.
> * 🛠 [SVGO](https://github.com/svg/svgo) a Nodejs-based tool for optimizing SVG vector graphics files.
> * 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) a web-based GUI version of SVGO for optimising your svgs online.


* [ ] **Picture/Srcset:** ![Medium][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)

* [ ] **Retina:** ![Low][low_img] You provide layout images 2x or 3x, support retina display.
* [ ] **Sprite:** ![Medium][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![High][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image size is known (can be omitted for CSS sizing).
* [ ] **Alternative text:** ![High][high_img] All `<img>` have an alternative text which describes the image visually.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images are lazyloaded (A noscript fallback is always provided).
> * 🛠 [Native lazy loading polyfill](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ back to top](#table-of-contents)**

---

## 자바스크립트

### 모범 사례

* [ ] **JavaScript Inline:** ![High][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![High][high_img] JavaScript files are concatenated.
* [ ] **Minification:** ![High][high_img] JavaScript files are minified (you can add the `.min` suffix).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:** ![High][high_img]

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **`noscript` tag:** ![Medium][medium_img] Use `<noscript>` tag in the HTML body if a script type on the page is unsupported or if scripting is currently turned off in the browser. This will be helpful in client-side rendering heavy apps such as React.js, see [examples](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498).

```html
<noscript>
  You need to enable JavaScript to run this app.
</noscript>
```

* [ ] **Non-blocking:** ![Medium][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using `defer` attribute.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Optimized and updated JS libraries:** ![Medium][medium_img] All JavaScript libraries used in your project are necessary (prefer Vanilla Javascript for simple functionalities), updated to their latest version and don't overwhelm your JavaScript with unnecessary methods.

> * 📖 [You may not need jQuery](http://youmightnotneedjquery.com/)
> * 📖 [Vanilla JavaScript for building powerful web applications](https://plainjs.com/)

* [ ] **Modernizr:** ![Low][low_img] If you need to target some specific features you can use a custom Modernizr to add classes in your `<html>` tag.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### Scan and check your web site

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)

### 모범 사례

* [ ] **HTTPS:** ![High][high_img] HTTPS is used on every page and for all external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] The HTTP header is set to 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] You ensure that requests made to your server-side are legitimate and originate from your website / app to prevent CSRF attacks.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Your page or website is free from XSS possible issues.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

* [ ] **Content Type Options:** ![Medium][medium_img] Prevents Google Chrome and Internet Explorer from trying to mime-sniff the content-type of a response away from the one being declared by the server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO):** ![Medium][medium_img] Protects your visitors against clickjacking attacks.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

* [ ] **Content Security Policy:** ![Medium][medium_img] Defines how content is loaded on your site and from where it is permitted to be loaded. Can also be used to protect against clickjacking attacks.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
> * 📖 [CSP Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
> * 📖 [Content Security Policy Reference](https://content-security-policy.com/)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### 모범 사례

* [ ] **Goals to achieve:** ![Medium][medium_img] Your pages should reach these goals:
  * First Meaningful Paint under 1 second
  * Time To Interactive under 5 seconds for the "average" configuration (a $200 Android on a slow 3G network with 400ms RTT and 400kbps transfer speed) and under 2 seconds for repeat visits
  * Critical file size under 170Kb gzipped

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 🛠 [WebPageTest](https://www.webpagetest.org/)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

* [ ] **Minified HTML:** ![Medium][medium_img] Your HTML is minified.

* [ ] **Lazy loading:** ![Medium][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

* [ ] **Cookie size:** ![Medium][medium_img] If you are using cookies be sure each cookie doesn't exceed 4096 bytes and your domain name doesn't have more than 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** ![Medium][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your user's activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake and TLS negotiation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)
> * 🛠 [Speedrank - Improve the performance of your website](https://speedrank.app/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **참고:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 모범 사례

* [ ] **Progressive enhancement:** ![Medium][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

* [ ] **Color contrast:** ![Medium][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![High][high_img] Headings should be used properly and in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### Semantics

* [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![High][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![High][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Medium][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![High][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![Low][low_img] Google Analytics is installed and correctly configured.

> * 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
> * 🛠 [GA Checker (and others)](http://www.gachecker.com/)

* [ ] **Search Console:** ![Low][low_img] Search Console is installed and correctly configured. It is a free service offered by Google that helps you monitor, maintain, and troubleshoot your site's presence in Google Search results.

> * 🛠 [Search Console](https://search.google.com/search-console/about)

* [ ] **Headings logic:** ![Medium][medium_img] Heading text helps to understand the content in the current page.

> * 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it)

* [ ] **sitemap.xml:** ![High][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).

> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

* [ ] **robots.txt:** ![High][high_img] The robots.txt is not blocking webpages.

> * 📖 [The robots.txt file](https://varvy.com/robottxt.html)
> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 📖 [JSON-LD](https://json-ld.org/)
> * 📖 [Microdata](https://www.w3.org/TR/microdata/)
> * 🛠 Test your page with the [Rich Results Test](https://search.google.com/test/rich-results)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Hierarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)

**[⬆ back to top](#table-of-contents)**

---

## Translations

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
* 🇫🇷 French: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
* 🇷🇺 Russian: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
* 🇹🇷 Turkish: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
* 🇩🇪 German: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)
* 🇵🇱 Polish: [mbiesiad/Front-End-Checklist](https://github.com/mbiesiad/Front-End-Checklist)
* 🇮🇩 Indonesian: [nniinnoo/Front-End-Checklist](https://github.com/nniinnoo/Front-End-Checklist)

---

## Front-End Checklist Badge

If you want to show you are following the rules of the Front-End Checklist, put this badge on your README file!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](https://frontendchecklist.io) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

## Support

If you have any question or suggestion, don't hesitate to use Gitter or Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Author

**[David Dias](https://github.com/thedaviddias)**

## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](.github/CONTRIBUTING.md).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" /></a>


## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890"></a>


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist/sponsor/0/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/1/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/2/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/3/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/4/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/5/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/6/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/7/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/8/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/9/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/9/avatar.svg"></a>

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: data/images/priority/low.svg
[medium_img]: data/images/priority/medium.svg
[high_img]: data/images/priority/high.svg

