<template>
  <div class="app">
    <ButtonDonate />
    <SectionOne />
    <SectionTwo />
    <SectionThree />
    <SectionFour />
    <SectionFive />
    <SectionSix />
    <SectionSeven />
    <AppFooter />
  </div>
</template>

<script>
import SectionOne from "@/components/SectionOne.vue";
import SectionTwo from "@/components/SectionTwo.vue";
import SectionThree from "@/components/SectionThree.vue";
import SectionFour from "@/components/SectionFour.vue";
import SectionFive from "@/components/SectionFive.vue";
import SectionSix from "@/components/SectionSix.vue";
import SectionSeven from "@/components/SectionSeven.vue";
import AppFooter from "@/components/AppFooter.vue";
import ButtonDonate from "@/components/ui/ButtonDonate.vue";

export default {
  components: {
    SectionOne,
    SectionTwo,
    SectionThree,
    SectionFour,
    SectionFive,
    SectionSix,
    SectionSeven,
    AppFooter,
    ButtonDonate,
  },
};
</script>

<style lang="scss" scoped>
.app {
}
</style>
