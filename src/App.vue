<script>
export default {
  name: 'App',
  data() {
    return {
      firstName: 'Sooia',
      lastName: 'Miffy',
      items: [
        {id:1, title: 'TV', price: 100},
        {id:2, title: 'Phone', price: 200},
        {id:3, title: 'Laptop', price: 300}
      ]
    };
  },
  methods: {
  },
  computed: {
    fullName(){
      return `${this.firstName} ${this.lastName}`
    }
  }
};
</script>

<template>
  <h2>Fullname - {{firstName}} {{lastName}}</h2>
  <h2>Fullname - {{fullName}}</h2>
  <h2>
    Total - {{items.reduce((total, curr) => (total = total + curr.price), 0)}}
  </h2>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>