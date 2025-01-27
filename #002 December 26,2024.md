
<!-- ##DECEMBER 26, 2024 -->

## 12/24/2024

- **Topics Covered**

- Making a Carousel Sliding images.

- **Code Challenges**:

## HTML

```HTML
            <div class="watchlist-container">
  <section class="watch-section">
    <button id="prev"><i class="fa-solid fa-angles-left"></i></button>
    <div class="watch-slider">
      <article class="watch-article">
        <img src="./WATCHES/product-14.png" alt="" />
        <span class="watch-span">
          <h1>CHRONOTRIGGER</h1>
          <p>$649.99</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-13.png" alt="" />
        <span class="watch-span">
          <h1>PRESTIGEHORIZONS</h1>
          <p>$719.49</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-11.png" alt="" />
        <span class="watch-span">
          <h1>DYNACHRONO</h1>
          <p>$659.89</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-10.png" alt="" />
        <span class="watch-span">
          <h1>DYNACHRONO</h1>
          <p>$599.75</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-09.png" alt="" />
        <span class="watch-span">
          <h1>SMARTSYNC</h1>
          <p>$739.20</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-08.png" alt="" />
        <span class="watch-span">
          <h1>DIGITALEDGE</h1>
          <p>$689.55</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-07.png" alt="" />
        <span class="watch-span">
          <h1>APEXGUARD</h1>
          <p>$579.90</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
      <article class="watch-article">
        <img src="./WATCHES/product-04.png" alt="" />
        <span class="watch-span">
          <h1>AEROSPORT</h1>
          <p>$629.30</p>
        </span>
        <button>VIEW PRODUCT</button>
      </article>
    </div>
    <button id="next"><i class="fa-solid fa-angles-right"></i></button>
  </section>
</div>

```

## CSS

  ```CSS
  .watchlist-container {
    width: 100%;
    overflow: hidden;
    /* Ensures content stays within the screen */}

    .watch-section {
    display: flex;
    position: relative;
    align-items: center;
    }
    .watch-slider {
    display: flex;
    gap: 1rem;
    transition: transform 0.5s ease-in-out;
    will-change: transform;
    width: max-content;
    /* Allows the slider to grow with its content */}
    .watch-article {
    width: calc(25% - 1rem);
    /* Each article takes up 25% of the container minus the gap */
    flex: 0 0 auto;
    text-align: center;
    }
    .watch-article img {
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 8px;
    margin-bottom: 1rem;
    }
    /* Responsive Design for smaller screens */
  @media screen and (max-width: 1024px) {
    .watch-article {
        width: calc(33.33% - 1rem);
        /* Show 3 items at a time on smaller screens */
    }
    }
    @media screen and (max-width: 768px) {
    .watch-article {
        width: calc(50% - 1rem);
        /* Show 2 items at a time on even smaller screens */
    }
    } @media screen and (max-width: 480px) {
    .watch-article {
        width: 100%;
        /* Show 1 item at a time on mobile */
    }
    }
    /* Navigation Buttons */
    #prev, #next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    cursor: pointer;
    z-index: 10;
    }
    #prev {
    left: 0.5rem;
    }
    #next {
    right: 0.5rem;
    }
    #prev:disabled, #next:disabled {
    opacity: 0.5;
    cursor: not-allowed;
    }
    .watch-span h1 {
    font-family: var(--wp--preset--font-family--roboto-slab);
    font-size: var(--wp--preset--font-size--medium);
    font-weight: 300;
    color: var(--wp--preset--color--bg-dark);
    }
    .watch-span p {
    font-family: var(--wp--preset--font-family--cinzel);
    font-size: var(--wp--preset--font-size--medium);
    font-weight: 300;
    color: var(--wp--preset--color--bg-dark);
    margin-bottom: 1rem;
    }
    .watch-article button {
    font-family: var(--wp--preset--font-family--roboto);
    font-size: var(--wp--preset--font-size--extra-small);
    font-weight: 300;
    letter-spacing: .2rem;
    padding: 1rem 2rem;
    margin-bottom: 2rem;
    background-color: var(--wp--preset--color--bg-dark);
    border: solid 1px var(--wp--preset--color--bg-dark);
    color: var(--wp--preset--color--white);
    }
  ```

## JAVASCRIPT

```js

const slider = document.querySelector('.watch-slider');
const articles = document.querySelectorAll('.watch-article');
const prevBtn = document.getElementById('prev');
const nextBtn = document.getElementById('next');

let currentIndex = 0;

const getVisibleItemsCount = () => {
   // Calculate the number of visible items based on the screen width
   const width = window.innerWidth;

   if (width <= 480) {
      return 1; // Show 1 item on small screens
   } else if (width <= 768) {
      return 2; // Show 2 items on medium screens
   } else if (width <= 1024) {
      return 3; // Show 3 items on large screens
   } else {
      return 4; // Show 4 items on larger screens
   }
};

const slideTo = (index) => {
   // Get the number of visible items
   const visibleItems = getVisibleItemsCount();

   // Loop the slider if it reaches the end or the beginning
   if (index < 0) {
      currentIndex = articles.length - visibleItems;
   } else if (index >= articles.length - visibleItems + 1) {
      currentIndex = 0;
   } else {
      currentIndex = index;
   }

   // Get the width of a single article
   const articleWidth = articles[0].offsetWidth;

   // Move the slider to the correct position
   slider.style.transform = `translateX(-${currentIndex * articleWidth}px)`;
};

prevBtn.addEventListener('click', () => {
   slideTo(currentIndex - 1); // Move one image to the left
});

nextBtn.addEventListener('click', () => {
   slideTo(currentIndex + 1); // Move one image to the right
});

// Optional: Update the slide on window resize to adjust for different screen sizes
window.addEventListener('resize', () => {
   // Recalculate the current position when the window is resized
   slideTo(currentIndex);
});
```

- **Reflections**: I added some gap between the images so they would fit into the container. If I remove the gap, there is a small space at the end of the images, so I fixed it by adding a gap between them.
