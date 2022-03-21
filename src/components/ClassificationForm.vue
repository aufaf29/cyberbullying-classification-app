<template>
  <div>
    <b-form-textarea
      id="textarea"
      v-model="text"
      placeholder="Enter something..."
      rows="3"
      max-rows="6"
    ></b-form-textarea>

    <pre class="mt-3 mb-0">{{ text }}</pre>
    Test
  </div>
</template>

<script>

const axios = require('axios');

export default {
    data() {
        return {
            text: ''
        }
    },
    mounted() {
        
        axios.create({
            baseURL: "http://localhost:5000",
        })
        .get("/")
        .then(res => {
            console.log(res)
        })
    }
}
</script>