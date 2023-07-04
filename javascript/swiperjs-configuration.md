---
description: Cấu hình swiperJS bằng js
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
