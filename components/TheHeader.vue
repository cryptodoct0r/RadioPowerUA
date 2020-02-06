<template>
  <div id="theHeader">
    <header class="main-header container">
      <nav class="navbar-top navbar px-0">
        <div class="col-sm-6 text-center text-sm-left p-0">
          <nuxt-link
            to=""
            class="logo py-1"
          >
            <img
              src="~/assets/img/logo.svg"
              alt="Project Target"
            >
          </nuxt-link>
        </div>

        <div class="col-sm-6 text-center text-sm-right p-0">
          <audio
            controls
            autoplay
            class="m-auto py-1"
            style="color: red;"
          >
            <source src="https://node-25.zeno.fm/2nbarxy58gruv?rj-ttl=5&rj-token=AAABbaz-hYmOGrId5LpDft3ShkPFG2ZoMeFGDoQpcTKrHQs2CDcwyQ&rj-tok=AAABcBowxjEAD9-yb1pypjSejA">
          </audio>
        </div>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  components: {},

  data () {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.main-header {
  width: 100%;
  height: auto;
  position: relative;
  top: 0;
  left: 0;
}

.navbar-top {
  height: 100px;
  display: flex;
  align-items: center;
}

.navbar-top .logo {
  display: block;
  width: auto;
  left: 0;
}
.logo img {
  width: 200px;
}

.navbar-social-links {
  position: absolute;
  right: 0;
}

.navbar-social-links li {
  display: inline-block;
  margin-left: 20px;
  position: relative;
}

.navbar-social-links li a {
  font-size: 20px;
}
</style>
