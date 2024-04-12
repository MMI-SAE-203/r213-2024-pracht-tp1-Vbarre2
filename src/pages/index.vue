
<script setup lang="ts">
import { ref } from "vue";
const sectionOpen = ref(1)
</script>

<template>
  <h1 class="text-2xl">Bonjour monde !</h1>
 <section>
    <button class="text-xl" @pointerdown="sectionOpen = 1">bouton 1</button>
    <p v-show="sectionOpen === 1">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magni assumenda suscipit sequi
      commodi maiores nam consequatur exercitationem fuga reprehenderit, molestias corporis eos sed
      incidunt iure blanditiis dolores, facere ratione odio!
    </p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 2">bouton 2</button>
    <p v-show="sectionOpen === 2">
      Ipsum commodi quo minus quisquam rem voluptatibus suscipit iusto blanditiis. Vero ab nobis
      explicabo. Hic corrupti mollitia ducimus facere. Id mollitia soluta quaerat reiciendis dolores
      harum eligendi quam consequuntur facilis?
    </p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = 3">bouton 3</button>
    <p v-show="sectionOpen === 3">
      In quidem iste consectetur aut, amet ratione corporis temporibus ab est molestias velit facere
      explicabo repudiandae deserunt sint omnis rerum error ut officiis consequuntur sunt beatae
      inventore. Illo, eum sunt?
    </p>
  </section>

</template>
