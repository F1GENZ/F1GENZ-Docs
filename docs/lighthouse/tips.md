---
sidebar_position: 3
---

# Bước đường cùng !important;

### 0. Disabled Lazy
``` js
<script>var _0x7a7f=["\x6E\x6F\x50\x53","\x6C\x61\x7A\x79\x53\x69\x7A\x65\x73\x43\x6F\x6E\x66\x69\x67","\x69\x6E\x69\x74"];var _0x1529=[_0x7a7f[0],_0x7a7f[1],_0x7a7f[2]];var _0x7197=[_0x1529[0],_0x1529[1],_0x1529[2]];var _0x2356=[_0x7197[0],_0x7197[1],_0x7197[2]];if(!window[_0x2356[0]]){window[_0x2356[1]]= window[_0x2356[1]]|| {};window[_0x2356[1]][_0x2356[2]]= false}</script>
```

### 1. CLS

:::tip

- Kiểm tra màn hình Mobile (360) và Desktop(1350) => Set height cứng section Slider cho các màn này
- Chạy đầu file head.

```css
@media (min-width: 359px) and (max-width: 360px) {
  #home-slider {
    height: 100px;
  }
}
@media (min-width: 1349px) and (max-width: 1350px) {
  #home-slider {
    height: 100px;
  }
}
```

:::

### 2. Slider

:::tip

- Nếu bắt buộc phải chạy Slider đầu tiên thì tắt Autoplay và loop

```js
if(window.noPS){
  $('#index_slider').slick('slickSetOption', 'infinite', true, true);
  $('#index_slider').slick('slickSetOption', 'autoplay', true, true);
}
```

:::

### 3. Content Product/Article
```liquid title="Replace liquid"
{{ article.content | replace: 'src', 'width="1" height="1" alt="" nosrc' }}
```
```css title="CSS đầu trang"
  #articleBody img{ width: auto; }
  #articleBody img:not([src]){ display: none }; 
```
```js title="Javascript dưới cùng"
<script>
	if(window.noPS){
		var dom = document.getElementById("articleBody");
		var images = dom.getElementsByTagName('img'); 
		for(var i = 0; i < images.length; i++) {
			images[i].setAttribute('src', images[i].getAttribute("nosrc"));
		}

		var iframes = dom.getElementsByTagName('iframe'); 
		for(var i = 0; i < iframes.length; i++) {
			iframes[i].setAttribute('src', iframes[i].getAttribute("nosrc"));
		}
	}
</script>
```
