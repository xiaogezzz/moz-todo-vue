<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper">
      <label for="new-todo-input">接下来需要做什么呢 </label>
    </h2>
    <input
      type="text"
      name="new-todo"
      id="new-todo-input"
      autocomplete="off"
      v-model.trim.lazy="label"
      class="input__lg"
    />
    <button class="btn btn__primary btn__lg" type="submit">创建</button>
  </form>
</template>

<script>
export default {
  methods: {
    onSubmit() {
      if (this.label === "") {
        return;
      }
      this.$emit("todo-added", this.label);
      this.label = "";
    },
  },
  data() {
    return { label: "" };
  },
};
</script>
