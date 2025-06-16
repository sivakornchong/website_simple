<template>
  <div class="education">
    <header class="section-header">
      <h2 class="section-title">Education</h2>
      <p class="section-subtitle">Academic background and certifications</p>
    </header>
    
    <div class="education-container">
      <div class="education-section">
        <h3 class="subsection-title">Degrees</h3>
        <div class="education-timeline">
          <div 
            v-for="degree in degrees" 
            :key="degree.id" 
            class="education-item"
          >
            <div class="education-date">
              {{ degree.year }}
            </div>
            <div class="education-content">
              <h4 class="degree-title">{{ degree.degree }}</h4>
              <h5 class="institution-name">{{ degree.institution }}</h5>
              <p class="education-location">{{ degree.location }}</p>
              <p class="gpa" v-if="degree.gpa">GPA: {{ degree.gpa }}</p>
              <ul class="relevant-courses" v-if="degree.courses">
                <li class="courses-title">Relevant Courses:</li>
                <li v-for="course in degree.courses" :key="course">{{ course }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      
      <div class="education-section">
        <h3 class="subsection-title">Certifications</h3>
        <div class="certifications-grid">
          <div 
            v-for="cert in certifications" 
            :key="cert.id" 
            class="certification-item"
          >
            <div class="cert-header">
              <h4 class="cert-title">{{ cert.title }}</h4>
              <span class="cert-date">{{ cert.date }}</span>
            </div>
            <p class="cert-issuer">{{ cert.issuer }}</p>
            <p class="cert-id" v-if="cert.credentialId">
              Credential ID: {{ cert.credentialId }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Education',
  data() {
    return {
      degrees: [
        {
          id: 1,
          degree: 'Bachelor of Science in Computer Science',
          institution: 'University of California, Berkeley',
          location: 'Berkeley, CA',
          year: '2014 - 2018',
          gpa: '3.8/4.0',
          courses: [
            'Data Structures and Algorithms',
            'Database Systems',
            'Web Development',
            'Software Engineering',
            'Computer Networks'
          ]
        },
        {
          id: 2,
          degree: 'Associate Degree in Web Development',
          institution: 'Community College of San Francisco',
          location: 'San Francisco, CA',
          year: '2012 - 2014',
          gpa: '3.9/4.0',
          courses: [
            'HTML/CSS Fundamentals',
            'JavaScript Programming',
            'Responsive Design',
            'UI/UX Design Principles'
          ]
        }
      ],
      certifications: [
        {
          id: 1,
          title: 'AWS Certified Solutions Architect',
          issuer: 'Amazon Web Services',
          date: 'March 2023',
          credentialId: 'AWS-SA-123456'
        },
        {
          id: 2,
          title: 'Google Analytics Certified',
          issuer: 'Google',
          date: 'January 2023',
          credentialId: 'GA-CERT-789012'
        },
        {
          id: 3,
          title: 'Certified Scrum Master',
          issuer: 'Scrum Alliance',
          date: 'November 2022',
          credentialId: 'CSM-345678'
        },
        {
          id: 4,
          title: 'MongoDB Developer Certification',
          issuer: 'MongoDB Inc.',
          date: 'September 2022',
          credentialId: 'MONGO-DEV-901234'
        }
      ]
    }
  }
}
</script>