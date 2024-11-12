<template>
  <div class="app-background">
    <nav class="navbar">
      <div class="navbar-container">
        <div class="brand-name">SHKRYM</div>

        <ul class="nav-list hidden-sm-and-down">
          <li><a href="#home" class="nav-item" :class="{ pressed: activeNav === 'Home' }" @click="setActive('Home')">Home</a></li>
          <li><a href="#about" class="nav-item" :class="{ pressed: activeNav === 'About' }" @click="setActive('About')">About</a></li>
          <li><a href="#services" class="nav-item" :class="{ pressed: activeNav === 'Services' }" @click="setActive('Services')">Services</a></li>
          <li><a href="#contact" class="nav-item" :class="{ pressed: activeNav === 'Contact' }" @click="setActive('Contact')">Contact</a></li>
        </ul>

      <!-- Mobile Toggle Button -->
      <v-btn 
          icon 
          class="hidden-md-and-up" 
          @click="drawer = !drawer"
          style="transition: transform 0.3s ease-in-out;"
          @mouseover="hover = true" 
          @mouseleave="hover = false">
          <v-icon :color="hover ? 'pink' : 'white'">mdi-menu</v-icon>
        </v-btn>
      </div>
    </nav>

    <!-- Mobile Drawer -->
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
      right
      width="250"
      class="hidden-md-and-up"
      style="transition: transform 0.3s ease-in-out;"
      :style="drawer ? { transform: 'translateX(0)' } : { transform: 'translateX(100%)' }"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in links"
          :key="i"
          @click="drawer = false; setActive(item.title)"
          class="drawer-item"
        >
          <v-list-item-title class="drawer-item-title">{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container fluid class="home-container" id="home">
        <v-row>
          <v-col cols="12" md="6" class="left-column">
            <div class="content-wrapper">
              <h1 >Welcome to my Portfolio!</h1>
              <p> Dive in and get to know more about me, my Skills, and Services.</p>
            </div>
          </v-col>
     <v-col  class="right-column">
       <img :src="giphyImage" alt="Animated GIF" class="giphy-image" />
     </v-col>
        </v-row>
      </v-container>
    </v-main>
  </div>
</template>
<script>
import giphyImage from '@/assets/giphy.webp';

export default {
  name: 'PortfolioComponent',
  data() {
    return {
      drawer: false,
      activeNav: 'Home',
      giphyImage, 
      links: [
        { title: 'Home' },
        { title: 'About' },
        { title: 'Services' },
        { title: 'Contact' },
      ],
    };
  },
  methods: {
    setActive(nav) {
      this.activeNav = nav;
      if (nav === 'Home') {
        this.scrollToTop();
      }
    },
    scrollToTop() {
      const element = document.getElementById('home');
      if (element) {
        window.scrollTo({
          top: element.offsetTop - 60, // Adjust for navbar height
          behavior: "smooth",
        });
      }
    }
  }
};
</script>
<style scoped>
html {
  scroll-behavior: smooth;
}


.app-background {
  background: url('https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2xudGdnOThpbXF6MnlvaDE1ZzM0dzZlNmthNnhkd2dsbzY0MnozaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/lnfzT3k8g7wpG/giphy.gif') no-repeat center center fixed;
  background-size: cover;
  color: #fff;
  background-size: cover;
  background-position: top center;
  height: 100vh;
  padding-top: 15%; 
}
.navbar {
  background-color: rgba(255, 255, 255, 0.048);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 0 20px;
  height: 60px;
}
.brand-name {
  font-size: 24px;
  color: #ff79c6;
}
.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 1%;
}
.nav-list {
  display: flex;
  align-items: center;
  }
.nav-list li {
  list-style: none;
  margin: 0 20px;
}
.nav-list li a {
  text-decoration: none;
  color: #00e1ff;
  text-shadow: #faf3f3;
  font-weight: bold;
  padding: 10px 15px;
  transition: color 0.3s ease;
}
.nav-list li a:hover {
  color: #ff497c;
}
/* Mobile Toggle Button Effects */
.v-btn.icon {
  color: #fff;
  transition: transform 0.3s ease-in-out, color 0.3s ease-in-out;
}

.v-btn.icon:hover {
  transform: scale(1.1);
}

.v-icon {
  transition: color 0.3s ease-in-out;
}

.v-icon[color='pink'] {
  color: #ff497c; /* Pink color when hovered */
}

/* Mobile Drawer */
.v-navigation-drawer {
  background: rgba(0, 0, 0, 0.7); /* Semi-transparent dark background */
  color: #fff; /* White text for the drawer items */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Shadow for depth */
  padding-top: 60px; /* Adjust top padding to avoid covering content */
}

.drawer-item {
  transition: background-color 0.3s ease-in-out;
}

.drawer-item:hover {
  background-color: rgba(255, 79, 124, 0.2); /* Hover effect with pink color */
}

.drawer-item-title {
  font-size: 20px; /* Larger font size for better readability */
  font-weight: bold;
  color: #fff;
  padding: 10px;
}

/* Optional: Darken the drawer when opened */
.v-navigation-drawer--open {
  background-color: rgba(0, 0, 0, 0.8);
}

.home-container{
      transform: translateY(-13%);
      padding-top: 19%;
}
.left-column {
  display: flex;
  justify-content: center;
  align-items: center; 
  text-align: center;
  height: 100%;
  flex-direction: column; 
}
.content-wrapper {
  max-width: 80%;
  text-align: center;
}
.left-column h1 {
  color: #e0b3ff;
  font-size: 60px;
  font-weight: bold;
  margin-bottom: 3%;
  transform: translateY(-30px);
  text-shadow: 0 0 10px #ff79c6;
  animation: glitch 1.5s infinite;
}
.left-column p {
  color: #ebe9e9;
  font-size: 25px;
  padding-bottom: 2%;
  transform: translateY(-30px);
}
@keyframes glitch {
  0% { text-shadow: 2px 2px #ff497c, -2px -2px #7b2cbf;}
  50% {text-shadow: -2px -2px #ff497c, 2px 2px #7b2cbf;}
  100% {text-shadow: 2px -2px #ff497c, -2px 2px #7b2cbf;
  }
}
@keyframes moveGrid {
  0% {transform: translateX(0) translateY(0);}
  50% {transform: translateX(-30px) translateY(30px);}
  100% {transform: translateX(0) translateY(0);}
}
.right-column {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  margin-bottom: 100%;
  flex-direction: column;
  opacity: 0.9;
  animation: fadeIn 3s ease-in-out;
  transform: translateY(-15%);

}
.giphy-image {
  max-width: 300px; 
  max-height: 300px; 
  border-radius: 15px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
  object-fit: cover;
  animation: zoomIn 5s infinite alternate;
}
@keyframes zoomIn {
  0% {transform: scale(1);}
  100% {transform: scale(1.1);}
}
</style>