<template>
  <div id="section1" class="menu-icon" onclick="toggleNav()">☰</div>
<div class="sliding-nav" id="slidingNav">
  <a href="#section2">ACADS</a>
  <a href="#section3">INTERESTS</a>
  <a href="javascript:void(0)" onclick="toggleNav()">Close</a>
</div>

    <div class="socials">
      <p>Add me on my socials!</p>
      <div class="social-icons">
        <a href="https://www.linkedin.com/in/jenine-dulay-b9988b284/" target="_blank">
          <img src="/images/linkedin-icon.png" alt="LinkedIn" />
        </a>
        <a href="https://www.instagram.com/elneeeeee/" target="_blank">
          <img src="/images/ig-icon.png" alt="Instagram" />
        </a>
        <a href="https://open.spotify.com/user/parkjimin3389?si=17e0114fba8641b8" target="_blank">
          <img src="/images/spotify-icon.png" alt="Spotify" />
        </a>
      </div>
    </div>
  </div>

  <div id="section2">
    <div class="education-wrapper">
      <img src="/images/intro.png" alt="intro" class="education-image" />
      <div class="education-container">
        <h2>EDUCATION & ACHIEVEMENTS</h2>
        <div class="school">
          <h3>Immaculate Heart of Mary College (2018-2023)</h3>
          <ul>
            <li>Junior High - Senior High (STEM Strand)</li>
            <li>Graduated Junior High with Honors</li>
            <li>Graduated Senior High with Honors</li>
            <li>STEM SOCIETY Organization Member</li>
          </ul>
        </div>
        <div class="school">
          <h3>Asia Pacific College (2023-PRESENT)</h3>
          <ul>
            <li>BSIT-MI</li>
            <li>1st Year of College - Honors</li>
            <li>Cinemasoma Member</li>
            <li>Flickers Photo Society Member</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

<div id="section3" class="container">
  <div id="experience">
    <h2 class="center">IT EXPERIENCE</h2>
    <div class="two-columns">
      <ul>
        <li>☆ Basic Java</li>
        <li>☆ Basic Python</li>
        <li>☆ Basic HTML, CSS, Javascript</li>
        <li>☆ UI/UX Experience (Website and mobile: RamQuest - Group Project)</li>
        <li>☆ Mobile Application (RESCUE app - Group Project)</li>
        <li>☆ MySQL</li>
      </ul>
      <img src="/images/it-exp.png" alt="IT Projects">
    </div>
  </div>

  <div id="hobbies-and-goals" class="container two-columns">
    <div id="hobbies">
      <h2 class="center">Hobbies & Interests</h2>
      <ul>
        <li>☆ Music (1D, Chappell Roan, Olivia Rodrigo, SZA)</li>
        <li>☆ Films (Beautiful Boy, Challengers, Pitch Perfect Trilogy)</li>
        <li>☆ Shows (Bojack Horseman, Grey’s Anatomy, The Bear)</li>
        <li>☆ Video Games (Life is Strange, The Last of Us, Valorant)</li>
        <li>☆ Photography</li>
        <li>☆ F1</li>
      </ul>
    </div>
    <div id="goals">
      <h2 class="center">Goals & Dreams</h2>
    <ul>
        <li>☆  To live on my own and give back to my siblings</li>
        <li>☆  To meet my favorite artists</li>
        <li>☆  Graduate college with Honors</li>
        <li>☆  Learn to play the piano</li>
        <li>☆  Find a stable job that I enjoy</li>
        <li>☆  Travel to Europe (and around the world)</li>
        <li>☆  To live near a beach</li>
    </ul>

    </div>
  </div>
</div>

  <div id="section4">
    <div class="carousel-container">
      <div class="carousel">
        <img v-for="(image, index) in images" :key="index" :src="image" :alt="'Image ' + (index + 1)" :class="{ active: index === currentIndex }">
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      images: [
        "/images/gallery1.jpg",
        "/images/gallery2.jpg",
        "/images/gallery3.jpg",
        "/images/gallery4.jpg",
        "/images/gallery5.jpg",
        "/images/gallery6.jpg",
        "/images/gallery7.jpg",
        "/images/gallery8.jpg",
        "/images/gallery9.jpg"
      ],
      currentIndex: 0
    };
  },
  mounted() {
    setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    }, 3000); // 3 seconds per slide
  }
};

function toggleNav() {
  const nav = document.getElementById('slidingNav');
  nav.classList.toggle('open');
}

</script>

<style>
/* Global Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  text-align: center;
  overflow-x: hidden;
  padding-top: 80px;
}

/* Navigation Bar */
.navbar {
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding: 20px 50px;
  font-size: 28px;
  font-weight: bold;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  background: #562123;
}

.navbar a {
  color: #f8f7f2;
  text-decoration: none;
}

/* Sections */
#section1, #section2, #section3, #section5 {
  width: 100%;
  height: 100vh;
  background-size: cover;
  background-position: center;
}

#section1 {
  background-image: url('/images/bg1.png');
  margin-top: -5px; 
}

#section2 {
  background-image: url('/images/bg2.png');
}

#section3 {
  background-image: url('/images/bgd3.png');
}

#section4 {
  background-image: url('/images/bg4.png');
  background-size: cover; /* Ensures the image covers the entire section */
  background-position: center; /* Centers the image */
  background-repeat: no-repeat; /* Prevents tiling */
  width: 100%; /* Ensures full width */
  min-height: 100vh; /* Ensures it fills the full height of the viewport */
}


#section5 {
  background-color: #f8f7f2;
}

/* Social Media */
.socials {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  text-align: center;
}

.socials p {
  font-style: italic;
  margin-bottom: 10px;
  color: white;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 15px;
}

.social-icons a img {
  width: 40px;
  height: 40px;
  filter: brightness(0) invert(1);
}

/* Education */
.education-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 55%;
    margin: 0 auto;
}

.education-image {
    width: 60%;
    max-width: 500px;
    height: auto;
    object-fit: cover;
    border-radius: 10px;
}

#section2 img {
    max-width: 80%;
    max-height: 500px;
    height: auto;
    object-fit: contain;
}

.education-container {
    background-color: #f8f7f2;
    color: black;
    padding: 20px;
    border-radius: 10px;
    width: 100%;
    margin-top: 7px;
    border-radius: 30px;
}

.education-container .school {
    margin-bottom: 20px;
}


.education-container h2 {
  margin-bottom: 20px; /* Adjust as needed */
  color: #562123;
}


.education-container .school h3 {
    font-size: 20px;
    margin-bottom: 10px;
}

.education-container .school ul {
    list-style-type: none;
    padding-left: 0;
    text-align: center;
}

.education-container .school ul li {
    margin-bottom: 5px;
}

.education-container .school ul li:last-child {
    margin-bottom: 50px; /* Adjust the value as needed */
}


/* IT Experience */
#section3 #experience {
  margin-bottom: 20px;
  border: 2px solid #562123;
  padding: 20px;
  border-radius: 30px;
}

#section3 #experience .two-columns {
  display: flex;
  gap: 20px;
  justify-content: space-between;
  align-items: center;
}

#section3 #experience img {
  max-width: 300px;
  border-radius: 8px;
}

#section3 #experience {
  margin: 20px auto; /* Centers it horizontally */
  padding: 20px;
  border: 2px solid #562123;
  border-radius: 30px;
  width: 80%; /* Adjust width as needed */
}

#experience ul {
  margin-left: 70px;
}

#experience ul li,  {
  margin-bottom: 10px; /* Space between each list item */
}

#section3 #experience h2 {
  color: #562123;
}


/* Hobbies and Goals */
#hobbies-and-goals {
  display: flex;
  flex-direction: row; /* Ensures they are side by side */
  justify-content: space-between;
  gap: 20px;
  width: 83%;
  padding: 20px;
  box-sizing: border-box;
  margin: 0 auto;
  height: auto;
  max-height: 350px;
}

#hobbies, #goals {
  flex: 1; /* Ensures equal width */
  background-color: #562123;
  color: #f8f7f2;
  border-radius: 30px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column; /* Makes the inner content stack */
  padding: 20px 20px 10px; 
  padding-bottom: 0;
}

#hobbies h2.center, #goals h2.center {
  text-align: center;
}

#experience ul,
#hobbies ul,
#goals ul,
.education-container ul {
  list-style: none; 
  text-align: left;
}

#hobbies h2.center, 
#goals h2.center {
  margin-bottom: 15px; /* Space between header and list */
}

#hobbies ul, 
#goals ul {
  padding-left: 0; /* Remove default padding */
  margin-top: 10px; /* Additional space between the header and the list */
  margin-left: 40px; 
  margin-bottom: 0; /* Remove extra bottom space */
  padding-bottom: 0; /* Ensure no extra padding */
}

#hobbies ul li, 
#goals ul li {
  margin-bottom: 10px; /* Space between each list item */
}

/* Section 4 Styles */
#section4 {
  text-align: center;
  padding: 40px 0;
  background-color: #f8f7f2;
}


.carousel-container {
  width: 80%;
  max-width: 600px;
  margin: 0 auto;
  overflow: hidden;
  position: relative;
  border-radius: 2px;
  margin-top: 80px;
}

.carousel {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel img {
  width: 100%;
  height: auto;
  display: none;
}

.carousel img.active {
  display: block;
}

/* Mobile and Tablet View */
@media (max-width: 768px) {
  .navbar {
    display: none; /* Hide default navbar */
  }

  .sliding-nav {
    display: block;
    position: fixed;
    top: 0;
    left: -250px; /* Initially hidden */
    width: 250px;
    height: 100%;
    background-color: #562123;
    z-index: 1001;
    overflow-x: hidden;
    transition: 0.5s ease-in-out;
  }

  .sliding-nav a {
    display: block;
    color: #f8f7f2;
    padding: 10px 15px;
    text-decoration: none;
  }

  .sliding-nav a:hover {
    background: #774246;
  }

  .sliding-nav.open {
    left: 0; /* Slide-in */
  }

  .menu-icon {
    display: block;
    position: fixed;
    top: 10px;
    left: 10px;
    z-index: 1002;
    font-size: 30px;
    cursor: pointer;
    color: #f8f7f2;
  }

  .education-container,
  #experience,
  #hobbies-and-goals {
    width: 90%; /* Adjust sections for better fit */
    margin: 10px auto; /* Add spacing */
  }

  .carousel-container {
    width: 90%; /* Ensure the carousel fits smaller screens */
  }
}

</style>
