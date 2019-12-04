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
          <a href="#design">美術設計</a>
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
    height: 56px;
    position: fixed;
    z-index: 10;
    top: 0;
    background-color: #c2b6b6;
    background-image: linear-gradient(315deg, #c2b6b6 0%, #576574 74%);
    box-shadow: 0 1px 5px rgba(32, 32, 32, 0.7);
    .logo {
      height: 100%;
      width: 12%;
      display: flex;
      justify-content: center;
      align-items: center;
      a {
        text-decoration: none;
        h1 {
          margin: 0 auto;
          text-align: center;
          color: #ddd;
          text-shadow: 2px 2px 5px #000000;
        }
      }
    }
    .menu {
      height: 100%;
      width: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      position: absolute;
      top: 0;
      right: 0;
      ul {
        list-style-type: none;
        overflow: hidden;
        li {
          float: left;
          width: 100px;
          padding: 10px;
          a {
            font-size: 20px;
            text-decoration: none;
            color: #ffffff;
            text-shadow: 2px 2px 5px #000000;
          }
        }
      }
    }
  }
</style>
