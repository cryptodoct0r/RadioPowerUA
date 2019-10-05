<template>
  <div class="">
    <TheHeader />
    <section class="masthead">
      <div class="container h-100">
        <div class="row h-100 align-items-center justify-content-center text-center">
          <div class="col-lg-10 align-self-end">
            <h1 class="text-uppercase text-white font-weight-bold">
              Radio Power UA
            </h1>
            <hr class="divider my-4">
          </div>
          <div class="col-lg-8 align-self-baseline">
            <h5 class="text-white-75 font-weight-light mb-5">
              Get in touch with us anytime anyday
            </h5>
            <form
              id="form-box"
              class="p-2 row col-md-8 col-sm-10 mx-auto text-center"
              @submit.prevent="checkForm"
            >
              <div
                v-if="errors.length"
                class="text-left text-danger"
              >
                <b>Please correct the following error(s):</b>
                <ol>
                  <li
                    v-for="error in errors"
                    :key="error"
                    class="ml-3"
                  >
                    {{ error }}
                  </li>
                </ol>
              </div>
              <div
                v-if="success && !errors.length"
                class="text-center text-success mx-auto mb-2"
              >
                <b>Your message has been sent succesfully</b>
              </div>

              <label
                data-aos="fade-up"
                for="name"
                class="form-group input-group col-6"
              >
                <div class="input-group-prepend">
                  <span class="input-group-text"><i class="fas fa-user" /></span>
                </div>
                <input
                  v-model="name"
                  type="text"
                  name="name"
                  class="form-control"
                  placeholder="Name"
                  required
                >
              </label>

              <label
                data-aos="fade-up"
                for="phone"
                class="form-group input-group col-6"
              >
                <div class="input-group-prepend">
                  <span class="input-group-text"><i class="fas fa-phone" /></span>
                </div>
                <input
                  v-model="phone"
                  type="number"
                  name="phone"
                  class="form-control"
                  placeholder="Phone"
                  required
                >
              </label>

              <label
                data-aos="fade-up"
                for="subject"
                class="form-group input-group col-12"
              >
                <div class="input-group-prepend">
                  <span class="input-group-text"><i class="fas fa-at" /></span>
                </div>
                <input
                  v-model="subject"
                  type="text"
                  name="subject"
                  class="form-control"
                  placeholder="Subject"
                >
              </label>

              <label
                data-aos="fade-up"
                for="msg"
                class="form-group input-group col-12"
              >
                <div class="input-group-prepend">
                  <span class="input-group-text"><i class="fas fa-comment-alt" /></span>
                </div>
                <textarea
                  id="msg"
                  v-model="message"
                  name="msg"
                  class="form-control"
                  placeholder="Write your message"
                  cols="30"
                  rows="4"
                  required
                />
                </label>
              <label data-aos="fade-up" for="submit" class="form-group mx-auto">
                <input
                  id="submit"
                  type="submit"
                  name="submit"
                  class="btn-send"
                  value="Send"
                >
              </label>
            </form>
            <nuxt-link
              v-scroll-to="'#about'"
              to="/"
            >
              <div class="chevron-container mx-auto">
                <div class="chevron" />
                <div class="chevron" />
                <div class="chevron" />
                <span class="text">Scroll down</span>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </section>

    <section class="page-section">
      <h3 class="text-center">
        Start Listening Live!
      </h3>
      <div class="wrapper">
        <div class="player">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item"
                style="background-image: url(https://raw.githubusercontent.com/muhammederdem/mini-player/master/img/3.jpg);"
              />
            </div>
            <div class="player-iframe text-center mx-auto">
              <iframe
                src="https://streaming.radio.co/saa30502bd/listen"
                frameborder="0"
                width="260px"
                height="auto"
                class="mx-auto"
              />
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="page-section bg-primary">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-8 text-center">
            <h2 class="text-white mt-0">
              We've got what you need!
            </h2>
            <hr class="divider light my-4">
            <p class="text-white-50 mb-4">
              Start Bootstrap has everything you need to get your new website up and running in no time! Choose one of our open source, free to download, and easy to use themes! No strings attached!
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
      <div class="container-fluid p-0">
        <div class="row no-gutters">
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/1.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/1.jpg" alt="">
              <div class="portfolio-box-caption">
                <div class="project-category text-white-50">
                  Monday
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/2.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/2.jpg" alt="">
              <div class="portfolio-box-caption">
                <div class="project-category text-white-50">
                  Teusday
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/3.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/3.jpg" alt="">
              <div class="portfolio-box-caption">
                <div class="project-category text-white-50">
                  Wednesdays
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/4.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/4.jpg" alt="">
              <div class="portfolio-box-caption">
                <div class="project-category text-white-50">
                  Thursday
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/5.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/5.jpg" alt="">
              <div class="portfolio-box-caption">
                <div class="project-category text-white-50">
                  Friday
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
          <div class="col-lg-4 col-sm-6">
            <a class="portfolio-box" href="~/assets/img/portfolio/fullsize/6.jpg">
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/6.jpg" alt="">
              <div class="portfolio-box-caption p-3">
                <div class="project-category text-white-50">
                  Saturday
                </div>
                <div class="project-name">
                  Project Name
                </div>
              </div>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="page-section">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-8 text-center">
            <h2 class="mt-0">
              Feel Free To Get In Touch!
            </h2>
            <hr class="divider my-4">
            <p class="text-muted mb-5">
              For any enquires or questions, feel free to contact us here.
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-4 ml-auto text-center mb-5 mb-lg-0">
            <i class="fas fa-phone fa-3x mb-3 text-muted" />
            <div>
              <a
                href="tel:+380932589716"
                class=" m-auto"
              >
                <span>+380 93 258 9716</span>
              </a>
            </div>
          </div>
          <div class="col-lg-4 ml-auto text-center mb-5 mb-lg-0">
            <i class="fab fa-telegram fa-3x mb-3 text-muted" />

            <a
              class="d-block"
              href="https://web.telegram.org/#/im?p=c1231729418_435351677776982262"
            >Telegram Channel</a>
          </div>
          <div class="col-lg-4 mr-auto text-center">
            <i class="fas fa-envelope fa-3x mb-3 text-muted" />

            <a
              class="d-block"
              href="mailto:info@radiopowerua.com"
            >info@radiopowerua.com</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-light py-5">
      <div class="container">
        <div class="small text-center text-muted">
          Made &copy;2019 - {{ new Date().getFullYear() }} By <a href="https://neniemsu.com">NeniEmsu</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import axios from 'axios'
import TheHeader from '~/components/TheHeader.vue'

export default {
  components: {
    TheHeader
  },
  data () {
    return {
      errors: [],
      success: false,
      name: null,
      phone: null,
      subject: null,
      message: null
    }
  },
  methods: {
    checkForm (e) {
      this.errors = []
      this.success = false

      if (!this.name) {
        this.errors.push('Name Needed')
      }
      if (!this.phone) {
        this.errors.push('Phone Numbers Needed')
      }
      if (!this.subject) {
        this.errors.push('Subject Needed')
      }
      if (!this.message) {
        this.errors.push('Message Needed')
      }
      if (!this.errors.length) {
        this.sendMessage()
      }
      e.preventDefault()
    },
    sendMessage () {
      axios.post(
        `https://api.telegram.org/bot971666849:AAEPhgDVYttaZZxm35uC5IFU-YO3MdH8nh0/sendMessage?chat_id=-1001231729418&text=${this.name} ${this.phone} ${this.subject} ${this.message}`
      )
      this.name = this.phone = this.subject = this.message = null
      this.success = true
    }
  }
}
</script>

<style lang="scss">
.masthead {
  margin-top: -30px;
  height: 100vh;
  padding-top: 10rem;
  padding-bottom: calc(10rem - #{$navbar-height});
  background: linear-gradient(
      115deg,
      rgba(54, 54, 54, 0.5) -4.64%,
      rgba(35, 36, 36, 0.5) 51.9%
    ),
    url("~assets/img/eric-nopanen-8e0EHPUx3Mo-unsplash.jpg");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: scroll;
  background-size: cover;
  h1 {
    font-size: 2.25rem;
  }
  @media screen and (max-width: 425px) {
    padding-top: 5rem;
    padding-bottom: calc(10rem - #{$navbar-height});
  }
}

form {
  margin-bottom: 20px;
}

input,
textarea {
  background: transparent;
  border: none;
  border-bottom: 2px #ced4da solid;
  border-radius: 0;
  outline: none;
}

input.btn-send {
  color: white;
  font-size: 20px;
  &:hover,
  &:focus {
    background: transparent;
    border: none;
    border-bottom: 2px #ced4da solid;
    border-radius: 0;
    outline: none;
  }
}

.icon {
  display: inline-block;
  width: 1em;
  height: 1em;
  stroke-width: 0;
  stroke: currentColor;
  fill: currentColor;
}

.wrapper {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  // background: url(../img/bg.png) no-repeat center;
  background-size: cover;
  @media screen and (max-width: 700px), (max-height: 500px) {
    flex-wrap: wrap;
    flex-direction: column;
  }
}

.player {
  background: #000000;
  width: 410px;
  height: 480px;
  // box-shadow: 0px 55px 75px -10px rgba(76, 70, 124, 0.5);
  // box-shadow: 0px 55px 105px 10px rgba(76, 70, 124, 0.35);
  box-shadow: 0px 15px 35px -5px rgba(72, 73, 73, 0.32);
  border-radius: 15px;
  padding: 30px;
  @media screen and (max-width: 425px) {
    width: 90%;
    padding: 5px;
    height: 300px;
  }
  &__top {
    display: flex;
    align-items: flex-start;
    position: relative;
    z-index: 4;
    @media screen and (max-width: 576px), (max-height: 500px) {
      flex-wrap: wrap;
    }
  }

  &-iframe {
    position: absolute;
    width: 100%;
    top: 260px;

    @media screen and (max-width: 425px) {
      top: 100px;
    }
  }

  &-cover {
    width: 300px;
    height: 300px;

    margin-left: -70px;
    flex-shrink: 0;
    position: relative;
    z-index: 2;
    border-radius: 15px;
    // transform: perspective(512px) translate3d(0, 0, 0);
    // transition: all .4s cubic-bezier(.125, .625, .125, .875);
    z-index: 1;

    @media screen and (max-width: 425px) {
      margin-top: -70px;
      margin-bottom: 25px;
      width: 260px;
      height: 200px;
      margin-left: auto;
      margin-right: auto;
    }

    &__item {
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
      width: 100%;
      height: 100%;
      border-radius: 15px;
      position: absolute;
      left: 0;
      top: 0;

      &:before {
        content: "";
        background: inherit;
        width: 100%;
        height: 100%;
        box-shadow: 0px 10px 40px 0px rgba(76, 70, 124, 0.5);
        display: block;
        z-index: 1;
        position: absolute;
        top: 30px;
        transform: scale(0.9);
        filter: blur(10px);
        opacity: 0.9;
        border-radius: 15px;
      }

      &:after {
        content: "";
        background: inherit;
        width: 100%;
        height: 100%;
        box-shadow: 0px 10px 40px 0px rgba(76, 70, 124, 0.5);
        display: block;
        z-index: 2;
        position: absolute;
        border-radius: 15px;
      }
    }

    &__img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 15px;
      box-shadow: 0px 10px 40px 0px rgba(76, 70, 124, 0.5);
      user-select: none;
      pointer-events: none;
    }
  }
}

.chevron-container {
  position: relative;
  width: 24px;
  height: 24px;

  top: -20px;
  z-index: 16;
}

.chevron {
  // position: absolute;
  width: 28px;
  height: 8px;
  opacity: 0;
  transform: scale3d(0.5, 0.5, 0.5);
  animation: move 3s ease-out infinite;

  z-index: 100;
}

.chevron:first-child {
  animation: move 3s ease-out 1s infinite;
}

.chevron:nth-child(2) {
  animation: move 3s ease-out 2s infinite;
}

.chevron:before,
.chevron:after {
  content: " ";
  position: absolute;
  top: 0;
  height: 100%;
  width: 51%;
  background: whitesmoke;
}

.chevron:before {
  left: 0;
  transform: skew(0deg, 30deg);
}

.chevron:after {
  right: 0;
  width: 50%;
  transform: skew(0deg, -30deg);
}

@keyframes move {
  25% {
    opacity: 1;
  }
  33% {
    opacity: 1;
    transform: translateY(30px);
  }
  67% {
    opacity: 1;
    transform: translateY(40px);
  }
  100% {
    opacity: 0;
    transform: translateY(55px) scale3d(0.5, 0.5, 0.5);
  }
}

.text {
  display: block;
  margin-top: -25px;
  margin-left: -30px;
  font-family: "Helvetica Neue", "Helvetica", Arial, sans-serif;
  font-size: 12px;
  color: whitesmoke;
  text-transform: uppercase;
  white-space: nowrap;
  opacity: 0.25;
  animation: pulse 2s linear alternate infinite;
}

@keyframes pulse {
  to {
    opacity: 1;
  }
}

@media screen and (max-width: 425px) {
  .chevron-container {
    position: relative;
    width: 24px;
    height: 24px;

    cursor: pointer;
    z-index: 16;
  }
}

// Styling for the portfolio section
#portfolio {
  .container-fluid {
    max-width: 1920px;
    .portfolio-box {
      position: relative;
      display: block;
      .portfolio-box-caption {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;

        width: 100%;
        height: 100%;

        position: absolute;
        bottom: 0;

        text-align: center;
        opacity: 0;

        color: white;
        background: fade-out($primary, 0.1);
        transition: opacity 0.25s ease;
        text-align: center;
        .project-category {
          font-family: $font-family-sans-serif;
          font-size: 0.85rem;
          font-weight: 600;
          text-transform: uppercase;
        }
        .project-name {
          font-size: 1.2rem;
        }
      }
      &:hover {
        .portfolio-box-caption {
          opacity: 1;
        }
      }
    }
  }
}
</style>
