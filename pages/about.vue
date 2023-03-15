<template>
    <div>this is about page</div>
    <h2> All User Name</h2>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.name }}
      </li>
    </ul>

    <ul>
      <li v-for="user in users2" :key="user.id">
        {{ user.name }}
      </li>
    </ul>

    <ul>
      <li v-for="user in users3" :key="user.id">
        {{ user.name }}
      </li>
    </ul>

    <div>
      {{ user.name }} <br>
      {{ user.email }} <br>
    {{ user.id }}
    </div>

    <div>
      <h2>Weather</h2>
      <div>Description: {{ weather.weather[0].description }}</div>
      <div>Temperature: {{ weather.main.temp }} C</div>
    </div>

</template>

<script setup>
definePageMeta({
  layout: "custom",
});

const users = ref([])

onMounted(() => {
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())

    .then(data =>users.value = data)
})

const { data: users2 } = await useAsyncData('users2', () => $fetch('https://jsonplaceholder.typicode.com/users')) 

const {data: users3 } = await useFetch('https://jsonplaceholder.typicode.com/users')

const {data: user } = await useFetch('https://jsonplaceholder.typicode.com/users/1', {pick: ['id', 'name', 'email']})

const {data: weather } = await useFetch('/api/weather')


</script>