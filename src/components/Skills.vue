<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "SkillsSection",
  data() {
    return {
      skills: [
        { name: "WordPress", percent: 95, animatedWidth: 0 },
        { name: "Webflow", percent: 85, animatedWidth: 0 },
        { name: "PHP", percent: 75, animatedWidth: 0 },
        { name: "Laravel", percent: 60, animatedWidth: 0 },
        { name: "VueJs", percent: 65, animatedWidth: 0 },
        { name: "Bootstrap", percent: 90, animatedWidth: 0 },
        { name: "Tailwind", percent: 90, animatedWidth: 0 },
      ],
      metrics: [
        {
          label: "Years Experience",
          value: 3,
          suffix: "+",
          current: 0,
          duration: 1000,
        },
        {
          label: "Projects Completed",
          value: 50,
          suffix: "+",
          current: 0,
          duration: 1000,
        },
        {
          label: "Technologies",
          value: 10,
          suffix: "+",
          current: 0,
          duration: 1000,
        },
        {
          label: "Client Satisfaction",
          value: 100,
          suffix: "%",
          current: 0,
          duration: 1000,
        },
      ],
    };
  },
  mounted() {
    // Delay to ensure rendering is complete
    setTimeout(() => {
      this.skills.forEach((skill) => {
        skill.animatedWidth = skill.percent;
      });
    }, 100);
    this.metrics.forEach((metric, idx) => {
      this.animateMetric(idx);
    });
  },
  methods: {
    animateMetric(idx) {
      const metric = this.metrics[idx];
      const start = 0;
      const end = metric.value;
      const duration = metric.duration;
      const stepTime = Math.abs(Math.floor(duration / end));
      let current = start;
      const timer = setInterval(() => {
        current++;
        this.metrics[idx].current = current;
        if (current >= end) {
          clearInterval(timer);
        }
      }, stepTime);
    },
  },
});
</script>

<template>
  <div
    class="skills-section" id="skills"
    style="
      background: linear-gradient(45deg, #7b2ff2 0%, #22388a 100%);
      padding: 50px 0;
    "
  >
    <div class="text-center mb-4">
      <h2 class="display-4 fw-bold skills-title">My Skills</h2>
      <div class="skills-underline mx-auto mb-2"></div>
      <p class="lead skills-subtitle">
        Technologies and tools I use to bring ideas to life
      </p>
    </div>
    <div class="container">
      <div class="row justify-content-center mb-5">
        <!-- Progress Bars Section -->
        <div class="col-md-7">
          <div class="skills-progress-container p-4 p-lg-5">
            <h4 class="text-center mb-4 fw-bold">Technical Skills</h4>
            <div class="row g-4">
              <div
                class="col-md-6"
                v-for="(skill, index) in skills"
                :key="index"
              >
                <div class="skill-item">
                  <div class="d-flex justify-content-between px-2 mb-2">
                    <span class="skill-name">{{ skill.name }}</span>
                    <span class="skill-percent">{{ skill.percent }}%</span>
                  </div>
                  <div
                    class="progress"
                    style="height: 10px; background: rgba(255, 255, 255, 0.1)"
                  >
                    <div
                      class="progress-bar"
                      role="progressbar"
                      :style="{
                        width: skill.animatedWidth + '%',
                        backgroundImage:
                          'linear-gradient(90deg, #60a5fa, #51d11a)',
                      }"
                      :aria-valuenow="skill.percent"
                      aria-valuemin="0"
                      aria-valuemax="100"
                    ></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- success message section  -->
        
            <div class="col-md-5 d-flex flex-wrap justify-content-center gap-3 mt-0">
              <div
                class="text-center"
                style="flex: 0 0 auto; width: 45%;"
                v-for="(metric) in metrics"
                :key="metric.label"
              >
                <div class="skills-metric d-flex justify-content-center flex-column h-100">
                  <h3>{{ metric.current }}{{ metric.suffix }}</h3>
                  <p>{{ metric.label }}</p>
                </div>
              </div>
            </div>
      </div>

      <!-- Skills Cards Section -->
      <div class="row g-4 justify-content-center">
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #f357a8, #ff69b4)"
            >
              <i class="bi bi-code-slash"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">Web Development</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>HTML5</span><span>CSS3</span><span>JavaScript</span
              ><span>Bootstrap</span><span>jQuery</span><span>PHP</span>
            </div>
          </div>
        </div>
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #7b2ff2, #b16cea)"
            >
              <i class="bi bi-stack"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">Frameworks</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>Laravel</span><span>Vue.js</span><span>Tailwind CSS</span>
            </div>
          </div>
        </div>
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #32cd32, #00c6fb)"
            >
              <i class="bi bi-globe"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">CMS & Platforms</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>WordPress</span><span>Webflow</span
              ><span>Theme Customization</span><span>SEO Optimization</span>
            </div>
          </div>
        </div>
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #ffa500, #ff5e69)"
            >
              <i class="bi bi-database"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">Database</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>MySQL</span><span>MongoDB</span><span>Database Design</span
              ><span>Query Optimization</span>
            </div>
          </div>
        </div>
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #9370db, #7b2ff2)"
            >
              <i class="bi bi-tools"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">Tools & Version Control</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>GitHub</span><span>GitLab</span><span>VS Code</span
              ><span>Chrome Dev Tools</span>
            </div>
          </div>
        </div>
        <div class="col-md-4 col-lg-4">
          <div class="skills-card align-items-center h-100 p-4">
            <div
              class="skills-icon"
              style="background: linear-gradient(135deg, #ff4040, #ff5e69)"
            >
              <i class="bi bi-phone"></i>
            </div>
            <h5 class="fw-bold mt-3 mb-2">Mobile & Other</h5>
            <div class="skills-tags justify-content-center mb-2">
              <span>Android Development</span><span>Python</span
              ><span>C Programming</span><span>CCNA Networking</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills-section {
  color: #fff;
}
.skills-title {
  color: #ff69b4;
  letter-spacing: 1px;
}
.skills-underline {
  width: 80px;
  height: 4px;
  background: linear-gradient(90deg, #ff69b4, #7b2ff2);
  border-radius: 2px;
}
.skills-subtitle {
  color: #bdbdbd;
  font-size: 1.1rem;
}
.skills-card {
  background: rgba(255, 255, 255, 0.04);
  border: 1.5px solid rgba(255, 255, 255, 0.08);
  border-radius: 18px;
  box-shadow: 0 4px 24px 0 rgba(123, 47, 242, 0.08);
  transition: transform 0.2s, box-shadow 0.2s;
  min-height: 260px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.skills-card:hover {
  transform: translateY(-6px) scale(1.03);
  box-shadow: 0 8px 32px 0 rgba(123, 47, 242, 0.18);
}
.skills-icon {
  width: 54px;
  height: 54px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  font-size: 2rem;
  color: #fff;
  margin-bottom: 10px;
  box-shadow: 0 2px 8px 0 rgba(0, 0, 0, 0.1);
}
.skills-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.skills-tags span {
  background: rgba(255, 255, 255, 0.1);
  color: #fff;
  font-size: 0.95rem;
  padding: 4px 12px;
  border-radius: 12px;
  margin-bottom: 4px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  font-weight: 500;
}
.skills-metric {
  background: rgba(255, 255, 255, 0.06);
  border-radius: 16px;
  padding: 18px 0 10px 0;
  box-shadow: 0 2px 8px 0 rgba(123, 47, 242, 0.08);
}
.skills-metric h3 {
  color: #ff69b4;
  font-size: 2.1rem;
  font-weight: 700;
  margin-bottom: 0.2rem;
}
.skills-metric p {
  color: #fff;
  font-size: 1rem;
  margin-bottom: 0;
}

.skills-progress-container {
  background: rgba(255, 255, 255, 0.04);
  border: 1.5px solid rgba(255, 255, 255, 0.08);
  border-radius: 18px;
  box-shadow: 0 4px 24px 0 rgba(123, 47, 242, 0.08);
}

.skill-name {
  color: #fff;
  font-weight: 500;
  font-size: 0.95rem;
}

.skill-percent {
  color: #bdbdbd;
  font-size: 0.85rem;
}

.progress {
  border-radius: 4px;
}

.progress-bar {
  border-radius: 4px;
  transition: width 1s ease-in-out;
}
</style>
