# Base Styles

Base Styles is CSS toolkit that's designed for:
1. Composing clean, consistent user interfaces 
2. Providing a lightweight way to keep CSS organized.


<br/>


## How It Works


### 1. Add Base Styles to your project

```html
<!-- This file contains the existing classes -->
<link href="https://cdn.base-styles.com/base-styles/0.0.1.css" rel="stylesheet">
<!-- This file contains your configuration -->
<link href="/base-styles-custom.css" rel="stylesheet">
```


### 2. Set your defaults

```css title="base-styles-custom.css"
:root {
  --ui-font-family-headers: 'Inter', sans-serif;
  --ui-font-family: 'Inter', sans-serif;
  --ui-color-primary: #0070f3;
  --ui-shared-border-radius: 6px;
  --ui-shared-border-width: 2px;
}
```


### 3. Use the classes to compose your UI


<div class="ui-box mb-2">

#### For example, to make a button
  
  ```html
  <button class="ui-button"> My Button </button>
  ```

  <button class="ui-button --primary">
    My Button
  </button>

</div>


See the [examples](./examples.md) for more.

### 4. (Optional) Add your own variants

If we don't have a variant you need, just add your own. See [customization](./customization.md) for more.

```css title="base-styles-custom.css"
.ui-button {
  & .--embossed {
    box-shadow: 0 0 0 2px var(--ui-color-primary);
  }
}
```
