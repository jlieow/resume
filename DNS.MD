Archived from https://gist.github.com/cvan/8630f847f579f90e0c014dc5199c337b

# Instructions

CloudFlare is an awesome reverse cache proxy and CDN that provides DNS, free HTTPS (TLS) support, best-in-class performance settings (gzip, SDCH, HTTP/2, sane `Cache-Control` and `E-Tag` headers, etc.), minification, etc.

1. Make sure you have registered a domain name.
2. Sign up for [CloudFlare](https://www.cloudflare.com/) and create an account for your domain.
3. In your domain registrar's admin panel, point the nameservers to CloudFlare's (refer to [this awesome list of links for instructions for various registrars](https://surge.sh/help/adding-a-custom-domain)).
4. From the CloudFlare settings for that domain, enable HTTPS/SSL and set up a [Page Rule to force HTTPS redirects](https://support.cloudflare.com/hc/en-us/articles/200168306-Is-there-a-tutorial-for-Page-Rules-). (If you want to get fancy, you can also enable automatic minification for text-based assets [HTML/CSS/JS/SVG/etc.], which is a pretty cool feature if you don't want already have a build step for minification.)
5. If you don't already have one, create a new repository on GitHub to store your site's contents (preferably in the form of static web pages and assets; though not necessary, for the A-Frame site we use a static-site generator called [Hexo](https://github.com/hexojs/hexo)).
6. From your domain registrar's settings, create a `CNAME` record to point `<domain>.<tld>` to `<user>.github.io`. (Refer to [the GitHub docs for more information](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site).)
7. In your Github repo, create a file at the root called `CNAME` containing the domain name (e.g., `aframe.io`).
8. Push to GitHub Pages (either by pushing to `gh-pages` or `master` of your repo; or you can use the `master` branch of a repo named `<org>.github.io` - example: https://github.com/aframevr/aframevr.github.io/ automatically gets published to https://aframevr.github.io/, which redirects to https://aframe.io/)
9. You're done! All content will now be served to your users from CloudFlare.
