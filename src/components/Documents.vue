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
          role: ["All", "Development"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Development"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Development"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Marketing"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
        },
        {
          role: ["All", "Development"],
          name: "Project chapter",
          txt:
            "The document provides a general project overview, it's mission anddevelopment direction"
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
