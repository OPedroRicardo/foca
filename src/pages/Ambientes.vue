<template lang="pug">
q-page-container 
  section.row
    button.environment
      h3 Nome do ambiente
      q-btn(round color="none" icon="edit")
</template>
<script>
import { defineComponent, ref } from 'vue';

const drawerList = [
  {
    icon: 'dashboard_customize',
    label: 'Ambientes'
  },
  {
    icon: 'task_alt',
    label: 'Tarefas'
  },
  {
    icon: 'alarm',
    label: 'Relógio'
  },
  {
    icon: 'graphic_eq',
    label: 'Música'
  },
  {
    icon: 'spa',
    label: 'Bem estar'
  },
  {
    icon: 'settings_suggest',
    label: 'Configurações'
  },
]

export default defineComponent({
  name: 'Ambientes',
  data() {
    return{
      drawer: ref(true) ,
      drawerList,
      drawerClick () {
        drawer = !drawer
      } 
    }
  }
})
</script>

<style lang="scss" scoped>
.q-page-container {

  font-family: 'Poppins';

  .environment {
    width: 17vw;
    height: 17vw;
    border: none;
    background: $accent;
    color: white;
    border-radius: 8px;
    cursor: pointer;
    transition: filter 0.3s ease-out;

    &:hover {
      filter: brightness(0.9);
    }

    h3 {
      font: 2rem/3rem 'Poppins Bold';
    }

    & button {
      position: relative;
      top: 6px;
      right: 6px;
      color: white;
    }
  }

}
</style>