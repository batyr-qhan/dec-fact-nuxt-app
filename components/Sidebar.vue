<template>
  <div class="sidebarContainer border-r-gray-700 border-r-2 w-48 px-8">
    <div class="header py-10">
      <div class="logo_placeholder"></div>
    </div>
    <ul class="itemsList">
      <NuxtLink to="/">
        <li class="menuItemContainer text-center mb-4">
          <p class="icon">
            <b-icon-arrow-up></b-icon-arrow-up>
          </p>
          <span>Опросы</span>
        </li>
      </NuxtLink>
      <NuxtLink to="/users">
        <li class="menuItemContainer text-center mb-4">
          <p class="icon">
            <b-icon-person></b-icon-person>
          </p>
          <span>Пользователи</span>
        </li>
      </NuxtLink>
      <NuxtLink to="/black-lists">
        <li class="menuItemContainer text-center mb-4">
          <p class="icon">
            <b-icon-card-list></b-icon-card-list>
          </p>
          <span>Черные списки</span>
        </li>
      </NuxtLink>
      <NuxtLink to="/call-center">
        <li class="menuItemContainer text-center">
          <p class="icon">
            <b-icon-telephone></b-icon-telephone>
          </p>
          <span>Колл-центр</span>
        </li>
      </NuxtLink>
    </ul>
  </div>
</template>

<script>
import {
  BIcon,
  BIconArrowUp,
  BIconPerson,
  BIconCardList,
  BIconTelephone,
} from "bootstrap-vue";
export default {
  name: "Sidebar",
  components: {
    BIconArrowUp,
    BIconPerson,
    BIconCardList,
    BIconTelephone,
  },
  setup() {},
};
</script>
<style>
a.nuxt-link-active {
}
a.nuxt-link-exact-active .menuItemContainer {
  color: #00c58e;
  border: 3px solid #00c58e;
  border-radius: 5px;
}
.sidebarContainer {
  overflow: hidden;
}
.header {
  display: flex;
  justify-content: center;
  align-items: center;
}
.logo_placeholder {
  width: 35px;
  height: 35px;
  background-color: blueviolet;
  border-radius: 50%;
}

.menuItemContainer {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px 10px;
  border: 3px solid transparent;
}
.menuItemContainer:hover {
  border: 3px solid #32de84;
  border-radius: 5px;
  color: #32de84;
}
.icon {
  font-size: 30px;
}
</style>