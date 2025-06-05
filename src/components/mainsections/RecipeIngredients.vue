<script setup lang="ts">
const ingredients = [
  '2-3 large eggs',
  'Salt, to taste',
  'Pepper, to taste',
  '1 tablespoon of butter or oil',
  'Optional fillings:',
  'cheese, diced vegetables, cooked meats, herbs',
]
</script>

<template>
  <section class="ingredient-container">
    <h2 class="header">Ingredients</h2>
    <div class="ingredient-list">
      <p class="list-item-container" v-for="(ingredient, index) in ingredients" :key="index">
        <span class="list-disc"></span>
        <span class="list-item"></span>{{ ingredient }}
      </p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use '../../assets/utils/mixins';
.header {
  @include mixins.header;
}

.ingredient-list {
  margin-left: 0.6rem;
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}

@include mixins.list;
</style>
