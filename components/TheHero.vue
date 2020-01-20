<template>
  <div class="container text-center">
    <div class="hero-header">
      <h1 class="intro-sec ">
        <div class="logo">
          <h1 class="mx-auto text-center">
            <b>Ra<span>d</span>io <span>Po</span>wer <span>UA</span></b>
          </h1>

          <p class="col-8 mx-auto d-none d-sm-block">
            Discover your power, the power within !!!
          </p>
        </div>
      </h1>

      <div class="home-hiw">
        <form
          id="form-box"
          class=" row"
          @submit.prevent="checkForm"
        >
          <h2>Contact Us:</h2>
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
            class="form-group input-group"
          >
            <div class="input-group-prepend">
              <span class="input-group-text"><i class="fas fa-user" /></span>
            </div>
            <input
              v-model="name"
              type="text"
              name="name"
              class="form-control"
              placeholder="Name/nickname"
              required
            >
          </label>

          <label
            data-aos="fade-up"
            for="subject"
            class="form-group input-group"
          >
            <div class="input-group-prepend">
              <span class="input-group-text"><i class="fas fa-at" /></span>
            </div>
            <input
              v-model="subject"
              type="text"
              name="subject"
              class="form-control"
              placeholder="Subject/Location"
            >
          </label>

          <label
            data-aos="fade-up"
            for="msg"
            class="form-group input-group"
          >
            <div class="input-group-prepend">
              <span class="input-group-text"><i class="fas fa-comment-alt" /></span>
            </div>
            <textarea
              id="msg"
              v-model="message"
              name="msg"
              class="form-control"
              placeholder="Write your message, questions or requests."
              cols="30"
              rows="3"
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
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
// import TheHeader from '~/components/TheHeader.vue'
// import TheHero from '~/components/TheHero'
// import TheSchedule from '~/components/TheSchedule'

export default {
  components: {
    // TheHeader,
    // TheHero
    // TheSchedule
  },
  data () {
    return {
      errors: [],
      success: false,
      name: null,
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
        `https://api.telegram.org/bot971666849:AAEPhgDVYttaZZxm35uC5IFU-YO3MdH8nh0/sendMessage?chat_id=-1001231729418&text=%0AName: ${this.name}, %0ASubject: ${this.subject}, %0AMessage: ${this.message}`
      )
      this.name = this.subject = this.message = null
      this.success = true
    }
  }
}
</script>

<style lang="scss" scoped>
.hero-header {
  padding-bottom: 60px;
}
p {
  font-size: 2rem;
  color: white;
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

.hero-header {
  margin: 30px 0;
  width: 100%;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.intro-sec {
  width: 65%;
  height: 400px;
  background: #5b52f8;
  background-image: linear-gradient(
      115deg,
      rgba(54, 54, 54, 0.25) -4.64%,
      rgba(35, 36, 36, 0.25) 51.9%
    ),
    url(https://abuk.com.ua/img/stick3.png);
  background-position: center;
  background-size: cover;
  border-radius: 3px;
  padding: 2rem;
  box-shadow: 0 12px 18px 2px rgba(34, 0, 51, 0.04),
    0 6px 22px 4px rgba(7, 48, 114, 0.12),
    0 6px 10px -4px rgba(14, 13, 26, 0.12);
  display: flex;
  align-items: center;
}

.intro-sec h1 {
  max-width: 90%;
  text-transform: capitalize;
  color: #fff;
  line-height: 1.3;
  font-size: 50px;
}

.home-hiw {
  width: 32%;
  height: 400px;
  padding: 10px 2rem;
  border-radius: 3px;
  display: flex;
  align-items: center;
  background: #fff;
  box-shadow: 0 12px 18px 2px rgba(34, 0, 51, 0.04),
    0 6px 22px 4px rgba(7, 48, 114, 0.06),
    0 6px 10px -4px rgba(14, 13, 26, 0.06);
}

.block-list {
  display: block;
  position: relative;
}

.block-list li {
  display: flex;
  align-items: center;
  font-size: 20px;
  height: 65px;
  width: 100%;
}

.block-list li .icon-hldr {
  width: 55px;
  height: 55px;
  border-radius: 50%;
  background: #f3f4f5;
  margin-right: 10px;
  padding: 10px;
}

.block-list li .icon-hldr svg {
  fill: #5b52f8 !important;
}

@media only screen and (max-width: 1024px) {
  .hero-header {
    display: block;
  }
  .intro-sec,
  .home-hiw {
    width: 100% !important;
  }
}

@media only screen and (max-width: 768px) {
  .intro-sec {
    height: 250px;
    padding: 1rem;
  }
  .intro-sec h1 {
    width: 100% !important;
    font-size: 35px;
    line-height: 1.5;
  }
}

// @import url(//fonts.googleapis.com/css?family=Vibur);

.logo h1 {
  user-select: none;
}

.logo h1 b {
  font: 400 4rem "Vibur";
  color: #fee;
  text-shadow: 0 -40px 100px, 0 0 2px, 0 0 1em #ff4444, 0 0 0.5em #ff4444,
    0 0 0.1em #ff4444, 0 10px 3px #000;
}
.logo h1 b span {
  animation: blink linear infinite 2s;
}
.logo h1 b span:nth-of-type(2) {
  animation: blink linear infinite 3s;
}
.logo h1 b span:nth-of-type(3) {
  animation: blink ease infinite 5s;
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
