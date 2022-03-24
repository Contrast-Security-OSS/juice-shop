_contrast_security.yaml_

```yaml
agent:
  node:
    rewrite_cache:
      enable: true
      path: .contrast # or /path/to/cache
```

<hr>

```sh
npx contrast-transpile ./build/app.js
```

look at _.contrast/_

example:
```js
"use strict";
/*
 * Copyright (c) 2014-2022 Bjoern Kimminich & the OWASP Juice Shop contributors.
 * SPDX-License-Identifier: MIT
 */
require('./lib/startup/validateDependencies')().then(() => {
    const server = require('./server');
    server.start();
});
//# sourceMappingURL=app.js.map
```
becomes:
```js
"use strict";
/*
 * Copyright (c) 2014-2022 Bjoern Kimminich & the OWASP Juice Shop contributors.
 * SPDX-License-Identifier: MIT
 */

const ContrastMethods = global.ContrastMethods || (() => {
  throw new SyntaxError("ContrastMethods undefined during compilation");
})();

const JSON = global.ContrastJSON || JSON;
const Function = global.ContrastFunction || Function;
const Object = global.ContrastObject || Object;
const String = global.ContrastString || String;
(function (exports, require, module, __filename, __dirname) {
  require('./lib/startup/validateDependencies')().then(() => {
    const server = require('./server');

    server.start();
  }); //# sourceMappingURL=app.js.map

}).apply(this, arguments);
```

<hr>

