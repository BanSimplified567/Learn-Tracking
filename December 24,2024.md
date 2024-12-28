
## 12/24/2024

- **Topics Covered**

- Using the block with 100% width size

- **Code Challenges**:

## HTML
  ```html
  <header class="header">
         <div class="header-container">
            <div class="header-section-one">
               <h1 class="header-so-title">GET UP TO LIMITED TIME <a href="">SHOP NOW</a></h1>
               <div id="header-so-timer">
                  <h1 id="countdown"></h1>
                  <span id="message"></span>
               </div>
            </div>
            <nav class="navbar-container">
               <ul class="navbar-unorder-list">
                  <li class="navbar-list">
                     <a href="" class="navbar-link">HOME</a>
                     <a href="" class="navbar-link">SHOP</a>
                     <a href="" class="navbar-link">ABOUT</a>
                     <a href="" class="navbar-link">NEWS</a>
                     <a href="" class="navbar-link">CONTACT</a>
                  </li>
                  <a href="" class="navbar-home-link">BANBAN</a>
                  <span class="navbar-list-icons">
                     <i class="fa-solid fa-magnifying-glass"></i>
                     <i class="fa-regular fa-user"></i>
                     <i class="fa-solid fa-cart-shopping"></i>
                  </span>
               </ul>
            </nav>
         </div>
      </header>
  ```


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
