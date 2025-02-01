<template>
  <div class="img-wrapper" ref="imgWrapper">
    <img :src="getImagePath(image)" alt="" />
  </div>
</template>

<script>
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { gsap } from "gsap";

gsap.registerPlugin(ScrollTrigger);
export default {
  mounted() {
    this.initAnimation();
  },
  props: {
    image: String,
  },
  methods: {
    getImagePath(img) {
      // Gunakan require untuk memuat gambar dinamis
      return require(`@/assets/images/${img}`);
    },
    initAnimation() {
      gsap.from(this.$refs.imgWrapper, {
        duration: 1,
        y: 50,
        opacity: 0,
        scrollTrigger: {
          trigger: this.$refs.imgWrapper, // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 20%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.img-wrapper {
  width: 50%;
  img {
    max-width: 100%;
  }

  @media (min-width: 479px) {
    width: 100%;
  }

  @media (min-width: 600px) {
    img {
      width: 140px;
    }
  }
}
</style>
