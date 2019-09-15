<template lang="html">
  <div v-if="film" id="filmDetail">
    <div id="detailWrapper">
    <h2>{{ film.title }}</h2>
    <div id="flexWrapper">
    </div>
      <div id="left">
        <p><span>Film Description</span>: {{ film.description }} </p>

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

#filmDetail {
  box-sizing: border-box;
  height: 550px;
  width: 60%;
  background: #eee;
  color: #222;
  padding: 10px;
  border: 1px solid #ccc;
  margin: 0 auto;
}

#detailWrapper {
  box-sizing: border-box;
  background: #fff;
  padding: 10px;
  height: 100%;
  border-radius: 3px;
}

#flexWrapper {
  display: flex;
  justify-content: space-between;
}

#left, #right {
  width: 80%;
}

#left p:first-child {
  margin-top: 0;
}

h2 {
  margin: 10px 0 20px;
  padding: 0;
}

p span {
  font-weight: bold;
}




</style>
