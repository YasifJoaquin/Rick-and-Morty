<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <div class="border border-double border-black w-3/5 h-screen flex justify-center items-center">
    <div class="border border-double border-yellow w-3/5 rounded-lg text-center bg-gray-800">
      <p class="text-green-500 text-5xl font-bold pt-6">Rick and Morty</p>
      <p class="mt-3 p-5 text-justify text-xl">
        Después de haber estado desaparecido durante casi 20 años, Rick Sanchez llega repentinamente
        a la puerta de la casa de su hija Beth para mudarse con ella y su familia. Aunque Beth le da
        la bienvenida a Rick a su casa, su esposo, Jerry, no está tan feliz con la reunión familiar.
        Jerry está preocupado por Rick, un científico sociópata, que usa el garaje como su laboratorio personal.
        En el laboratorio, Rick trabaja en varios dispositivos de ciencia ficción, algunos de los cuales podrían
        considerarse peligrosos. Pero eso no es todo lo que hace Rick que preocupa a Jerry. También emprende
        aventuras por todo el universo que a menudo involucran a sus nietos, Morty y Summer.
      </p>
    </div>
  </div>
</template>
