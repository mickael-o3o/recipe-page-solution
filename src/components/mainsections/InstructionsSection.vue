<script setup lang="ts">
import ReusableListItem from '../utils/ReusableListItem.vue'

interface Props {
  instructions: string[]
}

const { instructions } = defineProps<Props>()
</script>

<template>
  <section class="instructions-container">
    <h2 class="instructions-header">Instructions</h2>
    <ol class="instructions-list">
      <li v-for="(item, index) in instructions" :key="index">
        <ReusableListItem :item="item" :include-hightlight="true" />
      </li>
    </ol>
  </section>
</template>

<style lang="scss" scoped>
@use '../../assets/utils/mixins';

.instructions {
  &-header {
    @include mixins.section-header;
  }
  &-list {
    @include mixins.list;
    counter-reset: li;

    li {
      padding-left: 2.625rem;
      position: relative;

      &::before {
        content: counter(li) '.';
        counter-increment: li;
        color: var(--color-brown-800);
        font-weight: 700;
        display: inline;
        position: absolute;
        top: 0.5rem;
        left: 0.5rem;
        translate: 0 -0.5rem;
      }
    }
  }
}
</style>
