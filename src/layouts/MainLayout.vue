<template lang="pug">
q-layout
  router-view
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MainLayout',
  data() {
    
  },
})
</script>

<style lang="scss" scoped>
.q-layout {
  height: 100%;
  background: linear-gradient(295.46deg, #173647 0%, #175449 78.62%);
  font-family: 'Poppins';
  color: #fefefe;
}
</style>