<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  data() {
    return {
      icons: [
        { name: "youtube", src: require("@/assets/images/youtube_bxl.svg") },
        {
          name: "instagram",
          src: require("@/assets/images/instagram_bxl.svg"),
        },
        { name: "facebook", src: require("@/assets/images/facebook_bxl.svg") },
        { name: "patreon", src: require("@/assets/images/patreon_bxl.svg") },
        { name: "telegram", src: require("@/assets/images/telegram_bxl.svg") },
      ],
      showFirstImage: true,
    };
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
  beforeUnmount() {
    ScrollTrigger.getAll().forEach((trigger) => trigger.kill());
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

    .social {
      .social-icons {
        display: flex;
        gap: 10px;
        justify-content: center;

        .icon {
          min-width: 3%;
          min-height: 3%;
          cursor: pointer;
          transition: transform 0.3s ease;
          &:hover {
            transform: scale(0.8);
          }
        }
      }
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
        <div class="social-icons">
          <img
            v-for="icon in icons"
            :key="icon.name"
            :src="icon.src"
            :alt="icon.name"
            class="icon"
          />
        </div>
      </div>
    </div>
  </section>
</template>
