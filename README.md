# Browser Sync

[![Build status](https://ci.appveyor.com/api/projects/status/o508r208jkg13ob3?svg=true)](https://ci.appveyor.com/project/madskristensen/browsersync)

Download the extension at the
[VS Gallery](https://visualstudiogallery.msdn.microsoft.com/5741a548-5179-4a77-ad96-fca71535774d)
or get the
[nightly build](http://vsixgallery.com/extension/10d9b3af-1338-4c45-bc99-4ec38c3a11fb/)

------------------------------------------

A Visual Studio extension for ASP.NET projects that
leverages Browser Link to synchronize form field entry,
page navigation and scroll position.

![Browser Sync demo](art/animation.gif)

## Feature list

- Supports **all browsers** and emulators
- Typing in input fields is synced across browsers
- Supports the [Web Essentials Chrome extension](https://chrome.google.com/webstore/detail/web-essentials/mghdcdlpcdiodelbplncnodiiadljhhk)
- Keyboard hotkey to navigate all browsers to same URL
- Keyboard hotkey to synchronize scroll position
- Settings to enable/disable it all

For Browser Sync to work, make sure that Visual Studio's
Browser Link is up and running. Do that by running an
ASP.NET application from Visual Studio in one or more
browsers.

Hovering over the Browser Link button on the Standard
toolbar lets you know if Browser Link is connected.

![Browser Link Tooltip](art/browser-link-tooltip.png)

## Form field sync
This extension registers when typing occurs in these
HTML elements:

**Input**
```html
<input value="" id="email" />
```

Works for all input types including `range`, `number` and
`password`, `checkbox`, `datetime`, `color` and `radio`
to the extend browsers do.

The `file` type isn't supported due to browser security
constaints.

**Textarea**
```html
<textarea name="text"></textarea>
```

**Select**
```html
<select name="text">
  <option>First</option>
  <option>Second</option>
  <optgroup>
    <option>Third</option>
    <option>Fourth</option>
  </optgroup>
</select>
```

**Multi select**
```html
<select id="multiple" multiple>
  <option>First</option>
  <option>Second</option>
  <option>Third</option>
</select>
```

**contenteditable="true"**
```html
<div contenteditable="true" id="article" />
```

> The elements **MUST** have either an _id_ and/or _name_
> attribute for the sync to work.

## Navigation and scroll position
When you have multiple browser windows open onto the
website your building in Visual Studio, it is handy to
be able to navigate all the browsers to the same page on
your site.

Browser Sync makes that easy. Simply navigate to a page
on your site and hit **CTRL+ALT+Enter** in the browser.

That will navigate all the other browses to that same page.

Hit **CTRL+Alt+Enter** again and all browsers will move
to the same scroll position.

### Welcome message
The first time after installing this extension, a modal
overlay will be shown in all connected browser as you run
your website.

![Browser overlay](art/overlay.png)

This is to advertize the otherwise hidden feature of
navigational synchronization which is only available through
a keyboard shortcut in the browser and have no UI of their
own.

Hitting the **Thanks, got it** button or simply hitting
the **ESC** key will dismiss the modal for the duration of
the current Visual Studio session. It will dismiss the modal
in all the connected browsers.

By checking the checkbox, the modal will never be shown
again.

## Settings
You can disable Browser Sync very easily from the Browser
Link dropdown on the Standard toolbar.

![Browser Link Menu](art/browser-link-menu.png)

This will disable both the navigational sync using hotkeys
as well as the form field sync.

Both of those settings can be individually set in the
**Tools -> Options -> Web -> Browser Sync** dialog.

![Settings](art/settings.png)

## License

[Apache 2.0](LICENSE)