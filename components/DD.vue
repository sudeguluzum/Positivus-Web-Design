<template>
  <div class="relative">
    <div
      class="w-full flex items-center justify-between pb-2 cursor-pointer gap-2"
      @click="showDropdown = !showDropdown"
    >
    <Icon v-if="selectedItem?.icon" :name="selectedItem.icon" class="text-xl px-2" />
    <input
        type="text"
        :placeholder="placeholder"
        readonly
        :value="selectedItem?.text || selectedItem"
        class="w-full bg-transparent outline-none"
      />
      <Icon
        name="mingcute:down-line"
        class="text-xl ml-2 text-gray-600"
      />
    </div>

    <div
      class="absolute bottom-0 left-0 h-[2px] w-full bg-gradient-to-r from-[#8c33ef] to-[#5929B9]"
    ></div>

    <ul
      v-if="showDropdown"
      class="absolute z-10 w-full bg-white border border-gray-300 rounded-md mt-1 max-h-48 overflow-y-auto shadow-lg text-black"
    >
      <li
        v-for="(item, index) in items"
        :key="index"
        @click="selectItem(item)"
        class="px-4 py-2 hover:bg-purple-100 cursor-pointer flex items-center gap-2"
      >
      <Icon v-if="item.icon" :name="item.icon" class="text-xl" />
        <slot name="itemSlot" :item="item" :index="index">
          {{ item.text }}
        </slot>
      </li>
    </ul>
  </div>
</template>

<script setup>

// Dropdown görünürlüğünü kontrol ediyoruz
const showDropdown = ref(false);

// Seçilen öğeyi saklıyoruz
const selectedItem = ref(null);

// `items` prop'u dışarıdan geliyor
const props = defineProps({
  items: {
    type: Array,
    default: () => []
  },
  placeholder: {
    type: String,
    default: "Seçiniz"
  }
});

// Seçilen öğeyi belirliyoruz
const selectItem = (item) => {
  selectedItem.value = item;
  showDropdown.value = false;
  
};
</script>

