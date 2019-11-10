<template lang="html">
  <div class="page-container">
    <div ref="example" v-fullpage="opts" class="fullpage-wp">
      <div class="page-1 page">
        <TheHero v-animate="{value: 'bounceInLeft'}" class="part-1" />
      </div>
      <div class="page-2 page">
        <TheHero v-animate="{value: 'bounceInRight'}" class="part-2" />
      </div>
      <div class="page-3 page">
        <p v-animate="{value: 'bounceInLeft', delay: 0}" class="part-3">
          fullpage-vue
        </p>
        <p v-animate="{value: 'bounceInRight', delay: 600}" class="part-3">
          fullpage-vue
        </p>
        <p v-animate="{value: 'zoomInDown', delay: 1200}" class="part-3">
          fullpage-vue
        </p>
      </div>
    </div>
    <button @click="moveNext">
      next
    </button>
  </div>
</template>

<script>
import TheHero from '~/components/TheHero2'
export default {
  components: {
    // TheHeader,
    TheHero
    // TheSchedule
  },
  data () {
    return {
      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange (currentSlideEl, currenIndex, nextIndex) {
        },
        afterChange (currentSlideEl, currenIndex) {
        }
      }
    }
  },
  method: {
    moveNext () {
      this.$refs.example.$fullpage.moveNext() // Move to the next page
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
