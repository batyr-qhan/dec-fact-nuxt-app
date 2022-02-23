<template>
  <div class="grid grid-cols-12 py-8 items-center">
    <div class="col-span-6">
      <input
        class="
          border-2 border-solid border-gray-300
          w-full
          focus:outline-none
          p-1
          rounded
        "
        type="text"
      />
    </div>
    <div class="col-span-4"></div>
    <div class="col-span-2 flex justify-around items-center">
      <div class="w-8 h-8 rounded-full bg-green-500 "></div>
      <div class="flex flex-col text-center">
        <span class="font-bold">John Doe</span>
        <span>Administrator</span>
      </div>
    </div>
  </div>
</template>

<style>
.headerContainer {
  display: flex;
}
.input {
  width: 100%;
}
.spacer {
  flex: 2;
}
.userInfo {
  flex: 2;
}
</style>