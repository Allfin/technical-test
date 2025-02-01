<template>
  <div class="container">
    <h1>Our partners</h1>
    <p>are take care of our fund and help us with many questions</p>
    <div class="partners-wrapper">
      <div v-for="image in images" :key="image.id">
        <CardPartners :image="image" />
      </div>
    </div>
  </div>
</template>

<script>
import CardPartners from "./ui/CardPartners.vue";
export default {
  data() {
    return {
      images: [
        "62aa3401042d425391235aaa_Logo-adviRES.jpg",
        "62aa33e1380de680b7110ebf_ovid-wind-logo.png",
        "6265d803f32677c8352bc485_tbs_logo1-02.png",
        "6265d7edf0c46ce38f559328_download.png",
        "6265d7d930a5c2377aedf9d4_logo_laudis_accountancy.png",
        "6265d7c51ad96b1cbf31b0c0_photo_2022-04-21 20.43.09.jpeg",
      ],
    };
  },
  components: {
    CardPartners,
  },
};
</script>

<style lang="scss" scoped>
.partners-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  align-items: center;
  grid-column-gap: 2em;
  grid-row-gap: 3em;

  @media (min-width: 600px) {
    grid-template-columns: repeat(3, 1fr);
  }

  /* Laptop: 3 kolom */
  @media (min-width: 1024px) {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
