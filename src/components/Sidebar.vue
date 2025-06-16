<template>
  <aside class="sidebar">
    <div class="profile-section">
      <div class="profile-image">
        <img src="https://via.placeholder.com/120x120" alt="Profile Picture" />
      </div>
      <h1 class="profile-name">John Doe</h1>
      <p class="profile-title">Full Stack Developer</p>
    </div>
    
    <nav class="navigation">
      <ul class="nav-list">
        <li class="nav-item">
          <button 
            @click="changeTab('workexperience')"
            :class="{ active: activeTab === 'workexperience' }"
            class="nav-button"
          >
            <span class="nav-icon">💼</span>
            Work Experience
          </button>
        </li>
        <li class="nav-item">
          <button 
            @click="changeTab('education')"
            :class="{ active: activeTab === 'education' }"
            class="nav-button"
          >
            <span class="nav-icon">🎓</span>
            Education
          </button>
        </li>
        <li class="nav-item">
          <button 
            @click="changeTab('projects')"
            :class="{ active: activeTab === 'projects' }"
            class="nav-button"
          >
            <span class="nav-icon">🚀</span>
            Projects
          </button>
        </li>
      </ul>
    </nav>
    
    <div class="contact-section">
      <h3 class="contact-title">Contact</h3>
      <div class="contact-info">
        <p>📧 john.doe@email.com</p>
        <p>📱 (555) 123-4567</p>
        <p>📍 San Francisco, CA</p>
        <p>🔗 linkedin.com/in/johndoe</p>
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {
    activeTab: {
      type: String,
      required: true
    }
  },
  methods: {
    changeTab(tab) {
      this.$emit('tab-change', tab)
    }
  }
}
</script>