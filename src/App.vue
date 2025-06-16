<template>
  <div id="app">
    <div class="app-container">
      <Sidebar @tab-change="activeTab = $event" :active-tab="activeTab" />
      <main class="main-content">
        <WorkExperience v-if="activeTab === 'workexperience'" />
        <Education v-if="activeTab === 'education'" />
        <Projects v-if="activeTab === 'projects'" />
      </main>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'
import WorkExperience from './components/WorkExperience.vue'
import Education from './components/Education.vue'
import Projects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    Sidebar,
    WorkExperience,
    Education,
    Projects
  },
  data() {
    return {
      activeTab: 'workexperience'
    }
  }
}
</script>