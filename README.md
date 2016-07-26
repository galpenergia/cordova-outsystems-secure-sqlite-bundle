# OutSystems Secure SQLite Plugin
Cordova meta-plugin that bundles requirements for secure SQLite device storage and initialization code for easy usage within OutSystems Platform native mobile apps.

## Supported Platforms
- iOS
- Android
- Windows

## Installation
```shell
cordova plugin add https://github.com/OutSystems/cordova-outsystems-secure-sqlite-bundle.git
```

## Usage

The API is essentially unchanged from the bundled [Cordova SQLCipher Adapter](https://github.com/litehelpers/Cordova-sqlcipher-adapter), but the encryption key creation and usage is completely managed by this plugin using [SecureStorage](https://github.com/Crypho/cordova-plugin-secure-storage).
```javascript
var options = { 
  name: 'sample.db',
  location: 'default',
  key: 'secure-encryption-key' /* not used, will be overriden by this plugin */
};
window.sqlitePlugin.openDatabase(options, successCallback, errorCallback);
```

Refer to the Cordova SQLCipher Adapter plugin documentation for samples and details of the supported features.

## Known Limitations
- Will fail to open existing databases that are not encrypted
  - *Workaround*: either delete it prior to calling `openDatabase` or use a different database name.

---

LICENSE
=======

[The MIT License (MIT)](http://www.opensource.org/licenses/mit-license.html)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.  
