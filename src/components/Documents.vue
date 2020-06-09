<template>
  <div class="documents">
    <div class="main-container">
      <div class="title">
        Documents
        <a name="documents"></a>
      </div>
      <div class="filter">
        <div
          class="filter-container"
          v-for="item in filter"
          :key="item.id"
          :class="{ active: item.name == isActive }"
          v-on:click.prevent="isActive = item.name"
        >
          <p class="filter-title">{{ item.name }}</p>
        </div>
      </div>
      <div class="documents-container">
        <div
          class="one-document"
          v-for="(item, index) in doc"
          :key="index"
          :class="{ active: item.role.includes(isActive) }"
        >
          <div class="document-title">{{ item.name }}</div>
          <div class="document-text">{{ item.txt }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: "All",
      filter: [
        { id: 1, name: "All" },
        { id: 2, name: "Marketing" },
        { id: 3, name: "Development" }
      ],
      doc: [
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Detailed plan - internal",
          txt:
            "In convallis, lacus eget euismod elementum, magna ante"
        },
        {
          role: ["All", "Marketing"],
          name: "Presentation with core features",
          txt:
            "The presentation contains actual within the MVP along  with the features that will be developed during the next development stages"
        },
        {
          role: ["All", "Marketing"],
          name: "Competitors research",
          txt:
            "Competitors research with an info on the competitors general data"
        },
        {
          role: ["All", "Marketing"],
          name: "KPI",
          txt:
            "The explanation of the work KPI estimations"
        },
        {
          role: ["All", "Marketing"],
          name: "Initial user acquisition",
          txt:
            "Overview of the possible user acquisition strategies"
        },
        {
          role: ["All", "Development"],
          name: "User Flow",
          txt:
            "User Flow on the tournament creation and participation"
        },
        {
          role: ["All", "Development"],
          name: "Payment systems and integrations",
          txt:
            "Proposal on the payment system structure and features"
        },
        {
          role: ["All", "Development"],
          name: "Virtual currency",
          txt:
            "Proposal on the virtual currency functionality"
        },
        {
          role: ["All", "Development"],
          name: "White Label specifications",
          txt:
            "White Label concept and initial features to develop"
        },
        {
          role: ["All", "Development"],
          name: "White label - possible solutions",
          txt:
            "White Label concept and initial features to develop"
        },
        {
          role: ["All", "Development"],
          name: "Brackets",
          txt:
            "Pros and Cons of the own brackets development"
        },
        {
          role: ["All", "Development"],
          name: "How Brackets work",
          txt:
            "Overview of the brackets mechanics"
        },
        {
          role: ["All", "Development"],
          name: "Leaderboards system",
          txt:
            "Overview of the Leaderboards mechanics"
        },
        {
          role: ["All", "Development"],
          name: "Battle Royale",
          txt:
            "Mechanics of the Battle Royale tournaments"
        }

      ]
    };
  }
};
</script>

<style>
@import "../assets/css/main.css";
@import "../assets/css/documents.css";
</style>
