<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    // Inisialisasi animasi saat komponen terpasang
    this.initAnimation();
  },
  methods: {
    initAnimation() {
      gsap.from(".video", {
        duration: 1,
        y: -50,
        opacity: 0,
        scrollTrigger: {
          trigger: ".video", // Element yang memicu animasi
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
.quote-container {
  margin-left: 4rem;
  padding: 20px;
  border-left: 2px solid var(--plum);
}

.quote-text {
  font-size: 1.5em;
  font-style: italic;
  margin-bottom: 20px;
}

.quote-author {
  font-size: 1.2em;
  font-weight: bold;
}

.video-container {
  position: relative;
  padding-bottom: 46%; /* 16:9 */
  padding-top: 25px;
  margin: 30px 0;
  height: 0;

  iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
</style>
<template>
  <section>
    <div class="container">
      <h1>We are</h1>
      <p>
        team of like-minded people, socially active companies, media
        personalities, volunteers who help low-income shelters and foster carers
        to support homeless animals.
      </p>
      <h1>Our primary goal</h1>
      <p>
        is to provide animals with the most necessary things - food, medicine,
        and urgent needs for the livelihood of shelters. We believe in our power
        and the power of conscious citizens who care about the environment and
        their health, who understand the importance of helping each other,
        especially our little friends. Growth begins with your care for your
        loved ones. Animals are one of the closest creatures to humans who
        remain with us throughout our lives. We all know the healing power of
        warmth, grace, and big loving eyes.
      </p>
      <div class="quote-container">
        <div class="quote-text">
          "Animals need to have friends. Just like humans."
        </div>
        <div class="quote-author">
          -James Herriot, <em>All Creatures Great and Small</em>
        </div>
      </div>

      <div class="video-container">
        <iframe
          class="video"
          height="465px"
          width="470px"
          src="https://www.youtube.com/embed/5Wk1rp99B7o?si=LIA_fDW4WL_ZxNBe"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </section>
</template>
