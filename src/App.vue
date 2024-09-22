<template>
  <div class="hero-box">
    <div class="direitos"><p>© 2024 OminiString. Todos os direitos reservados. Design by OminiString.</p></div>
    <AppNavbar/>
    <div class="container">
      <AppHero/>
      <AppSphere/>
      <AppSphereMobile/>
      
    </div>
  </div>
</template>

<script>
import AppNavbar from './components/AppNavbar.vue';
import AppHero from './components/AppHero.vue';
import AppSphere from './components/AppSphere.vue'; 
import AppSphereMobile from './components/AppSphereMobile.vue'; 

export default {
  name: 'App',
  components: {
    AppNavbar,
    AppHero,
    AppSphere,
    AppSphereMobile
  }
}
</script>

<style>
      @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

      * {
        font-family: "Poppins", sans-serif;
        padding: 0;
        margin: 0;
      }

      a {
        text-decoration: none;
      }

  

      body {
        background: #F5F5F5;
      }

      .hero-box {
        display: flex;
        flex-direction: column;
        width: 100vw;
        height: 100vh;
        align-items: center;
        justify-content: center;
      }

      .container {
        position: relative;
        width: 1140px;
        height: 88vh;
        display: flex;
        align-items: center;
        justify-content: space-between;
      }

      .btn {
      text-align: center;
      max-width: 100px;
      padding: 10px 20px; 
      font-size: 1rem;
      color: #fff !important; 
      background-color: #6A0DAD; 
      border: none; 
      border-radius: 30px; 
      cursor: pointer; 
      transition: background-color 0.3s ease; 
    }

    .btn:hover {
      background-color: #9B30FF; 
    }

    .direitos {
      font-size: 12px;
      position: absolute;
      right: -100px;
      transform: rotate(90deg);
    }

    @media (max-width: 750px) {

      .direitos {
        display: none;
      }
      .container {
        position: relative;
        flex-direction: column;
        align-items: center;
        justify-content: center;
      }
    }

      
</style>
