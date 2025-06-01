<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>TsekouThePlug – AirPods Offer</title>
  <style>
    /* Reset */
    * {
      box-sizing: border-box;
    }
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f9f9f9;
      color: #222;
      line-height: 1.6;
    }
    header {
      background: black;
      color: white;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    /* Logo */
    .logo {
      display: flex;
      align-items: center;
      font-weight: bold;
      font-size: 1.8rem;
      gap: 0.5rem;
    }
    .logo img {
      height: 40px;
      width: 40px;
    }

    /* Hamburger */
    .hamburger {
      width: 25px;
      height: 20px;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .hamburger div {
      height: 3px;
      background: white;
      border-radius: 2px;
    }
    /* Dropdown menu */
    #menu {
      display: none;
      position: absolute;
      right: 2rem;
      top: 60px;
      background: white;
      border: 1px solid #ddd;
      border-radius: 5px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      width: 220px;
      z-index: 1000;
    }
    #menu.active {
      display: block;
    }
    #menu a {
      display: block;
      padding: 0.75rem 1rem;
      color: black;
      text-decoration: none;
      border-bottom: 1px solid #eee;
    }
    #menu a:hover {
      background: #f0f0f0;
    }

    .container {
      max-width: 900px;
      margin: 2rem auto;
      padding: 0 1rem;
    }

    .product-gallery {
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 1rem;
    }
    .product-gallery img {
      width: 280px;
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      transition: transform 0.3s ease;
      cursor: pointer;
    }
    .product-gallery img:hover {
      transform: scale(1.05);
    }

    .price-section {
      text-align: center;
      margin-bottom: 2rem;
    }
    .old-price {
      font-size: 1.4rem;
      text-decoration: line-through;
      color: #888;
      margin-right: 1rem;
    }
    .new-price {
      font-size: 2rem;
      font-weight: bold;
      color: #e63946;
    }
    .discount {
      background: #e63946;
      color: white;
      font-weight: bold;
      padding: 0.25rem 0.5rem;
      border-radius: 5px;
      margin-left: 1rem;
      font-size: 1rem;
      vertical-align: middle;
    }

    .paypal-button {
      margin-top: 1rem;
      text-align: center;
    }
    .paypal-button a {
      background: #0070ba;
      color: white;
      padding: 0.9rem 2.2rem;
      text-decoration: none;
      border-radius: 6px;
      font-size: 1.3rem;
      display: inline-block;
      transition: background 0.3s ease;
    }
    .paypal-button a:hover {
      background: #004b8b;
    }

    .reviews {
      margin-top: 3rem;
    }
    .reviews h3 {
      text-align: center;
      margin-bottom: 1rem;
      font-size: 1.8rem;
      color: #222;
    }
    .star {
      color: gold;
      font-size: 1.2rem;
    }
    .review {
      background: white;
      padding: 1rem 1.5rem;
      border-radius: 10px;
      margin-bottom: 1rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      text-align: left;
    }
    .review strong {
      display: block;
      margin-bottom: 0.3rem;
      font-weight: 700;
    }

    /* Phone Support */
    .phone-support {
      background: #222;
      color: white;
      text-align: center;
      padding: 1rem 2rem;
      margin: 3rem 0;
      border-radius: 12px;
      font-size: 1.2rem;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }
    .phone-support a {
      color: #e63946;
      font-weight: bold;
      text-decoration: none;
    }
    .phone-support a:hover {
      text-decoration: underline;
    }

    /* Contact Form */
    .contact-section {
      max-width: 700px;
      margin: 3rem auto 5rem;
      background: white;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
    }
    .contact-section h3 {
      text-align: center;
      margin-bottom: 1.5rem;
      font-size: 1.9rem;
    }
    .contact-section form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    .contact-section label {
      font-weight: 600;
    }
    .contact-section input,
    .contact-section textarea {
      padding: 0.7rem 1rem;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-radius: 8px;
      resize: vertical;
    }
    .contact-section button {
      background: #e63946;
      color: white;
      padding: 0.9rem;
      border: none;
      border-radius: 8px;
      font-size: 1.2rem;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .contact-section button:hover {
      background: #a82b35;
    }

    /* FAQ Section */
    .faq {
      max-width: 700px;
      margin: 0 auto 3rem;
      background: white;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
    }
    .faq h3 {
      text-align: center;
      margin-bottom: 1.5rem;
      font-size: 1.9rem;
    }
    .faq-item {
      margin-bottom: 1rem;
    }
    .faq-item strong {
      display: block;
      margin-bottom: 0.3rem;
      font-weight: 600;
    }
    /* Responsive */
    @media (max-width: 700px) {
      .product-gallery {
        flex-direction: column;
        align-items: center;
      }
      .product-gallery img {
        width: 90%;
        max-width: 350px;
      }
      header {
        padding: 1rem;
      }
    }
  </style>
</head>
<body>

<header>
  <div class="logo">
    <img src="https://cdn-icons-png.flaticon.com/512/5977/5977592.png" alt="TsekouThePlug Logo" />
    TsekouThePlug
  </div>
  <div class="hamburger" id="hamburger" aria-label="Toggle menu" role="button" tabindex="0">
    <div></div>
    <div></div>
    <div></div>
  </div>
  <nav id="menu" aria-label="Contact menu">
    <a href="mailto:alextheplug152@gmail.com">Email: alextheplug152@gmail.com</a>
    <a href="tel:+1234567890">Phone: +1 234 567 890</a>
  </nav>
</header>

<main class="container">

  <section class="product-gallery" aria-label="Product images">
    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/MQD83?wid=2000&hei=2000&fmt=jpeg&qlt=90&.v=1660803972364" alt="AirPods front view" />
    <img src="https://cdn.shopify.com/s/files/1/0054/6665/2713/products/Airpods_3_Mockup_03_1024x1024@2x.jpg?v=1640050496" alt="AirPods side view" />
    <img src="https://cdn.shopify.com/s/files/1/0054/6665/2713/products/Airpods_3_Mockup_06_1024x1024@2x.jpg?v=1640050496" alt="AirPods open case" />
  </section>

  <section class="price-section" aria-label="Pricing">
    <span class="old-price" aria-label="Original price">€29.99</span>
    <span class="new-price" aria-label="Discounted price">€19.99</span>
    <span class="discount" aria-label="Discount percentage">-33%</span>
  </section>

  <section class="paypal-button">
    <a href="https://www.paypal.me/YOURUSERNAME/19.99" target="_blank" rel="noopener noreferrer" aria-label="Buy now with PayPal">Buy Now with PayPal</a>
  </section>

  <section class="reviews" aria-label="Customer reviews">
    <h3>⭐️⭐️⭐️⭐️⭐️ Reviews</h3>

    <article class="review">
      <strong>Maria T.</strong>
      <p>"Super fast delivery and amazing sound quality!"</p>
      <p class="star" aria-label="Five stars">★★★★★</p>
    </article>

    <article class="review">
      <strong>Alex G.</strong>
      <p>"Best earbuds for this price. Very happy!"</p>
      <p class="star" aria-label="Five stars">★★★★★</p>
    </article>

    <article class="review">
      <strong>John D.</strong>
      <p>"I thought it was a scam, but it's real and worth it."</p>
      <p class="star" aria-label="Five stars">★★★★★</p>
    </article>
  </section>

  <section class="phone-support" aria-label="Phone support">
    📞 Need help? Call us at <a href="tel:+1234567890">+1 234 567 890</a> or email <a href="mailto:alextheplug152@gmail.com">alextheplug152@gmail.com</a>
  </section>

  <section class="contact-section" aria-label="Contact form">
    <h3>Contact Us</h3>
    <form id="contactForm">
      <label for="name">Name</label>
      <input id="name" name="name" type="text" placeholder="Your full name" required />
      
      <label for="address">Address</label>
      <input id="address" name="address" type="text" placeholder="Shipping address" required />
      
      <label for="email">Email</label>
      <input id="email" name="email" type="email" placeholder="you@example.com" required />

      <label for="message">Message (optional)</label>
      <textarea id="message" name="message" rows="4" placeholder="Any questions or details"></textarea>

      <button type="submit">Send</button>
    </form>
  </section>

  <section class="faq" aria-label="Frequently Asked Questions">
    <h3>Frequently Asked Questions</h3>

    <div class="faq-item">
      <strong>What is the warranty period?</strong>
      <p>All earbuds come with a 1-year limited warranty.</p>
    </div>
    <div class="faq-item">
      <strong>How long is the shipping time?</strong>
      <p>Shipping typically takes 5-7 business days.</p>
    </div>
    <div class="faq-item">
      <strong>Can I return the product?</strong>
      <p>Yes, we offer a 30-day return policy if unopened.</p>
    </div>
  </section>

</main>

<script>
  // Hamburger menu toggle
  const hamburger = document.getElementById('hamburger');
  const menu = document.getElementById('menu');
  hamburger.addEventListener('click', () => {
    menu.classList.toggle('active');
  });
  // Accessibility: toggle on keyboard enter
  hamburger.addEventListener('keydown', (e) => {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      menu.classList.toggle('active');
    }
  });

  // Simple contact form submit (demo only)
  const form = document.getElementById('contactForm');
  form.addEventListener('submit', e => {
    e.preventDefault();
    alert(`Thanks for contacting us, ${form.name.value}! We'll get back to you shortly.`);
    form.reset();
  });
</script>

</body>
</html>

