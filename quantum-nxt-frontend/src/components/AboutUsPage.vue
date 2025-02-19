<script setup>
// Define team members' details for display (extendable in the future)
const teamMembers = [
  { name: 'John Doe', role: 'Founder & CEO', bio: 'Passionate about technology and innovation.', image: 'https://via.placeholder.com/150' },
  { name: 'Jane Smith', role: 'Lead Developer', bio: 'Specializes in scalable server infrastructures.', image: 'https://via.placeholder.com/150' },
  { name: 'Alice Johnson', role: 'UI/UX Designer', bio: 'Focuses on creating seamless digital experiences.', image: 'https://via.placeholder.com/150' }
];

import HeaderComponent from './HeaderComponent.vue';
</script>

<template>
  <section class="about-us-container">
    <!-- About Quantum NXT Header -->
    <div class="text-center">
      <h1 class="text-5xl font-bold text-light mb-6">About Quantum NXT</h1>
      <p class="text-lg text-primary max-w-3xl mx-auto mb-6">
        Quantum NXT, founded in the Netherlands, began as a passion project among tech enthusiasts. Over time, it has evolved into a full-scale development studio, specializing in web, mobile, and game development, as well as scalable hosting solutions.
      </p>
    </div>

    <!-- Mission Statement Section -->
    <div class="mission-section p-6 bg-secondary rounded-lg shadow-md">
      <h2 class="text-3xl font-semibold text-light mb-4">Our Mission</h2>
      <p class="text-lg text-primary">
        At Quantum NXT, we are committed to pushing the boundaries of digital innovation. Our focus lies in delivering high-performance, secure, and user-centric solutions tailored to modern technological needs.
      </p>
    </div>

    <!-- Meet the Team Section -->
    <div class="team-section mt-10">
        <h2 class="text-3xl font-semibold text-light text-center mb-6">Meet Our Team</h2>
        <div class="team-grid grid grid-cols-1 md:grid-cols-3 gap-6">
            <div v-for="member in teamMembers" :key="member.name" class="team-card">
            <div class="team-member bg-accent p-6 rounded-lg shadow-md text-center">
                <img :src="member.image" :alt="member.name" class="w-24 h-24 rounded-full mx-auto mb-4">
                <h3 class="text-xl font-semibold text-light">{{ member.name }}</h3>
                <p class="text-sm text-highlight">{{ member.role }}</p>
                <p class="text-primary mt-3">{{ member.bio }}</p>
            </div>
            </div>
        </div>
    </div>

  </section>

  <!-- Header Component -->
  <HeaderComponent/>
</template>

<style scoped>
/* Main container for the About Us section */
.about-us-container {
  margin: 0 auto;
  padding: 2rem;
  background-color: #171822;
  color: white;
  min-height: 100vh; /* Ensure the container takes up the full screen height */
  display: flex;
  flex-direction: column;
  justify-content: center; /* Vertically centers the content */
}

/* Mission statement styling */
.mission-section {
  text-align: center;
  background-color: #38458e;
  color: #9bd3e6;
  border-radius: 8px;
  padding: 2rem;
}

/* Section containing the team members */
/* Section containing the team members */
.team-section {
  text-align: center;
}

/* Team member grid layout with responsive columns */
.team-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.5rem;
}

@media (min-width: 768px) {
  .team-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* Styling for individual team member card */
.team-card {
  display: flex;
  justify-content: center; /* Center cards horizontally */
}

.team-member {
  background-color: #1e1f2f;
  color: white;
  border-radius: 12px; /* Rounded corners */
  padding: 2rem; /* More padding for card spacing */
  border: 1px solid #38458e;
  transition: transform 0.3s ease-in-out;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15); /* Slightly larger shadow for more depth */
}

/* Hover effect to lift the card */
.team-member:hover {
  transform: translateY(-8px);
}

/* Image styling */
.team-member img {
  width: 96px; /* Increased size */
  height: 96px;
  border-radius: 50%;
  margin-bottom: 1rem;
}

/* Text color classes */
.text-light {
  color: white;
}

.text-primary {
  color: #9bd3e6;
}

.text-highlight {
  color: #757575;
}

/* Background color classes */
.bg-secondary {
  background-color: #38458e;
}

.bg-accent {
  background-color: #1e1f2f;
}
</style>
