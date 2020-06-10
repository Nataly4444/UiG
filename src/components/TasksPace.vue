<template>
  <div class="taskspace">
    <div class="main-container">
      <div class="title">Tasks Pace</div>
      <div class="tasks-container">
        <div class="tasks">
          <div class="tasks-container-center">
            <div class="tasks-title">Use of Funds</div>
            <div class="block-with-tasks">
            <div class="tasks-title-2" @click="show = !show">Setup <span>(12)</span></div>
            <transition name="fade">
                <div v-if="show" class="mini-block-with-tasks">
                <div class="one-task" v-for="item in setup"  :key="item.task"> {{item.task}}</div>
            </div>
            </transition>
            
          </div>
          </div>
          
        </div>

        <div class="matrix"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
        show: false,
        setup:[
             {  task: "Project set up"},
            { task: "Project initiation"},
             { task: "Planning"},
             { task: "UX and UI"},
             { task: "Project charter document"},
             { task: "Customer journey map"},
             { task: "Backend architecture document"},
             { task: "Development approach, life cycle selection"},
             { task: "Drafts for the payment system and virtual currency"},
             { task: "Draft for Marketing: initial user acquisition document"},
             { task: "Audit log"},
             { task: "API for creating tournaments"},
             { task: "Additional fields in user profiles according to layouts - date of birth, options like “receive notifications” (backend)"},
             { task: "Bootstrapped frontend: integrated with Django, made authorization, demo profile and demo main"},
             { task: "An environment for the front-end developers — deployment in one team, local backend with the latest edits and data, everything is being downloaded automatically"},
             { task: "Player Profile, ver 1"},
             { task: "Player History"},
             { task: "Edit profile"},
             { task: "Add country and birthdate"},
             { task: "Authentification via Discord account"},
             { task: "Linking profile to Discord account"},
             { task: "List of player's tournaments"},
             { task: "List of player's matches"},
             { task: "List of player's teams"},
             { task: "Player's settings"},
             { task: "Team profile, ver 1"},
             { task: "Team History"},
             { task: "Invitation to Join team"},
             { task: "Join team"},
             { task: "Edit team"},
             { task: "Delete team"},
             { task: "Team preferences: games"},
             { task: "Invitation to the tournament sent by the team"},
             { task: "Game List"},
             { task: "Games list view (grid, carousel, list)"},
             { task: "Game Detail"},
             { task: "Tournament Detail"},
             { task: "Create tournament (advanced settings)"},
             { task: "Match detail"},
             { task: "Tournament Admin role"},
             { task: "Tournament Leaderboard"},
             { task: "User verification for the tournament"},
             { task: "Edit Leaderboard"},
             { task: "Matches Schedule"},
             { task: "Edit matches schedule"},
             { task: "Add stream to the tournament set up max nimber of the tournament participants"},
             { task: "Finish tournament"},
             { task: "List of matches in the tournament"},
             { task: "List of tournament participants"},
             { task: "List of teams taking part in the tournament"},
             { task: "Tournament rules"},
             { task: "Tournaments requests"},
             { task: "Payment Processing"},
             { task: "Match Self Reporting"},
             { task: "Match score submitting and calculation"},
             { task: "Match Dispute"},
             { task: "Payment Transactions"},
             { task: "Super Admin Dashboard"},
             { task: "Game supported"},
             { task: "Email notifications"},
             { task: "Community building"},
             { task: "Mobile development (iOS)"},
             { task: "Mobile development (Android)"},
             { task: "Security / Stability / Maintenance"},
             { task: "API creation for gathering data from gamers platforms"},
             { task: "When the platform is in operation"},
             { task: "Online Events"},
             { task: "Offline Events"},
             { task: "Fair play"},
             { task: "Trainings"},
             
        ] }
    }
 
};
</script>

<style>
@import "../assets/css/taskspace.css";
</style>
