<template>
        <div>
          <NuxtLink :to="url" class="text-white flex items-center">
            <Icon
              :name="icon"
              class="w-5 h-5 text-green-700 mr-1"
            /> {{ name }}  <Icon :name="icon" class="w-5 h-5 text-white ml-1" />
        
          </NuxtLink>
        </div>
</template>

<script setup>
defineProps(["id", "name","icon"]);

</script>