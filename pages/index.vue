<template>
  <div>
    <b-modal
      id="modal-1"
      ref="modal"
      title="Wanna be live on the show?"
      hide-footer
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
      <form
        ref="form"
        @submit.stop.prevent="checkForm"
      >
        <b-form-group
          :state="nameState"
          label="Name"
          label-for="name-input"
          invalid-feedback="Name is required"
        >
          <b-form-input
            id="name-input"
            v-model="name"
            :state="nameState"
            required
          />
        </b-form-group>
        <b-form-group
          :state="nameState"
          label="Number"
          label-for="number-input"
          invalid-feedback="Number is required"
        >
          <b-form-input
            id="number-input"
            v-model="phone"
            :state="numberState"
            required
          />
        </b-form-group>
        <label
          data-aos="fade-up"
          for="submit"
          class="form-group mx-auto"
        >
          <input
            id="submit"
            type="submit"
            name="submit"
            class="btn-call"
            value="Send"
          >
        </label>
      </form>
    </b-modal>
    <div id="sidebar">
      <div class="social facebook">
        <a
          href="https://www.facebook.com/studliferadio/"
          target="_blank"
        >
          <p>Like on Facebook <i class="fab fa-facebook " /> </p>
        </a>
      </div>
      <div class="social twitter">
        <a
          href="https://twitter.com/Radiopower_UA"
          target="_blank"
        >
          <p>Follow on Twitter<i class="fab fa-twitter" /> </p>
        </a>
      </div>
      <div class="social instagram">
        <a
          href="https://www.instagram.com/radiopower_ua/"
          target="_blank"
        >
          <p>&nbsp; Follow on Instagram<i class="fab fa-instagram" /> </p>
        </a>
      </div>
      <div class="social youtube">
        <a
          href="https://www.youtube.com"
          target="_blank"
        >
          <p>Subscribe on Youtube<i class="fab fa-youtube" /> </p>
        </a>
      </div>
      <div class="social call">
        <nuxt-link
          v-b-modal.modal-1
          to=""
        >
          <p>Lets Call You!<i class="fas fa-phone" /> </p>
        </nuxt-link>
      </div>
    </div>
    <TheHeader />
    <TheHero />

    <!-- <TheSwiper /> -->
    <!-- <section class="masthead">
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
    </section> -->

    <!-- <section
      id="listen"
      class="page-section"
    >
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
              <audio
                controls
                autoplay
                class="mx-auto mt-5"
              >
                <source src="https://node-08.zeno.fm/2nbarxy58gruv?rj-ttl=5&rj-token=AAABbaz-hYmOGrId5LpDft3ShkPFG2ZoMeFGDoQpcTKrHQs2CDcwyQ">
              </audio>
            </div>
          </div>
        </div>
      </div>
    </section> -->

    <!-- About Section -->
    <section
      id="about"
      class="page-section bg-primary"
    >
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

    <!-- <section
      id="listen"
      class="page-section"
    >
      <h2 class="text-center">
        Our Anchors
      </h2>
      <hr class="divider mt-4">
      <div class="wrapper pt-5">
        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item nuel"
                style="background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Nuel</h4>
              <P>"An ardent student of life. A work in progress" favourite quote: "I laugh when I hear the fish in the water is thirsty"</P>
            </div>
          </div>
        </div>

        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item joan"
                style="background-position: top center;"
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Joan</h4>
              <P>A charismatic active young woman who is non apologetic to say her mind and live by it. A true african woman in her prime.</P>
            </div>
          </div>
        </div>
      </div>
      <div class="wrapper py-5">
        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item melcom"
                style="background-position: top center; "
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Malcom</h4>
              <P>Med student from Ghana, Love novels and writing. "We are all here on a mission and should strive everyday to make proactive steps towards achieving that mission."</P>
            </div>
          </div>
        </div>

        <div class="player mx-auto my-5 my-md-2">
          <div class="player__top">
            <div class="player-cover">
              <div
                class="player-cover__item bolu"
                style="background-position: top center;"
              />
            </div>
            <div class="player-iframe text-center mx-auto mt-5 text-white">
              <h4>Ogunjumelo Boluwatifemito</h4>
              <P>Medical student 3rd year My energy 💯</P>
            </div>
          </div>
        </div>
      </div>
    </section> -->

    <!-- Portfolio Section -->
    <section id="portfolio">
      <div class="container-fluid p-0 mb-2">
        <h2 class="mt-4 text-center">
          Our Team.
        </h2>
        <hr class="divider my-4">
        <div class="row no-gutters">
          <div class="col-lg-4 col-sm-6">
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="~/assets/img/emmanuelT.jpeg"
                alt=""
              >
              <div class="portfolio-box-caption">
                <h3 class="project-category">
                  Nuel
                </h3>
                <p class="project-name w-75">
                  "An ardent student of life. A work in progress" favourite quote: "I laugh when I hear the fish in the water is thirsty"
                </p>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="~/assets/img/joan.jpeg"
                alt=""
              >
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Joan
                </h3>
                <p class="project-name w-75">
                  A charismatic active young woman who is non apologetic to say her mind and live by it. A true african woman in her prime.
                </p>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="~/assets/img/melcom.jpeg"
                alt=""
              >
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Malcom
                </h3>
                <p class="project-name w-75">
                  Med student from Ghana, Love novels and writing. "We are all here on a mission and should strive everyday to make proactive steps towards achieving that mission."
                </p>
              </div>
            </nuxt-link>
          </div>
          <div class="col-lg-4 col-sm-6">
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="~assets/img/bolu.jpeg"
                alt=""
              >
              <div class="portfolio-box-caption">
                <h3 class="project-category ">
                  Ogunjumelo Boluwatifemito
                </h3>
                <p class="project-name w-75">
                  Medical student 3rd year My energy 💯
                </p>
              </div>
            </nuxt-link>
          </div>
          <!-- <div class="col-lg-4 col-sm-6">
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="https://images.unsplash.com/photo-1546074177-9e4787e95be7?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80"
                alt=""
              >
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
            <nuxt-link
              class="portfolio-box"
              to=""
              @click.prevent
            >
              <img
                class="img-fluid"
                src="https://images.unsplash.com/photo-1539963011628-c076c7870cad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=650&h=350&q=80"
                alt=""
              >
              <div class="portfolio-box-caption p-3">
                <h3 class="project-category ">
                  Saturday
                </h3>
                <h4 class="project-name">
                  Round Table Discussions
                </h4>
              </div>
            </nuxt-link>
          </div> -->
        </div>
      </div>
    </section>

    <h2 class="mt-4 text-center">
      Weekly Lineup!
    </h2>
    <hr class="divider my-4">

    <TheSchedule class="mb-4" />

    <h2 class="mt-4 text-center">
      Also Listen to Radio Power UA on:
    </h2>
    <hr class="divider my-4">

    <div class="container mb-4">
      <div class="row">
        <div class="col-sm-4 my-2">
          <div>
            <div class="text-center">
              <figure>
                <a
                  href="https://zeno.fm/radiopower-ua"
                  target="_blank"
                >
                  <svg
                    viewBox="0 0 140.55 54.35"
                    width="120"
                    height="120"
                  >
                    <g>
                      <path
                        d="M46.11 45.24l-4 5.62h-.41l-4-5.62v9.11h-1.9V42.48H38L41.91 48l3.9-5.56H48v11.91h-1.9zm17.06 9.1H54.4V42.46h8.72v1.85H56.3v3.21h6.55v1.76H56.3v3.19h6.87zM73.5 42.46a5.63 5.63 0 0 1 6 5.84 5.63 5.63 0 0 1-6 6H69V42.46zm-2.61 10h2.61a3.87 3.87 0 0 0 4.07-4.22 3.86 3.86 0 0 0-4.07-4h-2.61zm14.23 1.88V42.46H87v11.88zm16.49-2.5h-6.43l-1.12 2.49H92l5.33-11.87h2.07l5.33 11.87h-2zm-3.21-7.38l-2.51 5.65h5z"
                        fill="#fff"
                      />
                      <path
                        fill="#49a1d0"
                        d="M76.13 29.29V2.03l24.96 24.96V4.33h1.9v27.26L78.04 6.64v22.65h-1.91z"
                      />
                      <circle
                        fill="#49a1d0"
                        cx="102.04"
                        cy="4.34"
                        r="3.86"
                      />
                      <circle
                        fill="#49a1d0"
                        cx="77.08"
                        cy="29.29"
                        r="3.86"
                      />
                      <path
                        fill="#49a1d0"
                        d="M28.81 29.77H1.55L26.51 4.81H3.86V2.9h27.26L6.16 27.86h22.65v1.91z"
                      />
                      <circle
                        fill="#49a1d0"
                        cx="3.86"
                        cy="3.86"
                        r="3.86"
                      />
                      <circle
                        fill="#49a1d0"
                        cx="28.81"
                        cy="28.81"
                        r="3.86"
                      />
                      <path
                        class="hover-light"
                        fill="#49a1d0"
                        d="M126.39 31a14.16 14.16 0 1 1 14.16-14.16A14.18 14.18 0 0 1 126.39 31zm0-25.91a11.75 11.75 0 1 0 11.75 11.75 11.76 11.76 0 0 0-11.75-11.78zM41.71 15.35h23.57v1.97H41.71zm0-12.45h23.57v1.97H41.71zm0 24.9h23.57v1.97H41.71z"
                      />
                    </g>
                  </svg>
                </a>
              </figure>
              <h5>
                Zeno Media
              </h5>
            </div>
          </div>
        </div>
        <div class="col-sm-4 my-2">
          <div>
            <div class="text-center">
              <figure>
                <a
                  href="https://tunein.com/radio/RadiopowerUA-s300866/"
                  target="_blank"
                ><img
                  width="120"
                  height="120"
                  src="~/assets/img/tune-in-150x150.jpg"
                  class="img-fluid rounded-circle"
                  alt=""
                  sizes="(max-width: 150px) 100vw, 150px"
                ></a>
              </figure>
              <h5>
                TuneIN.com
              </h5>
            </div>
          </div>
        </div>
        <div class="col-sm-4 my-2">
          <div>
            <div class="text-center">
              <figure>
                <a
                  href="https://radio.garden/listen/radio-power-ua/iWTyUgC-"
                  target="_blank"
                ><img
                  width="120"
                  height="120"
                  src="~/assets/img/radio-garden-150x150.jpg"
                  class="img-fluid rounded-circle"
                  alt=""
                  sizes="(max-width: 150px) 100vw, 150px"
                ></a>
              </figure>
              <h5>
                RadioGarden.com
              </h5>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Contact Section -->
    <section
      id="contact"
      class="page-section"
    >
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-8 text-center">
            <h2 class="mt-0">
              Events
            </h2>
            <hr class="divider my-4">
            <p class="text-muted mb-5">
              Comming soon!
            </p>
          </div>
        </div>
        <!-- <div class="row">
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
        </div> -->
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-light py-5">
      <div class="container">
        <h5 class="medium text-center text-muted">
          Made with ❤️ &copy; in 2019 - {{ new Date().getFullYear() }} By <a
            href="https://neniemsu.com"
            target="_blank"
            rel="author"
          >NeniEmsu</a>
        </h5>
      </div>
    </footer>
  </div>
</template>

<script>
import axios from 'axios'
import TheHeader from '~/components/TheHeader.vue'
import TheHero from '~/components/TheHero'
// import TheSwiper from '~/components/TheSwiper'
import TheSchedule from '~/components/TheSchedule'

export default {
  components: {
    TheHeader,
    TheHero,
    // TheSwiper,
    TheSchedule
  },
  data () {
    return {
      errors: [],
      success: false,
      name: null,
      phone: null
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
      if (!this.errors.length) {
        this.sendMessage()
      }
      e.preventDefault()
    },
    sendMessage () {
      axios.post(
        `https://api.telegram.org/bot971666849:AAEPhgDVYttaZZxm35uC5IFU-YO3MdH8nh0/sendMessage?chat_id=-1001231729418&text=Please call me, Name:  ${this.name}, Phone Number:  ${this.phone}`
      )
      this.name = this.phone = null
      this.success = true
    }
  }
}
</script>

<style lang="scss" scoped>
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

.nuel {
  background-image: url(~assets/img/emmanuelT.jpeg);
}

.joan {
  background-image: url(~assets/img/joan.jpeg);
}

.melcom {
  background-image: url(~assets/img/melcom.jpeg);
}

.bolu {
  background-image: url(~assets/img/bolu.jpeg);
}

// .chevron-container {
//   position: relative;
//   width: 24px;
//   height: 24px;

//   top: -20px;
//   z-index: 16;
// }

// .chevron {
//   // position: absolute;
//   width: 28px;
//   height: 8px;
//   opacity: 0;
//   transform: scale3d(0.5, 0.5, 0.5);
//   animation: move 3s ease-out infinite;

//   z-index: 100;
// }

// .chevron:first-child {
//   animation: move 3s ease-out 1s infinite;
// }

// .chevron:nth-child(2) {
//   animation: move 3s ease-out 2s infinite;
// }

// .chevron:before,
// .chevron:after {
//   content: " ";
//   position: absolute;
//   top: 0;
//   height: 100%;
//   width: 51%;
//   background: whitesmoke;
// }

// .chevron:before {
//   left: 0;
//   transform: skew(0deg, 30deg);
// }

// .chevron:after {
//   right: 0;
//   width: 50%;
//   transform: skew(0deg, -30deg);
// }

// @keyframes move {
//   25% {
//     opacity: 1;
//   }
//   33% {
//     opacity: 1;
//     transform: translateY(30px);
//   }
//   67% {
//     opacity: 1;
//     transform: translateY(40px);
//   }
//   100% {
//     opacity: 0;
//     transform: translateY(55px) scale3d(0.5, 0.5, 0.5);
//   }
// }

// .text {
//   display: block;
//   margin-top: -25px;
//   margin-left: -30px;
//   font-family: "Helvetica Neue", "Helvetica", Arial, sans-serif;
//   font-size: 12px;
//   color: whitesmoke;
//   text-transform: uppercase;
//   white-space: nowrap;
//   opacity: 0.25;
//   animation: pulse 2s linear alternate infinite;
// }

// @keyframes pulse {
//   to {
//     opacity: 1;
//   }
// }

// @media screen and (max-width: 425px) {
//   .chevron-container {
//     position: relative;
//     width: 24px;
//     height: 24px;

//     cursor: pointer;
//     z-index: 16;
//   }
// }

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
        transition: opacity 0.5s ease;
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
          width: 100%;
          height: 50%;
          opacity: 0.6;
          transition: opacity 0.5s ease;

          .project-category,
          .project-nane {
            opacity: 1;
          }

          &:hover,
          &:focus,
          &:focus-within {
            height: 100%;
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

#sidebar {
  top: 22%;
  height: 250px;
  width: 10px;
  position: fixed;
  text-align: center;
  padding: 10px;
  margin-left: 10px;
  z-index: 10;

  p i {
    left: 40px;
    position: relative;
    vertical-align: middle;
    text-align: center;
    font-size: 24px;
  }

  .social {
    margin-left: -200px;
    width: 230px;
    padding: 0;
    display: inline-table;
    height: 0px;
    background-color: rgba(128, 128, 128, 0.73);
    transition-property: margin-left;
    -moz-transition-property: margin-left;
    transition-duration: 0.2s;
    -moz-transition-duration: 0.2s;
    transition-delay: 0.2s;
    -moz-transition-delay: 0.2s;
    -ms-transition-property: margin-left;
    -ms-transition-duration: 0.2s;
    -ms-transition-delay: 0.2s;
    -o-transition-property: margin-left;
    -o-transition-duration: 0.2s;
    -o-transition-delay: 0.2s;
    -webkit-transition-property: margin-left;
    -webkit-transition-duration: 0.2s;
    -webkit-transition-delay: 0.2s;
    box-shadow: 0px 0px 6px 0px #3e3d3d;
    cursor: pointer;
  }

  .social:hover {
    margin-left: -30px;
    width: 230px;
    background-color: #3b5998;
  }

  .facebook:hover {
    background-color: #3b5998;
  }

  .twitter:hover {
    background-color: #4099ff;
  }

  .instagram:hover {
    background: linear-gradient(
      45deg,
      #f09433 0%,
      #e6683c 25%,
      #dc2743 50%,
      #cc2366 75%,
      #bc1888 100%
    );
  }

  .call p i {
    left: 52px;
  }

  .instagram p i {
    left: 28px;
  }

  .youtube p i {
    left: 25px;
  }

  .youtube:hover {
    background-color: #e52d27;
  }

  .call:hover {
    background-color: #2ecc71;
  }

  a {
    text-decoration: none;
    vertical-align: middle;
    text-align: center;
    line-height: 2.5;
  }

  p {
    color: white;
    position: relative;
    top: 5px;
    left: -10px;
    font-family: "Lato";
  }
}

input.btn-call {
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
  transition: 500ms all ease-in-out;
  &:hover,
  &:focus {
    background: transparent;
    border: none;
    border-bottom: 2px #ced4da solid;
    border-radius: 0;
    outline: none;
    color: #ced4da;
  }
}
</style>
