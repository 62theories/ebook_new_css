<template>
  <div class="home-page">
    <div class="home-page-content">
      <div class="logobar">
        <img
          height="100%"
          class="ml-3"
          src="https://www.computing.psu.ac.th/th/wp-content/uploads/2018/03/Logo-PSU-TH-01.png"
          alt=""
        />
      </div>
      <div class="desktop-homepage-navbar mx-3 mt-3 mb-1">
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
      <div class="desktop-seperator mb-3"></div>
      <div class="menu-mobile-top" @click="isShowMenuMobile = !isShowMenuMobile">
        เมนู
      </div>
      <div
        :class="
          `menu-mobile ${
            isShowMenuMobile
              ? 'menu-mobile--show'
              : 'menu-mobile--hide'
          }`
        "
      >
        <router-link
          to="/"
          class="item"
          active-class="item--active"
        >
          หน้าหลัก
        </router-link>
        <router-link
          to="/mylend"
          class="item"
          active-class="item--active"
        >
          หนังสือของฉัน
        </router-link>
      </div>
      <div class="mobile-seperator mb-3"></div>
      <div class="content">
        <div class="desktop-content-category">
          <label for="">collections</label>
          <ul>
            <li>collection <a href="/">(1)</a> </li>
            <li>collection <a href="/">(1)</a></li>
            <li>collection <a href="/">(1)</a></li>
            <li>collection <a href="/">(1)</a></li>
            <li>collection <a href="/">(1)</a></li>
            <li>collection <a href="/">(1)</a></li>
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
    background-color: white;
    display: flex;
    justify-content: center;
  }
  .home-page-content {
    display: flex;
    flex-direction: column;
    width: 1024px;
  }
  .logobar {
    height: 80px;
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
    background-color: white;
    padding: 15px;
  }
  .content .content-book-shelf {
    width: 60%;
    background-color: #fcfcfc;
    padding: 15px;
    display: flex;
    flex-direction: column;
    box-shadow: inset 0 0 1px rgb(0 0 0 / 30%);
  }
  .content .content-book-shelf .book-container {
    width: 100%;
    flex-grow: 1;
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
  .desktop-seperator {
    width: 100%;
    height: 10px;
    border-bottom: 0.5px solid #dcdcdc;
  }
}
@media all and (max-width: 1023px) {
  [class*="desktop"] {
    display: none;
  }
  .home-page {
    min-height: 100vh;
    background-color: white;
    margin-left: 15px;
    margin-right: 15px;
    display: flex;
  }
  .home-page-content {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
  }
  .logobar {
    height: 40px;
    width: 100%;
  }
  .menu-mobile-top {
    margin-top: 15px;
    background-color: #1976d2;
    color: white;
    padding: 5px;
  }
  .menu-mobile {
    width: 100%;
    overflow-y: hidden;
    display: flex;
    flex-direction: column;
    overflow-y: hidden;
    -webkit-transition: max-height 0.8s;
	  -moz-transition: max-height 0.8s;
	  transition: max-height 0.8s;
  }
  .menu-mobile--hide {
    max-height: 0px !important;
  }
  .menu-mobile--show {
    max-height: 200px !important;
  }
  .menu-mobile .item {
    background-color: white;
    padding: 5px;
    color: black;
    margin: 2px;
    border: 0.5px solid #dcdcdc;
    border-radius: 5px;
  }
  .menu-mobile .item--active {
    background-color: #1976d2;
    padding: 5px;
    color: white;
  }
  .mobile-seperator {
    width: 100%;
    height: 10px;
    border-bottom: 0.5px solid #dcdcdc;
  }
  .content {
    flex-grow: 1;
    width: 100%;
    display: flex;
  }
  .content .content-book-shelf {
    width: 100%;
    background-color: #fcfcfc;
    padding: 15px;
    margin: 15px;
    display: flex;
    flex-direction: column;
    box-shadow: inset 0 0 1px rgb(0 0 0 / 30%);
  }
  .content .content-book-shelf .book-container {
    width: 100%;
    flex-grow: 1;
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
  }
  .content .content-book-shelf .book-container .book {
    width: 100%;
    height: 500px;
    background-color: burlywood;
    margin: 15px 10px;
  }
}
</style>
