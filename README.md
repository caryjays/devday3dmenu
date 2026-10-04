# DevDay 3D Menu: 小巷食堂 Xiaoxiang Shitang

A 3D storefront for a Taipei fried-snack cart. Pick a snack and it appears beside the cart.

Built with **ChatGPT + [CAD.show](https://cad.show/?utm_source=devday3dmenu-github&utm_medium=referral&utm_campaign=devday-2026)**. The cart and food are modelled with Tripo in CAD.show.

## Run it

It's a single static page, so any web server works:

```sh
npx serve .
```

Opening `index.html` straight from disk won't load the `.glb` files. Use a server, or the GitHub Pages URL.

## Swap in a 3D model

1. Put the textured `.glb` in `models/`. Files must be under 100 MB and must not be Draco-compressed.
2. In `index.html`, edit the `CONFIG` block at the top of the script:
   - cart: `cart.model = 'models/cart.glb'`
   - a menu item: set `model: 'models/egg.glb'` on that item
3. To fix placement, open the page with `#tune` on the end of the URL. Adjust the sliders and copy the printed JSON into `CONFIG.cart`.

You can also drag a `.glb` onto the 3D view to preview it without editing anything. A filename containing `cart` replaces the cart; any other file replaces the selected menu item.

## Menu, prices, links

The menu, prices and links all live in the same `CONFIG` block (`shop`, `items`, `addons`). Set `sampleMenu: false` once the real menu is in.

## Team

- Cary Jay Forest: 3D storefront, Tripo models
- Zhu Lin: merchant view and order queue, pay options
- Ethan Chuang ([@e40125](https://github.com/e40125)): contributor
