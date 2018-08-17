<template>
  <li>
      <input type="checkbox" @click="deleteItem" :checked="item.done" />
      <span v-bind:class="{delete: item.done}">{{ item.todo }}</span>
    </li>
</template>

<script>
export default {
  props: ["item"],
  methods: {
    deleteItem: function() {
      this.item.done = this.item.done ? false : true;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.delete {
  text-decoration: line-through;
}
</style>
