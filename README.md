# install puppeteer
npm install puppeteer --save

# example

```nodejs
"use strict";
var puppeteer = require('puppeteer');

(async function screenshot() {
  const browser = await puppeteer.launch({ headless: true, args: ['--no-sandbox', '--disable-setuid-sandbox']  });
  const page = await browser.newPage();
  // await page.setViewport({
  //     width: 1200,
  //     height: 1200,
  //     deviceScaleFactor: 1,
  // });
  await page.goto('https://docker.com', {waitUntil: 'networkidle0'});
  await page.screenshot({ path: "docker.png" });
  await browser.close();
})()
```
