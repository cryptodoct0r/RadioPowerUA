<template lang="html">
  <!--Please view in debug or full page view -->

  <div class="hero">
    <div class="hero-cont-block ">
      <div class="social-icons">
        <ul>
          <li>
            <a href="#">
              <i class="fab fa-facebook-f" />
            </a>
          </li>
          <li>
            <a href="#">
              <i class="fab fa-instagram" />
            </a>
          </li>
          <li>
            <a href="#">
              <i class="fab fa-codepen" />
            </a>
          </li>
        </ul>
      </div>

      <div class="scroll-down">
        <svg
          fill="#F95F51"
          preserveAspectRatio="xMidYMid meet"
          height="1em"
          width="1em"
          viewBox="0 0 40 40"
          style="vertical-align: middle;"
        ><g><path d="m27.5 12.5l-7.5 7.5-7.5-7.5-5 5 12.5 12.5 12.5-12.5-5-5z" /></g></svg>
      </div>
    </div>
    <div class="text-block">
      <h1>
        we design <br>
        beautiful things<span class="red">.</span>
        <h1 />
      </h1></h1>
    </div>

    <div id="hero-block">
      <div id="hero-image">
        <img src="https://images.unsplash.com/photo-1573296667722-87d18c8d0c00?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60" alt="...">
      </div>
    </div>
  </div>
</template>

<script>
if (process.client) {
  document.addEventListener(
    'DOMContentLoaded',
    function () {
      setTimeout(function () {
        document.getElementById('hero-image').className = 'shrink'
      }, 100)
    },
    false
  )
}
export default {

}
</script>

<style lang="scss" scoped>
* {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

html,
body {
  top: 0px;
  left: 0px;
  margin: 0 auto;
}
@media (max-width: 1024px) {
  .hide {
    display: none !important;
  }
}
/*................*/
section {
  display: block;
}

.hero {
  height: 100%;
  overflow-x: hidden;
  overflow-y: hidden;
  margin: 0;
}

/*.......Left-Image.......*/

.hero-cont-block {
  display: -ms-flexbox;
  display: flex;
  -ms-flex-direction: column;
  flex-direction: column;
  min-height: 30vw;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding: calc(100vw / 24 * 3);
  position: absolute;
  width: 50vw;
  z-index: 2;
  bottom: 0;
}

.hero-cont-block::after {
  background-image: url(https://reech.ca/wp-content/uploads/2019/03/contour.svg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  object-fit: cover;
  background-blend-mode: overlay;
}
.hero-cont-block::after {
  opacity: 1;
  background-color: #efefef;
  content: "";
  display: block;
  height: 80%;
  left: 0;
  position: absolute;
  bottom: 0;
  transform: scaleX(0);
  transform-origin: 0 0;
  transition: transform 1s cubic-bezier(0.82, 0.005, 0.29, 1) 1.1s;
  width: 100%;
  animation-name: slideInLeft;
  animation-fill-mode: both;
  animation-duration: 1.5s;
  animation-delay: 0.8s;
}
.hero-cont-block::after {
  transform: scaleX(1);
}

@media (max-width: 1024px) {
  .hero-cont-block {
    height: 100vh;
    position: relative;
    top: 0;
    width: 100%;
  }
}
@media (max-width: 1024px) {
  .hero-cont-block::after {
    height: 100vh;
  }
}

/*.........Text-block...........*/
.text-block {
  position: absolute;
  display: block;
  height: 60vh;
  left: 15.5%;
  top: 24%;
  z-index: 3;
  overflow: hidden;
}
@media (max-width: 1024px) {
  .text-block {
    top: 16vh;
    height: auto;
    left: 20vw;
  }
}
.text-block h1 {
  top: 30vh;
  color: #131530;
  font-family: "Poppins", serif;
  font-size: 90px;
  font-weight: 700;
  letter-spacing: -1.25px;
  width: 80%;
  text-transform: uppercase;
  line-height: 1em;
  text-align: left;
  animation-name: fadeInUp;
  animation-fill-mode: both;
  animation-duration: 1.5s;
  animation-delay: 1.5s;
  height: 100%;
  opacity: 1;
}
@media (max-width: 1024px) {
  .text-block h1 {
    font-size: 50px;
  }
}
.red {
  color: #f95f51;
}

@media (max-width: 1024px) {
  .hero-title {
    padding: 30px 0 20px;
    font-size: 1.4375rem !important;
    line-height: 1.5rem !important;
  }
}

/*.......Right-Image.......*/

#hero-block {
  transform: translateX(67%);
  width: 60%;
}

#hero-block {
  height: 100vh;
  overflow: hidden;
  position: relative;
  transition: all 1.35s cubic-bezier(0.82, 0.005, 0.29, 1) 0.75s;
  z-index: 1;
}
#hero-image {
  height: 100%;
  position: absolute;
  transform: scale(1.1);
  transition: transform 2.5s cubic-bezier(0.21, 0, 0.18, 1);
  width: 100%;
  margin: 0;
}
#hero-image {
  transform: scale(1);
}
#hero-image img {
  left: 50%;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  height: 100%;
  object-fit: cover;
  width: 100%;
}

@media (max-width: 1024px) {
  #hero-block {
    transform: translateX(0);
    width: 80% !important;
    height: 60vw;
    margin: 0 auto;
    margin-top: -10vh;
    z-index: 3;
  }
}
@media (max-width: 1024px) {
  #hero-block {
    transition: transform 1s cubic-bezier(0.82, 0.005, 0.29, 1) 1.1s;
    width: 100%;
    animation-name: slideInUp;
    animation-fill-mode: both;
    animation-duration: 1.5s;
    animation-delay: 1s;
  }
}
/*........Scroll Down............*/

.scroll-down {
  bottom: 4vh;
  position: absolute;
  left: 3vw;
  border-radius: 36px;
  border: 2px solid lightgrey;
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -webkit-justify-content: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -webkit-align-items: center;
  -ms-flex-align: center;
  align-items: center;
  width: 46px;
  height: 46px;
  z-index: 1;
  cursor: pointer;
  -webkit-transition: all 0.5s ease-in-out 0s;
  -moz-transition: all 0.5s ease-in-out 0s;
  transition: all 0.5s ease-in-out 0s;
}
@media (max-width: 1024px) {
  .scroll-down {
    margin-bottom: 12vh;
    margin-left: 2vw;
  }
}
.scroll-down:hover {
  border-top-color: #131530;
  border-right-color: #131530;
  border-bottom-color: #131530;
  border-left-color: #131530;
  -webkit-transition: border-top-color linear 0.15s,
    border-right-color 0.15s linear 0.1s, border-bottom-color 0.15s linear 0.2s,
    border-left-color 0.15s linear 0.3s;
  transition: border-top-color linear 0.15s,
    border-right-color 0.15s linear 0.1s, border-bottom-color 0.15s linear 0.2s,
    border-left-color 0.15s linear 0.3s;
}

scroll-down a {
  transform: translateY(-100%);
  transition: transform 0.3s cubic-bezier(0.77, 0, 0.175, 1) 0.3s;
}

/*...................*/

.shrink {
  animation-name: shrink;
  -webkit-animation-name: shrink;
  animation-duration: 1s;
  -webkit-animation-duration: 1s;
  animation-iteration-count: 1;
  animation-timing-function: ease-in;
  -webkit-animation-timing-function: ease-in;
  visibility: visible !important;
  // -webkit-animation-fill-mode: forwards;
}
@keyframes shrink {
  from {
    transform: scale(2);
  }
  to {
    transform: scale(1);
  }
}
@-webkit-keyframes shrink {
  from {
    transform: scale(2);
  }
  to {
    transform: scale(1);
  }
}

/*............Social..........*/

.social-icons {
  position: absolute;
  bottom: 6rem;
  left: 3.5rem;
  z-index: 999;
  overflow: hidden;
}
@media (max-width: 1024px) {
  .social-icons {
    left: 2.5rem;
    bottom: 10rem;
  }
}
.social-icons ul {
  position: relative;
  margin: 0;
  padding: 0;
  list-style: none;
}
.social-icons ul li {
  position: relative;
  display: block;
  padding: 0.8rem 0;
  animation-name: fadeInUp;
  animation-fill-mode: both;
  animation-duration: 1.5s;
  animation-delay: 1.5s;
  height: 100%;
  opacity: 1;
}
.social-icons ul a {
  display: block;
  width: 2rem;
  height: 2rem;
}
.social-icons ul a {
  color: #f95f51;
  display: block;
  width: 100%;
  height: 100%;
}

/*.......btn..........*/
.btn {
  position: relative;
}
.button-block {
  position: relative;
  left: 0;
  z-index: 7;
  transition: all 0.25s ease-out;
}
.button-block {
  display: inline-block;
  padding: 1em 1.3em 1em;
  text-transform: uppercase;
  font-family: "Poppins", sans-serif;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 0.1em;
  transition: cubic-bezier(0.22, 0.61, 0.36, 1);
  text-decoration: none;
}
.button-block--brand {
  border: 2px solid #131530;
  color: #131530;
  box-shadow: 2px 2px 0;
}
.button-block--brand:hover {
  border: 2px solid #131530;
  color: #131530;
  box-shadow: -2px -2px 0;
  -webkit-transition: color 0.15s ease-out;
  -moz-transition: color 0.15s ease-out;
  transition: color 0.15s ease-out;
  transition: all 0.4s;
  text-decoration: none !important;
}
.button-block--brand:hover:after {
  content: "";
  position: absolute;
  left: 14%;
  bottom: 13px;
  width: 80%;
  background: url(https://reech.ca/wp-content/uploads/2019/03/horz.png) 50%
    repeat;
  background-size: 12px auto;
  height: 12px;
  -webkit-transition: all 0.5s ease;
  -moz-transition: all 0.5s ease;
  -o-transition: all 0.5s ease;
  -ms-transition: all 0.5s ease;
  transition: all 0.5s ease;
  z-index: -1;
}
</style>
