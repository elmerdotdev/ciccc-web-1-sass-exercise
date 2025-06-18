# Web Dev 1 - SCSS Exercise

**Goal:** To practice and understand the basics of SCSS including nesting, variables, mixins, and partials.

## Instructions ✅

**Set Up Your Project**

Create a new directory for your project.
Inside this directory, create the following structure:

```
project/
├── index.html
├── scss/
│   ├── main.scss
│   ├── _variables.scss
│   ├── _mixins.scss
│   ├── _header.scss
│   ├── _footer.scss
└── css/
    └── main.css
```

**HTML Structure**

In `index.html`, create a basic HTML structure with a header, a main content section, and a footer:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SCSS Exercise</title>
    <link rel="stylesheet" href="css/main.css">
</head>
<body>
    <header>
        <h1>Welcome to SCSS</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section>
            <h2>Main Content</h2>
            <p>This is the main content section.</p>
        </section>
    </main>
    <footer>
        <p>&copy; SCSS Exercise</p>
    </footer>
</body>
</html>
```

**Create Variables**

In `scss/_variables.scss`, define some variables for colors and fonts:

```scss
// _variables.scss
$primary-color: #3498db;
$secondary-color: #2ecc71;
$font-stack: 'Helvetica Neue', sans-serif;
```

**Create Mixins**

In `scss/_mixins.scss`, create a mixin for a flexbox container:

```scss
// _mixins.scss
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

**Style the Header**

In `scss/_header.scss`, style the header using nesting and the variables:

```scss
// _header.scss
@use 'variables';
@use 'mixins';

header {
  background-color: variables.$primary-color;
  color: white;
  padding: 20px;

  h1 {
    margin: 0;
  }

  nav {
    ul {
      @include mixins.flex-center;
      list-style: none;
      padding: 0;

      li {
        margin: 0 10px;

        a {
          color: white;
          text-decoration: none;
        }
      }
    }
  }
}
```

**Style the Footer**

In `scss/_footer.scss`, style the footer similarly:

```scss
// _footer.scss
@use 'variables';
@use 'mixins';

footer {
  background-color: variables.$secondary-color;
  color: white;
  padding: 10px;
  text-align: center;
}
```

**Main SCSS File**

In `scss/main.scss`, import all the partials:

```scss
// main.scss
@use 'variables';
@use 'mixins';
@use 'header';
@use 'footer';

body {
  font-family: variables.$font-stack;
  margin: 0;
}

main {
  padding: 20px;

  section {
    background-color: #f4f4f4;
    padding: 20px;
    border-radius: 5px;

    h2 {
      color: variables.$primary-color;
    }
  }
}
```

**Compile SCSS to CSS:** Use a SCSS compiler to compile `scss/main.scss` into `css/main.css`. You can use tools like `sass` CLI.

**Open Your HTML File:** Open `index.html` in your browser to see your styled webpage.

## Additional Tasks (If You Have Time)

Add more sections to the main content and style them using SCSS.

Create additional mixins for common styles (e.g., buttons, card layouts).

Experiment with different variables and see how it affects the styles.

Happy coding!
