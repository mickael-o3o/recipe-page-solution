<template>
  <footer class="p-footer">
    <p class="p-footer__attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
      Coded by <a href="https://github.com/mickael-o3o/recipe-page-solution.git">mickael-o3o</a>.
    </p>
  </footer>
</template>

<style scoped lang="scss">
.p-footer {
  &__attribution {
    font-size: 0.6875rem;
    text-align: center;
    font-family: monospace;
    line-height: 1.5rem;
    margin: 1rem auto;
    inline-size: calc(100% - 1rem);
    padding: 0.5rem;
    background-color: var(--color-rose-50);
    border: 0.0625rem solid var(--color-rose-800);
  }

  a {
    color: hsl(228, 45%, 44%);
  }
}
</style>
