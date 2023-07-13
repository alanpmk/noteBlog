---
description: Cấu hình swiperJS bằng js
cover: >-
  https://images.unsplash.com/photo-1522252234503-e356532cafd5?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw3fHxjb2RlfGVufDB8fHx8MTY4OTIyNTEyM3ww&ixlib=rb-4.0.3&q=85
coverY: 0
layout:
  cover:
    visible: true
    size: hero
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ➕ SwiperJS configuration

<pre class="language-javascript" data-overflow="wrap" data-line-numbers data-full-width="false"><code class="lang-javascript"><strong>let swiper = new Swiper(".mySwiper1", {
</strong>                mousewheel: true,
                spaceBetween: 50,
                direction: "vertical",
                loop: true,
                paginationClickable: true,
                disableOnInteraction: false,
                autoplayDisableOnInteraction: false,
                autoplay: {
                    disableOnInteraction: false,
                    delay: 3000,
                },
                pagination: {
                    el: ".swiper-pagination",
                    clickable: true,
                },
            });
</code></pre>

SwiperJS version 8.4.7 [https://swiperjs.com/swiper-api#modules](https://swiperjs.com/swiper-api#modules)

CDN Link : [https://cdn.jsdelivr.net/npm/swiper/](https://cdn.jsdelivr.net/npm/swiper/)

```html
<script src="https://cdn.jsdelivr.net/npm/swiper@8.4.7/swiper-bundle.min.js"></script>
<link href="https://cdn.jsdelivr.net/npm/swiper@8.4.7/swiper-bundle.min.css" rel="stylesheet">
```
