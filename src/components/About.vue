<template>
 
  <section
    id="about"
    class="about-section d-flex flex-column justify-content-center align-items-center py-5"
    style="background: linear-gradient(45deg, #501fc8 0%, #22388A 100%); color: white; "
  >
    <div class="container">
      <div class="row align-items-center g-4">
        <!-- Profile Image -->
        <div class="col-md-5 text-center">
          <div
            class="profile-img-wrapper mx-auto"
            style="
              width: 350px;
              height: 380px;
              overflow: hidden;
              border-radius: 10%;
              border: 4px solid linear-gradient(45deg, #22388a, #7b2ff2);
              box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
            "
          >
            <img
              src="../assets/my_pic.jpeg?text=Your+Photo"
              alt="Profile"
              class="w-100"
              style="object-fit: cover; object-position: top"
            />
          </div>
        </div>

        <!-- About Content -->
        <div class="col-md-7">
         
          <h4 class="fw-bold display-5 mb-3">Professional Journey</h4>
          <p>
            I'm a passionate Full-Stack Web Developer with over 2 years of
            experience specializing in WordPress, Webflow, and modern PHP
            frameworks. Currently serving as a Senior WordPress/Webflow
            Developer at Prospect Engine, I create dynamic, responsive websites
            that deliver exceptional user experiences.
          </p>
          <h4 class="fw-bold mt-4 mb-3">My Passion</h4>
          <p>
            I specialize in creating flexible and dynamic websites tailored to
            client needs. My expertise spans from custom WordPress themes to
            complex Laravel applications, always focusing on clean code, smooth
            user experiences, and scalable solutions.
          </p>

          <!-- Info Cards -->
          <div class="row text-center g-3">
            <div class="col-6 col-sm-4">
              <div class=" text-white rounded-pill py-3 px-2 shadow-sm"
              style="background-color: rgba(255, 255, 255, 0.15)">
                <h4 class="fw-bold mb-0">3+</h4>
                <small class="text-white">Years Experience</small>
              </div>
            </div>
            <div class="col-6 col-sm-4">
              <div class="text-white rounded-pill py-3 px-2 shadow-sm"
              style="background-color: rgba(255, 255, 255, 0.15)">
                <h4 class="fw-bold mb-0">50+</h4>
                <small class="text-white">Projects Completed</small>
              </div>
            </div>
            <div class="col-12 col-sm-4">
              <div class="text-white rounded-pill py-3 px-2 shadow-sm"
              style="background-color: rgba(255, 255, 255, 0.15)">
                <h4 class="fw-bold mb-0">100%</h4>
                <small class="text-white">Client Satisfaction</small>
              </div>
            </div>
          </div>

          <!-- Download CV Button -->
          <div class="mt-4">
            <a
              href="/Mahmudul Hasan_WordPress-cv.pdf"
              class="btn btn-outline-light px-4 py-2 fw-semibold"
              download
            >
              <i class="bi bi-download me-2"></i>Download CV
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
