<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "Yu-Gi-Oh Api",
      cards: [],
      number: 20,
    };
  },
  methods: {
    fetchCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((res) => {
          console.log(res.data.data);
          this.cards = res.data.data;
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
    <div class="number-cards">
      <p>Found {{ number }} cards</p>
    </div>
    <div class="row">
      <div class="col" v-for="card in cards">
        <img :src="card.card_images[0].image_url" alt="" />
        <p class="name">
          {{ card.name }}
        </p>
        <p class="archetype">
          {{ card.archetype }}
        </p>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.container {
  width: 1400px;
  margin: auto;
  background-color: white;
  .number-cards {
    background-color: black;
    color: whitesmoke;
    height: 50px;
    display: flex;
    align-items: center;
    margin-bottom: 0;
  }
  .row {
    display: flex;
    flex-wrap: wrap;
    .col {
      background-color: rgb(212, 143, 56);
      margin: 10px;
      width: 250px;
      text-align: center;
      .name {
        color: whitesmoke;
        font-size: 1.3rem;
      }
      img {
        width: 250px;
        height: 350px;
      }
    }
  }
}
</style>
