<template>
  <div id="topNavbar">
    <div class="logo">
      <router-link to="/">
        <h1>致：不義時光</h1>
      </router-link>
    </div>
    <div class="menu">
      <ul>
        <li>
          <a href="#story">遊戲故事</a>
        </li>
        <li>
          <a href="#rule">玩法介紹</a>
        </li>
        <li>
          <a href="#item">美術設計</a>
        </li>
        <li>
          <a href="#team">團隊成員</a>
        </li>
        <li>
          <a href="#contact">聯絡我們</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'topNavbar'
}
</script>

<style lang="scss">
  #topNavbar {
    width: 100vw;
    height: 60px;
    background-color: grey;
    position: fixed;
    top: 0;
    .logo {

    }
    .menu {
      ul {
        list-style-type: none;
      }
    }
  }
</style>
