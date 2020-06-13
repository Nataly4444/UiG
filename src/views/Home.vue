<template>
  <div class="main-background">
    <Header v-on:index='ind' />
    <SubHeader />
    <Summary />
    <ForReview />
    <TasksPace :index="propIndex" :prefix="prefix" />
    <LastMinutes />
    <Documents />

    <Notes />
  </div>
</template>

<style>
@import "../assets/css/main.css";
@import "../assets/fonts/lato/stylesheet.css";
</style>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import SubHeader from "@/components/SubHeader.vue";
import Summary from "@/components/Summary.vue";
import ForReview from "@/components/ForReview.vue";
import TasksPace from "@/components/TasksPace.vue";

import LastMinutes from "@/components/LastMinutes.vue";
import Documents from "@/components/Documents.vue";
import Notes from "@/components/Notes.vue";

export default {
  name: "Home",
  components: {
    Header,
    SubHeader,
    Summary,
    ForReview,
    TasksPace,

    LastMinutes,
    Documents,
    Notes,
  },
  data() {
    return {
      propIndex: { prev: (11 - new Date().getMonth()) - 1, next: 11 - new Date().getMonth() },
      prefix: 0
    }
  },
  methods: {
    ind(e) {
      this.propIndex = e

      if ( e.p == 1 ) this.prefix += 3
      if ( e.n == 1 ) this.prefix -= 3
    }
  }
};
</script>
