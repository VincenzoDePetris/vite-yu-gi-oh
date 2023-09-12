<script>
import cardContainer from "./components/cardContainer.vue";

export default {
  data() {
    return {
      title: "Yu-Gi-Oh Api",
    };
  },
  components: { cardContainer },
};
</script>

<template>
  <div>
    <div class="dad">
      <div class="title">
        <h1>{{ title }}</h1>
      </div>
    </div>
    <cardContainer />
  </div>
</template>

<style lang="scss">
@use "./components/general.scss" as *;
.dad {
  background-color: white;
  height: 50px;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  padding: 10px;
}
</style>
