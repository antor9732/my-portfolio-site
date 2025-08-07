<template>
  <section id="contact" class="contact-section">
    <div class="container">
      <h2 class="text-center contact-title mb-2">Get In Touch</h2>
      <div class="contact-underline"></div>
      <p class="text-center contact-subtitle">Let's discuss your next project or collaboration opportunity</p>
      <div class="row g-4">
        <div class="col-lg-5">
          <div class=" p-4 mb-3">
            <div class="d-flex contact-card align-items-center mb-3">
              <div class="contact-info-icon" style="background: linear-gradient(135deg, #f357a8, #ff69b4);"><i class="bi bi-envelope-fill"></i>
              </div>
              <div>
                <div class="contact-info-title">Email</div>
                <div class="contact-info-detail">mahmudul.cse47@gmail.com</div>
              </div>
            </div>
            <div class="d-flex contact-card align-items-center mb-3">
              <div class="contact-info-icon" style="background: linear-gradient(135deg, #7b2ff2, #b16cea);"><i class="bi bi-telephone-fill"></i></div>
              <div>
                <div class="contact-info-title">Phone</div>
                <div class="contact-info-detail">+880 1521-404650<br>+880 1750-482756</div>
              </div>
            </div>
            <div class="d-flex contact-card align-items-center mb-3">
              <div class="contact-info-icon" style="background: linear-gradient(135deg, #32cd32, #00c6fb);"><i class="bi bi-geo-alt-fill"></i></div>
              <div>
                <div class="contact-info-title">Location</div>
                <div class="contact-info-detail text-info">House# 125, Road No: 13, Sector-10, Uttara, Dhaka</div>
              </div>
            </div>
            <div class="contact-socials d-flex gap-2 mt-3">
              <a href="https://www.linkedin.com/in/mahmudul-hasan-935299177/" target="_blank" class="rounded-circle d-flex align-items-center justify-content-center" style="width: 38px; height: 38px;"><i class="bi bi-linkedin"></i></a>
              <a href="https://gitlab.com/Mahmudul13" target="_blank" class="rounded-circle d-flex align-items-center justify-content-center" style="width: 38px; height: 38px;"><i class="bi bi-github"></i></a>
            </div>
          </div>
        </div>
        <div class="col-lg-7">
          <div class="contact-form-card p-4">
            <form>
              <div class="mb-3">
                <label class="form-label">Your Name</label>
                <input type="text" class="form-control" placeholder="Enter your name">
              </div>
              <div class="mb-3">
                <label class="form-label">Your Email</label>
                <input type="email" class="form-control" placeholder="Enter your email">
              </div>
              <div class="mb-3">
                <label class="form-label">Your Message</label>
                <textarea class="form-control" rows="4" placeholder="Enter your message"></textarea>
              </div>
              <button type="submit" class="btn btn-send w-100"><i class="bi bi-send me-2"></i>Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  background: linear-gradient(135deg, #7b2ff2 0%, #22388A 100%);
  padding: 50px 0;
}
.contact-title {
  color: #ff69b4;
  font-size: 2.5rem;
  font-weight: 700;
  letter-spacing: 1px;
}
.contact-underline {
  width: 250px;
  height: 4px;
  background: linear-gradient(90deg, #ff69b4, #7b2ff2);
  border-radius: 2px;
  margin: 0 auto 1rem auto;
}
.contact-subtitle {
  color: #bdbdbd;
  font-size: 1.1rem;
  margin-bottom: 2.5rem;
}
.contact-card {
  background: rgba(255,255,255,0.04);
  border: 1.5px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  box-shadow: 0 4px 24px 0 rgba(123,47,242,0.08);
  color: #fff;
  margin-bottom: 1.5rem;
  padding: 24px;
}
.contact-info-icon {
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12px;
  font-size: 1.5rem;
  color: #fff;
  margin-right: 12px;
  box-shadow: 0 2px 8px 0 rgba(0,0,0,0.10);
}
.contact-info-title {
  font-weight: 600;
  font-size: 1.1rem;
}
.contact-info-detail {
  color: #bdbdbd;
  font-size: 1rem;
}
.contact-socials a {
  background: rgba(255,255,255,0.10);
  color: #fff;
  border: none;
  font-size: 1.3rem;
  margin-right: 8px;
  transition: background 0.2s, color 0.2s;
}
.contact-socials a:hover {
  background: linear-gradient(135deg, #f357a8, #7b2ff2);
  color: #fff;
}
.contact-form-card {
  background: rgba(255,255,255,0.04);
  border: 1.5px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  box-shadow: 0 4px 24px 0 rgba(123,47,242,0.08);
  color: #fff;
}
.form-label {
  color: #fff;
  font-weight: 500;
}
.form-control {
  background: rgba(255,255,255,0.10);
  border: 1px solid rgba(255,255,255,0.15);
  color: #fff;
  border-radius: 10px;
  font-size: 1rem;
}
.form-control:focus {
  background: rgba(255,255,255,0.13);
  color: #fff;
  border-color: #ff69b4;
  box-shadow: 0 0 0 0.15rem rgba(255,105,180,0.15);
}
.btn-send {
  background: linear-gradient(90deg, #b16cea, #ff5e69);
  border: none;
  color: #fff;
  font-weight: 600;
  font-size: 1.1rem;
  border-radius: 10px;
  transition: background 0.2s;
}
.btn-send:hover {
  background: linear-gradient(90deg, #ff5e69, #b16cea);
}
</style>