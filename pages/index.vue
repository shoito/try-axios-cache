<template>
  <div class="container">
    <div>
      <h1>
        try-axios-cache
      </h1>
      <div>
        <button @click="callApi">Click!</button><button @click="callApi({cache: false})">Click! - cache:false</button>
        <p><img :src="dog" /></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dog: null
    }
  },
  methods: {
    callApi(params) {
      this.$axios.get('https://dog.ceo/api/breeds/image/random', params)
                  .then(res => this.dog = res.data.message);
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
