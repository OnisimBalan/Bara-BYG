<template>
  <div id="app" class="d-flex flex-column back-byg" style="height: 100vh">
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-org p-4">
      <div class="d-flex">
        <div class="right-space-nav">
          <a href="/index.html"
            ><img src="/src/assets/logo.png"  height="40" style="object-fit: contain;"
          /></a>
        </div>
        <div>
          <a class="ml-5 navbar-brand addMore byg-font" @click="goHome" href="#"
            >Home</a
          >
          <a
            class="ml-5 navbar-brand addMore byg-font"
            @click="goServices"
            href="#"
            >Services</a
          >
          <a
            class="ml-5 navbar-brand addMore byg-font"
            @click="goContact"
            href="#"
            >Contact</a
          >
          <a
            class="ml-5 navbar-brand addMore byg-font"
            @click="goAbout"
            href="#"
            >About</a
          >
        </div>
      </div>
    </nav>

    <!-- Page content (takes remaining height) -->
    <div class="flex-grow-1 d-flex justify-content-center align-items-center">
      <div v-if="home" class="contact-container">
        <div class="container">
          <b>Hello,</b>
          <div class="text-description mt-2">
            <a
              style="
                font-family: system-ui, -apple-system, BlinkMacSystemFont,
                  'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
                  'Helvetica Neue', sans-serif;
              "
            >
              Welcome to <strong>Bara BYG</strong> trusted source for web design
              specialized in the construction industry. We are exclusively
              dedicated to creating websites for companies in the construction
              sector, offering customized and innovative solutions for your
              business. Whether you’re a builder or part of the construction
              field, we are committed to helping you showcase your business in
              the best possible light online.
            </a>
          </div>
        </div>
      </div>

      <div v-if="services" class="services-container byg-font">
        <div id="servicesCarousel" class="carousel slide" data-ride="carousel">
          <div class="carousel-inner">
            <!-- Slide 1 -->
            <div class="carousel-item active">
              <div class="content-wrapper">
                <h4 class="mb-3"><strong>Construction Planning</strong></h4>
                <h6>
                  Our mission is to provide professional construction planning
                  services, tailored to meet diverse project needs.
                </h6>
                <img
                  src="/src/assets/logo.png"
                  width="1000"
                  height="505"
                  style="object-fit: contain;"
                  alt="Construction Planning"
                />
              </div>
            </div>
            <!-- Slide 2 -->
            <div class="carousel-item">
              <div class="content-wrapper">
                <h4 class="mb-3"><strong>Residential Construction</strong></h4>
                <h6>
                  We specialize in residential construction, creating homes
                  designed with care and expertise.
                </h6>
                <img
                  src="/src/assets/logo.png"
                  width="1000"
                  height="505"
                  style="object-fit: contain;"
                  alt="Residential Construction"
                />
              </div>
            </div>
            <!-- Slide 3 -->
            <div class="carousel-item">
              <div class="content-wrapper">
                <h4 class="mb-3"><strong>Renovation Services</strong></h4>
                <h6>
                  Transforming spaces through high-quality renovation and
                  remodeling solutions.
                </h6>
                <img
                  src="/src/assets/back.png"
                  width="1000"
                  height="505"
                  style="object-fit: contain;"
                  alt="Renovation Services"
                />
              </div>
            </div>
          </div>
          <!-- Controls -->
          <a
            class="carousel-control-prev"
            href="#servicesCarousel"
            role="button"
            data-slide="prev"
          >
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
          </a>
          <a
            class="carousel-control-next"
            href="#servicesCarousel"
            role="button"
            data-slide="next"
          >
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
          </a>
        </div>
      </div>

      <div v-if="contact" class="contact-container byg-font">
        <!-- Company Contact Info -->
        <div class="info-item">
          <span class=""> <strong>Contact BARA-BYG Company</strong></span>
        </div>
        <div class="info-item mb-3">
          <i class="fas fa-envelope"></i>
          <span>Phone: +4571368503</span>
        </div>
        <div class="info-item mb-3">
          <i class="fas fa-envelope"></i>
          <span>Email: bara-byg@gmail.com</span>
        </div>

        <div class="info-item">
          <i class="fas fa-envelope"></i>
          <span class="mr-2"><strong>Adress:</strong></span>
          <span>6900 Skjern, Vestergade 2, Denmark </span>
          <span class="ml-2"
            ><a
              href="https://www.google.com/maps/place/Vestergade+2,+6900+Skjern,+Danemarca/@55.9597185,8.6351445,15.5z/data=!4m6!3m5!1s0x464babc6f0ab2275:0x5ed2170642df996e!8m2!3d55.959677!4d8.6428002!16s%2Fg%2F11c5lxyckl?entry=ttu&g_ep=EgoyMDI1MDExNS4wIKXMDSoASAFQAw%3D%3D"
              >See adress</a
            ></span
          >
        </div>

        <div class="info-item">
          <span class="d-block mr-2"><strong>Director:</strong></span>
          <span>Ionut Bara</span>
          <span class="ml-2"
            ><a href="https://www.facebook.com/bara.ionut.1986"
              >Go to social</a
            ></span
          >
        </div>

        <div class="info-item">
          <span class="d-block mr-2"><strong>Personal email:</strong></span>
          <span>bara.ionut@example.com</span>
        </div>

        <div class="info-item">
          <i class="fas fa-envelope"></i>
          <span
            ><a
              href="https://proff.dk/firma/bara-byg-aps/skjern/pedeltjenester/0JE0N7I01TI"
              >Verify online</a
            ></span
          >
        </div>

        <!-- Email Button -->
        <div class="info-item">
          <button class="btn-email d-block" @click="showModal = true">
            Send Email
          </button>
        </div>
      </div>

      <div v-if="about" class="about-container byg-font">
        <table class="table table-borderless">
          <tbody>
            <tr>
              <th scope="row">Legal name</th>
              <td>BARA CONSTRUCTION ApS</td>
              <td>Address</td>
              <td>Vestergade 2, 6900 Skjern</td>
            </tr>
            <tr>
              <th scope="row">CVR number</th>
              <td>32566723</td>
              <td>Postal address</td>
              <td>Vestergade 2, 6900 Skjern</td>
            </tr>
            <tr>
              <th scope="row">Start date</th>
              <td>16.11.2009</td>
              <td>Company capital</td>
              <td>126</td>
            </tr>
            <tr>
              <th scope="row">Company type</th>
              <td>Private limited company</td>
              <td></td>
              <td></td>
            </tr>
            <tr>
              <th scope="row">Number of employees</th>
              <td>17</td>
              <td></td>
              <td></td>
            </tr>
            <tr>
              <th scope="row">NACE industry</th>
              <td>
                <a href="https://proff.dk/segmentering?naceIndustry=81.10.00"
                  >811000 Provision of combined auxiliary services in connection
                  with the operation of real estate</a
                >
              </td>
              <td></td>
              <td></td>
            </tr>
          </tbody>
        </table>

        <!-- <div class="company-info">
          <h3>Informații oficiale ale companiei</h3>
          <div class="info-item-about">
            <p class="mr-2"><strong>Scop:</strong></p>
            <p>
              Scopul companiei este vânzarea de servicii în cadrul diferitelor
              meserii de construcții și alte afaceri conexe, la discreția
              conducerii
            </p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Denumirea legală:</strong></p>
            <p>BARA BYG ApS</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>CVR nr:</strong></p>
            <p>32566723</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Data de începere:</strong></p>
            <p>16.11.2009</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Forma de companie:</strong></p>
            <p>Societate cu răspundere limitată</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Numărul de angajați:</strong></p>
            <p>17</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Industria NACE:</strong></p>
            <p>
              811000 Furnizare de servicii de sprijin combinate în legătură cu
              exploatarea bunurilor imobiliare
            </p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Director:</strong></p>
            <p>Ionut Bara</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Adresa:</strong></p>
            <p>Vestergade 2, 6900 Skjern</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Adresa postală:</strong></p>
            <p>Vestergade 2, 6900 Skjern</p>
          </div>
          <div class="info-item-about">
            <p class="mr-2"><strong>Capitalul companiei:</strong></p>
            <p>126</p>
          </div>
        </div> -->
      </div>
    </div>

    <!-- Email Modal -->
    <div v-if="showModal" class="modal byg-font">
      <div class="modal-content">
        <span class="close" @click="showModal = false">&times;</span>
        <h2>Get in touch</h2>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" v-model="form.email" required />
        </div>
        <div class="form-group">
          <label for="phone">Phone</label>
          <input type="tel" v-model="form.phone" required />
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea v-model="form.message" required></textarea>
        </div>
        <button class="btn-submit btn btn-primary" @click="sendEmail">
          Send
        </button>
      </div>
    </div>

    <!-- Horizontal Bar above Footer -->
    <div class="horizontal-bar bg-org"></div>

    <!-- Footer (sticky at the bottom) -->
    <footer class="footer bg-org-footer">
      <div class="d-flex justify-content-center">
        <div style="margin-right: 20px; width: 250px">
          <a href="/index.html"
            ><img src="/src/assets/logo.png" width="60" style="object-fit: contain;"
          /></a>
          <p class="byg-font byg-font-color mt-3">
            Laying the digital foundations for success in the construction
            industry
          </p>
        </div>
        <div>
          <p class="byg-font byg-font-color"><strong>Contact</strong></p>
          <p class="byg-font byg-font-color">Phone: +4571368503</p>
          <p class="byg-font byg-font-color">Email: bara-byg@gmail.com</p>
        </div>
      </div>
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
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
}

/* Footer Styling */
.footer {
  background-color: #f1f1f1;
  padding-top: 20px;
  color: #000;
  margin-top: auto;
}

.horizontal-bar {
  background-color: #ff5500;
  height: 4px;
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
  background-color: #f1f1f1dc; /* Background for the sections */
  box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.116);
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

.info-item-about {
  text-align: start;
  display: flex;
  align-items: initial;
  justify-content: center; /* Center items */
  margin-bottom: 10px;
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
  padding: 20px; /* Reduced padding */
  margin: auto; /* Center the container */
  border-radius: 8px; /* Rounded corners */
  text-align: center; /* Center text */
  background-color: #f1f1f1dc; /* Background for the sections */
  box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.116);
  flex-grow: 1; /* Allow sections to take remaining space */
}

.right-space-nav {
  margin-right: 40px;
}

.container {
  padding: 20px;
}

.byg-font {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}

.byg-font-color {
  color: #777777cc;
  font-size: 13px;
}

.back-byg {
  background-image: url(/src/assets/byg.jpg);
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  background-size: cover;
}
</style>
