<template>
  <div>
    <header
      class="
        flex
        items-stretch
        justify-center
        border-b-2 border-gray-100
        space-x-14
        text-blue-700
        underline
        p-3
      "
    >
      <div>
        <nuxt-link to="/">Home</nuxt-link>
      </div>
      <div>
        <nuxt-link to="jokes">Questions</nuxt-link>
      </div>
      <div>
        <nuxt-link to="/about">About</nuxt-link>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'AppHeader',
}
</script>

<style>
</style>