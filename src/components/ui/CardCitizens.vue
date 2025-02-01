<template>
  <div class="card-wrapper" ref="citizenCard">
    <div class="card">
      <img :src="getImagePath(citizen.img)" alt="" />
      <span>{{ citizen.name }}</span>
      <span>{{ citizen.position }}</span>
    </div>
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
    citizen: Object,
  },
  methods: {
    getImagePath(img) {
      return require(`@/assets/images/${img}`);
    },
    initAnimation() {
      gsap.from(this.$refs.citizenCard, {
        duration: 1,
        y: 50,
        opacity: 0,
        scrollTrigger: {
          trigger: this.$refs.citizenCard, // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 0%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.card-wrapper {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 50%;
  text-align: center;

  span {
    display: inline-block;

    &:nth-child(2) {
      font-weight: 300;
      font-size: large;
    }
  }

  img {
    max-width: 100%;
  }

  @media (min-width: 479px) {
    width: 100%;
  }

  @media (min-width: 600px) {
  }
}
</style>
