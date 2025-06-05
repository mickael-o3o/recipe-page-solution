<script setup lang="ts">
interface Props {
  nutritions: {
    Calories: string
    Carbs: string
    Fat: string
  }
}

const { nutritions } = defineProps<Props>()
</script>

<template>
  <section class="nutrition-container">
    <h2 class="nutrition-header">Nutrition</h2>
    <p class="nutrition-description">
      The table below shows nutritional values per serving without the additional fillings.
    </p>
    <table class="nutrition-table">
      <tbody>
        <tr v-for="(value, key) in nutritions" :key="key">
          <td class="nutrition-table-key">{{ key }}</td>
          <td class="nutrition-table-value">{{ value }}</td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<style lang="scss">
@use '../../assets/utils/mixins';

.nutrition {
  &-header {
    @include mixins.section-header;
  }

  &-description {
    margin-bottom: 1rem;
  }

  &-table {
    width: 100%;

    td {
      border-bottom: 1px solid var(--color-stone-150);
      width: 50%;
    }

    &-key {
      padding: 0.75rem 0;
      padding-left: 2.125rem;
    }

    &-value {
      font-weight: 600;
      color: var(--color-brown-800);
      text-align: left;
      padding-left: 0.5rem;
    }
  }
}
</style>
