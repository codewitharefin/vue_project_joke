<script setup>
import { ref, reactive } from 'vue'

// You can show joke on button click in 2 ways here. Using variable or using object

const joke = reactive({
  content: 'Chuck Norris can do a wheelie on a unicycle.'
})

//const jokex = ref('Chuck Norris can do a wheelie on a unicycle.')

function getAJoke() {
    fetch('https://api.chucknorris.io/jokes/random')
        .then(response => response.json())
        .then(data => {
            joke.content = data.value
            // jokex.value = data.value
        })
    }
</script>

<template>
    <p>{{ joke.content }}</p>
    <button @click="getAJoke()">Get a new joke</button>
</template>

<style scoped>
    
</style>