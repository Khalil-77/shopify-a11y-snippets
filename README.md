# Shopify A11y Snippets

Accessible Liquid snippets for Shopify Online Store 2.0 themes. Each snippet targets a common WCAG 2.2 AA failure I find when auditing Shopify stores, and can be dropped into Dawn or most third-party themes.

## Snippets

| Snippet | Fixes | WCAG |
| --- | --- | --- |
| [`skip-link.liquid`](snippets/skip-link.liquid) | No way for keyboard users to bypass the header and menu | 2.4.1 Bypass Blocks, 2.4.7 Focus Visible |
| [`a11y-price.liquid`](snippets/a11y-price.liquid) | Sale prices announced as two bare numbers, with the strikethrough meaning lost | 1.3.1 Info and Relationships |
| [`icon-button.liquid`](snippets/icon-button.liquid) | Icon-only buttons (cart, search, close) with no accessible name | 4.1.2 Name, Role, Value, 2.5.8 Target Size |

## Installation

1. In your theme code editor, create a file in `snippets/` with the same name.
2. Paste the snippet content.
3. Render it where you need it, for example:

```liquid
{% render 'skip-link', target: 'MainContent' %}
{% render 'a11y-price', product: product %}
{%- capture cart_icon -%}{% render 'icon-cart' %}{%- endcapture -%}
{% render 'icon-button', label: 'Open cart', icon: cart_icon %}
```

Each snippet has usage notes at the top of the file.

## Testing

Before shipping, test each snippet in your theme with keyboard only, NVDA + Chrome, and VoiceOver + Safari (macOS and iOS). Theme CSS can override focus styles and hidden-text utilities.

## Contributing

Issues and pull requests are welcome. If you find an accessibility bug, please include the browser, assistive technology, and steps to reproduce.

## License

MIT

---

Maintained by [Muhammad Khalil Akbar](https://github.com/Khalil-77), Web Accessibility Specialist & Shopify Developer.
