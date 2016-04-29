# cordova-icon-gm-ma

Automatic icon resizing for Cordova. Add `icon.png` to the root folder of your Cordova project and use cordova-icon-gm to automatically resize, copy and configure the icon for all current Android and iOS devices.

### Updates in this Fork:
It now is cordova 6.1.1 compatible (ios icon paths changed)

It now supports custom icons paths per platform

It uses ImageMagic per default

### Manual usage
1. Install ImageMagic binaries from http://www.imagemagick.org/script/binary-releases.php
2. `npm install https://github.com/moderna/cordova-icon-gm-ma.git --save`
3. Place `icon.png` to a res/3_used_by_cordova/icon/<anroid/io/...> folder of your Cordova project
4. Run `cordova-icon-gm-ma`.

### Automated usage
1. Install ImageMagic binaries from http://www.imagemagick.org/script/binary-releases.php

2. `npm install https://github.com/moderna/cordova-icon-gm-ma.git --save-dev`

3. Create `my-icon-hook.js`
    ```javascript
    var icon = require('cordova-icon-gm-ma');
    
    module.exports = function() {
      return icon.generate();
    };
    ```

4. Add hook to `config.xml`
    ```xml
    <hook src="my-icon-hook.js" type="after_prepare" />
    ```

That's it. The icons will be auto generated after each prepare event.

### Requirements
- GraphicsMagick
- At least one platform was added to your project
- Cordova's config.xml file must exist in the root folder

### Credits
All credit goes to [Carlos Antonio] (https://github.com/disusered) for his fork of Alex Dislers project and also to [Alex Disler](https://github.com/AlexDisler) for his [cordova-icon](https://github.com/AlexDisler/cordova-icon) module, from which this project is forked from. The node [imagemagick](https://www.npmjs.org/package/imagemagick) module is deprecated in favor of [gm](https://www.npmjs.org/package/gm).

### License

MIT
