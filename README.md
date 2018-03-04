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
  