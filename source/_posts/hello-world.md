---
title: Hello World
---
Welcome to [Hexo-NetlifyCMS](https://hexocms.imst.xyz/)! This is your very first post. Check [Hexo](https://hexo.io/docs/) and [NetlifyCMS](https://www.netlifycms.org/docs/intro/) for more info. If you get any problems when using Hexo-NetlifyCMS, you can find the answer in [Hexo troubleshooting](https://hexo.io/docs/troubleshooting.html) , [NetlifyCMS issues](https://github.com/netlify/netlify-cms/issues) or you can ask me on [GitHub](https://github.com/DemoMacro/Hexo-NetlifyCMS/issues).

### Quick Start

Let's get started with Hexo-NetlifyCMS in three steps.

### 1.Fork [Hexo-NetlifyCMS](https://github.com/DemoMacro/Hexo-NetlifyCMS) on Github

More info: [Configuration](https://hexo.io/docs/configuration.html)

### 2.Deploy which repository you forked on Netlify

```
Build command: hexo generate
Publish directory: public
```

More info: [A Step-by-Step Guide: Hexo on Netlify](https://www.netlify.com/blog/2015/10/26/a-step-by-step-guide-hexo-on-netlify/)

### 3.Add the Netlify Identity Widget

You'll need to add this to the ```<head>``` of your CMS index page at /admin/index.html, as well as the ```<head>``` of your site's main index page.We could include the script in your site using Netlify's Script Injection feature;

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

### You are finished with Hexo-NetlifyCMS

Now you can control site content in https://yoursite.netlify.com/admin/