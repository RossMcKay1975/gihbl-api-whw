<template lang="html">
  <div v-if="film" id="filmDetail">
    <div id="detailWrapper">
    <h2>{{ film.title }}</h2>
    <div id="flexWrapper">
    </div>
      <div id="left">
        <p><span>Film Description</span>: {{ film.description }} </p>
        <p><span>Must Watch</span>: </p>

      </div>
      <div id="right">
        <button type="button" v-on:click="makeFavourite">Make Favourite</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film'],
  methods: {
    makeFavourite: function(){
      this.film.favourite = true
    }
  }
}
</script>

<style lang="css" scoped>

  ul {
    list-style-type: none;
    }

  .button {
    background-color: #4CAF50;
  }



</style>
