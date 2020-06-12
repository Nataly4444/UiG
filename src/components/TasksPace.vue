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
                    <span>{{itm.task}}</span>
                    <div class="tasks-points">
                      <div
                        class="tasks-points-box"
                        :style="{
                        marginLeft: `${((n * ( (itm.week + (6 - isMonth)) + prefix ))) + .15}%`,
                        width: `${(n * itm.points.length) + .15}%`
                      }"
                      >
                        <div class="tasks-points-line">
                          <div
                            class="tasks-points-item"
                            v-for="(it, indd) in itm.points"
                            :key="indd"
                          >
                            <span
                              :class="{ active: it.isSpan, opacity: it.isOpacity }"
                            >{{ it.name }}%</span>
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
          <div class="matrix-item" v-for="(item, index) in calend" :key="index" :class="{active: index > 1}">
            <div class="matrix-year">{{ item }} 2020 {{ isMonth }}</div>
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
              week: 2
            },
            {
              task: "Project initiation",
              points: [
                { name: 100, isSpan: false, isOpacity: true },
                { name: 150, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: true },
                { name: 105, isSpan: false, isOpacity: true }
              ],
              week: 3
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
              week: 3
            },
            {
              task: "Project charter document",
              points: [{ name: 100, isSpan: false, isOpacity: true }],
              week: 5
            },
            {
              task: "Customer journey map",
              points: [{ name: 100, isSpan: false, isOpacity: true }],
              week: 5
            },
            {
              task: "Backend architecture document",
              points: [{ name: 100, isSpan: false, isOpacity: true }],
              week: 5
            },
            {
              task: "Development approach, life cycle selection",
              points: [{ name: 100, isSpan: false, isOpacity: true }],
              week: 5
            },
            {
              task: "Drafts for the payment system and virtual currency",
              points: [
                { name: 98, isSpan: false, isOpacity: true },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 5
            },
            {
              task: "Draft for Marketing: initial user acquisition document",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 8
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
              ],
              week: 6
            },
            {
              task: "API for creating tournaments",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 5
            },
            {
              task:
                "Additional fields in user profiles according to layouts - date of birth, options like “receive notifications” (backend)",
              points: [{ name: 0, isSpan: false, isOpacity: true }],
              week: 0
            },
            {
              task:
                "Bootstrapped frontend: integrated with Django, made authorization, demo profile and demo main",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 6
            },
            {
              task:
                "An environment for the front-end developers — deployment in one team, local backend with the latest edits and data, everything is being downloaded automatically",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 4
            },
            {
              task: "Player Profile, ver 1",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 5
            },
            {
              task: "Player History",
              points: [
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 5
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
              ],
              week: 8
            },
            {
              task: "Add country and birthdate",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 9
            },
            {
              task: "Authentification via Discord account",
              points: [
                { name: 100, isSpan: false, isOpacity: false } //отдельно
              ],
              week: 8
            },
            {
              task: "Linking profile to Discord account",
              points: [
                { name: 100, isSpan: false, isOpacity: false } //отдельно
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
            },
            {
              task: "List of player's teams",
              points: [
                { name: 100, isSpan: false, isOpacity: false }, //отдельно
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 8
            },
            {
              task: "Player's settings",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 17
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
              ],
              week: 11
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
              ],
              week: 11
            },
            {
              task: "Invitation to Join team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 14
            },
            {
              task: "Join team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 14
            },
            {
              task: "Edit team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 16
            },
            {
              task: "Delete team",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 20
            },
            {
              task: "Team preferences: games",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 20
            },
            {
              task: "Invitation to the tournament sent by the team",
              points: [{ name: 0, isSpan: false, isOpacity: true }],
              week: 21
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
              ],
              week: 14
            },
            {
              task: "Games list view (grid, carousel, list)",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 21
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
              ],
              week: 14
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
              ],
              week: 6
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
              ],
              week: 15
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
              ],
              week: 10
            },
            {
              task: "Tournament Admin role",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 17
            },
            {
              task: "Tournament Leaderboard",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 17
            },
            {
              task: "User verification for the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 22
            },
            {
              task: "Edit Leaderboard",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 18
            },
            {
              task: "Matches Schedule",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 19
            },
            {
              task: "Edit matches schedule",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 19
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
              ],
              week: 17
            },
            {
              task: "Set up max nimber of the tournament participants",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 17
            },
            {
              task: "Finish tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 17
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
              ],
              week: 9
            },
            {
              task: "List of tournament participants",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 19
            },
            {
              task: "List of teams taking part in the tournament",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 19
            },
            {
              task: "Tournament rules",
              points: [{ name: 0, isSpan: false, isOpacity: true }],
              week: 20
            },
            {
              task: "Tournaments requests",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 20
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
              ],
              week: 15
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
              ],
              week: 10
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
              ],
              week: 10
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
              ],
              week: 17
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
              ],
              week: 15
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
              ],
              week: 9
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
              ],
              week: 9
            },
            {
              task: "Email notifications",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 20
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
              ],
              week: 8
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
              ],
              week: 21
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
              ],
              week: 21
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
              ],
              week: 23
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
              ],
              week: 25
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
              ],
              week: 24
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
              ],
              week: 24
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
              ],
              week: 24
            },
            {
              task: "Fair play",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
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
              ],
              week: 25
            }
          ]
        },
        {
          name: "Features for future releases",
          list: [
            {
              task: "Authorization security options",
              points: []
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
              ],
              week: 19
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
              ],
              week: 19
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
              ],
              week: 19
            },
            {
              task: "Prizes section at the tournament page",
              points: []
            },
            {
              task: "Age requirements logic",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
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
              ],
              week: 19
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
              ],
              week: 19
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
              ],
              week: 19
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
              ],
              week: 19
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
              ],
              week: 19
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
              ],
              week: 19
            },
            { task: "Player's stats", points: [] },
            { task: "Teams ranks", points: [] },
            {
              task: "Personalization",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 19
            },
            {
              task: "User's preferences settings tab in the user profile",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
            },
            {
              task: "Suggestions for the user on how to move up",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
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
              ],
              week: 25
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
              ],
              week: 19
            },
            {
              task: "Tournaments matching",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
            },
            {
              task: "Team matching",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
            },
            {
              task: "Gamification",
              points: [
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true },
                { name: 0, isSpan: false, isOpacity: true }
              ],
              week: 25
            },
            { task: "Game bets", points: [] },
            { task: "AI engine", points: [] },
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
              ],
              week: 25
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
              ],
              week: 25
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
              ],
              week: 25
            }
          ],
          points: [{ name: 50 }, { name: 90 }, { name: 100 }]
        },
        {
          name: "Documentation",
          list: [
            {
              task: "Project charter",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 2
            },
            {
              task: "Detailed plan",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 2
            },
            {
              task: "Budget",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 2
            },
            {
              task: "Competitors research",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 2
            },
            {
              task: "User flow",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 3
            },
            {
              task: "Virtual currency overview",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 4
            },
            {
              task: "Payment systems and integrations",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 4
            },
            {
              task: "Marketing: initial user acquisition",
              points: [{ name: 100, isSpan: false, isOpacity: false }],
              week: 4
            },
            {
              task: "White Label options and overview",
              points: [
                { name: 30, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 4
            },
            {
              task: "Virtual Currency research",
              points: [
                { name: 40, isSpan: true, isOpacity: false },
                { name: 50, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 4
            },
            {
              task: "Research on competitors features",
              points: [
                { name: 50, isSpan: true, isOpacity: false },
                { name: 100, isSpan: false, isOpacity: false }
              ],
              week: 7
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
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
              ],
              week: 8
            }
          ]
        }
      ],
      n: "",
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
      isMonth: 0,
      isIndex: 1,
    };
  },
  props: {
    index: Number,
    prefix: Number
  },
  computed: {
    calend() {
    // eslint-disable-next-line vue/no-side-effects-in-computed-properties
      this.isMonth = this.index + 1;

      return this.calendar.slice((this.isMonth - 4) < 0 ? 0 : this.isMonth - 4, this.isMonth)
    }
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
