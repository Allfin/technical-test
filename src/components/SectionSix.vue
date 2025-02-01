<script>
import CardCitizens from "./ui/CardCitizens.vue";
export default {
  data() {
    return {
      citizens: [
        {
          img: "628398012a964488bb09078d_13.jpg",
          name: "Oleksiy Tritenko",
          position: "theater and film actor",
        },
        {
          img: "628397b3f06d2066cfe8e9a2_14.jpg",
          name: "Stanislav Boklan",
          position: "theater and film actor",
        },
        {
          img: "627fcdfcb2137dcf7db53e7f_12.jpg",
          name: "Alexander Rudinsky",
          position: "theater and film actor",
        },
        {
          img: "627fcdd72d729d8ecacf6de7_11.jpg",
          name: "Oksana Zhdanova",
          position: "theater and film actor",
        },
        {
          img: "627fcdaedc0f8eea17c92429_10.jpg",
          name: "Natalka Denisenko",
          position: "theater and film actor",
        },
        {
          img: "627fcd87d51b9051dfcbf349_09.jpg",
          name: "Maksym Samchyk",
          position: "theater and film actor",
        },
        {
          img: "627fcd5ca9508410b3a0d824_08.jpg",
          name: "Kateryna Vyshneva",
          position: "theater and film actor",
        },
        {
          img: "627fcd3288758547e6ee0e22_07.jpg",
          name: "Irma Vitovska",
          position: "theater and film actor",
        },
        {
          img: "627fcd1790c298c49bc7c436_06.jpg",
          name: "Igor Portyanko",
          position: "theater and film actor",
        },
        {
          img: "627fccf0fc672a5dcfa87ee9_05.jpg",
          name: "Dmytro Surzhikov",
          position: "theater and film actor",
        },
        {
          img: "627fccc57c3cb5177369015e_04.jpg",
          name: "Daria Barihashvili",
          position: "theater and film actor",
        },
        {
          img: "627fcc9bc50d7acc036982a9_03.jpg",
          name: "Vera Kobzar",
          position: "theater and film actor",
        },
        {
          img: "627fcc7339e6f5389ed03013_02.jpg",
          name: "Andriy Fedynchyk",
          position: "theater and film actor",
        },
        {
          img: "627fcc4b694dfd4d65a13230_01.jpg",
          name: "Anastasia Nesterenko",
          position: "theater and film actor",
        },
      ],
    };
  },
  components: {
    CardCitizens,
  },
};
</script>

<style lang="scss" scoped>
section {
  background-color: var(--plum);

  .citizen-wrapper {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;

    @media (min-width: 600px) {
      grid-template-columns: repeat(3, 1fr);
    }

    /* Laptop: 3 kolom */
    @media (min-width: 1024px) {
      grid-template-columns: repeat(4, 1fr);
    }
  }
}
</style>

<template>
  <section>
    <div class="container">
      <h1>Socially active citizens</h1>
      <p>support us</p>
      <div class="citizen-wrapper">
        <div v-for="citizen in citizens" :key="citizen.id">
          <CardCitizens :citizen="citizen" />
        </div>
      </div>
    </div>
  </section>
</template>
