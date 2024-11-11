# Exercise 4: Render a List of Books Using EJS
## Goal: Use EJS to render a list of books on the route GET `/books`, displaying them in an unordered list in the `views/books.ejs` file.

## Steps:

### 1. Create EJS Template `views/books.ejs` with the following content,
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Book List</title>
</head>
<body>
  <h1>Book List</h1>
  <ul>
    <% books.forEach(book => { %>
      <li><strong><%= book.title %></strong> by <%= book.author %></li>
    <% }); %>
  </ul>
</body>
</html>
```

### 2. Render the `books.ejs` on `GET /books` in `index.js` file
- Define a simple array of books (with properties like title and author).
- Render the books.ejs file, passing the book list as data to display each book title in an unordered list.

## Folder structure
```
views/
└── books.ejs
└── new-book.html
```

## Hint
```
// Sample book data
const books = [
  { title: "To Kill a Mockingbird", author: "Harper Lee" },
  { title: "1984", author: "George Orwell" },
  { title: "Moby Dick", author: "Herman Melville" },
];

const server = http.createServer((req, res) => {
  ...

  if (req.method === "GET" && req.url === "/books") {
    // Render the books.ejs template using `path` and `fs.readFile`.
  }
  
  ...
});

server.listen(6001, () => {
  console.log("Server is listening on port 6001");
});

```
