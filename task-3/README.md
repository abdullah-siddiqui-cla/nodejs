# Exercise 3: Serve an HTML Form and Handle POST Request Using Core http Module
## Goal: Serve a form from a static HTML file located in the `views/` directory, accessible at `/books/new`, and handle form submissions at `POST /books`.

## Steps:
### 1. Create the HTML Form
Place an HTML file (`new-book.html`) inside a `/views` folder with a simple form to capture book details (title and author).

### 2. Create a GET route for `/books/new` that serves the form HTML file:
A sample html form,
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Add New Book</title>
</head>
<body>
  <h1>Add a New Book</h1>
  <form action="/books" method="POST">
    <label for="title">Book Title:</label>
    <input type="text" id="title" name="title" required>

    <label for="author">Author:</label>
    <input type="text" id="author" name="author" required>

    <button type="submit">Add Book</button>
  </form>
</body>
</html>
```

### 3. Create a `POST` route for `/books` to handle form submissions and log the data.

Use the following code to parse the body of the POST request,
```
let body = "";
req.on("data", (chunk) => {
  body += chunk.toString();
});

req.on("end", () => {
  const formData = new URLSearchParams(body);
  const title = formData.get("title");
  const author = formData.get("author");

  // `title` and `author` contains the input given my user in the form.

  // Write your code here for this task
});
```

## Folder Structure
```
views/
└── new-book.html
.
.
.
```