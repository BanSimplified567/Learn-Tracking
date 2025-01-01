<!-- ##January 01, 2025 -->

## 01/01/2025

- **Topics Covered**:
  - Learned about background image with a blurry black overlay.

- **Code Challenges**:

  #HTML

  ```html
  <div class="newsletter-container">
    <section class="newsletter-article-section">
      <p>STAY UPDATED</p>
      <h1>Newsletter.</h1>
      <p>By subscribing to our newsletter, you gain exclusive access to the latest updates on new arrivals, limited-edition releases, and special promotions.</p>
    </section>
    <section class="newsletter-form-section">
      <form class="newsletter-form">
        <div class="newsletter-input-group">
          <input type="text" id="name" required>
          <label for="name" class="newsletter-label-name">
            NAME <span>(required)</span>
          </label>
        </div>
        <div class="newsletter-input-group">
          <input type="text" id="email" required>
          <label for="email" class="newsletter-label-name">
            EMAIL <span>(required)</span>
          </label>
        </div>
        <button type="submit" class="newsletter-submit-btn">Subscribe</button>
      </form>
    </section>
  </div>
  ```

  #CSS

  ```CSS
  .newsletter-container {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 4rem;
    width: 100%;
    height: 60vh;
    padding: 5rem;
    overflow: hidden;
    /*Ensure content stays within the container*/}
    /*Blurry background on the image */
    .newsletter-container::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('./WATCHES/banner-07-768x439.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    /* Adds blur to the background image */
    z-index: -2;
    /* Places the background behind everything*/}
    /*Overlay to darken the blurred background */
    .newsletter-container::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.6);
    /* Semi-transparent overlay */
    z-index: -1;
    /* Places the overlay above the blurred image*/
    }
    .newsletter-article-section{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 1rem;
    }
    .newsletter-article-section h1{
    color:#fff;
    font-size: 7rem;
    line-height: 1.1px;
    font-weight: 300;
    }
    .newsletter-article-section p{
    color: #fff;
    font-size: .8rem;
    font-family: "Roboto", sans-serif;
    line-height: 1.1;
    font-weight: 300;
    }
  ```

- **Reflections**:
  - I was confused at first about whether to place the image directly in the container, but I remembered that I could use `:before` and `:after`. I tried it, and it turned out to work well.
