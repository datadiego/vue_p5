<template>
<div class="container">
    <h1 class="titulo">* {{ titulo }}</h1>
  <div id="canvas" ref="p5Canvas"></div>
    <div class="info">
        <p class="entrada">AAAA</p>


    </div>
</div>
</template>
<script>
import { onMounted, ref } from 'vue';
import p5 from 'p5';

export default {
  setup() {
    const p5Canvas = ref(null);

    onMounted(() => {
      new p5((p) => {
        
        p.setup = () => {
          p.createCanvas(400, 400);
          p.background(255);
          p.fill(255);
          p.rectMode(p.CENTER)
          p.rect(200, 200, 100, 100)
        };

        p.draw = () => {
          p.ellipse(p.mouseX, p.mouseY, 50, 50);
        };
      }, p5Canvas.value);
    });

    return { p5Canvas };
  },
};
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 50vw;
    border: 3px solid var(--border);
    border-radius: 16px;
    margin: 0 auto;
    box-shadow: 15px 15px var(--shadow);
    margin-top: 1vw;
    margin-bottom: 5vw;
}
.titulo{
    font-size: 2.5vw;
    margin: 0;
    padding:1vw;
    background-color: var(--titlesBack);
    color: var(--titlesFront);
    border-bottom: 3px solid var(--border);
}
.entrada{
    font-size: 1.4vw;
    margin: 0;
    padding: 3vw;
    color: var(--text);
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
    flex-direction: column;
    align-items: center;
    background-color: var(--infoBack);
}

#canvas{
    background-color: var(--infoBack);
    display: flex;
    justify-content: center;
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
    .entrada{
        padding: 5vw;
        font-size: 3vw;
    }

    img{
        width: 30vw;
        height: auto;
        margin-left: auto;
        margin-right: auto;
    }
    
}
</style>