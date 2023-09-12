<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "Yu-Gi-Oh Api",
      cards: [],
    };
  },
  methods: {
    fetchCards() {
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php").then((res) => {
        console.log(res.data);
        this.cards = res.data;
      });
    },
  },
  created() {
    this.fetchCards();
  },
};
</script>

<template>
  <section class="container">
    <h1>{{ title }}</h1>

    <div class="row g-4">
      <div class="col" v-for="card in cards">
        {{ card.name }}
        {{ card.type }}
      </div>
    </div>
  </section>
</template>

<style scoped></style>
