<template>
  <form>
    <input type="text" v-model="name" placeholder="add an item..." />
    <input type="text" v-model="price" placeholder="$" />
    <button @click="persist" type="submit">Save</button>

    <br />
    <br />

    <p>
      {{ name }}
    </p>

    <p>
      {{ price }}
    </p>
  </form>
</template>

<script>
  export default {
    name: 'add-item',
    data: function () {
      return {
        name: '',
        price: 0
      }
    },
    mounted() {
      if (localStorage.name) {
        this.name = localStorage.name;
      }
      if (localStorage.price) {
        this.price = localStorage.price;
      }
    },
    methods: {
      persist() {
        localStorage.name = this.name;
        localStorage.price = this.price;
      }
    }
  }
</script>
