<template>
<div class="lastminutes">
    <div class="main-container">
        <div class="title">Last Minutes<a name='lastminutes' style="padding-top: 180px"></a></div>
        <div class="accordion">
            <!-- 1 -->
            <div class="accordion-item">
            <div  @click="show1 = !show1"  class="accordion-header">
                <p>What was done this week</p>
                <img v-if="show1==false" src="../assets/img/plus.svg" alt="">
                <img v-else src="../assets/img/minus.svg" alt="">
            </div>
                <transition  class="accordion-item-body">
                    <div v-if="show1" class="accordion-item-body-container">
                        <p>This week we’ve completed the backend for leaderboards subsystem: now we have all required features to submit the score for the match and view the updated leaderboard for the match or tournament. We’ve started working on the frontend part, planning to present the demo next week.</p>
                        <p>We’ve started developing UI components: website header and footer, basic inputs like button or text input. We have completed UI for the first page — the tournaments list.</p>
                        <p>Also, we’ve completed 90% of social authentication via discord, and started the research about linking user profiles to gamertag.</p>
                    </div>
                </transition>
            </div>


            <!-- 2 -->
            <div class="accordion-item">
            <div  @click="show2 = !show2" class="accordion-header">
                <p>Plan for next week</p>
                <img v-if="show2==false" src="../assets/img/plus.svg" alt="">
                <img v-else src="../assets/img/minus.svg" alt="">
            </div>
                <transition class="accordion-item-body">
                    <div v-if="show2" class="accordion-item-body-container">
                        <p>1) Social authentication (Discord only)</p>
                        <p>2) Scores system</p>
                        <p>3) Pages of matches</p>
                        <p>4) Tournament details page</p>
                        <p>5) Competitors research</p>
                        <p>6) Market research</p>
                        <p>7) UI updates</p>
                        <p>8) Future features planning</p>
                        <p>9) Groups creation research</p>
                        <p>10) Friends functionality research</p>
                        <p>11) Leaderboard sauggestions</p>
                    </div>
                </transition>
            </div>


            <!-- 3 -->
            <div class="accordion-item">
            <div  @click="show3 = !show3" class="accordion-header">
                <p>UiG to Review/Provide</p>
                <img v-if="show3==false" src="../assets/img/plus.svg" alt="">
                <img v-else src="../assets/img/minus.svg" alt="">
            </div>
                <transition class="accordion-item-body">
                    <div v-if="show3" class="accordion-item-body-container">
                        <div class="accordion-item-body-mini-container">
                            <a href="https://docs.google.com/spreadsheets/d/1UezLeNOaZBageAKfvkM0FHf7tJHWXb6XZe2mKW_GahQ/edit#gid=1339606528">Please review marketing analysis</a>
                            <div class="text-green">Please send us your comments before 06.12.2020</div>
                        </div>

                    </div>
                </transition>
            </div>





        </div>

    </div>

</div>
  
</template>

<script>
 export default {

  data: ()=> {
    return {
        show1: false,
        show2: false,
        show3: false,
    }
    }
}
</script>

<style>
@import "../assets/css/main.css";
@import "../assets/css/lastminutes.css";

</style>