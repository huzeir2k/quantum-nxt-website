<script setup>
    import HeaderComponent from './HeaderComponent.vue';
</script>
<template>
    <div class="container">
      <div class="background"></div>
      <HeaderComponent />
      <main class="main-content">
        <h1 class="title">Game Hosting</h1>
        <p class="description">
          In a world where game hosting is essential, QuantumNXT provides top-tier solutions.
        </p>
      </main>
    </div>
</template>

<style scoped>
  .container {
   
    width: 100vw;
    height: 100vh;
    background: #171822;
    display: flex;
    flex-direction: column;
  }

  .background {
    background: #171822;
  }

  .logo {
    font-family: ABeeZee, sans-serif;
    font-size: 48px;
    color: #757575;
  }

  .nav-menu {
    display: flex;
    gap: 30px;
  }

  .nav-item {
    font-family: ABeeZee, sans-serif;
    font-size: 24px;
    color: #171822;
    text-align: center;
    cursor: pointer;
  }

  .auth-button {
    display: flex;
    align-items: center;
  }

  .button-wrapper {
    width: 140px;
    height: 47px;
    background: #38458e;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .login-register {
    font-family: ABeeZee, sans-serif;
    font-size: 16px;
    color: white;
  }

  .main-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
  }

  .title {
    font-family: ABeeZee, sans-serif;
    font-size: 64px;
    color: white;
  }

  .description {
    margin-top: 20px;
    font-family: ABeeZee, sans-serif;
    font-size: 18px;
    color: #9bd3e6;
    max-width: 453px;
  }
</style>
