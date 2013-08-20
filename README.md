jQuery Clipboard
================

jQuery Clipboard plugin: copy any text to the user's clipboard. Implements ZeroClipboard over the jQuery plugin layer.


## Usage

### 1. Include Scripts

```html
<script type="text/javascript" src="/path/to/javascripts/jquery.js"></script>
<script type="text/javascript" src="/path/to/javascripts/jquery.clipboard.js"></script>
```


### 2. Apply On An Element

```javascript
$(document).ready(function(){
    $('.code-block a.code-copy').clipboard({
        path: '/path/to/flashes/jquery.clipboard.swf',
        copy: $(this).parents('.code-block').find('.code-lines').text()
    });
});
```


### 3. More Docs

More docs can be found on http://www.steamdev.com/zclip/

jQuery Clipboard is mostly based on jQuery.zClip, the plugin APIs remain barely the same.