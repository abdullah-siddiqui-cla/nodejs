# Exercise 2: Serve Static Files from a /public Folder
## Goal: Serve static files (e.g., CSS, images, JavaScript) from a /public directory using Node’s http module and fs module.

## Steps:
### 1. Create a /public Folder:
Add some code files, such as an style.css, and script.js.

### 2. Modify the Server:
Check the request URL, and if it starts with `/public`, serve the file from that folder.
Use the `fs` module to read the requested file and serve it in the response.

## Hints
### 1. Import `fs` and `path` core modules as,
```
const fs = require('fs');
const path = require('path');
```
### 2. Use the following code snippet to return a code file,

```
const filePath = path.join(__dirname, req.url);
fs.readFile(filePath, (err, data) => {
  if (err) {
    res.writeHead(404);
    res.end('File not found');
  } else {
    res.writeHead(200);
    res.end(data);
  }
});
```