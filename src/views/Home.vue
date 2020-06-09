<template>
  <div class="main-background">
    <Header />
    <SubHeader />
    <Summary />
    <ForReview />
    <LastMinutes />
    <Documents />

    <Notes />
  </div>
</template>

<style>
@import "../assets/css/main.css";
/* @import "../assets/css/stylename.css"; */
</style>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import SubHeader from "@/components/SubHeader.vue";
import Summary from "@/components/Summary.vue";
import ForReview from "@/components/ForReview.vue";

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

    LastMinutes,
    Documents,
    Notes,
  },
};
</script>
