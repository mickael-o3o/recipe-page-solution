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
  <section class="s-nutrition">
    <h2 class="s-nutrition__header">Nutrition</h2>
    <p class="s-nutrition__description">
      The table below shows nutritional values per serving without the additional fillings.
    </p>
    <table class="s-nutrition__table">
      <tbody>
        <tr class="s-nutrition__table-row" v-for="(value, key) in nutritions" :key="key">
          <td class="s-nutrition__table-data s-nutrition__table-key">{{ key }}</td>
          <td class="s-nutrition__table-data s-nutrition__table-value">{{ value }}</td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<style lang="scss">
@use '../../assets/utils/mixins';

.s-nutrition {
  &__header {
    @include mixins.section-header;
  }

  &__description {
    margin-block-end: 0.75rem;
  }

  &__table {
    inline-size: 100%;
    border-collapse: collapse;
  }

  &__table-row {
    border-block-end: 1px solid var(--color-stone-150);

    &:last-child {
      border-block-end: none;
    }
  }

  &__table-data {
    inline-size: 50%;
  }

  &__table-key {
    padding: 0.725rem 0;
    padding-inline-start: 2rem;
  }

  &__table-value {
    font-weight: 600;
    color: var(--color-brown-800);
    text-align: left;
    padding-inline-start: 0.5rem;
  }
}
</style>
