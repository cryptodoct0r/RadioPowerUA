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
            <h5 class="text-white-75 font-weight-light mb-2">
              Send your questions, requests and more.
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
                  rows="2"
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
              v-scroll-to="'#listen'"
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

    <section id="listen" class="page-section">
      <h2 class="text-center">
        Start Listening
        <div class="logo">
          <b>L<span>i</span>v<span>e!</span>!</b>
        </div>
      </h2>
      <div class="wrapper">
        <div class="player">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item"
                style="background-image: url(https://raw.githubusercontent.com/muhammederdem/mini-player/master/img/3.jpg);"
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5">
              <audio controls class="mx-auto mt-5">
                <source src="https://streaming.radio.co/saa30502bd/listen">
              </audio>
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
              Radio Power UA has everything you need to get your day up and running in no time! Choose one of our daily programs, free to listen, and easy to contribute! No strings attached!
            </p>
          </div>
        </div>
      </div>
    </section>

    <section id="listen" class="page-section">
      <h2 class="text-center">
        Our Anchors
      </h2>
      <hr class="divider mt-4">
      <div class="wrapper py-5">
        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item one"
                style="background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Nuel</h4>
              <P>"An ardent student of life. A work in progress" favourite quote:  "I laugh when I hear the fish in the water is thirsty"</P>
            </div>
          </div>
        </div>

        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item"
                style="background-image: url(https://media.licdn.com/dms/image/C5603AQEaONu0ek_84Q/profile-displayphoto-shrink_200_200/0?e=1576108800&v=beta&t=ijGlar4OU5NpNHLo7rwEjVWKyQfDDLsT4oI3nyAiqgs); background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Joan</h4>
              <P>A charismatic active young woman who is non apologetic to say her mind and live by it. A true african woman in her prime.</P>
            </div>
          </div>
        </div>
      </div>
      <div class="wrapper pb-5">
        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item"
                style="background-image: url(https://images.unsplash.com/photo-1566663839087-89f4372ce32f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80); background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Malcom</h4>
              <P>Life is inherently risky. There is only one big risk you should avoid at all costs, and that is the risk of doing nothing.</P>
            </div>
          </div>
        </div>

        <!-- <div class="player mx-auto my-5 my-md-2 col-md-4">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item"
                style="background-image: url(https://images.unsplash.com/photo-1486044938437-01b06ad8098d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80); background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Joana Opoku</h4>
              <P>Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident esse quos illo magni, repellat nemo!</P>
            </div>
          </div>
        </div> -->
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
      <div class="container-fluid p-0">
        <h2 class="mt-0 text-center">
          Weeks Schedule.
        </h2>
        <hr class="divider my-4">
        <div class="row no-gutters">
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="https://images.unsplash.com/photo-1530530698525-77a06a1088f2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80" alt="">
              <div class="portfolio-box-caption">
                <h3 class="project-category">
                  Monday
                </h3>
                <h4 class="project-name">
                  School Talks
                </h4>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/2.jpg" alt="">
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Tuesday
                </h3>
                <h4 class="project-name">
                  Life Talks
                </h4>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="https://images.unsplash.com/photo-1474552226712-ac0f0961a954?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80" alt="">
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Wednesdays
                </h3>
                <h4 class="project-name">
                  Love and Relationships
                </h4>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="~/assets/img/portfolio/thumbnails/4.jpg" alt="">
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Thursday
                </h3>
                <h4 class="project-name">
                  Open house discussions
                </h4>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="https://images.unsplash.com/photo-1546074177-9e4787e95be7?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80" alt="">
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Friday
                </h3>
                <h4 class="project-name">
                  Celebrity Interviews
                </h4>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link class="portfolio-box" to="" @click.prevent>
              <img class="img-fluid" src="https://images.unsplash.com/photo-1539963011628-c076c7870cad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80" alt="">
              <div class="portfolio-box-caption p-3">
                <h3 class="project-category ">
                  Saturday
                </h3>
                <h4 class="project-name">
                  Round Table Discussions
                </h4>
              </div>
            </nuxt-link>
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

            <nuxt-link
              class="d-block"
              to=""
            >
              Telegram Channel
            </nuxt-link>
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
        <h5 class="medium text-center text-muted">
          Made with ❤️ &copy; in 2019 - {{ new Date().getFullYear() }} By <a href="https://neniemsu.com" target="_blank" rel="author">NeniEmsu</a>
        </h5>
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

#about {
  background: linear-gradient(
      115deg,
      rgba(54, 54, 54, 0.5) -4.64%,
      rgba(35, 36, 36, 0.5) 51.9%
    ),
    url("https://images.unsplash.com/photo-1478737270239-2f02b77fc618?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
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
  border: 2px solid;
  border-radius: 3px;
  text-align: center;
  text-decoration: none;
  display: block;
  font-family: sans-serif;
  font-size: 20px;
  width: 13em;
  padding: 5px 10px;
  font-weight: 600;
  background: rgba(0, 0, 0, 0.2);
  box-shadow: 0 0 0px 3px rgba(0, 0, 0, 0.2);
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

    audio {
      @media screen and (max-width: 350px) {
        width: 260px;
      }
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
      // background-image: url(~assets/img/emmanuelT.jpeg);
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

.one {
  background-image: url(~assets/img/emmanuelT.jpeg);
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
          // font-size: 0.85rem;
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
      @media screen and (max-width: 780px) {
        .portfolio-box-caption {
          opacity: 0.8;

          .project-category,
          .project-nane {
            opacity: 1;
          }
        }
      }
    }
  }
}

// neon lights

@import url(//fonts.googleapis.com/css?family=Vibur);

.logo {
  text-align: center;
  margin: auto;
  user-select: none;
}

.logo b {
  font: 400 4rem "Vibur";
  color: #fee;
  text-shadow: 0 -40px 100px, 0 0 2px, 0 0 1em #ff4444, 0 0 0.5em #ff4444,
    0 0 0.1em #ff4444, 0 10px 3px #000;
}
.logo b span {
  animation: blink linear infinite 2s;
}
.logo b span:nth-of-type(2) {
  animation: blink linear infinite 3s;
}
@keyframes blink {
  78% {
    color: inherit;
    text-shadow: inherit;
  }
  79% {
    color: #333;
  }
  80% {
    text-shadow: none;
  }
  81% {
    color: inherit;
    text-shadow: inherit;
  }
  82% {
    color: #333;
    text-shadow: none;
  }
  83% {
    color: inherit;
    text-shadow: inherit;
  }
  92% {
    color: #333;
    text-shadow: none;
  }
  92.5% {
    color: inherit;
    text-shadow: inherit;
  }
}
</style>
