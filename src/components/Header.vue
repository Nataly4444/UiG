<template>
  <div class="header">
    <div class="main-container">
      <div class="header-container">
        <div class="mini-header-container">
          <div class="header-logo">
            <img class="logo" src="../assets/img/logo.svg" alt="" />
          </div>
          <div class="gradient"></div>
          <div class="navigation">
            <a class="navigation-arrow prev" href="">
              <img class="prev-img" src="../assets/img/arrow.svg" alt="" />
              <span>Prev</span>
            </a>
            <p class="data">
              June 5, 2020
            </p>
            <a href="" class="navigation-arrow next">
              <span>Next</span>
              <img class="next-img" src="../assets/img/arrow.svg" alt="" />
            </a>
          </div>
        </div>
        <div class="updates">
          <p>Last updated: 3 hours ago</p> 
           <a href="" class="burger-menu" @click="show = !show"><img src="../assets/img/burger.svg" alt=""></a>
        <!-- <a href="" class="burger-menu"><img src="../assets/img/close.svg" alt=""></a> -->

        </div>
       
      </div>
    </div>
  </div>
</template>

<script>
export default {

  data: ()=> {
    return {
      show: false
    }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../assets/css/main.css";
@import "../assets/css/header.css";
</style>
