<template>
  <div id="theHeader">
    <header id="header" class="header">
      <div class="row">
        <b-navbar-brand class=" theHeader-nav-brand mx-auto" to="/">
          <b-img class="" src="~/assets/img/logo.svg" alt="logo " />
        </b-navbar-brand>
      </div>
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
.header {
  box-shadow: none;
  top: 0;
  padding: 10px 0;
}

.theHeader-nav-brand img {
  left: 50%;
  position: absolute;

  transform: translateX(-50%);

  min-height: 60px;
  max-height: 60px;
  height: 100%;
}
</style>
