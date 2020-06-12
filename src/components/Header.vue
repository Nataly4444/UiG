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
              <a class="navigation-arrow prev" href v-on:click.prevent="slide">
                <img class="prev-img" src="../assets/img/arrow.svg" alt />
                <span>Prev</span>
              </a>
              <p class="data">{{ calendar[month] }} {{ day }}, 2020</p>
              <a href class="navigation-arrow next">
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
           <a class="navigation-arrow prev" href v-on:click.prevent="slide">
              <img class="prev-img" src="../assets/img/arrow.svg" alt />
              <span>Prev</span>
            </a>
            <p class="data">{{ calendar[month] }} {{ day }}, 2020</p>
           <a href class="navigation-arrow next">
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
      month: null,
      day: 0
    };
  },
  methods: {
    isShow() {
      !this.show ? this.show = true : this.show = false
    },
    slide() {
      this.month = (this.month - 1) < 0 ? 0 : (this.month - 1)
      this.$emit('index', this.month)
    }
  },
  mounted() {
    const d = new Date();
    // eslint-disable-next-line vue/no-side-effects-in-computed-properties

    // eslint-disable-next-line vue/no-side-effects-in-computed-properties
    this.month = d.getMonth();
    this.day   = d.getUTCDate();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "../assets/css/main.css";
@import "../assets/css/header.css";
/* @import "../assets/fonts/lato/stylesheet.css"; */
</style>
