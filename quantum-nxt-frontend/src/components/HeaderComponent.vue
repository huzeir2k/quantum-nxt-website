<script setup>
import { ref } from 'vue';

const isMobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>

<template>
  <div class="container">
    <header class="site-header">
      <div class="logo">QuantumNXT</div>

      <!-- Desktop Navigation -->
      <nav class="nav-menu">
        <ul>
          <li class="nav-item"><a href="#">Home</a></li>
          <li class="nav-item"><a href="#">Services</a></li>
          <li class="nav-item"><a href="#">Hosting</a></li>
          <li class="nav-item"><a href="#">Community</a></li>
          <li class="nav-item"><a href="#">Contact</a></li>
        </ul>
      </nav>

      <!-- Authentication Button -->
      <div class="auth-button">
        <button class="login-register">Login / Register</button>
      </div>

      <!-- Mobile Menu Button -->
      <button @click="toggleMobileMenu" class="mobile-menu-button">
        ☰
      </button>
    </header>

    <!-- Mobile Navigation -->
    <nav v-if="isMobileMenuOpen" class="mobile-menu">
      <ul>
        <li class="nav-item"><a href="#">Home</a></li>
        <li class="nav-item"><a href="#">Services</a></li>
        <li class="nav-item"><a href="#">Hosting</a></li>
        <li class="nav-item"><a href="#">Community</a></li>
        <li class="nav-item"><a href="#">Contact</a></li>
      </ul>
    </nav>
  </div>
</template>

<style scoped>
/* Header */
.site-header {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 80px;
  background: #9bd3e6;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 30px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

/* Logo */
.logo {
  font-family: ABeeZee, sans-serif;
  font-size: 32px;
  color: #757575;
}

/* Navigation */
.nav-menu ul {
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0;
  gap: 20px;
}

.nav-item a {
  position: relative;
  text-decoration: none; /* Remove default underline */
}

.nav-item a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -2px; /* Adjust underline position */
  width: 0%;
  height: 2px; /* Underline thickness */
  background: #171822; /* Underline color */
  transition: width 0.3s ease-in-out;
  font-family: ABeeZee, sans-serif;
}

.nav-item a:hover::after {
  width: 100%; /* Expand underline on hover */
}

/* Authentication Button */
.auth-button {
  display: flex;
  align-items: center;
}

.login-register {
  font-family: ABeeZee, sans-serif;
  font-size: 16px;
  color: white;
  background: #38458e;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

.login-register:hover {
  background: #2c376d;
}

/* Mobile Menu Button */
.mobile-menu-button {
  display: none;
  font-size: 24px;
  background: none;
  border: none;
  cursor: pointer;
  color: #38458e;
  z-index: 1100;
}

/* Mobile Menu */
.mobile-menu {
  position: absolute;
  top: 80px;
  right: 10px;
  background: #9bd3e6;
  padding: 10px;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

.mobile-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.mobile-menu .nav-item a {
  display: block;
  padding: 10px;
  font-size: 18px;
  text-align: center;
}

/* Responsive */
@media (max-width: 768px) {
  .nav-menu {
    display: none;
  }

  .mobile-menu-button {
    display: block;
  }
}
</style>
