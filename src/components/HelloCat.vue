<template>
    <div id="container">
        <h1>Hello Cat!</h1>
        <img :src="image.url" alt="cat">
        <button @click="loadNextImage">I want to see another cat!</button>
    </div>
</template>

<script>
const axios = require('axios');

export default {
    data () {
    return {
      image: { url: ""},
      image_type: "gif"
    }
  },
  created() {
      this.loadNextImage();
  },
   methods:{ loadNextImage() {
    axios.defaults.headers.common['x-api-key'] = "37d8b981-3bd6-49a4-9058-d2d763af859c";
    axios
      .get('https://api.thecatapi.com/v1/images/search', { params: { limit:1, size:"full" , mime_types: this.image_type } })
      .then(response => (this.image = response.data[0]))
  }
}
}
</script>

<style scoped>
    #container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img {
        margin-bottom: 2rem;
        max-width: 600px;
    }
    button {
        padding: 2rem;
        border: none;
        cursor: pointer;
        font-size: 1.3rem;
        font-weight: bold;
    }
    @media screen and (max-width: 425px) {
        img {
            max-width: 300px;
        }
    }
</style>