<template>
  <section>
    <div class="container">
      <div class="wrapper">
        <div class="contact">
          <h1>Contact us</h1>
          <p>Kyiv, Ukraine</p>
          <p class="email">mail@isa.co.ua</p>
          <SocialIcon />
        </div>
        <img
          src="@/assets/images/62647f9fbe07235ba9b28d67_star-white-with-animals.svg"
          alt=""
          class="img"
        />
      </div>
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import SocialIcon from "./ui/SocialIcon.vue";

gsap.registerPlugin(ScrollTrigger);
export default {
  mounted() {
    this.initAnimation();
  },
  components: {
    SocialIcon,
  },
  methods: {
    initAnimation() {
      gsap.from(".img", {
        duration: 1,
        y: 100,
        opacity: 0,
        scrollTrigger: {
          trigger: ".img", // Element yang memicu animasi
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
section {
  background-color: var(--green);

  .wrapper {
    display: grid;
    grid-template-columns: 1fr;

    .contact {
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 10px;
    }

    h1 {
      font-size: 8vw;
    }

    p {
      font-size: 3.72vw;
    }

    .email {
      cursor: pointer;
      transition: transform 0.3s ease;
      &:hover {
        transform: scale(0.8);
      }
    }
    @media (min-width: 768px) {
      width: 50%;

      h1 {
        font-size: 4vw;
      }

      p {
        font-size: 2.5vw;
      }
    }

    @media (min-width: 1024px) {
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      width: 100%;
    }
  }
}
</style>
