npm i local-web-server -g 
  ws -d dist
  ws -d dist -c
    compression doesn't seem to work.

npm i source-map-explorer -g
  source-map-explorer dist/vendor.bundle.js
  source-map-explorer dist/main.....js

ng build
ng build -prod --sourcemaps
  minify, remove compiler

start dist

compare change detection in angularjs, react, angular
  https://www.youtube.com/watch?v=QQ2plVD0gDI&feature=youtu.be&t=15m7s

angular compiler generates super-optimized js code from html templates, instead of letting
browser parse html templates.

angular language service extension in visual studio code
    auto complete in html templates
    check syntax errors in html templates

server-side rendering
    does it hurt for a component to use DOM api in lifecycle events?

npm run compile
  generates js code in dist/out-tsc/src/app/
  ngc is found in C:\lc\compiler-playground\node_modules\.bin

main.ts change to
```javascript
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModuleNgFactory } from '../dist/out-tsc/src/app/app.module.ngfactory';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModuleFactory(AppModuleNgFactory)
  .catch(err => console.log(err));
```
then the command window of ng serve,
ERROR in src/main.ts(4,36): error TS6143: Module '../dist/out-tsc/src/app/app.module.ngfactory' was resolved to 'C:/lc/compiler-playground/dist/out-tsc/src/app/app.module.ngfactory.js', but '--allowJs' is not set.
However, the browser is still updated.
