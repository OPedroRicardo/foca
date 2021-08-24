<template lang="pug">
q-dialog(v-model="relogio" position="bottom" seamless)
    q-card(style="width: 350px")
        q-card-section.row.items-center.justify-between.no-wrap(style="padding: 0;")
            .column.items-center.justify-between
                .text-weight-bold {{ fase }}
                .text.weight-bold(style="font-size: 2rem;") {{ tempoFormatado }}
            button(:class="estado" @click="iniciar()")
                q-icon(:name="estado")
</template>

<script>
import { ref } from 'vue'

export default {
    data() {
        return {
            relogio: ref(true),
            fase: 'Trabalho', // Trabalho, Pausa curta, Pausa longa
            estado: 'play_arrow', // pause, stop, play_arrow
            color: 'positive',
            tempo: 1500,
            tempoFormatado: '00:00'
        }
    },
    methods: {
        iniciar() {
            const relogio = setInterval(() => {
                /* if(this.estado == 'play_arrow') {
                    clearInterval(relogio)
                    return
                } */
                this.tempoFormatado = new Date(this.tempo * 1000).toISOString().substr(11, 8)
                --this.tempo
            }, 1000)

            relogio()
        }
    }
}
</script>

<style lang="scss" scoped>
.q-dialog {
    font: 5rem/6rem 'Poppins Medium';
    padding: 0;

    .q-card {
        background: $primary;
        color: #fefefe;
    }

    button {
        width: 5rem;
        height: 5rem;
        margin: 0;
        border: none;
        cursor: pointer;
        transition: filter 0.3s;

        &:hover {
            filter: brightness(0.85);
        }

        .q-icon {
            font-size: 2rem;
            color: #fefefe;
        }

        &.pause {
            background-color: $negative;
        }

        &.play_arrow {
            background-color: $positive;
        }

        &.stop {
            background-color: $info;
        }
    }

    .column {
        width: calc(100% - 5rem);
    }
}
</style>