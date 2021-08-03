<template lang="pug">
q-drawer.bg-secondary(
    v-model="drawer"
    show-if-above
    bordered
    :width="282"
    :breakpoint="500"
    @click.capture="drawerClick"
    dark
    )
        q-scroll-area.fit
            q-list.column.justify-between
                template(v-for="item in drawerList")
                    q-item(clickable :active="item.label === 'Outbox'" v-ripple)
                        q-item-section(avatar)
                            q-icon(:name="item.icon")
                        q-item-section {{ item.label }}
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


export default {
    name: "sectionDrawer",
    data() {
        return {
            drawerList,
            drawer: ref(true),
            drawerClick () {
                drawer = !drawer 
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.q-item {
    opacity: 0.85;

    &.active {
        opacity: 1;
        font-weight: bold;
    }
}
</style>