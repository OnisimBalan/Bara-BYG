<template>
  <div id="app" class="d-flex flex-column" style="height: 100vh">
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-org mb-5 p-4">
      <div class="d-flex">
        <div class="mr-auto">
          <a class="navbar-brand hover-zoom">#42b983Logo#</a>
        </div>
        <div>
          <a class="ml-5 navbar-brand addMore" @click="goHome" href="#">Home</a>
          <a class="ml-5 navbar-brand addMore" @click="goServices" href="#">Services</a>
          <a class="ml-5 navbar-brand addMore" @click="goContact" href="#">Contact</a>
          <a class="ml-5 navbar-brand addMore" @click="goAbout" href="#">About</a>
        </div>
      </div>
    </nav>

    <!-- Page content (takes remaining height) -->
    <div class="flex-grow-1 d-flex justify-content-center align-items-center">
      <div v-if="services" class="services-container">
        <h2 class="mb-1">Our services consist in</h2>
        <div id="servicesCarousel" class="carousel slide" data-ride="carousel">
          <div class="carousel-inner">
            <div class="carousel-item active">
              <img src="https://via.placeholder.com/800x400?text=Slide+1" class="d-block w-100" alt="Slide 1">
              <div class="carousel-caption d-none d-md-block">
                <h5>Slide Title 1</h5>
                <p>This is the description for slide 1.</p>
              </div>
            </div>
            <div class="carousel-item">
              <img src="https://via.placeholder.com/800x400?text=Slide+2" class="d-block w-100" alt="Slide 2">
              <div class="carousel-caption d-none d-md-block">
                <h5>Slide Title 2</h5>
                <p>This is the description for slide 2.</p>
              </div>
            </div>
            <div class="carousel-item">
              <img src="https://via.placeholder.com/800x400?text=Slide+3" class="d-block w-100" alt="Slide 3">
              <div class="carousel-caption d-none d-md-block">
                <h5>Slide Title 3</h5>
                <p>This is the description for slide 3.</p>
              </div>
            </div>
          </div>
          <a class="carousel-control-prev" href="#servicesCarousel" role="button" data-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
          </a>
          <a class="carousel-control-next" href="#servicesCarousel" role="button" data-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
          </a>
        </div>
      </div>

      <div v-if="contact" class="contact-container">
        <h2 class="mb-5">Contact BARA-BYG Company</h2>
        <div class="info-item">
          <i class="fas fa-phone-alt"></i>
          <span>Phone: 0700 000 000</span>
        </div>
        <div class="info-item mb-3">
          <i class="fas fa-envelope"></i>
          <span>Email: bara-byg@gmail.com</span>
        </div>
        <button class="btn-email" @click="showModal = true">Send Email</button>
      </div>

      <div v-if="about" class="about-container">
        <p>At BARA-BYG, we offer a wide range of construction and renovation services tailored to your needs. From residential to commercial projects, we've got you covered.</p>
      </div>
    </div>

    <!-- Email Modal -->
    <div v-if="showModal" class="modal">
      <div class="modal-content">
        <span class="close" @click="showModal = false">&times;</span>
        <h2>Send Email</h2>
        <div class="form-group">
          <label for="email">Your Email</label>
          <input type="email" v-model="form.email" required />
        </div>
        <div class="form-group">
          <label for="phone">Your Phone</label>
          <input type="tel" v-model="form.phone" required />
        </div>
        <div class="form-group">
          <label for="message">Your Message</label>
          <textarea v-model="form.message" required></textarea>
        </div>
        <button class="btn-submit" @click="sendEmail">Send</button>
      </div>
    </div>

    <!-- Horizontal Bar above Footer -->
    <div class="horizontal-bar bg-org"></div>

    <!-- Footer (sticky at the bottom) -->
    <footer class="footer bg-org-footer">
      <p>&copy; 2024 Bara-BYG. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      home: true,
      about: false,
      services: false,
      contact: false,
      showModal: false,
      form: {
        email: "",
        phone: "",
        message: "",
      },
    };
  },
  methods: {
    goHome() {
      this.home = true;
      this.about = false;
      this.services = false;
      this.contact = false;
    },
    goAbout() {
      this.home = false;
      this.about = true;
      this.services = false;
      this.contact = false;
    },
    goServices() {
      this.home = false;
      this.about = false;
      this.services = true;
      this.contact = false;
    },
    goContact() {
      this.home = false;
      this.about = false;
      this.services = false;
      this.contact = true;
    },
    sendEmail() {
      const emailBody = `
        Email: ${this.form.email}
        Phone: ${this.form.phone}
        Message: ${this.form.message}
      `;
      window.location.href = `mailto:balanonisim0@gmail.com?subject=Contact Form Submission&body=${encodeURIComponent(
        emailBody
      )}`;
      this.showModal = false; // Close the modal after sending
      this.resetForm(); // Reset form data
    },
    resetForm() {
      this.form.email = "";
      this.form.phone = "";
      this.form.message = "";
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
}

/* Footer Styling */
.footer {
  background-color: #f1f1f1;
  padding: 15px 0;
  color: #000;
  text-align: center; /* Ensures the footer stays at the bottom */
  margin-top: auto;
}

.horizontal-bar {
  background-color: #ff5500;
  height: 10px;
  width: 100%;
}

.bg-org {
  background-color: #fe5200; /* Footer background color */
}

.bg-org-footer {
  background-color: #f1f1f1;
}

.addMore:hover {
  box-shadow: 0px -2px 0px 0px #ffffff;
}

.about-container,
.services-container,
.contact-container {
  padding: 20px;
  background-color: #f1f1f1; /* Background for the sections */
  border-radius: 8px; /* Rounded corners */
  text-align: center; /* Center text */
  box-shadow: 0px 0px 0px 1px rgba(0, 0, 0, 0.171);
  flex-grow: 1; /* Allow sections to take remaining space */
}

.info-item {
  display: flex;
  align-items: center;
  justify-content: center; /* Center items */
  margin-bottom: 10px;
}

.info-item i {
  color: #ff5500; /* Icon color */
  margin-right: 10px;
}

.btn-email {
  background-color: #ff5500; /* Email button color */
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 16px;
  border-radius: 4px;
  margin-top: 10px; /* Space above button */
}

.btn-email:hover {
  background-color: #e64500; /* Darker orange on hover */
}

/* Modal styles */
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
}

.modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  width: 450px; /* Adjust width as needed */
  position: relative;
}

.close {
  position: absolute;
  top: 10px;
  right: 20px;
  font-size: 20px;
  cursor: pointer;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc; /* Default border color */
  border-radius: 4px; /* Rounded corners */
}

.services-container {
  padding: 10px; /* Reduced padding */
  max-width:1200px; /* Added max-width to constrain size */
  margin: auto; /* Center the container */
  background-color: #f1f1f1; /* Background for the section */
  border-radius: 8px; /* Rounded corners */
  text-align: center; /* Center text */
  box-shadow: 0px 0px 0px 1px rgba(0, 0, 0, 0.171);
  flex-grow: 1; /* Allow sections to take remaining space */
}

</style>
