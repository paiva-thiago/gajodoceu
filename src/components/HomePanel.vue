<script setup>
import Flag from './Flag.vue';

defineProps({
  appName: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ appName }}</h1>
    <h3>Um dicionário <Flag countryCode="pt"/>/<Flag countryCode="br"/> e <Flag countryCode="br"/>/<Flag countryCode="pt"/> </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
