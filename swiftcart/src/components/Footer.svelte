<script>
</script>

<footer class="footer">
  <div class="footer-content">
    <div class="footer-section about">
      <h1 class="logo-text">SwiftCart</h1>
      <p>
        SwiftCart is your one-stop shop for all your product needs. We offer a wide range of products at competitive prices.
      </p>
    </div>
    <div class="footer-section contact">
      <h1>Contact Us</h1>
      <p>Email: contact@swiftcart.com</p>
      <p>Phone: +123-456-7890</p>
      <p>Address: 123 Swift Street, Shopville</p>
    </div>
    <div class="footer-section social">
      <h1>Follow Us</h1>
      <div class="social-icons">
        <a href="#"><i class="fa fa-facebook"></i></a>
        <a href="#"><i class="fa fa-twitter"></i></a>
        <a href="#"><i class="fa fa-instagram"></i></a>
        <a href="#"><i class="fa fa-linkedin"></i></a>
      </div>
    </div>
  </div>
</footer>

<style>
  .footer {
    background-color: #333;
    color: #fff;
    padding: 20px 0;
  }

  .footer-content {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    padding: 0 20px;
  }

  .footer-section {
    flex: 1;
    padding: 10px;
  }

  .footer-section h1 {
    margin-bottom: 10px;
  }

  .footer-section p {
    margin: 5px 0;
  }

  .social-icons {
    display: flex;
    gap: 10px;
  }

  .social-icons a {
    color: #fff;
    font-size: 24px;
    transition: color 0.3s ease;
  }

  .social-icons a:hover {
    color: #ffd700;
  }

  @media (max-width: 768px) {
    .footer-content {
      flex-direction: column;
      text-align: center;
    }

    .footer-section {
      margin-bottom: 20px;
    }
  }
</style>



