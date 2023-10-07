# **Bootstrap 5 for Beginners: A Comprehensive Hands-on Guide**

## Introduction to Bootstrap Setup

### **Step-by-step Guide:**

1. **Downloading Bootstrap:**
   Navigate to [Bootstrap's download page](https://getbootstrap.com/docs/5.3/getting-started/download/). Here, you'll find various methods to integrate Bootstrap, but for this guide, we'll use the compiled CSS and JS.

2. **Extracting the Downloaded File:**
   Once downloaded, you'll get a ZIP file named something like `bootstrap-5.x.x-dist.zip` (where 5.x.x is the version number). Extract this ZIP file. You should see a folder named `bootstrap-5.x.x-dist`.

3. **Locate Essential Files:**
   Inside the extracted folder:
   - Navigate to the `css` directory. Here, find the file named `bootstrap.min.css`. This is the minified version of Bootstrap's core CSS.
   - Navigate to the `js` directory. Here, you'll find the file named `bootstrap.bundle.min.js`. This file contains Bootstrap’s JavaScript functionalities along with Popper.js (required for tooltips, popovers, and dropdowns).

4. **Setting Up Your Project:**
   Create a new project directory and place the two aforementioned files (or you can link directly to them if you prefer) in appropriate folders, e.g., `css/` and `js/`.

### **Folder Structure:**

Here's how your folder structure might look:

```
/my-bootstrap-project/
|-- css/
|   |-- bootstrap.min.css
|
|-- js/
|   |-- bootstrap.bundle.min.js
|
|-- index.html
```

### **Bootstrap Boilerplate:**

To kickstart your Bootstrap journey, use the following boilerplate for your `index.html`:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Starter</title>

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="css/bootstrap.min.css">
</head>

<body>

    <!-- Your content goes here -->

    <!-- Optional JavaScript; Bootstrap JS and Popper.js -->
    <script src="js/bootstrap.bundle.min.js"></script>
</body>

</html>
```

With this setup, you're ready to start integrating the Bootstrap components and utilities described in the the below guide.

## **1. Responsive Grid System**

### **Manual CSS**:

```css
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.row {
    display: flex;
    flex-wrap: wrap;
}

.column {
    flex: 1;
    padding: 10px;
}
```

**Usage in HTML:**
```html
<div class="container">
    <div class="row">
        <div class="column">Column 1</div>
        <div class="column">Column 2</div>
    </div>
</div>
```

### **Bootstrap Way**:
```html
<div class="container">
    <div class="row">
        <div class="col-sm-6">Column 1 for small screens</div>
        <div class="col-lg-6">Column 2 for large screens</div>
    </div>
</div>
```

**More Bootstrap Classes & Explanation**: 
- `.col`: Flexible column that occupies available horizontal space.
- `.col-{breakpoint}-{number}`: Defines column width based on screen size (`breakpoint`). Examples of breakpoints: `sm`, `md`, `lg`, `xl`, `xxl`. `{number}` ranges from 1 to 12.
- `.row-cols-{number}`: Ensures a row has a specific number of columns.

**Exercise**: Create a webpage layout using the Bootstrap grid. Have a header, a 3-column content area for large screens (that stacks on small screens), and a footer.

**Expected Output**

![GRID](https://github.com/techcodedu/bootstrap_way/blob/main/1.png)
---

## **2. Button Styling**

### **Manual CSS**:
```css
.my-btn {
    padding: 10px 15px;
    background-color: blue;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.my-btn:hover {
    background-color: darkblue;
}
```

**Usage in HTML:**
```html
<button class="my-btn">Click Me!</button>
```

### **Bootstrap Way**:
```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
```

**More Bootstrap Classes & Explanation**:
- `.btn-secondary`: Gray button.
- `.btn-info`: Light blue button for informational actions.
- `.btn-warning`: Yellow/orange button for cautionary actions.
- `.btn-light` and `.btn-dark`: Light and dark themed buttons.
- `.btn-link`: Makes the button appear as a link.

**Exercise**: Design a user registration form. Use different button styles for "Submit", "Clear Form", and "Help".

**Expected Output**

![Button](https://github.com/techcodedu/bootstrap_way/blob/main/2.png)
---

## **3. Navigation Bar (Navbar)**

### **Manual CSS**:
```css
.navbar {
    display: flex;
    background-color: #333;
    overflow: hidden;
}

.navbar a {
    float: left;
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}

.navbar a:hover {
    background-color: #ddd;
    color: black;
}
```

**Usage in HTML**:
```html
<div class="navbar">
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</div>
```

### **Bootstrap Way**:
```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Logo</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
            <li class="nav-item active">
                <a class="nav-link" href="#">Home</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#">About</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#">Contact</a>
            </li>
        </ul>
    </div>
</nav>
```

**More Bootstrap Classes & Explanation**:
- `.navbar-dark`: For dark-themed navbars.
- `.bg-primary`, `.bg-success`, etc.: Background color classes matching the button color schemes.
- `.navbar-fixed-top`: Fixes the navbar at the top of the page.
- `.navbar-collapse`: Contains the navigation links for mobile views.

**Exercise**: Design a navbar with the following sections: Home, Services (with a dropdown for Service 1, Service 2, and Service 3), Blog, and Contact. Style the navbar with a dark theme.

**Expected Output**

![navbar](https://github.com/techcodedu/bootstrap_way/blob/main/3.png)
---

## **4. Typography**

### **Manual CSS**:

```css
.heading {
    font-size: 24px;
    font-weight: bold;
}

.paragraph {
    font-size: 16px;
    line-height: 1.5;
    margin-bottom: 20px;
}
```

**Usage in HTML**:
```html
<h1 class="heading">This is a heading</h1>
<p class="paragraph">This is a sample paragraph.</p>
```

### **Bootstrap Way**:

```html
<h1 class="display-1">Display 1</h1>
<p class="lead">This is a leading paragraph.</p>
```

**More Bootstrap Classes & Explanation**:

- `.display-1` to `.display-4`: Large headings with decreased weights for massive headline styles.
- `.lead`: Makes a paragraph stand out.
- `.text-muted`: A muted (lighter) text color.
- `.font-weight-bold`, `.font-weight-light`, etc.: Adjust the weight (boldness) of the text.
- `.text-primary`, `.text-success`, etc.: Change the text color based on Bootstrap's color scheme.

**Exercise**: Craft a landing page for a product. Use large typography to highlight the product name and a leading paragraph to describe its main feature.

**Expected Output**

![Text](https://github.com/techcodedu/bootstrap_way/blob/main/4.png)
---

## **5. Cards**

### **Manual CSS**:

```css
.card {
    border: 1px solid #ddd;
    padding: 20px;
    border-radius: 5px;
    margin-bottom: 20px;
}
```

**Usage in HTML**:

```html
<div class="card">
    <h2>Title</h2>
    <p>Card content here.</p>
</div>
```

### **Bootstrap Way**:

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Card content here.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

**More Bootstrap Classes & Explanation**:

- `.card-img-top`: Designates an image as the top part of a card.
- `.card-header` & `.card-footer`: For upper and lower sections of a card.
- `.card-group`, `.card-deck`: Create a group or deck of cards for equal width and height cards.

**Exercise**: Design a user profile card with a profile picture at the top, followed by a name, short bio, and buttons for "Follow" and "Message".

**Expected Output**

![card](https://github.com/techcodedu/bootstrap_way/blob/main/5.png)
---

## **6. Carousels**

For brevity, let's consider just the Bootstrap approach for the carousel since it's complex to create manually.

### **Bootstrap Way**:

```html
<div id="carouselExample" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <!-- More items... -->
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
```

**More Bootstrap Classes & Explanation**:

- `.carousel`: Specifies the carousel component.
- `.carousel-inner`: Wraps the carousel items.
- `.carousel-item`: Each individual content piece in the carousel.
- `.carousel-control-prev` & `.carousel-control-next`: Navigation for the carousel.

**Exercise**: Create a carousel showcasing the top three features of a new product. Each slide should have an image and a brief description.

**Expected Output**

![carousel](https://github.com/techcodedu/bootstrap_way/blob/main/6.png)
---

## **7. Badges**

### **Manual CSS**:

```css
.badge {
    padding: 4px 8px;
    background-color: blue;
    color: white;
    border-radius: 4px;
    font-size: 12px;
}
```

**Usage in HTML**:
```html
<h1>Heading <span class="badge">New</span></h1>
```

### **Bootstrap Way**:

```html
<h1>Heading <span class="badge bg-primary">New</span></h1>
```

**More Bootstrap Classes & Explanation**:

- `.badge`: Base styling for badges.
- `.bg-primary`, `.bg-success`, `.bg-warning`, etc.: Badge background colors.
- `.badge-pill`: Makes the badge rounded.

**Exercise**: Design a blog homepage. Next to each blog post title, display a badge indicating if the post is "New", "Trending", or "Featured".

**Expected Output**

![badge](https://github.com/techcodedu/bootstrap_way/blob/main/7.png)
---

## **8. Lists**

### **Manual CSS**:

```css
.list-group {
    padding-left: 0;
    margin-bottom: 20px;
}

.list-item {
    list-style: none;
    padding: 10px 15px;
    border: 1px solid #ddd;
}
```

**Usage in HTML**:
```html
<ul class="list-group">
    <li class="list-item">Item 1</li>
    <li class="list-item">Item 2</li>
</ul>
```

### **Bootstrap Way**:

```html
<ul class="list-group">
    <li class="list-group-item">Item 1</li>
    <li class="list-group-item">Item 2</li>
</ul>
```

**More Bootstrap Classes & Explanation**:

- `.list-group-item`: Base class for each item in the list.
- `.list-group-item-primary`, `.list-group-item-success`, etc.: Add different background colors to the list items.

**Exercise**: Design a sidebar with a list of categories for an online shop. Highlight one of the categories as "active" or "selected".

**Expected Output**

![list](https://github.com/techcodedu/bootstrap_way/blob/main/8.png)
---

## **9. Tables**

### **Manual CSS**:

```css
.table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 20px;
}

.table th, .table td {
    border: 1px solid #ddd;
    padding: 8px 12px;
}
```

**Usage in HTML**:
```html
<table class="table">
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

### **Bootstrap Way**:

```html
<table class="table">
    <thead>
        <tr>
            <th scope="col">Header 1</th>
            <th scope="col">Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
    </tbody>
</table>
```

**More Bootstrap Classes & Explanation**:

- `.table-dark`, `.table-striped`, `.table-bordered`, etc.: Modifiers for the table appearance.
- `.table-responsive`: Makes the table scrollable horizontally on small devices.

**Exercise**: Create a table showcasing product details, including name, category, price, and stock status.

**Expected Output**

![table](https://github.com/techcodedu/bootstrap_way/blob/main/9.png)
---

## **10. Forms**

### **Manual CSS**:

```css
.form-control {
    padding: 10px;
    width: 100%;
    border: 1px solid #ddd;
    margin-bottom: 10px;
}
```

**Usage in HTML**:
```html
<form>
    <input type="text" class="form-control" placeholder="Name">
    <input type="email" class="form-control" placeholder="Email">
    <button type="submit">Submit</button>
</form>
```

### **Bootstrap Way**:

```html
<form>
    <div class="mb-3">
        <label for="name" class="form-label">Name</label>
        <input type="text" class="form-control" id="name" placeholder="Name">
    </div>
    <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input type="email" class="form-control" id="email" placeholder="Email">
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

**More Bootstrap Classes & Explanation**:

- `.form-check`, `.form-switch`: For checkboxes and switch controls.
- `.form-select`: For dropdown selects.
- `.form-range`: For range inputs.

**Exercise**: Design a user registration form that includes fields for first name, last name, email, password, and a dropdown to select a user type (Admin, User, Guest). Include a "Register" button.

**Expected Output**

![form](https://github.com/techcodedu/bootstrap_way/blob/main/10.png)

---


