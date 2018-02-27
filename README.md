# DEPRECATED AS OF 02/27/2018
# Starter-Kit

**What's included:**

1. [Bootstrap](http://getbootstrap.com/) **v3.3.7**
2. [jQuery](https://jquery.com/download/) **v1.12.4**
3. [FontAwesome](https://fortawesome.github.io/Font-Awesome/icons/) **v4.7.0**
4. [Animate.css](https://github.com/daneden/animate.css/blob/master/animate.min.css) **v3.5.1**
5. [WOW.js](https://github.com/matthieua/WOW/blob/master/dist/wow.min.js) **v1.1.3**
6. Flickity [CSS](https://github.com/metafizzy/flickity/blob/master/dist/flickity.min.css) and [JS](https://github.com/metafizzy/flickity/blob/master/dist/flickity.pkgd.min.js) **v2.0.5**

### **Guidelines - Setup:**

Make sure that `SASS` is configured properly. Standard configuration includes setting the output for `main.sass` to **/css/_site-styles.css_**. It is recommended that you rename the output CSS similar to the project name.

Install **Bourbon** in _0-libraries/_.

For Animations, add the following line under **PLUGINS CSS**:

```html
  <!-- PLUGINS CSS -->
  <link rel="stylesheet" href="/plugins/animate.min.css">
```

and the following line under **PLUGINS JS** if you need to utilize on-scroll Animations:

```html
  <!-- PLUGIN JS -->
  <script type="text/javascript" src="/plugins/wow.min.js"></script>
  <script type="text-javascript">
    new WOW().init();
  </script>
```

For touch, responsive Flickable Carousels, add the following lines under **PLUGINS CSS** and **PLUGINS JS**:

```html
  <!-- PLUGIN CSS -->
  <link rel="stylesheet" href="/plugins/flickity/flickity.min.css">
```

```html
  <!-- PLUGIN JS -->
  <script type="text/javascript" src="/plugins/flickity/flickity.min.js"></script>
```

### **Guidelines - Coding Standards:**

Take advantage of `SASS` to keep everything modular and neat. It is important to understand the `SASS` folder structure included in this Starter Kit.

Make sure to utilize Bourbon's preset `Mixins`. Refer to [Bourbon's Documentation](http://bourbon.io/docs/).

Animation is easily implemented thanks to **Animate.css** and **WOW.js**. Refer to [Animate.css' Documentation](https://github.com/daneden/animate.css#usage) & [WOW.js' Documentation](http://mynameismatthieu.com/WOW/docs.html).

To use **Flickity**, refer to [Flickity's Website](http://flickity.metafizzy.co/).

**Libraries**

- _0-libraries/bourbon/_ : this is where bourbon is usually installed.
- _0-libraries/_mixins.sass_ : for `Mixins`, add it here. There is a predefined `Breakpoint Mixin`.
- _0-libraries/_vars.sass_ : to avoid inconsistencies with colors, fonts, etc., declare **Sitewide** specs here.

```sass
  $white: rgb(255,255,255)
  $black: rgb(0,0,0)

  // ##########################
  // SITEWIDE FONTS
  // ##########################
  $sample-font: sans-serif

  // ##########################
  // SITEWIDE COLORS
  // ##########################
  $sample-color: #849302
```

**Base**

- _1-base/base.sass_ : add **Sitewide** styling here.

```sass
  base
    font-family: $sample-font
```

**Template Styling**

- _2-templates/_ : the importance why the `SASS` folder is structured this way is to keep everything modular. To utilize templates, add a `SASS` file with a filename matching the template, example:

```
  index.sass -- styles for the homepage
  about-us.sass -- styles for the about-us page
  contact.sass -- styles for the contact page

  sidebar-left.sass - template styling with left sidebar
```

- _2-templates/_templates-index.sass_ : if there are no templates used, leave this blank. Otherwise, import the `SASS` files here.

```sass
  @import "index"
  @import "about-us"
  @import "contact"

  @import "sidebar-left"
```

### **Compiling Everything**

If done correctly, `main.sass` will compile everything to **css/_site-styles_.css**. Make sure to take advantage of the `@extend` feature of `SASS`. For more info, checkout [SASS' Documentation](http://sass-lang.com/guide).

**IMPORTANT!** Exclude the `_sass` folder whenever the project is uploaded onto a live server.
