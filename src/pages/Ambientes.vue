<template lang="pug">
q-page-container 
  section.mode
      q-btn-toggle(
        v-model="active"
        push
        toggle-color="grey-4"
        :options="[{value: 'module', slot: 'module'}, {value: 'list', slot: 'list'}]"
      )
        template(v-slot:module)
          div(class="row items-center no-wrap")
            q-icon(name="view_module")
        template(v-slot:list)
          div(class="row items-center no-wrap")
            q-icon(right name="view_list")
  section.row
    button.environment
      q-btn(round color="accent" icon="edit" @click="card = !card")
      h3 Nome do ambiente
  q-dialog(v-model="card")
    q-card(style="width: 30vw")
      q-card-section
        div(style="font: 2rem/3rem 'Poppins Medium';") Nome do ambiente
      q-separator
      q-card-section(style="max-height: 50vh; width: 100%; padding: 0;")
        q-list(clickable v-ripple style="font: 1rem/2rem 'Poppins';")
          q-item(clickable v-ripple)
            q-item-section Nome do site
          q-item(clickable v-ripple)
            q-item-section Nome do site
          q-item(clickable v-ripple)
            q-item-section Nome do site
      q-separator
      q-card-actions(align="right")
        q-btn(flat label="Cancelar" no-caps color="dark" v-close-popup)
        q-btn(flat label="Confirmar" no-caps color="positive" v-close-popup)
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'Ambientes',
  data() {
    return{
      card: ref(false),
      active: ref('module')
    }
  }
})
</script>

<style lang="scss" scoped>
.q-page-container {

  font-family: 'Poppins';

  .mode {
    width: 100%;
    text-align: right;
    font-size: 2.5em; 
    padding: 1rem;
    
      .q-icon {
        padding: 1rem;
        cursor: pointer;
        color: $primary;
      }
  }

  .environment {
    width: 17vw;
    height: 17vw;
    border: none;
    background: $accent;
    color: white;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;

    &:hover {
      background-color: $secondary;
    }

    h3 {
      position: relative;
      top: -1vw;
      font: 2rem/3rem 'Poppins Bold';

    }

    & button {
      position: relative;
      top: -1vw;
      right: -6vw;
      color: white;
    }
  }

  .q-item {
    width: 100%;
  }

}
</style>