---
sidebar_position: 3
---

# Bước đường cùng !important;

### 1. CLS

:::tip

- Kiểm tra màn hình Mobile (360) và Desktop(1350) => Set height cứng section Slider cho các màn này
- Chạy đầu file head.

```css
@media (min-width: 359px) and (max-width: 360px) {
  #home-slider { height: 100px; }
}
@media (min-width: 1349px) and (max-width: 1350px) {
  #home-slider { height: 100px; }
}
```

:::
