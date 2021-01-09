# teste-feed

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


http://feed43.com/feed.html?name=4502845176441015


RUNKIT:
https://npm.runkit.com/rss-parser

let Parser = require('rss-parser');
let parser = new Parser();

(async () => {

  let feed = await parser.parseURL('http://feed43.com/4502845176441015.xml');
  console.log(feed.title);

  feed.items.forEach(item => {
    console.log(item)
  });

})();
