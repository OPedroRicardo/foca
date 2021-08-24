<template lang="pug">
q-page-container.column.items-center
    section.row.items-center.justify-around.no-wrap
        span
            h1 Foca,
            h2 
                | desafiando seu foco de um jeito que você nunca viu.
                br
                | Só relaxa!
        img(src="foca.svg" alt="Foca")
    router-link(to="/focado") Desejo desafiar meu foco!
</template>

<script>
export default {
    data() {
        return {
            
        }
    }, 
}
</script>

<style lang="scss" scoped>
.q-page-container {
    height: 100vh;
    font-family: 'Poppins Bold';
    
    section {
        width: 100vw;
    
        span {
            max-width: 50vw;

            h1 {
                font: 94px/74px;
                margin: 0 0 1.5rem;
            }
            
            h2 {
                font: 42px/46px 'Poppins Medium';
                opacity: 0.7;
                margin: 0;
            }

        }

        img {
            max-width: 416px;
            width: 100%;
        }    
    }

    a {
        font-size: 1.5rem;
        color: #fefefe;
        opacity: 0.8;
        transition: opacity 0.3s;
        animation-iteration-count: infinite;
        -moz-animation   : loop 1.5s infinite;
        -webkit-animation: loop 1.5s infinite;
        -o-animation     : loop 1.5s infinite;
        animation        : loop 1.5s infinite;

        &:hover {
            opacity: 1;
        }
    }
}

@keyframes loop {
    0% {padding-top: 0}
    50% {padding-top: 8px}
    100% {padding-top: 0}
}

</style>