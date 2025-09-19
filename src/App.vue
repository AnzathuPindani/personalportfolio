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
          <li class="menu-button"><a href="#about" v-smooth-scroll>About</a></li>
        <li class="menu-button"><a href="#work" v-smooth-scroll>Works</a></li>
        <li class="menu-button">
          <a href="#certifications" v-smooth-scroll>Achievements</a>
        </li>
      
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

    <div
    v-if="showCvModal"
    class="fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-50"
  >
    <div class="bg-white w-11/12 md:w-3/4 lg:w-1/2 rounded-lg shadow-2xl overflow-hidden">
      <!-- Header -->
      <div class="flex justify-between items-center p-4 border-b">
        <h2 class="text-xl font-bold text-gray-700">My CV</h2>
        <button @click="closeCv" class="text-gray-500 hover:text-red-500 text-2xl">&times;</button>
      </div>

      <!-- PDF Viewer -->
      <div class="h-[80vh]">
        <iframe
          src="Anzathu_Pindani_Complete_CV.pdf" 
          class="w-full h-full"
          frameborder="0"
        ></iframe>
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
      <button
    @click="openCv"
    class="relative flex items-center justify-center gap-2 text-white bg-gray-800 submit-button hidden md:flex px-6 py-3 rounded-lg transition"
    style="background-color: #0066A1;"
    :disabled="isLoadingCv"
  >
    <span v-if="!isLoadingCv">View My CV</span>

    <!-- Loading Animation -->
    <span v-else class="flex items-center gap-2">
      <svg
        class="w-5 h-5 animate-bounce"
        fill="currentColor"
        viewBox="0 0 20 20"
      >
        <path
          d="M6 2a2 2 0 00-2 2v12a2 2 0 002 2h8a2 2 0 002-2V8l-6-6H6z"
        />
      </svg>
      <span>Loading...</span>
    </span>
  </button>
  
          <button href="#about" v-smooth-scroll
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
         class="absolute top-10 left-20 w-14 animate-pulse cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12 hidden md:block" 
         @click="showModal = true"
         alt="Vue" />

    <img src="./assets/js.png" 
         class="absolute top-20 right-10 w-12 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12 hidden md:block" 
         @click="showJsModal = true"
         alt="JavaScript" />

    <img src="./assets/laravel.svg" 
         class="absolute bottom-10 left-10 w-14 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12 hidden md:block" 
         alt="Laravel" @click="showLaravelModal = true"
 />

    <img src="./assets/python.svg" 
         class="absolute bottom-5 right-20 w-14 cursor-pointer transform transition duration-300 hover:scale-125 hover:rotate-12 hidden md:block" 
          @click="showPythonModal = true"
         alt="Python" />

    <img src="./assets/wordpress.png" 
         class="absolute top-1/2 right-3 transform -translate-y-1/2 w-14 cursor-pointer  transition duration-300 hover:scale-125 hover:rotate-12 hidden md:block" 
        @click="showWordPressModal = true"
         alt="WordPress" />
  </div>
    </div>
  </div>
 <div class="banner-2 md:flex text-white items-center md:pt-10  md:justify-evenly space-y-10 pb-20" id="about">
 
    <div>
  <h3 class="text-gray my-5 md:text-5xl text-xl  font-bold font-work_sans tracking-wide px-6 md:px-20">
    About Me
  </h3>
<p class="font-work_sans text-lg leading-relaxed px-6 md:px-20">
I’m Anzathu Pindani, a Senior Software Developer from Malawi with 7+ years of experience building responsive, user-friendly applications using Vue.js, Laravel, and WordPress. I specialize in creating intuitive interfaces and scalable solutions, blending development with strong UI/UX practices. Currently, I’m pursuing a Master’s in Informatics to deepen my expertise in software engineering and data-driven systems.

Outside of coding, I enjoy UI/UX exploration, reading, wrestling, movies, and traveling.
</p>



    </div>
  </div>
<div class="banner-1 space-y-10 pb-20" id="work">
  <h3 class="text-gray my-5 md:text-5xl text-xl  font-bold font-work_sans tracking-wide px-6 md:px-20">
    My Recent Work
  </h3>

<div class="grid grid-cols-1  lg:grid-cols-3 gap-6 px-6 md:px-20">
  <!-- CARD TEMPLATE -->
  <div class="flex flex-col bg-gray-900 text-white rounded-2xl overflow-hidden shadow-xl group transition duration-500">
    <!-- Image -->
    <div class="relative h-60 overflow-hidden">
      <img
        src="./assets/bhs.png"
        alt="Blantyre Hotel"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
      />
      <!-- Hover Button -->
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
        <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg hover:bg-[#e2892e] hover:scale-105 transition-transform duration-300">
          View More
        </button>
      </div>
    </div>

    <!-- Content -->
    <div class="flex-grow p-5 flex flex-col justify-between">
      <h4 class="font-bold text-2xl">Blantyre Hotel</h4>
      <p class="text-sm mt-2 text-gray-300">Mobile-first design</p>
    </div>
  </div>

  <!-- Duplicate and replace content for other cards -->
  <!-- Card 2 -->
  <div class="flex flex-col bg-gray-900 text-white rounded-2xl overflow-hidden shadow-xl group transition duration-500 ">
    <div class="relative h-60 overflow-hidden">
      <img
        src="./assets/appic.png"
        alt="Appic"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
        <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg hover:bg-[#e2892e] hover:scale-105 transition-transform duration-300">
          View More
        </button>
      </div>
    </div>
    <div class="flex-grow p-5 flex flex-col justify-between">
      <h4 class="font-bold text-2xl">Appic</h4>
      <p class="text-sm mt-2 text-gray-300">A portfolio website exploring clean design and responsive layouts</p>
    </div>
  </div>

  <!-- Card 3 -->
  <div class="flex flex-col bg-gray-900 text-white rounded-2xl overflow-hidden shadow-xl group transition duration-500">
    <div class="relative h-60 overflow-hidden">
      <img
        src="./assets/fhs.png"
        alt="FHS"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
      />
      <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-500">
        <button class="px-6 py-2 bg-[#c17111] text-white font-bold rounded-full shadow-lg hover:bg-[#e2892e] hover:scale-105 transition-transform duration-300">
          View More
        </button>
      </div>
    </div>
    <div class="flex-grow p-5 flex flex-col justify-between">
      <h4 class="font-bold text-2xl">FHS</h4>
      <p class="text-sm mt-2 text-gray-300">Contributed to FHS frontend in Vue.</p>
    </div>
  </div>
</div>

 




</div>

<section id="certifications" class="banner-2 mt-2 py-20 bg-gray-900 text-white">
         <h3 class="text-4xl md:text-5xl font-bold mb-12  text-[#fff] px-6 md:px-20">My Certifications and Awards</h3>
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
<section id="contactus" class="banner-1 text-gray bg-gray-900">
  <div class="container mx-auto px-6 md:px-20 md:py-20 text-left space-y-10">


    <!-- Contact Form -->
    <form
      action="#"
      method="POST"
      class="grid grid-cols-1 md:grid-cols-2 gap-6 bg-gray-800 p-8 rounded-2xl shadow-lg"
    >
      <!-- Name -->
      <div class="col-span-1">
        <label for="name" class="block text-sm font-medium text-gray-300 mb-2">Name</label>
        <input
          type="text"
          id="name"
          name="name"
          placeholder="Your full name"
          class="w-full px-4 py-3 rounded-lg border border-gray-600 bg-gray-900 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
          required
        />
      </div>

      <!-- Email -->
      <div class="col-span-1">
        <label for="email" class="block text-sm font-medium text-gray-300 mb-2">Email</label>
        <input
          type="email"
          id="email"
          name="email"
          placeholder="you@example.com"
          class="w-full px-4 py-3 rounded-lg border border-gray-600 bg-gray-900 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
          required
        />
      </div>

      <!-- Subject -->
      <div class="col-span-2">
        <label for="subject" class="block text-sm font-medium text-gray-300 mb-2">Subject</label>
        <input
          type="text"
          id="subject"
          name="subject"
          placeholder="Subject of your message"
          class="w-full px-4 py-3 rounded-lg border border-gray-600 bg-gray-900 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
          required
        />
      </div>

      <!-- Reason Dropdown -->
      <div class="col-span-2">
        <label for="reason" class="block text-sm font-medium text-gray-300 mb-2">Reason</label>
        <select
          id="reason"
          name="reason"
          class="w-full px-4 py-3 rounded-lg border border-gray-600 bg-gray-900 text-white focus:ring-2 focus:ring-indigo-500 focus:outline-none"
          required
        >
          <option value="">Select a reason</option>
          <option value="collaboration">Collaboration</option>
          <option value="project">Project Inquiry</option>
          <option value="hiring">Hiring Opportunity</option>
          <option value="mentorship">Mentorship</option>
          <option value="other">Other</option>
        </select>
      </div>

      <!-- Message -->
      <div class="col-span-2">
        <label for="message" class="block text-sm font-medium text-gray-300 mb-2">Message</label>
        <textarea
          id="message"
          name="message"
          rows="5"
          placeholder="Write your message here..."
          class="w-full px-4 py-3 rounded-lg border border-gray-600 bg-gray-900 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
          required
        ></textarea>
      </div>

      <!-- Submit Button -->
      <div class="col-span-2 flex justify-start">
        <button
          type="submit"
          class="px-8 py-3 bg-indigo-600 hover:bg-indigo-700 text-white font-semibold rounded-lg shadow-md transition duration-300"
        >
          Send Message
        </button>
      </div>
    </form>
  </div>
</section>





  

 

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

const showCvModal = ref(false);


const isLoadingCv = ref(false);

const openCv = () => {
  isLoadingCv.value = true;

  // Simulate loading delay (e.g., fetching PDF or opening modal)
  setTimeout(() => {
    window.open("/Anzathu_Pindani_Complete_CV.pdf", "_blank"); 
    isLoadingCv.value = false;
  }, 3000); // adjust delay
};
const closeCv = () => {
  showCvModal.value = false;
};
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
