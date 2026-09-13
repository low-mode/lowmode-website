# LOWMODE Emblem Replacement Standard

## 1. Replacement rule

Use `/assets/lowmode-eagle-lm-emblem.webp` as the single approved LOWMODE emblem.

Replace any small standalone LOWMODE brand mark that is an old `M`, old `LM`, old bird/eagle, crest, or similar chest/hat/polo emblem with the eagle gripping the `LM` emblem.

Do **not** replace full artwork, slogans, large back graphics, illustrations, or campaign art unless the old emblem is a separate standalone brand mark inside that artwork.

Preferred placement:
- tees / polos / jackets / hoodies: small left-chest mark unless the design already has a dedicated emblem position
- hats: centered front mark
- site header/footer: use the same eagle-LM asset
- product cards: use the same asset only where the garment is intended to carry a LOWMODE emblem

## 2. Site code standard

### Canonical asset
```html
<img class="brand-emblem" src="/assets/lowmode-eagle-lm-emblem.webp" alt="LOWMODE eagle LM emblem">
```

### CSS for generated/site emblems
```css
.brand-emblem,
.lowmode-emblem {
  display: block;
  width: 52px;
  height: 40px;
  object-fit: contain;
}

.product-media[data-lowmode-emblem="true"],
.women-card .media[data-lowmode-emblem="true"] {
  position: relative;
}

.product-media[data-lowmode-emblem="true"]::after,
.women-card .media[data-lowmode-emblem="true"]::after {
  content: "";
  position: absolute;
  left: 50%;
  top: 34%;
  width: 72px;
  height: 56px;
  transform: translate(-50%, -50%);
  background: url('/assets/lowmode-eagle-lm-emblem.webp') center / contain no-repeat;
  pointer-events: none;
  z-index: 20;
}
```

### Product-card markup
```html
<div class="product-media" data-lowmode-emblem="true">
  <img src="/assets/product.webp" alt="LOWMODE product">
</div>
```

### Important limitation
If an old emblem is baked into a JPG/PNG/WebP product photograph, CSS or HTML cannot truly remove it. That source product image must be edited and re-exported with the eagle-LM emblem replacing the old mark. The site should then point to the edited image asset. This is required for a real visual replacement rather than a badge layered over the old emblem.
