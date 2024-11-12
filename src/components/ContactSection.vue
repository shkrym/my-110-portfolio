<template>
    <div id="contact">
      <!-- Upper Part: Full-width frame with padding and height of 1/4 screen -->
      <v-container fluid class="contact-container">
        <v-row>
          <v-col cols="12">
            <div class="contact-frame">
              <h1 class="contact-header">Ready to bring your ideas to life?  </h1>
            </div>
          </v-col>
        </v-row>
  
        <!-- Lower Part: Social Media, Number, and Address -->
        <v-row>
          <v-col cols="12" md="4" class="contact-info">
            <h3>Get in touch with:</h3>
            <v-btn href="https://www.facebook.com/profile.php?id=100009848012195" target="_blank" class="social-btn">Facebook</v-btn>
            <v-btn href="https://github.com/shkrym" target="_blank" class="social-btn">Github</v-btn>
            <v-btn href="https://www.instagram.com/shkrymi_/" target="_blank" class="social-btn">Instagram</v-btn>
          </v-col>
          <v-col cols="12" md="4" class="contact-info">
            <h3>Cellphone Number</h3>
            <p>09363256015</p>
          </v-col>
          <v-col cols="12" md="4" class="contact-info">
            <h3>Address</h3>
            <p> Butuan City,  Philippines </p>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>
  
  
  <script>
  export default {
    name: 'ContactSection',
  };
  </script>
  
  <style scoped>
  /* Container for the contact section */
  .contact-container {
    padding: 0;
    background: radial-gradient(circle, #7e1166, #3f0152ee);

  }
  
  /* Frame for the upper part of the contact section */
  .contact-frame {
    background-color: #7b2cbf; /* You can change this color */
    background-image: url('@/assets/image.png'); /* Replace with your image path */
    background-size: cover; /* Ensures the image covers the entire frame */
    background-position: center center; /* Centers the background image */
    color: white;
    width:90%;
    height: 30vh; 
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 6%;
    margin-top: 10%;
    margin-bottom: 10%;
    border-radius: 10px; /* Optional rounded corners */
  }
  
  /* Header inside the frame */
  .contact-header {
    font-size: 36px;
    font-weight: bold;
    text-align: center;
    text-shadow: 0 0 20px rgb(253, 5, 199);
 
  }
  
  /* Styling for the contact info section */
 
  .contact-info {
    text-align: center;
    padding-bottom: 5%;
    color: antiquewhite;
    transform: translateY(-50px);
}
  
  .contact-info h3 {
    font-size: 24px;
    margin-bottom: 25px;
    font-weight: bold;
  }
  
  /* Social media buttons */
  .social-btn {
    background-color: #ff79c6; /* Social media button color */
    color: white;
    margin-right: 1%;  
    margin-left: 2%; 
    font-weight: bold;
  }
  
  .social-btn:hover {
    background-color: #7b2cbf; /* Hover effect for buttons */
  }
  
  /* Responsive adjustments */
  @media (max-width: 600px) {
    .contact-frame {
      height: 30vh; /* Adjust frame height for smaller screens */
    }
  }
  </style>
  
  