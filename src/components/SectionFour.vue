<script>
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { gsap } from "gsap";

gsap.registerPlugin(ScrollTrigger);
import WardsBox from "./ui/WardsBox.vue";

export default {
  data() {
    return {
      wardsName: [
        "Shelter of Victoria Bulbyna",
        "City of faithful hearts",
        "Shelter of Natalia Tymoshenko",
        "Shelter of Jeanne Sass",
        "Shelter of Victoria Bondarenko",
        "Sterilization center",
        "Zoo chance",
        "Save lives",
        "City Center for the Treatment of Animals",
        "Society for the Protection of Animals in Sumy",
        "The right to life",
        "4 paws",
        "The kingdom of cats",
        "Zvir",
        "Mercy",
        "Happy dog",
        "Give me a paw, friend",
        "Friend",
        "Hope",
        "We are for the right to life",
        "Planeta",
        "Second Life",
        "Happy shore",
        "Retrieverteam",
        "Shelter of Irina Dobrolyubova",
        "Matilda",
        "Life",
        "Second chance",
        "SOS",
        "Best friends",
      ],
    };
  },
  components: {
    WardsBox,
  },
  mounted() {
    this.initAnimation();
  },
  methods: {
    initAnimation() {
      gsap.from(".button", {
        duration: 1,
        x: -30,
        opacity: 0,
        scrollTrigger: {
          trigger: ".button", // Element yang memicu animasi
          start: "top 100%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 5%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });
    },
    handleMouseEnter() {
      gsap.to(".arrow", {
        x: 15,
        duration: 0.2,
        ease: "power2.out",
      });
    },
    handleMouseLeave() {
      gsap.to(".arrow", {
        x: 0,
        y: 0,
        duration: 0.5,
        ease: "power2.out",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
section {
  background-color: var(--yellow);

  .wards-list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;

    @media (min-width: 600px) {
      grid-template-columns: repeat(2, 1fr);
    }

    /* Laptop: 3 kolom */
    @media (min-width: 1024px) {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  .button {
    background-color: var(--plum);
    border: 0.25em solid var(--black);
    position: relative;
    width: fit-content;
    margin-top: 10%;

    :hover {
      cursor: pointer;
    }

    .button-wrapper {
      padding: 1rem 2rem;
      display: flex;
      align-items: center;
      gap: 10px;

      img {
        rotate: 180deg;
        width: auto;
        height: 2vw;

        :hover {
          outline: none;
        }
      }
    }
  }
}
</style>

<template>
  <section>
    <div class="container">
      <h1>We want to help</h1>
      <p>
        homeless packs, volunteers, guardians, overstayers, shelters and other
        organisations
      </p>
      <div class="wards-list">
        <div v-for="ward in wardsName" :key="ward.id" class="wards-wrapper">
          <WardsBox :wards-name="ward" />
        </div>
      </div>
      <div
        class="button"
        @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave"
      >
        <div class="button-wrapper">
          <span>apply for help</span>
          <img src="../assets/images/arrow.png" alt="arrow" class="arrow" />
        </div>
      </div>
    </div>
  </section>
</template>
