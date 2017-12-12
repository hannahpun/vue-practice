<template>
 <div>
    <h1>livedealer</h1>
    <flickity  class="flickity" ref="flickity" :options="flickityOptions">
        <div class="carousel-cell"><img src="~/assets/images/test1.jpg"></div>
        <div class="carousel-cell"><img src="~/assets/images/test2.jpg"></div>
        <div class="carousel-cell"><img src="~/assets/images/test3.jpg"></div>
    </flickity>
 </div>
</template>

<script>
import Flickity from 'vue-flickity'

export default {
  components: {
    Flickity
  },
  data () {
    return {
      flickityOptions: {
        initialIndex: 3,
        prevNextButtons: true,
        pageDots: true,
        wrapAround: true,
        freeScroll: true
        // any options from Flickity can be used
      }
    }
  }
}
</script>