<template>
  <div>
    <h1>Mi banco de prueba</h1>
    <h3>{{ subtitle }}</h3>
  </div>
</template>

<script>
export default {
  name: 'Titulo',
  props: {
    subtitle: String,
  },
};
</script>

<style scoped>
  h1 {
    color: blue;
  }
</style>