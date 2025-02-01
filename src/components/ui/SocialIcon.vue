<template>
  <div class="social-icons">
    <img
      v-for="icon in icons"
      :key="icon.name"
      :src="icon.src"
      :alt="icon.name"
      class="icon"
    />
  </div>
</template>

<script>
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
};
</script>

<style lang="scss" scoped>
.social-icons {
  .icon {
    min-width: 3%;
    min-height: 3%;
    cursor: pointer;
    transition: transform 0.3s ease;
    &:hover {
      transform: scale(0.8);
    }
  }

  img {
    width: 35px;
  }
}
</style>
