# DevDay 3D Menu: Cong Siu Bing

A 3D storefront for a street-food cart. Pick a bing from the menu and it lands on the cart's counter.

Built with **ChatGPT + CAD.show**. The cart and food are modelled from photos with Tripo in CAD.show.

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
