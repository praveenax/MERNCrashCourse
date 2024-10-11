### **CSS Cheatsheet**

#### **1. CSS Syntax**

```css
selector {
  property: value;
}
```

- **Selector**: Targets the HTML element(s) to apply styles to.
- **Property**: The style you want to change (e.g., `color`, `font-size`, `margin`).
- **Value**: The value you assign to the property.

---

#### **2. Selectors**

- **Element Selector**:

  ```css
  p {
    color: blue;
  }
  ```

- **Class Selector**:

  ```css
  .classname {
    color: red;
  }
  ```

- **ID Selector**:

  ```css
  #idname {
    color: green;
  }
  ```

- **Universal Selector (`*`)**:

  ```css
  * {
    margin: 0;
  }
  ```

- **Group Selector**:

  ```css
  h1,
  h2,
  p {
    color: purple;
  }
  ```

- **Descendant Selector**:
  ```css
  div p {
    color: orange;
  }
  ```

---

#### **3. Colors**

- **Color by Name**:

  ```css
  color: red;
  ```

- **Hexadecimal**:

  ```css
  color: #ff0000;
  ```

- **RGB**:

  ```css
  color: rgb(255, 0, 0);
  ```

- **RGBA (with transparency)**:
  ```css
  color: rgba(255, 0, 0, 0.5);
  ```

---

#### **4. Text Styling**

- **Font Family**:

  ```css
  font-family: "Arial", sans-serif;
  ```

- **Font Size**:

  ```css
  font-size: 16px;
  ```

- **Font Weight**:

  ```css
  font-weight: bold;
  ```

- **Text Alignment**:

  ```css
  text-align: center;
  ```

- **Text Decoration**:

  ```css
  text-decoration: underline;
  ```

- **Text Transform** (uppercase, lowercase):
  ```css
  text-transform: uppercase;
  ```

---

#### **5. Box Model**

- **Width & Height**:

  ```css
  width: 100px;
  height: 200px;
  ```

- **Padding** (inside the box):

  ```css
  padding: 10px;
  ```

- **Margin** (outside the box):

  ```css
  margin: 20px;
  ```

- **Border**:
  ```css
  border: 2px solid black;
  ```

---

#### **6. Positioning**

- **Static** (default):

  ```css
  position: static;
  ```

- **Relative** (relative to its normal position):

  ```css
  position: relative;
  top: 10px;
  ```

- **Absolute** (relative to nearest positioned ancestor):

  ```css
  position: absolute;
  right: 10px;
  ```

- **Fixed** (relative to the viewport):

  ```css
  position: fixed;
  bottom: 0;
  ```

- **Z-index** (stacking order):
  ```css
  z-index: 2;
  ```

---

#### **7. Flexbox**

- **Display Flex**:

  ```css
  display: flex;
  ```

- **Justify Content** (horizontal alignment):

  ```css
  justify-content: center;
  ```

- **Align Items** (vertical alignment):

  ```css
  align-items: center;
  ```

- **Flex Direction** (row or column layout):
  ```css
  flex-direction: row;
  ```

---

#### **8. Grid Layout**

- **Display Grid**:

  ```css
  display: grid;
  ```

- **Grid Template Columns**:

  ```css
  grid-template-columns: repeat(3, 1fr);
  ```

- **Grid Gap**:
  ```css
  grid-gap: 10px;
  ```

---

#### **9. Backgrounds**

- **Background Color**:

  ```css
  background-color: lightblue;
  ```

- **Background Image**:

  ```css
  background-image: url("image.jpg");
  ```

- **Background Size**:
  ```css
  background-size: cover;
  ```

---

#### **10. Pseudo-Classes**

- **Hover**:

  ```css
  a:hover {
    color: green;
  }
  ```

- **Active**:

  ```css
  button:active {
    background-color: red;
  }
  ```

- **First Child**:
  ```css
  p:first-child {
    color: blue;
  }
  ```

---

#### **11. Transitions & Animations**

- **Transition**:

  ```css
  div {
    transition: all 0.5s ease;
  }
  ```

- **Animation**:

  ```css
  @keyframes example {
    from {
      background-color: red;
    }
    to {
      background-color: yellow;
    }
  }

  div {
    animation: example 5s infinite;
  }
  ```

---

#### **12. Media Queries**

- **Responsive Design**: Apply styles based on screen size.
  ```css
  @media only screen and (max-width: 600px) {
    body {
      background-color: lightgray;
    }
  }
  ```

---

#### **13. Display**

- **Block**:

  ```css
  display: block;
  ```

- **Inline**:

  ```css
  display: inline;
  ```

- **None** (hide element):
  ```css
  display: none;
  ```

---

#### **14. Overflow**

- **Overflow** (content inside the box):

  ```css
  overflow: scroll;
  ```

- **Text Overflow**:
  ```css
  text-overflow: ellipsis;
  ```

---

#### **15. Units**

- **Pixels (`px`)**: Fixed size.
- **Percentage (`%`)**: Relative to the parent element.
- **Em**: Relative to the font-size of the element.
- **Rem**: Relative to the font-size of the root element.

---
