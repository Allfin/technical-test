<template>
  <div
    class="btn-wrapper"
    @mouseenter="handleMouseEnter"
    @mouseleave="handleMouseLeave"
  >
    <div class="btn">donate</div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);
export default {
  methods: {
    handleMouseEnter() {
      gsap.to(".btn", {
        x: 8,
        y: -8,
        duration: 0.2,
        ease: "power2.out",
      });
    },
    handleMouseLeave() {
      gsap.to(".btn", {
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
.btn-wrapper {
  position: fixed;
  top: 5%;
  right: 5%;
  background-color: #fff;
  color: var(--black);
  z-index: 10;
  &:hover {
    cursor: pointer;
  }

  .btn {
    position: relative;
    border: 3px solid #000;
    padding: 5px;
  }
}
</style>
