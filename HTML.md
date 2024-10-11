

### **HTML Cheatsheet**

#### **1. HTML Document Structure**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Content goes here -->
  </body>
</html>
```

- **`<!DOCTYPE html>`**: Defines the document type and version (HTML5).
- **`<html>`**: Root element of the HTML document.
- **`<head>`**: Contains metadata, title, links to stylesheets, and scripts.
- **`<body>`**: Contains the visible content of the webpage.

---

#### **2. Basic HTML Tags**

- **`<h1>` to `<h6>`**: Headings (H1 is the largest, H6 is the smallest).

  ```html
  <h1>This is a Heading</h1>
  ```

- **`<p>`**: Paragraphs.

  ```html
  <p>This is a paragraph.</p>
  ```

- **`<a>`**: Anchor tag for links.

  ```html
  <a href="https://www.example.com">Visit Example</a>
  ```

- **`<img>`**: Image tag.

  ```html
  <img src="image.jpg" alt="description" />
  ```

- **`<br>`**: Line break.

  ```html
  <p>Line 1<br />Line 2</p>
  ```

- **`<hr>`**: Horizontal rule for separating content.
  ```html
  <hr />
  ```

---

#### **3. Lists**

- **Unordered List (`<ul>`)**:

  ```html
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
  ```

- **Ordered List (`<ol>`)**:
  ```html
  <ol>
    <li>First</li>
    <li>Second</li>
  </ol>
  ```

---

#### **4. Forms**

- **Form Structure**:

  ```html
  <form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" />

    <input type="submit" value="Submit" />
  </form>
  ```

- **Form Elements**:

  - **`<input>`**: For text, email, password, etc.

    ```html
    <input type="text" placeholder="Enter your name" />
    ```

  - **`<textarea>`**: Multi-line text input.

    ```html
    <textarea rows="4" cols="50">Your message</textarea>
    ```

  - **`<select>`**: Dropdown list.
    ```html
    <select>
      <option value="option1">Option 1</option>
      <option value="option2">Option 2</option>
    </select>
    ```

---

#### **5. Tables**

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>John</td>
    <td>30</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>25</td>
  </tr>
</table>
```

- **`<table>`**: Defines a table.
- **`<tr>`**: Table row.
- **`<th>`**: Table header cell.
- **`<td>`**: Table data cell.

---

#### **6. Semantic HTML**

- **`<header>`**: Defines the header of a document or section.

  ```html
  <header>This is a header</header>
  ```

- **`<footer>`**: Defines the footer of a document or section.

  ```html
  <footer>This is a footer</footer>
  ```

- **`<nav>`**: Defines navigation links.

  ```html
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
  </nav>
  ```

- **`<article>`**: Represents an independent, self-contained content.

  ```html
  <article>This is an article</article>
  ```

- **`<section>`**: Defines sections within a document.
  ```html
  <section>This is a section</section>
  ```

---

#### **7. Media Tags**

- **`<img>`**: Displays an image.

  ```html
  <img src="image.jpg" alt="Image description" />
  ```

- **`<video>`**: Embeds a video.

  ```html
  <video controls>
    <source src="movie.mp4" type="video/mp4" />
  </video>
  ```

- **`<audio>`**: Embeds audio content.
  ```html
  <audio controls>
    <source src="sound.mp3" type="audio/mpeg" />
  </audio>
  ```

---

#### **8. Block vs Inline Elements**

- **Block Elements**: Take up the full width (e.g., `<div>`, `<p>`, `<h1>`, `<table>`).

  ```html
  <div>This is a block element</div>
  ```

- **Inline Elements**: Only take up the space of their content (e.g., `<span>`, `<a>`, `<img>`).
  ```html
  <span>This is inline</span>
  ```

---

#### **9. Comments**

- **HTML Comment**:
  ```html
  <!-- This is a comment -->
  ```

---

#### **10. Metadata & Head Elements**

- **Meta Tags**: Provide metadata such as character set and viewport settings.

  ```html
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  ```

- **Linking Stylesheets**:

  ```html
  <link rel="stylesheet" href="styles.css" />
  ```

- **Adding JavaScript**:
  ```html
  <script src="script.js"></script>
  ```

---

This **HTML Cheatsheet** covers the essential elements, attributes, and concepts, helping you build a strong foundation for web development with HTML!
