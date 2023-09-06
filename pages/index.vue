<template>
  <main>
    <listItem
      v-for="(item, index) in database"
      :name="item.name"
      :department="item.deparment"
      :salary="item.salary"
      :position="index"
      v-on:deleteItem="deleteItem"
    />
  </main>
</template>

<script setup>
let database = ref([
  {
    name: 'Johnny',
    deparment: 'Marketing',
    salary: 30000,
  },
  {
    name: 'Sarah',
    deparment: 'Engineering',
    salary: 72000,
  },
  {
    name: 'Terrance',
    deparment: 'Executive',
    salary: 125000,
  },
]);

function deleteItem(position) {
  database.value.splice(position, 1);
}
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
</style>
