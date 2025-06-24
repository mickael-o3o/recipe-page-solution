<script setup lang="ts">
import DescriptionSection from './mainsections/DescriptionSection.vue'
import InstructionsSection from './mainsections/InstructionsSection.vue'
import NutritionSection from './mainsections/NutritionSection.vue'

const preparations = [
  ' Total: Approximately 10 minutes',
  'Preparation: 5 minutes',
  'Cooking: 5 minutes',
]
const ingredients = [
  '2-3 large eggs',
  '  Salt, to taste',
  '  Pepper, to taste',
  ' 1 tablespoon of butter or oil',
  '  Optional fillings: cheese, diced vegetables, cooked meats, herbs',
]

const instructions = [
  'Beat the eggs: In a bowl, beat the eggs with a pinch of salt and pepper until they are well mixed. You can add a tablespoon of water or milk for a fluffier texture.',

  'Heat the pan: Place a non-stick frying pan over medium heat and add butter or oil.',

  'Cook the omelette: Once the butter is melted and bubbling, pour in the eggs. Tilt the pan to ensure the eggs evenly coat the surface.',

  'Add fillings (optional): When the eggs begin to set at the edges but are still slightly runny in the middle, sprinkle your chosen fillings over one half of the omelette.',
  'Fold and serve: As the omelette continues to cook, carefully lift one edge and fold it over the fillings. Let it cook for another minute, then slide it onto a plate.',

  'Enjoy: Serve hot, with additional salt and pepper if needed.',
]

const nutritions = { Calories: '277kcal', Carbs: '0g', Protein: '20g', Fat: '22g' }
</script>

<template>
  <header class="p-header">
    <img
      src="/images/image-omelette.jpeg"
      alt="omelette image"
      width="1312px"
      height="600px"
      class="p-header__image"
    />
  </header>
  <main class="p-main">
    <DescriptionSection :preparations="preparations" :ingredients="ingredients" />
    <hr />
    <InstructionsSection :instructions="instructions" />
    <hr />
    <NutritionSection :nutritions="nutritions" />
  </main>
</template>

<style lang="scss" scoped>
.p-header {
  margin: 0 auto;
  background-color: var(--color-white);
  inline-size: 100%;
  overflow: hidden;

  @media (min-width: 812px) {
    margin-top: 7.7rem;
    padding: 2.5rem;
    padding-bottom: 0;
    border-radius: 1rem 1rem 0 0;
  }

  &__image {
    max-width: 100%;
    height: auto;
    display: block;

    @media (min-width: 812px) {
      border-radius: 0.5rem;
    }
  }
}

.p-main {
  background-color: var(--color-white);
  inline-size: 100%;
  margin: 0 auto;
  padding: 2.5rem;
  padding-top: 2.45rem;
  padding-block-end: 1.8rem;
  border-radius: 0 0 1rem 1rem;
  display: flex;
  flex-direction: column;
  gap: 2.02rem;
}

hr {
  color: palegoldenrod;
}
</style>
