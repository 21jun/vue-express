<template>
  <div>
    <h1>상세 내용</h1>
    <h2>{{movie[0].name}}</h2>
    <img v-bind:src="movie[0].poster" class="poster">


  </div>
</template>

<script>
  export default {
    created: function () {
      var id = this.$route.params.id
      console.log(id);
      this.$http.get(`/api/movies/${id}`)
        .then((response) => {
          this.movie = response.data
        })
    },
    data: function () {
      return {
        movie: {}
      }
    }
  }
</script>

<style scoped>

</style>
