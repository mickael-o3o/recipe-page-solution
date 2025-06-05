<script setup lang="ts">
import ReusableListItem from '../utils/ReusableListItem.vue'

interface Props {
  preparations: string[]
  ingredients: string[]
}

const { preparations, ingredients } = defineProps<Props>()
</script>

<template>
  <section class="description-container">
    <h1 class="name">Simple Omelette Recipe</h1>
    <p class="description">
      An easy and quick dish, perfect for any meal. This classic omelette combines beaten eggs
      cooked to perfection, optionally filled with your choice of cheese, vegetables, or meats.
    </p>
    <section class="preparation-time">
      <h2 class="preparation-time-header">Preparation time</h2>
      <ul class="preparation-time-list">
        <li v-for="item in preparations" :key="item">
          <ReusableListItem :item="item" :include-disc="true" :include-hightlight="true" />
        </li>
      </ul>
    </section>
    <section class="ingredients">
      <h2 class="ingredients-header">Ingredients</h2>
      <ul class="ingredients-list">
        <li v-for="item in ingredients" :key="item">
          <ReusableListItem :item="item" :include-disc="true" />
        </li>
      </ul>
    </section>
  </section>
</template>

<style lang="scss" scoped>
@use '../../assets/utils/mixins.scss';
.description-container {
  display: flex;
  flex-direction: column;
  gap: 1.75rem;
}

.name {
  font: {
    family: var(--font-family-young-serif);
    size: 2.25rem;
  }
  line-height: 2.25rem;
  color: var(--color-stone-900);
}

.preparation {
  &-time {
    background-color: var(--color-rose-50);
    border-radius: 1.25rem;
    padding: 1.5rem;

    &-header {
      font: {
        size: 1.375rem;
        weight: 600;
      }
      color: var(--color-rose-800);
      margin-bottom: 1rem;
    }
    &-list {
      @include mixins.list;
      margin-left: 8px;
    }
  }
}

.ingredients {
  &-header {
    @include mixins.section-header;
  }

  &-list {
    @include mixins.list;
  }
}
</style>
