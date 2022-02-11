# My Dark Ritual

Basic static webpage template with my favorite tools, my initial css setup and html boilerplate template.

My goal it's to use this repo to store initial best practices and favorite setup.

**TODO:**

- Google and facebook SEO metatags

---

## **TOOLS**

### Vite

This template uses [vite](https://vitejs.dev/)!

`npm create vite@latest`

### PostCSS

[Postcss](https://github.com/postcss/postcss)
it's my favorite css processor, I added my favorite plugins

- [Autoprefixer](https://github.com/postcss/autoprefixer)
- [Postcss-nesting](https://github.com/csstools/postcss-nesting)
- [Postcss-import](https://github.com/postcss/postcss-import)

`npm i --save-dev postcss autoprefixer postcss-nested postcss-import`

---

## **CSS Stuff**

### Css Reset

I used this to remove browser default styles:  
[The New CSS Reset](https://github.com/elad2412/the-new-css-reset)

### Useful common breakpoints

```
/* Extra Small (xs) */
/* < 600px */

/* Small (sm) */
@media (min-width: 600px) {
}

/* Medium (md) */
@media (min-width: 960px) {
}

/* Large (lg) */
@media (min-width: 1280px) {
}


/* Extra Large (xl) */
@media (min-width: 1920px) {
}

```

---

## **HTML Stuff**

### Favicons

Favicon structure is following the article:  
[How to Favicon in 2022](https://evilmartians.com/chronicles/how-to-favicon-in-2021-six-files-that-fit-most-needs)

- `.ico`
  > I recommend sticking to a single 32×32 image, unless the one you have doesn’t downscale well to 16×16 (if it becomes blurry, for instance). In that case, you can ask your designer to come up with a special version of the logo that’s tailored to fit small pixel grids.
- `.svg`
  > SVG is an XML format and can contain a `<style>` tag to describes CSS. As with any CSS, it can contain media queries like `@media (prefers-color-scheme: dark)`
- `apple-touch-icon.png`

  > 180×180 PNG image for Apple devices Apple touch icon will look better if you place 20px padding around the icon and add some background color.

- `icon-192.png` + `/icon-512.png` + `manifest.webmanifest`
  > Web app manifest with 192×192 and 512×512 PNG icons for Android devices two icons: 192×192, for display on the home screen, and 512×512 which will be used as a splash screen as PWA is loading.
