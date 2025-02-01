<script>
import CardTeam from "./ui/CardTeam.vue";
export default {
  data() {
    return {
      usersData: [
        {
          img: "62744ee9fce7fbaf400c22f8_2.jpg",
          name: "Daryna Deriy",
          position: "Chairman of the Board",
        },
        {
          img: "62744edaac91b4183ac27e10_5.jpg",
          name: "Polina Snisarenko-Kulchytska",
          position: "Curator of the Foundation",
        },
        {
          img: "62744ec97586a996f48f7a85_1.jpg",
          name: "Bohdan Kulchytsky",
          position: "Executive Manager",
        },
        {
          img: "62744eae22e10d8a15f909ef_9.jpg",
          name: "Mykhaylo Deriy",
          position: "Operation Manager",
        },
        {
          img: "62744e8e05f6c22bac85252a_7.jpg",
          name: "Ksenia Nikishina",
          position: "Office manager",
        },
        {
          img: "62744f0eb7cd3462ef475ebf_6.jpg",
          name: "Anna Andriychuk",
          position: "SMM-manager",
        },
        {
          img: "62744e6761e425c6956af3a5_3.jpg",
          name: "Anastasia Kovalchuk",
          position: "Director",
        },
        {
          img: "626ae0bcd92bf48017c14083_basil-square.png",
          name: "Basil Gloo",
          position: "Web Developer",
        },
        {
          img: "626ae01da2a805d176b1606b_Якобчук.jpg",
          name: "Lina Yakobchuk",
          position: "Designer",
        },
        {
          img: "627fc796cf3602b53a7512cf_4.jpg",
          name: "Anastasia Kovalchuk",
          position: "Translator",
        },
        {
          img: "isa-logo-dog-clean.svg",
          name: "Office Manager",
          position: "open vacancy",
        },
        {
          img: "isa-logo-cat-clean.svg",
          name: "SEO specialist",
          position: "open vacancy",
        },
      ],
    };
  },
  components: {
    CardTeam,
  },
  methods: {},
};
</script>

<style lang="scss">
.team-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;

  .team {
    :hover {
      cursor: pointer;
    }
  }

  @media (min-width: 600px) {
    grid-template-columns: repeat(3, 1fr);
  }

  /* Laptop: 3 kolom */
  @media (min-width: 1024px) {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>

<template>
  <div class="container">
    <h1>Our team</h1>
    <p>
      consists of completely different people who are united by a common desire
      - to help
    </p>
    <div class="team-wrapper">
      <div v-for="user in usersData" :key="user.id" class="team">
        <CardTeam :user="user" />
      </div>
    </div>
  </div>
</template>
