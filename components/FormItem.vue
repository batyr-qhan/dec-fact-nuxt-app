<template>
  <div class="grid grid-rows-2 gap-8 py-8 border-b-2 relative">
    <div class="grid grid-cols-12 items-center">
      <div class="col-span-4 text-lg">Условие {{ index + 1 }}</div>
      <div class="col-span-8">
        <select
          required
          class="w-full bg-transparent border-2 rounded p-2"
          v-model="item.condition"
          name="condition"
        >
          <option
            v-for="(option, i) in options"
            :key="option.id"
            :value="option.value"
          >
            {{ option.description }}
          </option>
        </select>
      </div>
    </div>
    <div v-if="item.condition === 'age'" class="grid grid-cols-12 items-center">
      <div class="col-span-4">Type</div>
      <div class="col-span-8">
        <label for="from">from</label>
        <input
          class="outline-none border-2 p-2 rounded mr-2"
          v-model="item.from"
          type="text"
          id="from"
          required
        />
        <label for="to">to</label>
        <input
          class="outline-none border-2 p-2 rounded"
          v-model="item.to"
          type="text"
          id="to"
          required
        />
      </div>
    </div>
    <div
      v-else-if="item.condition === 'card_type'"
      class="grid grid-cols-12 items-center"
    >
      <div class="col-span-4">Type</div>
      <div class="col-span-8">
        <select
          class="w-9/12 bg-transparent border-2 rounded p-2"
          v-model="item.type"
        >
          <option
            v-for="option in typeOptions"
            :value="option.value"
            :key="option.id"
          >
            {{ option.description }}
          </option>
        </select>
      </div>
    </div>
    <div
      v-else-if="item.condition === 'card_status'"
      class="grid grid-cols-12 items-center"
    >
      <div class="col-span-4">Status</div>
      <div class="col-span-8">
        <select
          class="w-9/12 bg-transparent border-2 rounded p-2"
          v-model="item.status"
        >
          <option
            v-for="option in statusOptions"
            :key="option.id"
            :value="option.value"
          >
            {{ option.description }}
          </option>
        </select>
      </div>
    </div>
    <div class="grid grid-cols-12">
      <div class="col-span-4"></div>
      <div class="col-span-8 grid grid-cols-12 justify-between">
        <button
          v-if="item.condition"
          class="
            col-span-3
            p-2
            border border-gray-500
            rounded
            text-gray-500
            bg-gray-300
          "
        >
          add
        </button>
        <div :class="[item.condition ? 'col-span-6' : 'col-span-9']"></div>
        <button
          @click="$emit('remove-item', index)"
          class="col-span-3 p-2 border border-red-500 rounded text-red-500"
        >
          remove
        </button>
      </div>
    </div>
    <div
      v-if="isLast"
      class="
        absolute
        -bottom-4
        left-3
        bg-green-500
        w-7
        h-7
        flex
        justify-center
        items-center
        rounded
      "
    >
      И
    </div>
  </div>
</template>

<script>
export default {
  props: ["item", "index", "isLast", "conditions"],
  data() {
    return {
      options: [
        { id: 1, value: "age", description: "Age" },
        { id: 2, value: "card_type", description: "Card Type" },
        { id: 3, value: "card_status", description: "Card Status" },
      ],
      typeOptions: [
        { id: 1, value: "gold", description: "Gold" },
        { id: 2, value: "silver", description: "Silver" },
      ],
      statusOptions: [
        { id: 1, value: "active", description: "Active" },
        { id: 2, value: "not_active", description: "Not Active" },
      ],
    };
  },
  computed: {
    filteredOptions() {
      let arr = this.conditions.map((el) => el.condition);
      return this.options.filter((el) => !arr.includes(el.value));
    },
  },
};
</script>