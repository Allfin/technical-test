<script>
import SocialIcon from "./ui/SocialIcon.vue";

export default {
  components: {
    SocialIcon,
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
        <SocialIcon />
      </div>
    </div>
  </section>
</template>
