<h1 align="center">
프론트엔드 체크리스트
</h1>

---

<h4 align="center">프론트엔드 체크리스트는 웹사이트나 HTML 페이지를 프로덕션에 출시하기 전에 가져야 할 모든 요소 및 테스트 항목을 상세하게 나열한 목록입니다.</h4>

<p align="center">
    <span>다른 체크리스트:</span>
    <br>
  <a href="https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-">🎮 프론트엔드 성능 체크리스트</a> • <a href="https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist">💎 프론트엔드 디자인 체크리스트</a>
</p>

---

## 사용 방법

항목의 필요성을 기준으로 3단계로 정의했습니다:

🟢 해당 항목은 권장되지만 특정 상황에서 생략할 수 있다는 것을 나타냅니다.
🟠 해당 항목은 강력히 권장되지만 매우 특정한 경우에만 생략할 수 있습니다. 그러나 이러한 요소를 생략하면 성능이나 SEO에 부정적인 영향을 줄 수 있습니다.
🔴 해당 항목은 어떠한 경우에도 생략할 수 없음을 나타냅니다. 이러한 요소를 제거하면 페이지 기능이 동작하지 않을 수 있거나 접근성 및 SEO 문제를 야기할 수 있습니다. 이러한 요소를 테스트할 때 우선순위로 두어야 합니다.



어떤 유형의 레퍼런스인지 이해하는 데 도움이 되는 이모티콘:

* 📖: 문서 또는 기사
* 🛠: 온라인 도구 / 테스트 도구
* 📹: 미디어 또는 비디오 콘텐츠

---

## Head

> **참고:** HTML 문서의 <head>에서 찾을 수 있는 모든 것에 대한 목록을 [여기](https://github.com/joshbuchea/HEAD)에서 찾을 수 있습니다.

### 메타 태그

* [ ] **Doctype:** 🔴 Doctype은 HTML5이며 모든 HTML 페이지의 맨 위에 있습니다.

```html
<!doctype html> <!-- HTML5 -->
```

> * 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*다음 2개의 메타 태그(Charset 및 Viewport)는 head 태그 내에서 가장 먼저 와야 합니다.*

* [ ] **Charset:** 🔴 문자 인코딩(UTF-8)이 올바르게 선언되었습니다.

```html
<!-- 문서의 문자 인코딩을 설정하세요. -->
<meta charset="utf-8">
```

* [ ] **Viewport:** 🔴 뷰포트가 올바르게 선언되었습니다.

```html
<!-- 반응형 웹 디자인을 위한 뷰포트 설정 -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

* [ ] **Title:** 🔴 모든 페이지에는 타이틀이 사용됩니다 (SEO: Google은 제목에 사용된 문자의 픽셀 너비를 계산하고 472에서 482 픽셀 사이에서 자릅니다. 평균 문자 제한은 약 55자입니다).

```html
<!-- Document Title -->
<title>Page Title less than 55 characters</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)
> * 🛠 [SERP Snippet Generator](https://www.sistrix.com/serp-snippet-generator/)

* [ ] **Description:** 🔴 메타 설명이 제공되었으며, 이는 고유하며 150자를 초과하지 않습니다.

```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```

> * 📖 [Meta Description - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description)

* [ ] **Favicons:** 🟠 각 파비콘이 만들어졌으며 올바르게 표시됩니다. 만약 `favicon.ico`만 가지고 있다면, 이를 사이트의 루트에 둡니다. 보통은 아무런 마크업을 사용하지 않아도 됩니다. 그러나 아래의 예시처럼 링크를 걸어두는 것이 좋습니다. `.ico` 형식 대신 **PNG 형식이 권장됩니다**. (크기: 32x32px).

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

* [ ] **Apple Web App Meta:** 🟢 Apple 메타 태그가 존재합니다.

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

* [ ] **Canonical:** 🟠 중복 콘텐츠를 피하기 위해 `rel="canonical"`을 사용하세요.

```html
<!-- 중복 콘텐츠 문제를 방지합니다. -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-read.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)
> * 📖 [SEO 초보자를 위한 '캐노니컬 태그' 설명하기](https://yozm.wishket.com/magazine/detail/1420/)

### HTML 태그

* [ ] **Language attribute:** 🔴 웹사이트의 `lang` 속성이 지정되어 있고 현재 페이지의 언어와 관련이 있습니다.

```html
<html lang="en">
```

* [ ] **Direction attribute:** 🟠 텍스트 방향이 HTML 태그에 지정되어 있습니다 (다른 HTML 태그에서도 사용할 수 있습니다).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **CSS Critical:** 🟠 CSS 크리티컬(또는 "above the fold: 아무런 행동을 하지 않은 기본 화면")은 페이지의 가시적인 부분을 렌더링하는 데 사용되는 모든 CSS를 수집합니다. 이는 기본 CSS 호출 전에 `<style></style>` 사이의 한 줄로 포함됩니다(최소화됨).

> * 🛠 [Critical by Addy Osmani on GitHub](https://github.com/addyosmani/critical) automates this.

* [ ] **CSS order:** 🔴 모든 CSS 파일은 `<head>` 안에서 어떤 자바스크립트 파일보다 먼저 로드됩니다. (페이지의 맨 위에서 가끔씩 자바스크립트 파일이 비동기적으로 로드되는 경우를 제외하고)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## HTML

### 모범 사례

* [ ] **HTML5 Semantic Elements:** 🔴 HTML5 의미 있는(Semantic) 요소들이 적절하게 사용됩니다 (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** 🔴 404 페이지와 5xx 에러 페이지가 존재합니다. 5xx 에러 페이지는 해당 CSS가 통합되어 있어야 합니다 (현재 서버에서 외부 호출 없이).

* [ ] **Noopener:** 🟠 만약 `target="_blank"`로 외부 링크를 사용한다면, 링크에는 탭내빙을 방지하기 위해 `rel="noopener"` 속성이 있어야 합니다. 오래된 버전의 Firefox를 지원해야 한다면, `rel="noopener noreferrer"`를 사용합니다.

> * 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)
> * 📖 [하이퍼링크를 신뢰할 수 없다면? noopener, noreferrer, nofollow](https://yozm.wishket.com/magazine/detail/1586/)

* [ ] **Clean up comments:** 🟢 페이지를 프로덕션으로 보내기 전에 불필요한 코드를 제거해야 합니다.

### HTML testing

[//]: # (* [ ] **W3C compliant:** 🔴 모든 페이지는 W3C 검증기를 사용하여 HTML 코드의 가능한 문제를 식별해야 합니다.)

[//]: # ()
[//]: # (> * 🛠 [W3C validator]&#40;https://validator.w3.org/&#41;)

* [ ] **HTML Lint:** 🔴 HTML 코드에서 발생할 수 있는 문제를 분석하는 데 도움이 되는 도구를 사용합니다.

> * 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/)
> * 🛠 [webhint](https://webhint.io/)

* [ ] **Link checker:** 🔴 페이지에 유효하지 않은 링크가 없고, 404 오류가 없습니다.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** 🟠 광고 차단기를 사용해도 콘텐츠를 올바르게 표시합니다. 광고 차단기를 해제하도록 사람들에게 메시지를 제공할 수 있습니다.

> * 📖 [Use AdBlocking in your Dev Environment](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86)


**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 웹폰트

> **참고:** 웹 폰트 사용으로 스타일이 적용되지 않은 텍스트의 순간적인 나타남 현상(Flash Of Unstyled Text) 또는 텍스트가 보이지 않는 순간적인 현상(Flash Of Invisible Text)이 발생할 수 있습니다. 이를 방지하기 위해 대체 폰트를 설정하거나 웹 폰트 로더를 활용하여 동작을 제어하는 것이 좋습니다.
> * 📖 [Google Technical considerations about webfonts](https://developers.google.com/fonts/docs/technical_considerations)

* [ ] **Webfont format:** 🔴 모든 최신 브라우저에서 WOFF, WOFF2 및 TTF 형식을 지원합니다.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** 🔴 웹폰트 크기가 모든 변형을 포함하여 2 MB를 초과하지 않습니다.

* [ ] **Webfont loader:** 🟢 웹폰트 로더를 사용하여 로딩 동작을 제어합니다.

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## CSS

> **참고:** 많은 프론트엔드 개발자가 따르는 [CSS 가이드라인](https://cssguidelin.es/)과 [Sass 가이드라인](https://sass-guidelin.es/)을 살펴보세요. CSS 속성에 대한 의문이 있다면 [CSS 레퍼런스](http://cssreference.io/)를 방문하세요. 일관성을 위한 간단한 [코드 가이드](http://codeguide.co/)도 있습니다.

* [ ] **Responsive Web Design:** 🔴 반응형 웹 디자인을 사용합니다.
* [ ] **CSS Print:** 🟠 인쇄 스타일 시트가 각 페이지에서 제공되며 올바르게 설정되어 있습니다.
* [ ] **Preprocessors:** 🟢 CSS 전처리기를 사용합니다. (예: [Sass](http://sass-lang.com/), [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/))
* [ ] **Unique ID:** 🔴 ID를 사용하는 경우, 각각 페이지의 ID가 고유합니다.
* [ ] **Reset CSS:** 🔴 CSS 리셋(reset), 정규화(normalize), 또는 재부팅(reboot)이 사용되고 최신 상태입니다. *(부트스트랩이나 파운데이션 같은 CSS 프레임워크를 사용하는 경우, 정규화가 이미 포함되어 있습니다.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** 🟢 자바스크립트 파일에서 사용되는 모든 클래스(또는 id)는 **js-** 로 시작하며 CSS 파일에 스타일이 지정되지 않습니다.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **embedded or inline CSS:** 🔴 `<style>` 태그에 CSS를 포함하거나 인라인 CSS를 사용하는 것을 지양합니다. 유효한 이유(예: 슬라이더의 배경 이미지, 중요한 CSS)만을 위해 사용합니다.
* [ ] **Vendor prefixes:** 🔴 CSS 벤더 프리픽스를 사용하고 브라우저 지원 호환성에 따라 적절하게 생성합니다.

> * 📖 [CSS3 Vendor Prefix](https://poiemaweb.com/css3-vendor-prefix)
> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### 성능

* [ ] **Concatenation:** 🔴 CSS 파일이 하나의 파일로 병합됩니다. (HTTP/2의 경우에는 해당하지 않음)
* [ ] **Minification:** 🔴 모든 CSS 파일이 최소화되었습니다.
* [ ] **Non-blocking:** 🟠 CSS 파일은 DOM이 로드되는 데 시간이 걸리지 않도록 Non-Blocking(다른 주체의 작업에 관련없이 자신의 작업을 하는 것)되어야 합니다.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)
> * 📖 [Sync/Async, Blocking/Non-Blocking 무슨 차이일까?](https://velog.io/@maketheworldwise/SyncAsync-BlockingNon-Blocking-%EB%AC%B4%EC%8A%A8-%EC%B0%A8%EC%9D%B4%EC%9D%BC%EA%B9%8C)

* [ ] **Unused CSS:** 🟢 사용되지 않는 CSS를 제거합니다.

> * 🛠 [UnCSS Online](https://uncss-online.com/)
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss)
> * 🛠 [Chrome DevTools Coverage](https://developer.chrome.com/docs/devtools/coverage/)


### CSS 테스트

* [ ] **Stylelint:** 🔴 모든 CSS 또는 SCSS 파일에 오류가 없어야 합니다.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** 🔴 모든 페이지는 다음의 중단점에서 테스트되었습니다: 320px, 768px, 1024px (분석에 따라 더 많거나 다를 수 있음).
**Responsive Checker -**
> * 🛠 [Am I Responsive?](http://ami.responsivedesign.is/)
> * 🛠 [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)
> * 🛠 [Responsive Website Design Tester](https://responsivedesignchecker.com/)
> * 🛠 [Responsinator](https://www.responsinator.com/)
> * 🛠 [XRespond](https://xrespond.com/)


* [ ] **CSS Validator:** 🟠 CSS가 테스트되고 관련된 오류가 수정되었습니다.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Desktop Browsers:** 🔴 모든 데스크톱 브라우저(Safari, Firefox, Chrome, EDGE 등)에서 모든 페이지가 테스트되었습니다.
* [ ] **Mobile Browsers:**  🔴 모바일 브라우저(Native browser, Chrome, Safari 등)에서 모든 페이지가 테스트되었습니다.
* [ ] **OS:**  🔴 모든 페이지가 모든 운영 체제(Windows, Android, iOS, Mac 등)에서 테스트되었습니다.

* [ ] **Design fidelity:** 🟢 프로젝트 및 디자인의 품질에 따라 디자인과의 일관성을 유지해야 합니다. 코드 구현과 크리에이티브를 비교하고 일관성을 보장하기 위해 몇 가지 도구를 사용할 수 있습니다.

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

* [ ] **Reading direction:** 🔴 모든 페이지는 LTR 및 RTL 언어에 대해 지원해야하는 경우를 위해 테스트되어야 합니다.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 이미지

> **참고:** 이미지 최적화에 대한 이해를 위해 Addy Osmani의 무료 eBook인 **[Essential Image Optimization](https://images.guide/)** 를 확인하세요.

### 모범 사례

* [ ] **Optimization:** 🔴 모든 이미지가 브라우저에서 렌더링될 수 있도록 최적화되었습니다. 홈페이지와 같은 중요한 페이지에는 WebP 형식을 사용할 수 있습니다.

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.
> * 🛠 Use [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) for image optimization in real time.
> * 🛠 Use [Kraken.io](https://kraken.io/web-interface) awesome alternative for both png and jpg optimization. Up to 1mb per files on free plan.
> * 🛠 [TinyPNG](https://tinypng.com/) optimises png, apng (animated png) and jpg images with very small loss in quality. Free and paid version available.
> * 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) jpg-like compression for transparent images using svg masking.
> * 🛠 [SVGO](https://github.com/svg/svgo) a Nodejs-based tool for optimizing SVG vector graphics files.
> * 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) a web-based GUI version of SVGO for optimising your svgs online.


* [ ] **Picture/Srcset:** 🟠 사용자의 현재 뷰포트에 가장 적합한 이미지를 제공하기 위해 picture/srcset을 사용합니다.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)
> * 📖 [picture elements 사용하기](https://wit.nts-corp.com/2021/02/04/6293)
> * 📖 [HTML IMG의 srcset과 sizes 속성](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)

* [ ] **Retina:** 🟢 레티나 디스플레이를 지원하기 위해 레이아웃 이미지를 2배 또는 3배로 제공합니다.

> * 📖 [레티나 디스플레이 대응하기](https://doridori-samsam.tistory.com/28)

* [ ] **Sprite:** 🟠 작은 이미지는 스프라이트 파일에 있습니다. (아이콘의 경우 SVG 스프라이트 이미지에 있을 수 있습니다.)
* [ ] **Width and Height:** 🔴 이미지의 최종 렌더링 크기를 알고 있다면 `<img>`에 `width`와 `height` 속성을 설정하세요. (CSS 크기 지정에 대해서는 생략할 수 있습니다.)
* [ ] **Alternative text:** 🔴 모든 `<img>`에는 이미지를 시각적으로 설명하는 대체 텍스트가 있어야 합니다.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** 🟠 이미지는 레이지 로딩되어 있습니다 (noscript 대체가 항상 제공됩니다).
> * 🛠 [Native lazy loading polyfill](https://github.com/mfranzke/loading-attribute-polyfill/)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 자바스크립트

### 모범 사례

* [ ] **JavaScript Inline:** 🔴 HTML 코드와 혼합된 인라인 자바스크립트 코드가 없습니다.
* [ ] **Concatenation:** 🔴 자바스크립트 파일이 연결되어 있습니다.
* [ ] **Minification:** 🔴 자바스크립트 파일이 최소화되었습니다 (.min 접미사를 추가할 수 있습니다).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:** 🔴

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **`noscript` tag:** 🟠 브라우저에서 스크립팅이 지원되지 않거나 현재 스크립팅이 꺼져 있는 경우 HTML 본문에 `<noscript>` 태그를 사용하세요. 이는 React.js와 같은 클라이언트 측 렌더링이 많이 필요한 애플리케이션에 유용할 것입니다. [예시](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498)를 참조하세요.

```html
<noscript>
  이 앱을 실행하려면 자바스크립트를 활성화해야 합니다.
</noscript>
```

* [ ] **Non-blocking:** 🟠 자바스크립트 파일은 `async` 속성을 사용하여 비동기적으로 로드되거나 `defer` 속성을 사용하여 지연되어 로드됩니다.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Optimized and updated JS libraries:** 🟠 프로젝트에서 사용되는 모든 자바스크립트 라이브러리가 필요하며(간단한 기능에는 Vanilla 자바스크립트를 사용하는 것이 좋습니다), 최신 버전으로 업데이트되어 있으며 불필요한 메서드로 자바스크립트가 과도하게 무거워지지 않도록 주의해야 합니다.

> * 📖 [You may not need jQuery](http://youmightnotneedjquery.com/)
> * 📖 [Vanilla JavaScript for building powerful web applications](https://plainjs.com/)

[//]: # (* [ ] **Modernizr:** 🟢 특정 기능을 대상으로 해야 할 경우 사용자 지정 Modernizr을 사용하여 `<html>` 태그에 클래스를 추가할 수 있습니다.)

[//]: # ()
[//]: # (> * 🛠 [Customize your Modernizr]&#40;https://modernizr.com/download?setclasses&#41;)

### 자바스크립트 테스트

* [ ] **ESLint:** 🔴 ESLint에 의해 오류가 플래그되지 않습니다 (구성 또는 표준 규칙에 따라).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 보안

### 웹 사이트 스캔 및 체크

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)

### 모범 사례

* [ ] **HTTPS:** 🔴 모든 페이지와 외부 콘텐츠(플러그인, 이미지 등)에 HTTPS가 사용됩니다.

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** 🟠 HTTP 헤더가 'Strict-Transport-Security'로 설정되어 있습니다.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html)

* [ ] **Cross Site Request Forgery (CSRF):** 🔴 서버 측으로의 요청이 정당하며 우리 웹사이트/앱에서 시작되었음을 확인하여 CSRF 공격을 방지합니다.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)

* [ ] **Cross Site Scripting (XSS):** 🔴 페이지나 웹사이트에 XSS 가능한 문제가 없습니다.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)

* [ ] **Content Type Options:** 🟠 Google Chrome이 서버에서 선언된 content-type과 다른 것을 시도하는 것을 방지합니다.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO):** 🟠 방문자를 클릭잭킹 공격으로부터 보호합니다.

> * 📖 [클릭재킹이란 무엇이며 어떻게 방지합니까?](https://ko.itpedia.nl/2022/10/02/wat-is-clickjacking-en-hoe-voorkomen-we-het/#google_vignette)
> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

* [ ] **Content Security Policy:** 🟠 웹사이트에서 콘텐츠가 어떻게 로드되는지 및 어디에서 로드되어 허용되는지를 정의합니다. 또한 클릭잭킹 공격에 대비하여 사용할 수 있습니다.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/)
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/)
> * 📖 [CSP Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
> * 📖 [Content Security Policy Reference](https://content-security-policy.com/)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 성능

### 모범 사례

* [ ] **Goals to achieve:** 🟠 페이지는 다음 목표를 달성해야 합니다:
  * 첫 번째 의미 있는 페인트는 1초 이내에 완료되어야 합니다.
  * "평균" 구성(느린 3G 네트워크에서 400ms RTT 및 400kbps 전송 속도를 갖는 $200 Android 장치)의 Time To Interactive는 5초 이내이어야 하며, 반복 방문에서는 2초 이내여야 합니다.
  * 크리티컬 파일 크기는 압축 후 170KB 이내여야 합니다.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 🛠 [WebPageTest](https://www.webpagetest.org/)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

* [ ] **Minified HTML:** 🟠 HTML은 압축되어 있습니다.

* [ ] **Lazy loading:** 🟠 이미지, 스크립트 및 CSS는 현재 페이지의 응답 시간을 개선하기 위해 레이지 로딩되어야 합니다. (해당 섹션에서 자세한 내용 참조)

* [ ] **Cookie size:** 🟠 쿠키를 사용하는 경우 각 쿠키가 4096바이트를 초과하지 않도록하고 도메인 이름에 20개 이상의 쿠키가 없도록합니다.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

* [ ] **Third party components:** 🟠 가능한 경우, 외부 자바스크립트에 의존하는 써드파티 iframe이나 구성 요소(공유 버튼과 같은)는 정적 구성 요소로 대체하여 외부 API 호출을 제한하고 사용자의 활동을 보호합니다.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/)

### 다가오는 요청 준비하기

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** 🟢 제공될 수 있는 필요한 제3자 서비스의 DNS는 `dns-prefetch`를 사용하여 유휴 시간 동안 미리 해결됩니다.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** 🟢 빠른 접속을 위해 필요한 서비스와의 DNS 조회, TCP 핸드셰이크 및 TLS 협상은 유휴 시간 동안 `preconnect`를 사용하여 미리 처리됩니다.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** 🟢 빠른 접속을 위해 필요한 리소스(예: 지연로드된 이미지)는 유휴 시간 동안 `prefetch`를 사용하여 미리 요청됩니다.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** 🟢 현재 페이지에서 필요한 리소스(예: `<body>` 끝에 배치된 스크립트)는 `preload`를 사용하여 미리 로드됩니다.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### 성능 테스트

* [ ] **Google PageSpeed:** 🔴 모든 페이지(홈페이지뿐만 아니라)가 테스트되었으며 적어도 90/100의 점수를 받았습니다.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/)
> * 🛠 [Speedrank - Improve the performance of your website](https://speedrank.app/)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 접근성

> **참고:** [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 재생 목록을 시청할 수 있습니다. 📹

### 모범 사례

* [ ] **Progressive enhancement:** 🟠 주요 기능인 주 메뉴 및 검색은 자바스크립트를 사용하지 않고도 작동해야 합니다.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

* [ ] **Color contrast:** 🟠 색 대비는 적어도 WCAG AA를 통과해야 합니다 (모바일의 경우 AAA).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** 🔴 모든 페이지에는 웹 사이트 제목이 아닌 H1이 있습니다.
* [ ] **Headings:** 🔴 Headings은 적절하게 사용되고 올바른 순서로 (H1에서 H6까지) 사용되어야 합니다.

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

### 시맨틱스

* [ ] **Specific HTML5 input types are used:** 🟠 모바일 기기에서 각 요소의 유형에 따라 사용자 지정된 키패드와 위젯이 표시됩니다.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### 폼

* [ ] **Label:** 🔴 각 입력 폼 요소에는 레이블이 연결되어 있습니다. 레이블을 표시할 수 없는 경우에는 대신 `aria-label`을 사용하세요.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label)

### 접근성 테스트

* [ ] **Accessibility standards testing:** 🔴 페이지가 접근성 표준을 준수하는지 테스트하기 위해 WAVE 도구를 사용하세요.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** 🔴 사용자가 키보드만 사용하여 웹사이트의 모든 상호 작용 가능한 요소가 예측 가능한 순서로 접근 가능하고 사용 가능한지 확인하세요.
* [ ] **Screen-reader:** 🟠 모든 페이지가 스크린 리더(보이스오버, ChromeVox, NVDA 또는 Lynx)에서 테스트되었습니다.
* [ ] **Focus style:** 🔴 포커스가 비활성화된 경우, CSS에서 visible 상태로 대체됩니다.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** 🟢 구글 애널리틱스가 설치되어 있고 올바르게 구성되었습니다.

> * 🛠 [Google Analytics](https://analytics.google.com/analytics/web/)
> * 🛠 [GA Checker (and others)](http://www.gachecker.com/)

* [ ] **Search Console:** 🟢 서치 콘솔이 설치되어 있고 올바르게 구성되었습니다. 이것은 Google에서 제공하는 무료 서비스로, Google 검색 결과에서 사이트의 존재를 모니터링, 유지 및 문제 해결하는 데 도움을 줍니다.

> * 🛠 [Search Console](https://search.google.com/search-console/about)

* [ ] **Headings logic:** 🟠 Heading 텍스트가 현재 페이지의 내용을 이해하는 데 도움이 됩니다.

> * 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it)

* [ ] **sitemap.xml:** 🔴 sitemap.xml이 있으며 구글 검색 콘솔(이전에는 구글 웹마스터 도구)에 제출되었습니다.

> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)

* [ ] **robots.txt:** 🔴 robots.txt가 웹페이지를 차단하지 않습니다.

> * 📖 [The robots.txt file](https://varvy.com/robottxt.html)
> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** 🔴 구조화된 데이터를 사용하는 페이지는 테스트되었고 오류가 없습니다. 구조화된 데이터는 크롤러가 현재 페이지의 콘텐츠를 이해하는 데 도움이 됩니다.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 📖 [JSON-LD](https://json-ld.org/)
> * 📖 [Microdata](https://www.w3.org/TR/microdata/)
> * 🛠 Test your page with the [Rich Results Test](https://search.google.com/test/rich-results)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Hierarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** 🟠 HTML 사이트맵이 제공되며 웹사이트의 푸터에 있는 링크를 통해 접근할 수 있습니다.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

---

## 참고

- [thedaviddias/Front-End-Checklist](https://github.com/thedaviddias/Front-End-Checklist)

**[⬆ 페이지 상단으로 이동](#table-of-contents)**

[low_img]: data/images/priority/low.svg
[medium_img]: data/images/priority/medium.svg
[high_img]: data/images/priority/high.svg

