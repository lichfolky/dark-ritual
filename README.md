# My Dark Ritual

Basic static webpage template with my favorite tools, an initial css setup and an html boilerplate.

My goal is to use this repo to store best practices and my favorite configurations, so it might look like an overly engineered page, but it's actually a repository of what I like to have available when I create new simple web page.

**TODO:**

- Google and facebook SEO metatags
- A dark ritual template should have dark mode support

**FIXME:**

- Nesting linting error

---

## **TOOLS**

### Vite

This template uses [vite](https://vitejs.dev/)!

```
npm create vite@latest
```

### PostCSS

[Postcss](https://github.com/postcss/postcss) it's my favorite css processor

- [Autoprefixer](https://github.com/postcss/autoprefixer)
- [Postcss-nesting](https://github.com/csstools/postcss-nesting)
- [Postcss-import](https://github.com/postcss/postcss-import)

```
npm i --save-dev postcss autoprefixer postcss-nested postcss-import
```

---

## **CSS Stuff**

### Css Reset

I used [The New CSS Reset](https://github.com/elad2412/the-new-css-reset) to remove browser default styles.

### Breakpoints and media queries

I prefer to set queries based on the size of the content, but using this structure encourages a mobile first approach which I have found to be my way to go in order not to neglect the mobile experience.

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

### Typography

**Type scales for font sizes**

I like to use type scales for my font selection.

**I always forget to begin with the most important font style: the body text**

Find the perfect font-size, line-height and letter-spacing for base text.

Choose one ratio (or multiple for different screens):

- minorSecond: 1.067
- majorSecond: 1.125
- minorThird: 1.2
- majorThird: 1.25
- perfectFourth: 1.333
- augmentedFourth: 1.414
- perfectFifth: 1.5
- goldenRatio: 1.618

(Ratios from [type-scale](https://type-scale.com/))

```
Es: majorThird ratio: 1.25, body fontsize: 18px
:root{ fontsize:18px;} => 1rem=18px

Multiply ratio for rem for each of the text size

body 1rem
h4 1rem * 1.25 = 1.25rem
h3 1.25rem * 1.25 = 1.5625rem
h2 1.953125rem
h1 2.44140625rem
small 0.8rem

Now you should round them.
```

In alternative you can use fluid type

```
/* font-size: clamp(min, ideal, max); */
font-size: clamp(1rem, 10vw, 2rem);
```

**line height**

I like to use kitty giraudel [magic line height formula](https://kittygiraudel.com/2020/05/18/using-calc-to-figure-out-optimal-line-height/) to have an initial guess.

> Since every typeface has its own ex value, we still need to fine-tune our px & ex values. Anyway, consider this a good starting point.

**Text blocks block-margin**
also the `margin-bottom: 0.65em;` should be considered only a initial guess

### User preferences media queries

`prefers-reduced-motion: reduce`

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
