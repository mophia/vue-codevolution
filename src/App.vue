<script>
export default {
  name: 'App',
  data() {
    return {
      headingId: 'heading',
      isDisabled: true,
      status: 'danger',
      isPromoted: false,
      isSoldout: false,
    };
  },
};
</script>

<template>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
  <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Sold out movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">
    Array conditional movie
  </h2>
  <h2
    v-bind:="{ promoted: isPromoted, new: !isSoldout, 'sold-out': isSoldout }"
  >
    Object conditional movie
  </h2>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.sold-out {
  color: red;
}

.sold-out {
  color: red;
}

.new {
  color: green;
}
</style>
