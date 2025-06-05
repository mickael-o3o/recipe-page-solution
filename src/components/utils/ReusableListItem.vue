<script setup lang="ts">
interface Props {
  item: string
  includeDisc?: boolean
  includeHightlight?: boolean
}

const { item, includeDisc } = defineProps<Props>()
</script>

<template>
  <div class="list-item">
    <span v-if="includeDisc" class="list-item-disc"></span>
    <p class="list-item-content">
      <span :class="{ 'list-item-content-hightlight': includeHightlight }">{{
        item.includes(':') ? item.split(':')[0] : ''
      }}</span>
      {{ item.includes(':') ? item.substring(item.indexOf(':')) : item }}
    </p>
  </div>
</template>

<style lang="scss" scoped>
.list-item {
  display: flex;
  align-items: center;
  gap: 1.5rem;

  &-disc {
    display: inline-block;
    width: 0.25rem;
    height: 0.25rem;
    border-radius: 100%;
    background-color: var(--color-rose-800);
    flex-shrink: 0;
  }

  &-content {
    &-hightlight {
      font-weight: 700;
    }
  }
}
</style>
