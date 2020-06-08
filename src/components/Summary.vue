<template>
  <div class="summary">
    <div class="main-container">
      <div  class="title">Project Dashboard <a name='summary'></a></div>
      <div class="graphics">
        <div class="double-graphic">
          <div class="graphic alpha">
            <!-- <img src="../assets/img/Main-progress.svg" alt="" /> -->
          </div>
          <div class="graphic core-task">
            <!-- <img src="../assets/img/Core-task.svg" alt="" /> -->
          </div>
          <h1>Core task: {{ task }}</h1>
            <div class="progress">
              <div
                class="progress-bar"
                v-for="item in progress"
                :key="item.id"
                :style="{ 'background' : item.isDone ? '#18B573' : '#3282FA', 'width' : `${item.count / task * 100}%` }"
              >
                <div class="progress-name">
                  {{ item.count }} <span>{{ item.isDone ? 'done' : 'in progress' }}</span>
                </div>
              </div>
            </div>

            <br><hr><br>

            <div class="circle-wrap">
              <div class="circle">
                <div class="circle__range" :style="{ 'transform' : `rotate(-${circles}deg)` }"></div>
              </div>
              
              <div class="circle-res">
                {{ circleRes }}%
              </div>
              <div class="circle-min">0%</div>
              <div class="circle-max">{{ circle }}%</div>
            </div>
        </div>
        <div class="graphic health">
          <!-- <img src="../assets/img/Project-Health.svg" alt="" /> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      task: 42,
      progress: [
        { id: 1, count: 28, isDone: true },
        { id: 2, count: 7, idDone: false }
      ],
      circle: 120,
      circleRes: 50
    };
  },
  computed: {
    circles() {
      return 180 - (this.circleRes / this.circle * 180)
    }
  }
};
</script>

<style>
@import "../assets/css/main.css";
@import "../assets/css/summary.css";
</style>
