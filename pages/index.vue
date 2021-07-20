<template>
  <div class="home-page">
    <div class="home-page-content">
      <div class="logobar">
        <img
          height="100%"
          width="100px"
          src="https://via.placeholder.com/150/92c952"
          alt=""
        />
      </div>
      <div class="desktop-homepage-navbar mx-3 my-3">
        <router-link
          to="/"
          class="desktop-homepage-navbar-item"
          active-class="desktop-homepage-navbar-item-active"
          >หน้าหลัก</router-link
        >
        <router-link
          to="/mylend"
          class="desktop-homepage-navbar-item"
          active-class="desktop-homepage-navbar-item-active"
          >หนังสือของฉัน</router-link
        >
      </div>
      <div class="menu-mobile" @click="isShowMenuMobile = !isShowMenuMobile">
        เมนู
      </div>
      <div
        :class="
          `menu-mobile-item-container ${
            isShowMenuMobile
              ? 'menu-mobile-item-container-show'
              : 'menu-mobile-item-container-hide'
          }`
        "
      >
        <router-link
          to="/"
          class="menu-mobile-item"
          active-class="menu-mobile-item-active"
        >
          หน้าหลัก
        </router-link>
        <router-link
          to="/mylend"
          class="menu-mobile-item"
          active-class="menu-mobile-item-active"
        >
          หนังสือของฉัน
        </router-link>
      </div>
      <div class="content">
        <div class="desktop-content-category">
          <label for="">collection</label>
          <ul>
            <li>test</li>
            <li>test</li>
            <li>test</li>
            <li>test</li>
            <li>test</li>
            <li>test</li>
          </ul>
        </div>
        <div class="content-book-shelf">
          <label for="">รายการหนังสือทั้งหมด</label>
          <div class="book-container">
            <div class="book"></div>
            <div class="book"></div>
            <div class="book"></div>
            <div class="book"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShowMenuMobile: false
    };
  }
};
</script>

<style scoped>
@media all and (min-width: 1024px) {
  * {
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
  [class*="mobile"] {
    display: none;
  }
  .home-page {
    min-height: 100vh;
    background-color: cadetblue;
    display: flex;
    justify-content: center;
  }
  .home-page-content {
    display: flex;
    flex-direction: column;
    width: 1024px;
  }
  .logobar {
    height: 60px;
    width: 100%;
  }
  .desktop-homepage-navbar {
    width: 100%;
    display: flex;
    justify-content: flex-start;
  }
  .content {
    flex-grow: 1;
    width: 100%;
    background-color: red;
    display: flex;
  }
  .content .desktop-content-category {
    width: 40%;
    background-color: blue;
    padding: 15px;
  }
  .content .content-book-shelf {
    width: 60%;
    background-color: blueviolet;
    padding: 15px;
    display: flex;
    flex-direction: column;
  }
  .content .content-book-shelf .book-container {
    width: 100%;
    flex-grow: 1;
    background-color: brown;
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
  }
  .content .content-book-shelf .book-container .book {
    width: 75px;
    height: 100px;
    background-color: burlywood;
    margin: 15px 10px;
  }
  .desktop-homepage-navbar-item {
    background-color: white;
    padding: 5px 10px;
    color: black;
  }
  .desktop-homepage-navbar-item-active {
    background-color: #1976d2 !important;
    padding: 5px 10px;
    color: white;
    border-radius: 5px;
  }
}
@media all and (max-width: 1023px) {
  [class*="desktop"] {
    display: none;
  }
  .logobar {
    height: 40px;
    width: 100%;
  }
  .menu-mobile {
    margin-top: 15px;
    background-color: #1976d2;
    color: white;
    padding: 5px;
  }
  .menu-mobile-item-container {
    width: 100%;
    overflow-y: hidden;
    display: flex;
    flex-direction: column;
    transition: max-height 0.2s;
    overflow-y: hidden;
  }
  .menu-mobile-item-container-hide {
    max-height: 0px !important;
  }
  .menu-mobile-item-container-show {
    max-height: 400px !important;
  }
  .menu-mobile-item-container .menu-mobile-item {
    background-color: white;
    padding: 5px;
    color: black;
  }
  .menu-mobile-item-container .menu-mobile-item-active {
    background-color: #1976d2;
    padding: 5px;
    color: white;
  }
}
</style>
