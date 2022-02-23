<template>
  <div class="p-8 shadow-md">
    <p class="mb-4 text-lg font-bold">Добавить опрос</p>
    <form v-on:submit.prevent="handleSubmit()">
      <ul>
        <li v-for="(condition, index) in conditions">
          <form-item
            :item="condition"
            :index="index"
            :key="index"
            :isLast="index + 1 !== conditions.length"
            :conditions="conditions"
            @remove-item="removeItem(index)"
          ></form-item>
        </li>
      </ul>

      <div class="pt-8">
        <button
          @click="addItem"
          :disabled="conditions.length > 2"
          :class="{ disabled: conditions.length > 2 }"
          class="
            addButton
            flex flex-col
            items-center
            justify-center
            border-2
            text-green-500
            p-4
            rounded
            cursor-pointer
            w-full
          "
        >
          <b-icon-plus class="text-4xl"></b-icon-plus>
          <span>add new condition</span>
        </button>
      </div>
      <div class="flex justify-end pt-8">
        <button
          type="submit"
          class="
            bg-green-500
            hover:bg-green-700
            text-white
            font-bold
            py-2
            px-4
            border border-green-700
            rounded
            w-40
          "
        >
          Submit
        </button>
      </div>
    </form>
  </div>
</template>

<script>
import { BIconPlus } from "bootstrap-vue";

export default {
  components: { BIconPlus },
  data() {
    return {
      conditions: [],
    };
  },
  methods: {
    addItem() {
      let formItemObj = {
        condition: "",
      };
      this.conditions.push(formItemObj);
    },
    removeItem(index) {
      this.conditions.splice(index, 1);
    },
    handleSubmit: function () {
      let payload = {
        conditions: this.conditions,
      };
      console.log(payload);

      fetch("https://test.com/api/get_product", {
        method: "POST",
        body: JSON.stringify(payload),
      })
        .then(function (response) {
          // your action after success
          console.log(response);
        })
        .catch(function (error) {
          // your action on error success
          console.log(error);
        });
    },
  },
  //   computed: {
  //     filteredOptions() {
  //       let arr = this.conditions.map((el) => el.condition);
  //       return arr;
  //     },
  //   },
  setup() {},
};
</script>

<style>
.addButton:hover {
  background: #f0f0f0;
}
.disabled {
  background-color: transparent;
}
.disabled:hover {
  background-color: transparent;
}
</style>