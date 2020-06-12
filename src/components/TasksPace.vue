<template>
  <div class="taskspace">
    <div class="main-container">
      <div class="title">
        Tasks Pace
        <a name="taskspace" style="padding-top: 190px"></a>
      </div>
      <div class="tasks-container">
        <div class="tasks">
          <div class="tasks-container-center">
            <div class="tasks-title">Use of Funds</div>
            <div class="block-with-tasks" v-for="(item, index) in tasks" :key="index">
              <div class="tasks-title-2" @click="show = (index + 1)">
                <div class="box-task" v-if="show != (index + 1)">+</div>
                <div class="box-task" v-else>-</div>
                {{ item.name }}
                <span>({{ item.list.length }})</span>
              </div>
              <transition name="fade">
                <div v-if="(index + 1) == show" class="mini-block-with-tasks">
                  <div class="one-task" v-for="(itm, ind) in item.list" :key="ind">
                    <span>{{itm.task}} {{ n * 3 / 1 }}</span>
                    <div class="tasks-points">
                      <div class="tasks-points-box" :style="{
                        marginLeft: `${n * itm.week}%`,
                        width: `${(n * itm.points.length) + .35}%`
                      }">
                        <div class="tasks-points-line">
                          <div
                            class="tasks-points-item"
                            v-for="(it, indd) in itm.points"
                            :key="indd"
                          >
                            <span :class="{ active: it.isSpan, opacity: it.isOpacity }">
                              {{ it.name }}%
                            </span>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </transition>
            </div>
          </div>
        </div>

        <div class="matrix">
          <div class="matrix-item">
            <div class="matrix-year">April 2020</div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w1</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w2</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w3</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w4</span>
              </div>
            </div>
          </div>
          <div class="matrix-item">
            <div class="matrix-year">May 2020</div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w1</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w2</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w3</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w4</span>
              </div>
            </div>
          </div>
          <div class="matrix-item active">
            <div class="matrix-year">June 2020</div>
            <div class="matrix-col active">
              <div class="matrix-name">
                <span>w1</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w2</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w3</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w4</span>
              </div>
            </div>
          </div>
          <div class="matrix-item active">
            <div class="matrix-year">July 2020</div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w1</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w2</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w3</span>
              </div>
            </div>
            <div class="matrix-col">
              <div class="matrix-name">
                <span>w4</span>
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
      show: 1,
      tasks: [
        {
          name: "Setup",
          list: [
            {
              task: "Project set up",
              points: [
                { name: 50, isSpan: true, isOpacity: false },
                { name: 90, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 1
            },
            {
              task: "Project initiation",
              points: [
                { name: 100, isSpan: false, isOpacity: true },
                { name: 150, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 105, isSpan: false, isOpacity: true }
              ],
              week: 2
            },
            {
              task: "Planning",
              points: [
                { name: 100, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true }
              ],
              week: 4
            },
            {
              task: "UX and UI",
              points: [
                { name: 75, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 9
            },
            {
              task: "Project charter document",
              points: [{ name: 100, isSpan: false, isOpacity: true }]
            },
            {
              task: "Customer journey map",
              points: [{ name: 100, isSpan: false, isOpacity: true }]
            },
            {
              task: "Backend architecture document",
              points: [{ name: 100, isSpan: false, isOpacity: true }]
            },
            {
              task: "Development approach, life cycle selection",
              points: [{ name: 100, isSpan: false, isOpacity: true }]
            },
            {
              task: "Drafts for the payment system and virtual currency",
              points: [
                { name: 98, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Draft for Marketing: initial user acquisition document",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Audit log",
              points: [
                { name: 90, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "API for creating tournaments",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task:
                "Additional fields in user profiles according to layouts - date of birth, options like “receive notifications” (backend)",
              points: [{ name: 0, isSpan: false, isOpacity: true }]
            },
            {
              task:
                "Bootstrapped frontend: integrated with Django, made authorization, demo profile and demo main",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task:
                "An environment for the front-end developers — deployment in one team, local backend with the latest edits and data, everything is being downloaded automatically",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Player Profile, ver 1",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Player History",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Edit profile",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Add country and birthdate",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Authentification via Discord account",
              points: [
                { name: 100, isSpan: false, isOpacity: false } //отдельно
              ]
            },
            {
              task: "Linking profile to Discord account",
              points: [
                { name: 100, isSpan: false, isOpacity: false } //отдельно
              ]
            },
            {
              task: "List of player's tournaments",
              points: [
                { name: 100, isSpan: false, isOpacity: false }, //отдельно
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "List of player's matches",
              points: [
                { name: 100, isSpan: false, isOpacity: false }, //отдельно
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "List of player's teams",
              points: [
                { name: 100, isSpan: false, isOpacity: false }, //отдельно
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Player's settings",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Team profile, ver 1",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Team History",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Invitation to Join team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Join team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Edit team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Delete team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Team preferences: games",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Invitation to the tournament sent by the team",
              points: [{ name: 0, isSpan: false, isOpacity: true }]
            },
            {
              task: "Game List",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Games list view (grid, carousel, list)",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Game Detail",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Tournament Detail",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Create tournament (advanced settings)",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Match detail",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Tournament Admin role",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Tournament Leaderboard",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "User verification for the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Edit Leaderboard",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Matches Schedule",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Edit matches schedule",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Add stream to the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Set up max nimber of the tournament participants",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Finish tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "List of matches in the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "List of tournament participants",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "List of teams taking part in the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Tournament rules",
              points: [{ name: 0, isSpan: false, isOpacity: true }]
            },
            {
              task: "Tournaments requests",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Payment Processing",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Match Self Reporting",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Match score submitting and calculation",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Match Dispute",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Payment Transactions",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Super Admin Dashboard",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Game supported",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Email notifications",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Community building",
              points: [
                { name: 50, isSpan: true, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Mobile development (iOS)",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Mobile development (Android)",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Security / Stability / Maintenance",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "API creation for gathering data from gamers platforms",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "When the platform is in operation",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Online Events",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Offline Events",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Fair play",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Trainings",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            }
          ]
        },
        {
          name: "Features for future releases",
          list: [
            {
              task: "Authorization security options"
            },
            {
              task: "Head-to-head tournaments",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Bracketed tournaments",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Paid tournaments",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            { task: "Prizes section at the tournament page" },
            {
              task: "Age requirements logic",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Admin panel with the White Label features",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "White label for the platform",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "White label for the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "White label of the features availability",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "White label landings",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "White label promotion",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            { task: "Player's stats" },
            { task: "Teams ranks" },
            {
              task: "Personalization",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "User's preferences settings tab in the user profile",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Suggestions for the user on how to move up",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Game supported",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Integration",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Tournaments matching",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Team matching",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Gamification",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            { task: "Game bets" },
            { task: "AI engine" },
            {
              task: "Points system as  virtual currency",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "In-app purchases",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Referral system",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            }
          ],
          points: [{ name: 50 }, { name: 90 }, { name: 100 }]
        },
        {
          name: "Documentation",
          list: [
            {
              task: "Project charter",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Detailed plan",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Budget",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Competitors research",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "User flow",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Virtual currency overview",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Payment systems and integrations",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "Marketing: initial user acquisition",
              points: [{ name: 100, isSpan: false, isOpacity: false }]
            },
            {
              task: "White Label options and overview",
              points: [
                { name: 30, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Virtual Currency research",
              points: [
                { name: 40, isSpan: true, isOpacity: false },
                { name: 50, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Research on competitors features",
              points: [
                { name: 50, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ]
            },
            {
              task: "Marketing plan",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Marketing strategy",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Market and competitors research",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Demographic research",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Traffic report",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Promo budget",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Promo strategy",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Marketing activities reports",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Video production plan",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Videos scenarios",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "SEO plan",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Keywords list",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Semantic core",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Touchpoint map",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            },
            {
              task: "Copyright content",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ]
            }
          ]
        }
      ],
      n: ""
    };
  },
  mounted() {
    // eslint-disable-next-line no-unused-vars
    const el = document.querySelector(".matrix-col").offsetWidth,
      // eslint-disable-next-line no-unused-vars
      wrap = document.querySelector(".matrix").offsetWidth;

    this.n = (el / wrap) * 100;
  }
};
</script>

<style>
@import "../assets/css/taskspace.css";
</style>
