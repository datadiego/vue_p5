<script>
import WindowComposition from "../components/WindowComposition.vue"
import p5sketch from "../components/p5sketch.vue"

import img from '../assets/img_1.jfif';

export default {
  name: "Home",
  components: {
    WindowComposition,
    p5sketch
  },
  data(){
        return{
                img,
            skills : [
                {id: 1, text: "Desarrollo Web"},
                {id: 2, text: "Robótica Industrial"},
                {id: 3, text: "Netart / Arte Digital"},
            ],
        }
  }
};
</script>

<template>
        <!-- <img class="logo" src="../assets/smiley.png" alt="logo" /> -->
        <!-- <WindowComposition titulo="Sobre mí" texto="Soy un desarrollador web y artista digital multimedia de 32 años localizado en Granada." :imgPath="img" /> -->
        <p5sketch />
</template>

<script>

</script>

<style scoped>
.logo{
        width: 10vw;
        height: auto;
        border: 6px solid black;
        border-radius: 200px;
        position: absolute;
        top: 10vh;
        left: 70vw;
        transform: rotate(20deg);

        background-color: yellow;
}
</style>