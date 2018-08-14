# HexoCMS

HexoCMS is a static site cms for hexo and could deploy and control content on Netlify.com. You can visit the official HexoCMS site in [https://hexocms.imst.xyz/](https://hexocms.imst.xyz/)

### Quick Start

Let's get started with HexoCMS in three steps.

### 1.Fork [HexoCMS](https://github.com/DemoMacro/HexoCMS) on Github

More info: [Configuration](https://hexo.io/docs/configuration.html)

### 2.Deploy which repository you forked on Netlify

More info: [A Step-by-Step Guide: Hexo on Netlify](https://www.netlify.com/blog/2015/10/26/a-step-by-step-guide-hexo-on-netlify/)

### 3.Add the Netlify Identity Widget

You'll need to add this to the <head> of your CMS index page at /admin/index.html, as well as the <head> of your site's main index page.We could include the script in your site using Netlify's Script Injection feature;

```html
<script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
```
 Add the following script before the closing body tag of your site's main index page using Netlify's Script Injection feature.

```html
<script>
  if (window.netlifyIdentity) {
    window.netlifyIdentity.on("init", user => {
      if (!user) {
        window.netlifyIdentity.on("login", () => {
          document.location.href = "/admin/";
        });
      }
    });
  }
</script>
```

### You are finished with HexoCMS

Now you can control site content in https://yoursite.netlify.com/admin/