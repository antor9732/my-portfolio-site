<script setup>
import ProjectCard from './ProjectCard.vue';
import { Carousel, Slide, Navigation, Pagination } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
import imagesPng from '../assets/image.png';
import PdcaImage from '../assets/image.png';
import dirkImage from '../assets/dirkWeb.png';
import wmsImage from '../assets/wms.png';
import SendOutImage from '../assets/Sendout.png';
import AskGxpImage from '../assets/Askgxp.png';

const projects = [
  {
    title: 'Dirk Burmann ',
    description: 'Developed a fully responsive and visually captivating personal portfolio website using WordPress, showcasing creative and professional work with custom design and SEO optimization.',
    tags: 'WordPress, Elementor,Elementor Pro, Adobe Photoshop, SEO, WPML',
    link: 'http://dirkburmann.com/',
    demoLabel: 'Live Demo',
    category: 'WordPress',
    image: dirkImage,
  },
   {
    title: 'Work Made Simple (WMS)',
    description: 'Developed and implemented tailored ERP ecosystems using Microsoft Dynamics 365 Business Central, providing solutions for finance, supply chain, and warehouse management. Successfully migrated clients from legacy systems and optimized database performance for large-scale operations.',
    tags: 'Microsoft Dynamics 365 Business Central, ERP, LS Retail, Continia, Tasklet Factory, Power Platform, Custom ERP',
    link: 'https://wmsit.com.au/',
    demoLabel: 'Live Demo',
    category: 'WordPress',
    image: wmsImage,
},
 {
    title: 'PDCA Consulting',
    description: 'Specialized in providing expert coaching, consulting, and training in ITIL, Agile, and PRINCE2. Empowers teams, optimizes workflows, and helps organizations achieve measurable improvements in IT service management and project delivery.',
    tags: 'ITIL, Agile, PRINCE2, Coaching, Consulting, Training, Certification, IT Service Management',
    link: 'https://pdcaconsulting.com/',
    demoLabel: 'Live Demo',
    category: 'WordPress',
    image: PdcaImage,
},
  {
    title: 'Sendout.ai',
    description: 'Created an AI-driven platform on Webflow for automating lead generation with predictive analytics, custom animations, and interactive elements for enhanced user experience.',
    tags: 'Webflow, JavaScript, Google Analytics, AI Integration',
    link: 'https://prospectengine.ai',
    demoLabel: 'Live Demo',
    category: 'Webflow',
    image: SendOutImage,
  },
  {
    title: 'AskGxP',
    description: 'Developed an AI-powered knowledge management solution for the pharmaceutical industry. The platform features an AI-driven document generator for SOPs and protocols, an expert AI chat assistant, and an interactive learning platform to enhance compliance and streamline operations.',
    tags: 'AI, Pharmaceutical, Knowledge Management, SOPs, Compliance, Document Generator, AI Chat, Learning Platform',
    link: 'https://www.askgxp.com/',
    demoLabel: 'Live Demo',
    category: 'Webflow',
    image: AskGxpImage,
  },
  {
    title: 'E-Learning System',
    description: 'Comprehensive e-learning platform built with PHP and Laravel featuring user management, course creation, progress tracking, and interactive learning modules.',
    tags: 'PHP, Laravel, MySQL, Bootstrap, JavaScript',
    link: '#',
    demoLabel: 'Code resource',
    category: 'Codebase',
    image: imagesPng,
  },
  {
    title: 'Online Grocery Shop',
    description: 'E-commerce website for grocery products with shopping cart functionality, user authentication, order management, and responsive design for optimal user experience.',
    tags: 'HTML5, CSS3, JavaScript, Bootstrap, MySQL',
    link: '#',
    demoLabel: 'Code resource',
    category: 'Codebase',
    image: imagesPng,
  },
];

const wpWebflowProjects = projects.filter(p => p.category === 'WordPress' || p.category === 'Webflow');
const codebaseProjects = projects.filter(p => p.category === 'Codebase');
</script>

<template>
  <section id="projects" class="py-5" style="background: linear-gradient(112deg, #501fc8 0%, #22388A 100%);">
    <div class="container">
      <h2 class="text-center fw-bold mb-4" style="color: #e7c6ff; font-size: 2.5rem;">Featured Projects</h2>
      <p class="text-center text-white mb-5">Showcasing my best work and technical expertise</p>
      <!-- WordPress & Webflow Projects Carousel -->
      <h4 class="text-white mt-4 mb-3">WordPress & Webflow Projects</h4>
      <div class="d-flex flex-column align-items-center mb-4">
        <Carousel 
          :items-to-show="2" 
          :wrap-around="true" 
          navigationEnabled 
          paginationEnabled
          :navigation-next-label="'>'"
          :navigation-prev-label="'<'"
          class="w-100 custom-carousel"
        >
          <template #addons>
            <div class="carousel-controls">
              <CarouselNavigation />
              <CarouselPagination />
            </div>
          </template>
          <Slide v-for="project in wpWebflowProjects" :key="project.title">
            <div class="px-2 h-100">
              <ProjectCard v-bind="project" />
            </div>
          </Slide>
        </Carousel>
      </div>
      <!-- Codebase Projects Carousel -->
      <h4 class="text-white mt-4 mb-3">Codebase Projects (Laravel, VueJs, etc.)</h4>
      <div class="d-flex flex-column align-items-center mb-4">
        <Carousel 
          :items-to-show="2" 
          :wrap-around="true" 
          navigationEnabled 
          paginationEnabled
          :navigation-next-label="'>'"
          :navigation-prev-label="'<'"
          class="w-100 custom-carousel"
        >
          <template #addons>
            <div class="carousel-controls">
              <CarouselNavigation />
              <CarouselPagination />
            </div>
          </template>
          <Slide v-for="project in codebaseProjects" :key="project.title">
            <div class="px-2 h-100">
              <ProjectCard v-bind="project" />
            </div>
          </Slide>
        </Carousel>
      </div>
      <!-- <div class="bg-dark bg-opacity-50 rounded-4 p-4 text-white mt-4">
        <h5 class="fw-bold mb-2">Final Year Research Project</h5>
        <p class="mb-0">Detection of Early-Stage Breast Cancer through Machine Learning<br>Developed and implemented various machine learning algorithms to detect breast cancer in early stages. Through comprehensive research and testing, we achieved the highest accuracy among compared algorithms, contributing to early detection methodologies in medical diagnostics.</p>
      </div> -->
    </div>
  </section>
</template>

<style scoped>
.custom-carousel .carousel-controls {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 10px;
}
.custom-carousel .carousel__pagination {
  margin-top: 6px;
}
</style>