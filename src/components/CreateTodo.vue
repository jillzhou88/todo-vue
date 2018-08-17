<template>
    <form>
      <input type="text" v-model="text" @keyup.enter="sendText" />
      <input type="button" value="Add Todo" @click="sendText" />
    </form>
</template>

<script>
export default {
  data() {
      return {
          text: ''
      }
  },
  methods: {
    sendText() {
      if (this.text.trim()) {
        this.$emit("create-todo", this.text);
        this.text = "";
      }
    }
  }
};
</script>

</script>