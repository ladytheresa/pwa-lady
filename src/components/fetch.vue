FETCH EXAMPLE

<template>
    <div>
      <h1>{{ title }}</h1>
      <ul>
        <li v-for="item in items" :key="item">{{ item.name }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  // Define reactive variables
  const title = ref('Fetching Data Example');
  const items = ref([]);
  
  // Define a function to fetch data
  const fetchData = async () => {
    try {
      const response = await fetch('https://pokeapi.co/api/v2/pokemon');
      if (response.ok) {
        const data = await response.json();
        items.value = data['results'];
        console.log(data);
      } else {
        console.error('Failed to fetch data');
      }
    } catch (error) {
      console.error('An error occurred:', error);
    }
  };
  
  // Call fetchData when the component is mounted
  onMounted(fetchData);
  </script>


  <!-- POST EXAMPLE -->
  <!-- <template>
    <div>
      <h1>{{ title }}</h1>
      <ul>
        <li v-for="item in items" :key="item.id">{{ item.username }}</li>
      </ul>
      <button @click="sendData">Send Data</button>
    </div>
  </template> -->
  
  <!-- <script setup>
  import { ref, onMounted } from 'vue';
  
  // Define reactive variables
  const title = ref('Fetching Data Example');
  const items = ref([]);
  
  // Define a function to send a POST request with application/x-www-form-urlencoded content type
  const sendData = async () => {
    try {
    //   const postData = new URLSearchParams();
      const postData = JSON.stringify({
        title:'foo',
        body:'bar',
        userId:'1'
      })
    //   postData.append('name', 'Letstrysomethingnew');
    //   postData.append('avatar', 'https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/301.jpg');
  
      const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
        method: 'POST',
        headers: {
            'Content-type': 'application/json; charset=UTF-8',
        },
        body: postData,
      });
  
      if (response.ok) {
        console.log('Data sent successfully');
      } else {
        console.error('Failed to send data');
      }
    } catch (error) {
      console.error('An error occurred:', error);
    }
  };
  
  // Call fetchData when the component is mounted
//   onMounted(sendData);
  </script> -->