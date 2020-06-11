<template>
  <div class="taskspace">
    <div class="main-container">
      <div class="title">Tasks Pace<a name="taskspace" style="padding-top: 190px"></a></div>
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
                  </div>
                </div>
              </transition>
            </div>
          </div>
        </div>

        <div class="matrix">
          <div class="matrix-item">
            <div class="matrix-year">
              April 2020
            </div>
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
            <div class="matrix-year">
              May 2020
            </div>
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
            <div class="matrix-year">
              June 2020
            </div>
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
          <div class="matrix-item">
            <div class="matrix-year">
              July 2020
            </div>
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
          name: 'Setup',
          list: [
            { task: "Project set up" },
            { task: "Project initiation" },
            { task: "Planning" },
            { task: "UX and UI" },
            { task: "Project charter document" },
            { task: "Customer journey map" },
            { task: "Backend architecture document" },
            { task: "Development approach, life cycle selection" },
            { task: "Drafts for the payment system and virtual currency" },
            { task: "Draft for Marketing: initial user acquisition document" },
            { task: "Audit log" },
            { task: "API for creating tournaments" },
            {
              task:
                "Additional fields in user profiles according to layouts - date of birth, options like “receive notifications” (backend)"
            },
            {
              task:
                "Bootstrapped frontend: integrated with Django, made authorization, demo profile and demo main"
            },
            {
              task:
                "An environment for the front-end developers — deployment in one team, local backend with the latest edits and data, everything is being downloaded automatically"
            },
            { task: "Player Profile, ver 1" },
            { task: "Player History" },
            { task: "Edit profile" },
            { task: "Add country and birthdate" },
            { task: "Authentification via Discord account" },
            { task: "Linking profile to Discord account" },
            { task: "List of player's tournaments" },
            { task: "List of player's matches" },
            { task: "List of player's teams" },
            { task: "Player's settings" },
            { task: "Team profile, ver 1" },
            { task: "Team History" },
            { task: "Invitation to Join team" },
            { task: "Join team" },
            { task: "Edit team" },
            { task: "Delete team" },
            { task: "Team preferences: games" },
            { task: "Invitation to the tournament sent by the team" },
            { task: "Game List" },
            { task: "Games list view (grid, carousel, list)" },
            { task: "Game Detail" },
            { task: "Tournament Detail" },
            { task: "Create tournament (advanced settings)" },
            { task: "Match detail" },
            { task: "Tournament Admin role" },
            { task: "Tournament Leaderboard" },
            { task: "User verification for the tournament" },
            { task: "Edit Leaderboard" },
            { task: "Matches Schedule" },
            { task: "Edit matches schedule" },
            {
              task:
                "Add stream to the tournament set up max nimber of the tournament participants"
            },
            { task: "Finish tournament" },
            { task: "List of matches in the tournament" },
            { task: "List of tournament participants" },
            { task: "List of teams taking part in the tournament" },
            { task: "Tournament rules" },
            { task: "Tournaments requests" },
            { task: "Payment Processing" },
            { task: "Match Self Reporting" },
            { task: "Match score submitting and calculation" },
            { task: "Match Dispute" },
            { task: "Payment Transactions" },
            { task: "Super Admin Dashboard" },
            { task: "Game supported" },
            { task: "Email notifications" },
            { task: "Community building" },
            { task: "Mobile development (iOS)" },
            { task: "Mobile development (Android)" },
            { task: "Security / Stability / Maintenance" },
            { task: "API creation for gathering data from gamers platforms" },
            { task: "When the platform is in operation" },
            { task: "Online Events" },
            { task: "Offline Events" },
            { task: "Fair play" },
            { task: "Trainings" }
          ]
        },
        {
          name: 'Features for future releases',
          list: [
            { task: "Authorization security options" },
            { task: "Head-to-head tournaments" },
            { task: "Bracketed tournaments" },
            { task: "Paid tournaments" },
            { task: "Prizes section at the tournament page" },
            { task: "Age requirements logic" },
            { task: "Admin panel with the White Label features" },
            { task: "White label for the platform" },
            { task: "White label for the tournament" },
            { task: "White label of the features availability" },
            { task: "White label landings" },
            { task: "White label promotion" },
            { task: "Player's stats" },
            { task: "Teams ranks" },
            { task: "Personalization" },
            { task: "User's preferences settings tab in the user profile" },
            { task: "Suggestions for the user on how to move up" },
            { task: "Game supported" },
            { task: "Integration" },
            { task: "Tournaments matching" },
            { task: "Team matching" },
            { task: "Gamification" },
            { task: "Game bets" },
            { task: "AI engine" },
            { task: "Points system as  virtual currency" },
            { task: "In-app purchases" },
            { task: "Referral system" }
          ]
        },
        {
          name: 'Documentation',
          list: [
            { task: "Project charter" },
            { task: "Detailed plan" },
            { task: "Budget" },
            { task: "Competitors research" },
            { task: "User flow" },
            { task: "Virtual currency overview" },
            { task: "Payment systems and integrations" },
            { task: "Marketing: initial user acquisition" },
            { task: "White Label options and overview" },
            { task: "Virtual Currency research" },
            { task: "Research on competitors features" },
            { task: "Marketing plan" },
            { task: "Marketing strategy" },
            { task: "Market and competitors research" },
            { task: "Demographic research" },
            { task: "Traffic report" },
            { task: "Promo budget" },
            { task: "Promo strategy" },
            { task: "Marketing activities reports" },
            { task: "Video production plan" },
            { task: "Videos scenarios" },
            { task: "SEO plan" },
            { task: "Keywords list" },
            { task: "Semantic core" },
            { task: "Touchpoint map" },
            { task: "Copyright content" }
          ]
        }
      ]
    };
  }
};
</script>

<style>
@import "../assets/css/taskspace.css";
</style>
