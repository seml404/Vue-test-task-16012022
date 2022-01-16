<template>
  <div class="kidsListContainer">
    <add-parents @addParent="handleAddParents" />
    <p>{{ parentsName }}</p>
    <kid-item
      v-for="(kid, idx) in kids"
      :kid="kid"
      :key="kid.id"
      :idx="idx + 1"
      @removeKid="this.$emit('removeKid', kid.id)"
    />
  </div>
</template>

<script>
import KidItem from "./KidItem.vue";
import AddParents from "./AddParents.vue";
export default {
  data() {
    return {
      parentsName: "",
    };
  },

  props: ["kids"],
  components: { KidItem, AddParents },
  methods: {
    handleAddParents(name) {
      console.log("setting");
      this.parentsName = name;
    },
  },
};
</script>

<style lang="scss" scoped>
.kidsListContainer {
  border: 1px solid #000;
  border-radius: 5px;
  padding: 5px;
  margin: 5px;
}
</style>
