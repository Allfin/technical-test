<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import SocialIcon from "./ui/SocialIcon.vue";

gsap.registerPlugin(ScrollTrigger);
export default {
  components: {
    SocialIcon,
  },
  mounted() {
    // Inisialisasi animasi saat komponen terpasang
    this.initAnimation();
  },

  methods: {
    initAnimation() {
      // Animasi menggunakan GSAP dan ScrollTrigger
      gsap.from(".text", {
        duration: 1,
        x: 50,
        opacity: 0,
        scrollTrigger: {
          trigger: ".text", // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 20%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });

      gsap.from(".logo", {
        duration: 1,
        y: -50,
        opacity: 0,
        scrollTrigger: {
          trigger: ".logo", // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 20%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });

      gsap.from(".social", {
        duration: 1,
        y: 50,
        opacity: 0,
        scrollTrigger: {
          trigger: ".social", // Element yang memicu animasi
          start: "top 100%",
          end: "bottom 10%",
          toggleActions: "play reverse play reverse",
        },
      });
    },
  },
};
</script>

<style lang="scss">
.hero {
  background: var(--yellow);
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;

  &-content {
    text-align: center;

    .hero-logo-wrapper {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;

      .text {
        text-align: left;
      }
    }

    .logo {
      max-width: 15%;
      height: auto;
      display: block;
    }
  }
}
</style>

<template>
  <section class="hero">
    <div class="hero-content">
      <div class="hero-logo-wrapper">
        <img
          v-if="showFirstImage"
          src="@/assets/images/isa-logo-cat-clean.svg"
          alt="Logo"
          class="logo"
        />
        <img
          v-else
          src="@/assets/images/isa-logo-dog-clean.svg"
          alt="Logo"
          class="logo"
        />
        <div class="text">
          <h1>
            Innovative <br />Solutions <br />for <br />
            Animals
          </h1>
        </div>
      </div>
      <div class="social">
        <p>charity organization</p>
        <SocialIcon />
      </div>
    </div>
  </section>
</template>
