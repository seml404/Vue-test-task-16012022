<template>
  <div>
    <form class="addForm">
      <input type="text" placeholder="ФИО родителей" v-model="name" />
      <button @click.prevent="handleAddParent">Указать родителей</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
    };
  },
  methods: {
    handleAddParent() {
      this.$emit("addParent", this.name);
      this.name = "";
    },
  },
};
</script>

<style lang="scss" scoped></style>
