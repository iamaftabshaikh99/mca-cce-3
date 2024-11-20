### **Q1. Explain !important in CSS with Example**

#### **Definition**
The `!important` rule in CSS gives a CSS property the highest priority, overriding any other rules applied to the same element, even if those rules are more specific.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>!Important Example</title>
    <style>
        p {
            color: blue;
        }

        .override {
            color: red !important;
        }

        #specific {
            color: green;
        }
    </style>
</head>
<body>
    <p>This text is blue by default.</p>
    <p id="specific" class="override">This text is red due to !important.</p>
</body>
</html>
```

---

#### **Output**
1. The first paragraph is blue because of the default rule.
2. The second paragraph is red because `!important` overrides the green color set by the `id`.

---

### **Q2. Explain CSS Selectors with Example**

#### **Definition**
CSS selectors are patterns used to target and style HTML elements. They can target elements based on their type, class, id, or attributes.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Selectors Example</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        h1 {
            color: blue;
        }

        .highlight {
            background-color: yellow;
        }

        #unique {
            font-size: 24px;
        }

        [title] {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Hello, World!</h1>
    <p class="highlight">This paragraph is highlighted.</p>
    <p id="unique">This paragraph has unique styling.</p>
    <a href="#" title="Link Example">Link with attribute selector</a>
</body>
</html>
```

---

#### **Output**
1. The `h1` tag is blue.
2. The `.highlight` class gives the paragraph a yellow background.
3. The `#unique` id gives the paragraph a larger font size.
4. The anchor tag is underlined due to the attribute selector `[title]`.

---

### **Q3. Explain Z-Index with Example**

#### **Definition**
The `z-index` property specifies the stack order of elements. Elements with a higher `z-index` appear in front of those with a lower value.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Z-Index Example</title>
    <style>
        .box1 {
            width: 200px;
            height: 200px;
            background-color: red;
            position: absolute;
            top: 50px;
            left: 50px;
            z-index: 1;
        }

        .box2 {
            width: 200px;
            height: 200px;
            background-color: blue;
            position: absolute;
            top: 100px;
            left: 100px;
            z-index: 2;
        }
    </style>
</head>
<body>
    <div class="box1"></div>
    <div class="box2"></div>
</body>
</html>
```

---

#### **Output**
1. The blue box appears in front of the red box because its `z-index` is higher.

---

### **Q4. Explain Padding and Margin with Example**

#### **Definition**
1. **Padding**: Space between the content and the element's border.
2. **Margin**: Space outside the element, separating it from other elements.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Padding and Margin Example</title>
    <style>
        .box {
            width: 200px;
            height: 100px;
            background-color: lightblue;
            padding: 20px;
            margin: 30px;
            border: 2px solid black;
        }
    </style>
</head>
<body>
    <div class="box">Content Here</div>
</body>
</html>
```

---

#### **Output**
1. Padding creates space inside the border.
2. Margin creates space outside the border, separating the element from others.

---

### **Q5. Explain Vertical Align in CSS with Example**

#### **Definition**
The `vertical-align` property aligns inline or table-cell elements vertically within a container.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vertical Align Example</title>
    <style>
        .container {
            height: 200px;
            display: table;
            border: 1px solid black;
        }

        .content {
            display: table-cell;
            vertical-align: middle;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="content">Centered Content</div>
    </div>
</body>
</html>
```

---

#### **Output**
The content is vertically and horizontally aligned in the middle of the container.

---

### **Q6. Explain Background-Repeat in CSS with Example**

#### **Definition**
The `background-repeat` property controls how a background image is repeated.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Background Repeat Example</title>
    <style>
        .box {
            width: 300px;
            height: 150px;
            background-image: url('https://via.placeholder.com/50');
            background-repeat: repeat-x;
        }
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

---

#### **Output**
The background image repeats horizontally across the element.

---

### **Q7. Explain Background-Image in CSS with Example**

#### **Definition**
The `background-image` property sets an image as the background of an element.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Background Image Example</title>
    <style>
        .box {
            width: 300px;
            height: 150px;
            background-image: url('https://via.placeholder.com/300x150');
            background-size: cover;
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

---

#### **Output**
A placeholder image fills the element's background.

---

### **Q8. Explain Concept of Overflow in CSS with Example**

#### **Definition**
The `overflow` property controls how content that overflows the element's bounds is displayed.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Overflow Example</title>
    <style>
        .container {
            width: 200px;
            height: 100px;
            overflow: hidden;
            border: 1px solid black;
        }

        .content {
            width: 300px;
            height: 150px;
            background-color: lightblue;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="content">This content is clipped.</div>
    </div>
</body>
</html>
```

---

#### **Output**
The content is clipped to fit within the container dimensions.


### **Q9. Explain Text-Decoration Property in CSS with Example**

#### **Definition**
The `text-decoration` property specifies the style of text decorations, such as underlining, overlining, striking through, or none.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Text Decoration Example</title>
    <style>
        .underline {
            text-decoration: underline;
        }

        .overline {
            text-decoration: overline;
        }

        .line-through {
            text-decoration: line-through;
        }

        .none {
            text-decoration: none;
        }
    </style>
</head>
<body>
    <p class="underline">This text is underlined.</p>
    <p class="overline">This text has an overline.</p>
    <p class="line-through">This text is struck through.</p>
    <p class="none">This text has no decoration.</p>
</body>
</html>
```

---

#### **Output**
1. The first paragraph is underlined.
2. The second paragraph has a line above it (overline).
3. The third paragraph has a line through it (strikethrough).
4. The fourth paragraph has no decoration.

---

### **Q10. What is Display Property in CSS? Explain Inline and Inline-Block**

#### **Definition**
The `display` property specifies how an element is displayed on the page. Common values are:
- **inline**: The element does not start on a new line and does not respect height/width.
- **inline-block**: Behaves like `inline` but respects height/width.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Display Property Example</title>
    <style>
        .inline {
            display: inline;
            background-color: lightblue;
            padding: 5px;
        }

        .inline-block {
            display: inline-block;
            background-color: lightgreen;
            width: 100px;
            height: 50px;
            padding: 10px;
        }
    </style>
</head>
<body>
    <span class="inline">Inline Element</span>
    <span class="inline-block">Inline-Block Element</span>
</body>
</html>
```

---

#### **Output**
1. The `inline` element appears on the same line without respecting width/height.
2. The `inline-block` element behaves inline but respects width, height, and padding.

---

### **Q11. Explain Border and Background in CSS with Example**

#### **Definition**
1. **Border**: Defines the boundary around an element (e.g., width, style, color).
2. **Background**: Specifies the element's background color or image.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Border and Background Example</title>
    <style>
        .box {
            width: 200px;
            height: 100px;
            border: 5px dashed red;
            background-color: lightblue;
            background-image: url('https://via.placeholder.com/50');
            background-repeat: no-repeat;
            background-position: center;
        }
    </style>
</head>
<body>
    <div class="box">This is a box</div>
</body>
</html>
```

---

#### **Output**
1. A dashed red border surrounds the element.
2. The background has a light blue color with a centered placeholder image.

---

### **Q12. Explain GET & POST Method with Example**

#### **Definition**
1. **GET**: Sends data via URL query parameters. Used for retrieving data.
2. **POST**: Sends data in the HTTP body. Used for sending secure or large data.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GET and POST Example</title>
</head>
<body>
    <h1>GET Example</h1>
    <form action="https://example.com/search" method="GET">
        <label for="query">Search:</label>
        <input type="text" id="query" name="q">
        <button type="submit">Submit</button>
    </form>

    <h1>POST Example</h1>
    <form action="https://example.com/login" method="POST">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username">
        <button type="submit">Submit</button>
    </form>
</body>
</html>
```

---

#### **Output**
1. **GET Form**: Sends the input data via URL parameters (`?q=value`).
2. **POST Form**: Sends the input data securely in the request body.

---

### **Q13. Explain Position Property with Example**

#### **Definition**
The `position` property controls how elements are positioned on the page. Common values:
- `static` (default), `relative`, `absolute`, `fixed`, `sticky`.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Position Property Example</title>
    <style>
        .static {
            position: static;
            background-color: lightgray;
        }

        .relative {
            position: relative;
            top: 20px;
            background-color: lightgreen;
        }

        .absolute {
            position: absolute;
            top: 50px;
            left: 50px;
            background-color: lightblue;
        }

        .fixed {
            position: fixed;
            top: 10px;
            right: 10px;
            background-color: lightcoral;
        }
    </style>
</head>
<body>
    <div class="static">Static Position</div>
    <div class="relative">Relative Position</div>
    <div class="absolute">Absolute Position</div>
    <div class="fixed">Fixed Position</div>
</body>
</html>
```

---

#### **Output**
1. The `relative` element is offset from its normal position.
2. The `absolute` element is positioned relative to the closest positioned ancestor.
3. The `fixed` element remains in place relative to the viewport.

---

### **Q14. Explain `<style>` & `<head>` Tag with Example**

#### **Definition**
1. **`<style>`**: Embeds CSS directly into the HTML document.
2. **`<head>`**: Contains meta information, styles, and scripts for the page.

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Style and Head Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        h1 {
            color: blue;
        }
    </style>
</head>
<body>
    <h1>Styled Heading</h1>
</body>
</html>
```

---

#### **Output**
The `<head>` organizes metadata and styling. The `<style>` tag applies CSS rules to the body and `h1` elements.

---

### **Q15. Explain `rem` in CSS**

#### **Definition**
The `rem` unit stands for "root em" and is relative to the font size of the root element (`<html>`).

---

#### **Example**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>rem Example</title>
    <style>
        html {
            font-size: 16px; /* 1rem = 16px */
        }

        h1 {
            font-size: 2rem; /* 2rem = 32px */
        }

        p {
            font-size: 1rem; /* 1rem = 16px */
        }
    </style>
</head>
<body>
    <h1>Heading with rem</h1>
    <p>Paragraph with rem</p>
</body>
</html>
```

---

#### **Output**
1. The `<h1>` font size is 32px (`2rem`).
2. The `<p>` font size is 16px (`1rem`).
