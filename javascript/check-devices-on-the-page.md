---
description: Code kiểm tra thiết bị đang truy cập trang web
cover: >-
  https://images.unsplash.com/photo-1498050108023-c5249f4df085?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxqYXZhfGVufDB8fHx8MTY4ODQ0NTg0OHww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# ➕ Check devices on the page

```javascript
            const getDeviceInfo = () => {
                const userAgent = navigator.userAgent.toLowerCase()
                let isPc = Boolean(userAgent.match(/mobile|android|iphone/i)) === false
                let isMobile = Boolean(userAgent.match(/mobile|android|iphone/i))
                let isIos = Boolean(userAgent.match(/iphone|ipad/i))
                let isAndroid = Boolean(userAgent.match(/android|mobile|pad/i) && Boolean(userAgent.match(/ipad/i)) === false && Boolean(userAgent.match(/mac/i)) === false)

                if (screen.availWidth >= 1024 && isAndroid) {
                    //安卓平板 视为pc端
                    isPc = true
                    isMobile = false
                    isAndroid = false
                }

                return { isPc, isMobile, isIos, isAndroid }
            }
            const { isPc, isMobile, isIos, isAndroid } = getDeviceInfo()
```

Function check userAgent từ navigator chuyển về kiểu chữ thông thường . gán 4 biến check theo điều kiện PC, Mobile, Ios và Android tùy theo thiết bị được truy cập
