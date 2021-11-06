---
title: README
---

# Hexo-NetlifyCMS

![GitHub](https://img.shields.io/github/license/DemoMacro/Hexo-NetlifyCMS)

> This is a hexo site hosted with Netlify.

<!-- Markdown snippet -->

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/DemoMacro/Hexo-NetlifyCMS/)

## Quick Start

Let's get started with Hexo-NetlifyCMS step by step.

### Fork [Hexo-NetlifyCMS](https://github.com/DemoMacro/Hexo-NetlifyCMS) on Github

More info: [Configuration](https://hexo.io/docs/configuration.html)

### Deploy which repository you forked on Netlify

```
Build command: hexo generate
Publish directory: public
```

More info: [A Step-by-Step Guide: Hexo on Netlify](https://www.netlify.com/blog/2015/10/26/a-step-by-step-guide-hexo-on-netlify/)

### Enable Identity and Git Gateway

Netlify's Identity and Git Gateway services allow you to manage CMS admin users for your site without requiring them to have an account with your Git host or commit access on your repo. From your site dashboard on Netlify:

1. Go to **Settings > Identity**, and select **Enable Identity service**.
2. Under **Registration preferences**, select **Open** or **Invite only**. In most cases, you want only invited users to access your CMS, but if you're just experimenting, you can leave it open for convenience.
3. If you'd like to allow one-click login with services like Google and GitHub, check the boxes next to the services you'd like to use, under **External providers**.
4. Scroll down to **Services > Git Gateway**, and click **Enable Git Gateway**. This authenticates with your Git host and generates an API access token. In this case, we're leaving the **Roles** field blank, which means any logged in user may access the CMS. For information on changing this, check the [Netlify Identity documentation](https://www.netlify.com/docs/identity/).

### Add the Netlify Identity Widget

You'll need to add this to the `<head>` of your CMS index page at /admin/index.html, as well as the `<head>` of your site's main index page.We could include the script in your site using Netlify's Script Injection feature;

```html
<!-- Include the script that enables Netlify Identity on this page. -->
<script
  src="https://cdn.jsdelivr.net/npm/netlify-identity-widget@1/build/netlify-identity-widget.min.js"
  async
  defer
></script>
```

Add the following script before the closing body tag of your site's main index page using Netlify's Script Injection feature.

```html
<script>
  if (window.netlifyIdentity) {
    window.netlifyIdentity.on('init', (user) => {
      if (!user) {
        window.netlifyIdentity.on('login', () => {
          document.location.href = '/admin/';
        });
      }
    });
  }
</script>
```

### You are finished with Hexo-NetlifyCMS

Now you can control site content in https://yoursite.netlify.com/admin/

## License

This Project is under the [MIT License](LICENSE).
