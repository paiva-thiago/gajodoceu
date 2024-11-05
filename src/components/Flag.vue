<script setup>
  defineProps({
  countryCode: {
    type: String,
    required: true,
  },
});  

</script>
<template>
  <img :src="`/images/flag-${countryCode}.png`"  alt="Flag" width="23" height="15">
</template>