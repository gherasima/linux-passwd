# passwd-linux
Node.js module for checking and changing Linux user and password


## Installation
```bash
$  npm install passwd-linux
```


## Features

    * Check if user exist
    * Change password without verify the old password first
    * Change password if user exist and old password is correct (SHA512 only, RHEL 6 & 7)
    * Check if old password is correct (SHA512 only, RHEL 6 & 7)


## Usage

Check if user exist:
```js
var passwd = require('passwd-linux');

passwd.checkUser('username', function (error, response) {
    "use strict";
    if (error) {
        console.log(error);
    } else {
        console.log(response);
    }
});
```

Change password without verify the old password first:

```js
var passwd = require('passwd-linux');

passwd.changePassNV('username', 'password', function (error, response) {
    "use strict";
    if (error) {
        console.log(error);
    } else {
        console.log(response);
    }
});
```

Change password if user exist and old password is correct (SHA512 only):

```js
var passwd = require('passwd-linux');

passwd.changePass('username', 'password', 'newpassword', function (error, response) {
    "use strict";
    if (error) {
        console.log(error);
    } else {
        console.log(response);
    }
});
```

Check if old password is correct (SHA512 only):

```js
var passwd = require('passwd-linux');

passwd.checkPassSHA512('username', 'password', function (error, response) {
    "use strict";
    if (error) {
        console.log(error);
    } else {
        console.log(response);
    }
});

```


## Release History

|Version  |Status|Functionality |
|---      |---  |---           |
|1.0.0      |released  |Initial release   |
|1.0.1      |released  |Bug fixes   |
|1.0.2      |released  |Bug fixes   |
|1.0.3      |released  |Bug fixes   |
|1.0.4      |released  |Bug fixes   |
|1.1.0      |released  |Added checkUser and changePassNV|


## Todo

* Add support for MD5 (RHEL 4 & 5)


## License

MIT

