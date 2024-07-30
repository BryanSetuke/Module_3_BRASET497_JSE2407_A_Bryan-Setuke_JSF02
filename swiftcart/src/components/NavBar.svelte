<script>
  import { faHome, faBoxOpen, faAddressBook, faShoppingCart, faHeart } from '@fortawesome/free-solid-svg-icons';
  import { FontAwesomeIcon } from '@fortawesome/svelte-fontawesome';
  let menuOpen = false;

  function toggleMenu() {
    menuOpen = !menuOpen;
  }
</script>

<nav>
  <div class="logo">
    <img src="./public/logo-icon.jpg" alt="Logo" />
    <span>SwiftCart</span>
  </div>
  <div class="menu-toggle" on:click={toggleMenu}>
    <svg viewBox="0 0 100 80" width="40" height="40">
      <rect width="100" height="20"></rect>
      <rect y="30" width="100" height="20"></rect>
      <rect y="60" width="100" height="20"></rect>
    </svg>
  </div>
  <div class="search-container">
    <input type="text" placeholder="Search product..." />
  </div>
  <ul class={menuOpen ? 'nav-links open' : 'nav-links'}>
    <li>
      <a href="/">
        <FontAwesomeIcon icon={faHome} /> Home
      </a>
    </li>
    <li>
      <a href="/products">
        <FontAwesomeIcon icon={faBoxOpen} /> Products
      </a>
    </li>
    <li>
      <a href="/contacts">
        <FontAwesomeIcon icon={faAddressBook} /> Contacts
      </a>
    </li>
    <li>
      <a href="/wishlist">
        <FontAwesomeIcon icon={faHeart} /> Wishlist
      </a>
    </li>
    <li>
      <a href="/cart">
        <FontAwesomeIcon icon={faShoppingCart} /> Cart
      </a>
    </li>
  </ul>
</nav>

<style>
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: #a0e5e2f7;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .logo {
    display: flex;
    align-items: center;
  }

  .logo img {
    height: 40px;
    margin-right: 0.5rem;
  }

  .menu-toggle {
    display: none;
    cursor: pointer;
  }

  .nav-links {
    list-style: none;
    display: flex;
    align-items: center;
  }

  .nav-links li {
    margin: 0 0.5rem;
  }

  .nav-links li a {
    text-decoration: none;
    color: #333;
    font-weight: bold;
  }

  .nav-links li a:hover {
    color: #007bff;
  }

  .search-container {
    flex: 1;
    display: flex;
    justify-content: center;
  }

  .search-container input {
    width: 50%;
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
  }

  @media (max-width: 768px) {
    .nav-links {
      display: none;
      flex-direction: column;
      align-items: flex-start;
      position: absolute;
      top: 64px;
      left: 0;
      width: 100%;
      background-color: #a0e5e2f7;
      padding: 1rem;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

    .nav-links.open {
      display: flex;
    }

    .menu-toggle {
      display: block;
    }
  }
</style>
