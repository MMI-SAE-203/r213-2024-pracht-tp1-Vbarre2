<script setup lang="ts">
import { onErrorCaptured } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})

import { ref } from "vue";
const menuIsOpen = ref(false)
</script>

<template>
  <header>
<button
  @click="menuIsOpen = !menuIsOpen"
  aria-controls="mainNav"
  aria-expanded="true"
  class="rounded-full border-2 border-red-600 bg-red-300 px-2"
>
  menu
</button>
<!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
<nav id="mainNav">
  <Transition
  class="transition-transform duration-1000"
  enter-from-class="-translate-x-full"
  enter-to-class="translate-x-0"
  leave-active-class="-translate-x-full"
>
<ul v-show="menuIsOpen">
          <li><RouterLink to="/" class="text-red-500 underline"> Accueil </RouterLink></li>
          <li><RouterLink to="/donnee" class="text-red-500 underline"> Données </RouterLink></li>
        </ul>
  </Transition>
</nav>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
