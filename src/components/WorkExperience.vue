<template>
  <div class="work-experience">
    <header class="section-header">
      <h2 class="section-title">Work Experience</h2>
      <p class="section-subtitle">My professional journey</p>
    </header>
    
    <div class="experience-timeline">
      <div 
        v-for="job in jobs" 
        :key="job.id" 
        class="experience-item"
      >
        <div class="experience-date">
          {{ job.startDate }} - {{ job.endDate }}
        </div>
        <div class="experience-content">
          <h3 class="job-title">{{ job.title }}</h3>
          <h4 class="company-name">{{ job.company }}</h4>
          <p class="job-location">{{ job.location }}</p>
          <ul class="job-responsibilities">
            <li v-for="responsibility in job.responsibilities" :key="responsibility">
              {{ responsibility }}
            </li>
          </ul>
          <div class="job-technologies">
            <span 
              v-for="tech in job.technologies" 
              :key="tech" 
              class="tech-tag"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WorkExperience',
  data() {
    return {
      jobs: [
        {
          id: 1,
          title: 'Senior Full Stack Developer',
          company: 'Tech Innovations Inc.',
          location: 'San Francisco, CA',
          startDate: 'Jan 2022',
          endDate: 'Present',
          responsibilities: [
            'Led development of microservices architecture serving 1M+ users',
            'Mentored junior developers and conducted code reviews',
            'Implemented CI/CD pipelines reducing deployment time by 60%',
            'Collaborated with product team to define technical requirements'
          ],
          technologies: ['Vue.js', 'Node.js', 'PostgreSQL', 'Docker', 'AWS']
        },
        {
          id: 2,
          title: 'Full Stack Developer',
          company: 'StartupXYZ',
          location: 'San Francisco, CA',
          startDate: 'Mar 2020',
          endDate: 'Dec 2021',
          responsibilities: [
            'Developed responsive web applications using modern frameworks',
            'Built RESTful APIs and integrated third-party services',
            'Optimized database queries improving performance by 40%',
            'Participated in agile development process and sprint planning'
          ],
          technologies: ['React', 'Express.js', 'MongoDB', 'Git', 'Heroku']
        },
        {
          id: 3,
          title: 'Junior Frontend Developer',
          company: 'Digital Agency Pro',
          location: 'San Francisco, CA',
          startDate: 'Jun 2018',
          endDate: 'Feb 2020',
          responsibilities: [
            'Created pixel-perfect UI components from design mockups',
            'Implemented responsive designs for mobile and desktop',
            'Collaborated with designers and backend developers',
            'Maintained and updated existing client websites'
          ],
          technologies: ['HTML5', 'CSS3', 'JavaScript', 'jQuery', 'Sass']
        }
      ]
    }
  }
}
</script>