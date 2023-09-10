<template>
  <div>
    <!-- <NuxtWelcome /> -->
    <TresCanvas window-size shadows alpha>
      <TresPerspectiveCamera :position="[20, 50, 50]" :fov="70" />
      <OrbitControls :target="[0, 15, 0]" />
      <TresMesh>
        <Suspense>
          <GLTFModel path="/models/3.glb" draco ref="modelRef" />
        </Suspense>
      </TresMesh>
      <!-- <TresDirectionalLight :position="[-4, 8, 4]" :intensity="1.5" cast-shadow /> -->
      <TresAmbientLight :intensity="5" />
    </TresCanvas>
  </div>
</template>

<script lang="ts" setup>
import { OrbitControls, GLTFModel } from "@tresjs/cientos";

// const { scene } = await useGLTF("/models/test.glb");
</script>
