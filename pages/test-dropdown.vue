<!-- <template>
  <div>
    <DD :items="items">
      <template #btn>
        <button>Seçilen Sude</button>
      </template>
      <template #itemSlot="{ item, index }">
        <p>#{{ index }} - {{ item }}</p>
      </template>
      
    </DD>
  </div>
</template>

<script setup>
const items = ["Sude", "Gül", "Üzüm"];


</script> -->

<template>
  <div>
    <!-- 1. Liste: Aylar -->
    <DD :items="months" v-model="selectedMonth" placeholder="Ay">
      <template #btn>
        <button>{{ selectedMonth }}</button>
      </template>
      <template #itemSlot="{ item, index }">
        <p>{{ item }}</p>
      </template>
    </DD>

    <DD :items="taxs" v-model:selected="selectedTax" placeholder="TR">
      <template #btn>
        <button>
          <Icon
            v-if="selectedTax?.icon"
            :name="selectedTax.icon"
            class="text-xl px-2"
          />
          {{ selectedTax?.text || "Seçiniz" }}
        </button>
      </template>
    </DD>

    <DD :items="states" v-model:selected="selectedState" placeholder="TR">
      <template #btn>
        <button>
          <Icon
            v-if="selectedState?.icon"
            :name="selectedState.icon"
            class="text-xl px-2"
          />
          {{ selectedState?.text || "Seçiniz" }}
        </button>
      </template>
    </DD>
  </div>
</template>

<script setup>

const months = [
  "01",
  "02",
  "03",
  "04",
  "05",
  "06",
  "07",
  "08",
  "09",
  "10",
  "11",
  "12",
];

const taxs = [
  { icon: "flag:tr-4x3", text: "TR" },
  { icon: "twemoji:flag-united-states", text: "USA" },
  { icon: "twemoji:flag-canada", text: "CDN" },
];


const states = [
 { icon: "flag:tr-4x3", text: "Türkiye" },
  { icon: "twemoji:flag-united-states", text: "Amerika" },
 { icon: "twemoji:flag-canada", text: "Canada" },
 ];

const selectedMonth = ref(null);
const selectedTax = ref(null);
const selectedState = ref(null);
</script>
