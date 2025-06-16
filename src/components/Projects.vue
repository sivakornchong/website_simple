<template>
  <div class="projects">
    <header class="section-header">
      <h2 class="section-title">Projects</h2>
      <p class="section-subtitle">Featured work and personal projects</p>
    </header>
    
    <div class="projects-grid">
      <div 
        v-for="project in projects" 
        :key="project.id" 
        class="project-card"
      >
        <div class="project-image">
          <img :src="project.image" :alt="project.title" />
          <div class="project-overlay">
            <div class="project-links">
              <a 
                v-if="project.liveUrl" 
                :href="project.liveUrl" 
                target="_blank" 
                class="project-link live-link"
              >
                🌐 Live Demo
              </a>
              <a 
                v-if="project.githubUrl" 
                :href="project.githubUrl" 
                target="_blank" 
                class="project-link github-link"
              >
                📂 GitHub
              </a>
            </div>
          </div>
        </div>
        
        <div class="project-content">
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-description">{{ project.description }}</p>
          
          <div class="project-features">
            <h4 class="features-title">Key Features:</h4>
            <ul class="features-list">
              <li v-for="feature in project.features" :key="feature">
                {{ feature }}
              </li>
            </ul>
          </div>
          
          <div class="project-technologies">
            <span 
              v-for="tech in project.technologies" 
              :key="tech" 
              class="tech-tag"
            >
              {{ tech }}
            </span>
          </div>
          
          <div class="project-meta">
            <span class="project-date">{{ project.date }}</span>
            <span class="project-status" :class="project.status.toLowerCase()">
              {{ project.status }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'E-Commerce Platform',
          description: 'A full-stack e-commerce solution with user authentication, payment integration, and admin dashboard. Built with modern technologies and scalable architecture.',
          image: 'https://via.placeholder.com/400x250',
          features: [
            'User registration and authentication',
            'Product catalog with search and filters',
            'Shopping cart and checkout process',
            'Payment integration with Stripe',
            'Admin dashboard for inventory management',
            'Responsive design for all devices'
          ],
          technologies: ['Vue.js', 'Node.js', 'Express', 'PostgreSQL', 'Stripe API', 'JWT'],
          liveUrl: 'https://ecommerce-demo.com',
          githubUrl: 'https://github.com/johndoe/ecommerce-platform',
          date: 'March 2024',
          status: 'Completed'
        },
        {
          id: 2,
          title: 'Task Management App',
          description: 'A collaborative task management application with real-time updates, team collaboration features, and project tracking capabilities.',
          image: 'https://via.placeholder.com/400x250',
          features: [
            'Real-time collaboration with Socket.io',
            'Drag-and-drop task management',
            'Team member invitations',
            'File attachments and comments',
            'Progress tracking and reporting',
            'Mobile-responsive interface'
          ],
          technologies: ['React', 'Socket.io', 'MongoDB', 'Express', 'AWS S3'],
          liveUrl: 'https://taskmaster-app.com',
          githubUrl: 'https://github.com/johndoe/task-management',
          date: 'January 2024',
          status: 'Completed'
        },
        {
          id: 3,
          title: 'Weather Analytics Dashboard',
          description: 'An interactive dashboard displaying weather data with charts, forecasts, and historical analysis using external APIs and data visualization libraries.',
          image: 'https://via.placeholder.com/400x250',
          features: [
            'Real-time weather data integration',
            'Interactive charts and graphs',
            'Historical weather analysis',
            'Location-based forecasts',
            'Data export functionality',
            'Customizable dashboard widgets'
          ],
          technologies: ['Vue.js', 'D3.js', 'Chart.js', 'OpenWeather API', 'Vuex'],
          liveUrl: 'https://weather-analytics.com',
          githubUrl: 'https://github.com/johndoe/weather-dashboard',
          date: 'November 2023',
          status: 'Completed'
        },
        {
          id: 4,
          title: 'AI Chat Application',
          description: 'An intelligent chat application powered by AI with natural language processing, context awareness, and multi-language support.',
          image: 'https://via.placeholder.com/400x250',
          features: [
            'AI-powered responses',
            'Context-aware conversations',
            'Multi-language support',
            'Voice message integration',
            'Chat history and search',
            'Custom AI model training'
          ],
          technologies: ['Python', 'FastAPI', 'TensorFlow', 'React', 'WebSocket'],
          liveUrl: null,
          githubUrl: 'https://github.com/johndoe/ai-chat-app',
          date: 'Ongoing',
          status: 'In Progress'
        }
      ]
    }
  }
}
</script>