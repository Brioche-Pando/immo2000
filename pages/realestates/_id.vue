<template>
  <div>
    <p>title: {{ title }}</p>
    <p>description: {{ description }}</p>
    <p>area: {{ area }}</p>
    <p>number_of_rooms: {{ number_of_rooms }}</p>
    <p>energy_class: {{ energy_class }}</p>
    <p>ges: {{ ges }}</p>
    <p>furnished: {{ furnished }}</p>
    <p>price: {{ price }}</p>
  </div>
</template>
<script>
export default {
  async asyncData({ params }) {
    const estate = await fetch("http://localhost:1337/api/real-estates/" + params.id).then((res) =>
      res.json()
    );
    return {
      title: estate.data.attributes.Title,
      description: estate.data.attributes.Description,
      area: estate.data.attributes.Area,
      number_of_rooms: estate.data.attributes.Number_of_rooms,
      energy_class: estate.data.attributes.Energy_class,
      ges: estate.data.attributes.GES,
      furnished: estate.data.attributes.Furnished,
      price: estate.data.attributes.Price + '€',
    }
  },
};
</script>