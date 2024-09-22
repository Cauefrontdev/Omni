<template>
    <header>
        <nav class="navbar">
          <img src="https://i.imgur.com/WSq33AA.png" alt="" class="logo">
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
    props: {
      msg: String
    }
  }
  </script>
  
  
  <style scoped>
      header {
        display: flex;
        align-items: center;
        justify-content: center;
        border-bottom: 0.001rem solid #00000020;
      }

      .navbar {
        width: 1140px;
        height: 12vh;
        display: flex;
        align-items: center;
        justify-content: space-between;
      }

      .logo {
        max-width: 190px;
      }

      .nav-list {
        display: flex;
        list-style: none;
        gap: 2rem;

        & a {
          color: #6A0DAD;
          transition: 400ms;
          font-size: 14px;
        }

        & a:hover {
          color: #9B30FF;
        }
      }
  </style>
  