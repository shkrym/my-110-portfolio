<template>
    <v-container fluid class="my-services-container" id="services">
      <!-- Services Row -->
      <v-row class="services-row" justify="center" align="center" no-gutters>
  <v-col
    v-for="(service, index) in services"
    :key="index"
    cols="12" sm="8" md="6" lg="3"
    class="d-flex justify-center align-center"
  >
    <v-card class="service-card" elevation="2" outlined>
      <v-card-title class="service-card-title">
        <v-icon class="service-icon">{{ service.icon }}</v-icon>
        <div class="service-title">{{ service.title }}</div>
      </v-card-title>
      <v-card-subtitle class="service-description">{{ service.description }}</v-card-subtitle>
    </v-card>
  </v-col>
</v-row>

      <div class="service-intro">
        <h2 class="service-intro-title">Services</h2>
        <p class="service-intro-description">
            Offering services to meet your needs: from web development and database management to 
            UI/UX design and branding. Let me help you bring your vision to life with solutions, 
            creative expertise, and technologies.</p>
      </div>
    </v-container>
  </template>
  
  <script>
  export default {
    name: "MyServicesSection",
    data() {
      return {
        services: [
          {
            title: "Web Development",
            description: "Creating dynamic, responsive websites using modern technologies.",
            icon: "mdi-web"
          },
          {
            title: "Database Management",
            description: "Design and manage efficient and scalable databases for your business.",
            icon: "mdi-database"
          },
          {
            title: "UI/UX Design",
            description: "Crafting intuitive and user-friendly interfaces with a focus on user experience.",
            icon: "mdi-format-paint"
          },
          {
            title: "Logo & Branding",
            description: "Designing unique and memorable logos that represent your brand.",
            icon: "mdi-palette"
          }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
.my-services-container {
  background: radial-gradient(circle, #df05c2d2, #0b4085b6);
  padding-top: 10%;
  padding-bottom: 10%;
}
.services-row {
  display: flex;
  justify-content: center;
  align-items: center;
}
.service-card {
  width: 100%;
  max-width: 300px;
  min-height: 230px;
  border-radius: 12px;
  background: radial-gradient(circle, #47025c, #3f0152ee);
  color: white;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
  text-align: center;
  padding-top: 10%;
  overflow: visible; 
}
.service-card:hover {
  transform: scale(1.05);
}
.service-icon {
  font-size: 2.5rem;
  color: #5480f8;
  margin-bottom: 10px;
}
.service-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #ffffff;
}
.service-description {
  font-size: 0.9rem;
  color: #e0e0e0;
  padding: 0 10px;
  white-space: normal; 
  overflow: visible; 
}
.service-intro {
  text-align: center;
  margin-top: 50px;
}
.service-intro-title {
  font-size: 1.8rem;
  font-weight: bold;
  color: #f0eded;
}
.service-intro-description {
  font-size: 1rem;
  color: #fffefe;
  max-width: 600px;
  margin: 10px auto 0;
}
@media (max-width: 1200px) {
  .service-card {
    max-width: 260px;
    min-height: 220px;
  }
}
@media (max-width: 768px) {
  .service-card {
    max-width: 220px;
    min-height: 200px;
  }
  .services-row {
    flex-wrap: wrap;
  }
}
  </style>