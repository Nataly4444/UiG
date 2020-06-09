<template>
  <div class="summary">
    <div class="main-container">
      <div class="title">Project Dashboard <a name="summary"></a></div>
      <div class="graphics">
        <div class="double-graphic">
          <div class="graphic alpha">
            <div class="container-90">
              <div class="graphic-title">Alpha {{ alpha }}</div>
              <div class="progress-container">
                <div class="progress">
                  <div
                    class="progress-bar"
                    :style="{
                      background: '#18B573',
                      width: `${alphaprogress}%`,
                    }"
                  >
                    <div class="progress-name">
                      {{ alphaprogress }}%
                      <span></span>
                    </div>
                  </div>
                </div>
                <div class="one-point">
                  <div class="one-point-text">
                    <div class="point-text-span">Estimate Date</div>
                    <div class="point-text-data">August 17, 2020</div>
                  </div>
                  <div class="point-circle"></div>
                </div>
                <div class="two-point">
                  <div class="point-circle"></div>
                  <div class="two-point-text">
                    <div class="point-text-span">Planned Date</div>
                    <div class="point-text-data">August 23, 2020</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="core-task">
            <div class="container-90">
              <div class="graphic-title">Core task: {{ task }}</div>
              <div class="progress">
                <div
                  class="progress-bar"
                  v-for="item in progress"
                  :key="item.id"
                  :style="{
                    background: item.isDone ? '#18B573' : '#3282FA',
                    width: `${(item.count / task) * 100}%`,
                  }"
                >
                  <div class="progress-name">
                    {{ item.count }}
                    <span>{{ item.isDone ? "done" : "in progress" }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="graphic health">
          <div class="container-health">
            <div class="circle-wrap">
              <div class="circle">
                <div
                  class="circle__range"
                  :style="{ transform: `rotate(-${circles}deg)` }"
                ></div>
              </div>

              <div class="circle-res">
                <img
                  class="icon-health"
                  src="../assets/img/health.svg"
                  alt=""
                />
                {{ circleRes }}%
                <div class="speed">2% ↑</div>
              </div>
              <div class="circle-min">0%</div>
              <div class="circle-max">{{ circle }}%</div>
            </div>
            <div class="health-text">
              <div class="health-text-title">Project Health</div>
              <div class="health-text-info">
                Project health is an integrated metric based on team speed, work
                quality, and organization degree.
              </div>
            </div>
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
      alphaprogress: 40,
      alpha: 1.1,
      task: 42,
      progress: [
        { id: 1, count: 28, isDone: true },
        { id: 2, count: 7, idDone: false },
      ],
      circle: 120,
      circleRes: 107,
    };
  },
  computed: {
    circles() {
      return 180 - (this.circleRes / this.circle) * 180;
    },
  },
};
</script>

<style>
@import "../assets/css/main.css";
@import "../assets/css/summary.css";
</style>
