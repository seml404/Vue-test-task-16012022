<template>
  <div class="main">
    <h1>Форма для добавления детей и их родителей</h1>
    <kids-list
      v-if="kidsList.length"
      :kids="kidsList"
      @removeKid="handleRemoveKid"
    />
    <alert v-else />
    <add-kid @addKid="handleAddKid" />
  </div>
</template>

<script>
import AddKid from "./components/AddKid.vue";
import Alert from "./components/Alert.vue";
import KidsList from "./components/KidsList.vue";
export default {
  components: { KidsList, AddKid, Alert },
  data() {
    return {
      kidsList: [],
    };
  },
  methods: {
    handleAddKid(kid) {
      this.kidsList.push({ id: kid.id, name: kid.name, age: kid.age });
    },
    handleRemoveKid(id) {
      console.log("removing");
      this.kidsList = this.kidsList.filter((kid) => kid.id !== id);
    },
  },
};
</script>

<style lang="scss">
.main {
  max-width: 500px;
  margin: 0 auto;
  padding: 30px;
  border: 1px solid grey;
  border-radius: 10px;
}
</style>
