<template>
  <div>
    <section>
      <ul v-for="(data, id) in results" :key="id">
        <li class="title">{{ data.title }}</li>
        <li class="description">{{ data.description }}</li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
    name: 'SearchResults',
    props: {
      results: {
        type: Array
      }
    }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  text-align: left;
}
/* .title, .description {
    /* text-align: left; */
    /* padding-left: 100px; */
 /* }*/
.title {
    font-weight: bold;
}
div {
  padding-top: 10px;
  margin-top: 20px  ;
}
</style>