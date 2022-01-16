<template>
  <div class="kidItemContainer">
    <div>
      <strong>{{ idx }} </strong>
    </div>
    <div>Имя: {{ kid.name }}</div>
    <div>Возраст: {{ kid.age }}</div>
    <button class="removeBtn" @click="this.$emit('removeKid', kid.id)">
      Удалить
    </button>
  </div>
</template>
<script>
export default {
  props: ["kid", "idx"],
};
</script>

<style lang="scss" scoped>
.kidItemContainer {
  padding: 5px;
  display: flex;
  border: 1px solid blue;
  border-radius: 5px;
  justify-content: space-between;
  margin: 10px;
}
.removeBtn {
  background-color: red;
  color: #ffff;
  font-weight: 700;
  border-radius: 5px;
}
</style>
