<template>
  <div id="counter">
    <p>{{ count }}</p>
    <button @click="add">plus</button>
    <button @click="down">down</button>
    <p v-if="count === 0">plus もしくは down ボタンを押してください。</p>
  </div>
</template>

<script>
export default {
  name: "CounterComponent",
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    add: function () {
      this.count = this.count + 1;
    },
    down: function () {
      this.count = this.count - 1;
    },
  },
};
</script>