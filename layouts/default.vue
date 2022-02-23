<template>
  <div class="grid grid-cols-12">
    <div class="col-span-2"><Sidebar /></div>
    <div class="col-span-10">
      <Header />
      <Nuxt />
    </div>
  </div>
</template>

<script>
import Sidebar from "../components/Sidebar.vue";
import Header from "../components/Header.vue";
export default {
  components: { Sidebar, Header },
  setup() {},
};
</script>