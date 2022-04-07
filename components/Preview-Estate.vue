<template>
  <div>
    <ul class="estates">
      <li v-for="estate in estates" :key="estate.id" class="estate">
        <NuxtLink :to="{ name: 'realestates-id', params: { id: estate.id } }">
          <header class="estate__header">
            <h2>{{ estate.attributes.Title }}</h2>
            <img src="" alt="" />
          </header>
          <div class="estate__content">
            <p class="estate__description">{{ estate.attributes.Description }}</p>
          </div>
          {{ estate.attributes.Area }}
          {{ estate.attributes.Price }}
          {{ estate.attributes.Number_of_rooms }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template> 

<script>
import axios from "axios";
export default {
  data() {
    return {
      estates: [],
    };
  },
  mounted() {
    axios({
      url: "http://localhost:1337/api/real-estates",
      method: "get",
    }).then((response) => {
      response.data.data.forEach((estate) => {
        this.estates.push(estate);
      });
    });
  },
};
</script>

<style scoped>
</style>