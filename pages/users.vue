<template>
  <div>
    <nav>
      <ul class="flex navigation-bar">
        <nuxt-link class="flex-1 text-center py-4" to="/users/parameters"
          >Parameters</nuxt-link
        >
        <nuxt-link class="flex-1 text-center py-4" to="/users/questions"
          >Questions</nuxt-link
        >
        <nuxt-link class="flex-1 text-center py-4" to="/users/logic"
          >Logic</nuxt-link
        >
        <nuxt-link class="flex-1 text-center py-4" to="/users/conditions"
          >conditions</nuxt-link
        >
        <nuxt-link class="flex-1 text-center py-4" to="/users/respondents"
          >Respondents</nuxt-link
        >
      </ul>
    </nav>
    <nuxt-child></nuxt-child>
  </div>
</template>

<style>
a.nuxt-link-active {
  font-weight: bold;
}
/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  color: #00c58e;
  border-bottom: 3px solid #00c58e;
}
.navigation-bar {
    border-bottom: 1px solid #00c58e;
}

</style>