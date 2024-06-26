<script setup>
import { FaBars, MdSharpClose } from '@kalimahapps/vue-icons'

const emits = defineEmits(["toggleMenu"]);
const toggleMenu = () => emits("toggleMenu");
const props = defineProps({
  isMenuOpen: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div class="h-12 button z-50">
    <button @click="toggleMenu" class="flex items-center justify-center">
      <MdSharpClose v-if="isMenuOpen" />
      <FaBars v-else />
    </button>
  </div>

</template>

<style scoped>
.button {
  display: none;
}

@media (max-width: 1023px) {
  .button {
    display: flex;
    align-items: center;
  }
}

button {
  width: 38px !important;
  padding: 10px;
}
</style>