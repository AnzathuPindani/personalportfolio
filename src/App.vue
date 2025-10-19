<style scoped>
.input {
  width: 100%;
  padding: 0.75rem;
  border-radius: 0.5rem;
  border: 1px solid #ccc;
}
.btn {
  padding: 0.75rem 1.5rem;
  background-color: #0066a1;
  color: white;
  border-radius: 0.5rem;
  cursor: pointer;
}
.btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}
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
 
  
    background-size: 600% 600%;
    animation: gradient 20s ease infinite;
}
@keyframes fade-slide-up {
  0% { opacity: 0; transform: translateY(20px); }
  100% { opacity: 1; transform: translateY(0); }
}
.animate-fade-slide-up {
  animation: fade-slide-up 0.7s ease-out forwards;
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
  <div class="banner-1">
<nav
  :class="[
    'fixed top-0 left-0 w-full z-50 transition-colors duration-300 border-b',
    scrolled ? 'bg-gray-900/80 backdrop-blur-lg border-gray-800' : 'bg-transparent border-transparent'
  ]"
>
<div class="container mx-auto px-10 md:px-28 flex justify-between items-center py-4">

      <!-- Logo / Brand -->
      <div class="flex items-center space-x-2">
       <h2 class="text-3xl font-bold hidden md:block">
  <span class="text-orange-500">{</span>
  <span class="text-white">AP</span>
  <span class="text-orange-500">}</span>
</h2>

      </div>

      <!-- Mobile Menu Button -->
      <div @click="showMenu = !showMenu" class="md:hidden text-white cursor-pointer">
        <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
          <path
            fill-rule="evenodd"
            d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
          />
        </svg>
      </div>

      <!-- Menu Links -->
      <ul
        :class="[
          'text-white font-semibold text-lg  md:text-lg transition-all duration-300',
          'md:flex md:flex-row md:space-x-8',
          showMenu
            ? 'flex flex-col mt-4 space-y-4 bg-gray-900 p-4 rounded-lg absolute top-16 left-0 w-full md:static md:bg-transparent md:p-0 md:rounded-none'
            : 'hidden md:flex'
        ]"
        class="items-center"
      >
        <li class="hover:text-orange-400 transition-colors duration-300">
          <a href="#">Home</a>
        </li>
        <li class="hover:text-orange-400 transition-colors duration-300">
          <a href="#about" v-smooth-scroll>About</a>
        </li>
        <li class="hover:text-orange-400 transition-colors duration-300">
          <a href="#work" v-smooth-scroll>Expertise</a>
        </li>
        <li class="hover:text-orange-400 transition-colors duration-300">
          <a href="#certifications" v-smooth-scroll>Skills</a>
        </li>
        <li class="hover:text-orange-400 transition-colors duration-300">
          <a href="#contactus" v-smooth-scroll>Contact Us</a>
        </li>
      </ul>
    </div>
  </nav>




<!--Start of Modals-->

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

    <div class="flex flex-col md:flex-row items-center">
      <div class="w-11/12 space-y-5 md:space-y-10">
      
<h2
  class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-Eczar font-bold leading-snug text-white animate-fade-slide"
>
  <span class="text-orange-500 font-mono">&lt;Hello/&gt;</span><br> 
  I’m Anzathu Pindani <br />
  Frontend Focused. WordPress Ready. Software Driven.
</h2>







<div class="flex gap-4 mt-6">
  <!-- Dribbble -->
  <a href="https://dribbble.com/" target="_blank" class="text-gray-400 hover:text-pink-500 transition-colors">
    <img src="./assets/dribble.png" alt="Dribbble" class="w-6 h-6"/>
  </a>

  <!-- GitHub -->
  <a href="https://github.com/" target="_blank" class="text-gray-400 hover:text-gray-800 transition-colors">
    <img src="./assets/github.png" alt="GitHub" class="w-6 h-6"/>
  </a>

  <!-- LinkedIn -->
  <a href="https://linkedin.com/" target="_blank" class="text-gray-400 hover:text-blue-600 transition-colors">
    <img src="./assets/linkedin.png" alt="LinkedIn" class="w-6 h-6"/>
  </a>

  <!-- Facebook -->
  <a href="https://facebook.com/" target="_blank" class="text-gray-400 hover:text-blue-500 transition-colors">
    <img src="./assets/facebook.png" alt="Facebook" class="w-6 h-6"/>
  </a>

  <!-- Instagram -->
  <a href="https://instagram.com/" target="_blank" class="text-gray-400 hover:text-pink-400 transition-colors">
    <img src="./assets/instagram.png" alt="Instagram" class="w-6 h-6"/>
  </a>
   <a href="https://instagram.com/" target="_blank" class="text-gray-400 hover:text-pink-400 transition-colors">
    <img src="./assets/mail.png" alt="Instagram" class="w-6 h-6"/>
  </a>
</div>

    <div class="md:flex gap-3 md:gap-5">
  <!-- CV Button -->
  <button
    @click="openCv"
    class="relative flex items-center justify-center gap-1 md:gap-2 text-white bg-gray-800 submit-button hidden md:flex px-4 py-2 md:px-5 md:py-2 rounded-lg transition text-sm md:text-base"
    style="background-color: #0066A1;"
    :disabled="isLoadingCv"
  >
    <span v-if="!isLoadingCv">View My CV</span>

    <!-- Loading Animation -->
    <span v-else class="flex items-center gap-1 md:gap-2 text-sm md:text-base">
      <svg
        class="w-4 h-4 animate-bounce"
        fill="currentColor"
        viewBox="0 0 20 20"
      >
        <path d="M6 2a2 2 0 00-2 2v12a2 2 0 002 2h8a2 2 0 002-2V8l-6-6H6z"/>
      </svg>
      <span>Loading...</span>
    </span>
  </button>

  <!-- Contact Button -->
  <button 
    href="#contactus" 
    v-smooth-scroll
    class="bg-orange-600 submit-button mb-3 md:mb-0 px-4 py-2 md:px-5 md:py-2 text-sm md:text-base"
  >
    Contact Me
  </button>
</div>



      </div>

<div class="relative w-full md:w-6/12 flex my-10 md:my-20 justify-end items-center">

  <div class="w-full md:w-12/12 bg-gray-900 rounded-2xl shadow-xl overflow-hidden">
    <!-- Tabs -->
    <div class="flex bg-gray-800 px-4 py-2 space-x-2">
<div class="px-3 py-1 rounded-t-lg bg-gray-700 text-white font-mono text-sm flex items-center gap-1">
  <img src="./assets/vue.png" alt="Vue Icon" class="w-4 h-4"/>
  profile.vue
</div>

      <div class="px-3 py-1 rounded-t-lg text-gray-400 font-mono text-sm hover:text-white cursor-pointer">app.vue</div>
      <div class="px-3 py-1 rounded-t-lg text-gray-400 font-mono text-sm hover:text-white cursor-pointer">main.js</div>
    </div>

    <!-- Code Content with Line Numbers -->
    <div class="flex bg-gray-900">
      <!-- Line Numbers -->
<div class="bg-gray-800 text-gray-500 text-xs font-mono px-3 py-6 select-none text-right">
  <div v-for="n in codeLines" :key="n">{{ n }}</div>
</div>

      <!-- Code Area -->
<pre class="p-6 font-mono text-sm text-white overflow-x-auto flex-1 w-full h-96 bg-gray-900">
<code>
// 5+ years of software experience
const softwaredeveloper = {
  frontEnd: ['JavaScript', 'Tailwind', 'Vuetify', 'React', 'Vue'],
  backEnd: ['Flask', 'Laravel', 'WordPress'],
  language: ['Python', 'PHP'],
  editor: ['VS Code']
};

// Currently learning
const learning = {
  frameworks: ['Nuxt.js', 'Pinia', 'Next.js'],
  languages: ['TypeScript'],
  tools: ['Docker', 'Vite', 'Jest']
};
</code>
</pre>


    </div>

    <!-- Footer / Editor Info -->
    <div class="px-6 py-2 bg-gray-800 text-gray-400 text-xs font-mono flex justify-between">
      <span>VS Code</span>
      <span>Line 1 - 20</span>
    </div>
  </div>
</div>


    </div>
  </div>
<div
  class="banner-2 flex flex-col md:flex-row text-white items-center md:items-center md:justify-center gap-12 md:gap-20 py-20"
  id="about"
>
  <!-- Image Section -->
  <div class="flex justify-center md:w-5/12 px-6 md:px-0">
    <div class="relative w-72 h-72 md:w-96 md:h-96  rounded-xl overflow-hidden shadow-2xl border border-gray-700">
      <!-- Editor Header -->
      <div class="flex items-center justify-start space-x-2 bg-gray-800 px-3 py-2">
        <span class="w-3 h-3 bg-red-500 rounded-full"></span>
        <span class="w-3 h-3 bg-yellow-500 rounded-full"></span>
        <span class="w-3 h-3 bg-green-500 rounded-full"></span>
        <span class="text-gray-400 font-mono text-xs ml-3">developer.jpg</span>
      </div>

      <!-- Image -->
      <img
        src="./assets/heroimage.png"
        alt="Anzathu Pindani"
        class="w-full h-full object-cover transition-transform duration-500 hover:scale-100"
      />

      <!-- Overlay Tag -->
      <div
        class="absolute bottom-2 right-2 bg-gray-800/70 px-3 py-1 rounded text-xs text-orange-400 font-mono"
      >
        &lt;Frontend /&gt;
      </div>
    </div>
  </div>

  <!-- About Content -->
  <div class="md:w-6/12 text-center md:text-left">
 <h3 class="text-4xl md:text-5xl font-bold mb-12 text-white px-6 md:px-0">
   About Me
  </h3>
    <p
      class="font-work_sans text-lg leading-relaxed px-6 md:px-0 text-gray-300"
    >
      I’m <span class="text-orange-500 font-semibold">Anzathu Pindani</span>, a
      Senior Software Developer from Malawi with 5+ years of experience building
      responsive, user-friendly applications using
      <span class="text-orange-500">Vue.js</span>,
      <span class="text-orange-500">Laravel</span>, and
      <span class="text-orange-500">WordPress</span>. I specialize in creating
      intuitive interfaces and scalable solutions.
      <br /><br />
      Outside of coding, I enjoy UI/UX exploration, reading books, watching
      wrestling, movies, and traveling.
    </p>
  </div>
</div>

<div class="banner-1 space-y-4 pt-32 pb-20" id="work">
 <h3 class="text-4xl md:text-5xl font-bold mb-12 text-white px-6 md:px-6">
My Expertise
  </h3>

<div class="grid grid-cols-1 md:grid-cols-3 gap-8 px-6 md:px-6">
  <!-- Card 1 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/mobileapps.jpg"
      alt="Mobile Apps"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">Mobile Application Development</h4>
    </div>
  </div>

  <!-- Card 2 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/website.jpg"
      alt="Appic"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">Website Development</h4>
    </div>
  </div>

  <!-- Card 3 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/116571.jpg"
      alt="FHS"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">Software Development</h4>
    </div>
  </div>
   <!-- Card 1 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/25876189_7100345.jpg"
      alt="Mobile Apps"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">API Intergration</h4>
    </div>
  </div>

  <!-- Card 2 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/118214.jpg"
      alt="Appic"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">Wordpress Plugin & Theme Development</h4>
    </div>
  </div>

  <!-- Card 3 -->
  <div class="relative overflow-hidden transform transition duration-500 hover:scale-105 hover:rotate-2 cursor-pointer group aspect-w-4 aspect-h-2 max-h-60">
    <div class="absolute inset-0 border-4 border-gray-700 rounded-xl shadow-inner pointer-events-none"></div>
    <img
      src="./assets/127029.jpg"
      alt="FHS"
      class="w-full h-full object-cover rounded-xl transition-transform duration-500 group-hover:scale-110 shadow-2xl"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end justify-center p-4 opacity-0 group-hover:opacity-100 transition duration-500">
      <h4 class="text-white text-xl md:text-2xl font-bold text-center animate-fade-slide-up">Data-driven Frontend Solutions</h4>
    </div>
  </div>

</div>


</div>




<section id="certifications" class="banner-1  space-y-30 mb-40">

 <h3 class="text-4xl md:text-5xl font-bold mb-12 text-white px-6 md:px-6">
    My Skills
  </h3>

  <div class="container mx-auto px-6 md:px-10 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
    <div
      v-for="(skill, index) in skills"
      :key="index"
      class="relative group p-6 rounded-2xl backdrop-blur-lg bg-white/10 border border-white/20 shadow-lg flex flex-col items-center justify-center transition-transform duration-500 hover:scale-105"
    >
      <div class="w-16 h-16 mb-4">
        <img :src="skill.icon" :alt="skill.name" class="w-full h-full object-contain" />
      </div>
      <h4 class="text-white text-xl font-semibold text-center">{{ skill.name }}</h4>
      <p class="text-gray-300 text-sm mt-2 text-center">{{ skill.level }}</p>
    </div>
  </div>
</section>
<section id="contactus" class="banner-1 bg-gray-900 text-gray-100">
  <div class="container mx-auto px-6 md:px-20 md:py-10">
    <!-- Contact Form -->
    <form @submit.prevent="sendEmail" class="space-y-6 bg-gray-800 p-8 rounded-2xl shadow-xl">
      
      <h2 class="text-3xl font-bold text-center text-white mb-6">Contact Me</h2>

      <!-- Name -->
      <input
        v-model="name"
        type="text"
        placeholder="Your Name"
        required
        class="w-full px-5 py-3 rounded-xl bg-gray-900 border border-gray-700 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none transition duration-300"
      />

      <!-- Email -->
      <input
        v-model="email"
        type="email"
        placeholder="Your Email"
        required
        class="w-full px-5 py-3 rounded-xl bg-gray-900 border border-gray-700 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none transition duration-300"
      />

      <!-- Subject -->
      <input
        v-model="subject"
        type="text"
        placeholder="Subject"
        required
        class="w-full px-5 py-3 rounded-xl bg-gray-900 border border-gray-700 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none transition duration-300"
      />

      <!-- Reason -->
      <select
        v-model="reason"
        required
        class="w-full px-5 py-3 rounded-xl bg-gray-900 border border-gray-700 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none transition duration-300"
      >
        <option value="" disabled>Select Reason</option>
        <option value="collaboration">Collaboration</option>
        <option value="project">Project Inquiry</option>
        <option value="hiring">Hiring Opportunity</option>
        <option value="mentorship">Mentorship</option>
        <option value="other">Other</option>
      </select>

      <!-- Message -->
      <textarea
        v-model="message"
        placeholder="Your message..."
        required
        rows="5"
        class="w-full px-5 py-3 rounded-xl bg-gray-900 border border-gray-700 text-white placeholder-gray-400 focus:ring-2 focus:ring-indigo-500 focus:outline-none transition duration-300"
      ></textarea>

      <!-- Button -->
      <button
        :disabled="loading"
        class="w-full py-3 bg-indigo-600 hover:bg-indigo-700 text-white font-bold rounded-xl shadow-md transition duration-300"
      >
        {{ loading ? 'Sending...' : 'Send Message' }}
      </button>

      <!-- Success & Error Messages -->
      <p v-if="successMsg" class="text-green-400 text-center font-medium">{{ successMsg }}</p>
      <p v-if="errorMsg" class="text-red-400 text-center font-medium">{{ errorMsg }}</p>

    </form>
  </div>
</section>









  

 


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
import vueIcon from './assets/vue.png';
import wordpressicon from './assets/wordpress.png';
import tailwindicon from './assets/css-3.png';
import reactIcon from './assets/science.png';
import bootIcon from './assets/bootstrap.png';
import figmaIcon from './assets/figma.png';
import jsIcon from './assets/js.png';
const showMenu = ref(false);
const scrolled = ref(false);

window.addEventListener('scroll', () => {
  scrolled.value = window.scrollY > 50; 
});

const showModal = ref(false);
const showLaravelModal = ref(false);
const showPythonModal = ref(false);
const showWordPressModal = ref(false);
const showJsModal = ref(false);
const codeLines=ref(20);
const showCvModal = ref(false);
import emailjs from '@emailjs/browser';


const name = ref('');
const email = ref('');
const subject = ref('');
const message = ref('');
const reason = ref('');
const loading = ref(false);
const successMsg = ref('');
const errorMsg = ref('');

// Your EmailJS credentials
const SERVICE_ID = 'service_fqhmkga';
const TEMPLATE_ID = 'template_8cduw4f';
const PUBLIC_KEY = 'ZGnyiDwXCLnwku-Cx';

const sendEmail = async () => {
  loading.value = true;
  successMsg.value = '';
  errorMsg.value = '';

  const templateParams = {
    from_name: name.value,
    from_email: email.value,
    subject: subject.value,
    message: message.value,
    reason: reason.value,
  };

  try {
    await emailjs.send(SERVICE_ID, TEMPLATE_ID, templateParams, PUBLIC_KEY);
    successMsg.value = 'Email sent successfully!';
    // Reset form
    name.value = '';
    email.value = '';
    subject.value = '';
    message.value = '';
    reason.value = '';
  } catch (error) {
    console.error(error);
    errorMsg.value = 'Failed to send email. Please try again.';
  } finally {
    loading.value = false;
  }
};

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
const skills = [
  {
    name: "Vue.js",
    icon: vueIcon, 
  },
  {
    name: "React JS",
    icon: reactIcon,
  },
  {
    name: "JavaScript",
    icon: jsIcon,
  },
  {
    name: "Python",
    icon: pythonIcon,
  },
  {
    name: "UX Design",
    icon: uxIcon,
  },
    {
    name: "Wordpress",
    icon: wordpressicon,
  },
   {
    name: "Tailwind",
    icon: tailwindicon,
  },
     {
    name: "Bootstrap",
    icon: bootIcon,
  },
    {
    name: "React Native",
    icon: reactIcon,
  },
];





</script>
