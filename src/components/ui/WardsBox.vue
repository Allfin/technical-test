<script>
import { gsap } from "gsap";
export default {
  mounted() {
    this.initAnimation();
  },
  props: {
    wardsName: String,
  },
  methods: {
    initAnimation() {
      gsap.from(this.$refs.wardWrapper, {
        duration: 1,
        y: 30,
        opacity: 0,
        scrollTrigger: {
          trigger: this.$refs.wardWrapper, // Element yang memicu animasi
          start: "top 100%", // Mulai animasi saat 80% dari elemen masuk ke viewport
          end: "bottom 5%", // Akhiri animasi saat 20% dari elemen keluar dari viewport
          toggleActions: "play reverse play reverse",
        },
      });
    },
    handleMouseEnter() {
      gsap.to(this.$refs.boxRef, {
        x: 15,
        y: -15,
        duration: 1,
        ease: "power2.out",
      });
    },
    handleMouseLeave() {
      gsap.to(this.$refs.boxRef, {
        x: 0,
        y: 0,
        duration: 1,
        ease: "power2.out",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.box-wrapper {
  background-color: var(--white);
  height: 100%;

  :hover {
    cursor: pointer;
  }

  @media (max-width: 425px) {
    width: 50%;
  }

  .box {
    padding: 28px;
    display: flex;
    justify-content: center;
    text-align: center;
    flex-direction: column;
    border: 3px solid black;
    height: 100%;
  }
}
</style>

<template>
  <div class="box-wrapper" ref="wardWrapper">
    <div
      ref="boxRef"
      @mouseenter="handleMouseEnter()"
      @mouseleave="handleMouseLeave()"
      class="box"
    >
      <span class="wards-name">{{ wardsName }}</span>
    </div>
  </div>
</template>
