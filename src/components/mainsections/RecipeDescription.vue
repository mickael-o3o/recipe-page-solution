<script setup lang="ts">
const preparationTime = [
  'Total: Approximately 10 minutes',
  'Preparation: 5 minutes',
  'Cooking: 5 minutes',
]
</script>

<template>
  <section class="description-container">
    <h1 class="recipe-name">Simple Omelette Recipe</h1>
    <p class="recipe-description">
      An easy and quick dish, perfect for any <br />
      meal. This classic omelette combines beaten eggs cooked to perfection, optionally filled with
      your choice of cheese, vegetables, or meats.
    </p>

    <div class="recipe-preparation-time">
      <h3 class="recipe-preparation-time-header">Preparation time</h3>
      <div class="recipe-preparation-time-list">
        <ListWithHightlight :disc="true" :list="preparationTime" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.description-container {
  display: flex;
  flex-direction: column;
  gap: 1.8rem;
}

.recipe-name {
  font: {
    family: var(--font-family-young-serif);
    size: 2.4rem;
  }
  line-height: 2.4rem;
}

.recipe-preparation-time {
  background-color: var(--color-rose-50);
  padding: 1.8rem;
  border-radius: 1rem;

  &-header {
    font: {
      size: 1.3rem;
      weight: 600;
    }
    color: var(--color-rose-800);
    margin-bottom: 1rem;
  }

  &-list {
    margin-left: 0.6rem;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }
}
</style>
