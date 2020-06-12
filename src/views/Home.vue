<template>
  <div class="main-background">
    <Header v-on:index='ind' />
    <SubHeader />
    <Summary />
    <ForReview />
    <TasksPace :index="propIndex" />
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
      propIndex: new Date().getMonth()
    }
  },
  methods: {
    ind(e) {
      this.propIndex = e
    }
  }
};
</script>
