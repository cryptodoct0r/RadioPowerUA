<template>
  <card class="mb-4">
    <!-- swiper -->
    <swiper :options="swiperOption">
      <swiper-slide>
        <img
          width="200"
          src="~/assets/img/joan.jpeg"
          alt=""
        >
      </swiper-slide>
      <swiper-slide>
        <img
          width="200"
          src="~/assets/img/joan.jpeg"
          alt=""
        >
      </swiper-slide>
      <swiper-slide>
        <img
          width="200"
          src="~/assets/img/joan.jpeg"
          alt=""
        >
      </swiper-slide>

      <div
        slot="pagination"
        class="swiper-pagination"
      />
    </swiper>
  </card>
</template>

<script>
export default {
  data () {
    return {
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 30,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      }
    }
  }
}
</script>
