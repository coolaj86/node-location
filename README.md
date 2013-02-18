location
====

A mock location object for unit tests and such and to maintain compatibility between `Ender.JS` and `Node.JS`

For best results, create a `location.config.js` in the working directory of your app that returns a location object that should be used.

Current Implementation
---

    var fs = require('fs')
      , location
      , defaultLocation
      ;

    defaultLocation = {
      "origin": "http://localhost:3000",
      "pathname": "/",
      "host": "localhost:3000",
      "hostname": "localhost",
      "port": "3000",
      "search": "",
      "hash": "#home",
      "href": "http://localhost:3000/#home",
      "protocol": "http:"
    };

    try {
      // TODO try all from `__dirname` to `/` before giving up
      location = fs.readFileSync('./location.config.js');
    } catch(e) {
      location = defaultLocation;
    }

    module.exports = location;

TODO
---

Look for `__dirname + "location.config.js"` and then look up one directory at each failure before finally giving up and using the default object.

LICENSES
===

MIT

> Copyright (c) 2011 AJ ONeal
>
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Apache v2

> Copyright 2011 AJ ONeal
>
> Licensed under the Apache License, Version 2.0 (the "License");
> you may not use this file except in compliance with the License.
> You may obtain a copy of the License at
>
>   <http://www.apache.org/licenses/LICENSE-2.0>
>
> Unless required by applicable law or agreed to in writing, software
> distributed under the License is distributed on an "AS IS" BASIS,
> WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
> See the License for the specific language governing permissions and
> limitations under the License.
