<template>
    <v-main>
      <v-container fluid class="about-container" id="about">
        <v-card class="about-card" elevation="10">
          <v-row>
            <v-col cols="12" md="4" class="column d-flex flex-column align-center justify-start">
              <div class="image-frame">
                <v-avatar class="square-avatar">
                  <v-img 
                    src="@/assets/pfp.png" 
                    alt="Ayumi Shakira Asendente"
                    class="image-content"
                  />
                </v-avatar>
              </div>
              <div class="text-content">
                <h2>Ayumi Shakira Asendente</h2>
                <div class="social-icons">
                  <v-btn icon href="https://www.facebook.com/profile.php?id=100009848012195" target="_blank">
                    <v-icon color="#3b5998">mdi-facebook</v-icon>
                  </v-btn>
                  <v-btn icon href="https://www.instagram.com/shkrymi_/" target="_blank">
                    <v-icon color="#e4405f">mdi-instagram</v-icon>
                  </v-btn>
                  <v-btn icon href="https://github.com/shkrym" target="_blank">
                    <v-icon color="#333">mdi-github</v-icon>
                  </v-btn>
                </div>
              </div>
            </v-col>
            <v-col cols="12" md="4" class="column d-flex flex-column align-center justify-start">
              <div class="image-frame">
                <v-avatar class="square-avatar">
                  <v-img 
                    src="@/assets/csu.png" 
                    alt="School Logo"
                    class="image-content"
                  />
                </v-avatar>
              </div>
              <div class="text-content">
                <h3>3rd Year, Bachelor of Science in Information Technology</h3>
                <p>Butuan City, Philippines</p>
              </div>
            </v-col>
            <v-col cols="12" md="4" class="column d-flex align-center justify-center">
              <div class="column-content">
                <h4>Courses Taken:</h4>
                <v-list>
                  <v-list-item v-for="(course, index) in courses" :key="index">
                    <v-list-item-icon>
                      <v-icon color="purple">mdi-book-open-page-variant</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title>{{ course }}</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list>
              </div>
            </v-col>
          </v-row>
        </v-card>
      </v-container>
    </v-main>
  </template>
  
  <script>
  export default {
    name: 'AboutSection',
    data() {
      return {
        courses: [
          'Web Development',
          'Database Management',
          'Data Structures & Algorithms',
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .about-container {
    padding-top: 100px;
    padding-bottom: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: radial-gradient(circle, #47025c, #3f0152ee);
  }
  
  /* Card Styles */
  .about-card {
    max-width: 1200px;
    margin: auto;
    padding-top: 5%;
    padding-bottom: 5%;
    border-radius: 20px;
    background: linear-gradient(145deg, #f51eb5c9, #559de071);
  }
  .column {
    text-align: center;
  }
.image-frame {
    width: 100%;
    max-width: 200px;
    aspect-ratio: 1;
    padding: 10px;
    border: 2px solid #fbf6ff;
    border-radius: 12px;
    box-shadow: 0 0 10px rgba(2, 2, 2, 0.411);
    margin-bottom: 20px;
    position: relative;
    overflow: hidden;
  }
    .square-avatar {
    width: 100%;
    height: 100%;
    border-radius: 12px;
  }
.image-content {
    object-fit: cover; 
    object-position: center; 
    width: 100%;
    height: 100%;
    transform: none; 
  }
   .image-frame:hover {
    transform: scale(1.05);
    transition: transform 0.3s ease-in-out;
  }
 .text-content {
    color: #fff;
    flex-grow: 1;
  }
  .column-content{
    color: #050505;
  }
.social-icons {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 15px;
  }
.column h2 {
    font-size: 26px;
    color: #fff;
}
.column h3 {
    font-size: 22px;
    color: #ffffff;
    padding-bottom: 2%;
  }
  .column h4 {
    font-size: 24px;
    color: #ffffff;
    padding-bottom: 10%;
  }
    .v-list-item {
    background: rgba(255, 255, 255, 0.05);
    border-radius: 10px;
    margin: 5px 0;
  }
  </style>
  