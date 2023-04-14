<template>
<div class="container">
    <h1 class="titulo">* Contador</h1>
    <div class="info">
    <p class="entrada">Cols: {{ cols }}</p>
        <button @click="incrementCols">+</button>
        <button @click="decrementCols">-</button>

    </div>
    <div class="info">
    <p class="entrada">Rows: {{ rows }}</p>
        <button @click="incrementRows">+</button>
        <button @click="decrementRows">-</button>

    </div>
</div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const cols = ref(0)
    const rows = ref(0)
    const incrementCols = () => {
        cols.value++
    }

    const decrementCols = () => {
        cols.value--
    }

    const incrementRows = () => {
        rows.value++
    }

    const decrementRows = () => {
        rows.value--
    }

    return { rows, cols, incrementRows, decrementRows, incrementCols, decrementCols }
  }
}
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 30%;
    border: 3px solid var(--border);
    border-radius: 16px;
    margin: 0 auto;
    margin-top: 1vw;
    margin-bottom: 5vw;
    padding-bottom: 2vw;
    background-color: var(--infoBack);
}
.titulo{
    font-size: 2vw;
    margin: 0;
    padding:1vw;
    background-color: var(--titlesBack);
    color: var(--titlesFront);
    border-bottom: 3px solid var(--border);
}

img{
    width: 200px;
    height: auto;
    margin-left: auto;
    margin-right: auto;
    margin-top: 2vw;
    border-radius: 250px;
}
.info{
    display: flex;
    flex-direction: row;
    align-items: center;
    background-color: var(--infoBack);
    padding: 0;
    padding-top: 3vw;
}
button{
    margin-left: 2vw;
    width: 3vw;
    height: 2vw;
    font-size: 2vw;
    text-align: center;
}
    p.entrada{
    width: 10vw;
        margin: 0;
        margin-left: 4vw;
    }
@media screen and (max-width: 1000px) {
    .container{
        margin-top: 5vw;
        margin-bottom: 16vw;
        width: 80%;
        
    }
    .titulo{
        font-size: 6vw;
    }



    img{
        width: 30vw;
        height: auto;
        margin-left: auto;
        margin-right: auto;
    }
    
}
</style>