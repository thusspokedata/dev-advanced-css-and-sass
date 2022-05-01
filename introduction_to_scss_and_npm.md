cd starter/

npm install node-sass --save-dev

npm install jquery --save

npm install <em>in case I delete the node_modules folder</em>

npm run compile:sass


package.json:
```scss

{
  "name": "starter",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "compile:sass": "node-sass sass/main.scss css/style.css -w"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "node-sass": "^7.0.1"
  },
  "dependencies": {
    "jquery": "^3.6.0"
  }
}


```

npm run compile:sass
