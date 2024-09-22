<template>
  <header>
    <nav :class="{'nav active': isMenuActive, 'nav': !isMenuActive}">
      <img src="https://i.imgur.com/WSq33AA.png" alt="" class="logo">
      <button class="hamburger" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </button>
      <ul class="nav-list">
        <li><a href="" class="btn">Home</a></li>
        <li><a href="" class="">Sobre nós</a></li>
        <li><a href="" class="">Serviços</a></li>
        <li><a href="" class="">Contato</a></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'AppNavbar',
  data() {
    return {
      isMenuActive: false, // Estado para controlar se o menu está ativo
    };
  },
  methods: {
    toggleMenu() {
      // Alterna entre abrir e fechar o menu
      this.isMenuActive = !this.isMenuActive;
    },
  },
};
</script>

<style scoped>
header {
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  border-bottom: 0.001rem solid #00000020;
}

.nav {
  width: 1140px;
  height: 70px;
  margin-inline: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  max-width: 190px;
}

.nav-list {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-list a {
  color: #6a0dad;
  transition: 400ms;
  font-size: 14px;
}

.nav-list a:hover {
  color: #9b30ff;
}

.hamburger {
  display: none;
  border: none;
  background: none;
  cursor: pointer;
  position: relative;
  z-index: 1001;
  flex-direction: column;
  justify-content: space-between;
  gap: 5px;
  height: 30px;
}

.hamburger span {
  width: 30px;
  height: 4px;
  border-radius: 30px;
  background-color: #9b30ff;
  transition: all 0.3s;
}

@media (max-width: 750px) {

  .logo {
    max-width: 100px;
  }

  header {
    width: 100%;
    position: fixed;
    top: 0;
    z-index: 1000;
    background: #f5f5f52e;
    backdrop-filter: blur(7.3px);
    -webkit-backdrop-filter: blur(7.3px);
  }

  .nav {
    width: 85vw;
  }
  .hamburger {
    display: flex;
  }

  .nav-list {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: #f5f5f5;
    clip-path: circle(100px at 90% -15%);
    transition: 1s ease-out;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    gap: 0;
    pointer-events: none;
  }

  .nav-list a {
    font-size: 24px;
    opacity: 0;
  }

  .nav-list li:nth-child(1) a {
    transition: 0.5s 0.2s;
  }

  .nav-list li:nth-child(2) a {
    transition: 0.5s 0.4s;
  }

  .nav-list li:nth-child(3) a {
    transition: 0.5s 0.6s;
  }

  .nav.active .nav-list {
    clip-path: circle(1500px at 90% -15%);
    pointer-events: all;
  }

  .nav.active .nav-list a {
    opacity: 1;
  }

  .nav.active .hamburger span:nth-child(1) {
    transform: rotate(45deg);
    position: absolute;
  }

  .nav.active .hamburger span:nth-child(2) {
    opacity: 0;
  }

  .nav.active .hamburger span:nth-child(3) {
    transform: rotate(-45deg);
    position: absolute;
  }
}
</style>
