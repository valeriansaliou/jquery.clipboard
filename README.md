jQuery Clipboard
================

jQuery Clipboard plugin: copy any text to the user's clipboard. Implements ZeroClipboard over the jQuery plugin layer.

[![build status](https://ci.frenchtouch.pro/projects/10/status.png?ref=master)](https://ci.frenchtouch.pro/projects/10?ref=master)


## Usage

### 1. Include Scripts

```html
<script type="text/javascript" src="/path/to/javascripts/jquery.js"></script>
<script type="text/javascript" src="/path/to/javascripts/jquery.clipboard.js"></script>
```

**Important: please check that you are using at least jQuery 1.7 - jQuery Clipboard won't work with versions below!**


### 2. Apply On An Element

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


### 3. More Docs

More docs can be found on http://www.steamdev.com/zclip/

I wrote a tutorial about jQuery Clipboard at https://waaave.com/tutorial/jquery/copy-text-to-clipboard-using-jquery/

jQuery Clipboard is mostly based on jQuery.zClip, the plugin APIs remain barely the same.