<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    this.initAnimation();
  },
  methods: {
    initAnimation() {
      gsap.from(".project-wrap", {
        duration: 1,
        x: -50,
        opacity: 0,
        scrollTrigger: {
          trigger: ".project-wrap", // Element yang memicu animasi
          start: "top 80%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 20%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play none play reverse",
        },
      });
    },
    handleMouseEnter(target) {
      gsap.to(target, {
        x: 15,
        y: -15,
        duration: 0.2,
        ease: "power2.out",
      });
    },
    handleMouseLeave(target) {
      gsap.to(target, {
        x: 0,
        y: 0,
        duration: 0.5,
        ease: "power2.out",
      });
    },
  },
  beforeMount() {
    ScrollTrigger.getAll().forEach((trigger) => trigger.kill());
  },
};
</script>

<style lang="scss" scoped>
section {
  background-color: var(--blue);
  color: var(--white);
  position: relative;

  .project-wrap {
    cursor: pointer;
    user-select: none;

    .project-detail {
      border: 3px solid var(--white);
      padding: 28px 42px;

      h2 {
        margin-bottom: 10px;
      }

      @media screen and (min-width: 767px) {
        padding: 56px;
      }
    }
  }
}
</style>

<template>
  <section>
    <div class="container">
      <h1>Our projects</h1>
      <p>
        are very different in terms of priority, scale and complexity of
        implementation
      </p>
      <div class="project-wrap background-black">
        <div
          class="project-detail black"
          @mouseenter="handleMouseEnter('.black')"
          @mouseleave="handleMouseLeave('.black')"
        >
          <h2>Emergency Aid. WAR 2022.</h2>
          <span>
            providing food and medicine to the shelters and animals which lost
            their homes and families due to the war
          </span>
        </div>
      </div>
      <div class="project-wrap background-green">
        <div
          class="project-detail green"
          @mouseenter="handleMouseEnter('.green')"
          @mouseleave="handleMouseLeave('.green')"
        >
          <h2>Non-commercial feed line</h2>
          <span>
            construction of industrial production base where food for shelters
            will be produced on a free basis
          </span>
        </div>
      </div>
      <div class="project-wrap background-plum">
        <div
          class="project-detail plum"
          @mouseenter="handleMouseEnter('.plum')"
          @mouseleave="handleMouseLeave('.plum')"
        >
          <h2>Education and Control</h2>
          <span>
            lectures on communication, organisation and coordination of
            processes, control over the use of aid
          </span>
        </div>
      </div>
    </div>
  </section>
</template>
