# Bookmarklet(s) <!-- omit from toc -->

A small collection of [JavaScript](https://en.wikipedia.org/wiki/JavaScript) [Bookmarklet](https://en.wikipedia.org/wiki/Bookmarklet)(s).

* [How it works](#how-it-works)
* [Collection](#collection)
  * [Dark Mode](#dark-mode)
  * [Notepad](#notepad)
  * [Embed](#embed)
  * [ExifExodus](#exifexodus)
  * [UpToBox](#uptobox)
* [Security](#security)
* [Author](#author)

## How it works

Basically, every modern browsers will evaluate JavaScript code written in the address bar. So what the bookmarklet does is just passing the JavaScript code as URL to the address bar and it gets evaluated.

As long as the website where you are running the bookmarklet don't have specific hardening instructions it will work.

Read the [security](#security) section for more details.

## Collection

Here is a list of existing bookmarklets.

> Feel free to contact me if you want to add yours to the list.

### Dark Mode

Used to apply some kind of dark theme over websites using white backgrounds.

```js
javascript:(function(){ var h=document.getElementsByTagName('head')[0],s=document.createElement('style');s.setAttribute('type','text/css'); s.appendChild(document.createTextNode('html{-webkit-filter:invert(100%) hue-rotate(180deg) contrast(70%) !important; -moz-filter:invert(100%) hue-rotate(180deg) contrast(70%) !important; background: #fff;} .line-content {background-color: #fefefe;}'));h.appendChild(s); })()
```

#### Installation <!-- omit from toc -->

Create a new bookmark and define the following:

* Name: __Dark Mode__
* URL: _Put the JavaScript code above in place of the `URL`._

#### Compatibility <!-- omit from toc -->

It should work in __Firefox__ and every __Chromium__ based browsers.

#### Improvements <!-- omit from toc -->

Some improvements can be made by adding some nice tricks from this [page](https://surf.suckless.org/stylesheets/darkmode_css/).

### Notepad

Used to create some sort of simple notepad inside the browser instance.

```js
data:text/html,<html contenteditable>
```

#### Installation <!-- omit from toc -->

Create a new bookmark and define the following:

* Name: __Notepad__
* URL: _Put the JavaScript code above in place of the `URL`._

#### Compatibility <!-- omit from toc -->

It should work in every modern browsers.

### Embed

Get info from any web service or page.

```js
javascript:(function(){window.open('http://oscarotero.com/embed3/demo/index.php?url=%27+document.location)})();
```

> __Warning:__ This bookmarklet use a third party service. See [here](https://github.com/oscarotero/Embed) more details.

#### Installation <!-- omit from toc -->

Create a new bookmark and define the following:

* Name: __Check with Embed__
* URL: _Put the JavaScript code above in place of the `URL`._

#### Compatibility <!-- omit from toc -->

It should work in every modern browsers.

### ExifExodus

Remove GPS data from your photos before you upload them.

```js
javascript:(function(d){d.body.appendChild(d.createElement('script')).src='http://exifexodus.com/assets/js/exifexodus.min.js'})(document)
```

> __Warning:__ This bookmarklet use a third party service. See [here](https://github.com/dmotz/ExifExodus) more details.

#### Installation <!-- omit from toc -->

Create a new bookmark and define the following:

* Name: __ExifExodus__
* URL: _Put the JavaScript code above in place of the `URL`._

#### Compatibility <!-- omit from toc -->

It should work in every modern browsers.

### UpToBox

Extract existing [UpToBox](https://uptobox.com) streaming links from the [Darkino](https://darkino.io) website and convert them to download links in order to bypass their awful and bloat download page.

```js
javascript:(function(){var fURL = document.getElementsByClassName('zw_frame')[0].src,pURL = new URL(fURL),cProto = pURL.protocol,cHost = pURL.host.replace('stream','box'),cPath = pURL.pathname.replace('/iframe',''),nURL = cProto + '//' + cHost + cPath;prompt("Enter Ctrl+C to copy this UpToBox hyperlink. :", nURL);window.close();})();
```

#### Installation <!-- omit from toc -->

Create a new bookmark and define the following:

* Name: __Extract UpToBox Link__
* URL: _Put the JavaScript code above in place of the `URL`._

#### Compatibility <!-- omit from toc -->

It should work in every modern browsers.

## Security

You can also use any bookmarklet as a security test to see if the website you are visiting is allowing you to inject some JavaScript code in its context.

Take the [dark mode](#dark-mode) bookmarklet for example, if it does not work on the website you are visiting, it will mean that the website has been hardened and does not allow code injection.

Most of the time, you should find some errors being logged in the console when it does not work.

## Author

* __Jiab77__