<template>
  <header class="container">
    <nav class="navbar">
      <img :src="require('@/assets/images/logo.svg')" alt />

      <ul class="nav">
        <li class="nav-item">
          <a href="#" class="nav-link">Features</a>
        </li>
        <li class="nav-item">
          <a href="#" class="nav-link">Pricing</a>
        </li>
        <li class="nav-item">
          <a href="#" class="nav-link">Resources</a>
        </li>
      </ul>
    </nav>

    <ul class="navbar-btn">
      <li class="nav-item">
        <a href="#" class="nav-link">Login</a>
      </li>
      <li class="nav-item">
        <a href="#" class="btn btn-primary">Sign Up</a>
      </li>
    </ul>

    <!-- <ion-icon name="menu-outline" @click="toggleNav"></ion-icon> -->

    <i class="fas fa-bars fa-2x toggler" @click="toggleNav"></i>
    <div class="mobile-nav rounded" v-if="mobileNav">
      <ul>
        <li class="nav-item">
          <a href="#" class="nav-link">Features</a>
        </li>
        <li class="nav-item">
          <a href="#" class="nav-link">Pricing</a>
        </li>
        <li class="nav-item">
          <a href="#" class="nav-link">Resources</a>
        </li>
        <!-- <hr /> -->
        <li class="nav-item">
          <a href="#" class="nav-link">Login</a>
        </li>
        <li class="nav-item">
          <a href="#" class="btn btn-primary">Sign Up</a>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  data: () => ({
    mobileNav: false,
  }),
  methods: {
    toggleNav() {
      this.mobileNav = !this.mobileNav;
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 2rem;
}

.navbar {
  display: flex;
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 0 2rem;
}

.navbar-btn {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

a {
  font-weight: 700;
}

.nav-item .nav-link {
  padding: 0 1.5rem;
}

.nav-link:hover {
  color: var(--bg-dark-violet);
}

.toggler {
  display: none;
}

.mobile-nav {
  display: none;
}

@media (max-width: 768px) {
  header {
    position: relative;
  }

  ul.navbar-btn,
  ul.nav {
    display: none;
  }

  .toggler {
    display: block;
  }

  .mobile-nav {
    background: var(--dark-violet);
    position: absolute;
    display: block;
    width: 100%;
    top: 80%;
    left: 0;
    height: 300px;
    z-index: 3;
    text-align: center;
    padding: 0.5rem 2rem;
    margin: 1rem 0;
  }

  .mobile-nav .nav-item {
    padding: 0.7rem 0;
  }

  .mobile-nav .nav-item:nth-child(3) {
    border-bottom: 1px solid var(--bg-gray);
  }

  .mobile-nav .nav-item a.btn {
    display: block;
  }
}
</style>