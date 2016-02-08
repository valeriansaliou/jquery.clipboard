jQuery Clipboard
================

[![Build Status](https://travis-ci.org/valeriansaliou/jquery.clipboard.svg?branch=master)](https://travis-ci.org/valeriansaliou/jquery.clipboard) [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/valeriansaliou/jquery.clipboard?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

jQuery Clipboard plugin: copy any text to the user's clipboard. Implements ZeroClipboard over the jQuery plugin layer.


## Usage

### 1. Before You Start

- Due to Flash restrictions, **jQuery Clipboard cannot be used on local domains** (localhost, .dev), you need to serve it from a genuine Internet domain (.com, .net or so)
- Please check that **you are using at least jQuery 1.7** - jQuery Clipboard won't work with versions below!


### 2. Include Scripts

```html
<script type="text/javascript" src="/path/to/javascripts/jquery.js"></script>
<script type="text/javascript" src="/path/to/javascripts/jquery.clipboard.js"></script>
```


### 3. Apply On An Element

```javascript
$(document).ready(function() {
    var copy_sel = $('.code-block a.code-copy');

    // Disables other default handlers on click (avoid issues)
    copy_sel.on('click', function(e) {
        e.preventDefault();
    });

    // Apply clipboard click event
    copy_sel.clipboard({
        path: '/path/to/flashes/jquery.clipboard.swf',

        copy: function() {
            var this_sel = $(this);

            // Hide "Copy" and show "Copied, copy again?" message in link
            this_sel.find('.code-copy-first').hide();
            this_sel.find('.code-copy-done').show();

            // Return text in closest element (useful when you have multiple boxes that can be copied)
            return this_sel.closest('.code-block').text();
        }
    });
});
```


### 4. More Docs

More docs can be found on http://www.steamdev.com/zclip/

jQuery Clipboard is mostly based on jQuery.zClip, the plugin APIs remain almost the same.
