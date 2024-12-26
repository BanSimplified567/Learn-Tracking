
## 12/24/2024

- Using the block with 100% width size

- **Code Challenges**:

  ```CSS
  // I use the block for perfect width of the header.
  .header {
    display: block;
    position: absolute;
    width: 100%;
    }
  // I use sticky here for the header stay at the top.
  .header-container {
    position: sticky;
    top: 0;
    z-index: 100;
    }
  ```

- **Reflections**: I think this is enough for the sticky top. I was also planning to add an animation so that when the screen is scrolled within an offsetHeight of 50vh, the header will animate.
