# Bookmarklet

Creates a shortened bookmarklet from your JavaScript code, optionally including the jQuery library.

Selecting the *Bookmarklet > Create HTML Link* command will create a _JavaScript Bookmarklet_ in the form of an HTML link from your current editor's content. The bookmarklet code will be copied to your system clipboard.

![Bookmarklet in Action!](https://raw.githubusercontent.com/nwinkler/bookmarklet/master/bookmarklet.gif)

In addition to the option of generating a link, the `Bookmarklet: Create JavaScript` command can be used to create just the JavaScript, without the HTML link tag.

## Including jQuery

Two additional commands (`Bookmarklet: Create HTML Link With jQuery` and `Bookmarklet: Create JavaScript With jQuery`) can be used to create the respective HTML link or just the JavaScript code with the additional feature or loading the jQuery library if it's not already available on the page.

The jQuery library will be loaded from the Google CDN.

Configuration options can be used to specify which version of jQuery to use, and whether to include the minified version or not - see below for details.

## Example

Given this code in your current editor

```javascript
var div = document.createElement('div');
div.setAttribute('foo', 'bar');
var text = document.createTextNode("This was added using the 'Bookmarklet' & Atom.io?!");
div.appendChild(text);
document.body.appendChild(div);
```

The *Bookmarklet > Create HTML Link* command will generate the following bookmarklet:

```html
<a href="javascript:(function(){var%20div%3Ddocument.createElement(%22div%22)%3Bdiv.setAttribute(%22foo%22%2C%22bar%22)%3Bvar%20text%3Ddocument.createTextNode(%22This%20was%20added%20using%20the%20'Bookmarklet'%20%26%20Atom.io%3F!%22)%3Bdiv.appendChild(text)%2Cdocument.body.appendChild(div)%3B})();">Click Me</a>
```

## Configuration Options

The package's configuration page has the following options. The _jQuery_ options are only used when one of the commands that include the jQuery library is executed.

* `jQuery Version`: The version of jQuery to use, e.g. _1.11.0_. Defaults to _1_, which will load the latest stable release of jQuery 1.
* `Use Minified jQuery`: Use the minified or unminified version of the jQuery library. Defaults to _true_, which will include the minified version.

## Keybinding

The Bookmarklet package does not define a default keybinding. To add one, use the following snippet in your local `~/.atom/keymap.cson` file:

```
'atom-text-editor:not(.mini)':
  'ctrl-alt-b': 'bookmarklet:create-link'
```

## Install

### Command Line

```bash
apm install bookmarklet
```

### Atom

Open the Atom settings/preferences, then select the _Packages_ entry and search for _Bookmarklet_ using the search field. In the results, click the _Install_ button of the _Bookmarklet_ package.

# TODO

* Unit tests
