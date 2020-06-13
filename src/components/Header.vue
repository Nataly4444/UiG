<template>
  <div class="header">
    <div class="main-container">
      <div class="header-container" >
        <div v-if="show" class="header-container-mini">
          <div class="mini-header-container">
            <div class="header-logo">
              <img class="logo" src="../assets/img/logo.svg" alt />
            </div>
            <div class="gradient"></div>
            <div class="navigation" >
              <a class="navigation-arrow prev" href v-on:click.prevent="slide" v-if="month != 3">
                <img class="prev-img" src="../assets/img/arrow.svg" alt />
                <span>Prev</span>
              </a>
              <p class="data">{{ calendar[month] }} {{ day }}, {{ year }}</p>
              <a href class="navigation-arrow next" v-on:click.prevent="slides" v-if="month != 11">
                <span>Next</span>
                <img class="next-img" src="../assets/img/arrow.svg" alt />
              </a>
            </div>
          </div>
          <div class="updates">
            <p>Last updated: 3 hours ago</p>
          </div>
        </div>
        <div class="navigation2" v-else>
          <a class="navigation-arrow prev" href v-on:click.prevent="slide" v-if="month != 3">
            <img class="prev-img" src="../assets/img/arrow.svg" alt />
            <span>Prev</span>
          </a>
          <p class="data">{{ calendar[month] }} {{ day }}, 2020</p>
          <a href class="navigation-arrow next" v-on:click.prevent="slides" v-if="month != 11">
            <span>Next</span>
            <img class="next-img" src="../assets/img/arrow.svg" alt />
          </a>
        </div>
        
        <a href class="burger-menu" @click.prevent="isShow">
          <img src="../assets/img/burger.svg" v-if="show" alt />
          <img src="../assets/img/close.svg" v-else alt />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      show: true,
      calendar: [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December"
      ],
      month: new Date().getMonth(),
      day: new Date().getUTCDate(),
      year: new Date().getFullYear()
    };
  },
  methods: {
    isShow() {
      !this.show ? this.show = true : this.show = false
    },
    slide() {
      this.month = (this.month - 1) < 3 ? 3 : (this.month - 1)
      
      this.$emit('index', this.month)
    },
    slides() {
      this.month = this.month > 10 ? 11 : (this.month + 1)
      
      this.$emit('index', this.month)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../assets/css/main.css";
@import "../assets/css/header.css";
/* @import "../assets/fonts/lato/stylesheet.css"; */
</style>
