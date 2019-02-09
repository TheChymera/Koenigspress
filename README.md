# Königspress

Königspress is an Octopress theme designed with an emphasis on typography.
The main goal of this theme is to provide a similar reading experience as a high-quality typeset book or PDF document.
We recommend this theme for content conducive to lengthy lecture and high immersion (e.g. memoir-like blogs, diaries, short stories, novellas).

The theme was, conceptually, strongly inspired by [Pageturner](https://github.com/elisehein/Pageturner) by Elise Hein, which is in turn visually based on [a design blog](http://simonfosterdesign.com/blog/) by Simon Foster. 
Our code is however completely different, and more closely based on  [proper in-place editing](http://chymeric.eu/blog/2013/12/30/octopress-theme/) of the default octopress theme.

## Demos

Default theme: [Themespace Preview](http://themespace.github.io/Koenigspress/)

Actual blogs: [Märzwasser](http://mw.chymera.eu), [Minisimo](http://blog.blakepatches.me/), [Bro Kaizen's Blog](http://bro-kaizen.github.io)

*If you are using Königspress and would like to showcase your website, we would be very happy to add you to the list! Just tell us your URL via the [issue tracking system](https://github.com/TheChymera/Koenigspress/issues/3)!*

## Install

From your octopress blog root directory:

    $ git clone https://github.com/TheChymera/Koenigspress.git .themes/Koenigspress
    $ rake install[Koenigspress]
    $ rake generate

## Update

From your octopress blog directory:

    $ git -C .themes/Koenigspress pull origin master
    $ rake install[Koenigspress]
    $ rake generate
    
### Update and Keep Customizations

*For this to work, you have to track your website theme customizations on a remote (we call it ```mywebsiterepo```).*

    $ git -C .themes/Koenigspress pull origin master
    $ rake install[Koenigspress]
    $ cd ../..
    $ git fetch --all
    $ git reset --hard mywebsiterepo/master
    $ rake generate

## Awesome Authoring and Licensing Features!

Königspress is designed to be compatible with multi-authored blogs and even multi-authored articles.
The footer of the website specifies a website license - which for instance you could make proprietary if you don't want anybody cloning your website structure.

Separately, you - or guest authors - can specify per-article licenses for your content.
You may do this by adding a ```license: ``` specification to your post header.
Per-article licensing also supports hyperlinks, which we encourage you to use.

Header example:

    ---
    layout: post
    title: "Lorem"
    date: 2013-12-28 17:49:17 +0200
    comments: true
    categories: 
    author: <a rel="author" href="https://your.website.org">A. U. Thor</a>
    license: <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
    ---
    
## Per-Article Font Specification

Our focus on typography extends to providing the user with an easy interface to specify fonts per-article.
You can use the ```font:``` tag in your article header to choose any of the fonts imported under ```source/_includes/custom/head.html```.
Additionally, if the font of your choice has a lower legibility at the default font size you can use a percent specification in the ```fontsize``` tag to increase the article font size.
For a published per-article example, check out [this page](http://mw.chymera.eu/blog/2009/06/21/morgenrot/) - using only ```font: UnifrakturMaguntia``` and ```fontsize:110%```.
You can also see the source of that article on [this GitHub page](https://github.com/TheChymera/mw/blob/master/source/_posts/2014-01-07-morgenrot.markdown).

## Edit and History Links

If you choose to track your content via an open repository (on  GitHub, Bitbucket, etc.) you can also link to your article's history (in the footer) or allow users to contribute via the version controlling backend (link in the header, next to "COMMENTS").
Whitespace automatically enables this if you set the following variables in your `_config.yml` - e.g.:

```
history: https://github.com/youruser/yourblog/commits/master/source/
edit: https://github.com/youruser/yourblog/edit/master/source/
```

## AdSense for Search

You can enable Google AdSense™ for search via your whitespace search bar.
For this to work you have to set `simple_search` and `adsense_cse_partner_ID` in your `_config.yml` file (you will have to add a line for the second variable, as it is not used with any other themes).
The value for this variable can be extracted from the custom code for your search bar from a line such as the following:

```
<input type="hidden" name="cx" value="<adsense_cse_partner_ID>" />
```

Example for `_config.yml`:

```
simple_search: https://www.google.com/search
adsense_cse_partner_ID: partner-pub-9999999999999999:9999999999
```

## Customize

The theme can be customized just as the default octopress theme - by edditing the files under `/sass/custom` and under `/source/_includes/custom`.
Additionally, Königspress allows font and logo customization:

### Logos

The logo displayed in the upper right corner of the screen can be changed by changing the `/source/logo.png` file.
The "favourite icon" (displayed by many browsers in the tabs or bookmarks list) can be changed by changing the `/source/favicon.png` file.
Both these changes will only take effect after you run the next 

    $ bundle exec generate
    
Additionally, favicon changes may take a while to become visible due to browser caching.

You can customize the way in which the logo is displayed by editing its HTML under `/source/_includes/logo.html` and its CSS at the end of the `/sass/partials/_blog.scss` file.

### Fonts

Our emphasis on typography goes hand in hand with permitting the user to choose a typographical style to best complement his content.
We use the convenient [Google Fonts](http://www.google.com/fonts#AboutPlace:about) framework for importing free, open, and high-quality webfonts.

A number of these (which we believe are in tune with our design paradigm) are already loaded under `/source/_includes/custom/head.html`.
You can add any other font from Google Fonts via that file.
Of these fonts the ones which the website will actually use to display your content are specified in the `/sass/base/_typograpphy.scss` file.

## Contribute

Please report any glitches or theme inconsistencies that may bother you (preferably alongside a link to your website).
We highly appreciate forks, hacks, pull request, or any other kinds of contributions.

---
Released under the GPLv3 license.
Project led by Horea Christian (address all correspondence to: h.chr@mail.ru, or contact via [chymera.eu](http://chymera.eu)).
