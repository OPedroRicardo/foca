<template lang="pug">
q-layout
  q-header
    q-toolbar.row.items-center.justify-center Foca
  section-drawer
  router-view
</template>

<script>
import { defineComponent, ref } from 'vue';
import sectionDrawer from '../components/sectionDrawer.vue'

export default defineComponent({
  name: 'MainLayout',
  data() {
    return {

    }
  },
  components: {
    sectionDrawer
  }
})
</script>

<style lang="scss" scoped>
.q-page {
  .q-list {
    .q-item {
      height: 64px;
      padding: 8px auto;
    }
  }
}
</style>