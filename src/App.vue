<style scoped>
@keyframes spin-slow {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
.animate-spin-slow {
  animation: spin-slow 12s linear infinite;
}
@keyframes fade-slide {
  0% { opacity: 0; transform: translateY(20px); }
  100% { opacity: 1; transform: translateY(0); }
}
.animate-fade-slide {
  animation: fade-slide 1s ease-out forwards;
}
@keyframes gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
.bg-animated {
  background: linear-gradient(270deg, #F0F0F0,#f4cba5);
  background-size: 600% 600%;
  animation: gradient 20s ease infinite;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
<template>
  <div class="banner-1 bg-animated">
    <!-- NavBar -->
    <nav
      class="container px-6 mx-auto md:flex md:justify-between md:items-center"
    >
      <div class="flex items-center justify-between">
        <div class="relative w-16 h-16">
       <h2 style="font-size: 40px !important;font-weight: 600;"><span style="color: orange;">{</span><span style="color:#0066A1">AP</span><span style="color: orange;">}</span></h2>
        </div>
        <!-- Mobile menu button -->
        <div @click="showMenu = !showMenu" class="flex md:hidden">
          <button
            type="button"
            class="text-gray-800 hover:text-gray-400 focus:outline-none focus:text-gray-400"
          >
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>
      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul
        :class="showMenu ? 'flex' : 'hidden'"
        class="flex-col items-end mt-8 space-y-4 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
      >
        <li class="menu-button"><a href="#">Home</a></li>
        <li class="menu-button"><a href="#work" v-smooth-scroll>Works</a></li>
        <li class="menu-button">
          <a href="#testimonial" v-smooth-scroll>Testimonials</a>
        </li>
        <li class="menu-button"><a href="#about" v-smooth-scroll>About</a></li>
      </ul>
    </nav>
<!--Start of Modals-->
<div 
  v-if="showModal" 
  class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
>
  <div class="bg-[#41B883] rounded-2xl shadow-xl p-6 max-w-lg w-full relative text-white">
    <!-- Close Button -->
    <button 
      @click="showModal = false" 
      class="absolute top-3 right-3 text-white hover:text-gray-200"
    >
      ✕
    </button>

    <!-- Modal Content -->
    <h2 class="text-2xl font-bold mb-4">My Vue Experience</h2>
    <p class="leading-relaxed">
      I craft scalable and modern frontend applications powered by Vue.js — from seamless API integrations to efficient state management with Pinia, and reusable component-driven designs.

      Currently, I’m also pursuing a Vue.js Mid-Level Certification, sharpening my expertise to deliver even more powerful, maintainable, and user-friendly solutions.
    </p>
  </div>
</div>

<div 
      v-if="showLaravelModal" 
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div class="bg-red-600 rounded-2xl shadow-xl p-6 max-w-lg w-full relative text-white">
        <!-- Close Button -->
        <button 
          @click="showLaravelModal = false" 
          class="absolute top-3 right-3 text-white hover:text-gray-200"
        >
          ✕
        </button>

        <!-- Modal Content -->
        <h2 class="text-2xl font-bold mb-4">My Laravel Experience</h2>
        <p class="leading-relaxed">
I have been developing robust web systems with Laravel for over half a decade, building scalable, secure, and maintainable applications.  
          From database design to RESTful APIs and server-side logic, I focus on delivering reliable solutions.  
          I also integrate Laravel with modern frontend frameworks to create full-stack, high-performance applications that meet real-world needs. 
        </p>
      </div>
    </div>

  <div 
      v-if="showPythonModal" 
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div class="bg-yellow-500 rounded-2xl shadow-xl p-6 max-w-lg w-full relative text-white">
        <!-- Close Button -->
        <button 
          @click="showPythonModal = false" 
          class="absolute top-3 right-3 text-white hover:text-gray-200"
        >
          ✕
        </button>

        <!-- Modal Content -->
        <h2 class="text-2xl font-bold mb-4">My Python Experience & Certifications</h2>
        <p class="leading-relaxed mb-4">
          I have experience developing software solutions with Python, building backend services, scripts, and data-driven applications.  
  Python allows me to tackle complex problems, automate workflows, and integrate systems seamlessly.  
  To further my knowledge and validate my skills, I have obtained the Python Certified Associate in Programming and Python Certified Entry-Level Programmer certifications.
        </p>

        <!-- Badges -->
        <div class="flex space-x-4 mt-4">
          <img src="./assets/pcep.png" alt="Python Certification 1" class="w-16 h-16" />
          <img src="./assets/pcap.png" alt="Python Certification 2" class="w-16 h-16" />
        </div>
      </div>
    </div>

        <div 
      v-if="showWordPressModal" 
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div class="bg-blue-700 rounded-2xl shadow-xl p-6 max-w-lg w-full relative text-white">
        <!-- Close Button -->
        <button 
          @click="showWordPressModal = false" 
          class="absolute top-3 right-3 text-white hover:text-gray-200"
        >
          ✕
        </button>

        <!-- Modal Content -->
        <h2 class="text-2xl font-bold mb-4">My WordPress Experience</h2>
        <p class="leading-relaxed mb-4">
          I have experience developing dynamic and responsive websites with WordPress, creating custom plugins, and optimizing sites for performance and security.  
          I specialize in building user-friendly, scalable solutions that meet client needs and integrate modern web technologies.  
          To strengthen my expertise, I continually explore advanced WordPress development techniques and best practices.
        </p>

      
        
      </div>
    </div>
        <!-- JavaScript Modal -->
    <div 
      v-if="showJsModal" 
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div class="bg-yellow-500 rounded-2xl shadow-xl p-6 max-w-2xl w-full relative text-white">
        <!-- Close Button -->
        <button 
          @click="showJsModal = false" 
          class="absolute top-3 right-3 text-white hover:text-gray-200"
        >
          ✕
        </button>

        <!-- Modal Content -->
        <h2 class="text-2xl font-bold mb-4">My JavaScript Journey</h2>
        <p class="leading-relaxed mb-4">
          My love for JavaScript has driven me to develop dynamic, interactive web applications.  
          This passion has also inspired me to advance further into Vue.js, mastering modern frontend techniques and component-driven development.  
          I focus on writing clean, efficient code to build scalable and maintainable applications.
        </p>

        <!-- Certification Badge -->
        <div class="flex justify-center mt-6">
          <img 
            src="./assets/javascriptcertification.jpg" 
            alt="JavaScript Certification" 
            class="max-w-full h-auto rounded-lg shadow-lg"
          />
        </div>
      </div>
    </div>
<!--End of Modals-->

    <div class="flex items-center">
      <div class="w-11/12 space-y-5 md:space-y-10">
      
        <h1
          class="3xl:text-13xl 2xl:text-5xl xl:text-9xl lg:text-8xl md:text-3xl sm:text-3xl text-xl font-Eczar font-bold leading-tight text-gray-700 animate-fade-slide"
        >
      👋 Hi, I’m
          <a
            href="https://www.linkedin.com/"
            target="_blank"
            class="text-black hover:underline"
          >
            Anzathu Pindani</a
          ><br />Frontend Focused. WordPress Ready. Software Driven.
        </h1>

        <div class="md:flex gap-1 md:gap-10">
          <button class="text-white bg-gray-800 submit-button hidden md:block" style="background-color: #0066A1;">
            View My CV
          </button>
          <button
            class="text-orange-600   submit-button mb-5 md:mb-0" style="border: 2.5px solid orangered;"
          >
            Contact Me
          </button>
        </div>
      </div>

<div class="relative w-8/12 flex justify-center items-center">
    <!-- Profile Image -->
    <img
      class="3xl:h-[800px] 2xl:h-[650px] xl:h-[550px] lg:h-[550px] md:h-[450px] sm:h-[350px] rounded-full "
      src="./assets/heroimage.jpg"
      alt="user image"
    />

    <!-- Floating Tech Logos -->
    <img src="./assets/vue.png" 
         class="absolute top-10 left-20 w-14 animate-pulse cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12" 
         @click="showModal = true"
         alt="Vue" />

    <img src="./assets/js.png" 
         class="absolute top-20 right-10 w-12 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12" 
         @click="showJsModal = true"
         alt="JavaScript" />

    <img src="./assets/laravel.svg" 
         class="absolute bottom-10 left-10 w-14 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12" 
         alt="Laravel" @click="showLaravelModal = true"
 />

    <img src="./assets/python.svg" 
         class="absolute bottom-5 right-20 w-14 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12" 
          @click="showPythonModal = true"
         alt="Python" />

    <img src="./assets/wordpress.png" 
         class="absolute top-1/2 right-3 transform -translate-y-1/2 w-14 cursor-pointer  transition duration-300 hover:scale-125 hover:rotate-12" 
        @click="showWordPressModal = true"
         alt="WordPress" />
  </div>
    </div>
  </div>

<div class="banner-2 space-y-10 pb-20" id="work">
  <h3 class="text-white my-5 md:text-5xl text-xl  font-bold font-work_sans tracking-wide px-6 md:px-20">
    My Recent Work
  </h3>

  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 px-6 md:px-20">

    <!-- Large card (spans 2 cols) -->
    <div class="relative group overflow-hidden rounded-2xl shadow-xl sm:col-span-2">
      <img
        src="./assets/castel.png"
        alt="Project 1"
        class="w-full h-96 object-cover transform transition duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
       <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg">
          View More
        </button>
      </div>
      <div class="p-5 bg-gray-900 text-white">
        <h4 class="font-bold text-2xl">Castel Website</h4>
        <p class="text-sm mt-2">Contributed to the development of Castel’s corporate website.</p>
      </div>
    </div>

    <!-- Vertical card -->
    <div class="relative group overflow-hidden rounded-2xl shadow-xl row-span-2">
      <img
        src="./assets/egghunt.jpg"
        alt="Project 2"
        class="w-full h-full object-cover transform transition duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
      <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg">
          View More
        </button>
      </div>
      <div class="p-5 bg-gray-900 text-white">
        <h4 class="font-bold text-2xl">Project Two</h4>
        <p class="text-sm mt-2">Creative dashboard design with unique interactions.</p>
      </div>
    </div>

    <!-- Medium card -->
    <div class="relative group overflow-hidden rounded-2xl shadow-xl">
      <img
        src="./assets/bhs.png"
        alt="Project 3"
        class="w-full h-64 object-cover transform transition duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
       <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg">
          View More
        </button>
      </div>
      <div class="p-5 bg-gray-900 text-white">
        <h4 class="font-bold text-2xl">Blantyre Hotel</h4>
        <p class="text-sm mt-2">Mobile-first design</p>
      </div>
    </div>

    <!-- Wide card -->
    <div class="relative group overflow-hidden rounded-2xl shadow-xl sm:col-span-2">
      <img
        src="./assets/appic.png"
        alt="Project 4"
        class="w-full h-72 object-cover transform transition duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
        <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg">
          View More
        </button>
      </div>
      <div class="p-5 bg-gray-900 text-white">
        <h4 class="font-bold text-2xl">Appic</h4>
        <p class="text-sm mt-2">A portfolio website exploring clean design and responsive layouts</p>
      </div>
    </div>

    <!-- Square card -->
    <div class="relative group overflow-hidden rounded-2xl shadow-xl">
      <img
        src="./assets/fhs.png"
        alt="Project 5"
        class="w-full h-72 object-cover transform transition duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
       <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg">
          View More
        </button>
      </div>
      <div class="p-5 bg-gray-900 text-white">
        <h4 class="font-bold text-2xl">FHS</h4>
        <p class="text-sm mt-2">Contributed to FHS frontend in Vue.</p>
      </div>
    </div>

  </div>
 




</div>
<section id="certifications" class="banner-2 mt-2 py-20 bg-gray-900 text-white">
         <h3 class="text-4xl md:text-5xl font-bold mb-12  text-[#fff] px-6 md:px-20">My Achievements: Certifications & Awards</h3>
 <div class="container mx-auto px-6 md:px-10 grid grid-cols-1 md:grid-cols-2 gap-0">

      <!-- LEFT: Timeline -->
      <div class="relative">
        <!-- Vertical line -->
        <div class="absolute left-6 md:left-1/2 transform md:-translate-x-1/2 h-full border-l-2 border-[#c17111]"></div>

        <div
          v-for="(cert, index) in certifications"
          :key="index"
          @click="selectedCert = cert"
          class="mb-16 relative pl-16 md:pl-0 md:w-3/4 md:mx-auto cursor-pointer group"
        >
          <!-- Icon -->
          <div
            class="absolute left-0 md:left-1/2 transform -translate-x-1/2 w-12 h-12 flex items-center justify-center  group-hover:scale-110 transition"
          >
        
            <img :src="cert.icon" :alt="cert.title" class="h-10" />
          </div>
          <!-- Title -->
          <div class="mt-2">
            <p class="text-xl font-bold">{{ cert.title }}</p>
            <p class="text-sm text-gray-300">{{ cert.issuer }}</p>
          </div>
        </div>
      </div>

      <!-- RIGHT: Certificate Preview -->
      <div class="flex items-center justify-center">
        <transition name="fade">
          <img
            v-if="selectedCert"
            :src="selectedCert.image"
            :alt="selectedCert.title"
            class="rounded-lg shadow-2xl max-h-[500px] object-contain"
          />
        </transition>
      </div>
    </div>
</section>

<section id="work-process" class="banner-1 text-gray  bg-gray-900">
  <div class="container mx-auto px-6 md:px-20 md:py-20  text-left space-y-10">
    <!-- Section Title -->
    <h3 class="text-4xl md:text-5xl font-bold tracking-wide">My Work Process</h3>

    <!-- Slider Container -->
    <div class="flex  snap-x snap-mandatory space-x-6 py-10">

      <!-- Slide 1: Research -->
      <div class="snap-start flex-shrink-0  w-80  rounded-2xl  overflow-hidden hover:scale-105 transform transition duration-500">
        <img src="./assets/1191.jpg" alt="Research" class=" object-cover">
        <div class="p-6 ">
          <h4 class="text-2xl font-bold mb-2">1. Research & Discovery</h4>
          <p class="text-sm">Understand client needs, audience, and project goals to plan effectively.</p>
        </div>
      </div>

      <!-- Slide 2: Planning (shifted down for zig-zag) -->
      <div class="snap-start flex-shrink-0 w-80 rounded-2xl relative top-20  overflow-hidden hover:scale-105 transform transition duration-500">
        <img src="./assets/15943.jpg" alt="Planning" class="w-full object-cover">
        <div class="p-6 ">
          <h4 class="text-2xl font-bold mb-2">2. Planning & Strategy</h4>
          <p class="text-sm">Define sitemaps, user flows, and timelines for smooth project execution.</p>
        </div>
      </div>

      <!-- Slide 3: Design & Development -->
      <div class="snap-start flex-shrink-0 rounded-2xl w-80 overflow-hidden hover:scale-105 transform transition duration-500">
        <img src="./assets/2150104489.jpg" alt="Design & Development" class=" object-cover">
        <div class="p-6">
          <h4 class="text-2xl font-bold mb-2">3. Design & Development</h4>
          <p class="text-sm">Wireframes, mockups, and coding functional responsive websites with Vue or Laravel.</p>
        </div>
      </div>

      <!-- Slide 4: Testing & Launch (shifted down for zig-zag) -->
      <div class="snap-start flex-shrink-0 w-80 relative top-20  rounded-2xl  overflow-hidden hover:scale-105 transform transition duration-500">
        <img src="./assets/123880.jpg" alt="Testing" class=" object-cover">
        <div class="p-6 ">
          <h4 class="text-2xl font-bold mb-2">4. Testing & Launch</h4>
          <p class="text-sm">QA, bug fixes, and deployment for a smooth and successful launch.</p>
        </div>
      </div>

    </div>

    <!-- Optional: Add navigation dots or arrows here -->

  </div>
</section>




  

  <div class="banner-2 md:flex text-white items-center md:pt-10  md:justify-evenly" id="about">
    <img
      class="md:h-[500px] h-[400px]"
      src="./assets/top-view-man-using-his-laptop.png"
      alt="user image"
    />
    <div class="space-y-5 py-8 px-5 md:py-10 md:px-10 md:w-1/2">

<p class="font-work_sans text-lg leading-relaxed">
  I’m Anzathu Pindani, a Senior Software Developer from Malawi specializing in Vue.js, Laravel, and WordPress. 
  I build intuitive, responsive applications and am currently pursuing a Master’s in Informatics. 
  Outside of coding, I enjoy UI/UX exploration, side projects, reading, puzzles, wrestling, movies, and traveling.
</p>



    </div>
  </div>

  <div class="banner-1 flex h-full items-center">
    <div class="w-7/12 p-12">
      <h2 class="text-gray-700 md:text-6xl text-2xl font-Eczar mb-5 font-bold">
   Let’s build experiences that are both delightful and highly functional.
      </h2>
      <a class="underline text-2xl text-blue-600 font-work_sans"
        >📧 anzathupindani286@gmail.com</a
      >
    </div>
    <div class="w-5/12 pr-28">
      <div class="flex flex-wrap justify-end gap-2">
        <button
          class="bg-gray-700 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded"
        >
          <svg
            class="w-4 h-4 md:w-10 md:h-10 lg:w-10 lg:h-10 xl:h-10 xl:w-10 fill-current"
            role="img"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
          >
            <path
              d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
            />
          </svg>
        </button>

        <button
          class="bg-gray-700 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded"
        >
          <svg
            class="w-4 h-4 md:w-10 md:h-10 lg:w-10 lg:h-10 xl:h-10 xl:w-10 fill-current"
            role="img"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
          >
            <path
              d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"
            />
          </svg>
        </button>

        <button
          class="bg-gray-700 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded"
        >
          <svg
            class="w-4 h-4 md:w-10 md:h-10 lg:w-10 lg:h-10 xl:h-10 xl:w-10 fill-current"
            role="img"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M12 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0zm5.01 4.744c.688 0 1.25.561 1.25 1.249a1.25 1.25 0 0 1-2.498.056l-2.597-.547-.8 3.747c1.824.07 3.48.632 4.674 1.488.308-.309.73-.491 1.207-.491.968 0 1.754.786 1.754 1.754 0 .716-.435 1.333-1.01 1.614a3.111 3.111 0 0 1 .042.52c0 2.694-3.13 4.87-7.004 4.87-3.874 0-7.004-2.176-7.004-4.87 0-.183.015-.366.043-.534A1.748 1.748 0 0 1 4.028 12c0-.968.786-1.754 1.754-1.754.463 0 .898.196 1.207.49 1.207-.883 2.878-1.43 4.744-1.487l.885-4.182a.342.342 0 0 1 .14-.197.35.35 0 0 1 .238-.042l2.906.617a1.214 1.214 0 0 1 1.108-.701zM9.25 12C8.561 12 8 12.562 8 13.25c0 .687.561 1.248 1.25 1.248.687 0 1.248-.561 1.248-1.249 0-.688-.561-1.249-1.249-1.249zm5.5 0c-.687 0-1.248.561-1.248 1.25 0 .687.561 1.248 1.249 1.248.688 0 1.249-.561 1.249-1.249 0-.687-.562-1.249-1.25-1.249zm-5.466 3.99a.327.327 0 0 0-.231.094.33.33 0 0 0 0 .463c.842.842 2.484.913 2.961.913.477 0 2.105-.056 2.961-.913a.361.361 0 0 0 .029-.463.33.33 0 0 0-.464 0c-.547.533-1.684.73-2.512.73-.828 0-1.979-.196-2.512-.73a.326.326 0 0 0-.232-.095z"
            />
          </svg>
        </button>

        <button
          class="bg-gray-700 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded"
        >
          <svg
            class="w-4 h-4 md:w-10 md:h-10 lg:w-10 lg:h-10 xl:h-10 xl:w-10 fill-current"
            role="img"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M12.017 0C5.396 0 .029 5.367.029 11.987c0 5.079 3.158 9.417 7.618 11.162-.105-.949-.199-2.403.041-3.439.219-.937 1.406-5.957 1.406-5.957s-.359-.72-.359-1.781c0-1.663.967-2.911 2.168-2.911 1.024 0 1.518.769 1.518 1.688 0 1.029-.653 2.567-.992 3.992-.285 1.193.6 2.165 1.775 2.165 2.128 0 3.768-2.245 3.768-5.487 0-2.861-2.063-4.869-5.008-4.869-3.41 0-5.409 2.562-5.409 5.199 0 1.033.394 2.143.889 2.741.099.12.112.225.085.345-.09.375-.293 1.199-.334 1.363-.053.225-.172.271-.401.165-1.495-.69-2.433-2.878-2.433-4.646 0-3.776 2.748-7.252 7.92-7.252 4.158 0 7.392 2.967 7.392 6.923 0 4.135-2.607 7.462-6.233 7.462-1.214 0-2.354-.629-2.758-1.379l-.749 2.848c-.269 1.045-1.004 2.352-1.498 3.146 1.123.345 2.306.535 3.55.535 6.607 0 11.985-5.365 11.985-11.987C23.97 5.39 18.592.026 11.985.026L12.017 0z"
            />
          </svg>
        </button>

        <button
          class="bg-gray-700 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded"
        >
          <svg
            class="w-4 h-4 md:w-10 md:h-10 lg:w-10 lg:h-10 xl:h-10 xl:w-10 fill-current"
            role="img"
            viewBox="0 0 256 256"
            xmlns="http://www.w3.org/2000/svg"
          >
            <g>
              <path
                d="M218.123122,218.127392 L180.191928,218.127392 L180.191928,158.724263 C180.191928,144.559023 179.939053,126.323993 160.463756,126.323993 C140.707926,126.323993 137.685284,141.757585 137.685284,157.692986 L137.685284,218.123441 L99.7540894,218.123441 L99.7540894,95.9665207 L136.168036,95.9665207 L136.168036,112.660562 L136.677736,112.660562 C144.102746,99.9650027 157.908637,92.3824528 172.605689,92.9280076 C211.050535,92.9280076 218.138927,118.216023 218.138927,151.114151 L218.123122,218.127392 Z M56.9550587,79.2685282 C44.7981969,79.2707099 34.9413443,69.4171797 34.9391618,57.260052 C34.93698,45.1029244 44.7902948,35.2458562 56.9471566,35.2436736 C69.1040185,35.2414916 78.9608713,45.0950217 78.963054,57.2521493 C78.9641017,63.090208 76.6459976,68.6895714 72.5186979,72.8184433 C68.3913982,76.9473153 62.7929898,79.26748 56.9550587,79.2685282 M75.9206558,218.127392 L37.94995,218.127392 L37.94995,95.9665207 L75.9206558,95.9665207 L75.9206558,218.127392 Z M237.033403,0.0182577091 L18.8895249,0.0182577091 C8.57959469,-0.0980923971 0.124827038,8.16056231 -0.001,18.4706066 L-0.001,237.524091 C0.120519052,247.839103 8.57460631,256.105934 18.8895249,255.9977 L237.033403,255.9977 C247.368728,256.125818 255.855922,247.859464 255.999,237.524091 L255.999,18.4548016 C255.851624,8.12438979 247.363742,-0.133792868 237.033403,0.000790807055"
              ></path>
            </g>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref} from 'vue';

import innoIcon from './assets/nico-logo.png';
import innoCert from './assets/innovationcert.png';
import uxIcon from './assets/ux.png';
import uxCert from './assets/uxcertificate.jpg';
import javaCert from './assets/javacert.jpg';
import entrypythonCert from './assets/entrycert.jpg';
import reactCert from './assets/reactcert.jpg';
import assocPythonCert from './assets/pythonassccert.jpg';
import pythonIcon from './assets/python.svg';
import reactIcon from './assets/science.png';
import jsIcon from './assets/js.png';
const showMenu=ref('false');
const showModal = ref(false);
const showLaravelModal = ref(false);
const showPythonModal = ref(false);
const showWordPressModal = ref(false);
const showJsModal = ref(false);


const certifications = [
  {
    title: "Innovation Award",
    issuer: "NICO Technologies – 2025",
    icon: innoIcon,
    image: innoCert, 
  },
  {
    title: "UX Design ",
    issuer: "Coursera – 2024",
    icon: uxIcon,
    image: uxCert,
  },
  {
    title: "Python Associate",
    issuer: "Python Institute – 2024",
    icon: pythonIcon,
    image: assocPythonCert,
  },
  {
    title: "Python Entry Level",
    issuer: "Python Institute – 2023",
    icon: pythonIcon,
    image: entrypythonCert,
  },
  {
    title: "React JS",
    issuer: "Edureka – 2022",
    icon: reactIcon,
    image: reactCert,
  },
  {
    title: "JavaScript",
    issuer: "W3 Schools – 2021",
    icon: jsIcon,
    image: javaCert,
  },
];

const selectedCert = ref(certifications[0]);


</script>
