<script setup lang="ts">
import ReusableListItem from '../utils/ReusableListItem.vue'

interface Props {
  preparations: string[]
  ingredients: string[]
}

const { preparations, ingredients } = defineProps<Props>()
</script>

<template>
  <section class="s-recipe">
    <h1 class="s-recipe__name">Simple Omelette Recipe</h1>
    <p class="s-recipe__description">
      An easy and quick dish, perfect for any meal. This classic omelette combines beaten eggs
      cooked to perfection, optionally filled with your choice of cheese, vegetables, or meats.
    </p>

    <div class="s-recipe__preparation-time">
      <section class="c-preparation-time">
        <h2 class="c-preparation-time__header">Preparation time</h2>
        <ul class="c-preparation-time__list">
          <li v-for="item in preparations" :key="item">
            <ReusableListItem :item="item" :include-disc="true" :include-hightlight="true" />
          </li>
        </ul>
      </section>
    </div>

    <section class="s-ingredients">
      <h2 class="s-ingredients__header">Ingredients</h2>
      <ul class="s-ingredients__list">
        <li v-for="item in ingredients" :key="item">
          <ReusableListItem :item="item" :include-disc="true" />
        </li>
      </ul>
    </section>
  </section>
</template>

<style lang="scss" scoped>
@use '../../assets/utils/mixins.scss';
.s-recipe {
  display: flex;
  flex-direction: column;
  gap: 1.45rem;

  &__name {
    font: {
      family: var(--font-family-young-serif);
      size: 2.5rem;
    }
    line-height: 2.6rem;
    color: var(--color-stone-900);
  }

  &__description {
    letter-spacing: -0.006rem;
  }
}

.c-preparation-time {
  background-color: var(--color-rose-50);
  border-radius: 1.25rem;
  padding: 1.7rem;
  padding-block-start: 2.1rem;

  &__header {
    font: {
      size: 1.26rem;
      weight: 600;
    }
    color: var(--color-rose-800);
    margin-block-end: 0.95rem;
  }

  &__list {
    @include mixins.list;
    margin-inline-start: 0.55rem;
  }
}

.s-ingredients {
  &__header {
    @include mixins.section-header;
    margin-block-start: 0.75rem;
  }

  &__list {
    @include mixins.list;
    margin-inline-start: 0.55rem;
  }
}
</style>
