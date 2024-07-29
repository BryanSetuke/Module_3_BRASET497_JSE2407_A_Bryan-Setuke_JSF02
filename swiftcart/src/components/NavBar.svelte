<script>
  let isOpen = false;

  function toggleNav() {
    isOpen = !isOpen;
  }
</script>

<nav>
  <div class="nav-container">
    <div class="brand">
      <a href="/">SwiftCart</a>
    </div>
    <div class="menu-icon" on:click={toggleNav}>
      &#9776;
    </div>
    <ul class:active={isOpen}>
      <li><a href="/">Home</a></li>
      <li><a href="#products">Products</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</nav>

<style>
  nav {
    width: 100%;
    background-color: #333;
    overflow: hidden;
  }
  .nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 20px;
  }
  .brand a {
    color: #fff;
    text-decoration: none;
    font-size: 24px;
  }
  .menu-icon {
    display: none;
    font-size: 30px;
    color: #fff;
    cursor: pointer;
  }
  ul {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
  }
  ul li {
    margin: 0 15px;
  }
  ul li a {
    color: #fff;
    text-decoration: none;
    font-size: 18px;
  }
  @media (max-width: 768px) {
    .menu-icon {
      display: block;
    }
    ul {
      display: none;
      flex-direction: column;
      width: 100%;
    }
    ul.active {
      display: flex;
    }
    ul li {
      text-align: center;
      margin: 10px 0;
    }
  }
</style>
