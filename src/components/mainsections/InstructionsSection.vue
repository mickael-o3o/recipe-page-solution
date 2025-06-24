<script setup lang="ts">
import ReusableListItem from '../utils/ReusableListItem.vue'

interface Props {
  instructions: string[]
}

const { instructions } = defineProps<Props>()
</script>

<template>
  <section class="s-instructions">
    <h2 class="s-instructions__header">Instructions</h2>
    <ol class="s-instructions__list">
      <li v-for="(item, index) in instructions" :key="index">
        <ReusableListItem :item="item" :include-hightlight="true" />
      </li>
    </ol>
  </section>
</template>

<style lang="scss" scoped>
@use '../../assets/utils/mixins';

.s-instructions {
  &__header {
    @include mixins.section-header;
  }

  &__list {
    @include mixins.list;
    counter-reset: li;

    li {
      padding-inline-start: 2.5rem;
      position: relative;
      letter-spacing: -0.006rem;

      &::before {
        content: counter(li) '.';
        letter-spacing: 0.01rem;
        counter-increment: li;
        color: var(--color-brown-800);
        font-weight: 700;
        display: inline;
        position: absolute;
        inset-block-start: 0.5rem;
        inset-inline-start: 0.5rem;
        translate: 0 -0.5rem;
      }
    }
  }
}
</style>
