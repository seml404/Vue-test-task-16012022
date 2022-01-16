<template>
  <div class="addKiddFormContainer">
    <form>
      <input type="text" placeholder="Имя ребенка" v-model="name" />
      <input type="number" placeholder="Возраст ребенка" v-model="age" />
      <button @click.prevent="handleAddKid">Добавить ребенка</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      age: "",
    };
  },
  methods: {
    handleAddKid() {
      if (this.name && this.age) {
        this.$emit("addKid", {
          name: this.name,
          age: this.age,
          id: Date.now(),
        });
        this.name = "";
        this.age = "";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
form {
  display: flex;
  justify-content: space-between;
}
</style>
