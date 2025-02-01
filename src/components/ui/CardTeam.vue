<script>
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { gsap } from "gsap";

gsap.registerPlugin(ScrollTrigger);
export default {
  mounted() {
    this.initAnimation();
  },
  props: {
    user: Object,
  },
  methods: {
    getImagePath(img) {
      // Gunakan require untuk memuat gambar dinamis
      return require(`@/assets/images/${img}`);
    },
    initAnimation() {
      gsap.from(this.$refs.cardRefWrapper, {
        duration: 1,
        y: 50,
        opacity: 0,
        scrollTrigger: {
          trigger: this.$refs.cardRefWrapper, // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 20%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });
    },
    handleMouseEnter() {
      gsap.to(this.$refs.cardRef, {
        scale: 0.9, // Perbesar 1.5x dari ukuran asli
        duration: 0.2, // Durasi animasi 1 detik
        ease: "power2.out", // Efek easing
      });
    },
    handleMouseLeave() {
      gsap.to(this.$refs.cardRef, {
        scale: 1, // Perbesar 1.5x dari ukuran asli
        duration: 0.2, // Durasi animasi 1 detik
        ease: "power2.out", // Efek easing
      });
    },
  },
};
</script>
<style lang="scss">
.card-wrapper {
  background-color: var(--yellow);
  height: 100%;
  .card {
    border: 0.25em solid var(--black);
    height: 100%;
    padding: 1em;
    text-align: center;
    display: flex;
    flex-direction: column;
    gap: 14px;
    align-items: center;

    img {
      max-width: 100%;
    }

    span {
      display: inline-block;
    }

    @media (min-width: 479px) {
      padding: 2em;
    }

    @media (min-width: 600px) {
      img {
        width: 140px;
      }
    }
  }
}
</style>

<template>
  <div
    ref="cardRefWrapper"
    class="card-wrapper"
    @mouseenter="handleMouseEnter"
    @mouseleave="handleMouseLeave"
  >
    <div class="card" ref="cardRef">
      <img :src="getImagePath(user.img)" alt="" />
      <span>{{ user.name }}</span>
      <span>{{ user.position }}</span>
    </div>
  </div>
</template>
